helm repo add jupyterhub https://jupyterhub.github.io/helm-chart/

helm install my-jupyterhub jupyterhub/jupyterhub --version 4.0.0-0.dev.git.6568.he1cdef40 --namespace jh