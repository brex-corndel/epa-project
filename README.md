# epa-project
Repository for EPA Project Work

The project builds a somple Python app in flask linking to an Oracle Database and Grafana/Promethius in local Docker for Development.

Source is held in Github with a CI/CD Pipeline build with Jenkins to promote the docker image to Dockerhub if pytest tests are passed.

# Project Notes

Python
Flask
Pytest
Selenium

# Jenkins Notes

Jenkins is installed on Mac and can be controlled as follows :-

brew services stop jenkins-lts
brew services start jenkins-lts
brew services info jenkins-lts
brew services reload jenkins-lts

# CI/CD Pipelines

Jenkins
XL Release
Liquibase

# Infrastructure as Code(IaaC)

Terraform
Ansible
Kubernetes

# Monitoring The Database

Prometheus
Grafana

# Database Pipeline using XL Release

# Source Control Using Git and Github

https://github.com/brex-corndel/epa-project

# Containers

https://hub.docker.com/

Docker

docker build . (Same Directory as Dockerfile)

Docker compose

docker-compose up (from root)

# Oracle DB

Sql Developer
sqlcl
cx_oracle

# REST API

Oracle ORDS
Postman

https://www.postman.com/
https://web.postman.co/

Python/Jinka

# Oracle Cloud Infrastructure(OCI)

https://console.uk-london-1.oraclecloud.com/

# Source Control

Git
Visual Studio Code

# Design

S4 Diagrams

# ssh-keygen

Open SSH. Used for authentication key pairs for linking systems securely for automating logins.
-- In source

ssh-keygen -b 2048 -t rsa
(file stored in HOME/.ssh) id_rsa (private) id_rsa.pub (public)
ssh-copy-id -i ~/.ssh/id_rsa.pub user@<host/IP>

-- In Target (root)

useradd myadmin
mkdir /home/myadmin/.ssh
cd $HOME/.ssh
echo "<id_rsa.pub>" > /home/new_user/.ssh/authorized_keys

vi /etc/ssh/sshd_config
AllowUsers oracle opc myadmin

chown -R myadmin:myadmin /home/myadmin/.ssh
/sbin/service sshd restart

sudo visudo -f /etc/sudoers
add - %myadmin   ALL=(ALL)       NOPASSWD: ALL

Connect using : ssh new_user@ip_address -i id_rsa
ssh -i /path/to/private/key myadmin@203.0.113.5

X.509 supported with tectia ssh

opc user is created automatically in Oracle Cloud

# Tracking The Project 

Jira
Confluence
