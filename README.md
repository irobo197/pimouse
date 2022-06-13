# raspimouse_sim

ROS package suite for Raspberry Pi Mouse

## ROS Package Status

| main develop<br>(master)|Melodic + Ubuntu Bionic<br>(melodic-devel)|
|:---:|:---:|
|[![industrial_ci](https://github.com/rt-net/raspimouse_sim/workflows/industrial_ci/badge.svg?branch=master)](https://github.com/rt-net/raspimouse_sim/actions?query=branch%3Amaster+workflow%3Aindustrial_ci)|[![industrial_ci](https://github.com/rt-net/raspimouse_sim/workflows/industrial_ci/badge.svg?branch=melodic-devel)](https://github.com/rt-net/raspimouse_sim/actions?query=branch%3Amelodic-devel+workflow%3Aindustrial_ci)|

The follwing branches are not maintained.

* rpim_book_version
* indigo-devel
* kinetic-devel


## Requirements

requires the following to run:

* Ubuntu
  * Ubuntu Bionic Beaver 18.04.*
* ROS
  * ROS Melodic Morenia
* Gazebo
  * Gazebo 9.x
* ROS Package
  * ros-melodic-desktop-full

## Installation

Download this ROS package.

```
cd ~/catkin_ws/src
git clone https://github.com/irobo197/pimouse.git
```
Build this package using `catkin_make`.

```
cd ~/catkin_ws && catkin_make
source ~/catkin_ws/devel/setup.bash
```
### SLAM

```
# robot side
roslaunch pimouse_slam robot_side.launch
# desktop side
roslaunch pimouse_slam desktop_side.launch
```

### Save map
```
roscd raspimouse_navigation/maps
rosrun map_server map_saver -f my_map
```
### Navigation

```
# robot side
roslaunch pimouse_slam robot_side.launch
# desktop side
roslaunch raspimouse_navigation raspimouse_navigation.launch
```
### Autonomous SLAM

```
# robot side
roslaunch pimouse_slam robot_side.launch
# desktop side
roslaunch raspimouse_autoslam autonomous_slam.launch
```
## License

This repository is licensed under the MIT license, see [LICENSE]( ./LICENSE ).  
Unless attributed otherwise, everything in this repository is under the MIT license.

### Acknowledgements

* [CIR-KIT/fourth_robot_pkg]( https://github.com/CIR-KIT/fourth_robot_pkg )
  * author
    * RyodoTanaka
  * maintainer
    * RyodoTanaka
  * BSD ([BSD 3-Clause License](https://opensource.org/licenses/BSD-3-Clause))
  * See [package.xml](https://github.com/CIR-KIT/fourth_robot_pkg/blob/indigo-devel/fourth_robot_control/package.xml) for details.
* [yujinrobot/kobuki]( https://github.com/yujinrobot/kobuki )
  * authors
    * Daniel Stonier
    * Younghun Ju
    * Jorge Santos Simon
    * Marcus Liebhardt
  * maintainer
    * Daniel Stonier
  * BSD ([BSD 3-Clause License](https://opensource.org/licenses/BSD-3-Clause))
  * See [package.xml](https://github.com/yujinrobot/kobuki/blob/melodic/kobuki/package.xml) for details。
