FROM pytorch/pytorch:1.12.1-cuda11.3-cudnn8-devel

RUN apt-get update && apt-get install -y git
# RUN yum makecache && yum install -y git

RUN pip config set global.index-url https://mirrors.bfsu.edu.cn/pypi/web/simple

COPY requirements.txt /root/requirements.txt

RUN pip install -r /root/requirements.txt

ADD models /root/models