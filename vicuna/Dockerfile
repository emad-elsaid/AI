FROM ubuntu:23.04

RUN apt update
RUN apt install -yy python3 pip git pkg-config cmake transmission-cli
RUN pip3 install --break-system-packages fschat
RUN pip3 install --break-system-packages git+https://github.com/huggingface/transformers

RUN mkdir /ai

# Convert the model to hugging face format
RUN echo "#!/usr/bin/env bash\npython3 `find . -iname convert_llama_weights_to_hf.py` --input_dir /model/LLaMA/ --model_size 13B --output_dir /model/LLaMA-hf" > /ai/convert
RUN chmod +x /ai/convert

# Merge fastchat changes
RUN echo "#!/usr/bin/env bash\npython3 -m fastchat.model.apply_delta --base /model/LLaMA-hf --target /model/vicuna-13b --delta lmsys/vicuna-13b-delta-v0" > /ai/merge-vicuna
RUN chmod +x /ai/merge-vicuna

# vicuna commands
RUN echo "#!/usr/bin/env bash\npython3 -m fastchat.serve.cli --model-name /model/vicuna-13b --device cpu" > /ai/vicuna-cpu
RUN chmod +x /ai/vicuna-cpu

RUN echo "#!/usr/bin/env bash\npython3 -m fastchat.serve.cli --model-name /model/vicuna-13b" > /ai/vicuna-gpu
RUN chmod +x /ai/vicuna-gpu


CMD /ai/vicuna-cpu
