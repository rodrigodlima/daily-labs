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

## Pods not running across the cluster

```bash
kubectl get pods -A --field-selector=status.phase!=Running
```

## Decode a secret

```bash
kubectl get secret <name> -o jsonpath='{.data.password}' | base64 -d
```

## Switch default namespace

```bash
kubectl config set-context --current --namespace=<ns>
```

## Create a kind cluster

```bash
kind create cluster --name lab --image kindest/node:v1.31.0
```

## Scale a deployment

```bash
kubectl scale deploy/<name> --replicas=3
```

## Pod logs from previous crash

```bash
kubectl logs <pod> --previous
```

## Labels as columns

```bash
kubectl get pods -L app,version
```

## Wait for a condition

```bash
kubectl wait --for=condition=available deploy/<name> --timeout=120s
```
