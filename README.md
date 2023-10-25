# Docker Rust Example

A simple Rust server/microservice example for [Docker's Rust Language Guide](https://docs.docker.com/language/rust/) I went through to learn Docker and how it works with Rust.

-) To build adocker image:
```
cd docker-rust && docker build --tag docker-rust-image .
```

-) To run the container (`--publish (-p)` tag is used to expose port 8000 inside the container to port 3001 outside the container to use `curl http://localhost:3001` later):
```
docker run -p 3001:8000 docker-rust-image
```

-) Since the example app is a simple web server, we don't have to be connected to the container, so we can run it in the detached mod (`--detach (-d)`), in background basically:
```
docker run -d -p 3001:8000 docker-rust-image
```

-) To see what containters are being run on your machine:
```
docker ps
```
OR
```
docker ps -a
```
to see all the existing containers

-) To stop the container:
```
docker stop [name]
```

-) To restart the container (detach mode):
```
docker restart [name]
```

-) To remove containers:
```
docker rm [name] [name] [name] ...
```

-) To give a certain name to the container:
```
docker run -d -p 3001:8000 --name [name] docker-rust-image
```