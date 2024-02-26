# chimera_ros

Spot + floating arm


# Build

```bash
source /opt/ros/${ROS_DISTRO}/setup.bash # please replace ${ROS_DISTRO} with your specific env variable, e.g., noetic
mkdir -p ~/ros/chimera_ros_ws/src
cd ~/ros/chimera_ros_ws
rosdep update
wstool init src
wstool set -u -t src chimera_ros https://github.com/tongtybj/chimera_ros.git --git
wstool merge -t src src/chimera_ros/chimera.rosinstall
wstool update -t src
rosdep install -y -r --from-paths src --ignore-src --rosdistro $ROS_DISTRO
catkin build
```


## dependent packages:

### Floating arm
- URL: https://github.com/tongtybj/aerial_robot.git
- branch: develop/free_arm_robot/model

### Spot:
- URL: https://github.com/clearpathrobotics/spot_ros.git
- branch: master

### Valve (temporalry)
- URL: https://github.com/tongtybj/aerial_robot_demo
- branch: dragon/valve