# Docker-JupyterLab

---

## コンテナの最新バージョンを確認

[Tags](https://hub.docker.com/r/jupyter/datascience-notebook/tags) から、
latest 相当のイメージのタグを確認する

## docker-compose.yml を作成

```yml
version: "3"

services:
  jupyter:
    image: jupyter/datascience-notebook:3b1f4f5e6cc1
    container_name: jupyterlab

    environment:
      JUPYTER_ENABLE_LAB: "yes"
      TZ: "Asia/Tokyo"

    command: start.sh jupyter lab
    ports:
      - "8888:8888"
    working_dir: /home/jovyan/work
    volumes:
      - .:/home/jovyan/work
```

## 起動

```sh
$ docker-compose up
```
