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
mkdir /data
cd /data
cd ..
mkdir -p /data/dir1/dir2/dir3
mkdir -p ./data/dir1/dir2/dir3
pwd
echo "miguel" > data.txt
```

```bash
vi demo.txt
press i
ESC + :
wq 
q!
```

```bash
for i in `seq 1 10`;do;echo $i > data_demo.txt;done
for i in `seq 1 10`;do;echo $i >> data_demo.txt;done
tail -3 data_demo.txt
cat data_demo.txt |grep 2
```
### Copiar y mover archivos
```bash
mkdir dir01
cd dir01
echo "hola2" > lab01.txt
cp ./lab01.txt lab02.txt
mv lab01.txt ../
cp -r dir01/ dir02
mv dir01/ dir02/
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
