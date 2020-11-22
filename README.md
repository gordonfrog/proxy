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

run proxy from host connecting to eureka on rasPi:

mvn spring-boot:run -DEUREKA_SERVICE=http://pf4devicesdev1.local:8761/eureka

http://pf4devicesdev1.local:8080/

run proxy from rasPi as a container:

