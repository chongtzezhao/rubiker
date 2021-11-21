# Originally noob.txt

```
# after installing ubuntu, install the ROS Noetic:
# instructions adapted from http://wiki.ros.org/noetic/Installation/Ubuntu
# note some of these commands are very long and should be run as one line. Make ur window wider to see which are single lines
sudo sh -c 'echo "deb http://packages.ros.org/ros/ubuntu $(lsb_release -sc) main" > /etc/apt/sources.list.d/ros-latest.list'
sudo apt install curl
curl -s https://raw.githubusercontent.com/ros/rosdistro/master/ros.asc | sudo apt-key add -
sudo apt update
sudo apt install ros-noetic-desktop-full
echo "source /opt/ros/noetic/setup.bash" >> ~/.bashrc
source ~/.bashrc
sudo apt install python3-rosdep python3-rosinstall python3-rosinstall-generator python3-wstool build-essential
sudo rosdep init
rosdep update

# Do tutorials:
# http://wiki.ros.org/ROS/Tutorials Step 1 to 18
# got any questions ask.
# ignore all $ signs. They are to specify the start of a line of command (so you don't key in the wrong thing when the command is too long and broken into multiple lines on the webpage)
```
