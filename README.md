```

https://forms.office.com/r/zJ7bWVPGj1

```


```
server creation :

us-east-1

ami-0cd59ecaf368e5ccf, ubuntu :20.04

created keypair

sg created


connect to instance
```


```

iam roles :

ways to connect to aws account :
ui :
cli : aws cli
sdk : botocore 


authentication : first way 
aws configure : access , 






aws roles : authentication 2nd way ,prefeered
created a role with s3 permissions 

attach it to my instance




    1  clear
    2  aws
    3  clear
    4  aws s3 ls
    5  apt  install awscli
    6  apt update -y
    7  apt  install awscli
    8  clear
    9  aws
   10  clear
   11  aws s3 ls
   12  aws configure
   13  aws s3 ls
   14  clear
   15  ls -a
   16  cd .ssh/
   17  ls
   18  cd ..
   19  ls
   20  ls-a
   21  l s-a
   22  ls -a
   23  cd .aws
   24  ls
   25  cat config
   26  cat credentials
   27  aws s3ls
   28  aws clear
   29  clear
   30  aws -h
   31  aws help
   32  clear
   33  aws iam -h
   34  aws iam help
   35  aws iam  list-users
   36  ls -a
   37  cat credentials
   38  ls
   39  cd ..
   40  ls
   41  ls -a
   42  rm -rf .aws
   43  clear
   44  aws s3 ls
   45  aws iam  list-users
   46  aws s3 ls
   47  ls -a
   48  aws s3 ls
   49  aws iam list-users
   50  ls -a
aws ec2 describe-instances --region us-east-1

aws ec2 describe-instances --region us-east-1 --query 'Reservations[*].Instances[*].[InstanceId]'

```
```
install apache2 on server

apt install apache2

manage sg and nacl to switch traffic across however u like

``` 


```
encryption kms example :

aws encryption :

aws own managed keys : by default
u create ur kms cmk on kms







aws s3 ls
   62  ls -a
   63  clear
   64  vi ExampleSecretFile.txt
   65  ls
   66  cat ExampleSecretFile.txt 
   67* aws kms decrypt  ExampleSecretFileEncrypted.base64
   68  ls
   69  cat ExampleSecretFileEncrypted.base64
   70  cat ExampleSecretFileEncrypted.base64 | base64 --decode > ExampleSecretFileEncrypted
   71  ls
   72  clear
   73  cat ExampleSecretFileEncrypted
   74  ls
   75  aws kms decrypt --ciphertext-blob fileb://ExampleSecretFileEncrypted   --output text --query Plaintext > ExampleFileDecrypted.base64  --region eu-west-2
   76  aws kms decrypt --ciphertext-blob fileb://ExampleSecretFileEncrypted   --output text --query Plaintext > ExampleFileDecrypted.base64  --region us-east-1
   77  ls
   78  cat ExampleFileDecrypted.base64
   79  cat ExampleFileDecrypted.base64 | base64 --decode > ExampleFileDecrypted.txt
   80  ls
   81  cat xampleFileDecrypted.txt
   82  cat exampleFileDecrypted.txt
   83  cat ExampleFileDecrypted.txt

```


```
cloudshell:

[root@ip-10-136-41-188 ~]# history
    1  ssh -i "raman-nv-delloite.pem" ubuntu@ec2-3-88-158-9.compute-1.amazonaws.com
    2  vi raman.pem
    3  ls
    4  ssh -i "raman.pem" ubuntu@ec2-3-88-158-9.compute-1.amazonaws.com
    5  ls -ltr
    6  chmod 400 raman.pem 
    7  ls -ltr
    8  ssh -i "raman.pem" ubuntu@ec2-3-88-158-9.compute-1.amazonaws.com

```


```
created an alarm , and set up a threshold of 50 cpu utilization..

stressing the cpu :

apt install stress
stress --cpu 16

```

