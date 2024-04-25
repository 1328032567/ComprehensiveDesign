# HostPc Environment

*为什么使用docker*

(1)**便于环境配置**：使用Docker可以将项目的开发环境打包成一个容器，确保每位开发人员都在相同的环境中工作，避免因为环境配置不一致导致的问题。

(2)**提高开发效率**：Docker容器可以快速部署和启动，节省了开发人员的时间，提高了开发效率。

(3)**简化部署**：将项目打包成Docker容器后，可以轻松地部署到其他设备或服务器上，避免了部署过程中的各种依赖和配置问题。

(4)**增强安全性**：Docker容器之间相互隔离，可以确保项目的安全性，避免恶意代码对系统的影响。

(5)**方便团队协作**：多人参与的项目中，使用Docker可以统一开发环境，便于团队成员之间的协作和交流。





*dockerfile的编写*

​	Docker是一种容器化平台，可以将应用程序及其依赖项打包成一个独立的可移植容器。Dockerfile是用于定义Docker镜像的文本文件，其中包含了构建镜像所需的指令和配置。为了构建镜像需要编写dockerfile，为了编写dockerfile，需要知道donkeycar所需环境的配置过程。

​	根据donkeycar官方文档，donkeycar开发是基于ubuntu22.04版本的linux系统。所以需要使用ubuntu 22.04作为基础镜像：

~~~dockerfile
FROM ubuntu:22.04
~~~

​	之后需要设置工作目录，即：

~~~dockerfile
WORKDIR /tmp
~~~

​	且为了开发donkeycar，系统需要git、miniconda应用。

~~~dockerfile
RUN apt-get update && apt-get install -y wget git

# 下载并安装Miniconda
RUN wget https://repo.anaconda.com/miniconda/Miniconda3-py39_23.3.1-0-Linux-x86_64.sh && \
    bash Miniconda3-py39_23.3.1-0-Linux-x86_64.sh -b -p /miniconda && \
    rm Miniconda3-py39_23.3.1-0-Linux-x86_64.sh
~~~



在安装以上应用后，需要更新相应的环境变量。因此要有以下操作：

~~~dockerfile
ENV PATH="/miniconda/bin:${PATH}"
~~~

之后再在github上拉取donkeycar项目，安装donkey，创建车辆项目。

~~~dockerfile
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
~~~



​	







