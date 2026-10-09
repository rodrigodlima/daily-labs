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
