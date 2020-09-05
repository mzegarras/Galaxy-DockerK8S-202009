# Lab01

1. Instalar dnf (opcional)
    ```console
    yum install dnf
    dnf --version
    ```

1. Actualizar centos (opcional)
    ```console
    sudo dnf update -y
    ```

1. wget
    ```console

    curl https://ifconfig.me
    wget https://ifconfig.me
    sudo dnf install -y wget
    sudo dnf remove -y wget
    ```



# 1: bash / sh

```bash
#!/bin/sh
echo "123"
```

```bash
#!/bin/bash
echo "123"
```
# 2: Sistema de archivos

```bash
mkdir /data
cd /data
pwd
echo "miguel" > data.txt
```

```bash
for i in `seq 1 10`;do;echo $i > data_demo.txt;done
for i in `seq 1 10`;do;echo $i >> data_demo.txt;done
tail -3 data_demo.txt
cat data_demo.txt |grep 2
```

# 3: Listar contenido
```bash
ls
ls -lt
ls -lta
```

# 4: Permisos

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

# 4: Cambiar permisos y owner
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
