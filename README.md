k8s-hardway-cilium

This branch aims at configuring k8s, the hardway. A VM is created in GCP and the lone VM serves as control plane node & worker node. Detailed information of each of the configuration files below

1. runc & containerd.txt -- Installs runc & containerd. Also creates containerd unit service file along with configuration
2. kubelet & certs.txt
    /etc/hosts entry to be modified to have kubernetes.svc.cluster.local
    config & kubeconfig file of kubelet
    Generate CA certs & kubelet certs
3. kubectl.txt -- Install kubectl and kubeconfig for kubectl to refer to and the certs to present to API for the admin role
4. crictl.txt -- Install crictl and set env variable, CONTAINER_RUNTIME_ENDPOINT, on the server
5. etcd.txt -- Install etcdctl and etcd manifest file to run etcd as a static pod
6. apiserver & certs.txt -- manifest file of apiserver. runs apiserver as static pod, generates certs for the apiserver and service accounts
7. controller manager & certs.txt -- manifest file of controller manager. runs controller manager as static pod, generates certs, and kubeconfig
8. scheduler & certs.txt -- manifest file of scheduler. runs scheduler as static pod, generates certs, and kubeconfig
9. kube-api-server-to-kubelet-rbac.txt -- kube-apiserver has the necessary permissions to communicate with the kubelets on the cluster nodes
10. Cilium.txt -- Installs cilium using helm.
