# Use the official Ubuntu as the base image
FROM browserless/chrome:latest
# Set environment variables to avoid interactive prompts during installation
ENV DEBIAN_FRONTEND=noninteractive
USER root
# Install necessary dependencies, including wget
RUN apt-get update && apt-get install -y software-properties-common apt-transport-https gcc unzip wget curl xvfb vim libnss3 libatk-bridge2.0-0 libatspi2.0-0 python3.10 python3.10-distutils
RUN update-alternatives --install /usr/bin/python3 python3 /usr/bin/python3.10 1
RUN update-alternatives --config python3
RUN curl -m 900 -sS https://bootstrap.pypa.io/get-pip.py | python3.10
RUN apt-get update && apt-get install -y python3-distutils python3-pip python3-apt
# Additional packages
RUN apt-get clean
RUN rm -rf /var/lib/apt/lists/*
# Firefox Installation
# 安装Firefox的依赖库
RUN apt-get update && apt-get install -y firefox && \
    apt-get clean && rm -rf /var/lib/apt/lists/*
# sudo docker build -t web_services:base ./imagebase/
