# argocd

### Installing Self Managing ArgoCD
ArgoCD has the ability to manage its own manifests.
In `argo-install` folder, 
- `kustomization.yaml` file points the raw manifest for ArgoCD.
- `resources/argocd-app.yaml` file instructs ArgoCD to watch the git repo (this repo, and in fact the very directory which the ArgoCD Application file lives)

To Deploy ArgoCD, the argocd namespace must be first created.
Although, the application file has the following config, we have to avoid the chicken and egg problem by creating the namespace for argocd to first exist
```
syncOptions:
  - CreateNamespace=true
```

Install ArgoCD using kubectl kustomize
```
kubectl apply -k ./argocd-install
```