## K3D

Just start with Docker Desktop:

    k3d cluster create --config democluster.yaml


    kubectl cluster-info
    k3d_demo ➤ kubectl cluster-info
    Kubernetes control plane is running at https://0.0.0.0:6443
    CoreDNS is running at https://0.0.0.0:6443/api/v1/namespaces/kube-system/services/kube-dns:dns/proxy
    Metrics-server is running at https://0.0.0.0:6443/api/v1/namespaces/kube-system/services/https:metrics-server:https/proxy

    To further debug and diagnose cluster problems, use 'kubectl cluster-info dump'.


k get nodes

kubectl config get-contexts


k3d cluster delete democluster

k3d cluster list

k3d cluster  start democluster


## Argo

* setup argo: [https://argo-cd.readthedocs.io/en/stable/getting_started/#1-install-argo-cd](https://argo-cd.readthedocs.io/en/stable/getting_started/#1-install-argo-cd)

    kubectl create namespace argocd
    kubens argocd

    
    kubectl apply   -f https://raw.githubusercontent.com/argoproj/argo-cd/stable/manifests/install.yaml

 

    k get pods --watch 
    k port-forward svc/argocd-server 8080:443 
    k get secret argocd-initial-admin-secret -o yaml
    base64 decode the password

    open localhost:8080 login with `admin` and password


