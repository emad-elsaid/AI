# GPT 4 allow

repo: https://github.com/nomic-ai/gpt4all

## Download the model

```
wget https://the-eye.eu/public/AI/models/nomic-ai/gpt4all/gpt4all-lora-quantized.bin
```


## build the image

```
docker build . -t gpt4all
```

## run it

```
docker run -it -v /home/emad/AI/gpt4all/gpt4all-lora-quantized.bin:/gpt4all/chat/model gpt4all
```
