# Rocket.chat on Cent OS with Sakura VPS.

1. Access Cent OS on Sakura VPS.
```
# sudo ssh [your ip address]
# [Enter password]
```

2. Update and upgrade Cent OS.
```
# yum update
# yum upgrade
```

3. Install the official stable yum repository.
```
# sudo yum -y yum-utils device-mapper-persistent-data lvm2
# yum-config-manager --add-repo https://download.docker.com/linux/centos/docker-ce.repo
```

4. Install docker CE and enable docker.
```
# yum install docker-ce docker-ce-cli containerd.io
# systemctl start docker
# systemclt enable docker
```

5. Install docker-compose.
```
# yum install docker-compose
```

6. Make directories to mount mongo db on host side.
```
# mkdir -p /var/www/rocket.chat/data/runtime/db
# mkdir -p /var/www/rocket.chat/data/dump
```
7. Make a docker compose file.
```
# vim /var/www/rocket.chat/docker-compose
```

8. make and run docker container.
```
# cd /var/www/rocket.chat
# docker-compose up
```

### Reference

[Get Docker Engine - Community for CentOS](https://docs.docker.com/install/linux/docker-ce/centos/#set-up-the-repository)

[Rocket.Chat/docker-compose.yml](https://github.com/RocketChat/Rocket.Chat/blob/develop/docker-compose.yml)
