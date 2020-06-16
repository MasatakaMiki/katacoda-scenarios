herokuにデプロイしているスターターアプリをDB連携アプリに改造しましょう

1. Terminalから、再度、herokuにログインしましょう。<br>
```shell
heroku login --interactive
```{{copy}}

2. herokuにデプロイしているgitをcloneします
```shell
git clone https://git.heroku.com/{herokuのアプリ名}.git
```{{copy}}
<font color="red">※{LIFF アプリ名}部分は控えているheroku アプリ名に、"{}"は除いて置き換えてください。</font><br>

3. githubからToDoリストアプリのファイルをCloneします<br>
```shell
git clone https://github.com/MasatakaMiki/ldgq.git
```{{copy}}

4. ファイルを上書きコピーします<br>
```shell
cp -f -r ./ldgq/202006_handson/todo-app/* ./{herokuのアプリ名}
```{{copy}}
<font color="red">※{LIFF アプリ名}部分は控えているheroku アプリ名に、"{}"は除いて置き換えてください。</font><br>

5. カレント・ディレクトを`{herokuのアプリ名}`に変更します<br>
```shell
cd {herokuのアプリ名}
```{{copy}}

6. herokuの環境変数にデータベース情報を設定します<br>
```shell
heroku config:set PG_HOST={PG Host} PG_NAME={PG Database} PG_USER={PG User} PG_PORT={PG Port} PG_PWD={PG Password}
```{{copy}}
<font color="red">※{PG Host}、{PG Database}、{PG User}、{PG Port}、{PG Password}部分は前のステップで控えたデータベース情報を使用します。"{}"は除いて置き換えてください。</font><br>
例）<br>
```shell
heroku config:set PG_HOST=ec2-9-99-999-99.compute-1.amazonaws.com PG_NAME=x9xxxxx9xxx999 PG_USER=xxxxxxxxxxxxxx PG_PORT=5432 PG_PWD=0x00x00x9999999x0x0xx00000x9x999999999xx9x9xx00000x9x00x0x0x99x0
```
設定した環境変数は、以下のコマンドで確認できましたね。ここはよく間違うポイントなので、慎重によくチェックしてください！<br>
```shell
heroku config
```{{copy}}

7. package.jsonにライブラリを3つ追加します<br>
・body-parser<br>
```shell
npm install body-parser
```{{copy}}
・pg<br>
```shell
npm install pg --save
```{{copy}}
・knex<br>
```shell
npm install knex --save
```{{copy}}

8. gitの初期設定を行います<br>
```shell
git config --global user.email you@example.com
```{{copy}}
<font color="red">※you@example.com部分はご自身のメールアドレスに置き換えてください。</font><br>
```shell
git config --global user.name your_name
```{{copy}}
<font color="red">※your_name部分はご自身の名前に置き換えてください。</font><br>

9. gitでherokuにデプロイします。gitのコマンドを3つ実行します。<br>
```shell
git add .
```{{copy}}
```shell
git commit -m "deploy todo-list app"
```{{copy}}
```shell
git push
```{{copy}}

10. ToDoリストのアプリがデプロイされました。LINEアプリやブラウザで動作確認してみましょう。また、<a href="https://pgweb-demo.herokuapp.com/" target="_blank">pgweb</a>でテーブルのレコードの状態も確認してみましょう。<br>

11. ブラウザから、タスクを完了させた場合、エラーメッセージが表示されます。これは、外部ブラウザで開かれている場合、LIFFのsendMessagesが使用できないので、条件分岐でエラーメッセージを表示するようにしているためです（todolist.js 181行目～）。LIFFからはメッセージが送れないので、友達になっているボットを利用して、ボットのトークルームにメッセージが送信されるようにしてみましょう。

12. herokuの環境変数にボットの情報を設定します。チャネルシークレットとチャネルアクセストークンの2つを追加します。<br>
```shell
heroku config:set CHANNEL_SECRET={チャネルシークレット}
```{{copy}}
<font color="red">※{チャネルシークレット}部分は最初のシナリオで控えているチャネルシークレットに、"{}"は除いて置き換えてください。</font><br>
```shell
heroku config:set CHANNEL_ACCESS_TOKEN={チャネルアクセストークン}
```{{copy}}
<font color="red">※{チャネルアクセストークン}部分は最初のシナリオで控えているチャネルアクセストークンに、"{}"は除いて置き換えてください。</font><br>

