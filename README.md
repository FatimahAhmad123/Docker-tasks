# Docker-tasks:
This Repository contains tasks related to docker which help in getting familiar with docker. It is designed to help you learn and practice various aspects of working with Docker containers and images.

## Task-1( Installation and basic usage):
In this task you have to install Docker in your system. If you already have docker installed, it is advised to reinstall and install again.
For installation, follow the tasks below:
1. Open the terminal on Ubuntu.

2. Remove any Docker files that are running in the system, using the following command:
```
$ sudo apt-get remove docker docker-engine docker.io
```
After entering the above command, you will need to enter the password of the root and press enter.

3. Check if the system is up-to-date using the following command:
```
$ sudo apt-get update
```
4. Install Docker using the following command:
```
$ sudo apt install docker.io
```
You’ll then get a prompt asking you to choose between y/n - choose y.

Now to run the hello-world example, run the follow command:
```
docker run hello-world
```
To pull and run the nginx image, use the following commands:
```
docker pull nginx
docker run -d -p 80:80 nginx
```
To stop and remove the container, use docker ps -a to get id of your container and then use it to stop and remove:
```
docker stop <container_id>
docker rm <container_id>
```

## Task-2 (Building and running a custom Docker image):
In this task you have to create a custom Docker image using a Dockerfile. 
Build your custom image using:
```
docker build -t custom-image .
```
Using c=volume mapping, map your required directory with cpp app in your container and run in interactive mode:
```
docker run -it -v /path/to/your/source:/new/path custom_image:latest bash
```
Now your container will run in interatctive mode and you an directly run your cpp_app from here.
```
g++ -o cpp_app main.cpp
```
Now to push to dockerhub, Tag your custom image with your Docker Hub username and the desired image name:
```
docker tag custom_image your-dockerhub-username/custom_image:latest
docker push your-dockerhub-username/custom_image_name:latest
```
## Task-3 (Docker Compose):
In this task you need a dockercompose.yml file and a dockerfile (the one created in previous task).
Build the docker compose file using:
```
docker-compose build
```
Now run it using:
```
docker-compose up
```
