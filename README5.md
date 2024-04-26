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
