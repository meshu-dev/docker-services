# Docker setup for services

This setup allows you to use docker and docker-compose to provide services to support development.

## Prerequisites

Install [Gitbash](https://gitforwindows.org) if using Windows

Go to user directory and open the .bashrc file

```
vim ~/.bashrc
```
    
Add the following shorthand for the docker-compose command...

```
# Docker
alias dc='docker-compose'
```

## Setup

1. Open up terminal application and change to a directory where you want your docker dev setup, an example would be...

```
cd ~/
```

2. Clone repository and then change directory to inside of the repository

```
git clone git@github.com:meshu-dev/docker-services.git
```

```
cd docker-services
```

3. Create docker network by running the following command...

```
docker network create dev
```

4. Update hosts file with docker container domains...

```
vim /etc/hosts
```

```
127.0.0.1   mysql.local
127.0.0.1   mongodb.local
127.0.0.1   mongoexpress.local
127.0.0.1   postgresql.local
127.0.0.1   redis.local
```

***Windows version***

If you are using Windows OS do the following...

Press the Start menu, search for "notepad" and select the "Run as administrator".

Once notepad has opened select File -> Open, add in the following directory and then press enter to show the hosts file.

```
C:\Windows\system32\drivers\etc\
```

Select hosts to open, add in the below lines, save and finally close notepad.

```
127.0.0.1   mysql.local
127.0.0.1   mongodb.local
127.0.0.1   mongoexpress.local
127.0.0.1   postgresql.local
127.0.0.1   redis.local
```

5. Create and run containers with the following command...

```
dc up -d
```

6. Up open your web browser and go to http://adminer.local and the website should show up.

7. Start expanding the docker dev setup by adding your own services, check below to see commands on how to use setup.

___

## Docker compose commands

A full list of docker-compose commands can be found at [https://docs.docker.com](https://docs.docker.com/compose/reference").

Here is a list of common docker-compose commands you would use...

### Docker Compose - Up

Usage:
```
dc up -d
```

Start up service docker containers.

___

### Docker Compose - Down

Usage:
```
dc down
```

Shutdown service docker containers.

___

### Docker Compose - Build

Usage:
```
dc build
```
Build service docker containers.
