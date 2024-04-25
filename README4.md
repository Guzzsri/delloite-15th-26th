```

kubectl get pods
  147  kubectl run -d --image httpd
  148  kubectl run ramanapp --image httpd
  149  kubectl get pods
  150  kubectl describe pod ramanapp

  156  kubectl run ramanapp2 --image httpd --labels "env=ramanprod"
  157  k describe pod ramanapp2
  158  kubectl describe pod ramanapp2
  159  clear
  160  docker ps
  161  crctl ps
  162  critl ps
  163  crictl ps -a

  179  docker run --rm -v `pwd`:/host docker.io/aquasec/kube-bench:latest install
  180  docker ps
  181  ./kube-bench 
  182  ./kube-bench | grep -i FAIL
  183  kubeadm.conf
  184  ps -ef | grep etcd
  185  chown etcd:etcd /var/lib/etcd
  186  clear
  187  vi /etc/kubernetes/manifests/kube-controller-manager.yaml 
  188  crictl ps 
  189  ./kube-bench | grep -i FAIL
  190  clear


  ```
