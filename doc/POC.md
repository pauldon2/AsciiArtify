

Step 1. \
Configure network access to the administration port

```
kubectl port-forward svc/argocd-server -n argocd 8080:443&
```

Step 2. \
Open URL https://127.0.0.1:8080

Step 3a. \
Install ArgoCD CLI
https://argo-cd.readthedocs.io/en/stable/cli_installation/

Step 4a. \
Get admin password
```
argocd admin initial-password -n argocd
```

## OR

Step 3b. \
```
kubectl -n argocd get secret argocd-initial-admin-secret -o jsonpath="{.data.password}"|base64 -d;echo
```

Step 5. \

Login as admin and use password from step 4a or 3b.


