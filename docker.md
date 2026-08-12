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
