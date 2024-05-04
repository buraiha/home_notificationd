# Home Notificationd

「今日は何時に洗濯物を取り込む」  
「何時に犬の散歩をしろ、と通知がほしい」

等、カレンダーやTODOアプリ等を使って通知が可能なものはありますが、
「やっぱりいつも使ってるLINEで知らせてほしい」
という要望が自分の中から出てきたので作りました。皆さん、「～家グループ」とか、家族でLINEくらい使ってるでしょ？

基本的には管理者画面で通知を設定し、ユーザーは通知を受け取るだけのシンプルなアプリです。管理者画面のセキュリティはそれほど高くはなく、uuidをURLに含めて認証を行う簡単なものになっています。他家に知られるとまずい情報は扱わない方がよいでしょう。

将来的にはデーモン化したいので名前の最後に"d"がついてます。

## DEMO

作成中

## Features

以下、Version.1の要件定義メモです。実装するかどうかはわかんないですが、たいてい実装するでしょう。

- そもそも、デーモンにするか、cronで定期実行するか検討する。[MARKER: デーモンかcronか]
  - 最初はcronでいいかな。最終的にはデーモンにしたい。
- 通知機能
  - 時間を指定して、その時間以降に起動したら通知する。(できればタイムラグは短いほうがよいのでまあ最終的には1分を目指す。[MARKER: デーモンかcronか]にも関わりま)
  - DBはとりあえずSQLiteでいいんじゃない。
  - キーワード置換型通知
    - 通知内容にキーワードを埋め込むことができる。
    - キーワードは各メッセージごとに自由に定義可能。
      - Aというキーワードを通知時に"アルファベットのA"という文字列に置換する感じ。
    - 例えば、`{time}`というキーワードを埋め込むと、通知時にそのキーワードを指定した時間に置換する。
    - と、書いてはみたものの、こんな機能いるかや？ ちょっと考えていらにゃ初期は実装なし。
- 認証UUID_URL埋め込み型認証
  - 管理者画面にアクセスするための認証を、URLにUUIDを埋め込むことで行う。

※上はあくまでもメモなので、リリース後に機能一覧として整備する。  
上記Ver.1要件後の要件等はissueで管理する。

## Requirement

### LINE Notify

本アプリでは、LINE通知に[LINE Notify](https://notify-bot.line.me/ja/)で発行されるアクセストークン利用しています。  
利用方法は上記サイトをご確認ください。

### Libraries

## Installation

初期設定準備中

## Usage

使い方作成中

## Note

注意点などがあれば書く

## Author

古橋　崇史(Takashi Furuhashi)  
よろづシステムズ(Yorozu-Systems)  
<tf@yorozu-sys.net>  

## License

ライセンス選定中
