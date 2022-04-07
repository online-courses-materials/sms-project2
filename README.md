# sms-course-projects

- Creating the projects 
```bash
os@ubuntu:~$ cd catkin_ws/
ros@ubuntu:~/catkin_ws$ mkdir project2_ws
ros@ubuntu:~/catkin_ws$ cd project2_ws/
ros@ubuntu:~/catkin_ws/project2_ws$ mkdir src
ros@ubuntu:~/catkin_ws/project2_ws$ ls
src
ros@ubuntu:~/catkin_ws/project2_ws$ cd src/
ros@ubuntu:~/catkin_ws/project2_ws/src$ catkin_create_pkg project2 roscpp
Created file project2/package.xml
Created file project2/CMakeLists.txt
Created folder project2/include/project2
Created folder project2/src
Successfully created files in /home/ros/catkin_ws/project2_ws/src/project2. Please adjust the values in package.xml.
ros@ubuntu:~/catkin_ws/project2_ws/src$ cd ..
ros@ubuntu:~/catkin_ws/project2_ws$ catkin_make
Base path: /home/ros/catkin_ws/project2_ws
Source space: /home/ros/catkin_ws/project2_ws/src
.
.
.
-- ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
-- +++ processing catkin package: 'project2'
-- ==> add_subdirectory(project2)
-- Configuring done
-- Generating done
-- Build files have been written to: /home/ros/catkin_ws/project2_ws/build
####
#### Running command: "make -j4 -l4" in "/home/ros/catkin_ws/project2_ws/build"
####
Scanning dependencies of target rpm_pub
Scanning dependencies of target speed_calc
[ 50%] Building CXX object project2/CMakeFiles/rpm_pub.dir/src/rpm_pub.cpp.o
[ 50%] Building CXX object project2/CMakeFiles/speed_calc.dir/src/speed_calc.cpp.o
[ 75%] Linking CXX executable /home/ros/catkin_ws/project2_ws/devel/lib/project2/rpm_pub
[100%] Linking CXX executable /home/ros/catkin_ws/project2_ws/devel/lib/project2/speed_calc
[100%] Built target rpm_pub
[100%] Built target speed_calc
ros@ubuntu:~/catkin_ws/project2_ws$

```
- Clone the repository 
```bash
ros@ubuntu:~/catkin_ws/project2_ws$ git clone "https://github.com/online-courses-materials/sms-project2.git"
```

- Run the rosecore in the command line
```bash
ros@ubuntu:~/catkin_ws/project1_ws$ roscore
.. logging to /home/ros/.ros/log/2eef3038-b49f-11ec-8a39-8b31e70de496/roslaunch-ubuntu-2895.log
Checking log directory for disk usage. This may take a while.
Press Ctrl-C to interrupt
Done checking log file disk usage. Usage is <1GB.

started roslaunch server http://ubuntu:36287/
ros_comm version 1.15.13


SUMMARY
========

PARAMETERS
 * /rosdistro: noetic
 * /rosversion: 1.15.13

NODES

auto-starting new master
process[master]: started with pid [2906]
ROS_MASTER_URI=http://ubuntu:11311/

setting /run_id to 2eef3038-b49f-11ec-8a39-8b31e70de496
process[rosout-1]: started with pid [2918]
started core service [/rosout]
```
- Compile the project
```bash
ros@ubuntu:~/catkin_ws/project2_ws$ catkin_make
```
- Run the subscriber node in the new tab
```bash
ros@ubuntu:~/catkin_ws/project2_ws$ source devel/setup.bash
os@ubuntu:~/catkin_ws/project2_ws$ rosrun project2 rpm_pub
[ INFO] [1649312650.755458099]: Publishing RPM...
```
- Run the publisher node in the new tab
```bash
ros@ubuntu:~/catkin_ws/project2_ws$ source devel/setup.bash
ros@ubuntu:~/catkin_ws/project2_ws$ rosrun project2 speed_calc 
```
- Run the publisher node in the new tab
```bash
os@ubuntu:~/catkin_ws/project2_ws$ rostopic list
/rosout
/rosout_agg
/rpm
/speed
ros@ubuntu:~/catkin_ws/project2_ws$ rostopic echo rpm
data: 60.0
---
data: 60.0
---
data: 60.0
ros@ubuntu:~/catkin_ws/project2_ws$ rostopic echo speed
data: 0.7853975296020508
---
data: 0.7853975296020508
---
data: 0.7853975296020508

```
