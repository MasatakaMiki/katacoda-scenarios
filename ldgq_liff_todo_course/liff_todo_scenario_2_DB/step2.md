構築したデータベースにテーブルを作成します

1. ターミナルに戻り、herokuの環境変数にデータベース情報を設定します<br>
```shell
heroku config:set PG_HOST={PG Host} PG_NAME={PG Database} PG_USER={PG User} PG_PORT={PG Port} PG_PWD={PG Password} -a {app name}
```{{copy}}
<font color="red">※{PG Host}、{PG Database}、{PG User}、{PG Port}、{PG Password}部分は前のステップで控えたデータベース情報を使用します。"{}"は除いて置き換えてください。<br>
また、{app name}はherokuのアプリ名に"{}"は除いて置き換えてください。</font><br>


<b>①サーバーのアドレス（Host）</b>
```shell
heroku config:set PG_HOST={PG Host}
```{{copy}}
<font color="red">※{PG Host}部分は前のステップで控えたPG Hostを使用します。"{}"は除いて置き換えてください。</font><br>
例）<br>
```shell
heroku config:set PG_HOST=ec2-9-99-999-99.compute-1.amazonaws.com
```
<br>
<b>②データベースの名前（Database）</b>
```shell
heroku config:set PG_NAME={PG Database}
```{{copy}}
<font color="red">※{PG Database}部分は前のステップで控えたPG Databaseを使用します。"{}"は除いて置き換えてください。</font><br>
例）<br>
```shell
heroku config:set PG_NAME=x9xxxxx9xxx999
```
<br>
<b>③ユーザー名（User）</b>
```shell
heroku config:set PG_USER={PG User}
```{{copy}}
<font color="red">※{PG User}部分は前のステップで控えたPG Userを使用します。"{}"は除いて置き換えてください。</font><br>
例）<br>
```shell
heroku config:set PG_USER=xxxxxxxxxxxxxx
```
<br>
<b>④ポート（Port）</b>
```shell
heroku config:set PG_PORT={PG Port}
```{{copy}}
<font color="red">※{PG Port}部分は前のステップで控えたPG Portを使用します。"{}"は除いて置き換えてください。</font><br>
例）<br>
```shell
heroku config:set PG_PORT=5432
```
<br>
<b>⑤パスワード（Password）</b>
```shell
heroku config:set PG_PWD={PG Password}
```{{copy}}
<font color="red">※{PG Password}部分は前のステップで控えたPG Hostを使用します。"{}"は除いて置き換えてください。</font><br>
例）<br>
```shell
heroku config:set PG_PWD=0x00x00x9999999x0x0xx00000x9x999999999xx9x9xx00000x9x00x0x0x99x0
```
<br>

2.設定した環境変数を以下のコマンドで確認します<br>
```shell
heroku config
```{{copy}}

3.ターミナルからデータベースに接続します<br>
```shell
heroku pg:psql
```{{copy}}

4.タイムゾーンの変更をします<br>
①現在の時刻を確認<br>
```shell
select CURRENT_TIMESTAMP;
```{{copy}}
②タイムゾーンを変更<br>
```shell
alter database {PG Database} set timezone = 'Asia/Tokyo';
```{{copy}}
<font color="red">※{PG Database}部分は前のステップで控えたPG Databaseを使用します。"{}"は除いて置き換えてください。</font><br>

5.接続をし直し、タームゾーンの変更を確認します<br>
①一旦接続<br>
```shell
\q
```{{copy}}
②再度接続<br>
```shell
heroku pg:psql
```{{copy}}
③現在の時刻を確認<br>
```shell
select CURRENT_TIMESTAMP;
```{{copy}}


