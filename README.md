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
