前のステップで準備したアプリをherokuに展開しましょう

1. まずは、herokuにログインします。<br>
Terminalに戻って、以下のコマンドを実行します。<br>
```shell
heroku login --interactive
```{{copy}}

2. herokuでアプリを作成します。<br>
無料で5つまで作成でき、クレジットカード登録したら作成枠が増えます。
アプリの名前は一意になるようにしてください。英小文字、数字、-(ハイフン)のみ使用可能です。<br>
```shell
heroku create ldgq-20200617-name
```{{copy}}
作成されたらURLが出力されていると思います。
LIFFの作成時に必要となるので、アプリ名とURLを控えておいてください。<br>
`https://ldgq-20200617-name.herokuapp.com`

3. 前のステップで準備したアプリ（リポジトリ）とherokuのアプリを紐づけます<br>
```shell
heroku git:remote -a ldgq-20200617-name
```{{copy}}

次のステップでは、LIFFを作っていきますよ！