```

secrets manager :



--- create a secret in sm

-- write the code 


-https://boto3.amazonaws.com/v1/documentation/api/latest/reference/services/secretsmanager/client/get_secret_value.html





root@ip-172-31-18-82:~# cat sm.py 
import boto3
from botocore.exceptions import ClientError

def get_secret():
    secret_name = "test-secret"
    region_name = "us-east-1"

    # Create a Secrets Manager client
    session = boto3.session.Session()
    client = session.client(
        service_name='secretsmanager',
        region_name=region_name
    )

    try:
        get_secret_value_response = client.get_secret_value(
            SecretId=secret_name
        )
    except ClientError as e:
        # For a list of exceptions thrown, see
        # https://docs.aws.amazon.com/secretsmanager/latest/apireference/API_GetSecretValue.html
        raise e

    secret = get_secret_value_response['SecretString']

    return secret

# Call the function and print the secret
secret_value = get_secret()
print(secret_value)








vi sm.py
  119  cat sm.py 
  120  clear
  121  pip 
  122  python --version
  123  apt install python3-pip
  124  pip install virtualenv
  125  python3 -m venv testenv 
  126  apt install python3.8-venv
  127  ls
  128  rm -rf testenv/
  129  python3 -m venv testenv 
  130  ls
  131  source testenv/bin/activate
  132  cat sm.py 
  133  pip install boto3
python3 sm.py




(testenv) root@ip-172-31-18-82:~# cat sm.py 
import boto3
import json
from botocore.exceptions import ClientError

def get_secret():
    secret_name = "test-secret"
    region_name = "us-east-1"

    # Create a Secrets Manager client
    session = boto3.session.Session()
    client = session.client(
        service_name='secretsmanager',
        region_name=region_name
    )

    try:
        get_secret_value_response = client.get_secret_value(
            SecretId=secret_name
        )
    except ClientError as e:
        # For a list of exceptions thrown, see
        # https://docs.aws.amazon.com/secretsmanager/latest/apireference/API_GetSecretValue.html
        raise e

    secret = get_secret_value_response['SecretString']
    # Convert the secret string to a list (assuming it's JSON-formatted)
    secret_list = json.loads(secret)
    return secret_list

# Call the function and print the secret
secret_value = get_secret()
print(secret_value['password'])



```

```

static -horusec :



static testing : horusec 
  https://github.com/juice-shop/juice-shop


git clone https://github.com/juice-shop/juice-shop.git
  189  clear
  190  ls
  191  history
  192  clear
  193  ls
  194  cd juice-shop/
  195  ls
  196  clear
  197  curl -fsSL https://raw.githubusercontent.com/ZupIT/horusec/master/deployments/scripts/install.sh | bash -s latest
  198  apt install jq
  199  curl -fsSL https://raw.githubusercontent.com/ZupIT/horusec/master/deployments/scripts/install.sh | bash -s latest
  200  horusec
  201  clear
  202  horusec
  203  clear
  204  horusec -h
  205  clear
  206  ls
  207  horusec -h
  208  clear
  209  horusec -p .
  210  clear
  211  ls
  212  horusec start -p .
  213  clear
  214  horusec start -p .
  215  horusec start
  216  clear
  217  ls
  218  horusec start -p . --disable-docker="true"


```
-------------------------------------------------------------------

