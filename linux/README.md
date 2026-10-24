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

## Check disk inodes

```bash
df -i
```

## Show open files by process

```bash
lsof -p <pid>
```

## Trace syscalls of a command

```bash
strace -f -e trace=network curl -s example.com
```

## Test TCP connectivity without telnet

```bash
timeout 3 bash -c '</dev/tcp/10.0.0.5/443' && echo open
```

## Check listening services quickly

```bash
sudo ss -tulpn
```

## Watch a command output

```bash
watch -n 2 -d 'free -h'
```

## Kernel ring buffer with human timestamps

```bash
dmesg -T | tail -50
```

## Find files modified in the last day

```bash
find /var/log -type f -mtime -1 -ls
```
