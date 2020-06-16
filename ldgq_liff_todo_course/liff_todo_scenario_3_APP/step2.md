構築したデータベースにテーブルを作成します

cd {herokuのアプリ名}
```{{copy}}
<font color="red">※{LIFF アプリ名}部分は控えているheroku アプリ名に、"{}"は除いて置き換えてください。</font><br>

3. herokuの環境変数にデータベース情報を設定します<br>
```shell
heroku config:set PG_HOST={PG Host} PG_NAME={PG Database} PG_USER={PG User} PG_PORT={PG Port} PG_PWD={PG Password}
```{{copy}}
<font color="red">※{PG Host}、{PG Database}、{PG User}、{PG Port}、{PG Password}部分は前のステップで控えたデータベース情報を使用します。"{}"は除いて置き換えてください。</font><br>
例）<br>
```shell
heroku config:set PG_HOST=ec2-9-99-999-99.compute-1.amazonaws.com PG_NAME=x9xxxxx9xxx999 PG_USER=xxxxxxxxxxxxxx PG_PORT=5432 PG_PWD=0x00x00x9999999x0x0xx00000x9x999999999xx9x9xx00000x9x00x0x0x99x0
```
設定した環境変数は、以下のコマンドで確認できましたね。ここはよく間違うポイントなので、慎重によくチェックしてください！<br>
```shell
heroku config
```{{copy}}

4. それでは、データベースに接続し、テーブルを作成していきます。下の表にある通り、色々なツールがありますが、今回は、<a href="https://pgweb-demo.herokuapp.com/" target="_blank">pgweb</a>を使ってみたいと思います。<br>
<table><tr><th>ツール名</th><th>特徴</th></tr>
<tr><td><a href="https://www.postgresql.jp/document/9.3/html/app-psql.html" target="_blank">psql</a></td><td>CUI</td></tr>
<tr><td><a href="https://www.pgadmin.org/" target="_blank">pgAdmin</a></td><td>OSS</td></tr>
<tr><td><a href="https://a5m2.mmatsubara.com/" target="_blank">A5:SQL Mk-2</a></td><td>Windows用フリーソフト</td></tr>
<tr><td><a href="https://a5m2.mmatsubara.com/" target="_blank">HeidiSQL</a></td><td>OSS。MySQL用だがSQL Serverにも対応</td></tr>
<tr><td><a href="https://eggerapps.at/postico/" target="_blank">Postico</a></td><td>for Mac</td></tr>
</table>

5. <a href="https://pgweb-demo.herokuapp.com/" target="_blank">pgweb</a>を開いたら、Host、Port、Username(User)、Password、Databaseを入力し、`Connect`ボタンをクリックします<br>

6. 以下、`Query`タブに、SQLを入力して、`Run Query`ボタンでSQLを実行して、テーブルなどを作成していきます。
![pgweb](https://raw.githubusercontent.com/MasatakaMiki/katacoda-scenarios/master/ldgq_liff_todo_course/liff_todo_scenario_2_DB/img/s0201_pgweb.jpg)

7. タイムゾーンの変更をします<br>
①現在の時刻を確認<br>
```shell
select CURRENT_TIMESTAMP;
```{{copy}}
②タイムゾーンを変更<br>
```shell
alter database {PG Database} set timezone = 'Asia/Tokyo';
```{{copy}}
<font color="red">※{PG Database}部分は前のステップで控えたPG Databaseを使用します。"{}"は除いて置き換えてください。</font><br>
③ 右上の`Disconnect`ボタンで一旦切断し、再接続します
④現在の時刻を確認<br>
```shell
select CURRENT_TIMESTAMP;
```{{copy}}

8. テーブルを作成します<br>
```shell
create table todolist (
id serial not null,
userid varchar(64) not null,
task varchar(256) not null,
status int default 0 not null,
created timestamp default CURRENT_TIMESTAMP not null,
updated timestamp default CURRENT_TIMESTAMP not null,
primary key (id)
);
```{{copy}}

9. レコードを追加してみましょう<br>
```shell
insert into todolist
(userid, task, status, created, updated) values
('{ユーザーID}', 'やること', 0, current_timestamp, current_timestamp);
```{{copy}}
<font color="red">※{ユーザーID}部分は最初のシナリオで控えたLINEのユーザーIDに、"{}"は除いて置き換えてください。</font><br>

これで、データベースの準備もできました。次のシナリオでは、スターターアプリをデータベースと連携するアプリに改造してみましょう。<br>
