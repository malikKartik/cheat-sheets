## Setting up postgres in docker for development

- Install docker
- pull image
```docker pull postgres:alpine (or with any other tag)```
- Run a container with exposed port
```docker run --name postgres-container-name -e POSTGRES_PASSWORD=mysecretpassword -d -p 5432:5432 postgres'
This will map the post 5432 of container to the post 5432 of the Local machine