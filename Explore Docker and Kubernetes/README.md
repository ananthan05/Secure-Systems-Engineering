ANANTHANARAYANAN S
CB.SC.P2CYS23007


# Asisgnment on docker 


For the following task refer the link 1
* Create and use a Docker container interactively
* Create a Dockerfile, which allows you to declaratively define your containers
* Run detached containers and understand port forwarding
* Use docker-compose to run a multi-container web application

For the following task 1, 2, 3 refer link 3
* Task 1: Run some simple Docker containers
* Task 2: Package and run a custom app using Docker
* Task 3: Modify a Running Website

1.	https://decal.ocf.berkeley.edu/archives/2018-fall/labs/a11
2.	https://www.youtube.com/watch?v=F7We8xx1_Lw
3.	https://training.play-with-docker.com/beginner-linux/
https://github.com/dockersamples -- this  has apps for docker

# Set Up the Environment:

## Install Docker Desktop:

1. Visit the Docker Desktop for Windows download page.
2. Download the Docker Desktop installer.
3. Double-click Docker Desktop Installer.exe to run the installer.
4. Follow the installation instructions.

![image](https://github.com/ananthan05/Secure-Systems-Engineering/assets/140697378/e2a59ed1-577f-40a5-89ca-f7be9ce2b75d)

## Verify Installation:

1. Open a command prompt (Windows PowerShell or Command Prompt).
2. Run the command: docker --version
It should show client and server both installation where client is our host os command Prompt and server is Docker Engine.

![image](https://github.com/ananthan05/Secure-Systems-Engineering/assets/140697378/201e58bc-d0ea-4107-bd47-a0164319800b)

![image](https://github.com/ananthan05/Secure-Systems-Engineering/assets/140697378/4f15e761-3832-45ad-89f4-236a07392e22)

Run the hello-world Image docker run hello-world.

![image](https://github.com/ananthan05/Secure-Systems-Engineering/assets/140697378/026fae1b-6ebc-468d-8df3-74c7d69c0849)

## Create and use a Docker container interactively

```
docker run -it ubuntu bash
```

In this command -i refers to an interactive, -t refers to the tag that needs to be pulled. ubuntu is the tag name that gets pulled, bash is the command that would be run interactively.

![image](https://github.com/ananthan05/Secure-Systems-Engineering/assets/140697378/fddd75dc-ee20-42ad-8812-24dbc6cc6bc9)

```
docker images
```

![image](https://github.com/ananthan05/Secure-Systems-Engineering/assets/140697378/b9dfb36b-40b0-4119-8eaf-974dc53b8853)

## Create a Dockerfile, which allows you to declaratively define your containers

Create a file named Dockerfile in the current directory with the following contents.

```
FROM ubuntu:bionic

RUN apt-get update && apt-get install -y python3.6 --no-install-recommends

CMD ["/usr/bin/python3.6", "-i"]
```

Build an image using the instructions written in the Dockerfile.

```
docker build -t mypython:latest .
```

![image](https://github.com/ananthan05/Secure-Systems-Engineering/assets/140697378/5fd912f7-ec43-408d-9e28-662b2cd290b5)

Verify the created Docker Image.

```
docker images
```

![image](https://github.com/ananthan05/Secure-Systems-Engineering/assets/140697378/81991179-5e64-4557-98cd-280f4b12dc7a)

Interactively run the Docker Image and execute Python commands.

```
docker run -it mypython
```
![image](https://github.com/ananthan05/Secure-Systems-Engineering/assets/140697378/427be1b6-4c1f-45fb-82b5-60814da14eed)

## Run detached containers and understand port forwarding

```
docker run -d -p=5050:80 httpd
```
The -d in the above command instructs the Docker Engine to run the container in detached mode. This will make the container to keep running until we explicitly stop it.

The httpd is the name of an image already built and available in the Docker Hub. The -p flag takes in a colon separated pair of HOST_PORT:CONTAINER_PORT.

![image](https://github.com/ananthan05/Secure-Systems-Engineering/assets/140697378/cfcf017f-65ad-438b-8e74-032645f5b78f)

httpd image is downloaded successfully.

If we check in browser it works.

![image](https://github.com/ananthan05/Secure-Systems-Engineering/assets/140697378/076e60da-402c-4cf3-a2cd-972a07cf6a05)


##  Use docker-compose to run a multi-container web application

docker compose is installed by typing the below commands in the Terminal. As windows is there as hostOS, So docker compose is available

```
docker-compose version
```

![image](https://github.com/ananthan05/Secure-Systems-Engineering/assets/140697378/d7dd6640-7be2-4d86-a071-34d5caa941d3)

A Dockerfile is written in the project directory which would contain the instructions required for the deployment of the NodeJS project.

The NodeJS project is downloaded from the provided location by typing the below commands. 

git clone https://github.com/0xcf/decal-sp18-a10

`cd decal-sp18-a10`


