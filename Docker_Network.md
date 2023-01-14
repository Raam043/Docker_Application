# Docker Network

![image](https://user-images.githubusercontent.com/111989928/212470383-f9dfd0fe-b2f6-4cc6-9112-bc476098df83.png)

Docker networking allows you to attach a container to as many networks as you like. You can also attach an already running container.

Create your own network
```sh
docker network create -d bridge my_network
```
For view the list of networks
```sh
docker network ls
```
[Optional] For more details about your network
```sh
docker network inspect my_network
```
Running Database Container image with your network
```sh
docker run -d --net=my_network --name db test/postgres
```
Running Web Application image with default network
```sh
docker run -d --name web test/webapp python app.py
```
