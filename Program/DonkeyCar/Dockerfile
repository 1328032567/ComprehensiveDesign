FROM ubuntu:22.04
RUN apt-get update \
    && apt-get install -y wget \
    && rm -rf /var/lib/apt/lists/* 
RUN wget https://repo.anaconda.com/miniconda/Miniconda3-py39_23.3.1-0-Linux-x86_64.sh \
    && bash ./Miniconda3-py39_23.3.1-0-Linux-x86_64.sh 
RUN conda create -n donkey python=3.11 \
    && conda activate donkey \
    && mkdir projects \
    && cd projects \
    && git clone https://github.com/autorope/donkeycar \
    && cd donkeycar \
    && git checkout main \
    && pip install -e .[pc]
RUN donkey createcar --path ~/mycar

CMD conda activate donkey


EXPOSE 8888