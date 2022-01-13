## Common docker commands 
- sudo yum -y install docker
- sudo systemctl start docker
- sudo docker info
- docker system info
- docker run hello-world
- docker ps
- docker ps -a
- docker run --name web-server -d -p 8080:80 nginx:1.12
- docker stop web-server
- docker start web-server
- docker logs web-server
- docker exec -it web-server /bin/bash
- docker exec web-server ls /etc/nginx

# Test a python-flask project with docker 
## Clone a git repo
- git clone https://github.com/cloudacademy/flask-content-advisor.git
- cd flask-content-advisor

##  Create a Dockerfile with the following content
    FROM python:3
    WORKDIR /usr/src/app
    COPY . .
    RUN pip install --no-cache-dir -r requirements.txt
    EXPOSE 5000
    CMD [ "python", "./src/app.py" ]

- docker build -t flaskapp .
- docker run --name advisor -p 80:5000 flaskapp
- test the app with you localhost:80
- 

# Cheat Sheet 

## Build 
- docker build -t myimage:1.0
- docker image ls
- docker image rm alpine:3.4

## Share 
- docker pull myimage:1.0
- docker tag myimage:1.0 myrepo/myimage:2.0 
- docker push myrepo/myimage:2.0

## Run 
- docker container run --name web -p 5000:80 alpine:3.9
- docker container stop web 
- docker container kill web
- docker network ls 
- docker container ls 
- docker container rm -f $(docker ps -aq)
- docker container logs --tail 100 web

## Container MGMT 
- docker create image 
- docker run image 
- docker start <container ..>
- docker stop <container ..>
- docker kill <container ..>
- docker restart <container ..>
 - docker pause <container ..>
 - docker unpause <container ..>
 - docker rm [-f] <container ..>

# Docker Compose 
- Docker Compose gives you with respect to defining and managing multi-container environments in Docker. You still get the benefits of being able to use source control, but the emphasis shifts to describing what you want instead of how to create it. By way of analogy, Docker Compose is similar to using Dockerfiles. You can run a container, attach to it, run some commands, and use Docker commit to create a new image from the container. But in most situations, you want the enhanced documentation and maintainability that a Dockerfile gives you for accomplishing the same task along with Docker build. Analogously, you usually want to use Docker Compose instead of running a series of Docker commands.
- Mange multi-container environments 
- 