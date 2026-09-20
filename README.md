# README

[中文](README-zh_CN.md) | English

1. Project Name: ysu-ros-humble-jammy
2. Version: v1.0
3. Status: Pre-release
4. Author: Tung Chia-hui
5. Website: [tungchiahui.cn](https://www.tungchiahui.cn/)
6. Email: tungchiahui@gmail.com
7. Team: Yanying Robotics Team, Robotics Innovation Club, Yanshan University
8. Build Date: 2026-09-20
9. Future Features:
   1. None


# Project Description

## 1. Pull the Image

### Overview

- Docker Hub: [https://hub.docker.com/r/tungchiahui/ysu-ros](https://hub.docker.com/r/tungchiahui/ysu-ros)

### Usage

1. **Pull the Docker Image**

   Use the following command to pull the image:

   ```bash
   # Pull the Docker image
   docker pull tungchiahui/ysu-ros:humble-jammy
   ```

2. **Create the Container**

   Use the following command to create and start the container:

   ```bash
   sudo docker run --name=ysu_ros_humble \
     --gpus all \
     -e NVIDIA_DRIVER_CAPABILITIES=all \
     -e DISPLAY=$DISPLAY \
     -dit \
     --privileged \
     --net=host \
     --group-add audio \
     --group-add video \
     --group-add dialout \
     -e XAUTHORITY=$HOME/.Xauthority \
     -e WAYLAND_DISPLAY=$WAYLAND_DISPLAY \
     -e XDG_RUNTIME_DIR=$XDG_RUNTIME_DIR \
     -e QT_QPA_PLATFORM=xcb \
     -v /tmp/.X11-unix:/tmp/.X11-unix:rw \
     -v /dev/dri:/dev/dri \
     -v $HOME/.Xauthority:$HOME/.Xauthority:ro \
     -v /run/user/$(id -u)/wayland-0:/run/user/$(id -u)/wayland-0 \
     -v /run/user/$(id -u):/run/user/$(id -u) \
     -v $HOME:$HOME \
     -w $HOME \
     tungchiahui/ysu-ros:humble-jammy
   ```
