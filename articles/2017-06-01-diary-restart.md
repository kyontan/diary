---
title: 日記を再開します
---

# やったこと

## 日記を再開した

さすがに一ヶ月間何をしていたか思い出すのはしんどいので5月分の日記はなかったことにします。がんばって6月くらいは毎日更新できるように努力します。

5月もそこそこ映画を観たのでその感想だけでも書いとけばよかったなと後悔しています。
観た映画（劇場で観たもの）は、

  - ラストコップ THE MOVIE
  - 帝一の國
  - 劇場版FAIRY TALE
  - 夜明け告げるルーの唄
  - ブレイブウィッチーズ劇場版
  - けものフレンズ一挙
  - BLAME!

辺りでしょうか。帝一の國が面白かったです。あとBLAME!の漫画欲しいです。

## BFAの実装を進めた

とりあえず選言標準形（加法標準形）の実装を進めている。

## DaoでQuineを書いた

よく分からないけどRosetta Codeで目に付いたので。あんましGitHubのスターは無いけど1700コミットとかされてるので開発者のやる気はあるっぽい。C++っぽい型付けをオプショナルにできるのとかは面白そうに思う。

特にHomebrewでインストールできたりはしないので、自前でビルドすることになる。

```console
$ make -f Makefile.daomake macosx
```

とすると`bin/dao`が使えるようになるので、それで実行する。

```console
$ ./bin/dao quine.dao | diff quine.dao -
```

適当にドキュメントを見たらVerbatim Stringとやらが面白かったのでそれを使ってみたけど、もっと面白い機能があるかもしれない。非同期とかJITとか色々書いてあるし。ただ、ドキュメントが死ぬほど見辛いのでその気になれなかった。

## Déjà VuでQuineを書いた

デジャヴのヴの発音が難しいってハヤテのごとくネタだっけ？　詳しい人教えてください。

これも上に同じくRosetta Codeで見つけた言語。スタックベースのプログラミング言語なんだけど、右から左に実行されるのが特徴。右から左にすると関数が左側に来るから一見すると普通のプログラミング言語に見えるという特徴があるような、無いような‥‥。

なんか普通にレポジトリをcloneしてビルドしても、ヘッダにプロトタイプ宣言しかしてない関数に`inline`宣言が付いているらしくリンクでこける。のでそれを消して、ついでにmacには`-lrt`は無いのでそれを消すと動くようになる。

ファイルの拡張子は`.deja`で、コンパイル後のバイトコードの格納されたファイルの拡張子が`.vu`らしい。しかし一発でコンパイルから実行までされる。

```console
$ ./vm/vu quine.deja | diff quine.deja -
```

Quineは、そもそもREADMEに例としてあったので、それと被らないように1行で完結するようにした。`vm/std.deja`に標準ライブラリのコードがあるんだけど全く読めない。いや、なんとなく読めるんだけど何となくしか読めないと言うか‥‥。そのせいで苦労したけどどうにか1行のQuineが書けた。`!.\`で改行なしのデバッグプリントのようだ。
