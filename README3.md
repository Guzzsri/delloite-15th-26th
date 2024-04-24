
```
https://aquasecurity.github.io/trivy/v0.50/


wget https://github.com/aquasecurity/trivy/releases/download/v0.18.3/trivy_0.18.3_Linux-64bit.deb
sudo dpkg -i trivy_0.18.3_Linux-64bit.deb



trivy
  194  ls
  195  wget https://github.com/aquasecurity/trivy/releases/download/v0.18.3/trivy_0.18.3_Linux-64bit.deb
  196  ls
  197  sudo dpkg -i trivy_0.18.3_Linux-64bit.deb
  198  ls
  199  trivy
  200  clear
  201  docker images
  202  trivy 
  203  trivy image webapp:v1
  204  clear
  205  trivy image -h
  206  trivy image webapp:v1 --severity CRITICAL
  207  trivy image webapp:v1 grep
  208  docker images
  209  trivy image webapp:v1 | grep CRITICAL
  210  trivy image --severity CRITICAL webapp:v1
  211  trivy image --severity CRITICAL,HIGH webapp:v1




```



```


ifconfig
  215  ip a
  216  clear
  217  docker network ls
  218  docker ps 
  219  docker ps-a
  220  docker ps -a
  221  ip a
  222  clear
  223  docker ps
  224  ip a
  225  clear
  226  docker ps -a
  227  docker start httpdserver
  228  docker ps -a
  229  docker inspect sonarqube
  230  docker inspect httpdserver
  231  clear
  232  docker ps
  233  docker run -d --name nginx -P nginx:latest
  234  docker ps
  235  docker rm -f nginx
  236  docker rm -f httpdserver
  237  clear
  238  docker network ls
  239  docker network describe bridge
  240  docker network inspect bridge
  241  ip a
  242  clear
  243  docker network inspect host
  244  clear
  245  docker run -d --name httpd --network host
  246  docker run -d --name httpd  --network host httpd
  247  docker ps
  248  netstat -tulnp
  249  apt install net-tools
  250  netstat -tulnp
  251  clear
  252  docker ps
  253  docker inspect httpd
  254  clear
  255  docker ps
  256  docker run -d --name redis  --network host redis
  257  docker ps
  258  netstat -tulnp
  259  docker run -d --name nginx  --network host nginx
  260  docker ps
  261  docker ps -a
  262  docker logs nginx
  263  docker run -d --name nginx  --network none nginx
  264  docker run -d --name nginx2  --network none nginx
  265  docker ps
  266  netstat -tulnp


```


```

ON MASTER :

vi script




#!/bin/bash
sudo apt update -y
sudo apt install docker.io -y
sudo mkdir -p -m 755 /etc/apt/keyrings
curl -fsSL https://pkgs.k8s.io/core:/stable:/v1.29/deb/Release.key | sudo gpg --dearmor -o /etc/apt/keyrings/kubernetes-apt-keyring.gpg
echo 'deb [signed-by=/etc/apt/keyrings/kubernetes-apt-keyring.gpg] https://pkgs.k8s.io/core:/stable:/v1.29/deb/ /' | sudo tee /etc/apt/sources.list.d/kubernetes.list
sudo apt-get update
sudo apt-get install -y kubelet kubeadm kubectl

#on master
#kubeadm init --pod-network-cidr=10.244.0.0/16 >> cluster_initialized.txt
kubeadm init --pod-network-cidr=192.168.0.0/16 >> cluster_initialized.txt
mkdir /root/.kube
cp /etc/kubernetes/admin.conf /root/.kube/config
kubectl apply -f https://raw.githubusercontent.com/projectcalico/calico/v3.25.0/manifests/calico.yaml
#kubectl apply -f https://raw.githubusercontent.com/coreos/flannel/master/Documentation/kube-flannel.yml
systemctl restart kubelet.service
kubeadm token create --print-join-command





    4  sh script 
    5  history
    6  clear
    7  alias k=kubectl
    8  k get nodes


---

ON WORKERS : BOTH 

 vi script




#!/bin/bash
sudo apt update -y
sudo apt install docker.io -y
sudo mkdir -p -m 755 /etc/apt/keyrings
curl -fsSL https://pkgs.k8s.io/core:/stable:/v1.29/deb/Release.key | sudo gpg --dearmor -o /etc/apt/keyrings/kubernetes-apt-keyring.gpg
echo 'deb [signed-by=/etc/apt/keyrings/kubernetes-apt-keyring.gpg] https://pkgs.k8s.io/core:/stable:/v1.29/deb/ /' | sudo tee /etc/apt/sources.list.d/kubernetes.list
sudo apt-get update
sudo apt-get install -y kubelet kubeadm kubectl





    3  sh script 
    4  kubeadm join 172.31.59.103:6443 --token npvgez.dlrc6n9ohj29020x --discovery-token-ca-cert-hash sha256:6410957ea7f3cc06c18014c5fcd960eec30fe6a1a00733725451cb6fcbebe7d3


```


```


alias k=kubectl
    8  k get nodes
    9  history
   10  k get nodes
   11  clear
   12  k 
   13  clear
   14  k get pods
   15  k get ns
   16  clear
   17  k get nodes
   18  k k get pods
   19  k get pods
   20  k getns
   21  k get ns
   22  clear
   23  k get pods -n kube-system
   24  k get pods
   25  docker ps
   26  clear
   27  k get pods -n kube-system 
   28  k get pods -o wide
   29  k get pods -o wide -n kube-system
   30  clear
   31  k run ramanapp --image httpd 
   32  k get pods
   33  k get pods -o wide -n kube-system
   34  clear
   35  k get pods
   36  k get pods -o wide
   37  cat script 
   38  clear
   39  k get pods
   40  k get pods -o wide
   41  k get ns
   42  k get pods -o wide
   43  k get pods -nkube-system
   44  clear
   45  k get api-resources
   46  k api-resources
   47  clear

   55  k get pods
   56  k create ns raman

   48  k get pods
   49  k run ramanapp2 --image httpd 
   50  k get pods
   51  k get pods -o wide
   52  k delete pod ramanapp
   53  k get pods
   54  clear

   57  k get ns
   58  k create deployment ramandep --image httpd --replicas 5 -n raman
   59  k get pods
   60  k get pods -n raman
   61  k get pods -n raman -o wide
   62  k scale deploy ramandep --replicas 10 -n raman
   63  k get pods -n raman -o wide
   64  k delete pod ramandep-676757c4b5-rw59z
   65  k delete pod ramandep-676757c4b5-rw59z -n raman
   66  k get pods -n raman -o wide
   67  history
root@master:~# k get pods -n raman -o wide


```
