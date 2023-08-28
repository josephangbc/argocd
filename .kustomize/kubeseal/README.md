## Kubeseal

```
kubectl create secret generic mysecret -n cert-manager --dry-run=client --from-literal foo=bar --output json | kubeseal | tee mysecret.yaml
```
