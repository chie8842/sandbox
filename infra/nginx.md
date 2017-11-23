nginx
====

webサーバ


リバースプロキシ


resolver
DNSを指定する。
通常locationの内容は最初のアクセス時にキャッシュされるため、
ホスト名指定で書くとき、IPアドレスが変わるとエラーが起こる。
これを防ぐために指定する。

Reference
---------
[【nginx】ホスト名指定でのリバプロはresolverをセットで](http://sora33.hatenadiary.com/entry/2017/07/02/002353)
