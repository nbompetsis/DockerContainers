# Use ubuntu 18:04 as base image
FROM ubuntu:18.04

# Labels of image
LABEL image=apache-spark
LABEL maintainer "Nikolas Bompetsis <nikolas.mpompetsis@gmail.com>"

# Spark and Hadoop versions
ENV SPARK_VERSION=3.1.1
ENV HADOOP_VERSION=2.7

# Install the below packages on the ubuntu image
RUN apt-get update -qq && \
    apt-get install -qq -y gnupg2 wget openjdk-8-jdk scala python3 python-numpy 

# Download Spark binaries 
WORKDIR /
RUN wget --no-verbose https://ftp.cc.uoc.gr/mirrors/apache/spark/spark-3.1.1/spark-3.1.1-bin-hadoop2.7.tgz

# Untar the downloaded binaries
# Move them to spark folder
# Add spark binaries to PATH
RUN tar -zxvf /spark-3.1.1-bin-hadoop2.7.tgz && \
    rm /spark-3.1.1-bin-hadoop2.7.tgz && \
    mv /spark-3.1.1-bin-hadoop2.7 spark && \
    echo "export PATH=$PATH:/spark/bin" >> ~/.bashrc

# Expose Port 4040 of Spark UI.
EXPOSE 4040
