# Lab07

### Link containers

1. Pasos previos en local
    ```bash
    sudo systemctl stop firewalld
    sudo systemctl disable firewalld
    sudo iptables -t filter -F
    sudo iptables -t filter -X
    systemctl restart docker
    ```

1. Instalar wordpress
    ```bash
    docker pull wordpress
    docker pull mysql
    ```

1.  Generar container llamado mysql01
    ```bash
    docker run --name mysql01 -p 3306:3306 -e MYSQL_ROOT_PASSWORD=Password1234 -d mysql
    ```


1. Pull images
    ```bash

    docker run --name wordpress01 --link mysql01 -p 8080:80 -e WORDPRESS_DB_HOST=mysql01:3306 -e WORDPRESS_DB_USER=root -e WORDPRESS_DB_PASSWORD=Password1234 -e WORDPRESS_DB_NAME=wordpress -d wordpress

    docker run --name wordpress01 --link mysql01:serverbd01 -p 8080:80 -e WORDPRESS_DB_HOST=serverbd01:3306 -e WORDPRESS_DB_USER=root -e WORDPRESS_DB_PASSWORD=Password1234 -e WORDPRESS_DB_NAME=wordpress -d wordpress

    ```

1. Pull images
    ```bash
    --link <name or id>:alias
    docker network inspect bridge
    ```

1. Multiple links
    ```bash
    docker run -d \
        --link node1:node1 \
        --link node2:node2 \
        --link node3:node3 \
        -p hostport:containerport \
        your-image
    ```

1. Wordpress with proxy-reverse
    ```bash

    docker run --name mysql01 -e MYSQL_ROOT_PASSWORD=Password1234 -d mysql

    docker run --name wordpress01 --link mysql01 -e WORDPRESS_DB_HOST=mysql01:3306 -e WORDPRESS_DB_USER=root -e WORDPRESS_DB_PASSWORD=Password1234 -e WORDPRESS_DB_NAME=wordpress -e WORDPRESS_CONFIG_EXTRA="define('WP_HOME','http://34.213.80.185:8080'); define('WP_SITEURL','http://34.213.80.185:8080');" -d wordpress

     docker run --name webserver --link wordpress01 -v $PWD/nginx.conf:/etc/nginx/nginx.conf:ro -p 8080:9060 -d nginx


    ```


1. Api / Web  
    ```bash

    docker run --name mongodb -e MONGO_INITDB_ROOT_USERNAME=root \
    -e MONGO_INITDB_ROOT_PASSWORD=pwd1234 \
    -e MONGO_INITDB_DATABASE=shop \
    -d mongo

     docker run --name mongo-express \
    -e ME_CONFIG_MONGODB_ADMINUSERNAME=root \
    -e ME_CONFIG_MONGODB_ADMINPASSWORD=pwd1234 \
    -e ME_CONFIG_MONGODB_ENABLE_ADMIN=true \
    -p 8081:8081 \
    --link mongodb:mongo \
    -d mongo-express
    
    docker build -t reactivedemo .

    docker run -p 8082:8080 --name reactiveapi -v $PWD/application.yml:/application.yml --link mongodb -d reactivedemo:latest


     docker run --name reactiveapi -v $PWD/application.yml:/application.yml --link mongodb -d reactivedemo:latest

    http://localhost:8082/listar
    http://localhost:8082/api/productos


    docker run --name webserver --link reactiveapi -v $PWD/nginx.conf:/etc/nginx/nginx.conf:ro -p 8083:9060 -d nginx

    ```    

    ```bash
    docker run --name mongodb -e MONGO_INITDB_ROOT_USERNAME=root \
    -e MONGO_INITDB_ROOT_PASSWORD=pwd1234 \
    -e MONGO_INITDB_DATABASE=shop \
    -p 27017:27017 \
    -d mongo

    *** host.docker.internal
    ```        


# Reto Node

* Generar la imagen del proyecto node

    * PORT: 3000
    * URL_DB: 'mongodb://localhost:27017/interfaces'
    * URL_DB_USER:
    * URL_DB_PWD:

* Ejecutar los containers
    proxy-reverse->backend(proyecto previo)-->mongo

* Para admins pudan usar mongo-express
    mongo-express-->mongo


### Networks

```bash
docker network ls
docker network rm
docker inspect network bb9dc739d01f
docker network create galaxy-net
    
```

```bash
docker run --name mongo -e MONGO_INITDB_ROOT_USERNAME=root \
-e MONGO_INITDB_ROOT_PASSWORD=pwd1234 \
-e MONGO_INITDB_DATABASE=shop \
--network galaxy-net  \
-d mongo

docker run --name mongo-express \
-e ME_CONFIG_MONGODB_ADMINUSERNAME=root \
-e ME_CONFIG_MONGODB_ADMINPASSWORD=pwd1234 \
-e ME_CONFIG_MONGODB_ENABLE_ADMIN=true \
-p 8081:8081 \
--network galaxy-net  \
-d mongo-express
```    