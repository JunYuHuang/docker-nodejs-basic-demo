# Docker + Node.js

Dockerize a Node.js app.

Watch the full [Docker video](https://youtu.be/gAkwW2tuIqE) on YouTube or read the [Docker Tutorial](https://fireship.io/lessons/docker-basics-tutorial-nodejs/) on Fireship.io.

## Docker Image Details

- name (tag): `fireship/demoapp:1.0`
- hash: `c9b4adbfddc87c63e709023349fc0c3e0`

## My Notes

- `docker ps`: view all running Docker containers in local machine
- `docker build -t {dockerImageName} {pathToDockerfile}`:
  - builds the Docker image with the Dockerfile
- `docker run -p {outsidePort}:{insidePort} {dockerImageHash}`:
  - `{outsidePort}`: port that the app will run locally (outside the container)
  - `{insidePort}`: port that the app will run in the container
  - runs the Docker image so the image is accessible outside the container via the port `{outsidePort}` via port forwarding
- `volumes`: a dedicated folder on the host machine (running the Docker containers)
  - a tool for sharing peristent data / files among multiple containers
  - why?
    - containers lose all their state when they stop running
  - `docker volume create {folderName}`: creates a Docker volume
  - `docker run --mount source={folderName},target={subfolder}`:
    - runs a docker container that uses data from a volume
- debugging
  - check logs for each container
    - via Docker Desktop client
    - via Docker CLI `docker exec`
- tips
  - use microservice architecture
  - run 1 process per container
- Docker Compose: tool for running multiple containers at the same time
  - `docker-compose up`: runs several containers at same time
  - `docker-compose down`: shut down the containers set
