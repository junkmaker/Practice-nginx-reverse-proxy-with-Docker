# nginxでリバースプロキシを構成する

## 使い方

1. コンテナを起動する

    ```sh
    docker-compose up -d
    ```

1. nginxにアクセスする

    <http://localhost:8888>にブラウザアクセス  
    アクセスできると"NGINX"が表示される

1. flaskアプリにアクセスする

    <http://localhost:8888/flask>にブラウザでアクセス  
    アクセスできると"Flask App"が表示される
    