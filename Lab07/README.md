# Lab07

### Link containers

1. Instalar wordpress
    ```bash
    docker pull wordpress
    docker pull mysql
    ```

1.  Generar container llamado mysql01
    ```bash
    docker run --name mysql01 -e MYSQL_ROOT_PASSWORD=Password1234 -d mysql
    ```


1. Pull images
    ```bash

    docker run --name wordpress01 --link mysql01 -p 8080:80 -e WORDPRESS_DB_HOST=mysql01:3306 -e WORDPRESS_DB_USER=root -e WORDPRESS_DB_PASSWORD=Password1234 -e WORDPRESS_DB_NAME=wordpress -d wordpress
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

1. Proxy reverse
    ```bash

    docker run --name mysql01 -e MYSQL_ROOT_PASSWORD=Password1234 -d mysql

    docker run --name wordpress01 --link mysql01 -e WORDPRESS_DB_HOST=mysql01:3306 -e WORDPRESS_DB_USER=root -e WORDPRESS_DB_PASSWORD=Password1234 -e WORDPRESS_DB_NAME=wordpress -e WORDPRESS_CONFIG_EXTRA="define('WP_HOME','http://localhost:8080'); define('WP_SITEURL','http://localhost:8080');" -d wordpress

     docker run --name webserver --link wordpress01 -v $PWD/nginx.conf:/etc/nginx/nginx.conf:ro -p 8080:9060 -d nginx


    ```