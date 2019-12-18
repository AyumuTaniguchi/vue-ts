# vue-ts
### vue.js + typescript + Docker 環境構築手法

- Dockerfile

``` Dockerfile
FROM node:12.7.0-alpine

WORKDIR /app
```

- docker-compose.yml

```docker-compose.yml
version: '3'
services:
  app:
    build: .
    ports:
      - 8080:8080
    volumes:
      - .:/app
    stdin_open: true
    tty: true
```

- 上記 docker 関連ファイルを用意し下記コマンドを順に実行する。

```
$ docker-compose build

$ docker-compose run app sh

$ npm install -g @vue/cli

# 下記コマンドでプロジェクトを作成する
$ vue create .
```

