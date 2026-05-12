# Linux notes

Short, practical notes collected while studying and testing.

## Find the biggest directories

```bash
du -xh --max-depth=1 / 2>/dev/null | sort -rh | head -20
```

## Which process holds a port

```bash
ss -ltnp | grep :8080
```

## Follow systemd unit logs

```bash
journalctl -u nginx -f --since '10 min ago'
```
