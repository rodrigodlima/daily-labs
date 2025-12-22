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
