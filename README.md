# アプリケーション名

## Git リポジトリの準備手順(この手順はアプリ完成時には README から削除する)

-   リモートリポジトリの作成
    GitHub でリモートリポジトリを作成する(Add a README file のチェックは外す)  
    リポジトリ名は作るアプリケーションに合わせる  
    このリポジトリは下記説明で出てくる{上で作成したリモートリポジトリ}の事になる

-   カレントディレクトリを変更する
    現在いるディレクトリを作業ディレクトリに移動してから行う  
    ※こだわりが無ければ coachtech ディレクトリに移動してから下記コマンドを行う

-   クローンして名前変更する

```
git clone git@github.com:tamachima327/laravel-template.git
mv laravel-template {上で作成したリモートリポジトリ名}
```

-   リモートリポジトリの紐づけを変更する

```
$ cd {上で作成したリモートリポジトリ名}
$ git remote set-url origin {上で作成したリモートリポジトリのSSHアドレス(Codeからコピー)}
$ git remote -v
```

-   以下の環境構築手順で動くことを確認したら commit/push して環境構築完了
    コミットメッセージは"First commit"

## 環境構築手順

-   コンテナを立ち上げるため、以下を実行

```
docker compose up -d --build
```

-   env ファイルの作成をするため、以下を実行

```
cp src/.env.example .env
```

-   composer パッケージをインストールするため、以下を実行

```
composer install
```

-   アプリケーションキーを作成するため、以下を実行

```
php artisan key:generate
```

-   マイグレーションを実行するため、以下を実行

```
php artisan migrate
```

## 開発でやる必要があること(この手順はアプリ完成時には README から削除する)

-   view ファイルの作成・修正・削除
-   controller の作成・修正
-   model の作成・修正
-   css の作成・修正・削除(クラス名も直すこと)
-   migration ファイルの作成・修正
-   seeder の作成
-   README.md(このファイル)の修正
