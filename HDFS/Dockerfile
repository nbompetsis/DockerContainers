FROM centos:7.3.1611

LABEL maintainer "Nikolas Bompetsis <nikolas.mpompetsis@gmail.com>"

LABEL HDFS 2.7.3

USER root

# Installing dev tools
RUN rpm --import /etc/pki/rpm-gpg/RPM-GPG-KEY-CentOS-7 && \
    yum install -y curl which tar wget sudo openssh-server openssh-clients && \
    yum -y install java-1.8.0-openjdk-headless which && \
    yum clean all ;

ENV JAVA_HOME /usr/lib/jvm/jre

