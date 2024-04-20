# ITI - Docker Lab 🐋

## Task 1: Working with Docker Hello-world Image
### Objective
Learn how to run a container using the hello-world image and manage containers and images.


### Steps
#### 1. Run a Container with hello-world Image
```bash
docker pull hello-world
**************************
docker run hello-world

```



#### 2. Check Container Status and Explain
```bash
docker ps -a
**********************************
container will execute  hello-world program , then exit
```


#### 3. Start the Stopped Container
```bash
docker start <container_id>
```


#### 4. Remove the Container
```bash
docker rm <container_id>

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
docker pull ubuntu
*************************
docker run -it ubuntu
```


#### 2. Create a File inside the Container
```bash
touch hello-docker
```



#### 3. Stop and Remove the Container
```bash
exit
***************
docker container stop <container_id>
**********************************
docker container rm <container_id>
```


#### 4. Check File Status
```bash
ls
ls -l
```

#### 5. What happened to hello-docker file?
```bash
hello-docker file are removed , as any changes made inside the container are not persisted after the container is removed.
```

#### 6. Remove All Stopped Containers
```bash
docker container prune
```


#### 7. Bonus: Remove All Containers in One Command
```bash
docker container prune
************************
docker rm -f $(docker ps -aq)

```


---
## Task 3: Creating a Custom Nginx Docker Image
### Objective
Create a custom Docker image using Nginx and a local HTML file.

### Steps
#### 1. Create a Local HTML File
```bash
vim index.html
***************
write inside Aya Adel Mohamed El-mahdy 
```
#### 2. Write Dockerfile and Copy the HTML file to the Docker Image
```bash
vim Dockerfile
*************
write inside :FROM nginx:1.23

COPY index.html /usr/share/nginx/html
```
#### 3. Run Container with New Image
```bash
```
docker build -t custom-nginx:v2.0 .

docker run -d -p 8080:80 custom-nginx:v2.0 .

#### 4. Test the Container, open your browser and navigate to http://localhost:8088 to check if everything is okay
```bash
```

