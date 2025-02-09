FROM osrf/ros:iron-desktop-full

WORKDIR /home/nav2_gps_ws

RUN . /opt/ros/iron/setup.sh \
    && apt-get update \
    && apt-get install -y python3-pip \
    ros-iron-demo-nodes-cpp \
    ros-iron-robot-localization \
    ros-iron-mapviz \
    ros-iron-mapviz-plugins \
    ros-iron-tile-map \
    ros-iron-navigation2 \
    ros-iron-nav2-bringup \
    ros-iron-turtlebot3-gazebo \
    ros-iron-xacro \
    ros-iron-turtlebot3-msgs \
    ros-iron-slam-toolbox \
    &&  apt autoremove -y \
    &&  rm -rf /var/lib/apt/lists/*

COPY ./ /home/nav2_gps_ws/src

RUN . /opt/ros/iron/setup.sh \
    && apt-get update \
    && cd /home/nav2_gps_ws/ \
    && colcon build \
    && rm -rf /var/lib/apt/lists/*

# COPY ros_entrypoint.sh /
# ENTRYPOINT [ "/ros_entrypoint.sh" ]

CMD ["bash"]