# Docker Interview Questions

## What is Docker?

- Docker is a containerization platform that packages an application and its dependencies in a lightweight, portable container image. Containers run consistently across environments.

## What is a Docker image and a container?

- Image: a read-only template containing application code, runtime, libraries, and metadata.
- Container: a running instance of an image with an isolated filesystem and process namespace.

## What is Docker Compose?

- Docker Compose is a tool for defining and running multi-container applications using a YAML file (`docker-compose.yml`). It defines services, networks, and volumes.

## CMD vs ENTRYPOINT

- CMD: provides default arguments for the container. Can be overridden by `docker run` arguments.
- ENTRYPOINT: sets the main executable for the container. CMD can supply default arguments to ENTRYPOINT.

## Common Docker commands

- Build: `docker build -t myimage:tag .`
- Run: `docker run --rm -it myimage:tag`
- List images: `docker images`
- Exec into running container: `docker exec -it <container> /bin/bash`

## Best practices

- Keep images small by using slim base images and multi-stage builds.
- Pin base image versions.
- Avoid storing secrets in images; use runtime secrets or external secret managers.

## How do you list all running docker images

- `docker ps`

## How would you build and deploy a custom docker image

- Open a terminal in the same folder as your Dockerfile

```sh
docker login
docker build .
docker images # get the id of the docker image
docker tag IMAGE_ID NEW_IMAGE_NAME:latest
docker push NEW_IMAGE_NAME:latest
```

## Dockerfile

- Know the components of a Dockerfile and how to make your own
- This uses the ubuntu docker image and installs python and an python app

```Dockerfile
FROM ubuntu
RUN apt-get update && apt-get install curl python
COPY main.py /app/main.py
WORKDIR /app
ENTRYPOINT ["python /app/main.py"]
```

## How do you keep docker images lightweight?

- Disable caching in commands
- Reduce the amount of layers
- Use multi-stage builds
- Run multiple commands on the same line

## What is a multi-stage docker build and whats the benefit?

- A multi-stage docker build is a technique used to keep dockerfiles small.
- An example, use a dockerfile to build the application, then copy the compiled application and place on a lightweight image like alpine to serve the compiled app.

```Dockerfile
# syntax=docker/dockerfile:1

FROM golang:1.16 AS builder
WORKDIR /go/src/github.com/alexellis/href-counter/
RUN go get -d -v golang.org/x/net/html
COPY app.go ./
RUN CGO_ENABLED=0 GOOS=linux go build -a -installsuffix cgo -o app .

FROM alpine:latest
RUN apk --no-cache add ca-certificates
WORKDIR /root/
COPY --from=builder /go/src/github.com/alexellis/href-counter/app ./
CMD ["./app"]
```
