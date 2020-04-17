LIFFの準備も整いました。herokuにアプリをデプロイ（展開）していきましょう。

1. herokuの環境変数にLIFF IDを設定します<br>
```shell
heroku config:set MY_LIFF_ID={liff id}
```{{copy}}
<font color="red">※{liff id}部分は前のステップで控えたLIFF URLのLIFF ID部分だけを使用します。"{}"は除いて置き換えてください。</font><br>
例）<br>
```shell
heroku config:set MY_LIFF_ID=1234567890-aBcdefGH
```
設定した環境変数は、以下のコマンドで確認できます<br>
```shell
heroku config
```{{copy}}

2. gitの初期設定を行います<br>
```shell
git config --global user.email you@example.com
```{{copy}}
<font color="red">※you@example.com部分はご自身のメールアドレスに置き換えてください。</font><br>
```shell
git config --global user.name your_name
```{{copy}}
<font color="red">※your_name部分はご自身の名前に置き換えてください。</font><br>

3. gitでherokuにデプロイします。gitのコマンドを3つ実行します。<br>
```shell
git add .
```{{copy}}
```shell
git commit -m "first commit"
```{{copy}}
```shell
git push heroku master
```{{copy}}

4. これでスターターアプリがデプロイされました。ブラウザでLIFF URLにアクセスしてみましょう。<br>
たくさんボタンがあるので、まずLog inして、色々クリックしてみてください。LIFFでできることが分かると思います。

5. では、スマホのLINEアプリからも動かしてみましょう<br>
長くなりそうなので次のステップで・・・
