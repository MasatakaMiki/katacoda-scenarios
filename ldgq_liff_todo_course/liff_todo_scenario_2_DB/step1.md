heroku上でデータベースを構築しましょう

1. ブラウザで herokuの管理画面へ、ログインし、作成したアプリをクリックします。<br>
<a href="https://dashboard.heroku.com/" target="_blank">https://dashboard.heroku.com/</a>
![heroku_app](https://raw.githubusercontent.com/MasatakaMiki/katacoda-scenarios/master/ldgq_liff_todo_course/liff_todo_scenario_2_DB/img/s0101_heroku_app.jpg)

2. `Resources`をクリックし、`Add-ons`の入力欄に`Postgres`と入力します。選択肢の候補に、`Heroku Postgres`がありますので、クリックします。<br>
![create_db](https://raw.githubusercontent.com/MasatakaMiki/katacoda-scenarios/master/ldgq_liff_todo_course/liff_todo_scenario_2_DB/img/s0102_create_db.jpg)

3. `Plan name`に、<font color="red">必ず`Hobby Dev - Free`を選択し、</font>`Provision`ボタンをクリックします。<br>
![create_db](https://raw.githubusercontent.com/MasatakaMiki/katacoda-scenarios/master/ldgq_liff_todo_course/liff_todo_scenario_2_DB/img/s0103_create_db.jpg)

4. 準備された、`Heroku Postgres`をクリックします。<br>
![create_db](https://raw.githubusercontent.com/MasatakaMiki/katacoda-scenarios/master/ldgq_liff_todo_course/liff_todo_scenario_2_DB/img/s0104_create_db.jpg)

5. データベースの管理画面が開きますので、`Settings`をクリックし、`View Credentials...`ボタンをクリックします。<br>
![create_db](https://raw.githubusercontent.com/MasatakaMiki/katacoda-scenarios/master/ldgq_liff_todo_course/liff_todo_scenario_2_DB/img/s0105_create_db.jpg)

6. Host、Database、User、Port、Passwordをメモしておきます。<br>
![create_db](https://raw.githubusercontent.com/MasatakaMiki/katacoda-scenarios/master/ldgq_liff_todo_course/liff_todo_scenario_2_DB/img/s0106_create_db.jpg)

次のステップでは、データベースにテーブルを作っていきますよ！
