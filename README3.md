
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
