# Docker Apache
    - docker run -d --name [container-name] -p 80:[host-port] httpd
    - docker run -d --name http-cont -p 80:80 httpd
    - docker kill $(docker ps -aq)
    - docker rm $(docker ps -aq)

# Build image
    - docker build -t thalassa-httpd .
    - docker run -d --name thalassa-web -p 80:80 thalassa-httpd

# Mysql -
    - docker pull mysql:latest
    - OR 
    - docker pull mysql:8.2
    - docker run --name thalassa-mysql -e MYSQL_ROOT_PASSWORD=mysqldb -d mysql
    - docker exec -it thalassa-mysql bash
    - mysql -u root -p
## Mysql with volume
    - docker volume create test-mysql-data
    - docker run --name thalassa-mysql -v mysql-data:/var/lib/mysql -e MYSQL_ROOT_PASSWORD=mysqldb -d mysql

## Map configuration directory 
    ocker run \
   --name final-mysql \
   -e MYSQL_ROOT_PASSWORD=strong_password \
   -p 3307:3306 \
   -v /etc/docker/test-mysql:/etc/mysql/conf.d \
   -v final-mysql-data:/var/lib/mysql \
   -d mysql
