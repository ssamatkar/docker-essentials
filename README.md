# Docker Essentials Lab Cheat Sheet

### Docker Labs Pre-requisites
1. Basic understanding of Linux Commands.
2. Basic knowledge of a Cloud platform such as AWS.
3. Good to have an AWS-Free Tier Account for Practice.

## Lab-1: Creating an EC2 Instance in AWS and Installing Docker

To begin with Lab-1, log in to AWS Console.

### Task-1: Installing Docker on Ubuntu 20.04 operating system

* Manually Launch a `t2.micro` instance with OS version as `Ubuntu 22.04 LTS` in North Virginia (us-east-1) Region.
* Use tag "`Name:Docker-Server`"
* Create a new Keypair with the Name `Docker-Keypair-YourName`
* In security groups, include ports `22 (SSH)`  `80 (HTTP)` `443 (HTTPS)` and `8080 (custom TCP port)`
* Configure Storage: 10 GiB
* Launch the Instance.
* Once Launched, Connect to the Instance using `MobaXterm` or `Putty` with username "`ubuntu`".

Once the EC2 is ready, follow the below Commands to perform lab:

Switching to super user and setting up a host name
```
sudo hostnamectl set-hostname DockerServer
bash
```
```
sudo su
```
Updating the packages
```
apt update -y
```
Installing the packages
```
apt install curl -y
```
Connecting to url
```
curl -SSL https://get.docker.com/ | sh
```
Checking the status of the docker
```
service docker status
```
If the service is not active, then we need to start the service
```
service docker start
```
To add ubuntu user to docker group, if you are not working as the root user
```
usermod -aG docker ubuntu
```
Checking the version of the docker
```
docker --version
```
#### =========================END of LAB-01=========================
