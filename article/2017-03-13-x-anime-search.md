---
title: Cross Anime Searchを軽量化した
---

# やったこと

## Cross Anime Searchを軽量化した

ひさしぶりにCross Anime Searchに手を入れた。APIのJSONのキーとかを無くして全部配列にしたら1MBあったレスポンスが700KBになった。大して変わらないような気がする。

あとGitHubに学生と認めてもらえたのでプライベートリポジトリを作れるようになったので、プライベートリポジトリを作ってそっちにプッシュするようにした。これで多少は扱いやすくなったと思う。

それにしても、サーバーのdocker-composeを落とす度にエラーが出てサーバーを再起動してるんだけど、これはどうしたらいいんだろう？　一度サーバーごと死んだので油断ならない。