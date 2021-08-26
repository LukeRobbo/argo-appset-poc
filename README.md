# argo-appset-poc

## env setup

- kustomize build k8s/infra/argo-cd | kubectl apply -f -

- port forward argo to access dashboard
    ```
    kubectl port-forward -n argocd svc/argocd-server 1111:80
    ```
- add access to your git repo [argo docs](https://argoproj.github.io/argo-cd/user-guide/private-repositories/)

- apply argo appset
    ```
    kustomize build k8s/argo-apps | kubectl apply -f -
    ```
- apps should then be created in your argocd ns (check the UI to verify)
