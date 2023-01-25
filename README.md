# orange_ros2 v0.3.2 [![](https://img.shields.io/badge/ROS2%20Humble-stable-green?style=flat-square&logo=ros)](https://github.com/KBKN-Autonomous-Robotics-Lab/orange_ros2)
This project is to use orange robot with ROS2.
## Setup
```
$ git clone https://github.com/KBKN-Autonomous-Robotics-Lab/orange_ros2.git
$ rosdep install -r -y -i --from-paths .
```
## Launch simulation world
- empty_world
<img src="https://user-images.githubusercontent.com/84959376/211162608-ba114bec-af38-4f07-95ed-8c0dbecca21b.png" width="500px">

```
$ ros2 launch orange_gazebo empty_world.launch.xml
```
- orange_world
<img src="https://user-images.githubusercontent.com/84959376/211162925-7293f724-f4dd-422d-8253-d741626cc434.png" width="500px">


```
$ ros2 launch orange_gazebo orange_world.launch.xml
```
- orange_igvc
<img src="https://user-images.githubusercontent.com/84959376/214539778-0fc88537-64b0-4d26-bdbc-762e1df343cb.png" width="500px">

```
$ ros2 launch orange_gazebo orange_igvc.launch.xml
```
## Operate orange robot
- keyboard

```
$ ros2 launch orange_teleop teleop_keyboard.launch.xml
```
- gamepad

```
$ ros2 launch orange_teleop teleop_joy.launch.xml
```
## RViz2 visualization
<img src="https://user-images.githubusercontent.com/84959376/211379404-81bacf08-63d7-4fb6-bd76-46f2627bbe23.png" width="500px">

```
$ ros2 launch orange_bringup rviz2.launch.xml
```
## SLAM

### slam_toolbox
<img src="https://user-images.githubusercontent.com/84959376/214502711-18c58840-1b5b-4886-87c0-020549de0db1.png" width="300px">

- Gazebo simulation
```
$ ros2 launch orange_gazebo orange_world.launch.xml
$ ros2 launch orange_slam slam_toolbox.launch.xml
$ ros2 launch orange_teleop teleop_keyboard.launch.xml
```
- ros2 bag
```
$ ros2 bag play your_bag -r 3
$ ros2 launch orange_slam slam_toolbox.launch.xml with_ros2bag:=true
```
### cartographer
<img src="https://user-images.githubusercontent.com/84959376/214502942-ac4e9211-6b20-4722-9e50-fe6df9166c4b.png" width="300px">

- Gazebo simulation
```
$ ros2 launch orange_gazebo orange_world.launch.xml
$ ros2 launch orange_slam cartographer.launch.xml
$ ros2 launch orange_teleop teleop_keyboard.launch.xml
```
- ros2 bag
```
$ ros2 bag play your_bag -r 3
$ ros2 launch orange_slam cartographer.launch.xml with_ros2bag:=true
```
