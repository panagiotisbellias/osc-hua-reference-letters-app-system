# reference-letters-app-system
A web system about reference letters handling in the context of DIT-HUA pre-graduate course "Distributed Systems"

<p align="left"> <img src="https://komarev.com/ghpvc/?username=panagiotisbellias&label=Profile%20views&color=0e75b6&style=flat" alt="panagiotisbellias" /> </p>

<h3 align="left">Languages and Tools:</h3>
<p align="left"> <a href="https://www.linux.org/" target="_blank"> <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/linux/linux-original.svg" alt="linux" width="40" height="40"/> </a><a href="https://www.gnu.org/software/bash/" target="_blank"> <img src="https://www.vectorlogo.zone/logos/gnu_bash/gnu_bash-icon.svg" alt="bash" width="40" height="40"/> </a> 
<a href="https://www.w3.org/html/" target="_blank"> <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/html5/html5-original-wordmark.svg" alt="html5" width="40" height="40"/> </a><a href="https://www.w3schools.com/css/" target="_blank"> <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/css3/css3-original-wordmark.svg" alt="css3" width="40" height="40"/> </a><a href="https://getbootstrap.com" target="_blank"> <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/bootstrap/bootstrap-plain-wordmark.svg" alt="bootstrap" width="40" height="40"/> </a> 
<a href="https://git-scm.com/" target="_blank"> <img src="https://www.vectorlogo.zone/logos/git-scm/git-scm-icon.svg" alt="git" width="40" height="40"/> </a>
<a href="https://www.docker.com/" target="_blank"> <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/docker/docker-original-wordmark.svg" alt="docker" width="40" height="40"/> </a>
<a href="https://www.postgresql.org" target="_blank"> <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/postgresql/postgresql-original-wordmark.svg" alt="postgresql" width="40" height="40"/> </a>
<a href="https://www.python.org" target="_blank"> <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/python/python-original.svg" alt="python" width="40" height="40"/> </a>
<a href="https://www.nginx.com" target="_blank"> <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/nginx/nginx-original.svg" alt="nginx" width="40" height="40"/> </a>  <!-- 
<a href="https://azure.microsoft.com/en-in/" target="_blank"> <img src="https://www.vectorlogo.zone/logos/microsoft_azure/microsoft_azure-icon.svg" alt="azure" width="40" height="40"/> </a> 
</p> -->

<a name="contents"></a>
## Table Of Contents
1. [Table Of Contents](#contents)  
2. [Setup & Run Projects Locally (Installation)](#execution)  
3. [Deployment with Docker and docker-compose using Ansible to a VM(Virtual Machine)](#deployment)  

<a name="execution"></a>
## Setup & Run Projects Locally (Installation)

### Clone repository with submodules
```bash
git clone --recurse-submodules https://github.com/panagiotisbellias/reference-letters-app-system.git
cd reference-letters-app-system
```

For Java Spring Boot project see [here](https://github.com/panagiotisbellias/reference-letter-spring-service#run-project-locally-installation) and for JavaScript VueJS project see [here](https://github.com/panagiotisbellias/reference-letters-vuejs-client#project-setup)

<a name="deployment"></a>
## Deployment with Docker and docker-compose using Ansible to a VM (Virtual Machine)

We are going to need 1 VM for the docker execution environment.

* [Create VM in Azure Portal](https://docs.microsoft.com/en-us/azure/virtual-machines/linux/quick-create-portal)
* [SSH Access to VMs](https://help.skytap.com/connect-to-a-linux-vm-with-ssh.html)
* [SSH Automation](https://linuxize.com/post/using-the-ssh-config-file/)
* [Reserve Static IP in Azure](https://azure.microsoft.com/en-au/resources/videos/azure-friday-how-to-reserve-a-public-ip-range-in-azure-using-public-ip-prefix/)

In order to be able to use Ansible for automation, there is the [ansible-project-docker-install.yml](ansible-project-docker-install.yml).

### Ansible Prerequisites
Blah blah

### Docker & Ansible
Now, In order to deploy our project in Docker environment, we use a playbook that uses an Ansible role to run the application
with docker-compose according to the [docker-compose.yml](docker-compose.yml). In that file, we have defined three
services, the postgres container with its volume in order to be able to store data, the spring boot container and the vuejs container for our
system taking environmental variables from local hidden files. The spring-boot container is built according
to the [nonroot.Dockerfile](https://github.com/panagiotisbellias/reference-letter-spring-service/blob/spring-boot/nonroot.Dockerfile) as a nonroot process for safety reasons.
The vuejs container is built according
to the [Dockerfile](https://github.com/panagiotisbellias/reference-letters-vuejs-client/blob/master/Dockerfile).