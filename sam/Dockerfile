FROM pytorch/pytorch:1.12.1-cuda11.3-cudnn8-devel

RUN apt-get update && apt-get install -y git
# RUN yum makecache && yum install -y git

RUN pip config set global.index-url https://mirrors.bfsu.edu.cn/pypi/web/simple

RUN pip install git+https://github.com/facebookresearch/segment-anything.git && \
    pip install some-package opencv-python pycocotools matplotlib onnxruntime onnx

ADD checkpoint /root/checkpoint