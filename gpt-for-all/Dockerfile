FROM ubuntu:23.04

RUN apt update
RUN apt install -yy git

WORKDIR /
RUN git clone https://github.com/nomic-ai/gpt4all.git

WORKDIR /gpt4all/chat

CMD ./gpt4all-lora-quantized-linux-x86 -m model
