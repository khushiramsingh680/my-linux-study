## Docker 
- [ ] where does docker stores public images ?
```sh
https://hub.docker.com/
```
- [ ] Install Docker on ubuntu
```sh
apt update
apt install docker.io
```
- [ ] Check docker version
```sh
docker info
```
- [ ] Download an image of nginx
```sh
docker pull nginx
```
- [ ] Check all images
```sh
docker images
```
- [ ] How to create a container ?
```sh
docker run nginx
docker run -d nginx
```
- [ ] Check all running containers
```sh
docker ps
docker ps -a     to check all stopped or running
```


- [ ] Get the ip of a container
```sh
docker inspect <conatiner id or name>
```
- [ ] Check your application
```sh
curl <ip of container>
curl <name of container>
```
# We can not access application of container from outside network but we can map with your Vm ip then we can access 
-  Example 1
  ```sh
docker run -d -p 80:80 nginx
docker run -d -p 9000:80 nginx
```
- [ ] Create a container and I want to access this from port 800
- [ ] How to check the logs for a container
```sh
docker logs <containername>
```
-  [ ]  Kill all container
```sh
docker rm $(docker ps -aq)
docker rm $(docker ps -aq) --force 
```

## Container Storage 
- [ ] How to login to a container
```sh
docker exec -it 6cab1c3b4a sh
```
- [ ] How to map a directorty to your container location
```sh
docker run -d -v <system-location:container locartion> nginx

docker run -d -v /root/mydata:/tmp  nginx
```

## Docker hub Login 
- [ ] How to save a running container or covert running container to an image
```sh
 docker commit 3d2e0fbe9299  newimage
```
- [ ] How to login to dockerhub
```sh
docker login
```
- [ ] How to push images to my dockerhub repo
- [ ] Image name policy if you want to push your image to any repo
```sh
<reponame>/image
```
- [ ] How to rename an image
```sh
docker tag newimage nippy/newimage
```

- [ ] Now push image and verify on dockerhub
```sh
docker push nippy/newimage
```
