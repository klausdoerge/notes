

Image -> software to run
container -> running version of an image


**Running containers**
docker container run --publish 8080:80 nginx

This will expose port 80 on the container to port 8080 on your psychical network

docker container run --publish 8080:80 --detach nginx
Run the container in the background

**Getting Shell inside containers**
docker container run -it (start new container interatively)
docker container exec -it (run additional command in existing container - new bash)