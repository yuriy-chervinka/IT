# <p align="center">IT</p>

<!-- Comment method 1 -->
[//]: # (Comment method 2 - the preferable one. + insert empty string before)
[//]: <> (Comment method 3)
[//]: # "Comment method 4"



</br>

## <p align="center">Table of Contents</p>
<details>
  <summary><b>Expand</b></summary>  

- __[Markdown](#markdown)__
<!--  - [Links](#markdown.links)
-->
- __[Linux](#linux)__
<!--  - [Workflow](#linux.workflow)
  - [Commands](#linux.commands)
  - [Links](#linux.links)
-->
- __[GIT](#git)__
<!--  - [Installation](#git.install)
  - [Commands](#git.commands)
  - [Workflow](#git.workflow)
  - [Links](#git.links)
-->
- __[Docker](#docker)__
<!--  - [Installation](#docker.install)
  - [Commands](#docker.commands)
  - [Workflow](#docker.workflow)
  - [Links](#docker.links)
-->
- __[SQL (PostgreSQL)](#postgres)__
<!--  - [Installation](#postgres.install)
  - [Commands](#postgres.commands)
  - [Workflow](#postgres.workflow)
  - [Links](#postgres.links)
-->

</br>
</details>

--------------------------------------------------------------------------------

## <p align="center">Markdown</p><a name="markdown"></a>
<details>
  <summary>Expand</summary>  
  
  - [Syntax](#markdown.syntax)  
  - [Links](#markdown.links)  
  



</br>

### Syntax <a name="markdown.syntax"></a>





</br>

### Links <a name="markdown.links"></a>





</br>
</details>

--------------------------------------------------------------------------------

## <p align="center">Linux</p><a name="linux"></a>
<details>
  <summary>Expand</summary>  
  
  - [Workflow](#linux.workflow)  
  - [Commands](#linux.commands)  
  - [Links](#linux.links)  
  



</br>

### Workflow <a name="linux.workflow"></a>

#### Virtual Environment
  
Create Virtual Environment folder vith name 'env':  
  ```
  $ python -m venv env
  ```  
  
Activate Virtual Environment:  
  ```
  $ source env/bin/activate
  (env) user_name:path$ 
  ```  
  
Deactivate Virtual Environment:  
  ```
  $ deactivate
  user_name:path$ 
  ```  
  

#### SSH
  
Generate SSH key:  
  ```
  $ ssh-keygen -t rsa
  ```  





$ source <dir_name>/bin/activate
(dir_name) user@host:~/dir_name$	- virtualenv activated


</br>

### Commands <a name="linux.commands"></a>




</br>

### Links <a name="linux.links"></a>





</br>
</details>

--------------------------------------------------------------------------------

## <p align="center">GIT</p> <a name="git"></a>
<details>
  <summary>Expand</summary>  
  
  - [Installation](#git.install)  
  - [Commands](#git.commands)  
  - [Workflow](#git.workflow)  
  - [Links](#git.links)  



</br>

### Installation <a name="git.install"></a>



</br>

### Commands <a name="git.commands"></a>



</br>

### Workflow <a name="git.workflow"></a>




</br>

### Links <a name="git.links"></a>






</br>
</details>

--------------------------------------------------------------------------------

## <p align="center">Docker</p> <a name="docker"></a>
<details>
  <summary>Expand</summary>  

  - [Installation](#docker.install)  
  - [Commands](#docker.commands)  
  - [Workflow](#docker.workflow)  
  - [Links](#docker.links)  

  

</br>

### Installation <a name="docker.install"></a>  
  
__1. Set up the repository__  
  
1.1. Update the apt package index, and install packages to allow apt to use a repository over HTTPS:
  ```
  $ sudo apt update
  $ sudo apt install apt-transport-https ca-certificates curl gnupg-agent software-properties-common
  ```  
1.2. Add Docker’s official GPG key:  
  ```
  $ curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -  
  OK
  ```  
1.3. Verify that you now have the key with the fingerprint 9DC8 5822 9FC7 DD38 854A  E2D8 8D81 803C 0EBF CD88, by searching for the last 8 characters of the fingerprint:  
  ```
  $ sudo apt-key fingerprint 0EBFCD88
  pub   rsa4096 2017-02-22 [SCEA]
        9DC8 5822 9FC7 DD38 854A  E2D8 8D81 803C 0EBF CD88
  uid           [ unknown] Docker Release (CE deb) <docker@docker.com>
  sub   rsa4096 2017-02-22 [S]
  ```  
1.4. Set up the stable repository:  
  ```
  $ sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable"
  ```  
  
__2. Install Docker Engine__  
  
2.1. Update the apt package index, and install the latest version of Docker Engine and containerd:
  ```
  $ sudo apt update
  $ sudo apt install docker-ce docker-ce-cli containerd.io
  ```  
2.2. Verify that Docker Engine is installed correctly by running the hello-world image:  
  ```
  $ sudo docker run hello-world  
  Unable to find image 'hello-world:latest' locally
  latest: Pulling from library/hello-world
  0e03bdcc26d7: Pull complete 
  Digest: sha256:e7c70bb24b462baa86c102610182e3efcb12a04854e8c582838d92970a09f323
  Status: Downloaded newer image for hello-world:latest

  Hello from Docker!
  This message shows that your installation appears to be working correctly.
  ...
  ```  
2.3. Install docker-compose:
  ```
  $ sudo apt install docker-compose
  ```  
  
__3. Post-installation steps__  
  
3.1. Manage Docker as a non-root user:  
The Docker daemon binds to a Unix socket instead of a TCP port. By default that Unix socket is owned by the user `root` and other users can only access it using `sudo`. The Docker daemon always runs as the `root` user.  
If you don’t want to preface the `docker` command with `sudo`, create a Unix group called `docker` and add users to it. When the Docker daemon starts, it creates a Unix socket accessible by members of the `docker` group.  
  
Create a `docker` group, and add your user to the `docker` group:  
  ```
  $ sudo groupadd docker
  $ sudo usermod -aG docker $USER
  ```  
Log out and log in, so that your group membership is re-evaluated. Or run the following command to activate the changes to groups:  
  ```
  $ newgrp docker
  ```  
Verify that you can run docker commands without sudo:  
  ```
  $ docker run hello-world
  Hello from Docker!
  This message shows that your installation appears to be working correctly.
  ...
  ```  
Check if docker engine is running:  
  ```
  $ sudo systemctl status docker
  ```  
  
3.2. Configure Docker to start on boot:  
   ```
  $ sudo systemctl enable docker
  ```  




</br>

### Commands <a name="docker.commands" ></a>  <a href="https://docs.docker.com/engine/reference/commandline/docker/" target="_blank"> (documentation)</a>  
  
- check the version:  
`$ docker --version`  
- create and run container from an image:  
`$ docker run [OPTIONS] IMAGE [COMMAND] [ARG...]`  
- manage images:  
`$ docker image COMMAND`  
  - list images:  
  `$ docker image ls`  
  - build an image from docker file:  
  `$ docker image build`  
  - pull an image from registry:  
  `$ docker image pull`  
  - push an image to registry:  
  `$ docker image push`  
  - remove image:  
  `$ docker image rm`  
- manage containers:  
`$ docker container COMMAND`  
  - list containers:  
  `$ docker container ls`  
  - start container:  
  `$ docker container start`  
  - stop container:  
  `$ docker container stop`  
  - remove container:  
  `$ docker container rm`  
- list containers:  
`$ docker ps [OPTIONS]`  
  - list all:  
  `$ docker ps -a`  
- remove container:  
`$ docker rm [OPTIONS] CONTAINER`  
- remove image:  
`$ docker rmi [OPTIONS] IMAGE`  
- stop running container:  
`$ docker stop [OPTIONS] CONTAINER`  
- start stopped container:  
`$ docker start [OPTIONS] CONTAINER`  



</br>

### Workflow <a name="docker.workflow"></a>




  
</br>

### Links <a name="docker.links"></a>
- <a href="https://docs.docker.com/" target="_blank">docs.docker.com</a> - official site






</br>
</details>

--------------------------------------------------------------------------------

## <p align="center">SQL (PostgreSQL)</p> <a name="postgres"></a>
<details>
  <summary>Expand</summary>  

  - [Installation](#postgres.install)  
  - [Commands](#postgres.commands)  
  - [Workflow](#postgres.workflow)  
  - [Links](#postgres.links)  
  
  - [Installation](#mysql.install)  
  

</br>

### Installation <a name="postgres.install"></a>  
  
__1. Set up the repository__  
  
1.1. Create the repository configuration file:  
  ```
  $ sudo sh -c 'echo "deb http://apt.postgresql.org/pub/repos/apt $(lsb_release -cs)-pgdg main" > /etc/apt/sources.list.d/pgdg.list'
  ```  
1.2. Import the repository signing key:  
  ```
  $ wget --quiet -O - https://www.postgresql.org/media/keys/ACCC4CF8.asc | sudo apt-key add -
  ```  
  
__2. Install__  
  
2.1. Update the apt package index:  
  ```
  $ sudo apt update
  ```  
2.2. Install server, client, contributor extensions, pgadmin:  
  ```
  $ sudo apt install postgresql postgresql-client postgresql-contrib pgadmin4 pgadmin4-apache2
  ```  
  
__3. Post-installation steps__  
  
3.1. Server configuration:  

Check if server is listening for incoming connection on port 5432:  
  ```
  $ ss -nlt
  State       Recv-Q        Send-Q        Local Address:Port        Peer Address:Port       Process       
  LISTEN      0             5                 127.0.0.1:631             0.0.0.0:*       
  LISTEN      0             244               127.0.0.1:5432            0.0.0.0:*       
  ...
  ```  
  
By default, PostgreSQL Server will start up automatically each time system boots. To disable start on boot:  
  ```
  $ sudo systemctl disable postgresql
  ```  
  To enable start on boot:  
  ```
  $ sudo systemctl enable postgresql
  ```  
  
By default, PostgreSQL Server only listens on local loopback interface `127.0.0.1`.  
To change IP adress(es):  
- modify file `/etc/postgresql/13/main/postgresql.conf`:  
  - in section `CONNECTIONS AND AUTHENTICATION` uncomment and appropriately modify line `listen_addresses = ` ('listen_addresses = * ' for all IPs)  
  - save file and restart postgreSQL:  
    ```
    $ sudo systemctl restart postgresql
    ```  
- modify file `/etc/postgresql/13/main/pg_hba.conf` which will allow incoming client connections to all databases and users:  
  - add line `host    all    all    0.0.0.0/0  md5` (to open all IPs):  
    ```
    $ sudo bash -c "echo host    all          all            0.0.0.0/0  md5 >> /etc/postgresql/13/main/pg_hba.conf"
    ```  
- open port 5432 in firewall to any incoming TCP traffic:  
  ```
  $ sudo ufw allow from any to any port 5432 proto tcp
  Rule added
  Rule added (v6)
  ```  
  
Set PostgresqL user password:  
  ```
  $ sudo passwd postgres
  ```  
  
Access PostgreSQL shell:  
  ```
  $ sudo su -l postgres
  $ psql
  ```  
  or, alternatively:  
  ```
  $ sudo -u postgres psql
  ```  
  
Connect to remote postgreSQL server:  
  ```
  $ psql -h postgre-server -U postgre-user
  ```  
  
Start pgAdmin:  
  open browser and go to `http://[ServerIP_or_domain]/pgadmin4`  
  



</br>

### Commands <a name="postgres.commands"></a>  
  
__1. Server shell commands__  
  
- check if PostgreSQL server is running:  
`$ sudo systemctl status postgresql`  
- check if apache server is running (required for pgAdmin):  
`$ sudo systemctl status apache2`  
- stop server:  
`$ sudo systemctl stop postgresql`  
- start server:  
`$ sudo systemctl start postgresql`  
- restert server:  
`$ sudo systemctl restart postgresql`  
- disable start server on boot:  
`$ sudo systemctl disable postgresql`  
- enable start server on boot:  
`$ sudo systemctl enable postgresql`  





</br>

### Workflow <a name="postgres.workflow"></a>




</br>

### Links <a name="postgres.links"></a>



</br>

### Installation <a name="mysql.install"></a>  
  
__1. Install__  
  
2.1. Update the apt package index:  
  ```
  $ sudo apt update
  ```  
2.2. Install server, client, libraries:  
  ```
  $ sudo apt upgrade
  $ sudo apt install mysql-server mysql-client libmysqlclient-dev
  ```  
  





</br>
</details>

--------------------------------------------------------------------------------



