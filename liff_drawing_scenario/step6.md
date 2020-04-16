スターターアプリをお絵描きアプリに改造しましょう。<br>
今回は、すでに完成したアプリを上書きし、デプロイし直すという手順を行ったあと、具体的にどこを変更したのかを説明したいと思います。

1. package.jsonにライブラリを2つ追加します<br>
    ・body-parser
    ```shell
    npm install body-parser
    ```{{copy}}
    ・date-utils
    ```shell
    npm install date-utils
    ```{{copy}}

2. カレント・ディレクトリを変更します
    ```shell
    cd ..
    ```{{copy}}

3. githubからお絵描きアプリのファイルをCloneします
    ```shell
    git clone https://github.com/MasatakaMiki/ldgq.git
    ```{{copy}}

4. ファイルを上書きコピーします
    ```shell
    cp -f -r ./ldgq/202004_handson/oekaki-app/* ./line-liff-v2-starter
    ```{{copy}}

5. 変更箇所の説明
<a href="https://github.com/MasatakaMiki/ldgq/tree/master/202004_handson/oekaki-app" target="_blank">https://github.com/MasatakaMiki/ldgq/tree/master/202004_handson/oekaki-app</a>
<table><tr><th>ファイル</th><th>内容</th></tr>
<tr><td>./public/index.html</td><td>お絵描きアプリに変更</td></tr>
<tr><td>./public/imgs/*.png</td><td>ペンと消しゴムの画像</td></tr>
<tr><td>./public/oekaki.css</td><td>スタイルシート</td></tr>
<tr><td>./public/oekaki.js</td><td>liff-starter.jsをコピーして編集</td></tr>
<tr><td>./public/vconsole.min.js</td><td>便利</td></tr>
<tr><td>./index.js</td><td>画像ファイルをimgの下に保存する関数を追加</td></tr>
</table>

6. カレント・ディレクトを`line-liff-v2-starter`に変更します
    ```shell
    cd line-liff-v2-starter
    ```{{copy}}

7. gitでherokuにデプロイし直します。gitのコマンドを3つ実行します。
    ```shell
    git add .
    ```{{copy}}
    ```shell
    git commit -m "deploy oekaki app"
    ```{{copy}}
    ```shellw
    git push heroku master
    ```{{copy}}

8. 再度、リッチメニューからLIFFを起動してみましょう

お絵描きアプリが動いたでしょうか？このようにスターターアプリである程度のひな形が準備されており、herokuを利用すると、簡単なアプリなら、あっという間にリリース＆動作確認を行うことができます。<br>
次のステップでは、3月にLINEからリリースされたShare Target Picker（シェアターゲットピッカー）を試してみましょう。
