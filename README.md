# jupyter-in-docker

Jupyter Notebook 環境を Docker 内で実現

## コマンド関連

- 初回起動

```bash
docker run -v `pwd`:/home/jovyan/work -p 10000:8888 --name jupyter jupyter/scipy-notebook
```

- 2 回目以降の起動

```bash
# コンテナ起動
$ docker start jupyter
  jupyter

# 状態を確認、STATUS: UPなら起動成功
$ docker ps

# もしトークンを確認された場合はコンテナに入ってログを出力する
$ docker exec -it jupyter bash
$ jupyter notebook list
  Currently running servers:
  http://localhost:8888/?token=<トークン>
```
