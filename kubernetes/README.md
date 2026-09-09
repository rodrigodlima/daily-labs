# Kubernetes notes

Short, practical notes collected while studying and testing.

## Watch pod events in a namespace

```bash
kubectl get events -n <ns> --sort-by=.lastTimestamp -w
```

## Debug with ephemeral container

```bash
kubectl debug -it <pod> --image=busybox --target=<container>
```

## Restart a deployment

```bash
kubectl rollout restart deploy/<name>
```

## Get pod resource usage

```bash
kubectl top pods -A --sort-by=memory
```

## Port-forward a service

```bash
kubectl port-forward svc/<name> 8080:80
```
