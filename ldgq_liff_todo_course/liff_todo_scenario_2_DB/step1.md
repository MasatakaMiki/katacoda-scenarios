herokuでアプリを作成し、データベースを構築しましょう

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
`https://ldgq-20200617-name.herokuapp.com`<br>

3. ブラウザで herokuの管理画面へ、ログインし、作成したアプリをクリックします。<br>
<a href="https://dashboard.heroku.com/" target="_blank">https://dashboard.heroku.com/</a>
![heroku_app](https://raw.githubusercontent.com/MasatakaMiki/katacoda-scenarios/master/ldgq_liff_todo_course/liff_todo_scenario_2_DB/img/s0101_heroku_app.jpg)

4. `Resources`をクリックし、`Add-ons`の入力欄に`Postgres`と入力します。選択肢の候補に、`Heroku Postgres`がありますので、クリックします。<br>
![create_db](https://raw.githubusercontent.com/MasatakaMiki/katacoda-scenarios/master/ldgq_liff_todo_course/liff_todo_scenario_2_DB/img/s0102_create_db.jpg)

5. `Plan name`に、<font color="red">必ず`Hobby Dev - Free`を選択し、</font>`Provision`ボタンをクリックします。<br>
![create_db](https://raw.githubusercontent.com/MasatakaMiki/katacoda-scenarios/master/ldgq_liff_todo_course/liff_todo_scenario_2_DB/img/s0103_create_db.jpg)

6. 準備された、`Heroku Postgres`をクリックします。<br>
![create_db](https://raw.githubusercontent.com/MasatakaMiki/katacoda-scenarios/master/ldgq_liff_todo_course/liff_todo_scenario_2_DB/img/s0104_create_db.jpg)

7. データベースの管理画面が開きますので、`Setings`をクリックし、`View Credentials...`ボタンをクリックします。<br>
![create_db](https://raw.githubusercontent.com/MasatakaMiki/katacoda-scenarios/master/ldgq_liff_todo_course/liff_todo_scenario_2_DB/img/s0105_create_db.jpg)

8. Host、Database、User、Port、Passwordをメモしておきます。<br>
![create_db](https://raw.githubusercontent.com/MasatakaMiki/katacoda-scenarios/master/ldgq_liff_todo_course/liff_todo_scenario_2_DB/img/s0106_create_db.jpg)

次のステップでは、データベースにテーブルを作っていきますよ！
