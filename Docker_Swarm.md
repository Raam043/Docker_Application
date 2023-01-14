# Docker Swarm

## 1 Release Amazon Linux server and install Docker

```sh
yum udpate -y
yum install docker -y
systemctl enable docker
systemctl start docker
yum install pip -y
pip install docker-py
```
## 2 Enable password less authentication through SSH Commands :
```sh
ssh-keygen
```
```sh
cat /root/.ssh/id_rsa.pub>>/root/.ssh/authorized_keys
chmod 755 /root/.ssh/authorized_keys
```

## 3 Create AMI (Amazon Machine Image) for Copy the server

## 4 Docker swarm init (After AMI + slave servers )

Run below command on Master with Public IP
```sh
docker swarm init --advertise-addr 18.224.202.231
```
Run nodes list
```sh
docker node ls
```
Run below command for generate code to join nodes 
```sh
docker swarm join-token worker
```
![image](https://user-images.githubusercontent.com/111989928/212469584-436cd7fb-c285-49f7-a443-dff202377c49.png)

You will get one code and run it on nodes / slaves to join with Master

Node joined to Master
![image](https://user-images.githubusercontent.com/111989928/212469619-a157fd97-8341-4fd8-9a61-ff436ed2779d.png)

Once node connected with master run "docker node ls" to view list of active master and nodes

[Optional] optional manager node can be initialized using below command
```sh
docker swarm join-token manager
```
Docker swarm options commands run below command
```sh
docker swarm
```
## 5 Run Docker Containers using docker swarm

```sh
ocker service create --replicas 3 -p 80:80 --name
```
