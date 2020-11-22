# proxy

---

ssh pi@pf4devicesde1.local

docker container ls

http://pf4devicesdev1.local:8080/

dashboard - start containers - build with parameters

PORTS: 8761:8761

IMAGE_NAME: xdevices/discovery

Build

docker container ls

docker logs -f 7b1cc9f8b1a6

http://pf4devicesdev1.local:8761/

mvn clean install 

## run proxy from host connecting to eureka on rasPi:

mvn spring-boot:run -DEUREKA_SERVICE=http://pf4devicesdev1.local:8761/eureka

http://pf4devicesdev1.local:8080/

## run proxy from rasPi as a container

git add .

git commit -m "dockerized"

git push -u origin master

http://pf4devicesdev1.local:8080/

dashboard - new item - proxy build - freestyle - 

source code mgmt - git - 

https://github.com/gordonfrog/proxy.git

build - add build step - execute shell - 

mvn clean package docker:build -DskipTests

apply/save

Build Now

docker images

## start with docker-compose via jenkins

cd startscripts

code docker-compose

git add .

git commit -m "docker-compose"

git push -u origin master

http://pf4devicesdev1.local:8080/

dashboard - new item - docker-compose start - freestyle - 

source code mgmt - git -

https://github.com/gordonfrog/startscripts.git

build - add build step - execute shell - 

docker-compose up -d

apply/save

stop all docker containers

docker-container ls

Build Now

ssh pi@pf4devicesdev1.local

look at discovery:

docker logs -f 6761b011c571

look at proxy:

docker logs -f 2a1144ac70f8

http://pf4devicesdev1.local:8761/

## stop with docker-compose via jenkins

http://pf4devicesdev1.local:8080/

dashboard - new item - docker-compose stop - freestyle - 

build - add build step - execute shell - 

for i in `docker container ls -aq`; do docker container stop $i; done

apply/save

Build Now

docker container ls

## jenkins automation pipeline

http://pf4devicesdev1.local:8080/

dashboard - manage jenkins - manage plugins - available

search for Multijob plugin

install without restart

dashboard - new item - xdevices pipeline - multi-job - 

build - add build step - multi-job phase - 

name: deploy prep

job: stop containers

job execution type: sequentially

continue when: success

add build step - multi-job phase - 

name: docker build

job: discovery build

add job -

job: proxy build

job execution type: sequentially

continue when: success

add build step - multi-job phase -

name: docker run

job: docker-compose start

job execution type: sequentially

continue when: always

apply/save

Build Now

docker container ls




