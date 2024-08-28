# Behaviourtrees_rosmonitoring
Instructions to implement Behaviour Trees and Ros Monitoring 

Required Ros2 Humble, behaviour_trees_v3, Groot installation for visualization of Behaviour trees
git clone current repo to your ros_ws

$ mkdir -p ros_ws/src
$ cd ros_ws/src
$ git clone <current_repo_url>
$ cd ros_ws
$ colcon build
$ ros2 run bt_bumpgo bt_bumpgo_main
$ ros2 run groot Groot ( or ros2 run groot Groot)
  select monitor -> start -> connect local ( you can visualize behaviour trees graph)

Implementing Ros Monitoring
git clone this RosMonitoring Package https://github.com/autonomy-and-verification-uol/ROSMonitoring.git ( Install dependencies)
 $ cd ~/
 $ git clone https://github.com/autonomy-and-verification-uol/ROSMonitoring.git
 $ cd ROSMonitoring
 $ git checkout ros2

 Create a simple Offline monitor
 copy offline config file available in current git repo to RosMonitoring Repo
 ( There is no need to keep RosMonitoring repo in your Ros Workspace, it can be executed seperately)
$ cd ~/ROSMonitoring/generator/ros2_devel/
$ chmod +x generator
$ python3 ./generator --config_file offline_config.yaml

#to get rid of any errors ( follow these instructions in your ros_ws)
$ rm -rf build 
$ rm -rf install 
$ rm -rf log
#sourcing ros 2
$ source /opt/ros/humble/setup.bash 
#building
$ colcon build

In a terminal we do:
$ cd ~/ros_ws/
$ . install/setup.bash
$ ros2 launch src/monitor/launch/monitor.launch

Then, in another terminal we do:

$ cd ~/ros_ws/
$ . install/setup.bash
$ ros2 launch src/Bump-and-Go-with-Behavior-Trees/launch/run_instrumented.launch ( you can execute`this command src/Bump-and-Go-with-Behavior-Trees/launch/run_launch.py)

log.txt file will be generated in your repo







