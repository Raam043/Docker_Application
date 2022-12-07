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

## Check Downloaded Docker Images
```sh
docker images -a
docker ps -a
```

