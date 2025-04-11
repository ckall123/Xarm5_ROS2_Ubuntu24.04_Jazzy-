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

### Try some examples
If you installed `ros-jazzy-desktop` above you can try some examples.
In one terminal, source the setup file and then run a C++ `talker`:
```
source /opt/ros/jazzy/setup.bash
ros2 run demo_nodes_cpp talker
```
In another terminal source the setup file and then run a Python `listener`:
```
source /opt/ros/jazzy/setup.bash
ros2 run demo_nodes_py listener
```
### ...OR You can add `Source /opt/ros/jazzy/setup.bash` to your `.bashrc`
Type in the terminal:
```
echo "source /opt/ros/jazzy/setup.bash" >> ~/.bashrc
source ~/.bashrc
```
#### Try examples:
**talker**
```
ros2 run demo_nodes_cpp talker
```
**listener:**
```
ros2 run demo_nodes_py listener
```
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

### Install Tips [URL](https://gazebosim.org/docs/all/getstarted/)
[Summary of Compatible ROS and Gazebo Combinations](https://gazebosim.org/docs/latest/ros_installation/)

- ### 2.3 Install [Gazebo](https://classic.gazebosim.org/tutorials?tut=install_ubuntu)


- #### if you install ROS 2 Jazzy - ******************-------------you will found it is not useful-------------******************

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

**Tips:**
- Gazebo 的版本更新： Gazebo 團隊最近對版本命名進行了調整，將新版本命名為 Gazebo Ionic，而不是之前的 Garden。因此，套件名稱也相應地更新了。 [Gazebo 官方公告](https://gazebosim.org/docs/latest/getstarted/)
  
- ROS 2 的整合： 如果你同時使用 ROS 2 Jazzy，Gazebo Ionic 與其有良好的整合性，可以提供更順暢的開發體驗。 [ROS 2 與 Gazebo 的整合](https://github.com/gazebosim/docs/blob/master/ros_installation.md)

- ### 2.3 Install [GZ Harmonic](https://gazebosim.org/docs/harmonic/install_ubuntu/)

1. First install some necessary tools:
- ```bash
  sudo apt-get update
  sudo apt-get install curl lsb-release gnupg
  ```
2. Then install Gazebo Harmonic:
- ```bash
  sudo curl https://packages.osrfoundation.org/gazebo.gpg --output /usr/share/keyrings/pkgs-osrf-archive-keyring.gpg
  echo "deb [arch=$(dpkg --print-architecture) signed-by=/usr/share/keyrings/pkgs-osrf-archive-keyring.gpg] http://packages.osrfoundation.org/gazebo/ubuntu-stable $(lsb_release -cs) main" | sudo tee /etc/apt/sources.list.d/gazebo-stable.list > /dev/null
  sudo apt-get update
  sudo apt-get install gz-harmonic
  ```
  
  ** ...OR if you already install `gz-ionic` **
  ```
  sudo apt remove gz-ionic
  sudo apt install gz-harmonic
  sudo apt install ros-jazzy-ros-gz
  ```
  
- ### 2.4 Install [ros_gz](https://github.com/gazebosim/ros_gz) - ROS 2 ↔ Gazebo Sim Bridge

  Since we are using **Gazebo Sim (Ionic)** instead of Gazebo Classic,  
we need to use the new bridge package `ros_gz` to integrate with ROS 2.

Install it via apt:

```bash
sudo apt install ros-jazzy-ros-gz
```
**More info:**
- [ros_gz GitHub Repository](https://github.com/gazebosim/ros_gz)
- [Gazebo ROS 2 Integration Guide](https://gazebosim.org/docs/latest/ros_installation/)

---

### 💬 Bonus 說明
**Note:** 
`gazebo_ros_pkgs` is used for **Gazebo Classic (e.g. gazebo11)**.  
Since this project uses `gz-ionic` (Gazebo Sim), please use `ros_gz` for ROS integration.

## 3. How To Use

- ### 3.1 Create a workspace && python venv
  Create a workspace - Skip this step if you already have a target workspace
  ```bash
    cd ~
    mkdir -p dev_ws/src
  ```
  Create a python venv
  ```bash
  sudo apt install python3-venv
  python3 -m venv ~/ros_env
  source ~/ros_env/bin/activate
  pip install rosdep
  ```
  ```
  pip3 install jinja2 typeguard --break-system-packages
  ```

- ### 3.2 Obtain source code of "xarm_ros2" repository
    ```bash
    # Remember to source ros2 environment settings first
    cd ~/dev_ws/src
    # DO NOT omit "--recursive"，or the source code of dependent submodule will not be downloaded.
    # Pay attention to the use of the -b parameter command branch, $ROS_DISTRO indicates the currently activated ROS version, if the ROS environment is not activated, you need to customize the specified branch (foxy/galactic/humble/jazzy)
    git clone https://github.com/xArm-Developer/xarm_ros2.git --recursive -b $ROS_DISTRO
    ```

- ### 3.3 Update "xarm_ros2" repository 
    ```bash
    cd ~/dev_ws/src/xarm_ros2
    git pull
    git submodule sync
    git submodule update --init --remote
    ```

- ### 3.4 Install dependencies
    ```bash
    # Remember to source ros2 environment settings first
    cd ~/dev_ws/src/
    sudo $(which rosdep) init
    rosdep update
    rosdep install --from-paths . --ignore-src --rosdistro $ROS_DISTRO -y
    ```

- ### 3.5 Build xarm_ros2
    ```bash
    sudo apt install colcon
    pip install empy
    pip install numpy
    pip install lark
    
    # Remember to source ros2 and moveit2 environment settings first
    cd ~/dev_ws/
    # build all packages
    colcon build
    
    # build selected packages
    colcon build --packages-select xarm_api
    ```
- ### Check it and Move
 `ls ~/dev_ws/src/xarm_ros2/xarm_gazebo/launch`
 `cd ~/dev_ws/`

  ```bash
  source install/setup.bash  # 每次開 terminal 都要 source 一次

  # 啟動 Gazebo 模擬環境（xarm with realsense）
  ros2 launch xarm_gazebo xarm5_beside_table_gazebo.launch.py
  # 然後啟動 MoveIt：
  ros2 launch xarm_moveit_config xarm5_moveit_planning_execution.launch.py
  ```
  #### 用程式控制」xArm
   



