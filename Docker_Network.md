# Docker Network

![image](https://user-images.githubusercontent.com/111989928/212470383-f9dfd0fe-b2f6-4cc6-9112-bc476098df83.png)
https://docs.docker.com/engine/tutorials/networkingcontainers/#:~:text=Docker%20includes%20support%20for%20networking,that%20is%20an%20advanced%20task for more understanding of network.

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
docker run --name db -e MYSQL_ROOT_PASSWORD=my-secret-pw -d mysql
```
Running Web Application image with default network
```sh
docker run -d -p 80:80 --name web raam043/nginx
```
View IP address of database container
```sh
docker inspect --format='{{range .NetworkSettings.Networks}}{{.IPAddress}}{{end}}' db
```
View IP address of web container
```sh
docker inspect --format='{{range .NetworkSettings.Networks}}{{.IPAddress}}{{end}}' web
```
Connect web container with private network
```sh
docker network connect my_network web
```
Now see the results of private network ip address.
