# CIDER

* Clojure Interactive Development Environment that Rocks
ClojureのインタラクティブなプログラミングをサポートするEmacsのプラグイン

~/.lein/profiles.cljに以下を記述する
```
{:user {:plugins [[cider/cider-nrepl "0.15.1"]]}}
```

## vim上で利用する場合
1. 以下のvimプラグインをインストールする
'tpope/vim-fireplace'

2. `lein repl`コマンドでREPLを起動する
3. vimをたちあげて、コマンドモードで`:Connect`を実行する
nREPL serverのホスト名、ポート番号を入力する

## vim-firebaseの使い方
visualモードで範囲を選択して`:Eval`を入力すると、REPL上で実行される
