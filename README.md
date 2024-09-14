# nostr-relay-benchmark by inaridiy

Mattn氏が作成したnostr-relay-benchmarkをフォークし、自作のリレーを追加しました。

## ベンチマーク手法

イベント投稿、ID指定のイベント検索、イベント削除。これを1セットとして5回の実行に掛かる秒数を計測。

あくまで大阪の実家からの接続なので関東でやると変わる可能性あり。またリレーを動かしているサーバのスペックが大きく異なる可能性あり。

以下の手順で実行。

```
$ ./benchmark-all.sh
```

## 対象リレー

* wss://yabu.me (strfry)
* wss://nos.lol (strfry)
* wss://cagliostr.compile-error.net (cagliostr)
* wss://nostr.compile-error.net (nostr-relay)
* wss://relay-jp.nostr.wirednet.jp (nostream)
* wss://relay.nostr.band (独自)
* wss://nrelay-jp.c-stellar.net (strfry)
* wss://r.kojira.io (strfry)
* wss://relay-jp.shino3.net (strfry)
* wss://nostr.inaridiy.com (Honostr 独自)

## 結果

|リレー                           |スコア|ソフトウェア|
|---------------------------------|------|------------|
|wss://yabu.me                    |3.78  |strfry      |
|wss://nos.lol                    |18.89 |strfry      |
|wss://cagliostr.compile-error.net|4.16  |cagliostr   |
|wss://nostr.compile-error.net    |4.08  |nostr-relay |
|wss://relay-jp.nostr.wirednet.jp |4.09  |nostream    |
|wss://relay.nostr.band           |20.78 |独自        |
|wss://nrelay-jp.c-stellar.net    |4.03  |strfry      |
|wss://r.kojira.io                |12.77 |strfry      |
|wss://relay-jp.shino3.net        |4.21 |strfry      |
|wss://nostr.inaridiy.com         |4.15  |Honostr     |

## 結論

結果を見る限り、Mattn氏が作成したオリジナルと同じ傾向の結果が出た。
しかし、上位のリレーはスコアが4秒前後で並んでいるため、計測場所の回線のせいで律速されている可能性がある。
あと、拙作のリレーも4.15秒という結果だったので、ちょっと嬉しい。

## License

MIT

## Author

inaridiy
Yasuhiro Matsumoto (a.k.a. mattn)
