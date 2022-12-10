# Docker

![Docker work flow](https://user-images.githubusercontent.com/111989928/206645113-a02cba0f-6214-490a-856a-350da9f8567d.png)



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
![Docker-Version](https://user-images.githubusercontent.com/111989928/206135782-6289c5d1-dda3-4ba7-86fb-2d7dd6b03b91.png)



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

Check Downloaded Docker Images and container ( Docker images & docker ps -a)

Before running the container check the 80 port. (Open new tab and paste server public IP address)


## Run the image as container at 80 port
```sh
docker run --name myapp -d -p 80:80 raam043/web-paint
```

![Container run](https://user-images.githubusercontent.com/111989928/206136012-f2a7f06f-0594-4cdd-aa54-dc83998e9570.png)

## Check 80 port with server IP for result

![Result](https://user-images.githubusercontent.com/111989928/206136537-7a6bf762-a62e-44bd-b55b-035fe05f1451.png)




## Check the container status / list
```sh
docker ps -a
```

## Stop Running Containers
```sh
docker stop <CONTAINER_ID>
```

## Remove / Delete Containers
```sh
docker rm <CONTAINER_ID>
```

## Stop and Remove all at same time
```sh
docker stop $(docker ps -a -q)
docker rm $(docker ps -a -q)
```

## Remove all docker images at same time
```sh
docker rmi $(docker images -q)
```


