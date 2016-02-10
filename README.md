# Docker container for SaltStack 8.5

This docker installs the lastest stable version (2015.8.5) of
SaltStack.

Also, you can install the old stable version (2015.5.3) from
SaltStack's repository, just modify this line like

```
ENV MVER 2015.5.3+ds-1~bpo8+1
```

### Plus

* Installs master and minion.
* Configures minion.
* You can define which version of SaltStack should be installed.
* Installs an emacs-like: [mg](http://homepage.boetes.org/software/mg).
* Installs vim with [plugins](https://github.com/saltstack/salt-vim) for SaltStack.
* Forces IPv4 for APT.

## How to build

On this directory, build and lauch the container

```
docker build -t saltstack .
```

Also, you can pull this container from Docker Hub

```
docker pull vando/saltstack
```

## Connect to container

Start the container

```
docker run -d -p 4505:4505 -p 4506:4506 --name saltstack saltstack
docker exec -it saltstack /bin/bash
```

## SaltStack first steps

```
salt 'minion' test.ping
```
