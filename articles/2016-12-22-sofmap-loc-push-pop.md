---
title: ソフマップでイヤホンを交換してもらったり、あきゆめくくるを買ったり、#<loc:push>や#<loc:pop>プラグマを実装したり
---

<script async src="//cdn.embedly.com/widgets/platform.js"></script>

やったことが妙に多くて次の日に回したら、次の日も忙しくなって書ききれる気がしない。

# やったこと

## ソフマップに行ってイヤホンを交換してもらった

イヤホンが壊れたのでメーカーに送ろうと思ったのだけど、そもそも買った店に持っていけばいいのではないかと気付いたので行ってみたら、すぐに新品に交換してもらえた。

ソフマップは神。

## あきゆめくくるを買った

ソフマップが神だったので課金しようと思い買ってきてしまった。ぶっちゃけアメニティーズライフとどっちにするか悩んだ。

まだインストールすらしていない。

ソフマップは神。

## `#<loc:push>`や`#<loc:pop>`を実装した

<a class="embedly-card" href="https://github.com/crystal-lang/crystal/pull/3751">Reset location after block yielding in macro expansion by MakeNowJust · Pull Request #3751 · crystal-lang/crystal</a>

Crystalのマイナーというかドキュメント化されてるのか怪しい機能として`#<loc:...>`プラグマというのがある。これは字句解析中に処理されて、エラーメッセージ中に表示される行番号を変更することができる。具体的にはECRの内部とマクロ中の`yield`の展開時に使われている。

しかし、一方的に座標を変更するだけで元の座標に戻すことができない。ので、マクロ中で`yield`したあとの部分でエラーが起きるとエラー位置が盛大にずれる。というわけで元の座標に戻せる機能を追加し、マクロ中の`yield`にもそれを対応した。

ちなみに、名前が`#<loc:push>`と`#<loc:pop>`になっているけれど1段階のpush/popにしか対応していない。なぜなら複数回`push`できるようにした場合のユースケースが想定できないから。もしも見付かったら実装される可能性がある。

# 結論

ソフマップは神。