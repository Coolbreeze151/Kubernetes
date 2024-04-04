
## [Back to Top](../README.md)

# Jupyterhub
## Notebooks for users to work with Data

![Image of Argo CD Logo](../src/img/jupyter/logo.png)
helm repo add jupyterhub https://jupyterhub.github.io/helm-chart/

helm install my-jupyterhub jupyterhub/jupyterhub --version 4.0.0-0.dev.git.6568.he1cdef40 --namespace jh