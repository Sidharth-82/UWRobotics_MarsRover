# UWRobotics_MarsRover

Workspace to create and configure a ROS2 Nav2 Geonavigation system using GPS. Docker Container configured to work with nav2 in ros2 Iron


```
docker run -it --net=host --privileged --volume="${XAUTHORITY}:/root/.Xauthority" --env="DISPLAY=$DISPLAY" -v="/tmp/.gazebo/:/root/.gazebo/" -v /tmp/.X11-unix:/tmp/.X11-unix:rw --shm-size=1000mb nav2_gps_iron
```
