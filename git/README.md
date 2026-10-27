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
