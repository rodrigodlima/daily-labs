# Kubernetes notes

Short, practical notes collected while studying and testing.

## Watch pod events in a namespace

```bash
kubectl get events -n <ns> --sort-by=.lastTimestamp -w
```
