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
