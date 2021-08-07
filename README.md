# docker
=======
# Create a docker image with a simple web service
Tutorial source from Youtube channel thenewboston https://www.youtube.com/watch?v=BG3f0E_4HiE&list=PL6gx4Cwl9DGBkvpSIgwchk0glHLz7CQ-7&index=11


## Create a **Dockerfile** without extension
```
e.g.
FROM node:alpine
WORKDIR /usr/app
COPY ./ ./
RUN npm install
CMD ["npm", "start"]
```

## Build image
```docker build .
or
docker build  -t [image name]:[status] . 
```

## Run docker
```
docker run [image name]

# direct from localhost 8080 port to container's 8080 port
docker run -p 8080:8080 [image name]
```


### Save the image:
To save an image to any file path or shared NFS place see the following example.

Get the image id by doing:

```docker images```
Say you have an image with id "matrix-data".

Save the image with id:   
```docker save -o /home/matrix/matrix-data.tar matrix-data```
https://stackoverflow.com/questions/23935141/how-to-copy-docker-images-from-one-host-to-another-without-using-a-repository



# Extra docker commands
> docker version

> docker run [image name] or docker container run [image name]   (the latter one is new version and suggested from Docker)

> docker container ls (show running container by default)

> docker container ls -a (show all containers)

> docker container create [image] (create container from image and is ready to be run with status: created)

> docker container start -a [container_id] (to start running container)

Note: docker run = docker create + docker start

> docker system prune --all (remove all containers)

> docker container stop [container_id] (to stop and give system the buffer of 10 seconds to stop the container)

> docker container kill [container_id] (to stop/kill it right away)

> docker container rm [container_id] (remove container)

> docker container rm -f [container_id] (remove container with force)

> docker container exec -it [container_id] [command] (run a command in a Running container with exec)

> docker image ls (list out all images)


