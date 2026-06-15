ARG BASE_IMAGE=ros:jazzy

FROM ${BASE_IMAGE}

# workaround interractive prompts during apt installations and install the PAIRS UAV System
RUN echo 'debconf debconf/frontend select Noninteractive' | sudo debconf-set-selections && \
    apt-get update && curl -fsSL https://thanhnguyencanh.github.io/apt/KEY.gpg | gpg --dearmor -o /usr/share/keyrings/pairs.gpg && \
    echo "deb [signed-by=/usr/share/keyrings/pairs.gpg] https://thanhnguyencanh.github.io/apt ${ROS_DISTRO} main" > /etc/apt/sources.list.d/pairs.list && \
    apt-get update && \
    apt-get --no-install-recommends -y install ros-${ROS_DISTRO}-pairs-uav-system-full \
    ros-${ROS_DISTRO}-mavros-extras gdb keyboard-configuration software-properties-common && \
    apt-get clean && rm -rf /var/lib/apt/lists/*

CMD ["/ros_entrypoint.sh"]
