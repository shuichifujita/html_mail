# html_mail
htmlメール制作用

## 概要
SASSをコンパイルしてCSSにした後、CSSをインラインに変換します。  
また、ブラウザを自動で更新します。

## 使い方
```shell
$ git clone https://github.com/yuki-tomioka/html_mail.git
$ cd html_mail
$ npm ci
$ npx gulp

// メールの送信
$ npx gulp mail
```

### メール送信のための設定方法
gulpfile.jsのsmtpInfoを下記のように設定する。

- Gmailを使って送信する場合

下記のような.envを作成する

```dotenv
# 送信先（複数はカンマ区切り、スペースを入れない）
mailTo=example@gmail.com,example_02@gmail.com

# 送信元
smtpUser=example_03@gmail.com
smtpPass=example_03_pass
smtpHost=smtp.gmail.com
smtpPort=465
```
ログインエラー対応  
Gmailを確認すると「重大なセキュリティ通知」としてログインをブロックしましたというメールが届いている場合、[安全性の低いアプリのアクセス
](https://myaccount.google.com/lesssecureapps?pli=1)から安全性の低いアプリの許可を有効にして改善しないか試す。  
検証後は設定を元に戻すことをおすすめする。

## 主なプラグイン
- [gulp-inline-css](https://www.npmjs.com/package/gulp-inline-css)
- [gulp-mail](https://www.npmjs.com/package/gulp-mail)
- [node-env-file](https://www.npmjs.com/package/node-env-file)

## 作成環境
- gulp
  - CLI version: 2.2.0
  - Local version: 4.0.2
- nodenv
  - local 10.15.3
