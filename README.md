
## Lightweight RESTful API with Spring Boot, PostgreSQL, JPA, Docker, Lombok, Spotify plugin, OpenAPI, etc.

[![Build Status](https://travis-ci.org/OKaluzny/spring-boot-docker-postgres.svg?branch=master)](https://travis-ci.org/OKaluzny/spring-boot-docker-postgres)

## How it works:
**1. Docker. First, you need to install docker**
* Download Docker [Here](https://docs.docker.com/docker-for-windows/install/). Hint: Enable Hyper-V feature on windows and restart;
* Then open powershell and check:
```bash
docker info
```
or check docker version
```bash
docker -v
```
or docker compose version
```bash
docker-compose -v
```
**2. Spring boot app**
* Clone the repository:
```bash
git clone https://github.com/OKaluzny/spring-boot-docker-postgres.git
```
* Build the maven project:
```bash
mvn clean install
```
* Running the containers:
  
This command will build the docker containers and start them.
```bash
docker-compose up
```
or

This is a similar command as above, except it will run all the processes in the background.
```bash
docker-compose -f docker-compose.yml up
```

Appendix A.

All commands should be run from project root (where docker-compose.yml locates)

* If you have to want to see running containers. Checklist docker containers
```bash
docker container list -a
```
or
```bash
docker-compose ps
```
# Screenshots

![Screenshot application list](/images/screenshot1.png)

*Dashboard with desktop notifications*

**Guide for using endpoints the app:**

Go to [http://localhost:8088/demo/api/automobiles](http://localhost:8088/demo/api/automobiles) to test and would specify basic authorization a username: `user` and password: `user` or username: `admin` and password: `admin`

* GET request to `/api/automobiles/` returns a list of "automobiles";
* GET request to `/api/automobiles/1` returns the "automobile" with ID 1;
* POST request to `/api/automobiles/` with a "automobile" object as JSON creates a new "automobile";
* PUT request to `/api/automobiles/3` with a "automobile" object as JSON updates the "automobile" with ID 3;
* DELETE request to `/api/automobiles/4` deletes the "automobile" with ID 4;
* DELETE request to `/api/automobiles/` deletes all the "automobiles".
---
* GET request to `/api/automobiles?color=madeira-violet` returns the "automobile"`s with color madeira-violet;
* GET request to `/api/automobiles?name=BMW&color=techno-violet` returns the "automobile"`s with name BMW and color techno-violet;
* GET request to `/api/automobiles?colorStartsWith=Ma&page=0&size=2` returns the "automobile"`s with color which starts with "m". Included Pagination and sorting;

or use Swagger API [http://localhost:8088/demo/swagger-ui.html](http://localhost:8088/demo/swagger-ui.html)

and generation API docks [http://localhost:8088/demo/v3/api-docs.yaml](http://localhost:8088/demo/v3/api-docs.yaml)

* Do not forget, if you see db, open the Windows Services Manager on your Windows 10 computer and stop postgres

**3. Docker control commands**
* Check all the images you have:
```bash
docker images
```
* If you have to want see running containers:
```bash
docker ps
```
**4. End stop app**
*  Stop containers:
```bash
docker-compose down
```
* Remove old stopped containers of docker-compose
```bash
docker-compose rm -f
```



