# image llm tests

## Prerequisites
- docker

## Infra
- gcloud artifact registry: https://console.cloud.google.com/artifacts/docker/image-llm-408613/europe-west3/llms?hl=de&project=image-llm-408613
  
  check [auth docs](https://cloud.google.com/artifact-registry/docs/docker/authentication?hl=de) for docker authentication


## LLMs
### Open Clip

https://github.com/mlfoundations/open_clip

    docker compose -f docker-compose.open-clip.yaml up

Click URL in log-output to open Jupyter notebook

![open clip](./docs/open_clip.png "Open Clip Jupyter Notebook")

Unfortunately this model is not useful for our case, since the output is limited to a small amount of 
descriptive words.


### Qwen-VL

https://github.com/QwenLM/Qwen-VL

to build and run locally:

    cd qwen-vl
    ./clone-qwen-vl-repo.sh
    cd ..
    docker compose -f docker-compose.qwen-vl-chat.yaml up

or run:

    docker run --gpus all -p 8080:8080 europe-west3-docker.pkg.dev/image-llm-408613/llms/qwen-vl-chat:1.0
