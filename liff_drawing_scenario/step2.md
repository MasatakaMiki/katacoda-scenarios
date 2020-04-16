前のステップで準備したアプリをherokuに展開する準備をしましょう

1. まずは、herokuにログインします
    ```shell
    heroku login --interactive
    ```{{copy}}

2. herokuでアプリを作成します。<br>
無料で5つまで作成でき、クレジットカード登録したら作成枠が増えます。
アプリの名前は一意になるようにしてください。英小文字、数字、-(ハイフン)のみ使用可能です。
    ```shell
    heroku create ldgq-20200417-name
    ```{{copy}}
作成されたらURLが出力されていると思います。
LIFFの作成時に必要となるので、控えておいてください。
    `https://ldgq-20200417-name.herokuapp.com`

3. 前のステップで準備したアプリ（リポジトリ）とherokuのアプリを紐づけます
    ```shell
    heroku git:remote -a ldgq-20200417-name
    ```{{copy}}

次のステップでは、LIFFを作っていきますよ！
