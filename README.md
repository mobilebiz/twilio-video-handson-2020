# WebRTC ハンズオン 2020年版 （Twilio CLI）

Twilio Videoのハンズオン（2020年版）

## Twilio Videoの設定

- Twilioの管理コンソールを開き、スライドメニューから**Programmable Video**を選択します。
- **部屋**（Rooms）の**設定**(Setting）を選択します。
- **Room Topology**を以下のように設定します。

|設定項目|設定値|備考|
|:--|:--|:--|
|ROOM TYPE|Peer-to-peer|ピアツーピアルーム|
|TURN|ENABLED|必要に応じてTURNを利用する|
|MAXIMUM PERTICIPANTS|2|最大参加者数を2に制限|

<img width="800" alt="スクリーンショット 2018-07-21 00.48.43.png" src="https://qiita-image-store.s3.amazonaws.com/0/86046/6264b568-306c-0439-727e-7c85911befdd.png">

- **Save**ボタンを押します。

## インストール

Twilio CLI Serverless でプロジェクトを作成します。

```sh
$ twilio serverless:init --template blank [プロジェクト名]
```

本プロジェクトの中の以下のファイルを、作成したご自分のプロジェクトにコピーします。

- `assets/video.html`
- `assets/video.js`
- `functions/video-token.js`

.env.sampleを参考に、ご自分のプロジェクトの.envファイルに以下の3項目を追加します。

変数名|説明
:--|:--
MAIN_ACCOUNT_SID|TwilioのアカウントSID（ACから始まる文字列）
TWILIO_VIDEO_KEY|APIキー（SKから始まる文字列）
TWILIO_VIDEO_SECRET|APIシークレット

デプロイ

```sh
$ twilio serverless:deploy
```

## 実行

デプロイされた以下のファイルをブラウザで開きます。

`https://XXXXXXXXXXXXXX-dev.twil.io/video.html`

