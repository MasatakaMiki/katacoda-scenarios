Share Target Picker（シェアターゲットピッカー）とは、LIFFから送信先を選んでメッセージを送信することが出来る機能です。
これまでは、送信先のトークルームなどからLIFFを開かないと、特定の送信先にメッセージを送信できませんでした。
この機能が追加されたことで、どこで開かれても（ブラウザでも！）、任意の友達にメッセージが送信できるようになりました！

1. IDEでファイル(./public/oekaki.js)を編集します<br>
120行目の`liff.sendMessage`を`liff.shareTargetPicker`に変更、127行目の`liff.closeWindow();`をコメントアウトして、保存します<br>
![vim](https://raw.githubusercontent.com/MasatakaMiki/katacoda-scenarios/master/liff_drawing_scenario/img/s0701_vim.jpg)<br>

2. gitでherokuにデプロイし直します。gitのコマンドを3つ実行します。<br>
```shell
git add .
```{{copy}}
```shell
git commit -m "use share target picker"
```{{copy}}
```shell
git push heroku master
```{{copy}}

3. 確認してみましょう<br>

4. 【補足】LIFF v2にliff.isApiAvailable()が追加されました<br>
<a href="https://l.facebook.com/l.php?u=https%3A%2F%2Fdevelopers.line.biz%2Fja%2Fdocs%2Fliff%2Frelease-notes%2F%3Ffbclid%3DIwAR0ExUGFrsonRNmvpOgJfuHh_ssbjhrAHBibupkdIc3t7boiTezM0H8ekPw%23liff-v2%25E3%2581%25ABliff-isapiavailable-%25E3%2581%258C%25E8%25BF%25BD%25E5%258A%25A0%25E3%2581%2595%25E3%2582%258C%25E3%2581%25BE%25E3%2581%2597%25E3%2581%259F&h=AT2dc1lOEzw5KhWggFVL3r7BrvUwGB6pAMydqKhikkMRA8wkAu-70-I0EO7GIHvo_GyR1QcX-L4SqfNihcRv9fg3hJpUaiEgvccpS9hMinPb7hva35G3nzeGjf1hi5HkPLQ" target="_blank">リリースノート</a><br>
以下のように `liff.isApiAvailable('shareTargetPicker')` を事前に実行することで、`liff.shareTargetPicker()`のエラーを回避することができます。<br>
![api](https://raw.githubusercontent.com/MasatakaMiki/katacoda-scenarios/master/liff_drawing_scenario/img/s0702_api.jpg)

以上で、今回のハンズオンはすべて終了です。<br>
皆さんも、LIFFのスターターアプリをベースに色々な面白いアプリを作ってみてくださいね！<br>
お疲れ様でした。
