# Install and Configure Maven, git & Docker in Jenkins server

## Install Maven
```sh
yum install wget
wget http://apachemirror.wuchna.com/maven/maven-3/3.6.3/binaries/apache-maven-3.6.3-bin.tar.gz
mv apache-maven-3.6.3-bin.tar.gz /opt/
cd /opt/
tar -xvzf apache-maven-3.6.3-bin.tar.gz
cd ~
export M2_HOME=/opt/apache-maven-3.6.3
export M2=$M2_HOME/bin
PATH=$PATH:$M2
# To set it permanently update your .bash_profile
M2_HOME=/opt/apache-maven-3.8.3
M2=$M2_HOME/bin
export M2
PATH=$PATH:$HOME/bin:$JAVA_HOME:$M2
source ~/.bash_profile
yum install -y maven
```

## Install git
yum install git


## Install Docker
```sh
yum install docker
systemctl start docker
systemctl enable docker
```

## Assign shell to jenkins user

```sh
vi /etc/passwd
change shell from /bin/false to /bin/bash
```

## provide permissions to jenkins user in jenkins server to access docker
```sh
  sudo groupadd docker
  sudo usermod -aG docker jenkins
  sudo chmod 777 /var/run/docker.sock
```
