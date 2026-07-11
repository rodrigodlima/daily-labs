# Git notes

Short, practical notes collected while studying and testing.

## Undo the last commit keeping changes

```bash
git reset --soft HEAD~1
```

## Show files changed in a commit

```bash
git show --stat <sha>
```

## Interactive staging of hunks

```bash
git add -p
```

## Find who changed a line

```bash
git blame -L 10,20 path/to/file
```

## Clean untracked files (dry run first)

```bash
git clean -nd && git clean -fd
```

## Rewrite last commit message

```bash
git commit --amend
```

## Stash including untracked

```bash
git stash push -u -m 'wip'
```

## Bisect a regression

```bash
git bisect start
git bisect bad
git bisect good v1.2.0
```

## Worktrees for parallel branches

```bash
git worktree add ../hotfix hotfix/1.2.1
```

## Log as graph

```bash
git log --oneline --graph --decorate --all
```

## Cherry-pick a range

```bash
git cherry-pick A^..B
```

## Sign commits with SSH key

```bash
git config --global gpg.format ssh
git config --global user.signingkey ~/.ssh/id_ed25519.pub
```

## Search the history for a string

```bash
git log -S 'functionName' --oneline
```

## Delete merged local branches

```bash
git branch --merged main | grep -v ' main$' | xargs -r git branch -d
```

## Diff only names between branches

```bash
git diff --name-only main...feature
```

## Shallow clone

```bash
git clone --depth 1 <url>
```

## Restore a file from another branch

```bash
git restore --source main -- path/to/file
```

## Aliases

```bash
git config --global alias.st 'status -sb'
git config --global alias.lg 'log --oneline --graph'
```

## Sparse checkout

```bash
git sparse-checkout init --cone
git sparse-checkout set services/api
```
