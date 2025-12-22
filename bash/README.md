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
