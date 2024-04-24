
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
