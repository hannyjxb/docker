FROM selenium/standalone-chromium:131.0-chromedriver-131.0
USER root

# Set environment variables to avoid interactive prompts during installation
ENV DEBIAN_FRONTEND=noninteractive

# Install necessary dependencies, including wget
RUN apt-get update && apt-get install -y software-properties-common
RUN apt-get update && apt-get install -y apt-transport-https
RUN apt-get update && apt-get install -y gcc
RUN apt-get update && apt-get install -y unzip
RUN apt-get update && apt-get install -y wget
RUN apt-get update && apt-get install -y curl
RUN apt-get update && apt-get install -y xvfb
RUN apt-get update && apt-get install -y vim
RUN apt-get update && apt-get install -y libnss3
RUN apt-get update && apt-get install -y libatk-bridge2.0-0
RUN apt-get update && apt-get install -y  libatspi2.0-0
RUN add-apt-repository -y ppa:deadsnakes/ppa

RUN apt-get update && apt-get install -y python3.10 python3.10-distutils
RUN update-alternatives --install /usr/bin/python3 python3 /usr/bin/python3.10 1
RUN update-alternatives --config python3
RUN curl -m 900 -sS https://bootstrap.pypa.io/get-pip.py | python3.10

RUN apt-get update && apt-get install -y python3-distutils python3-pip python3-apt

# Firefox Installation
# 安装Firefox的依赖库
RUN apt-get update && apt-get install -y firefox && apt-get clean && rm -rf /var/lib/apt/lists/*
