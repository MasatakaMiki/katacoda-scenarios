スターターアプリをお絵描きアプリに改造しましょう。<br>
今回は、すでに完成したアプリを上書きし、デプロイし直すという手順を行ったあと、具体的にどこを変更したのかを説明したいと思います。

1. カレント・ディレクトリを変更します
    ```shell
    cd ..
    ```{{copy}}

2. githubからお絵描きアプリのファイルをCloneします
    ```shell
    git clone https://github.com/MasatakaMiki/ldgq.git
    ```{{copy}}

3. ファイルを上書きコピーします
    ```shell
    cp -f -r ./ldgq/202004_handson/oekaki-app/* ./line-liff-v2-starter
    ```{{copy}}

4. 変更箇所の説明
    <a href="" target="_blank"></a>

5. gitでherokuにデプロイし直します。gitのコマンドを3つ実行します。
    ```shell
    git add .
    ```{{copy}}
    ```shell
    git commit -m "deploy oekaki app"
    ```{{copy}}
    ```shell
    git push heroku master
    ```{{copy}}

6. LIFF URLにアクセスしてみましょう

お絵描きアプリが動いたでしょうか？このようにスターターアプリである程度のひな形が準備されており、
herokuを利用すると、簡単なアプリなら、あっという間にリリース＆動作確認を行うことができます。<br>
次のステップでは、3月にLINEからリリースされたShare Target Picker（シェアターゲットピッカー）を試してみましょう。
