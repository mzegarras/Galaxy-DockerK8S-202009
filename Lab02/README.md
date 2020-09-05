ssh-keygen
chmod 400 taller1
ssh -i taller1 mzegarra@35.193.42.41


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
