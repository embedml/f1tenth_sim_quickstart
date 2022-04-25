# f1tenth_sim_quickstart

Guide to get started with the [f1tenth simulator](https://github.com/f1tenth/f1tenth_gym_ros)

### How to run F1Tenth Simulator

Pull container from EML packages
```
docker pull ghcr.io/embedml/f1tenth_gym_ros:latest
```

Clone from f1tenth_gym_ros
```
git clone https://github.com/f1tenth/f1tenth_gym_ros.git
cd f1tenth_gym_ros
```

Run container from `docker-compose.yml` config
```
docker-compose up
```

Open new terminal window. Change directory to f1tenth_gym_ros again.\
Start bash session and ssh into container

```
docker exec -it f1tenth_gym_ros_sim_1 /bin/bash
```
Setup ROS commands and launch RVIZ sim\
(you can copy and paste the following all at the same time)
```
source /opt/ros/foxy/setup.bash
source install/local_setup.bash
ros2 launch f1tenth_gym_ros gym_bridge_launch.py
```
Open http://localhost:8080/vnc.html and click “connect”
To add Keyboard:
Open new terminal window. Change directory to simulator
```
docker exec -it f1tenth_gym_ros_sim_1 /bin/bash
```

Setup ROS commands and launch keyboard function\
(you can copy and paste the following all at the same time)
```
source /opt/ros/foxy/setup.bash
source install/local_setup.bash
ros2 run teleop_twist_keyboard teleop_twist_keyboard
```
