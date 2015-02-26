# Docker-playonlinux
A Dockerbuild to create a docker image with playonlinux... a must have for all you Linux gamers

## Installation:
```
git clone https://github.com/HEnKHub/Docker-playonlinux
docker build -t playonlinux <build file path>
```
Or get the image from Docker hub:
```
docker pull joriss/playonlinux
```

## Usage:
```
docker run -it -e DISPLAY=$DISPLAY -v /tmp/.X11-unix:/tmp/.X11-unix playonlinux
```

Of course you could mount extra drives in case you want to store save-data somewhere.

#TODO
See if hardware acceleration is possible with a Docker container.
