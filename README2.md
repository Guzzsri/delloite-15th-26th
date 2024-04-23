```


root@ip-172-31-38-169:~# cat dockerfile 
FROM centos:7
MAINTAINER  Raman Khanna raman.khanna@TechLanders.com
RUN mkdir /data
RUN yum update -y
RUN yum -y install httpd   php
RUN echo " Delloite  Deals in DevOps and Cloud" > /var/www/html/index.html
EXPOSE 80
VOLUME  /data
RUN echo "httpd" >> /root/.bashrc
CMD ["/bin/bash"]









docker images
  135  vi dockerfile
  136  cat /etc/os-release 
  137  cat dockerfile 
  138  netstat -tulnp
  139  which httpd
  140  which apache2
  141  vi dockerfile 
  142  ls
  143  docker images
  144  docker ps -a
  145  docker build -t webapp:v1 .
  146  ls
  147  docker images
  148  docker ps -a
  149  docker run -dit --name c1 -p 8080:80 webapp:v1
  150  docker ps
  151  docker exec -it --name c1 ls
  152  docker exec -it c1 ls
  153  docker exec -it c1 /bin/bash
  154  docker ps
  155  curl 172.31.38.169:8080



```
