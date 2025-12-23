---
kindle-sync:
  bookId: '49734'
  title: 'リーダブルコードC#: C#で読みやすいコードを書く50の方法'
  author: ピーコックアンダーソン
  asin: B0B35PG33Y
  lastAnnotatedDate: Invalid date
  bookImageUrl: 'https://m.media-amazon.com/images/I/61N2eI+QRxL._SY160.jpg'
  highlightsCount: 83
---
# リーダブルコードC#
## Metadata
* Author: [ピーコックアンダーソン](https://www.amazon.comundefined)
* ASIN: B0B35PG33Y
* ISBN: B0B2TTVP38
* Reference: https://www.amazon.com/dp/B0B35PG33Y
* [Kindle link](kindle://book?action=open&asin=B0B35PG33Y)

## Highlights
ポイントは， 何行で書くかではなく何秒で読めるか？ ということです。行数を減らすのではなく，初めてコードを読んだ人が，何秒で理解できるか？ということを意識してコードを書くことが，読みやすいコードを書くことにつながります。ですので，コードの行数が減ったかどうかではなく， 理解に必要な秒数 が減っているかどうかをチェックしてみてください。 — location: [335](kindle://book?action=open&asin=B0B35PG33Y&location=335) ^ref-18247

---
隣のとなりまでしか訪ねないということ を目安にして，うまく文を切っていくことを検討してみてください。 — location: [453](kindle://book?action=open&asin=B0B35PG33Y&location=453) ^ref-55441

---
恋愛のように「君みたいな子，嫌いじゃない」みたいな表現はやめましょう。 — location: [594](kindle://book?action=open&asin=B0B35PG33Y&location=594) ^ref-43442

---
11.5 コードは書くより読む方が多い プログラマーを始めたころはあまり気が付かないかもしれませんが，プログラムというのは，書くより，読まれる機会の方が，断然に多いのです。書くのは，担当プログラマーが書く１回ですが，読む機会は，デバッグをするプログラマー全員が，バグ修正や，調査などのたびに，何度も読まれる機会があります。 — location: [987](kindle://book?action=open&asin=B0B35PG33Y&location=987) ^ref-12329

---
機械的にこういったコードレビューを行うようにした方が，人間が指摘することに比べて，精神的にもいいと思います。あまりこういったケースを人間同士で指摘しあうと，険悪なムードになったりもしますので，ツールでチェックできることはツールにやらせるということがおすすめです。 — location: [1378](kindle://book?action=open&asin=B0B35PG33Y&location=1378) ^ref-14185

---
if文のもう一つのポイントが，早めに抜けるということですね。 — location: [1449](kindle://book?action=open&asin=B0B35PG33Y&location=1449) ^ref-56649

---
対象外の場合は極力早めに抜けて，すべてをくぐり抜けてきた場合のみ処理するという形が一番読みやすいコードになります。「 — location: [1450](kindle://book?action=open&asin=B0B35PG33Y&location=1450) ^ref-2599

---
判断は可能な限り１つずつ行うのが，バグを少なくするコツです。 — location: [1471](kindle://book?action=open&asin=B0B35PG33Y&location=1471) ^ref-54891

---
どういった名前がわかりやすいかというのは，ある程度個人の主観にも関係しますが，まずは「気取らない」ということです。「素直」に命名するというのが１つです。 — location: [1480](kindle://book?action=open&asin=B0B35PG33Y&location=1480) ^ref-30570

---
「素直に気取らず命名する」ということと，あとは基本的にはすべて「英語」で命名するというのがC#の基本です。. — location: [1485](kindle://book?action=open&asin=B0B35PG33Y&location=1485) ^ref-25932

---
何文字までという決まりはありませんが，40文字程度なら問題ないと思います。 — location: [1494](kindle://book?action=open&asin=B0B35PG33Y&location=1494) ^ref-42298

---
ではインテリセンスの機能があり「.Ele」などど入力すると，「.ElectricPowerGeneration」が選択できるようになっているため，あまりタイピング量を気にして命名する必要もありません。それよりも後から見た人が理解できるようにする方が大事です。 — location: [1500](kindle://book?action=open&asin=B0B35PG33Y&location=1500) ^ref-10011

---
意図が明確な名前を付ける — location: [1504](kindle://book?action=open&asin=B0B35PG33Y&location=1504) ^ref-11681

---
DateCheckというメソッド名では現在日時をチェックするということがわからないし，dateという引数名では，現在日時を求めているということが理解できません。 — location: [1517](kindle://book?action=open&asin=B0B35PG33Y&location=1517) ^ref-8139

---
CurrentDateCheckやcurrentDateという名前にすることで，現在日時を求めていることが理解できます。 — location: [1522](kindle://book?action=open&asin=B0B35PG33Y&location=1522) ^ref-49421

---
例えばCurrentDateクラスの中にあるdate変数であればそれが現在日時であることがわかるということはあるので，うまくクラス分割ができている場合はこの限りではありません。 — location: [1533](kindle://book?action=open&asin=B0B35PG33Y&location=1533) ^ref-13638

---
基本的には仕様をそのまま英語で表現しましょう。回りくどい言い方や，連想しないと分らないもの，仕様がわからないと意味の分からない名前にしないようにしましょう。 — location: [1627](kindle://book?action=open&asin=B0B35PG33Y&location=1627) ^ref-1961

---
一人のプログラマーが勝手に命名するのであれば，素直に，普通に英語に訳した名前にするというのが基本です。 — location: [1631](kindle://book?action=open&asin=B0B35PG33Y&location=1631) ^ref-37244

---
for文の中でインクリメントする変数名を「i」にしたりする要領で，こういった短いスコープであれば，こういった名前でも特に問題ないということで，NOTBADとしています。 — location: [1653](kindle://book?action=open&asin=B0B35PG33Y&location=1653) ^ref-40571

---
クラスの中で， 1つの事しかしていなければ短い名前でも理解できる — location: [1736](kindle://book?action=open&asin=B0B35PG33Y&location=1736) ^ref-30899

---
元のクラス名が長いのは仕方がない — location: [1742](kindle://book?action=open&asin=B0B35PG33Y&location=1742) ^ref-39395

---
もともと長いクラス名は長いままで仕方がありません。これは，この名前が一番意味を表現できているということで命名したということであれば，これを短くする術はないので，これは仕方がないです。 — location: [1744](kindle://book?action=open&asin=B0B35PG33Y&location=1744) ^ref-43071

---
対になる言葉の組み合わせを決めておく 今回は「対になる言葉の組み合わせを決めておく」というお話をしていきます。言葉にはついになる言葉がありますね。StartとStopなど，1つの組み合わせで表現される単語があるのでまとめておきます。参考にしてください。 24.1 対になる単語の組み合わせ一覧 ● add / remove ● insert / delete ● get / set ● start /stop ● begin / end ● send / receive ● first / last ● put / get ● up / down ● show / hide ● open / close ● source / destination ● increment / decrement ● lock / unlock ● old / new ● next / previous startで始まって，endで終わるとか，beginで始まってStopで終わるということがないように，対になる単語を意識してコーディングしましょう。 — location: [1842](kindle://book?action=open&asin=B0B35PG33Y&location=1842) ^ref-41360

---
お客さんのことを「Customer」と呼ぶのか，「User」と呼ぶのか，商品と製品で違いがあるのか，自社製品は製品と表現し，仕入れているものを商品と呼んでいるなら，その通り命名した方がいいし，同じ意味だけど，日本語がごちゃまぜで使われているのであれば，プログラミングする際は，Productに統一するなど，検討が必要です。 ホテルの宴会予約システムなどでは「宴会」のことを「Banquet」と呼ぶのか，「Party」と呼ぶのかなど，英訳が複数ある場合は，必ずチームで統一させておく必要があります。 基本的に，その業界に精通している人にヒヤリングすれば，ある程度統一した言葉というものがわかってくるはずです。 — location: [1887](kindle://book?action=open&asin=B0B35PG33Y&location=1887) ^ref-12773

---
うまく言葉が見つけられない場合も，プログラマー全員で統一できていれば問題にはなりません。 — location: [1897](kindle://book?action=open&asin=B0B35PG33Y&location=1897) ^ref-28865

---
どのような名前にするとしても，プログラマー全員が統一した名前を付けることが重要です。しかし，それは口で言うほど簡単なことではありません。 — location: [1912](kindle://book?action=open&asin=B0B35PG33Y&location=1912) ^ref-16699

---
開発プロジェクトで辞書ツールのようなものを作り，「日本語」と「英語」が対になったリストのようなものがあるといいでしょう。 — location: [1915](kindle://book?action=open&asin=B0B35PG33Y&location=1915) ^ref-13150

---
エクセルを使う程度でもいいと思うので，チーム全体が名前を統一できるような辞書を作ることをおすすめします。 — location: [1921](kindle://book?action=open&asin=B0B35PG33Y&location=1921) ^ref-3654

---
GOOD：インスタンス変数（メンバ変数）は一番上 — location: [1931](kindle://book?action=open&asin=B0B35PG33Y&location=1931) ^ref-26151

---
アンダーバーを付ける利点 インテリセンス エディターにアンダーバーを打ち込むと，インテリセンスにprivateな変数が絞り込まれるため，クラスで使用しているメンバ変数が把握しやすい。 — location: [1960](kindle://book?action=open&asin=B0B35PG33Y&location=1960) ^ref-27168

---
全ての型がオブジェクトしか書けないような言語で，「これはintとして使う」みたいな感じで覚えておかないといけないようなプログラミング言語の場合は，変数名に型名を付けたらいいとは思いますが，C#ではそんな必要もないので，変数の名前の解説のところでもお伝えした通り，そのままの英語で命名するということで，覚えておいてください。 — location: [2033](kindle://book?action=open&asin=B0B35PG33Y&location=2033) ^ref-14884

---
34.3 usingキーワードでの記述 次のようにSqlConnectionのインスタンスを生成するタイミングで，usingキーワードで囲んでしまえば，usingブロックを抜けた際に，確実にDisposeが呼び出されます。 private 　 void 　解放が必要なオブジェクトにはusingを使うGOOD() { 　 using 　( var 　connection　=　 new 　 SqlConnection("XXX")) 　{ 　Console.WriteLine($"...{connection}");　//① 　}　 } また，①の部分で例外が発生しても確実にDisposeが呼び出されるようになっており，前述の，try-finallyの書き方と挙動は同じになります。挙動は同じですが，可読性はこちらの方がよく，瞬時に解放漏れが無いことも理解できるので，ことらの書き方を推奨しています。 — location: [2475](kindle://book?action=open&asin=B0B35PG33Y&location=2475) ^ref-4490

---
は，②のようにvarキーワードを使って書いてしまえばよいです。ただ，①の書き方がBADかというと，そういうわけではなく，①の書き方でも特に問題ありません。そもそもvarキーワードはC#の最初からあったわけではなく，C#のバージョン３で登場している文化なので，varを使わないといけないということではありません。ただ，①のように左右に全く同じことを書くくらいならvarキーワードを使った方が楽ですよという程度のものです。あとは，複数のローカル変数を宣言する場合に，varでそろえると，左辺が３文字で揃うので見やすいという特性もあります。 — location: [2515](kindle://book?action=open&asin=B0B35PG33Y&location=2515) ^ref-28812

---
varキーワードを使った方がよいかどうかは，右辺を文字として見ただけで，明らかに型がわかる場合はvarを使うというのが良いと思います。 — location: [2524](kindle://book?action=open&asin=B0B35PG33Y&location=2524) ^ref-22829

---
次の①のような場合は，右辺を見ただけでは型はわかりません。実施にはGetProductの戻り値の型が指定されているはずなので，コンパイラ的には型はわかるので，コンパイルエラーにはなりません。だからこのケースでもvarを使う人もいるとは思いますが，ただ，テキストとしてみるだけの場合，例えば本や印刷物で見る場合は，型はわからないので，こういった場合は②のように，あえてvarを使わずに型を明記するという考え方もあります。 //NOTBAD:この場合，文字を見ただけでは右辺から型が分からないので //varでなくてもいい var 　product3　=　ProductSqlServer.GetProducts();　//① //NOTBAD:右辺から型が書かれていないのでvarでなくていい IEnumerable<Product>　product4　=　ProductSqlServer.GetProducts();　//② この辺りは，人によって価値観が分かれるところで，この場合もvarが良いと感じる人もいるかもしれません。ただ，私は右辺をテキストとしてみたときに明らかに型がわかる場合にvarを使う，という判断基準が良いと考えています。 — location: [2528](kindle://book?action=open&asin=B0B35PG33Y&location=2528) ^ref-18323

---
①のようにvarで宣言するのと，②のようにインタフェースであるIMeasureで宣言するのでは意味が変わってきます。 //次の2つはvarとIMeasureで意味が変わってくる var 　measure1　=　 new 　MeasureRepository();　//① //GOOD:インタフェースに対して実装する IMeasure　measure2　=　 new 　MeasureRepository();　//② ①の場合はmeasure1がMeasureRepositoryという具象クラスがそのまま取得されますが，②の場合はMeasureRepositoryという具象クラスをIMeasureのインタフェースで受け取ります。①の場合は，インタフェースに対して実装しているつもりが，具象クラスに対して実装していたということになってしまうので，通常は②のように，インタフェースで受け取りたい場合は，インタフェースとして宣言する必要があるので注意してください。 — location: [2556](kindle://book?action=open&asin=B0B35PG33Y&location=2556) ^ref-13720

---
名前は動詞 メソッド名は基本的には動詞で付けます。保存する処理の場合は，「Save」としたり，印刷処理なら「Print」にしたりといった感じで命名します。 — location: [2573](kindle://book?action=open&asin=B0B35PG33Y&location=2573) ^ref-61530

---
命名はシンプルな方がいいです。例えば「保存処理」だから「Save」ではなく「SaveProcess」といった感じで，語尾にProcessを付ける，といった命名は冗長です。 — location: [2583](kindle://book?action=open&asin=B0B35PG33Y&location=2583) ^ref-7983

---
ただし，検索条件によって，検索したいメソッドが複数ある場合で，すべてにFindという命名にしてしまうと，引数の型が同じ場合にコンパイルエラーとなるので，その場合は，FindByPriceのように，どういった条件で検索するのかを表した名前にするといいでしょう。 — location: [2606](kindle://book?action=open&asin=B0B35PG33Y&location=2606) ^ref-54192

---
FindByProductIdは主キーなので，この場合のもFindとしておいて，その他の特殊な検索の場合のみFindByPriceなどと語尾でずらして命名してもいい — location: [2615](kindle://book?action=open&asin=B0B35PG33Y&location=2615) ^ref-36472

---
単数と複数を意識した名前とし，1行が返却されるのか，複数行が返却されるのがわかるような名前で命名し — location: [2623](kindle://book?action=open&asin=B0B35PG33Y&location=2623) ^ref-41040

---
GOOD:functionは何が取得されるかが分かるように命名 — location: [2642](kindle://book?action=open&asin=B0B35PG33Y&location=2642) ^ref-30869

---
生成メソッドはCreate_型変換の時はToを使う — location: [2763](kindle://book?action=open&asin=B0B35PG33Y&location=2763) ^ref-53661

---
インスタンスを生成するメソッドはメソッド名の頭にCreateを付けると分りやすいです。 — location: [2769](kindle://book?action=open&asin=B0B35PG33Y&location=2769) ^ref-44418

---
オブジェクトの型を変換して返却するようなメソッドの場合は頭にToを付けます。マイクロソフトのライブラリの中にもToInt32など，型を変換するメソッドの頭には，Toが使われています。 — location: [2791](kindle://book?action=open&asin=B0B35PG33Y&location=2791) ^ref-56184

---
重複コードが生まれるタイミングは，次の2つではないでしょうか？ ①既存のコードをコピーして一部を変更したコードを書く ②すでに似たようなコードがあることを知らずに同じようなコードを書く ②に関してはプログラムコードの構成，アーキテクチャーなどが整理されていないとどうしても発生してしまいますが，①に関しては，確信犯なので，防ぎようがあります。要するに，コピーして一部変更しようとしている時点で，同じようなコードを量産しようとしてしまっているので，なんとか，そこで食い止められないかを検討する余地があります。 — location: [2866](kindle://book?action=open&asin=B0B35PG33Y&location=2866) ^ref-60542

---
コピーして同じようなメソッドを作成しようとした場合は，「共通化出来ないか？」ということを検討し，この例であれば，addStockのパラメータを追加することで，GetProductAとGetProductBの動きを共通化し，GetProductCというメソッド１つで対応できるようになるので，こういった共通化が出来ないかを，メソッドを追加するタイミングで検討しましょう。 — location: [2931](kindle://book?action=open&asin=B0B35PG33Y&location=2931) ^ref-64177

---
リージョンとは#regionと#endregionというキーワードで囲むことで，エディター上でコードの開閉をすることが出来る機能です。 — location: [2943](kindle://book?action=open&asin=B0B35PG33Y&location=2943) ^ref-16975

---
リージョンが不要な理由としては，まず，開閉が面倒ということです。１つくらいなら大した問題にはならないかもしれませんが，数が多いと開くのが面倒です。まとめて開くということもできますが，とにかく開閉が面倒です。 — location: [2964](kindle://book?action=open&asin=B0B35PG33Y&location=2964) ^ref-57119

---
クラスを小さく作るというオブジェクト指向的観点でコーディングをすれば，50行程度の小さなクラスが大量で作られたりするので，リージョンで区切らないといけないということは，うまくクラス分割が出来ていないということが予想されます。リージョンで区切らないといけないようなクラス自体を作らないようにした方が，オブジェクト指向の観点からは，良いコードである可能性が高いわけです。 最後に，リージョンで区切るとStyleCop.Analyzersというマイクロソフトの解析ツールでは警告が出ます。「リージョンで区切らないでください」というに警告が出るわけです。マイクロソフトの機能でリージョンがあるのに，警告が出るとは何とも不思議ですが，マイクロソフト的にも，リージョンがコードの見通しを悪くしているという認識なのだと思います。 — location: [2968](kindle://book?action=open&asin=B0B35PG33Y&location=2968) ^ref-51722

---
明示的にinternalと書いた方がわかりやすいですし，StyleCop.Analyzersという解析ツールでも，アクセス修飾子無しは警告扱いになるため，すべてのクラスにアクセス修飾子とつけると覚えておいてください。 — location: [2992](kindle://book?action=open&asin=B0B35PG33Y&location=2992) ^ref-8836

---
VisualStudio2022以降は，クラスをデフォルトで作成した段階でinternalがデフォルトで記載されるようになっているようです。それ以前のバージョンではアクセス修飾子なしなので，特に注意が必要です。 — location: [3004](kindle://book?action=open&asin=B0B35PG33Y&location=3004) ^ref-29429

---
GOOD：sealedを付ける クラスのアクセス修飾子を付けるとともに，その流れで覚えておいていただきたいのが，sealedキーワードを付けるということです。 — location: [3009](kindle://book?action=open&asin=B0B35PG33Y&location=3009) ^ref-57771

---
このようにinternalなどのアクセス修飾子に続けてsealedキーワードを書くことで，継承できないクラスになります。多くのクラスは継承されるつもりで作成していないと思うので，基本的にはsealedキーワードを付けると覚えておいてください。 — location: [3016](kindle://book?action=open&asin=B0B35PG33Y&location=3016) ^ref-24261

---
Sealedキーワードが無いと，継承してもよいクラスということを明示していることになるので，不用意な継承が行われたり，継承されていないかを解析したりする手間も出てしまうので，クラスを作成する段階でお決まりの作法としてsealedキーワードを記述しておくことをお勧めします。 — location: [3021](kindle://book?action=open&asin=B0B35PG33Y&location=3021) ^ref-58352

---
クラス名はソリューションエクスプローラーで並べることを意識する — location: [3027](kindle://book?action=open&asin=B0B35PG33Y&location=3027) ^ref-61248

---
クラス名は，大項目，中項目，小項目の順に書くことで，ファイル名としてソリューションエクスプローラーで表示されたときにアルファベット順に並ぶので，その際に同じカテゴリーのクラスがわかりやすくなります。以前，メソッド名はインテリセンスを意識して命名するというようなことを解説しましたが，それと同じ要領です。 — location: [3033](kindle://book?action=open&asin=B0B35PG33Y&location=3033) ^ref-25873

---
例えば「計測」という「Measure」というカテゴリーがあり，その中に，「Rain」と「Temperature」というオブジェクトが必要な場合は，大項目であるMeasureを先に記載し，「MeasureRain」「MeasureTemperature」とすることで，同じカテゴリーのクラスがうまくエクスプローラー上に並ぶため，わかりやすくなります。 — location: [3038](kindle://book?action=open&asin=B0B35PG33Y&location=3038) ^ref-37710

---
これを逆に，Measureを後ろにつけてしまうと，「RainMeasure」「TemperatureMeasure」といった感じになり，エクスプローラー上で見たときに，離れてファイルが表示され，カテゴリーが同じであることがわかりづらくなります。この考え方はデータベースのテーブルも同じです。大項目，中項目，小項目の順番で記載することで，同じ用途と使われるテーブルということがわかりやすくなり，良い命名になります。 — location: [3045](kindle://book?action=open&asin=B0B35PG33Y&location=3045) ^ref-24462

---
BAD:語尾にDataやInfoやObject等は付けない — location: [3061](kindle://book?action=open&asin=B0B35PG33Y&location=3061) ^ref-63217

---
よほどの理由がない限りは，顧客ならCustomerなど，名詞のみにしてしまった方がよい命名となります。 — location: [3066](kindle://book?action=open&asin=B0B35PG33Y&location=3066) ^ref-29155

---
インタフェースの場合は，慣例として，C#ではインタフェースを示す「I」をインタフェース名の頭に付けることが一般的なので，IMemberなど，頭に「I」を付けることでインタフェースを表現します。 //インタフェース //GOOD:インタフェースの頭にIを付ける public 　 interface 　 IMember {　} — location: [3100](kindle://book?action=open&asin=B0B35PG33Y&location=3100) ^ref-26585

---
抽象クラスの場合は，語尾にBaseを付けることで抽象クラスを表現します。 — location: [3107](kindle://book?action=open&asin=B0B35PG33Y&location=3107) ^ref-19151

---
Memberという命名よりは，MemberBaseと命名することで，抽象クラスということを表現します。 — location: [3110](kindle://book?action=open&asin=B0B35PG33Y&location=3110) ^ref-54633

---
また，テストコードクラスを複数まとめたフォルダーを作成する場合は，ViewModelTestsなど，複数形のフォルダー名にするとよいでしょう。さらにテストコードのプロジェクトなども，テストを行るソリューション全体の名前，多くの場合は製品名になると思いますが，その名前の語尾に「Tests」などとつけるとよいでしょう。 — location: [3121](kindle://book?action=open&asin=B0B35PG33Y&location=3121) ^ref-37838

---
昔はよくメソッドの中にコメントを書いていましたが，現状はメソッドの中のコメントは基本的に書かないことを推奨しています。 — location: [3131](kindle://book?action=open&asin=B0B35PG33Y&location=3131) ^ref-53580

---
コードでやっていることと，コメントが異なると数年後にそのコードを読んだプログラマーたちは，どちらを信じればよいのか混乱します。つまり，バグなのか，コメントが間違えているだけなのかで，対応が大きく変わります。コメントミスなら改修する必要はありませんが，バグであれば改修が必要になります。 — location: [3164](kindle://book?action=open&asin=B0B35PG33Y&location=3164) ^ref-37509

---
コードを読むのはC#の読めるプログラマーを想定すればよく，そもそもC#を理解できない人は読まないわけですから，コードで表現すればよく，コードの意味を日本語で説明する必要はないわけです。 — location: [3177](kindle://book?action=open&asin=B0B35PG33Y&location=3177) ^ref-39058

---
それでもコメントを書きたくなるのであれば，それはトリッキーなことをしているコードや，少し，複雑なコードなので，後で読むプログラマーや，記憶をなくした自分のために書いているはずです。この場合は，ある程度は仕方がないと思うので，絶対にコメントを書いてはいけないということではないので，局所的に，必要な場合は書いてもよいでしょう。 — location: [3181](kindle://book?action=open&asin=B0B35PG33Y&location=3181) ^ref-34909

---
分かりづらい部分はメソッド化をしてメソッド名で想いを伝える — location: [3188](kindle://book?action=open&asin=B0B35PG33Y&location=3188) ^ref-54826

---
コードを読むプログラマーが，確実に「え？」と思うだろうな・・・と思う部分は，少量のコメントを残してもよいと思います。 — location: [3296](kindle://book?action=open&asin=B0B35PG33Y&location=3296) ^ref-63639

---
コメントで悪いコードを取り繕うことはできない — location: [3299](kindle://book?action=open&asin=B0B35PG33Y&location=3299) ^ref-48535

---
コメントではなくメソッド名で表現する — location: [3310](kindle://book?action=open&asin=B0B35PG33Y&location=3310) ^ref-35273

---
メソッドは1つ3行で書くくらいの気持ちで書いた方がいいと言っている方もいます。実際にはすべて3行で書くことはできませんが，3行くらいで一塊になるようなメソッド分割を検討することで，意味のある単位でメソッド分割もできると思います。 — location: [3318](kindle://book?action=open&asin=B0B35PG33Y&location=3318) ^ref-58158

---
過去のコードと比較したい場合は，ソース管理の履歴で比較することで，簡単に見ることが出来ます。過去のコードをコメントアウトすると，コメントの合間に本番コードが挟まった状態になり，非常に可読性が悪くなります。過去のコードをコメントで残すというのは，ソース管理のない，過去の文化として，今後は廃止していただいた方がいいと思います。 — location: [3324](kindle://book?action=open&asin=B0B35PG33Y&location=3324) ^ref-18320

---
に「//TODO:登録処理未実装」などと書くことで，目で見て作業が残っていることがわかりますし，ツールとしても，タスク一覧に表示されるので，非常に便利です。 — location: [3341](kindle://book?action=open&asin=B0B35PG33Y&location=3341) ^ref-34235

---
最後にリーダブルコードのまとめをしたいと思います。 52.1 コードに想いを込める — location: [3352](kindle://book?action=open&asin=B0B35PG33Y&location=3352) ^ref-37957

---
「おばあちゃんがわかるように説明できなければ、 本当に理解したとは言えない」 アルバート・アインシュタイン — location: [3360](kindle://book?action=open&asin=B0B35PG33Y&location=3360) ^ref-3251

---
私の見解では，.NETのバージョン3.5くらいまでが一つの完成形で，.NET3.5以降で革新的なのは非同期処理が書きやすくなったという意味で，AsyncAwaitくらいではないかと思います。あとは別になくてもさほど困らない機能が多いです。新しい書き方よりも，基本文法を学んだあとは，オブジェクト指向や，デザインパターンを学ぶ方が重要でしょう。 — location: [3373](kindle://book?action=open&asin=B0B35PG33Y&location=3373) ^ref-34769

---
注意が必要なのは，開発中に，コーディングの構想をあまり変えないということです。最初の1年目と2年目でアーキテクチャーが変わっていると，ヘルプで入ってくる，派遣プログラマーも混乱します。プロジェクト初動時に，コーディングルールや，今回のようなリーダブルコード的な決まりは，しっかり決めておきましょう。 — location: [3381](kindle://book?action=open&asin=B0B35PG33Y&location=3381) ^ref-52537

---
心理的に，学んだ直後は使いたくなるので，ある程度家などで熱を冷ましてから仕事に持ち込むとよいと思います。 — location: [3389](kindle://book?action=open&asin=B0B35PG33Y&location=3389) ^ref-19836

---
サンプルソリューションを作る アプリケーション造りはある程度パターンがあります。データの取得，データの登録，設定ファイルの読み書き，データバインド，ツールの使い方など。それらのやり方を事前に検証し，小さなサンプルプログラムに，それぞれのやり方を詰め込んだソリューションを１つ作っておけば，コーディングのお作法として，プログラマー全員が技術を共有出来て，統一感のあるコーディングができるようになります。 — location: [3393](kindle://book?action=open&asin=B0B35PG33Y&location=3393) ^ref-30988

---
本書の内容はUdemyで動画解説をしている内容のため，動画で受講したい方は，Udemyをのぞいてみてください。 リーダブルコード：C#で読みやすいコードを書く50の方法 https://www.udemy.com/course/readable_code/?referralCode=6B1FDF06A945D331B474 53.1 — location: [3403](kindle://book?action=open&asin=B0B35PG33Y&location=3403) ^ref-1060

---
