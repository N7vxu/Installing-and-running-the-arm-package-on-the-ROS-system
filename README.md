# Installing-and-running-the-arm-package-on-the-ROS-system

  download VMware



  download Ubuntu 16.4 desktop image
 Create a new virtual machine



 # Install ROS melodic

   1- Installation

1.1 Configure your Ubuntu repositories

Configure your Ubuntu repositories to allow "restricted," "universe," and "multiverse." You can follow the Ubuntu guide for instructions on doing 

1.2 this.Setup your sources.list

Setup your computer to accept software from packages.ros.org.

$ sudo sh -c 'echo "deb http://packages.ros.org/ros/ubuntu $(lsb_release -sc) main" > /etc/apt/sources.list.d/ros-latest.list'

1.3 Set up your keys

$ curl -s https://raw.githubusercontent.com/ros/rosdistro/master/ros.asc | sudo apt-key add -

1.4 Installation

First, make sure your Debian package index is up-to-date:

$ sudo apt update

Desktop-Full Install: (Recommended) : ROS, rqt, rviz, robot-generic libraries, 2D/3D simulators and 2D/3D perception

$ sudo apt install ros-melodic-desktop-full

1.5 Environment setup

$ echo "source /opt/ros/melodic/setup.bash" >> ~/.bashrc

$ source ~/.bashrc

1.6 Dependencies for building packages

To install this tool and other dependencies for building ROS packages, run:

$ sudo apt install python-rosdep python-rosinstall python-rosinstall-generator python-wstool build-essential

1.6.1 Initialize rosdep

$ sudo apt install python-rosdep

With the following, you can initialize rosdep.

$ sudo rosdep init

$ rosdep update


#  Create a workspace by using catkin_make

$ sudo apt-get install ros-melodic-catkin

$ mkdir -p ~/catkin_ws/src

$ cd ~/catkin_ws/

$ catkin_make

$ cd ~/catkin_ws/src

$ git clone https://github.com/smart-methods/arduino_robot_arm.git 

$ cd ~/catkin_ws

$ rosdep install --from-paths src --ignore-src -r -y

$ sudo apt-get install ros-kinetic-moveit

$ sudo apt-get install ros-kinetic-joint-state-publisher ros-kinetic-joint-state-publisher-gui

$ sudo apt-get install ros-kinetic-gazebo-ros-control joint-state-publisher

$ sudo apt-get install ros-kinetic-ros-controllers ros-kinetic-ros-control

$ sudo nano ~/.bashrc

$ /home/nada/catkin_ws/src:/opt/ros/kinetic/share

$ source ~/.bashrc

$ roslaunch robot_arm_pkg check_motors.launch
