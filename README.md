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
docker run -it --privileged -e DISPLAY=$DISPLAY -v /tmp/.X11-unix:/tmp/.X11-unix:rw -v /dev/snd:/dev/snd:rw [-v <local dir for playonlinux>:/home/gamer:rw] playonlinux
```

The mount to your gamer dir is optional, but if you want to store saves outside of your container it is recommended.

## 3D Hardware Acceleration
Hardware acceleration is possible. You will need to have correct drivers installed in this build (this image is tested with an Intel Iris Pro 5200 and the Intel drivers are installed by default in Ubuntu.
Use the following parameter in your docker run command when using an Intel video card:
```
--device /dev/dri/card0:/dev/dri/card0
```

## Examples of running
First time usage:
```
docker run -it --privileged --device /dev/dri/card0:/dev/dri/card0 -e DISPLAY -v /tmp/.X11-unix:/tmp/.X11-unix:rw -v /dev/snd:/dev/snd:rw -v /home/joriss/Documents/Gamer:/home/gamer:rw --name playonlinux joriss/playonlinux
```
After running for the first time:
```
docker start playonlinux
```

