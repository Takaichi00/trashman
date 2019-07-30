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