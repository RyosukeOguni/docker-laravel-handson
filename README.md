# Docker × Laravel 最少構成環境設定

## １．機能構成
| FW | WEB SERVER | DB | DB MANAGER |
----|----|----|----
| Laravel | Nginx | MySQL | phpMyAdmin |


## ２．導入手順

下記Gitコマンドを入力してGit hubからダウンロード
```
$ git clone https://github.com/RyosukeOguni/docker-laravel-handson.git
```

ディレクトリに移動
```
$ cd docker-laravel-handson
```

dockerをビルド
```
$ docker compose up -d --build
```

appコンテナに入る
```
$ docker compose exec app bash
```

composerをインストール
```
$ composer install
```

.envファイルを作成
```
$ cp .env.example .env
```

.envファイルを変更（DB設定箇所）
```
DB_CONNECTION=mysql
DB_HOST=db
DB_PORT=3306
DB_DATABASE=laravel_local
DB_USERNAME=phper
DB_PASSWORD=secret
```

アプリケーションキーを生成
```
$ php artisan key:generate
```

マイグレーションを実行
```
$ php artisan migrate
```

動作を確認
▼Laravel
http://127.0.0.1:8080/
▼phpMyadmin
http://localhost:8081/index.php


## ３．作成者情報

-   作成者：小国 亮介

