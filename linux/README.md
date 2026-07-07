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

## CPU and IO per process

```bash
pidstat -u -d 1 5
```

## Persist sysctl change

```bash
echo 'vm.max_map_count=262144' | sudo tee /etc/sysctl.d/99-es.conf && sudo sysctl --system
```

## Count lines per extension

```bash
find . -type f -name '*.py' | xargs wc -l | sort -n | tail
```

## Show routing table

```bash
ip route show
```

## DNS lookup with dig short

```bash
dig +short example.com A
```

## Check certificate expiry

```bash
echo | openssl s_client -connect example.com:443 2>/dev/null | openssl x509 -noout -dates
```

## Create a swap file

```bash
sudo fallocate -l 2G /swapfile && sudo chmod 600 /swapfile && sudo mkswap /swapfile && sudo swapon /swapfile
```

## Tar with progress and compression

```bash
tar -I 'zstd -T0' -cf backup.tar.zst /data
```
