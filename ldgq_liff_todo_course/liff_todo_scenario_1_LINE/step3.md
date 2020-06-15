それでは早速、LINEの開発者向けコンソールからLIFFを作っていきましょう

1. ブラウザで LINE Developers Console を開き、ログインします<br>
<a href="https://developers.line.biz/console/" target="_blank">https://developers.line.biz/console/</a>

2. プロバイダーを作成または既存のプロバイダーを選択します<br>
![create_provider](https://raw.githubusercontent.com/MasatakaMiki/katacoda-scenarios/master/ldgq_liff_todo_course/liff_todo_scenario_1_LINE/img/s0301_create_provider.jpg)

3. チャネルを作成します。<font color="red">この時、必ず`LINEログイン`を選択してください。</font><br>
![create_channel](https://raw.githubusercontent.com/MasatakaMiki/katacoda-scenarios/master/ldgq_liff_todo_course/liff_todo_scenario_1_LINE/img/s0302_create_channel.jpg)

4. 各項目を埋めていきます<br>
<table><tr><th>項目</th><th>値</th></tr>
<tr><td>①チャネル名</td><td>LDGQ ToDoリスト</td></tr>
<tr><td>②チャネル説明</td><td>LDGQ LIFFアプリです</td></tr>
<tr><td>③アプリタイプ</td><td>チェックを2つ入れる</td></tr>
<tr><td>④メールアドレス</td><td>ご自身のメールアドレスを入力</td></tr>
</table>
![channel_setting](https://raw.githubusercontent.com/MasatakaMiki/katacoda-scenarios/master/ldgq_liff_todo_course/liff_todo_scenario_1_LINE/img/s0303_channel_setting.jpg)

5. 同意にチェックし、作成ボタンをクリックします。必須項目が未入力だったり、同意にチェックがない場合、作成ボタンはクリックできません。
![channel_setting](https://raw.githubusercontent.com/MasatakaMiki/katacoda-scenarios/master/ldgq_liff_todo_course/liff_todo_scenario_1_LINE/img/s0304_channel_setting.jpg)

6. `LIFF` をクリックして、追加ボタンをクリックします<br>
![create_liff](https://raw.githubusercontent.com/MasatakaMiki/katacoda-scenarios/master/ldgq_liff_todo_course/liff_todo_scenario_1_LINE/img/s0305_create_liff.jpg)

7. 各項目を埋めていきます<br>
<table><tr><th>項目</th><th>値</th></tr>
<tr><td>①LIFFアプリ名</td><td>LIFF-ToDoList</td></tr>
<tr><td>②サイズ</td><td>Full</td></tr>
<tr><td>③エンドポイント</td><td>https://temporary-name.herokuapp.com</td></tr>
<tr><td>④Scope</td><td>チェックを<font color="red">3つ</font>に入れる</td></tr>
<tr><td>⑤ボットリンク機能</td><td>On(Normal)</td></tr>
</table>
<font color="red">※エンドポイントは仮のURLです。herokuのアプリ作成後変更します。</font><br>
<font color="red">※Scopeは`すべて表示`をクリックしないと`chat_message.write`にチェックを入れることができないので注意</font>
![create_liff](https://raw.githubusercontent.com/MasatakaMiki/katacoda-scenarios/master/ldgq_liff_todo_course/liff_todo_scenario_1_LINE/img/s0306_liff_setting.jpg)
![create_liff](https://raw.githubusercontent.com/MasatakaMiki/katacoda-scenarios/master/ldgq_liff_todo_course/liff_todo_scenario_1_LINE/img/s0307_liff_setting.jpg)

8. 追加ボタンをクリックすると、LIFFのURLが生成されますので、控えておいてください<br>
`https://liff.line.me/9999999999-xxxxxxxx`<br>
<font color="red">LIFF URLの最後の/(スラッシュ)以降が、LIFFのIDです</font><br>
![create_liff](https://raw.githubusercontent.com/MasatakaMiki/katacoda-scenarios/master/ldgq_liff_todo_course/liff_todo_scenario_1_LINE/img/s0308_liff_url.jpg)

9. ついでに、`シェアターゲットピッカー`をONにしておきます。スクロールして、同意にチェックを入れ、有効化します。<br>
![create_liff](https://raw.githubusercontent.com/MasatakaMiki/katacoda-scenarios/master/ldgq_liff_todo_course/liff_todo_scenario_1_LINE/img/s0309_stp.jpg)
![create_liff](https://raw.githubusercontent.com/MasatakaMiki/katacoda-scenarios/master/ldgq_liff_todo_course/liff_todo_scenario_1_LINE/img/s0310_stp.jpg)
![create_liff](https://raw.githubusercontent.com/MasatakaMiki/katacoda-scenarios/master/ldgq_liff_todo_course/liff_todo_scenario_1_LINE/img/s0311_stp.jpg)

これで、LIFFの準備は完了しました。続いてボットを作成します！
