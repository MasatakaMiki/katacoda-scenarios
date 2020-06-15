herokuでアプリを作成しましょう

1. まずは、herokuにログインします。<br>
Terminalで、以下のコマンドを実行します。<br>
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
LIFFのエンドポイント設定に必要となるので、控えておいてください。<br>
`https://ldgq-20200617-name.herokuapp.com`

3. ブラウザで herokuの管理画面へ、ログインし、作成したアプリをクリックします。<br>
<a href="https://dashboard.heroku.com/" target="_blank">https://dashboard.heroku.com/</a>

3. herokuの管理画面<br>
```shell
heroku git:remote -a ldgq-20200417-name
```{{copy}}

次のステップでは、LIFFを作っていきますよ！
