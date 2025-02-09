FROM osrf/ros:iron-desktop-full

WORKDIR /home/realsense_ws

RUN . /opt/ros/iron/setup.sh \
    && apt-get update \
    && apt-get install -y python3-pip \
    python3-rosdep \
    ros-iron-librealsense2* \
    &&  apt autoremove -y \
    &&  rm -rf /var/lib/apt/lists/*

COPY src/ /home/realsense_ws/src

RUN . /opt/ros/iron/setup.sh \
    && apt-get update \
    && cd /home/realsense_ws/ \
    && rm -f /etc/ros/rosdep/sources.list.d/20-default.list \ 
    && rosdep init --include-eol-distros \
    && rosdep update --include-eol-distros \
    && rosdep install -i --from-path src --rosdistro $ROS_DISTRO --skip-keys=librealsense2 -y \
    && colcon build \
    && rm -rf /var/lib/apt/lists/*

# COPY ros_entrypoint.sh /
# ENTRYPOINT [ "/ros_entrypoint.sh" ]

CMD ["/bin/bash"]