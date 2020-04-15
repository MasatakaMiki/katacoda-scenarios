Share Target Picker（シェアターゲットピッカー）とは、LIFFから送信先を選んでメッセージを送信することが出来る機能です。
これまでは、送信先トークルームなどからLIFFを開かないと、特定の送信先にメッセージを送信できませんでした。
この機能が追加されたことで、どこで開かれても（ブラウザでも！）、任意の友達にメッセージが送信できるようになりました！

1. vimでファイルを編集します
    ```shell
    vim ./public/oekaki.js
    ```{{copy}}

2. 120行目の`liff.sendMessage`を`liff.shareTargetPicker`に変更して、保存します
    ```shell
    vim ./public/oekaki.js
    ```{{copy}}
![vim](https://raw.githubusercontent.com/MasatakaMiki/katacoda-scenarios/master/liff_drawing_scenario/img/s0601_vim.jpg)
|key|内容|
|:--|:--|
|i|挿入モード|
|Esc|コマンドモード|
|:wq(Enter)|保存して終了|
|:q!(Enter)|保存せず終了|

3. gitでherokuにデプロイし直します。gitのコマンドを3つ実行します。
    ```shell
    git add .
    ```{{copy}}
    ```shell
    git commit -m "use share target picker"
    ```{{copy}}
    ```shell
    git push heroku master
    ```{{copy}}

4. 確認してみましょう
