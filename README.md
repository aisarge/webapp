# webapp

## Step 1:  Install docker

```
~$ sudo apt install docker-ce
Reading package lists... Done
Building dependency tree... Done
Reading state information... Done
The following package was automatically installed and is no longer required:
  libzstd-dev
Use 'sudo apt autoremove' to remove it.
The following additional packages will be installed:
  containerd.io docker-buildx-plugin docker-ce-cli docker-ce-rootless-extras docker-compose-plugin
Suggested packages:
  aufs-tools cgroupfs-mount | cgroup-lite
The following NEW packages will be installed:
  containerd.io docker-buildx-plugin docker-ce docker-ce-cli docker-ce-rootless-extras docker-compose-plugin
0 upgraded, 6 newly installed, 0 to remove and 3 not upgraded.
Need to get 123 MB of archives.
After this operation, 441 MB of additional disk space will be used.
Do you want to continue? [Y/n] Y
Get:1 https://download.docker.com/linux/ubuntu jammy/stable amd64 containerd.io amd64 1.7.22-1 [29.5 MB]
Get:2 https://download.docker.com/linux/ubuntu jammy/stable amd64 docker-buildx-plugin amd64 0.17.1-1~ubuntu.22.04~jammy [30.3 MB]                                                                                
Get:3 https://download.docker.com/linux/ubuntu jammy/stable amd64 docker-ce-cli amd64 5:27.3.1-1~ubuntu.22.04~jammy [15.0 MB]                                                                                     
Get:4 https://download.docker.com/linux/ubuntu jammy/stable amd64 docker-ce amd64 5:27.3.1-1~ubuntu.22.04~jammy [25.6 MB]                                                                                         
Get:5 https://download.docker.com/linux/ubuntu jammy/stable amd64 docker-ce-rootless-extras amd64 5:27.3.1-1~ubuntu.22.04~jammy [9,589 kB]                                                                        
Get:6 https://download.docker.com/linux/ubuntu jammy/stable amd64 docker-compose-plugin amd64 2.29.7-1~ubuntu.22.04~jammy [12.7 MB]                                                                               
Fetched 123 MB in 32s (3,786 kB/s)                                                                                                                                                                                
Selecting previously unselected package containerd.io.
(Reading database ... 305382 files and directories currently installed.)
Preparing to unpack .../0-containerd.io_1.7.22-1_amd64.deb ...
Unpacking containerd.io (1.7.22-1) ...
Selecting previously unselected package docker-buildx-plugin.
Preparing to unpack .../1-docker-buildx-plugin_0.17.1-1~ubuntu.22.04~jammy_amd64.deb ...
Unpacking docker-buildx-plugin (0.17.1-1~ubuntu.22.04~jammy) ...
Selecting previously unselected package docker-ce-cli.
Preparing to unpack .../2-docker-ce-cli_5%3a27.3.1-1~ubuntu.22.04~jammy_amd64.deb ...
Unpacking docker-ce-cli (5:27.3.1-1~ubuntu.22.04~jammy) ...
Selecting previously unselected package docker-ce.
Preparing to unpack .../3-docker-ce_5%3a27.3.1-1~ubuntu.22.04~jammy_amd64.deb ...
Unpacking docker-ce (5:27.3.1-1~ubuntu.22.04~jammy) ...
Selecting previously unselected package docker-ce-rootless-extras.
Preparing to unpack .../4-docker-ce-rootless-extras_5%3a27.3.1-1~ubuntu.22.04~jammy_amd64.deb ...
Unpacking docker-ce-rootless-extras (5:27.3.1-1~ubuntu.22.04~jammy) ...
Selecting previously unselected package docker-compose-plugin.
Preparing to unpack .../5-docker-compose-plugin_2.29.7-1~ubuntu.22.04~jammy_amd64.deb ...
Unpacking docker-compose-plugin (2.29.7-1~ubuntu.22.04~jammy) ...
Setting up docker-buildx-plugin (0.17.1-1~ubuntu.22.04~jammy) ...
Setting up containerd.io (1.7.22-1) ...
Created symlink /etc/systemd/system/multi-user.target.wants/containerd.service → /lib/systemd/system/containerd.service.
Setting up docker-compose-plugin (2.29.7-1~ubuntu.22.04~jammy) ...
Setting up docker-ce-cli (5:27.3.1-1~ubuntu.22.04~jammy) ...
Setting up docker-ce-rootless-extras (5:27.3.1-1~ubuntu.22.04~jammy) ...
Setting up docker-ce (5:27.3.1-1~ubuntu.22.04~jammy) ...
Created symlink /etc/systemd/system/multi-user.target.wants/docker.service → /lib/systemd/system/docker.service.
Created symlink /etc/systemd/system/sockets.target.wants/docker.socket → /lib/systemd/system/docker.socket.

```
### Verify Docker version
```
~$ docker --version
Docker version 27.3.1, build ce12230
```

## Step 2: Create webapp directory & required files

```
:~$ cd /tmp
:/tmp$ mkdir webapp
:/tmp$ cd webapp
:/tmp/webapp$ touch Dockerfile index.html
:/tmp/webapp$ ls
Dockerfile  index.html

```

