ここでは、LIFF v2のスターターアプリをローカルに持って来て、きちんと動く環境にするために、3つのコマンドを実行します

1. LINEのgithubから、[line-liff-starter](https://github.com/line/line-liff-v2-starter) リポジトリをCloneします<br>
```shell
git clone https://github.com/line/line-liff-v2-starter
```{{copy}}

2. カレント・ディレクトを`line-liff-v2-starter`に変更します
    ```shell
    cd line-liff-v2-starter
    ```{{copy}}

3. Node Package ManagerでNode.jsのライブラリをインストールします
   ```shell
   npm install
   ```{{copy}}

これで、ルートディレクトリにあるpackage.jsonに記載されたパッケージなどが一括でインストールされ、スターターアプリが動く環境が準備できました。<br>
それでは、次のステップから、このアプリをherokuに展開していきましょう！
