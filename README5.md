```


jenkins : heart ...

sdlc : security tools

trufflehog >> code >> sast >> build (mvn) >> artefact >> dockerfile >> docker build >> trivy >> docker image  >> container app >> dast

 

code >> build (mvn) >> artefact >> dockerfile >> docker build >> docker image  >> container app 


sonarqube :

admin
admin1


http://35.173.204.177:9000/projects


---

jenkins url :

http://35.173.204.177:8080/


raman
raman

-----------


netstat -tulnp
  267  clear
  268  history
  269  clear
  270  docker stats
  271  clear
  272  docker ps -a
  273  trivy
  274  docker start sonarqube
  275  clear
  276  docker ps
  277  clear
  278  echo deb [signed-by=/usr/share/keyrings/jenkins-keyring.asc]     https://pkg.jenkins.io/debian-stable binary/ | sudo tee     /etc/apt/sources.list.d/jenkins.list > /dev/null
  279  sudo apt-get update
  280  sudo apt-get install fontconfig openjdk-17-jre
  281  sudo apt-get install jenkins
  282  systemctl status jenkins
  283  clear
  284  netstat -tulnp
  285  clear
  286  cat /var/lib/jenkins/secrets/initialAdminPassword
  287  cat /etc/passwd
  288  clear
  289  systemctl status jenkins
  290  vi /lib/systemd/system/jenkins.service
  291  systemctl daemon-reload
  292  systemctl restart jenkins
  293  cd /var/lib/jenkins/
  294  ls


```


```

-----
freestyle project ...




code >> sast (sonarqube ) >> build (mvn) >> artefact >> dockerfile >> docker build >> trivy >> docker image  >> container app >> dast




install plugin
-- manage jenkins >> installed sonarqube scanner plugin



connected sonarqube with jenkins...
-- system >> added sonaqube server on jenkins


tools >> sonarqube tool gets installed 




------

in our pipeline :
prepared sonarqube scanner env


added a build step for analysis propertoes:
sonar.projectName=test
sonar.projectKey=test
sonar.sources=src/main



sonar new token : sqa_f2c2ac13525bb3a29d9f947bf0f417317d44601c



================================

```



```


================================


add mvn tool in manage jenkins >> tool 



build the code >> created the image >> ran it as a container ....


docker rm -f mynewcontainer
docker rmi `docker images`|| echo "Command 3 failed with exit code $?"
docker build -t image-name:version .
trivy --no-progress --exit-code 1 --severity HIGH,CRITICAL image-name:version
docker run -d -p 8081:8080 --name mynewcontainer image-name:version


===========================


fromgitbash locally ,polling the pipleine:


 git clone https://github.com/ramannkhanna2/devops-maven-docker.git
  503  clear
  504  cd devops-maven-docker/
  505  ls
  506  ls
  507  cd src/
  508  ls
  509  cd main/
  510  ls
  511  cd java/
  512  ls
  513  cd webapp/
  514  ls
  515  vi LoginServlet.java
  516  git add .
  517  git commit -m "made changes "
  518  git push origin master

===================================

```
