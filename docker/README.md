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

## Build for multiple platforms

```bash
docker buildx build --platform linux/amd64,linux/arm64 -t user/app:1.0 --push .
```

## Show image layers

```bash
docker history --no-trunc <image>
```

## Run as non-root user

```bash
RUN useradd -r -u 10001 app
USER 10001
```

## Follow logs with timestamps

```bash
docker logs -f --since 10m -t <id>
```

## Disk usage overview

```bash
docker system df -v
```

## Healthcheck in Dockerfile

```bash
HEALTHCHECK --interval=30s --timeout=3s CMD curl -fs http://localhost:8080/health || exit 1
```

## Use .dockerignore

```bash
Keep .git, node_modules, .venv and build outputs out of the build context to speed up builds.
```
