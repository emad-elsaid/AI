FROM ubuntu:23.04

RUN apt update
RUN apt install -yy git build-essential python3 pip pkg-config cmake
RUN pip3 install --break-system-packages torch numpy sentencepiece

RUN git clone --depth=1 https://github.com/ggerganov/llama.cpp
WORKDIR llama.cpp
RUN make


# convert model to ggml
RUN echo "#!/usr/bin/env bash\npython3 convert-pth-to-ggml.py /models/LLaMA/13B 1" > convert
RUN chmod +x convert

CMD ./main --interactive-first -m /models/LLaMA/13B/ggml-model-f16.bin -n 128
