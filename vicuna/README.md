# [Vicuna](https://github.com/lm-sys/FastChat)

## Prerequisite

* at least 268.1 GiB disk storage for the models
* 60GB of RAM

## Build docker image

```
docker build . -t vicuna
```

## Download LLaMA weights (235.2GB)

all commands will assume the LLaMA models are downloaded from the torrent to
this path `/home/emad/AI` in a folder called `LLaMA`. replace the path with your
actual path.


Note: This needs to be revised. it stops without downloading.
```
docker run -it --network host -p 51413 -p 51413/udp -v /home/emad/AI:/model vicuna /ai/download-llama
```

## Convert LLaMA to HuggingFace format

```
docker run -it -v /home/emad/AI:/model vicuna /ai/convert
```

## Merge Vicuna delta

```
docker run -it -v /home/emad/AI:/model vicuna /ai/merge-vicuna
```

## Run vicuna on CPU

```
docker run -it -v /home/emad/AI:/model vicuna /ai/vicuna-cpu
```
