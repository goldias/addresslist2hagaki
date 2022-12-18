addresslist2hagaki
==================
郵便局はがきデザインキットの宛名印刷機能が消滅してしまったので作成しました。
郵便局はがきデザインキットの住所録cvsファイルからjletteraddressl.cls用texファイルを生成します。
platex環境が前提条件となります。cf.https://texwiki.texjp.org/ （これだけのためにplatex環境構築するのはコスパ悪いかもしれません）
はがきデザインキットのcvs用に作っていますが、同梱のサンプルcsvファイルや、本体の%addressを参考にcsvファイルをエクセルなどで作成すればはがきデザインキットは必要ありません。


quick start
-----------
```bash
$ ./addresslist2hagaki sample_addresslist.csv sample_addresslist.tex
$ ptex2pdf -l sample_addresslist.tex
```
sample_addresslist.pdfが生成されていれば成功です。

Usage
-----
本体のaddresslist2hagakiはperlスクリプトです。
先頭の%senderの中身を自分に合わせて書き換えてください。
```perl
# 差出人を書き換えてください
my %sender = (
                name        =>      '千利休',
                nameb       =>      '　稲　',
                addressa    =>      '大阪府堺市堺区宿院町西一七',
                addressb    =>      '宮寺町中尾グランド三〇五',
                postcode    =>      '９２０３３４２'

);
```



```bash
$ ./addresslist2hagaki <入力cvsファイル名> <出力texファイル名>
```
あとはtexファイルを微調整・編集するなりしてください。同梱のjletteraddresslのREADME.mdやsample.texが参考になるでしょう。

```bash
$ ptex2pdf <texファイル名>
```
おつかれさまでした！