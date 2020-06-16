herokuにデプロイしているスターターアプリをDB連携アプリに改造しましょう

1. Terminalから、再度、herokuにログインしましょう。<br>
```shell
heroku login --interactive
```{{copy}}

2. herokuにデプロイしているgitをcloneします
```shell
git clone https://git.heroku.com/{herokuのアプリ名}.git
```{{copy}}
<font color="red">※{LIFF アプリ名}部分は控えているheroku アプリ名に、"{}"は除いて置き換えてください。</font><br>

3. githubからToDoリストアプリのファイルをCloneします<br>
```shell
git clone https://github.com/MasatakaMiki/ldgq.git
```{{copy}}

4. ファイルを上書きコピーします<br>
```shell
cp -f -r ./ldgq/202006_handson/todo-app/* ./{herokuのアプリ名}
```{{copy}}
<font color="red">※{LIFF アプリ名}部分は控えているheroku アプリ名に、"{}"は除いて置き換えてください。</font><br>




次のステップでは、データベースにテーブルを作っていきますよ！
