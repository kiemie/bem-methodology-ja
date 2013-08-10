# BEM

通常のWebサイト開発プロセスは、デザインや技術面に対する要求が変わらないことを想定している。

デザイナーもフロントエンド開発者も、そしてプログラマーも、お互いの領域で作業を行い、干渉し合うことはほとんどない:

1. デザイナーはデザインレイアウトという形でサイトのデザインを作成する
2. フロントエンド開発者はデザインレイアウトをもとに静的なHTMLやCSSを作成する
3. プログラマーはそれらの静的なページからテンプレートを作り、いくつかのJavaScriptも書く

このようなアプローチは、Webサイトのデザインがその生涯を通じて変わることなく、また変更が「コンテンツを追加することだけ」である場合にのみうまく機能する。

しかし、大抵はそうはいかない。Webサイトは常に開発中の状態で生き続ける。ページのデザインは徐々に変化していき、新しいページやブロックが追加され続ける。

もしWebサイトのソースコードが決められた構造から外れていくとしたら、もしその開発が決められたルールに基づかないとしたら、次第にメンテナンスが困難になっていくだろう。
Webサイトのコードは開発者たちの手を離れていってしまう。

BEM方法論では、Webサイトの開発に携わるすべての人は1つのコードベースで作業を行い、同じ用語でやり取りをし、同じ言葉を使うことになる:

1. Webサイトのデザインはいつでも変更可能であり、私たちはそれに備えなければならない
2. HTMLやCSSはデザインと一緒に開発され、いつでもデザインの変化に対応できる
3. プログラマーとフロントエンド開発者はWebサイトのコードベース上で一緒に作業をし、お互いのコードに貢献し合う

## 方法論が生み出された状況
BEM方法論は、[Yandex](http://company.yandex.com)で沢山のWebサービスを開発する過程で生み出され、以下のような狙いがある:

* 高速な開発、息の長いプロジェクト
   * 長い期間に渡ってメンテナンスをしていけるようにするためのアーキテクチャーを備えつつも、Webサイトの最初のバージョンは迅速に開発・公開できなければならない。
* チームのスケーラビリティ
   * チームに新しい人を加えることでスピードが落ちるのではなく、上がらなければならない。急激な学習カーブなしに、新しいメンバーをチームにアサインできる必要がある。
   * コードはプロジェクトに対して適切に構造化され、時間がたってもチームが変わってもメンテ可能でなければならない。
* コードの再利用
   * UIの一貫性を保つため、また、一般的なインターフェース部品の開発労力を最小限にするためには、そういった部品は簡単に再利用できなければならない。
   * ソースコードは他のコードに対する文脈的な依存を持つべきではない。そうすることで、コードを他の場所に容易に移動することができる。

何年もの間、私たちは問題に対する解決策を探し続けてきており、ある時点でそれが`BEM方法論`となった。