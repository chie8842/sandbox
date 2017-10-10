## mathjaxをきちんと表示できるPDFファイルの作り方

いろいろやったけど部分的に表示できないなどのトラブルが多いので、うまくいった方法をメモ。

### 編集環境
editor: vscode,プラグイン：Markdown+Math
コマンドパレット(Command + Shift + P)でMarkdownプレビューを横に表示

### PDFの作成
pandocとかいろいろ試したけど部分的に描画されなかったりする。
最終的に以下でうまくいった。

1. VSCodeのコマンドパレット(Command + Shift + P)でMarkdown: Clip Markdown+Math to HTML で、HTMLに変換した内容をクリップボードに保存
2. 保存した内容をsample.htmlなどに書き出す。
3. FirefoxでもChromeでも見れた。
4. ブラウザの印刷機能でPDFに書き出し
