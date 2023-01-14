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

