# Docker 


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
```sh
pipeline {
    agent any

    stages {
        stage('Git checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/Raam043/Jenkins-project-test.git'
            }
        }
        stage('Docker image Build') {
            steps {
                sh 'docker stop testapp & docker rm -f testapp & docker image rm -f testapp & docker build -t testapp .'
            }
        }
        stage('Docker Conatiner run') {
            steps {
                sh 'docker run -d --name testapp -p 80:80 testapp'
                sh 'docker tag testapp raam043/testapp:latest'
            }
        }
        stage('Image pushing to DockerHub') {
            steps {
                withCredentials([string(credentialsId: 'DP', variable: 'DP')]) {
                    sh 'docker login -u raam043 -p ${DP}'
                    sh 'docker push raam043/testapp:latest'
            }
        }
        }
    }
}
```
