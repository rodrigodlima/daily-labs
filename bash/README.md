# Bash notes

Short, practical notes collected while studying and testing.

## Strict mode

```bash
set -euo pipefail
IFS=$'\n\t'
```

## Default value for variables

```bash
name="${1:-world}"
```

## Loop over lines safely

```bash
while IFS= read -r line; do echo "$line"; done < file.txt
```

## Trap cleanup

```bash
tmp=$(mktemp -d)
trap 'rm -rf "$tmp"' EXIT
```

## Parallel jobs with xargs

```bash
ls *.log | xargs -P4 -I{} gzip {}
```

## Here-doc without expansion

```bash
cat <<'EOF'
$HOME is not expanded here
EOF
```

## Arrays

```bash
arr=(a b c)
for i in "${arr[@]}"; do echo "$i"; done
echo "len=${#arr[@]}"
```
