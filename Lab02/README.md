
* wget
```bash
sudo docker images
sudo su -
docker images

docker run -p 8008:80 nginx
docker run -p 8080:80 nginx:latest
docker run -p 8080:80 nginx:alpine

docker run -d -p 8080:80 nginx:alpine
docker run -d -p 8081:80 nginx:alpine
docker run -d -p 8082:80 nginx:alpine
docker run -d -p 8083:80 nginx:alpine

docker pull nginx:alpine

docker rm  -f 3a00bfa2cc8a
docker rm  -f c1a1ebc903ad
docker rm  -f 009748a1683c

docker logs <<ID_container>>
docker logs <<ID_container>> -f
ctrl + c


```

### Reto 01
1. Descargar la siguientes imagenes de nginx
    1.19.2-alpine
    1.19-perl

```bash
    docker pull nginx:1.19.2-alpine
    docker pull nginx:1.19.2-perl
```

1. Listar todas la imagenes

```bash
docker images
```

1. Listar todas la imagenes Rabbitmq

latest
management-alpine

```bash
docker pull rabbitmq:management-alpine
docker pull rabbitmq:latest
```

1. Listar todas la imagenes Mysql

```bash
25.0 --> docker pull mysql:25.0 (No existe la tag)
8.0.21 --> docker pull mysql:8.0.21
8.0 --> docker pull mysql:8.0
```


# 1: Crear containers

```
docker run -d nginx
docker run -d -p 8080:80 nginx
docker run -p 8086:80 nginx:pipeline
docker run -p 8087:80 nginx:latest
docker run -d -e MYSQL_ROOT_PASSWORD=my-secret-pw -p 3306:3306 mysql:5.7
```

# 2: Listar containers
```
docker ps -a
docker ps -aq
```

# 3: Iniciar y detener containers
```
docker stop a1051285c4ab
docker start a1051285c4ab
```

# 4: Eliminar containers
```
docker rm a1051285c4ab -f
```

# 5: Conectarse container
```
docker exec -it a1051285c4ab /bin/sh
```

# 6: images

```bash

docker images
docker rmi 3af156432993
docker tag
docker push

docker login --username=yourhubusername --email=youremail@company.com
docker login xxx.azurecr.io
```

docker run -d -p 8080:80 xxx.azurecr.io/nginx
docker tag nginx:latest manudemo.azurecr.io/pepe:1.0.0
docker push manudemo.azurecr.io/pepe:1.0.0
