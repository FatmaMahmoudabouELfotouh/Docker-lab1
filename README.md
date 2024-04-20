# ITI - Docker Lab 🐋

## Task 1: Working with Docker Hello-world Image
### Objective
Learn how to run a container using the hello-world image and manage containers and images.

### Steps
#### 1. Run a Container with hello-world Image
```bash 
   docker pull hello-world   
   bash docker run hello-world
```
#### 2. Check Container Status and Explain
```bash 
docker ps -a

CONTAINER ID   IMAGE         COMMAND    CREATED          STATUS                      PORTS     NAMES
c47a6fccc8df   hello-world   "/hello"   14 seconds ago   Exited (0) 14 seconds ago             naughty_tu

```
#### 3. Start the Stopped Container
```bash
 docker start c47a6fccc8df   or     docker start naughty_tu
```
#### 4. Remove the Container
```bash
   docker rm  naughty_tu
```
#### 5. Remove the Image
```bash

  docker rmi hello-world
```
---

## Task 2: Running Container with Ubuntu Image
### Objective
Run an Ubuntu container in interactive mode, create a file inside it, and manage containers.

### Steps
#### 1. Run Ubuntu Container in Interactive Mode
```bash
  
    dockrer run -it ubuntu
```
#### 2. Create a File inside the Container
```bash
    touch hello-docker

```
#### 3. Stop and Remove the Container
```bash
     1- docker stop naughty_tu
     2- docker rm naughty_tu 
```
#### 4. Check File Status
```bash
```
#### 5. What happened to hello-docker file?
```bash
    when remove the container all changes made inside he comtainer including the creation of files like hello-docker are removed
```
#### 6. Remove All Stopped Containers
```bash
    docker container prune
```
#### 7. Bonus: Remove All Containers in One Command
```bash
   docker container prune -f
```

---
## Task 3: Creating a Custom Nginx Docker Image
### Objective
Create a custom Docker image using Nginx and a local HTML file.

### Steps
#### 1. Create a Local HTML File
```bash
    touch index.html
```
#### 2. Write Dockerfile and Copy the HTML file to the Docker Image
```bash
   FROM nginx:alpine
   COPY index.html /usr/share/nginx/html/index.html
```
#### 3. Run Container with New Image
```bash
     docker build -t nginx-custom
```

#### 4. Test the Container, open your browser and navigate to http://localhost:8088 to check if everything is okay
```bash
   docker run -d -p  8080:80 nginx-custom
```

