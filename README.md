# nginxでリバースプロキシを構成する

## 使い方

1. コンテナを起動する

    ```sh
    docker-compose up -d
    ```

1. nginxにアクセスする

    <http://localhost:4443>にブラウザアクセス  
    アクセスできると"NGINX"が表示される

1. flaskアプリにアクセスする

    <http://localhost:4443/flask>にブラウザでアクセス  
    アクセスできると"Flask App"が表示される

***

### 自己署名証明書によるHTTPS対応

1. 秘密鍵の作成

    ```sh
    sudo openssl genrsa -out server.key 2048
    ```

1. 証明書署名要求(CSR:Certificate Signing Request)の作成

    ```sh
    sudo openssl req -new -key server.key -out server.csr
    ```

1. サーバ証明書の作成

    ```sh
    sudo openssl x509 -days 3650 -req -signkey server.key -in server.csr -out server.crt
    ```

## 参考サイト

- [NginxでSSL接続をリバースプロキシする方法・設定](https://hirooooo-lab.com/development/nginx-ssl-reverse-proxy/)
- [NginxでSSL（HTTPS）設定！オレオレ（自己署名）証明書を作成しよう！](https://kitsune.blog/nginx-ssl)
- [nginx でリバースプロキシするときの Tips](https://onair.jp/archives/3883.html#toc6)
