## [Back to Top](../README.md)

# Setting Up ArgoCD

![Image of ArgoCD Logo](../src/img/argocd/logo.png)

kubectl create ns argocd

helm repo add argo https://argoproj.github.io/argo-helm

helm install my-argo-cd argo/argo-cd --version 6.7.8 --namespace argocd

In order to access the server UI you have the following options:

1. kubectl port-forward service/my-argo-cd-argocd-server -n argocd 8080:443

    and then open the browser on http://localhost:8080 and accept the certificate

2. enable ingress in the values file `server.ingress.enabled` and either
      - Add the annotation for ssl passthrough: https://argo-cd.readthedocs.io/en/stable/operator-manual/ingress/#option-1-ssl-passthrough
      - Set the `configs.params."server.insecure"` in the values file and terminate SSL at your ingress: https://argo-cd.readthedocs.io/en/stable/operator-manual/ingress/#option-2-multiple-ingress-objects-and-hosts

helm upgrade my-argo-cd argo/argo-cd --version 6.7.8 --values values.yaml --namespace argocd


After reaching the UI the first time you can login with username: admin and the random password generated during the installation. You can find the password by running:

kubectl -n argocd get secret argocd-initial-admin-secret -o jsonpath="{.data.password}" | base64 -d


username: admin
password: P@ssword