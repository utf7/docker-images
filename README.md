# Dockerfile

# this repo for Dockerfile

# QUICK START 

## prepare
 
  download the jdk like jdk-{version}-{linux}-{x64}.tar.gz and put it with the same dir with Dockerfile 

## build

```bash
IMAGE_NAME=utf7/jdk8:{YOUR_VERSION}  #image name and version
REPO=master:7443   #image repo 
docker build -t ${IMAGE_NAME} .
```
## view images
```bash
#docker images
REPOSITORY                                               TAG                 IMAGE ID            CREATED             SIZE
utf7/jdk8                                                 latest              204a86499ba4        6 minutes ago       960MB
```

## push

```bash 
docker tag  ${IMAGE_NAME}  REPO/${IMAGE_NAME}
docker push REPO/${IMAGE_NAME}
```

## test

Run a command in a new container from an image

```bash
docker run -it --name jdk8 -d ${IMAGE_NAME}
```
Run a command in a running container 
```
docker exec -it jdk8 /bin/bash

java -version

echo $PATH

some output like 

```bash
[root@3c6ed3a48c6a ~]# java -version
java version "1.8.0_231"
Java(TM) SE Runtime Environment (build 1.8.0_231-b11)
Java HotSpot(TM) 64-Bit Server VM (build 25.231-b11, mixed mode)
[root@3c6ed3a48c6a ~]# echo $PATH
/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:/jdk64/jdk1.8.0_231/bin
```

## exit container
```bash 
exit
```
## stop container
```bash 
docker stop 3c6ed3a48c6a
```
## delete container
```bash 
docker rm 3c6ed3a48c6a
```
## delete image
```bash 
docker rmi 204a86499ba4
```




