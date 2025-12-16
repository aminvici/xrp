FROM ubuntu:16.04

RUN apt -y update
RUN apt -y upgrade
RUN apt -y install build-essential g++ git libbz2-dev wget python-dev
RUN apt -y install cmake flex bison graphviz graphviz-dev libicu-dev
RUN apt -y install jarwrapper java-common

RUN cd /tmp
ENV CM_INSTALLER=cmake-3.10.0-rc3-Linux-x86_64.sh
ENV CM_VER_DIR=/opt/local/cmake-3.10.0
RUN cd /tmp && wget https://cmake.org/files/v3.10/$CM_INSTALLER && chmod a+x $CM_INSTALLER
RUN mkdir -p $CM_VER_DIR
RUN ln -s $CM_VER_DIR /opt/local/cmake
RUN /tmp/$CM_INSTALLER --prefix=$CM_VER_DIR --exclude-subdir
RUN rm -f /tmp/$CM_INSTALLER