```
DAST :

docker files >> docker image >> docker container
dast : owasp zap 
 
docker installation :
https://docs.docker.com/engine/install/ubuntu/ :

  261  sudo apt-get update
  262  sudo apt-get install ca-certificates curl
  263  sudo install -m 0755 -d /etc/apt/keyrings
  264  sudo curl -fsSL https://download.docker.com/linux/ubuntu/gpg -o /etc/apt/keyrings/docker.asc
  265  sudo chmod a+r /etc/apt/keyrings/docker.asc


echo \
  "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.asc] https://download.docker.com/linux/ubuntu \
  $(. /etc/os-release && echo "$VERSION_CODENAME") stable" | \
  sudo tee /etc/apt/sources.list.d/docker.list > /dev/null



  267  sudo apt-get update
  268  sudo apt-get install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin





rm -rf horusec-config.json 
  251  clear
  252  ls
  253  cd ..
  254  ls
  269  docker ps
  270  docker pull bkimminich/juice-shop
  271  docker images
  277  docker run -d -p 81:3000 bkimminich/juice-shop
  278  docke ps
  279  docker ps


-- after deployingthe application

-- https://www.zaproxy.org/docs/docker/baseline-scan/
https://www.zaproxy.org/docs/alerts/


docker run -t ghcr.io/zaproxy/zaproxy:stable zap-baseline.py -t http://18.215.157.2:81



docker run -v $(pwd):/zap/wrk/:rw -t -u $(id -u):$(id -g) ghcr.io/zaproxy/zaproxy:stable zap-baseline.py -t http://18.232.148.71:81 -r dastreport.html





docker rm -f `docker ps -aq`
  286  clear
  287  docker ps -a
  288  docker pull bkimminich/juice-shop
  289  docker images
  290  docker run -d -p 81:3000 bkimminich/juice-shop
  291  docker ps
  292  docker run -t ghcr.io/zaproxy/zaproxy:stable zap-baseline.py -t http://18.215.157.2:81
docker ps -a
  295  docker start 04b8c7b44008
  296  docker start 7012eb4af12b
  297  docker ps
  298  pwd
  299  docker run -v $(pwd):/zap/wrk/:rw -t -u $(id -u):$(id -g) ghcr.io/zaproxy/zaproxy:stable zap-baseline.py -t http://18.232.148.71:81 -r dastreport.html
  300  ls
  301  clear
  302  cat dastreport.html 
  303  clear
  304  which httpd
  305  systemctl status apache2
  306  which apache2
  307  netstat -tulnp
  308  apt install net-tools
  309  netstat -tulnp
  310  cd /var/www/
  311  ls
  312  cd html/
  313  ls
  314  cp /root/dastreport.html .
  315  ls
  316  mv index.html index

----

```

```

SRE IMPORTANT LINKS :

Difference Between DevOps and SRE :

https://www.youtube.com/watch?v=uTEL8Ff1Zvk&list=PLIivdWyY5sqJrKl7D2u-gmis8h9K66qoj&index=1


SLIs, SLOs, SLAs :

https://www.youtube.com/watch?v=tEylFyxbDLE&list=PLIivdWyY5sqJrKl7D2u-gmis8h9K66qoj&index=2


Risk and Error Budgets :

https://www.youtube.com/watch?v=y2ILKr8kCJU&list=PLIivdWyY5sqJrKl7D2u-gmis8h9K66qoj&index=3

Toil :

https://www.youtube.com/watch?v=IvQ-15-yE_c&list=PLIivdWyY5sqJrKl7D2u-gmis8h9K66qoj&index=4

```




```
--- create a public repo test using ui :


git
    4  clear
    5  git clone https://github.com/ramannkhanna2/test.git
    6  ls
    7  cd test
    8  ls
    9  ls -a
   10  git branch
   11  vi testfile
   12  ls
   13  git status
   14  git add .
   15  ls
   16  git status

   20  git config --global user.name raman
   21  git config --global user.email raman@email
   17  git commit -m "added new file"
   22  git status
   23  git remote -v
   24  git push origin main
   25  ls
   26  cd ..
   27  ls
   28  clear



-- after this now go to repository settings >> deploy keys :

https://docs.github.com/en/authentication/connecting-to-github-with-ssh/managing-deploy-keys

   29  ssh-keygen -t ed25519 -C "raman@email"
   30  ls -a
   31  cd .ssh
   32  ls
   33  cat cat id_ed25519.pub 
   34  cat id_ed25519.pub 
   35  clear
   36  cd ..
   37  ls
   38  git clone git@github.com:ramannkhanna2/test.git
   39  ls
   40  rm -rf test
   41  git clone git@github.com:ramannkhanna2/test.git
   42  ls
   43  cd test/
   44  ls
   45  git status
   46  vi testfile2
   47  ls
   48  git status
   49  git add .
   50  git commit -m "changes as per ssh method"
   51  git push origin main


===============================================================

```