13. package.jsonにライブラリを追加します<br>
・LINE Messaging API SDK for nodejs(https://github.com/line/line-bot-sdk-nodejs)<br>
```shell
npm install @line/bot-sdk --save
```{{copy}}

14. サーバー側（./index.js）にルートを追加します。1行目、22～29行目、87～100行目のコメントアウトを解除します。<br>
![fix_pg](https://raw.githubusercontent.com/MasatakaMiki/katacoda-scenarios/master/ldgq_liff_todo_course/liff_todo_scenario_3_APP/img/s0101_fix_pg.jpg)
<br>
![fix_pg](https://raw.githubusercontent.com/MasatakaMiki/katacoda-scenarios/master/ldgq_liff_todo_course/liff_todo_scenario_3_APP/img/s0102_fix_pg.jpg)

15. LIFFのjs（./public/todolist.js）に外部ブラウザだった場合の処理を追加します。183行目と184行目をコメントアウトし、185～207行目のコメントアウトを解除します。<br>
![fix_pg](https://raw.githubusercontent.com/MasatakaMiki/katacoda-scenarios/master/ldgq_liff_todo_course/liff_todo_scenario_3_APP/img/s0103_fix_pg.jpg)

16. gitでherokuにデプロイします。gitのコマンドを3つ実行します。<br>
```shell
git add .
```{{copy}}
```shell
git commit -m "add external browser's sending message method"
```{{copy}}
```shell
git push
```{{copy}}

17. 【補足】<br>
①メッセージ送信は、送信者の名前やアイコンを変更することもできます。<br>
```shell
client.pushMessage(hidden_userid, {
    type: 'text',
    text: message,
    sender: {
        name: "MIKI",
        iconUrl: "https://p62.f2.n0.cdn.getcloudapp.com/items/04uPNLeG/59UcuxelIy3u3Nc1584956046_1584956055.png?v=c586b91712e6400e8055dc46c7f30ac9",
    }
})
```{{copy}}<br>
②Flex Messageというものもあります。ちょっと長くなりますが・・・<br>
```shell
client.pushMessage(hidden_userid, {
  "type": "bubble",
  "hero": {
    "type": "image",
    "url": "https://p62.f2.n0.cdn.getcloudapp.com/items/04uPNLeG/59UcuxelIy3u3Nc1584956046_1584956055.png?v=c586b91712e6400e8055dc46c7f30ac9",
    "size": "full",
    "aspectRatio": "20:13",
    "aspectMode": "cover",
    "action": {
      "type": "uri",
      "uri": "http://linecorp.com/"
    }
  },
  "body": {
    "type": "box",
    "layout": "vertical",
    "contents": [
      {
        "type": "text",
        "text": "MIKI",
        "weight": "bold",
        "size": "xl"
      },
      {
        "type": "box",
        "layout": "baseline",
        "margin": "md",
        "contents": [
          {
            "type": "icon",
            "size": "sm",
            "url": "https://scdn.line-apps.com/n/channel_devcenter/img/fx/review_gold_star_28.png"
          },
          {
            "type": "icon",
            "size": "sm",
            "url": "https://scdn.line-apps.com/n/channel_devcenter/img/fx/review_gray_star_28.png"
          },
          {
            "type": "icon",
            "size": "sm",
            "url": "https://scdn.line-apps.com/n/channel_devcenter/img/fx/review_gray_star_28.png"
          },
          {
            "type": "icon",
            "size": "sm",
            "url": "https://scdn.line-apps.com/n/channel_devcenter/img/fx/review_gray_star_28.png"
          },
          {
            "type": "icon",
            "size": "sm",
            "url": "https://scdn.line-apps.com/n/channel_devcenter/img/fx/review_gray_star_28.png"
          },
          {
            "type": "text",
            "text": "1.0",
            "size": "sm",
            "color": "#999999",
            "margin": "md",
            "flex": 0
          }
        ]
      },
      {
        "type": "box",
        "layout": "vertical",
        "margin": "lg",
        "spacing": "sm",
        "contents": [
          {
            "type": "box",
            "layout": "baseline",
            "spacing": "sm",
            "contents": [
              {
                "type": "text",
                "text": "From",
                "color": "#aaaaaa",
                "size": "sm",
                "flex": 1
              },
              {
                "type": "text",
                "text": "Tagawa-gun, Fukuoka",
                "wrap": true,
                "color": "#666666",
                "size": "sm",
                "flex": 5
              }
            ]
          },
          {
            "type": "box",
            "layout": "baseline",
            "spacing": "sm",
            "contents": [
              {
                "type": "text",
                "text": "Time",
                "color": "#aaaaaa",
                "size": "sm",
                "flex": 1
              },
              {
                "type": "text",
                "text": "9:00 - 18:00",
                "wrap": true,
                "color": "#666666",
                "size": "sm",
                "flex": 5
              }
            ]
          }
        ]
      }
    ]
  },
  "footer": {
    "type": "box",
    "layout": "vertical",
    "spacing": "sm",
    "contents": [
      {
        "type": "button",
        "style": "link",
        "height": "sm",
        "action": {
          "type": "uri",
          "label": "CALL",
          "uri": "https://linecorp.com"
        }
      },
      {
        "type": "button",
        "style": "link",
        "height": "sm",
        "action": {
          "type": "uri",
          "label": "WEBSITE",
          "uri": "https://linecorp.com"
        }
      },
      {
        "type": "spacer",
        "size": "sm"
      }
    ],
    "flex": 0
  }
})
```{{copy}}<br>
<a href="https://developers.line.biz/flex-simulator/" target="_blank">シミュレータ</a>があるので、簡単に作れます。シミュレータに慣れるための<a href="https://developers.line.biz/ja/news/2020/06/09/flex-message-simulator-tutorial/" target="_blank">チュートリアル</a>も準備されています。<br>
<br>
③LIFFには、シェアターゲットピッカーという機能があります。これは、友だちやグループを指定して、メッセージを送信できる機能です。<br>
```shell
liff.sendMessages(
```
の部分を<br>
```shell
liff.shareTargetPicker(
```{{copy}}
に変えてみましょう<br>
<br>
LINE DevelopersのTwitter(@LINE_DEV)をフォローしておけば、API関連の更新情報をいち早く知ることができます！<br>

18. LILFFアプリを公開しましょう。LINE DevelopersのLIFF（LINEログイン）の設定で、`非公開`をクリックして、`公開`にします。<br>
![open_to_the_public](https://raw.githubusercontent.com/MasatakaMiki/katacoda-scenarios/master/ldgq_liff_todo_course/liff_todo_scenario_3_APP/img/s0104_open_to_the_public.jpg)

以上、終了！<br>
お疲れ様でした！！
