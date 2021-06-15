# Typora-docker
```bash
docker builder build \
    --no-cache \
    --build-arg IMAGE_VERSION=unstable-slim \
    --build-arg GID=$(id -g) \
    --build-arg GID_NAME=$(id -gn) \
    --build-arg UID=$(id -u) \
    --build-arg UID_NAME=$(id -un) \
    --file Dockerfile \
    --tag ugeek/typora:amd64 .
```
```bash
xhost +local:docker
```
```bash
docker container run \
    --interactive \
    --tty \
    --privileged \
    --volume /tmp/.X11-unix:/tmp/.X11-unix \
    --env DISPLAY=unix$DISPLAY \
    --name typora ugeek/typora:amd64
```
