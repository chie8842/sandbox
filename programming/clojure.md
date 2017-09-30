# Clojure

## 公式サイト
https://clojure.org/

日本語訳してくれている人がいる。
https://japan-clojurians.github.io/clojure-site-ja/

## 概要（Wikipedia抜粋）
Clojure (発音は/'klouʒər/[2], クロージャー)はプログラミング言語であり、LISP系の言語の方言の一つである。関数型プログラミングのプログラミングスタイルでのインタラクティブな開発を支援し、マルチスレッドプログラムの開発を容易化する汎用言語である。Clojure言語のプログラムはJava仮想マシンとMicrosoft .NET 共通言語ランタイムで動作する。Clojure言語は「データとしてのプログラムコード」 (英語:「code as data」) という思想で設計されており、洗練されたマクロ機構を持つ。

## Clojureを試すには

幾つかの方法がある

1. Minimal Install
Download clojre-X.X.X.jar and execute following command

```
java -cp clojure-1.8.0.jar clojure.main
```

2. Online Repl Environment
  * [repl.it](https://repl.it/languages/clojure)
  * [TryClojure](http://tryclj.com/)

3. Leiningen
JavaやScalaでいうmaven, gradle, sbtのようなビルドシステム。
leiningenをインストールすると、以下のコマンドでreplが使える

```
lein repl
```

4. Boot
BootはClojureのビルドフレームワークで、Clojureスクリプトをアドホックに評価するもの。
[Clojure の Boot というビルドツールについて](http://ayato.hateblo.jp/entry/20150502/1430560799)

```
boot repl
```

## クラスパスを表示する方法

```
(use 'clojure.contrib.pprint)
(pprint (seq (.getURLs (java.lang.ClassLoader/getSystemClassLoader))))
```
もしくは以下
```
(use 'clojure.contrib.classpath)
(classpath)
```

参考：http://d.hatena.ne.jp/fatrow/20100405/1270483781
