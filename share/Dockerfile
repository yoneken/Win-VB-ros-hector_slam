FROM ros:melodic-ros-core-bionic
WORKDIR /
ENV DEBIAN_FRONTEND=noninteractive
RUN sed -i 's@archive.ubuntu.com@ftp.jaist.ac.jp/pub/Linux@g' /etc/apt/sources.list && \
    apt update && \
    apt install -y iputils-ping net-tools git \
    python-sphinx python-breathe python-wstool python-catkin-tools && \
    mkdir -p /catkin_ws/src

WORKDIR /catkin_ws
RUN git clone https://github.com/DaikiMaekawa/hector_slam_example.git src/hector_slam_example && \
    wstool init src && \
    wstool update -t src && \
    rosdep install --from-paths src -y -r && \
    apt install -y ros-melodic-hector-slam ros-melodic-urg-node && \
    apt clean && \
    rm -rf /var/lib/apt/lists/* && \
    /opt/ros/melodic/env.sh catkin b -j 2 && \
    rm -rf /catkin_ws/build /catkin_ws/log

ENTRYPOINT ["devel/env.sh"]