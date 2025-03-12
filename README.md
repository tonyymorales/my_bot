## Robot Package Intructions for Operation

This will include information about required packages and a tutorial on the setup.

This repo is modified from Articulated Robotics Template for Navigaition, Mapping and Control of a differential drive mobile robot.

Work done by Tony Morales

## Tutorial

loading urdf in rviz

### robot publisher launch 
ros2 launch my_bot rsp.launch.py 

### joint state publisher for wheels
ros2 run joint_state_publisher_gui joint_state_publisher_gui 

### gazebo sim
ros2 launch my_bot launch_sim.launch.py
ros2 run teleop_twist_keyboard teleop_twist_keyboard


### launching slam toolbox
ros2 launch slam_toolbox online_async_launch.py slam_params_file:=~/ros2_ws/src/my_bot/config/mapper_params_online_async.yaml use_sim_time:=true

### To Do List 
- [ ] Serial Connection from RasPi to Arduino
- [ ] ROS Node Publising /joint_states
- [ ] 
- [ ] Run existing ROS joint_state_publisher 

