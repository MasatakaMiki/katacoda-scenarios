続いてLINEボットを作成し、メニューからLIFFを呼び出せるようにします

1. <a href="https://developers.line.biz/console/" target="_blank">LINE Developers</a>のページから`新規チャネル作成`をクリックします<br>
![create_channel](https://raw.githubusercontent.com/MasatakaMiki/katacoda-scenarios/master/ldgq_liff_todo_course/liff_todo_scenario_1_LINE/img/s0501_create_channel.jpg)

2. 今度は、`Messaging API`を選択します<br>
![create_channel](https://raw.githubusercontent.com/MasatakaMiki/katacoda-scenarios/master/ldgq_liff_todo_course/liff_todo_scenario_1_LINE/img/s0502_create_channel.jpg)

3. 各項目を埋めていきます<br>
<table><tr><th>項目</th><th>値</th></tr>
<tr><td>⓪チャネルアイコン</td><td>任意です。<br><img src="https://p62.f2.n0.cdn.getcloudapp.com/items/NQugZ40Q/todo.png?v=345132b267befc85123043a5ebbfdff8" style="height:50%;width:50%;border: 1px solid #0000ff;" alt="右クリックで保存して使ってください" /></td></tr>
<tr><td>①チャネル名</td><td>LDGQ ToDoリスト HOME</td></tr>
<tr><td>②チャネル説明</td><td>LDGQ LIFFアプリをメニュー起動するアプリです</td></tr>
<tr><td>③大業種</td><td>個人</td></tr>
<tr><td>④小業種</td><td>個人（その他）</td></tr>
<tr><td>⑤メールアドレス</td><td>ご自身のメールアドレスを入力</td></tr>
<tr><td>⑥同意</td><td>チェックを2つ入れる</td></tr>
</table>
![channel_setting](https://raw.githubusercontent.com/MasatakaMiki/katacoda-scenarios/master/ldgq_liff_todo_course/liff_todo_scenario_1_LINE/img/s0503_channel_setting.jpg)
![channel_setting](https://raw.githubusercontent.com/MasatakaMiki/katacoda-scenarios/master/ldgq_liff_todo_course/liff_todo_scenario_1_LINE/img/s0504_channel_setting.jpg)

4. 作成ボタンをクリックします。「情報利用に関する同意について」が表示されるので、`同意する`をクリックします。<br>
![channel_agreement](https://raw.githubusercontent.com/MasatakaMiki/katacoda-scenarios/master/ldgq_liff_todo_course/liff_todo_scenario_1_LINE/img/s0505_channel_agreement.jpg)

5. リッチメニューを作ります。リッチメニューは、`LINE Official Account Manager` で作成しますので、リンクをクリックします。<br>
![oam](https://raw.githubusercontent.com/MasatakaMiki/katacoda-scenarios/master/ldgq_liff_todo_course/liff_todo_scenario_1_LINE/img/s0506_oam.jpg)

6. `ホーム` - `リッチメニュー`をクリックし、作成ボタンをクリックします<br>
![create_richmenu](https://raw.githubusercontent.com/MasatakaMiki/katacoda-scenarios/master/ldgq_liff_todo_course/liff_todo_scenario_1_LINE/img/s0507_create_richmenu.jpg)

7. リッチメニューのタイトルを入力します<br>
<table><tr><th>項目</th><th>値</th></tr>
<tr><td>①タイトル</td><td>LIFF MENU</td></tr>
<tr><td>②表示期間</td><td>2020/06/17 00:00 - 2029/12/31 23:59</td></tr>
</table>
![richmenu_setting](https://raw.githubusercontent.com/MasatakaMiki/katacoda-scenarios/master/ldgq_liff_todo_course/liff_todo_scenario_1_LINE/img/s0508_richmenu_setting.jpg)

8. `テンプレートを選択`をクリックし、左下のテンプレートを選択して、選択ボタンをクリックします<br>
![richmenu_setting](https://raw.githubusercontent.com/MasatakaMiki/katacoda-scenarios/master/ldgq_liff_todo_course/liff_todo_scenario_1_LINE/img/s0509_richmenu_setting.jpg)
![richmenu_setting](https://raw.githubusercontent.com/MasatakaMiki/katacoda-scenarios/master/ldgq_liff_todo_course/liff_todo_scenario_1_LINE/img/s0510_richmenu_setting.jpg)

9. アクションを設定します<br>
<table><tr><th>項目</th><th>値</th></tr>
<tr><td>①タイプ</td><td>リンク</td></tr>
<tr><td>②URL</td><td>控えているLIFF URL</td></tr>
<tr><td>③アクションラベル</td><td>LIFFを開く</td></tr>
</table>
![richmenu_setting](https://raw.githubusercontent.com/MasatakaMiki/katacoda-scenarios/master/ldgq_liff_todo_course/liff_todo_scenario_1_LINE/img/s0511_richmenu_setting.jpg)

10. `画像を作成`をクリックし、リッチメニューのテキストや背景色を設定します。出来たら、適用ボタンをクリックします。<br>
![richmenu_setting](https://raw.githubusercontent.com/MasatakaMiki/katacoda-scenarios/master/ldgq_liff_todo_course/liff_todo_scenario_1_LINE/img/s0512_richmenu_setting.jpg)
![richmenu_setting](https://raw.githubusercontent.com/MasatakaMiki/katacoda-scenarios/master/ldgq_liff_todo_course/liff_todo_scenario_1_LINE/img/s0513_richmenu_setting.jpg)
![richmenu_setting](https://raw.githubusercontent.com/MasatakaMiki/katacoda-scenarios/master/ldgq_liff_todo_course/liff_todo_scenario_1_LINE/img/s0514_richmenu_setting.jpg)

11. 最後に、保存ボタンをクリックしたら、リッチメニューの完成です<br>
![richmenu_setting](https://raw.githubusercontent.com/MasatakaMiki/katacoda-scenarios/master/ldgq_liff_todo_course/liff_todo_scenario_1_LINE/img/s0515_richmenu_setting.jpg)

12. ボットの応答をオフに設定します。`設定`をクリック、`応答設定`をクリックし、`応答メッセージ`を`オフ`にします。<br>
![bot_setting](https://raw.githubusercontent.com/MasatakaMiki/katacoda-scenarios/master/ldgq_liff_todo_course/liff_todo_scenario_1_LINE/img/s0516_bot_setting.jpg)

13. チャネルシークレット、ユーザーIDを控えます。<br>
<a href="https://developers.line.biz/console/" target="_blank">LINE Developers</a>のページに戻り、`チャネル基本設定`をクリックします。下にスクロールして`チャネルシークレット`と`あなたのユーザーID`をメモします。<br>
![channel_secret](https://raw.githubusercontent.com/MasatakaMiki/katacoda-scenarios/master/ldgq_liff_todo_course/liff_todo_scenario_1_LINE/img/s0517_channel_secret.jpg)
![channel_secret](https://raw.githubusercontent.com/MasatakaMiki/katacoda-scenarios/master/ldgq_liff_todo_course/liff_todo_scenario_1_LINE/img/s0518_channel_secret.jpg)

14. チャネルアクセストークンを発行し、控えます。<br>
`Messaging API設定`をクリックします。下にスクロールして`チャネルアクセストークン`を発行し、メモします。<br>
![access_token](https://raw.githubusercontent.com/MasatakaMiki/katacoda-scenarios/master/ldgq_liff_todo_course/liff_todo_scenario_1_LINE/img/s0519_access_token.jpg)
![access_token](https://raw.githubusercontent.com/MasatakaMiki/katacoda-scenarios/master/ldgq_liff_todo_course/liff_todo_scenario_1_LINE/img/s0520_access_token.jpg)
<br>
↓発行後
<br>
![access_token](https://raw.githubusercontent.com/MasatakaMiki/katacoda-scenarios/master/ldgq_liff_todo_course/liff_todo_scenario_1_LINE/img/s0521_access_token.jpg)

15. 作ったボットと友達になりましょう。<br>
<a href="https://developers.line.biz/console/" target="_blank">LINE Developers</a>のページに戻り、`Messaging API設定`をクリックします。そこに表示されているQRコードをLINEのアプリから読み取って友達になります。<br>
![be_friend](https://raw.githubusercontent.com/MasatakaMiki/katacoda-scenarios/master/ldgq_liff_todo_course/liff_todo_scenario_1_LINE/img/s0522_be_friend.jpg)

これでこのボットのトークルームのリッチメニューからもLIFFが起動するようになりました！
