# homelab-DockerProject
*Docker running on raspberry pi 4

Disclaimer: This project started on August 2023, some package might different 

## 1) Install linux on Raspberry pi 4
Please download Raspberry Pi OS (64-bit) since it have 8GB of RAM
Please download [Raspberry Pi OS (64-bit)](https://www.raspberrypi.com/software/operating-systems/) since it have 8GB of RAM

Use imager from raspberry pi, click advance setting to enable ssh and using port 22.
Also please set appropriate hostname
![alt text]img\1.jpg)

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