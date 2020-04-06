docker-compose settings for Ruby on Rails

・このリポジトリをcloneする

・rails newでRailsインストール
`docker-compose run web rails new . --force --no-deps --database=postgresql`

・dockerビルド
`docker-compose build`

・DBコネクション設定

```
default: &default
  adapter: postgresql
  encoding: unicode
  pool: <%= ENV.fetch("RAILS_MAX_THREADS") { 5 } %>
+  host: db
+  username: postgres
+  password: password
```

・DB作成
`docker-compose run web rake db:create`

・コンテナ起動
`docker-compose up -d`

・http://localhost:3000 でアクセスしたらホーム画面が表示される


