# homelab-DockerProject
*Docker running on raspberry pi 4

Disclaimer: This project started on August 2023, some package might different 

## 1) Install linux on Raspberry pi 4
Please download Raspberry Pi OS (64-bit) since it have 8GB of RAM
Please download [Raspberry Pi OS (64-bit)](https://www.raspberrypi.com/software/operating-systems/) since it have 8GB of RAM

Use imager from raspberry pi, click advance setting to enable ssh and using port 22.
Also please set appropriate hostname
![alt text](img/1.jpg)

## 2) ssh into raspberry pi
## 3) Install docker
### a) Update the package index and install the necessary dependencies:
```sudo apt update
sudo apt install apt-transport-https ca-certificates curl gnupg lsb-release
```
### b) Add the Docker GPG key to ensure the authenticity of the Docker packages
```
curl -fsSL https://download.docker.com/linux/debian/gpg | sudo gpg --dearmor -o /usr/share/keyrings/docker-archive-keyring.gpg
```

### c) Add the Docker repository to the system's package sources:
```
echo "deb [arch=amd64 signed-by=/usr/share/keyrings/docker-archive-keyring.gpg] https://download.docker.com/linux/debian $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
```

### d) Update the package index again to include the Docker packages from the newly added repository:
```sudo apt update
```

### e) Install docker
```
sudo apt install docker-ce docker-ce-cli containerd.io
```

### f) Docker should now be installed on your Debian system. You can verify it by checking the Docker version:
```
docker --version
```

If Docker is installed correctly, it will display the installed version.

## Install Portainer (To undersand more how docker vs docker-compose works)
## 1) xxx
## 2) xxx
## 3) xxx
## 4) xxx
## 5) xxx
Docker Stacks @ Docker compose

Create file docker ``` vim docker-compose.yml ```

```
version: '3'
services:
  website:
    image: nginx:latest
    ports:
      - 8080:80
    volumes:
      - ./website:/usr/share/nginx/html
    container_name: docker-stacks_Website_Surau
    restart: always

```

![alt text](img/2.JPG)

![alt text](img/3.JPG)



This command starts the containers in the background and allows you to continue using the terminal without interrupting Docker Compose.

Bring up the docker stacks
```
docker-compose up -d
```

To transfer file from RP4 to docker (ed02ab0840bb)
```
docker cp /home/pi/html-files/. ed02ab0840bb:/usr/share/nginx/html/
```

To enter docker
```
docker exec -it ed02ab0840bb bash
```

Result running NGINX in docker compose (example of website)
![alt text](img/4.png)


### Register No-IP DDNS
### Enable port fowarding from router
