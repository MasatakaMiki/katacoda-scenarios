構築したデータベースにテーブルを作成します

1. それでは、データベースに接続し、テーブルを作成していきます。下の表にある通り、色々なツールがありますが、今回は、<a href="https://pgweb-demo.herokuapp.com/" target="_blank">pgweb</a>を使ってみたいと思います。<br>
<table><tr><th>ツール名</th><th>特徴</th></tr>
<tr><td><a href="https://www.postgresql.jp/document/9.3/html/app-psql.html" target="_blank">psql</a></td><td>CUI</td></tr>
<tr><td><a href="https://www.pgadmin.org/" target="_blank">pgAdmin</a></td><td>OSS</td></tr>
<tr><td><a href="https://a5m2.mmatsubara.com/" target="_blank">A5:SQL Mk-2</a></td><td>Windows Only</td></tr>
<tr><td><a href="https://a5m2.mmatsubara.com/" target="_blank">HeidiSQL</a></td><td>OSS。MySQL用だがSQL Serverにも対応</td></tr>
<tr><td><a href="https://eggerapps.at/postico/" target="_blank">Postico</a></td><td>Mac Only</td></tr>
</table>

2. <a href="https://pgweb-demo.herokuapp.com/" target="_blank">pgweb</a>を開いたら、Host、Port、Username(User)、Password、Databaseを入力し、`Connect`ボタンをクリックします<br>

3. 以下、`Query`タブに、SQLを入力して、`Run Query`ボタンでSQLを実行して、テーブルなどを作成していきます。
![pgweb](https://raw.githubusercontent.com/MasatakaMiki/katacoda-scenarios/master/ldgq_liff_todo_course/liff_todo_scenario_2_DB/img/s0201_pgweb.jpg)

4. タイムゾーンの変更をします<br>
①現在の時刻を確認<br>
```shell
select CURRENT_TIMESTAMP;
```{{copy}}
②タイムゾーンを変更<br>
```shell
alter database {PG Database} set timezone = 'Asia/Tokyo';
```{{copy}}
<font color="red">※{PG Database}部分は前のステップで控えたPG Databaseを使用します。"{}"は除いて置き換えてください。</font><br>
③ 右上の`Disconnect`ボタンで一旦切断し、再接続します<br>
④現在の時刻を確認<br>
```shell
select CURRENT_TIMESTAMP;
```{{copy}}

5. テーブルを作成します<br>
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

6. レコードを追加してみましょう<br>
```shell
insert into todolist
(userid, task, status, created, updated) values
('{ユーザーID}', 'やること', 0, current_timestamp, current_timestamp);
```{{copy}}
<font color="red">※{ユーザーID}部分は最初のシナリオで控えたLINEのユーザーIDに、"{}"は除いて置き換えてください。</font><br>

これで、データベースの準備もできました。次のシナリオでは、スターターアプリをデータベースと連携するアプリに改造してみましょう。<br>
