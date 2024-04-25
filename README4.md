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




```



https://helm.sh/docs/intro/install/


https://artifacthub.io/packages/search?verified_publisher=true



admin
prom-operator






clear
  205  curl -fsSL -o get_helm.sh https://raw.githubusercontent.com/helm/helm/main/scripts/get-helm-3
  206  ls
  207  chmod 700 get_helm.sh
  208  ./get_helm.sh
  209  ls
  210  helm
  211  clear
  212  netstat -tulnp
  213  apt install net-tools
  214  netstat -tulnp
  215  clear
  216  helm repo add prometheus-community https://prometheus-community.github.io/helm-charts
  217  helm repo list
  218  helm install my-kube-prometheus-stack prometheus-community/kube-prometheus-stack --version 58.2.2
  219  k get all
  220  clear
  221  k get svc
  222  k edit svc my-kube-prometheus-stack-grafana
  223  k get deploy
  224  k get svc 
  225  k edit svc my-kube-prometheus-stack-operator
  226  k get svc 
  227  k edit svc y-kube-prometheus-stack-prometheus
  228  k edit svc my-kube-prometheus-stack-prometheus
  229  k get svc 
  230  clear
  231  k get pods
  232  k get pods -n raman
  233  clear



http://18.209.179.168:31872/graph?g0.expr=sum(node_namespace_pod_container%3Acontainer_cpu_usage_seconds_total%3Asum_irate%7Bnamespace%3D%22raman%22%2C%20pod%3D%22ramanapp%22%7D)%20by%20(container)&g0.tab=0&g0.display_mode=lines&g0.show_exemplars=0&g0.range_input=1h



http://18.209.179.168:31930/d/200ac8fdbfbb74b39aff88118e4d1c2c/kubernetes-compute-resources-node-pods?orgId=1&refresh=10s&var-datasource=default&var-cluster=&var-node=master&var-node=w1&var-node=w2


https://github.com/dotdc/grafana-dashboards-kubernetes

```
