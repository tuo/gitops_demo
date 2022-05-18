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


#### nginx

kubectl create deployment nginx --image=nginx
kubectl create service nodeport nginx --tcp=80:80