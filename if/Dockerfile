FROM pytorch/pytorch:1.12.1-cuda11.3-cudnn8-devel

RUN apt-get update && apt-get install -y git

RUN pip config set global.index-url https://mirrors.bfsu.edu.cn/pypi/web/simple

RUN pip install deepfloyd_if==1.0.2rc0 && \
    pip install xformers==0.0.16 && \
    pip install git+https://github.com/openai/CLIP.git --no-deps

ENV FORCE_MEM_EFFICIENT_ATTN 1

ADD .cache/IF_ /root/.cache/IF_
ADD .cache/clip /root/.cache/clip 