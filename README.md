# Robotics-and-AI-Department-tasks
1st task of Robotics and AI Department Department - Summer training program at Smart Methods

![image](https://github.com/H16Bw/Robotics-and-AI-Department-tasks/assets/139852537/a1c167df-d151-465f-a5f2-3e1d0088a6ea)


# Report on setting up a virtual machine with Ubuntu and installing ROS Noetic and the Robot Arm package:

## 1. Download and Install VirtualBox:
Begin by downloading VirtualBox from the official website: https://www.virtualbox.org/wiki/Downloads. 

Follow the installation instructions based on your operating system.

## 2. Download Ubuntu Image:
Next, download the Ubuntu Desktop image from the official website: https://ubuntu.com/download/desktop. 

Choose the appropriate version, such as Ubuntu 20.04 LTS.

## 3. Create a New Virtual Machine in VirtualBox:
- Open VirtualBox and click on "New" to create a new virtual machine.
- Provide a name for the virtual machine (e.g., "ROS_Noetic_VM") and select "Linux" as the Type and "Ubuntu (64-bit)" as the Version.
- Assign memory (RAM) to the virtual machine (at least 2 GB is recommended).
- Choose "Create a virtual hard disk now" and select "VDI" as the hard disk file type.
- Choose "Dynamically allocated" for the storage on physical hard disk and set the desired size (at least 20 GB).

## 4. Configure Virtual Machine Settings:
Before starting the virtual machine, right-click on it in VirtualBox and select "Settings." In the settings, navigate to the "Storage" tab and add the Ubuntu ISO image to the virtual CD/DVD drive as the installation medium.

## 5. Install Ubuntu in the Virtual Machine:
- Start the virtual machine, and it will boot from the Ubuntu ISO image.
- Follow the on-screen instructions to install Ubuntu as you would on a regular system.
- Once the installation is complete, the virtual machine will restart, and you will have a fresh Ubuntu installation.

### 5.1 Open Terminal on Ubuntu:
After Ubuntu is installed in the virtual machine, open the Terminal by clicking on the "Activities" button in the top-left corner, searching for "Terminal," and launching it.

### 5.2 Install ROS Noetic:
In the Terminal, execute the following commands to install ROS Noetic:

```
bash
sudo apt update
sudo apt install -y curl gnupg2 lsb-release
curl -s https://raw.githubusercontent.com/ros/rosdistro/master/ros.asc | sudo apt-key add -
sudo sh -c 'echo "deb http://packages.ros.org/ros/ubuntu $(lsb_release -sc) main" > /etc/apt/sources.list.d/ros-latest.list'
sudo apt update
sudo apt install -y ros-noetic-desktop-full
echo "source /opt/ros/noetic/setup.bash" >> ~/.bashrc
source ~/.bashrc
```

### 5.3 Create a Catkin Workspace:
In the Terminal, create a catkin workspace to organize your ROS packages:

```
bash
mkdir -p ~/catkin_ws/src
cd ~/catkin_ws
catkin_make
echo "source ~/catkin_ws/devel/setup.bash" >> ~/.bashrc
source ~/.bashrc
```

## 6. Install the Robot Arm Package:
Finally, use the Terminal to install the Robot Arm package (replace "robot_arm_package" with the actual package name):

``
`bash
sudo apt install ros-noetic-robot-arm-package
```

With these steps completed, you now have a virtual machine with Ubuntu, ROS Noetic installed, and the Robot Arm package ready to be used for your robotics projects. Ensure to refer to official ROS documentation for further information on working with ROS and the Robot Arm package.
