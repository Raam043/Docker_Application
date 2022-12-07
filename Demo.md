# Docker Installation on AWS - EC2 server


## Installation commands

```sh
yum udpate -y
yum install docker -y
systemctl enable docker
systemctl start docker
```

## Check Docker version to confirm docker installation
```sh
docker --version
```

## Check Downloaded Docker Images
```sh
docker images -a
```

## Check Running Containers
```sh
docker ps -a
```

## Download Docker Images from DockerHub (Search specific images or use below images for test)
```sh
docker search nginx
```

## Download Docker image from Hub
```sh
docker pull raam043/web-paint
```

Check Downloaded Docker Images and container ( Docker images && docker ps -a)

Before running the container check the 80 port. (Open new tab and paste server public IP address)


## Run the image as container at 80 port
```sh
docker run --name myapp -d -p 80:80 raam043/web-paint
```

## Check the container status / list
```sh
docker ps -a
```

