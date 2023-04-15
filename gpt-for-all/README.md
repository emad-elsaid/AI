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

make sure to replace the path `/home/emad/AI/...` with the path to the model file (not the directory, the file itself)

```
docker run -it -v /home/emad/AI/gpt4all/gpt4all-lora-quantized.bin:/model gpt4all
```
