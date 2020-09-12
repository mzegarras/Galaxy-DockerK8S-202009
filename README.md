# Despliegue de Aplicaciones con Docker y Kubernetes

* [Zoom] ()
* [Syllabus](https://raw.githubusercontent.com/mzegarras/Galaxy-DockerK8S-202009/master/Lab01/Syllabus.pdf)
* [Notepad](https://notepad.pw/g1vwws42)

### Tools

1. [Filezilla](https://filezilla-project.org/) - Transferir archivos
1. [Putty](https://www.putty.org/) - Putty
1. [Docker](https://www.docker.com/) - Docker / Docker-compose

### Conectarse a la máquina

1. AWS AMI ID
    ```console
    ami-060396dd859d237db
    ```

1. Modificar permisos
    ```console
    chmod 400 ./credentials/DockerK8S-202009.pem
    ```

1. Conectarse a la máquina con certificado
    ```console
    ssh -i ./credentials/DockerK8S-202009.pem centos@34.211.110.106
    ```

1. Conectarse a la máquina con certificado
    ```console
    ssh centos@host_ip_address
    ```