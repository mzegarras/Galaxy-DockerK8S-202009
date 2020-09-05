# Lab01

### Package manager

* Instalar dnf (opcional)
    ```bash
    yum install dnf
    dnf --version
    ```

* Actualizar centos (opcional)
    ```bash
    sudo dnf update -y
    ```

* wget
    ```bash
    curl https://ifconfig.me
    wget https://ifconfig.me
    sudo dnf install -y wget
    sudo dnf remove -y wget
    ```


### bash / sh

```bash
echo $0
sh
echo $0
```


```bash
#!/bin/sh
echo "123"
```

```bash
#!/bin/bash
echo "123"
```

### Sistema de archivos

```bash
pwd
cd
cd ~
echo "galaxy" > data.txt
echo "galaxy2" > data
ls -lt
cat data.txt
mkdir /data2
mkdir data2
mkdir ./data3
cd /data2
cd data2
cd ./data2
cd ..
mkdir -p /data4/dir1/dir2/dir3
mkdir -p ./data4/dir1/dir2/dir3/dir4
pwd
cd ~ 
```

```bash
cat data.txt
vi demo.txt
press i
ESC + :wq 
q!
```

```bash
vi docker.log
presionar i
2020-09-05 10:40
ESC + :wq 
```


```bash
man pwd
man ls
presionar q
```



```bash
for i in `seq 1 10`;do echo $i > data_demo2.txt;done **fix
for i in `seq 1 10`;do echo $i >> data_demo.txt;done **fix

head -n 2 data_demo.txt
tail -2 data_demo.txt
cat data_demo.txt
cat data_demo.txt |grep 10
```

### Copiar y mover archivos
```bash
mkdir dir01
cp data_demo.txt ./dir01
mv data_demo2.txt ./dir01
mv docker.log ./dir01/docker01.log
cd dir01
```

### Reto 01

1. Crear un archivo galaxy.log con valores del 1 - 5 (vi)
2. Buscar cadenas de texto que contengan 3 (cat|grep)

```bash
for var in {1..5};do  echo "valor de var $var" >> data.txt;  done;
cat data.txt |grep 3

echo "l1" > data01.txt
echo "l2" >> data01.txt
echo "l3" >> data01.txt
```


### Reto 02

1. Crear los directorios ~/apps/app01/log
2. Crear el archivo ~/apps/app01/log/server01.log
3. Copiar el archivo ~/apps/app01/log/server01.log al profile

```bash

mkdir apps
cd apps
mkdir app01
mkdir log
cd ~
cd ~/apps/app01/log


mkdir -p ~/apps/app01/log
touch ~/apps/app01/log/server01.log
cp ~/apps/app01/log/server01.log ./server01.log

```
### Remover contenido

```bash
rm server01.log
rm *.txt
rm -rf ./apps
```

### Listar contenido
```bash
ls
ls -lt
ls -lta
```

### Permisos

```bash
-rw-r--r--    1  wada  users  4096 abr 13 19:30 file
drw-r--r--    1  wada  users  4096 abr 13 19:30 file
```

```bash
x-------------x-------------x
|  permisos   |  pertenece  |
x-------------x-------------x
|  rwx------  | usuario     |
|  ---r-x---  | grupo       |
|  ------r-x  | otros       |
x-------------x-------------x
```

```bash
r	Permiso de lectura (4)
w	Permiso de escritura (2)
x	Permiso de ejecución (1)
```

```bash
x-----x-----x-----------------------------------x
| rwx |  7  | Lectura, escritura y ejecución    |
| rw- |  6  | Lectura, escritura        |
| r-x |  5  | Lectura y ejecución       |
| r-- |  4  | Lectura               |
| -wx |  3  | Escritura y ejecución             |
| -w- |  2  | Escritura                         |
| --x |  1  | Ejecución             |
| --- |  0  | Sin permisos          |
x-----x-----x-----------------------------------x
```

### Cambiar permisos y owner
```bash
chmod 400 file
chmod 440 file
chmod 444 file
chmod 644 file
chmod 744 file
chmod 774 file
chmod 777 file
```

miguel es owner y clients es el grupo propietario

```bash
chown miguel:clients demo.txt
```

miguel es owner
```bash
chown miguel demo.txt
```


Permisos ejecución
```bash
chmod 744 01_hello.sh

vi 01_hello_B.sh

#!/bin/bash
echo "bash - 123"


chmod +x 01_hello.sh

./01_hello_B.sh
./01_hello.sh
```