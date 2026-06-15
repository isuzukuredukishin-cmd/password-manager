# Local Vault スマホ配布手順

このフォルダは、Local Vault をスマホにインストール可能なPWAとして配布するための一式です。

## 配布方法

`local-vault-pwa` フォルダをHTTPSで公開できる場所に置きます。例:

- GitHub Pages
- Netlify
- Cloudflare Pages
- 自宅NASやVPSのHTTPSサイト

PWAのインストールとオフライン起動には、スマホ側から `https://...` で開けることが必要です。`file://` で直接開くと通常のHTMLとしては使えますが、ホーム画面アプリ化とオフラインキャッシュは有効になりません。

## Android

1. Chromeで公開URLを開きます。
2. アプリ内の「インストール」ボタン、またはChromeメニューの「アプリをインストール」を押します。
3. ホーム画面の `Local Vault` から起動します。

## iPhone

1. Safariで公開URLを開きます。
2. 共有ボタンを押します。
3. 「ホーム画面に追加」を選びます。
4. ホーム画面の `Local Vault` から起動します。

## 別スマホへ保管庫を移す

Local Vault のデータは各スマホのブラウザ内に保存されます。別端末へ移す場合は、元の端末で「バックアップ」を押して暗号化JSONを保存し、新しい端末で「読み込み」からそのJSONを選んでください。マスターパスワードがないと復号できません。

## APKやiPhoneアプリ化について

Androidは、このPWAをWebView/CapacitorでAPK化できます。ただしAPKをビルドするにはAndroid StudioまたはAndroid SDKが必要です。

iPhoneは任意の実行ファイルやインストーラーを配布して自由に入れる方式が基本的に使えません。個人配布ならPWA、正式なネイティブアプリ配布ならApple Developer ProgramとTestFlight/App Storeが必要です。
