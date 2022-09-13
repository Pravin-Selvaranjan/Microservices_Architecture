# How to install Docker

![architecture](https://user-images.githubusercontent.com/110179866/189690669-866ee9fa-2896-4d23-8868-bae6cbdae761.svg)

- Install Docker here [Docker](https://docs.docker.com/desktop/install/windows-install/)
- Ensure to follow troubleshooting tips and be on the correct version of Windows 10/11
- You will be prompted to restart your machine multiple times in order to get Docker up and running

- Navigate to your terminal and run `docker run hello-world`
- `docker images` you should now be able to see hello-world under the list of your images
- Docker is installed and working
- `docker run -p 80:80 nginx` this will open nginx up on the specified port 
- `docker run -d -p 80:80 nginx` this will run in the background so you can continue to use the same terminal 
- `alias docker="winpty docker` ensure to run this command to alter the variable
- `docker exec -it idofrunningimage bash` this will take you into the machine
- ensure to `docker install update -y`
- use `docker login` and `docker logout` respectively 
## Other commands to be used
`docker pull name_of_image`

`docker run name_of_image`

`docker build -t name_of_image`

`docker commit name_of_image/container-id`

`docker start container-id`

`docker stop conainer-id/name`

`docker rm container-id/name`

`docker ps and ps -a`

`docker run` – Runs a command in a new container.

`docker start` – Starts one or more stopped containers

`docker stop` – Stops one or more running containers

`docker build` – Builds an image form a Docker file

`docker pull` – Pulls an image or a repository from a registry

`docker push` – Pushes an image or a repository to a registry

`docker export` – Exports a container’s filesystem as a tar archive

`docker exec` – Runs a command in a run-time container

`docker search` – Searches the Docker Hub for images

`docker attach` – Attaches to a running container

`docker commit` – Creates a new image from a container’s changes


Link to further commands and explanations [Docker Commands](https://www.edureka.co/blog/docker-commands/)

Link to extensive documentation on how to use Docker [Docker cheat](https://stackify.com/docker-tutorial/)


![dockercheatsheet8](https://user-images.githubusercontent.com/110179866/189697839-55e2de8e-a8fd-4729-8faf-dbda4a4ae722.png)


# Replacing index.html in Nginx

- 1- move file from localhost to container
- 2- delete the existing file
- 3- send file.html from localhost to container
- 4- copy data from a - b

## Example of copying
```
 docker cp ./some_file CONTAINER:/work 
 
 
 # Copy local files to container

 ```



# Creating a Dockerfile

- Create file named `Dockerfile` in same location where `index.html` is 

```

# Select base image

FROM nginx     # which image do you want to use

# label it

LABEL MAINTAINER=pravin     # naming 

# copy data from localhost to the container
COPY index.html /usr/share/nginx/html/    # copy the data from our lh to the folder  within the image

# allow required port

EXPOSE 80                # port required for exposure 

# execute required command

CMD ["nginx", "-g", "daemon off;"]      # command given to us by dockerhub to use 

```
- run `docker build -t pselvaranjan/nginx_host_pravin .` the "." denotes dockerfiles contained within this location
- run `docker run -d -p 80:80 pselvaranjan/nginx_host_pravin`
- Your html page should now be live 