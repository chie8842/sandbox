# agコマンド

* カレントディレクトリ以下のファイル内を検索
ag target_word

* ディレクトリを指定して検索
ag target_word /path/to/dir

| オプション|説明|
|----------|-------|
|z|圧縮ファイルも検索|
|G '正規表現'| 正規表現パターンで検索|
|--python|.pyファイルのみ検索|
|--ruby|.rb,.rhtml,.rjs,.rxml,.erb,.rake,.specのみ検索|
|--shell|.sh, .bash,.csh,.tcsh,.ksh,.zsh|
|--yaml|.yaml,.yml|
|--xml|.xml,.dtd,.xsl,.xslt,.ent|
|--php|.php,.phpt,.php3,.php4,.php5,.phtml|
|--java|.java,.properties|
|--html|.html,.htm,.shtml,.xhtml|
|--list-file-types|上記以外にもどんな言語に対応しているか表示|
|--hidden|隠しファイルも検索|
|-u|全ファイルを検索|
|-l|ファイル名のみ表示|
|-L|マッチしなかったファイル名のみ表示|
|-g|ファイル名に対する検索|
|--depth|ディレクトリ階層の深さを指定|






Reference: [The Silver Searcher のススメ](https://qiita.com/thermes/items/e1e0c94e2875df96921c)
