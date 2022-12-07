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
