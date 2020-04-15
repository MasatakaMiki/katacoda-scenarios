LIFFの準備も整いました。それでは、herokuにアプリをデプロイ（展開）していきましょう

1. herokuの環境変数にLIFF IDを設定します
    ```shell
    heroku config:set MY_LIFF_ID={liff id}
    ```{{copy}}
    <font color="red">※{liff id}部分は前のステップで控えたLIFF URLのLIFF ID部分だけを使用します。"{}"は除いて置き換えてください。</font>
    例）
    ```shell
    heroku config:set MY_LIFF_ID=1234567890-aBcdefGH
    ```
    設定した環境変数は、以下のコマンドで確認できます
    ```shell
    heroku config
    ```{{copy}}

2. gitでherokuにデプロイします。gitのコマンドを3つ実行します。
    ```shell
    git add .
    ```{{copy}}
    ```shell
    git commit -m "first commit"
    ```{{copy}}
    ```shell
    git push heroku master
    ```{{copy}}

3. LIFF URLにアクセスしてみましょう

これでスターターアプリがデプロイされました。たくさんボタンがあるので、まずLog inして、色々クリックしてみてください。LIFFでできることが分かると思います。
次のステップからは、このアプリをお絵描きアプリに改造してみましょう。
