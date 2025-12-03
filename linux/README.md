# Linux notes

Short, practical notes collected while studying and testing.

## Find the biggest directories

```bash
du -xh --max-depth=1 / 2>/dev/null | sort -rh | head -20
```
