# jsSandbox

JavaScript が実行できる Chrome Extension (v3)

## 概要

### 実行

- 🏃Run
- `alt` + `Enter`

`console.log` のみ、出力可能（`.error` や、`.warn` 等は未対応）

### エディタ部分

[Monaco Editor](https://microsoft.github.io/monaco-editor/) (`v0.50.0`)

### 実行環境

iframe の sandbox 内で`eval` 呼び出し

- [javascript - console.log の履歴にアクセスしたいのですがどうすればよいでしょうか？ - スタック・オーバーフロー](https://ja.stackoverflow.com/questions/2388/console-log%E3%81%AE%E5%B1%A5%E6%AD%B4%E3%81%AB%E3%82%A2%E3%82%AF%E3%82%BB%E3%82%B9%E3%81%97%E3%81%9F%E3%81%84%E3%81%AE%E3%81%A7%E3%81%99%E3%81%8C%E3%81%A9%E3%81%86%E3%81%99%E3%82%8C%E3%81%B0%E3%82%88%E3%81%84%E3%81%A7%E3%81%97%E3%82%87%E3%81%86%E3%81%8B)
- [マニフェスト - サンドボックス | Chrome Extensions | Chrome for Developers](https://developer.chrome.com/docs/extensions/reference/manifest/sandbox?hl=ja)
- [サンドボックス化された iframe で eval() を使用する  |  Chrome Extensions  |  Chrome for Developers](https://developer.chrome.com/docs/extensions/how-to/security/sandboxing-eval?hl=ja)
- [chrome-extensions-samples/api-samples/sandbox/sandbox at main · GoogleChrome/chrome-extensions-samples · GitHub](https://github.com/GoogleChrome/chrome-extensions-samples/tree/main/api-samples/sandbox/sandbox)

## 拡張のインストールから起動

- [Chrome 拡張機能の概要｜ React ではじめる Chrome 拡張開発入門](https://zenn.dev/alvinvin/books/chrome_extension/viewer/chapter02)

- [開発のための基礎知識｜ React ではじめる Chrome 拡張開発入門](https://zenn.dev/alvinvin/books/chrome_extension/viewer/chapter03#4.-toolbar-action%EF%BC%88%E3%83%84%E3%83%BC%E3%83%AB%E3%83%90%E3%83%BC%E3%82%A2%E3%82%AF%E3%82%B7%E3%83%A7%E3%83%B3%EF%BC%89)

## エラー対応

Chrome の拡張機能ページにて、エラー対応処理

[Chrome 拡張機能の作り方を分かりやすく解説](https://original-game.com/how-to-make-chrome-extensions/#:~:text=%E3%81%AE%E3%81%A7%E3%80%81%E4%BF%AE%E6%AD%A3%E3%81%97%E3%81%9F%E3%82%89%E3%80%8C-,%E3%81%99%E3%81%B9%E3%81%A6%E5%89%8A%E9%99%A4,-%E3%80%8D%E3%82%92%E3%82%AF%E3%83%AA%E3%83%83%E3%82%AF%E3%81%97)

## Monaco Editor の更新方法

### 取得先

[Monaco Editor](https://microsoft.github.io/monaco-editor/) のページの [download link](https://registry.npmjs.org/monaco-editor/-/monaco-editor-0.50.0.tgz) から、`.tgz` を直接取得

[monaco-editor/website at main · microsoft/monaco-editor · GitHub](https://github.com/microsoft/monaco-editor) リポジトリでは、自前でビルドする必要があるため

### 解凍

[Windows で拡張子が tar.gz 形式のファイルを解凍/展開する | 無停電電源装置(UPS) | イートン](https://www.eaton-daitron.jp/techblog/12776.html)

```解凍コマンド.cmd
tar -xvzf XXX.tar.gz
```

`package` フォルダが吐かれるので、`./jsSandBox/src/js/` の`package` へ上書き

## todo - wip

- [ ] フォルダ構成
  - 各 1 ファイルにぎゅっとまとまっているので
- [ ] 開発環境整備
  - Docker から、node で諸々持ってきて。。。的な
  - React 使うとか
- [ ] `console` 関係の出力
  - かなり力技してるので、スマートにしたい
  - dev_tools の情報を反映できないかな？
- [ ] 耐久値と危険度テスト
- [ ] エディタ部分と、ログ表示部分のサイズを自由に動かしたい
- [ ] wasm とかでエンジンそのものを乗せる？
  - 他の言語もやってみたい
