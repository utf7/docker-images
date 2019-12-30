# Dockerfile

# this repo for Dockerfile

## prepare
 
  download the jdk like jdk-{version}-{linux}-{x64}.tar.gz and put it with the same dir with Dockerfile 

## build
```bash
IMAGE_NAME=utf7/jdk8:{YOUR_VERSION}
REPO=master:7443   #image 

# build
docker build -t ${IMAGE_NAME} .

# push

docker tag  ${IMAGE_NAME}  REPO/${IMAGE_NAME}

docker push REPO/${IMAGE_NAME}

```
