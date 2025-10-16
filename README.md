## Kubernetes example app

This example shows how to build a simple multi-tier web application using Kubernetes and Docker. It is based on https://github.com/kubernetes/examples/tree/master/web/guestbook-go .


## Links
GitHub repo: https://github.com/tsimionescu/kube-deployment-training
Cluster IPs: 
- Master: ssh lab@4.165.8.169
- Workers: http://4.223.137.80, http://20.240.94.5 

## Prereq

    apt install git docker build-essential
    git clone https://github.com/tsimionescu/kube-deployment-training.git

## Kubectl cheatsheet
    
    kubectl create namespace $MY_NAME
    kubectl apply -f FILE
    kubectl get pods -n $ MY_NAME