## Step 3: Build Docker image
```shell
/tmp/webapp$ sudo docker build -t webapp .
[+] Building 20.1s (7/7) FINISHED                                                                                                                                                                   docker:default
 => [internal] load build definition from Dockerfile                                                                                                                                                          0.0s
 => => transferring dockerfile: 96B                                                                                                                                                                           0.0s
 => [internal] load metadata for docker.io/library/httpd:2.4                                                                                                                                                  2.6s
 => [internal] load .dockerignore                                                                                                                                                                             0.0s
 => => transferring context: 2B                                                                                                                                                                               0.0s
 => [internal] load build context                                                                                                                                                                             0.0s
 => => transferring context: 272B                                                                                                                                                                             0.0s
 => [1/2] FROM docker.io/library/httpd:2.4@sha256:bbea29057f25d9543e6a96a8e3cc7c7c937206d20eab2323f478fdb2469d536d                                                                                           17.3s
 => => resolve docker.io/library/httpd:2.4@sha256:bbea29057f25d9543e6a96a8e3cc7c7c937206d20eab2323f478fdb2469d536d                                                                                            0.0s
 => => sha256:7fa508eeda1a92870329441e0cdeb372e21b81e1209746dc162867281889edb1 2.10kB / 2.10kB                                                                                                                0.0s
 => => sha256:3a2663e666707642d4fa962265d11d8ffe70b69fb63759fd2357d966dbebff25 142B / 142B                                                                                                                    1.2s
 => => sha256:bbea29057f25d9543e6a96a8e3cc7c7c937206d20eab2323f478fdb2469d536d 10.16kB / 10.16kB                                                                                                              0.0s
 => => sha256:1bcf11fa154f23987201bd92a75bf75e3507fc49f415d5dfe35887d1be3fd596 8.02kB / 8.02kB                                                                                                                0.0s
 => => sha256:a480a496ba95a197d587aa1d9e0f545ca7dbd40495a4715342228db62b67c4ba 29.13MB / 29.13MB                                                                                                             15.9s
 => => sha256:4f4fb700ef54461cfa02571ae0db9a0dc1e0cdb5577484a6d75e68dc38e8acc1 32B / 32B                                                                                                                      1.2s
 => => sha256:dbde712f81fb4a8648d9588ee8c8a26659b24763b21d023f2e07e67440adf949 4.20MB / 4.20MB                                                                                                                6.9s
 => => sha256:867b2ea3628d174d086062614bc2c6e1fbab681834f80f871a5ad99088b925a7 26.04MB / 26.04MB                                                                                                             10.6s
 => => sha256:6bd9d3710aaec01e07cd1db1d6afa00502d9158f3f368f8f5c8ec6a74f186caf 290B / 290B                                                                                                                    7.3s
 => => extracting sha256:a480a496ba95a197d587aa1d9e0f545ca7dbd40495a4715342228db62b67c4ba                                                                                                                     0.8s
 => => extracting sha256:3a2663e666707642d4fa962265d11d8ffe70b69fb63759fd2357d966dbebff25                                                                                                                     0.0s
 => => extracting sha256:4f4fb700ef54461cfa02571ae0db9a0dc1e0cdb5577484a6d75e68dc38e8acc1                                                                                                                     0.0s
 => => extracting sha256:dbde712f81fb4a8648d9588ee8c8a26659b24763b21d023f2e07e67440adf949                                                                                                                     0.1s
 => => extracting sha256:867b2ea3628d174d086062614bc2c6e1fbab681834f80f871a5ad99088b925a7                                                                                                                     0.4s
 => => extracting sha256:6bd9d3710aaec01e07cd1db1d6afa00502d9158f3f368f8f5c8ec6a74f186caf                                                                                                                     0.0s
 => [2/2] COPY index.html /usr/local/apache2/htdocs/                                                                                                                                                          0.0s
 => exporting to image                                                                                                                                                                                        0.0s
 => => exporting layers                                                                                                                                                                                       0.0s
 => => writing image sha256:190076453907c0f4080c94c8d45ce0140a6358531504c8eaa6bf40b15f768ac1                                                                                                                  0.0s
 => => naming to docker.io/library/webapp 

```

### Verify Docker Image 

```shell
:/tmp/webapp$ sudo docker images
REPOSITORY   TAG       IMAGE ID       CREATED              SIZE
webapp       latest    190076453907   About a minute ago   148MB
```

## step 4: Run the Docker Container
```shell
:/tmp/webapp$ sudo docker images
REPOSITORY   TAG       IMAGE ID       CREATED              SIZE
webapp       latest    190076453907   About a minute ago   148MB
:/tmp/webapp$ sudo docker run -p 8080:80 -d webapp
eb8360a56d7d036bc950c4d504e06866f4ae0acb5ef58b7f2073f8faf9082688

```
### verify the docker container is runnig 

```
sudo docker ps -a
CONTAINER ID   IMAGE     COMMAND              CREATED              STATUS              PORTS                                     NAMES
eb8360a56d7d   webapp    "httpd-foreground"   About a minute ago   Up About a minute   0.0.0.0:8080->80/tcp, [::]:8080->80/tcp   beautiful_hermann

```
