# [LLaMA.CPP](https://github.com/ggerganov/llama.cpp)

## Build the image

```
docker build . -t llama.cpp
```

## Download LLaMA model

* the command assumes it's in `/home/emad/AI` and the LLaMA folder is called `LLaMA`

```
docker run -it -v /home/emad/AI:/models llama.cpp ./convert
```

## Run it

```
docker run -it -v  /home/emad/AI:/models llama.cpp
```
