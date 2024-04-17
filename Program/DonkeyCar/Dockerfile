# 使用ubuntu 22.04作为基础镜像
FROM ubuntu:22.04

# 设置工作目录
WORKDIR /tmp

# 安装必要的工具
RUN apt-get update && apt-get install -y wget git

# 下载并安装Miniconda
RUN wget https://repo.anaconda.com/miniconda/Miniconda3-py39_23.3.1-0-Linux-x86_64.sh && \
    bash Miniconda3-py39_23.3.1-0-Linux-x86_64.sh -b -p /miniconda && \
    rm Miniconda3-py39_23.3.1-0-Linux-x86_64.sh

# 更新环境变量
ENV PATH="/miniconda/bin:${PATH}"

# 创建conda环境并安装donkey
RUN conda create -y -n donkey python=3.11 && \
    echo "source activate donkey" > ~/.bashrc && \
    /bin/bash -c "source activate donkey && \
    mkdir projects && \
    cd projects && \
    git clone https://github.com/autorope/donkeycar && \
    cd donkeycar && \
    git checkout main && \
    pip install -e .[pc]"

# 创建车辆
RUN /bin/bash -c "source activate donkey && donkey createcar --path ~/mycar"