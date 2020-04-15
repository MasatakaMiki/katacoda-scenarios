それでは、LINEの開発者向けコンソールからLIFFを作っていきましょう

1. ブラウザで LINE Developers Console を開き、ログインします
    <a href="https://developers.line.biz/console/" target="_blank">https://developers.line.biz/console/</a>

2. プロバイダーを作成または既存のプロバイダーを選択します
![create_provider](https://raw.githubusercontent.com/MasatakaMiki/katacoda-scenarios/master/liff_drawing_scenario/img/s0301_create_provider.jpg)

3. チャネルを作成します。<font color="red">この時、必ずLINEログインを選択してください。</font>
![create_channel](https://raw.githubusercontent.com/MasatakaMiki/katacoda-scenarios/master/liff_drawing_scenario/img/s0302_create_channel.jpg)

4. 各項目を埋めていきます

|項目|値|
|:--|:--|
|①チャネル名|LDGQ-LIFF-Handson|
|②チャネル説明|LDGQ-LIFF-Handson|
|③アプリタイプ|チェックを2つ入れる|
|④メールアドレス|ご自身のメールアドレスを入力|
![channel_setting](https://raw.githubusercontent.com/MasatakaMiki/katacoda-scenarios/master/liff_drawing_scenario/img/s0303_channel_setting.jpg)

5. 同意にチェックし、作成ボタンをクリックします。必須項目が未入力だったり、同意にチェックがない場合、作成ボタンはクリックできません。作成ボタンをクリックした後に、「情報利用に関する同意について」が表示される場合は、そちらも同意をして進みます。
![channel_setting](https://raw.githubusercontent.com/MasatakaMiki/katacoda-scenarios/master/liff_drawing_scenario/img/s0304_channel_setting.jpg)

6. `LIFF` をクリックして、追加ボタンをクリックします
![create_liff](https://raw.githubusercontent.com/MasatakaMiki/katacoda-scenarios/master/liff_drawing_scenario/img/s0305_create_liff.jpg)

7. 各項目を埋めていきます

|項目|値|
|:--|:--|
|①LIFFアプリ名|LIFF-drawing|
|②サイズ|Tall|
|③エンドポイント|https://ldgq-handson-20200406-name.herokuapp.com|
|④Scope|チェックを<font color="red">3つ</font>に入れる|
|⑤ボットリンク機能|On(Normal)|

<font color="red">エンドポイントは前のステップで控えておいたherokuのアプリのURLです</font>
<font color="red">Scopeは`すべて表示`をクリックしないと`chat_message.write`にチェックを入れることができないので注意</font>

![create_liff](https://raw.githubusercontent.com/MasatakaMiki/katacoda-scenarios/master/liff_drawing_scenario/img/s0306_liff_setting.jpg)
![create_liff](https://raw.githubusercontent.com/MasatakaMiki/katacoda-scenarios/master/liff_drawing_scenario/img/s0307_liff_setting.jpg)

8. 追加ボタンをクリックすると、LIFFのURLが生成されますので、控えておいてください
    `https://liff.line.me/9999999999-xxxxxxxx`
    <font color="red">LIFF URLの最後の/(スラッシュ)以降が、LIFFのIDです</font>
    ![create_liff](https://raw.githubusercontent.com/MasatakaMiki/katacoda-scenarios/master/liff_drawing_scenario/img/s0308_liff_url.jpg)

9. ついでに、`シェアターゲットピッカー`をONにしておきます。スクロールして、同意にチェックを入れ、有効化します。
![create_liff](https://raw.githubusercontent.com/MasatakaMiki/katacoda-scenarios/master/liff_drawing_scenario/img/s0309_stp.jpg)
![create_liff](https://raw.githubusercontent.com/MasatakaMiki/katacoda-scenarios/master/liff_drawing_scenario/img/s0310_stp.jpg)
![create_liff](https://raw.githubusercontent.com/MasatakaMiki/katacoda-scenarios/master/liff_drawing_scenario/img/s0311_stp.jpg)

これで、LIFFの準備は、完了しました。それでは、またherokuに戻って、アプリをデプロイ（展開）していきます！
