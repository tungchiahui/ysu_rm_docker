# README

中文 | [English](README.md) 

1. 项目名称：ysu-ros-humble-jammy
2. 版本：v1.0
3. 版本状态：预发行版本
4. 作者：Tung Chia-hui
5. 网站：[tungchiahui.cn](https://www.tungchiahui.cn/)
6. 电子邮件：tungchiahui@gmail.com
7. 团队：燕山大学机器人创新社团燕鹰战队
8. 构建日期：2026-09-20
9. 未来功能：
    1. 无


# 项目说明

## 1. `拉取仓库`

### 功能

- 仓库链接：[https://hub.docker.com/r/tungchiahui/ysu-ros]https://hub.docker.com/r/tungchiahui/ysu-ros

### 使用方法

1. **拉取镜像**

   使用以下命令编译出二进制文件：

   ```bash
    # 拉取仓库镜像
    docker pull tungchiahui/ysu-ros:humble-jammy


2. **创建容器**

   使用以下命令创建：

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


