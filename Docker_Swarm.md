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

