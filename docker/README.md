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
