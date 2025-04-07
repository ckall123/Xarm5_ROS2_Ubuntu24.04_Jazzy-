# Xarm5_ROS2_Ubuntu24.04_Jazzy-

# xarm_ros2

For simplified Chinese version: [简体中文版](./ReadMe_cn.md)

## 1. Introduction

&ensp;&ensp;&ensp;&ensp;This repository contains simulation models, and corresponding motion planning and controlling demos of the xArm series from UFACTORY. The development and test environment is as follows
- Ubuntu 20.04 + ROS Foxy
- Ubuntu 20.04 + ROS Galactic
- Ubuntu 22.04 + ROS Humble
- Ubuntu 24.04 + ROS Jazzy
- Ubuntu 22.04 + ROS Rolling

&ensp;&ensp;&ensp;&ensp;Please switch to the corresponding code branch according to different ros2 versions (no corresponding code branch means it has not been tested in this version)
- Foxy: [foxy](https://github.com/xArm-Developer/xarm_ros2/tree/foxy)
- Galactic: [galactic](https://github.com/xArm-Developer/xarm_ros2/tree/galactic)
- Humble: [humble](https://github.com/xArm-Developer/xarm_ros2/tree/humble)
- Jazzy: [jazzy](https://github.com/xArm-Developer/xarm_ros2/tree/jazzy)
- Rolling: [rolling](https://github.com/xArm-Developer/xarm_ros2/tree/rolling)


## 2. Preparation

1. 啟用必要的軟體庫：

- ``` bash
  sudo apt install software-properties-common
  sudo add-apt-repository universe
  ```
2. 添加 ROS 2 的 GPG 金鑰：
- ``` bash 
  sudo apt update && sudo apt install curl -y
  sudo curl -sSL https://raw.githubusercontent.com/ros/rosdistro/master/ros.key -o /usr/share/keyrings/    ros-archive-keyring.gpg
  ```
3. 添加 ROS 2 軟體庫到你的 sources list：
- ```
  echo "deb [arch=$(dpkg --print-architecture) signed-by=/usr/share/keyrings/ros-archive-keyring.gpg] http://packages.ros.org/ros2/ubuntu $(. /etc/os-release && echo $UBUNTU_CODENAME) main" | sudo tee /etc/apt/sources.list.d/ros2.list > /dev/null
  ```

這些步驟的詳細說明可以參考官方文檔：
[Ubuntu (deb packages) - Jazzy documentation - ROS 2](https://docs.ros.org/en/jazzy/Installation/Ubuntu-Install-Debs.html)



完成上述步驟後，更新你的軟體包索引：
- ```bash
  sudo apt update
  ```

- ### 2.1 Install [ROS2](https://docs.ros.org/) 
  - [Foxy](https://docs.ros.org/en/ros2_documentation/foxy/Installation.html)
  - [Galactic](https://docs.ros.org/en/ros2_documentation/galactic/Installation.html)
  - [Humble](https://docs.ros.org/en/ros2_documentation/humble/Installation.html)
  - [Jazzy](https://docs.ros.org/en/ros2_documentation/jazzy/Installation.html) -- I chose it

- ### 2.2 Install [Moveit2](https://moveit.ros.org/install-moveit2/binary/)
- ```
  sudo apt install ros-jazzy-moveit
  ```

- ### 2.3 Install [Gazebo](https://classic.gazebosim.org/tutorials?tut=install_ubuntu)


- #### if you install ROS 2 Jazzy

1. 安裝必要的工具：
- ```bash
  sudo apt-get update
  sudo apt-get install lsb-release gnupg curl
  ```
2. 添加 Gazebo 的官方 GPG 金鑰：
- ```bash
  sudo curl -sSL https://packages.osrfoundation.org/gazebo.gpg -o /usr/share/keyrings/pkgs-osrf-archive-keyring.gpg
  ```
3. 添加 Gazebo 的套件庫到系統來源列表：
- ```bash
  echo "deb [arch=$(dpkg --print-architecture) signed-by=/usr/share/keyrings/pkgs-osrf-archive-keyring.gpg] http://packages.osrfoundation.org/gazebo/ubuntu-stable $(lsb_release -cs) main" | sudo tee /etc/apt/sources.list.d/gazebo-stable.list > /dev/null
  ```
4. 更新套件列表並安裝 Gazebo Ionic：
- ```bash
  sudo apt-get update
  sudo apt-get install gz-ionic
  ```

安裝完成後，你就可以使用最新版本的 Gazebo 模擬器了！🚀

這些步驟是根據 Gazebo 官方的安裝指南整理 [Gazebo 官方安裝指南](https://gazebosim.org/docs/latest/install_ubuntu/)

- ### 2.4 Install [gazebo_ros_pkgs](http://gazebosim.org/tutorials?tut=ros2_installing&cat=connect_ros)  

