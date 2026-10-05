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

## Multi-stage build skeleton

```dockerfile
FROM golang:1.22 AS build
WORKDIR /src
COPY . .
RUN go build -o /app

FROM gcr.io/distroless/base
COPY --from=build /app /app
ENTRYPOINT ["/app"]
```

## Limit container resources

```bash
docker run --memory=512m --cpus=1.5 nginx
```

## Compose: wait for healthy dependency

```yaml
depends_on:
  db:
    condition: service_healthy
```

## Copy files out of a container

```bash
docker cp <id>:/var/log/app.log .
```
