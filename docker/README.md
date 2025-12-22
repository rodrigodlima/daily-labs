# Docker notes

Short, practical notes collected while studying and testing.

## Remove dangling images

```bash
docker image prune -f
```

## Inspect container IP

```bash
docker inspect -f '{{range .NetworkSettings.Networks}}{{.IPAddress}}{{end}}' <id>
```
