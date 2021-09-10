# Crispy-K8

Docker
Introduction
Tool used to automate the deployment of applications in light weight containers so that applications can work efficiently in different environment

Setting up Docker
Editions – Community , Enterprise

 Installation :https://www.docker.com/products/docker-desktop
 
Docker hub   : https://hub.docker.com/
![image](https://user-images.githubusercontent.com/88343653/132908619-f98c07f8-a3de-4db5-911f-fe129eb7ad07.png)


image

Docker Vs VM

image

Docker Commands
$docker run nginx
$docker pull nginx
$docker ps
$docker ps -a

$docker run ubuntu
$docker run ubuntu sleep 5
$docker ps -a 
$docker exec <image name> cat etc/hosts
$docker run -d ubuntu
$docker attach <containerid>

$docker run centos
$docker run -it centos bash
 $cat /etc/release
$docker ps 
$docker run -d centos sleep 20
$docker rm <images>
$docker exec 
$docker version

$docker run helloworld
$docker run –p 80:5000 helloworld

$docker run mysql
$docker stop mysql
$dcker rm mysql

$docker run jenkins
$docker run -p 8080:8080 jenkins

Run container using redis image

$docker run redis
$docker run redis:4.0 -- tag

Default container port : 5000
Port mapping and volume mapping
$docker run -p 80:5000 <app name>

$ docker run -p 8306:3306 mysql
$docker run -p 3306:3306 mysql
$docker run -v  /opt/datadir:/var/lib/mysql mysql
$docker logs <imagename>
Images
$docker build .

FROM Ubuntu
RUN apt-get update && apt-get -y install python
RUN pip install flask flask-mysql
COPY . /opt/source-code
ENTRYPOINT FLASK_APP=/opt/source-code/app.py flask
run
Docker Runtime
https://docs.docker.com/config/containers/resource_constraints/

Docker network
$docker network ls

Docker swarm
$docker service create --replicas=100 nodejs $docker service create --replicas=3 -p 8080:80 ani-web-server $docker swarm --init

k8s
kubectl run --replicas=10 ani-web-server kubectl scale --replicas=10 ani-web-server kubectl rolling-update ani-web-server --image=ani-web-server:2 kubectl rolling-update ani-web-server --rollback