```

git status
   58  ls
   59  vi password
   60  ls
   61  git status
   62  ls
   63  vi .gitignore
   64  cat .gitignore 
   65  git status
   66  git add .
   67  git status
   68  git commit -m "created gitignore file"
   69  git status
   70  git push origin main

```


```


stop the server :

requiremnt :
t2.micro >> t2.large , instance settings
storage : 20 gb , storage >> modifyvolume 

start the server


-- installing sonrqube server as a container :

docker run -d --name sonarqube -p 9000:9000 -e SONAR_ES_BOOTSTRAP_CHECKS_DISABLE=true sonarqube:latest



http://54.236.234.107:9000/projects/create

username: admin
password :admin1


--- create a project on sonar ui :

sonar token , test :

sqa_000c2422b947e9df8199707eb012e83e1a8e257d


---- installing sonar cli as a container :
https://docs.sonarsource.com/sonarqube/latest/analyzing-source-code/scanners/sonarscanner/


docker run \
    --rm \
    -e SONAR_HOST_URL="http://54.236.234.107:9000/" \
    -e SONAR_SCANNER_OPTS="-Dsonar.projectKey=test" \
    -e SONAR_TOKEN="sqp_7284c8f961d5e5a16d7eed7c21bbf4574d3c5ca6" \
    -v "/root/juice-shop:/usr/src" \
    sonarsource/sonar-scanner-cli






docker run \
    --rm \
    -e SONAR_HOST_URL="http://54.236.234.107:9000/" \
    -e SONAR_SCANNER_OPTS="-Dsonar.projectKey=test" \
    -e SONAR_TOKEN="sqp_7284c8f961d5e5a16d7eed7c21bbf4574d3c5ca6" \
    -v "/root/nodejsapp_jenkins-docker-kubernetes:/usr/src" \
    sonarsource/sonar-scanner-cli






history :



docker ps -a
   89  docker images
   90  docker run -d --name sonarqube -p 9000:9000 -e SONAR_ES_BOOTSTRAP_CHECKS_DISABLE=true sonarqube:latest
   91  docker ps
   92  docker images
   93  clear
   94  ls
   95  git clone https://github.com/juice-shop/juice-shop.git
   96  ls
   97  cd juice-shop/
   98  ls
   99  docker ps
  100  ls
  101  pwd
  102  clear
  103  ls
  104  dockr ps
  105  clear
  106  docker ps
  107  docker run     --rm     -e SONAR_HOST_URL="http://54.236.234.107:9000/"     -e SONAR_SCANNER_OPTS="-Dsonar.projectKey=test"     -e SONAR_TOKEN="sqp_7284c8f961d5e5a16d7eed7c21bbf4574d3c5ca6"     -v "/root/juice-shop:/usr/src"     sonarsource/sonar-scanner-cli
  108  clear
  109  git clone https://github.com/ramannkhanna2/nodejsapp_jenkins-docker-kubernetes.git
  110  rm -rf nodejsapp_jenkins-docker-kubernetes/
  111  cd ..
  112  git clone https://github.com/ramannkhanna2/nodejsapp_jenkins-docker-kubernetes.git
  113  cd nodejsapp_jenkins-docker-kubernetes/
  114  pwd
  115  docker ps
  116  docker run     --rm     -e SONAR_HOST_URL="http://54.236.234.107:9000/"     -e SONAR_SCANNER_OPTS="-Dsonar.projectKey=test"     -e SONAR_TOKEN="sqp_7284c8f961d5e5a16d7eed7c21bbf4574d3c5ca6"     -v "/root/nodejsapp_jenkins-docker-kubernetes:/usr/src"     sonarsource/sonar-scanner-cli
  117  history



============================================

```

