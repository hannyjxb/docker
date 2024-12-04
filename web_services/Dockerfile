# Use the official Ubuntu as the base image
FROM ubuntu:20.04
# Set environment variables to avoid interactive prompts during installation
ENV DEBIAN_FRONTEND=noninteractive
# Install necessary dependencies, including wget
RUN apt-get update -qq && apt-get install -y -qq software-properties-common apt-transport-https gcc unzip wget curl xvfb vim libnss3 libatk-bridge2.0-0 libatspi2.0-0 && add-apt-repository -y ppa:deadsnakes/ppa
RUN apt-get update && apt-get install -y python3.10 python3.10-distutils
RUN update-alternatives --install /usr/bin/python3 python3 /usr/bin/python3.10 1
RUN update-alternatives --config python3
RUN curl -m 900 -sS https://bootstrap.pypa.io/get-pip.py | python3.10
RUN apt-get update && apt-get install -y python3-distutils python3-pip python3-apt
# Additional packages
RUN apt-get clean
RUN rm -rf /var/lib/apt/lists/*
# Firefox Installation
# 安装Firefox的依赖库
RUN apt-get update && apt-get install -y firefox
# Chrome Installation
# Set up the Chrome PPA
RUN wget -q -O - https://dl-ssl.google.com/linux/linux_signing_key.pub | apt-key add -
RUN echo "deb [arch=arm64] https://dl.google.com/linux/chrome/deb/ stable main" >> /etc/apt/sources.list.d/google.list
# Update the package list and install chrome
RUN apt-get update && apt-get install -y google-chrome-stable
# Clean up
RUN apt-get clean && rm -rf /var/lib/apt/lists/*
# sudo docker build -t web_services:base ./imagebase/
