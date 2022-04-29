# DjangoのDocker環境練習リポジトリ

- Python3
- Django3.2 LTS
- PostgreSQL
- Docker/DockerCompose

# 注意

- Windows(WSL2)の場合
    - Ubuntuのフォルダのhome/user名/にいること
    - ¥¥wsl$とフォルダ検索
- Git
    - Ubuntu用のGitを入れる
    - Gitパスワードではなく個人アクセストークンを使うかもしれない

# 操作手順

```bash
# Ubuntuを開きgit cloneする
git clone https://github.com/YukiYucha/Django.git
# ディレクトリを変更
cd Django
```

```docker
# ビルド
docker-compose build
# コンテナ起動
docker-compose up -d
```

[http://localhost:8000](http://localhost:8000) でDjangoのWelcomeページ

```docker
# コンテナ停止
docker-compose down または、
docker-compose stop
# Postgresのコンテナに入る
docker-compose exec db bash
psql -U postgres
# データベースを見る
\l

# docker環境を見る
docker ps
docker image ls
docker volume ls
dockre network ls
# docker環境を綺麗にする
docker rm コンテナID
docker image rm イメージID
docker volume rm ボリュームID
docker network rm ネットワーク名
```

## ミスったこと

- data/*はGitで管理しない(多分)ので、.gitignoreに設定
- dataディレクトリの権限(ls -lで見れる)がrootから変更してはいけなかった。

## 参考リンク

[環境構築参考サイト](https://docs.docker.com/samples/django/)

[PostgreSQLのコンテナに入る](https://code-examples.net/ja/q/23f2e0b)

[MySQLとPostgreSQLコマンドの違い](https://qiita.com/aosho235/items/c657e2fcd15fa0647471)

[Django命名規則で嵌まったエラー](https://automationpanda.com/2018/02/06/starting-a-django-project-in-an-existing-directory/)

[WSL2が遅くなる理由](https://www.aska-ltd.jp/jp/blog/197)
