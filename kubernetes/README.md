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

## Explain a field

```bash
kubectl explain deployment.spec.strategy
```

## Dry-run and generate YAML

```bash
kubectl create deploy web --image=nginx --dry-run=client -o yaml > web.yaml
```

## Node drain for maintenance

```bash
kubectl drain <node> --ignore-daemonsets --delete-emptydir-data
```

## Rollback a deployment

```bash
kubectl rollout undo deploy/<name> --to-revision=2
```
