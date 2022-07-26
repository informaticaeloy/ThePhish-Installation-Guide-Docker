# ThePhish-Installation-Guide-Docker
Instalación de ThePhish usando Dockers en Ubuntu Desktop 22.04 LTS

Welcome to the ThePhish-Installation-Guide-Docker wiki!

* Instalar Ubuntu Desktop 22.04LTS (VM en VMWare, 4GB RAM, 2 Cores, 30GB HD, network en Bridge)
* Tras todo el asistente inicial:
  ```shell
  sudo apt-get update 
  ```
  ```shell
  sudo apt-get upgrade
  ```
* Pasos previos

  > configurar la dirección IP 

  > instalar el servicio SSH 

  ```shell
  sudo apt-get install ssh
  ```

  > configurar el autoarranque de SSH

  ```shell
  sudo systemctl enable ssh
  ```

  > comprobar estado del servicio ssh

  ```shell
  sudo systemctl status ssh
  ```

  > instalar Java
  ```shell
  sudo apt-get install default-jre
  ```

* Instalar Dockers y Dockers-compose

  > Primero, actualice su lista de paquetes existente:
    
  ```shell
  sudo apt update
  ```
    
  > A continuación, instale algunos paquetes de requisitos previos que permitan a apt usar paquetes a través de HTTPS:
     
  ```shell
  sudo apt install apt-transport-https ca-certificates curl software-properties-common
  ```
      
  > Luego, añada la clave de GPG para el repositorio oficial de Docker en su sistema:
    
  ```shell
  curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -
   ```
      
    > Agregue el repositorio de Docker a las fuentes de APT:
    > 
    ```shell
    sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu focal stable"
     ```
     
    > A continuación, actualice el paquete de base de datos con los paquetes de Docker del repositorio recién agregado:
    > 
    ```shell
    sudo apt update
     ```
     
    > Asegúrese de estar a punto de realizar la instalación desde el repositorio de Docker en lugar del repositorio predeterminado de Ubuntu:
    > 
    ```shell
    apt-cache policy docker-ce
     ```
     
    > Si bien el número de versión de Docker puede ser distinto, verá un resultado como el siguiente:
    > 
     ```shell
     usuario@ThePhish:~$ apt-cache policy docker-ce
      ```
     
       > docker-ce:
       > Installed: (none)
       > Candidate: 5:20.10.17~3-0~ubuntu-focal
       > Version table:
       > 5:20.10.17~3-0~ubuntu-focal 500
       >     500 https://download.docker.com/linux/ubuntu focal/stable amd64 Packages

    > Observe que docker-ce no está instalado, pero la opción más viable para la instalación es del repositorio de Docker para Ubuntu 20.04 (focal).
    
    > Por último, instale Docker:
    
     ```shell
     sudo apt install docker-ce
      ```
      
    > Instalamos Docker-Compose
    
     ```shell
     sudo apt install docker-compose
      ```

* Ejecute los contenedores con Docker Compose
   
   > Clonar el repositorio
   
   ```shell
   git clone https://github.com/emalderson/ThePhish.git
    ```

Si nos sale un error de ejecución o no tenemos git instalado en el sistema:

```shell
sudo apt-get install git-all
```
    
   > Se nos creará la carpeta 'ThePhish' y una subcarpeta llamada 'docker'. Accedemos a ella:
    ```shell
    cd /ThePhish/docker
     ```
     
   > Y dentro de la subcarpeta docker, ejecutamos el comando siguiente:
    ```shell
    sudo docker-compose up
     ```

Esperamos a que termine la instalación:

![image](https://user-images.githubusercontent.com/20743678/181035255-03b6db11-52a4-47df-8666-8d8bb79a6331.png)

