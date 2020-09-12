# Lab04

### Docker volumes

1. Volumes - Stateless vs Statefull
    ```bash
    docker run -p 8080:80 mzegarra/lpsa:1.0
    docker run -p 8080:8080 mzegarra/msclientes:0.0.1
    ``` 

1. Volumes
    ```bash
    docker images ls
    docker run -v /usr/local/Proyectos/Galaxy/DockerK8S-202009/Lab04/resources:/usr/share/nginx/html -p 9060:80 nginx
    docker exec -it a15f6d725e0c /bin/sh
    echo $PWD
    cd /usr/local/Proyectos/Galaxy/DockerK8S-202009/Lab04
    docker run -v $PWD/resources:/usr/share/nginx/html -p 9060:80 nginx
    ``` 

1. Volumes readOnly
    ```bash
    docker images ls
    docker run -v /usr/local/Proyectos/Galaxy/DockerK8S-202009/Lab04/resources:/usr/share/nginx/html:ro -p 9060:80
    ``` 

1. Mongo Volume
    ```bash
    docker run -v $(PWD)/data:/data/db -d mongo
    docker exec -it d5396946ffa5 /bin/sh
    mongo
    show dbs
    use shop
    db.products.insertOne({name:"A book",pice: 12.99})
    db.products.find()
    db.products.find().pretty()
    ```


1. Mysql Volume
    ```bash
    docker run -e MYSQL_ROOT_PASSWORD=password -e MYSQL_DATABASE=ventas -d mysql:8.0
    docker run -v $(PWD)/data2:/var/lib/mysql -e MYSQL_ROOT_PASSWORD=password -e MYSQL_DATABASE=ventas -d mysql:8.0

    use ventas;
    CREATE TABLE pet (name VARCHAR(20), owner VARCHAR(20),species VARCHAR(20), sex CHAR(1), birth DATE, death DATE);
    DESCRIBE pet;
    INSERT INTO pet values ('Fido','Manuel','dog','M',CURDATE(),CURDATE());
    select * from pet;
    ``` 

1. Reto: Redis Volume
1. Reto: Rabbitmq Volume
