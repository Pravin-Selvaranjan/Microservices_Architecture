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

