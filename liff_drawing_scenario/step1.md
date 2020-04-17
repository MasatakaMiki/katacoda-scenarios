ここでは、LIFF v2のスターターアプリをローカルに持って来て、きちんと動く環境にするために、3つのコマンドを実行します

1. LINEのgithubから、[line-liff-starter](https://github.com/line/line-liff-v2-starter) リポジトリをCloneします<br>
```shell
git clone https://github.com/line/line-liff-v2-starter
```{{copy}}

2. カレント・ディレクトを`line-liff-v2-starter`に変更します<br>
```shell
cd line-liff-v2-starter
```{{copy}}

3. Node Package ManagerでNode.jsのライブラリをインストールします<br>
```shell
npm install
```{{copy}}

4. KatacodaのIDEをクリックします
![ide](https://raw.githubusercontent.com/MasatakaMiki/katacoda-scenarios/master/liff_drawing_scenario/img/s0101_ide.jpg)<br>

5. `line-liff-v2-starter`を展開します
![ide](https://raw.githubusercontent.com/MasatakaMiki/katacoda-scenarios/master/liff_drawing_scenario/img/s0102_ide.jpg)<br>

6. `.gitignore`ファイルを作成します<br>
`line-liff-v2-starter`上でマウスを右クリック、`New File`をクリックし、ファイル名に.gitignoreと入力します
![gitignore](https://raw.githubusercontent.com/MasatakaMiki/katacoda-scenarios/master/liff_drawing_scenario/img/s0103_gitignore.jpg)<br>

7. ファイルに下記を追加し、保存します
```
node_modules
package-lock.json
```
![gitignore](https://raw.githubusercontent.com/MasatakaMiki/katacoda-scenarios/master/liff_drawing_scenario/img/s0104_gitignore.jpg)<br>

これで、ルートディレクトリにあるpackage.jsonに記載されたパッケージなどが一括でインストールされ、スターターアプリが動く環境が準備できました。<br>
それでは、次のステップから、このアプリをherokuに展開していきましょう！
