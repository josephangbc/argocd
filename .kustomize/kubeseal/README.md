## Kubeseal

```
kubectl create secret generic mysecret --dry-run=client --from-literal foo=bar --output json | kubeseal | tee mysecret.yaml
```