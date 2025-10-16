## Al doilea exercițiu - deployment in Kubernetes

În primul rând, avem nevoie de o cheie de SSH pentru a ne conecta la cluster:

    $ ssh-keygen 
    # nume fișier: my_key
    # nu e nevoie de passphrase
    # o data ce s-a generat:
    $ cat ./my_key.pub
    # copiem output pe Discord
    $ chmod 600 ./my_key

Apoi, vom edita cele două fișiere de aici pentru a avea un namespace unic:

    $ sed -i 's/namespace: /namespace: YOUR_NAME/g' *.yaml

Având un cluster existent pe CLUSTER_IP:

    $ ssh -i ./my_key lab@CLUSTER_IP
    (lab@CLUSTER_IP) $ mkdir YOUR_NAME
    (lab@CLUSTER_IP) $ exit
    $ scp guestbook.yaml lab@CLUSTER_IP:YOUR_NAME/
    $ scp redis.yaml lab@CLUSTER_IP:YOUR_NAME/
    $ ssh -i ./my_key lab@CLUSTER_IP
    (lab@CLUSTER_IP) $ cd YOUR_NAME
    (lab@CLUSTER_IP) $ kubectl create namespace -n YOUR_NAME
    (lab@CLUSTER_IP) $ kubectl apply -f redis.yaml
    (lab@CLUSTER_IP) $ kubectl apply -f guestbook.yaml
    (lab@CLUSTER_IP) $ kubectl get pods -n YOUR_NAME