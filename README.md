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


argocd application yaml: https://github.com/argoproj/argo-cd/blob/master/docs/operator-manual/application.yaml
https://argo-cd.readthedocs.io/en/stable/operator-manual/declarative-setup/

    k apply -f argocd_application.yaml


#### Argo Update

    k port-forward svc/create-react-demo -n create-react-demo   8081:80
    http://localhost:8081/
    show version 1.1

    then update deployment.yaml with new image tag v1.2

    http://localhost:8081/
    show version 1.2

<img width="1394" alt="step1" src="https://user-images.githubusercontent.com/491610/168952137-0d69c03d-44a4-46ca-82eb-f071305309cd.png">

<img width="1400" alt="step2" src="https://user-images.githubusercontent.com/491610/168952134-f55bef6c-4ddd-4081-95e0-f928cab283d5.png">

<img width="1440" alt="step3" src="https://user-images.githubusercontent.com/491610/168952129-a4f92126-ef6d-4093-a92f-c8cb42291614.png">
