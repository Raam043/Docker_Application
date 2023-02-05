# End to End Docker uses


## Installation on server
```sh
sudo bash
yum udpate -y
yum install docker -y
systemctl enable docker
systemctl start docker
yum install git -y
wget -O /etc/yum.repos.d/jenkins.repo \
    https://pkg.jenkins.io/redhat-stable/jenkins.repo
rpm --import https://pkg.jenkins.io/redhat-stable/jenkins.io.key
yum upgrade
amazon-linux-extras install java-openjdk11 -y
yum install jenkins -y
systemctl enable jenkins
systemctl start jenkins
sudo chmod 666 /var/run/docker.sock
```

## Upload the application on GitHub account to use it on jenkins pipeline
