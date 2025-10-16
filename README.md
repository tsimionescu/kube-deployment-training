# Kubernetes example app

Acest repository conține exerciții pentru a crea și deploya o aplicație simplă în Kubernetes. Aplicația este bazată pe https://github.com/kubernetes/examples/tree/master/web/guestbook-go .


### Linkuri
GitHub repo:
-  https://github.com/tsimionescu/kube-deployment-training

Cluster IPs: 
- Master: ssh lab@4.165.8.169
- Workers: http://4.223.137.80, http://20.240.94.5 

### Prereq

    apt install git build-essential
    # pentru instalat Docker, urmati instructiunile de aici : https://docs.docker.com/engine/install/
    git clone https://github.com/tsimionescu/kube-deployment-training.git

### Kubectl cheatsheet
    
    kubectl create namespace $MY_NAME  # creaza un namespace cu numele dat
    kubectl apply -f FILE              # creaza resursele din fisier
    kubectl get pods -n $ MY_NAME      # listeaza pod-urile deployed
    kubectl get svc -n NAME            # listeaza servciile deployed
    kubectl get deployments -n NAME    # listeaza deployments
    kubectl get nodes                  # listeaza master si worker nodes din cluster
