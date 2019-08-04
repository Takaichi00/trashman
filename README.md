# Trashman

- 以下の要件を満たすアプリケーションを作成する
  - 自身が住んでいるのゴミの日を登録できる
  - 指定日付のゴミ種類を取得できる
  - ゴミの日の朝に通知を送ることができる
- LINE Bot の利用を検討する
  - 参考サイト: [LINE Bot × Java(Spring Boot)構築手順](https://qiita.com/zakisanbaiman/items/e87c4834b28c6d964e54)



## LINE Developers アカウント登録

- Messaging API を利用するため、[LINE Developers のサイト](https://developers.line.biz/ja/services/messaging-api/)から開発者のアカウント登録

- [Messaging APIの公式ドキュメント](https://developers.line.biz/ja/docs/messaging-api/)

## [Messaging APIを利用する](https://developers.line.biz/ja/docs/messaging-api/getting-started/)

- Messaging APIを使ってボットを作成するには、まず[LINE Developersコンソール](https://developers.line.biz/console/)でチャネルを作成する必要があります。

### チャネルの作成

- アカウントはすでに作成済み
- 新規プロバイダーを作成する
- 「Trashman」チャンネルを作成する



## [サンプルボット作成](https://developers.line.biz/ja/docs/messaging-api/building-sample-bot-with-heroku/)

### [heroku CLI をインストール](https://devcenter.heroku.com/articles/heroku-cli)

```
$ sudo snap install --classic heroku
```



### Echoサンプルボットをデプロイする

- [コンソール](https://developers.line.biz/console/)で、チャネルシークレットとチャネルアクセストークンを確認します。
- GitHubの`sample-spring-boot-echo`ディレクトリの[READMEファイル](https://github.com/line/line-bot-sdk-java/tree/master/sample-spring-boot-echo#step-2)に含まれる**［Deploy to Heroku］**ボタンをクリックします。
- 手順1で確認した値を使って、［App name］（任意）、［LINE_BOT_CHANNEL_TOKEN］、および［LINE_BOT_CHANNEL_SECRET］の各フィールドに入力し、**［Deploy app］**をクリックします。次の手順で使うので、アプリ名は記録しておきます。アプリがデプロイされるまでしばらく待ちます。
- 「`https://{HEROKU_APP_NAME}.herokuapp.com/callback`」というURL形式で、Webhook URLを[コンソール](https://developers.line.biz/console/)に入力します。
  注：`{HEROKU_APP_NAME}`は手順3で指定したアプリ名です。
- コンソールの［チャネル基本設定］ページにあるQRコードを読み取って、ボットが関連づけられている公式アカウントをLINEで友だち追加します。
- LINE公式アカウントにLINEでテキストメッセージを送り、同じメッセージが返ってくることを確認します。



#### ログを見る

```
$ heroku login
$ heroku logs --tail --app linebot-test-syamozi
```

- LINE からメッセージを送信するとそのままテキストメッセージが返却されることを確認



## Spring Boot Application 作成

- [Spring Initializr](https://start.spring.io/)