7. リッチメニューのタイトルを入力します<br>
<table><tr><th>項目</th><th>値</th></tr>
<tr><td>①タイトル</td><td>LIFF MENU</td></tr>
<tr><td>②表示期間</td><td>2020/06/17 00:00 - 2029/12/31 23:59</td></tr>
</table>
![richmenu_setting](https://raw.githubusercontent.com/MasatakaMiki/katacoda-scenarios/master/ldgq_liff_todo_course/liff_todo_scenario_1_LINE/img/s0208_richmenu_setting.jpg)

8. `テンプレートを選択`をクリックし、左下のテンプレートを選択して、選択ボタンをクリックします<br>
![richmenu_setting](https://raw.githubusercontent.com/MasatakaMiki/katacoda-scenarios/master/ldgq_liff_todo_course/liff_todo_scenario_1_LINE/img/s0209_richmenu_setting.jpg)
![richmenu_setting](https://raw.githubusercontent.com/MasatakaMiki/katacoda-scenarios/master/ldgq_liff_todo_course/liff_todo_scenario_1_LINE/img/s0210_richmenu_setting.jpg)

9. アクションを設定します<br>
<table><tr><th>項目</th><th>値</th></tr>
<tr><td>①タイプ</td><td>リンク</td></tr>
<tr><td>②URL</td><td>控えているLIFF URL</td></tr>
<tr><td>③アクションラベル</td><td>LIFFを開く</td></tr>
</table>
![richmenu_setting](https://raw.githubusercontent.com/MasatakaMiki/katacoda-scenarios/master/ldgq_liff_todo_course/liff_todo_scenario_1_LINE/img/s0211_richmenu_setting.jpg)

10. `画像を作成`をクリックし、リッチメニューのテキストや背景色を設定します。出来たら、適用ボタンをクリックします。<br>
![richmenu_setting](https://raw.githubusercontent.com/MasatakaMiki/katacoda-scenarios/master/ldgq_liff_todo_course/liff_todo_scenario_1_LINE/img/s0212_richmenu_setting.jpg)
![richmenu_setting](https://raw.githubusercontent.com/MasatakaMiki/katacoda-scenarios/master/ldgq_liff_todo_course/liff_todo_scenario_1_LINE/img/s0213_richmenu_setting.jpg)
![richmenu_setting](https://raw.githubusercontent.com/MasatakaMiki/katacoda-scenarios/master/ldgq_liff_todo_course/liff_todo_scenario_1_LINE/img/s0214_richmenu_setting.jpg)

11. 最後に、保存ボタンをクリックしたら、リッチメニューの完成です<br>
![richmenu_setting](https://raw.githubusercontent.com/MasatakaMiki/katacoda-scenarios/master/ldgq_liff_todo_course/liff_todo_scenario_1_LINE/img/s0215_richmenu_setting.jpg)

12. ボットの応答をオフに設定します。`設定`をクリック、`応答設定`をクリックし、`応答メッセージ`を`オフ`にします。<br>
![bot_setting](https://raw.githubusercontent.com/MasatakaMiki/katacoda-scenarios/master/ldgq_liff_todo_course/liff_todo_scenario_1_LINE/img/s0216_bot_setting.jpg)

13. チャネルシークレット、ユーザーIDを控えます。<br>
<a href="https://developers.line.biz/console/" target="_blank">LINE Developers</a>のページに戻り、`チャネル基本設定`をクリックします。下にスクロールして`チャネルシークレット`と`あなたのユーザーID`をメモします。<br>
![channel_secret](https://raw.githubusercontent.com/MasatakaMiki/katacoda-scenarios/master/ldgq_liff_todo_course/liff_todo_scenario_1_LINE/img/s0217_channel_secret.jpg)
![channel_secret](https://raw.githubusercontent.com/MasatakaMiki/katacoda-scenarios/master/ldgq_liff_todo_course/liff_todo_scenario_1_LINE/img/s0218_channel_secret.jpg)

14. チャネルアクセストークンを発行し、控えます。<br>
`Messaging API設定`をクリックします。下にスクロールして`チャネルアクセストークン`を発行し、メモします。<br>
![access_token](https://raw.githubusercontent.com/MasatakaMiki/katacoda-scenarios/master/ldgq_liff_todo_course/liff_todo_scenario_1_LINE/img/s0219_access_token.jpg)
![access_token](https://raw.githubusercontent.com/MasatakaMiki/katacoda-scenarios/master/ldgq_liff_todo_course/liff_todo_scenario_1_LINE/img/s0220_access_token.jpg)
<br>
↓発行後
<br>
![access_token](https://raw.githubusercontent.com/MasatakaMiki/katacoda-scenarios/master/ldgq_liff_todo_course/liff_todo_scenario_1_LINE/img/s0221_access_token.jpg)

15. 作ったボットと友達になりましょう。<br>
<a href="https://developers.line.biz/console/" target="_blank">LINE Developers</a>のページに戻り、`Messaging API設定`をクリックします。そこに表示されているQRコードをLINEのアプリから読み取って友達になります。<br>
![be_friend](https://raw.githubusercontent.com/MasatakaMiki/katacoda-scenarios/master/ldgq_liff_todo_course/liff_todo_scenario_1_LINE/img/s0222_be_friend.jpg)

これでトークルームのリッチメニューからLIFFが起動する準備ができました。<br>
（エンドポイントが仮のURLなので、起動はしません）
