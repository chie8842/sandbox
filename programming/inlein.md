# inlein
Clojureをスクリプトとして使うためのツール
leiningen経由でclojureのコードを実行すると起動が遅い問題を緩和する。


## Install
* JDK1.7以上が入っていること
* inleinをダウンロード
https://github.com/hyPiRion/inlein/releases/latest
inlein-daemon-0.2.0-standalone.jar をダウンロード

```
mkdir ~/.clojure
wget https://github.com/hyPiRion/inlein/releases/download/0.2.0/inlein ~/.clojure/
chmod 775 ~/.clojure/inlein 
echo "export PATH=$PATH:~/.clojure" >> ~/.bashrc
```

## Usage

```
inlein foo.clj
```

## サンプルプログラム

```
$ cal foo.clj
#!/usr/bin/env inlein
; ↑ シバン行。
; *nix環境では、これが書いてあってスクリプトに実行権限が与えられていれば、そのファイルを直接実行できる。

; 依存ライブラリ一覧。クオートしてる以外はleiningenと同様の形式。
'{:dependencies [[org.clojure/clojure "1.8.0"]
                 [com.hypirion/primes "0.2.1"]]}

; ここからが処理内容。nsは無くてもよい。

(require '[com.hypirion.primes :as p])

; -main関数とかいらなくて、いきなり地の文に処理を書いていける。

(when-not (first *command-line-args*)
  (println "Usage:" (System/getProperty "$0") "prime-number")  ; $0でファイル名が参照できる
  (System/exit 1))

(-> (first *command-line-args*)
    (Long/parseLong)
    (p/get)
    println
)```


# Reference
[Clojureをスクリプトとして使う：inlein](http://hatappo.hatenadiary.jp/entry/2016/03/19/182931)
