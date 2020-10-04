## 広告ブロック FAQ

脚注は少し詳しい方向けです。

<details>

<summary><strong>ブロッカー選択</strong></summary>

1. AdBlockやAdblock Plus（ABP）ではダメなのですか？
  それらでも大部分の広告は消えるでしょう。ですが、AdBlockで適用されるABP Japanese filtersは2020年2月に更新が停止しており、不具合の修正等は期待できません（ABPでは既に削除されたようです）。実は、主要な日本語サイトの広告を大体除去するだけなら、100ほどのドメインをブロックするだけでもかなりの効果があります。しかし、一部の厄介なサイトに対応するには特殊な文法で書かれたフィルタが必要です。そしてここからが重要なのですが、<strong>現在の主要な広告ブロッカーにはそれぞれ専用のフィルタ記法があり、それを無視して使うと十分な効果が得られません。</strong>今のところ、もちフィルタや豆腐フィルタといった主要な日本用フィルタが十分に性能を発揮できるのはuBlock OriginとNano Adblockerだけであり、AdGuard（iOS版とコンテンツブロッカーを除く）が許容範囲といえる互換性を持っています<sup>1</sup>。日本用のフィルタでABPと互換性があるフィルタは280blockerさんのものだけですが、こちらはモバイルサイトを対象としています。ほかに選択肢がないならともかく、より良い選択肢がある以上、わざわざAdBlockやABPを使う必要はありません。

  <sub>1: ABPでは+jsや:styleといった文法が機能しないのが致命的です。これらはページにスクリプトや特定のCSSを挿入するもので、アンチ広告ブロックや迂回広告などに対処するうえで強力な武器になります。実はスクリプトについてはABPも対応しているのですが、ABP用の文法で書く必要があります。</sub>

2.  AdBlockとAdblock Plusの違いは？
  歴史的な経緯についてはほかに優れた記事があるのでそちらに譲ります。現在はAdBlockのエンジンはAdblock Plusそのものであり、外装を付け替えただけです。小文字のAdblockについては知りません。

3. ブラウザ組込みのブロッカーはどうですか？
  1.を参照していただきたいのですが、豆腐フィルタやもちフィルタが採用しているuBlock Origin文法に対応した組込みブロッカーは、PCでは私の知る限りBraveのみです。しかし、Braveは今のところカスタムフィルタの購読ができません。Vivaldiなどにこれらのフィルタを入れても十分な性能は発揮できません。

4. Nano Adblocker（+ Nano Defender）の方がよいと聞きました。
  目的と使い方によります。もし、アンチ広告ブロックを念頭に置いておられるのなら、uBlock Originで十分です。現在、Nanoに報告されるすべてのアンチ広告ブロックはuBlock filtersかuBlock filters - Annoyancesにて対処されています。ただ、Nanoではコンテンツを妨害しないソフトアンチブロック（例：Outlook.com無料版で右側に出る「お願い」）もデフォルトで対処するのに対し、uBlock Originの場合はuBlock filters - Annoyancesの購読が必要になります。Nanoの最大の利点は強力だがリスクもあるスクリプトレットで一部の迷惑要素に対処できる点ですが<sup>2</sup>、Nano filters -  Annoyancesはほぼ海外向けです。日本語サイトを中心に見る人は、自分でルールを書くのでなければNanoを使うメリットはほぼありません。むしろ最新機能への追随が遅れることがあり<sup>3</sup>、使うフィルタによってはデメリットさえあります。ただ、NanoにはQuick reporterという問題報告ツールがあり、これは別の意味で大きなメリットといえます。ところで、アンチ広告ブロックは目立つため、初心者の方にはなにか特別な対処を要するものに思えてしまうのかもしれません。しかしこれは評判が悪かったため、近年増えてきているのはブロッカーを検知してそれを迂回する広告を再挿入するパターンです。

  追記：Nanoプロジェクトはトルコの開発者への譲渡が[ほぼ決まったようです](https://github.com/NanoAdblocker/NanoCore/issues/362)。新開発者の方向性が見えてくるまで、様子を見た方がいいかもしれません。

  <sub>2: スクリプトレットにはもともとリスクがありますが、uBlock Originではあらかじめハードコードされたスクリプトのみを使うようにしてリスクを抑えています。この点はNanoも同じです。では何が違うかというと、uBlock Originの組込みスクリプトは最悪でもページの外見や機能を壊すくらいしかできないのに対し、Nanoのスクリプトにはたとえばクリックをシミュレーションするものがあり、これを使ったフィルタの存在を知っている攻撃者が対象サイトを乗っ取れば、マルウェアのリンクを自動クリックさせることもできます。ショッピングサイトなどであればもっと直接的な悪用もできるでしょう。このため、uBlock Originではこれらのスクリプトが広告やアンチ広告ブロックへの対処にどうしても必要となるまでは採用しないと決めています。その日が来るかはわかりませんが、参考までに、同様の理由で保留されていたパラメータの書き換え機能が現在（2020年10月）Twitchの広告対策に必要なことがわかり、検討が進んでいます。</sub>

  <sub>3: DandelionSprout氏によると、最近ではdomainオプションのワイルドカードサポートへの対応遅れが問題となったようです。</sub>

5. 初心者にお勧めのブロッカーを教えてください。
  PCではブラウザ上のブロックで大抵の人は足りると思います。この場合、一番のお勧めはuBlock Originです。Macは使っていないのでわかりません。Androidだとアプリ内の広告もまれではないため、デバイス全体をカバーできた方がよいでしょう。AdGuard for Androidがもっともメジャーで、かつ機能的にも十分だと思います。[なんJ AdGuard部](https://wikiwiki.jp/nanj-adguard/)さんに記事がまとまっています。iOSは2020年現在、広告ブロッカーへの制約が最も厳しい環境で、正直な話、厄介な広告再挿入などへの根本的な対処はできません（OSの問題で、ブロッカー開発者の技術でどうにかなるものではありません。文句はAxxleに）。日本語サイトを中心にみられる場合、280blockerがベストだと思います。最近の更新でアプリ内広告にもある程度対応できるようになりました。少し詳しい人や海外サイトを本格的にみる人はいくつか選択肢がありますが、そういう人にはこんな導入記事は必要ないでしょう。ネットワーク全体をカバーするには、Pi-holeやAdGuard Homeを使う方法と、DNSキャッシュサーバーを広告ブロック機能のあるものにする簡易的な方法があります。AdGuard Homeについては280blockerさんがわかりやすい[記事](https://280blocker.net/blog/20181027/1254/)を書いてくださっています。ただしこれらはドメイン単位の「粗い」ブロックしかできないため、各デバイスのブロッカーを置き換えることはできません。

</details>

<details>

<summary><strong>uBlock Origin - 拡張機能</strong></summary>

6. ブロックのカウンターが上がり続けます。
  [何も問題ありません](https://old.reddit.com/r/uBlockOrigin/comments/itw503/ubo_google_docs_high_cpu_spikes_and_blocked/g5l5yjd/)。どういうわけか、カウンターが上がり続けるとパフォーマンスに悪影響があると信じている人が多いようです。確かに、ブロックされた場合にものすごい勢いでリクエストを送り続けるケースはあり、フリーズしたりCPU使用率が跳ね上がったりしますがこれはそのサイトの問題です。1秒に1つ程度のカウンター上昇なら何も影響ありません。どうしても信じられないなら、開発者ツールからパフォーマンスレコードをとって報告してください。証明できたらuBlock Origin史上初の発見です。

7. Chrome/EdgeでuBlock Extraは必要なのでしょうか？
  [もしかしたら役に立つこともあるかもしれない](https://forums.lanik.us/viewtopic.php?f=106&t=43736)程度です。私自身は有用性を確認できませんでした。

</details>

<details>

<summary><strong>uBlock Origin - フィルタ</strong></summary>

8. クラス名が毎回ランダムに変わる要素はどう消せばいいのでしょうか？/「要素をブロック」が機能しません。

  「要素をブロック」はフィルター作者のための補助ツールです。１つ２つならともかく、同機能で自動生成されたルールをたくさん作るのはお勧めしません。クラス名が変わる場合、まずはクラス名以外で使える属性がないか、開発者ツールで見てみるのがよいと思います。もしなければ、該当要素の親や子孫で安定した属性を持つものや、使えそうなテキストを含むものがないか探します。そうしたものがあれば（必ずと言っていいほどあります）、あとは[Procedural cosmetic filters](https://github.com/gorhill/uBlock/wiki/Procedural-cosmetic-filters)を使うだけです。初心者であれば`:has`, `:has-text`と`:upward`だけでも十分でしょう。

9. 効率的な非表示ルールの書き方を教えてください。

  細かいTipsはありますが、一番大切なのは[最小マッチング](https://github.com/gorhill/uBlock/wiki/Procedural-cosmetic-filters#important)を意識することです。通常の非表示ルールでもそうですが、Procedural cosmetic filtersにおいては[とくに](https://github.com/uBlockOrigin/uAssets/commit/8fd12b060148cfde8e53e70012733b089abf65bc#commitcomment-39037147)[重要](https://old.reddit.com/r/uBlockOrigin/comments/j4ewg7/best_practice_hasx_or_xupward/)です。

10. お勧めのフィルタ構成を教えてください。

  フィルタ構成についてはこれが正解といえるものはなく、各自で調べて自身の好みに合うものを選択するしかありません。ただ、間違いといえるものはあります。フィルタを解釈して評価できる人はまれなため、インターネット上には主観的な使用感や信念にもとづいた「おすすめ」がたくさん転がっています。たとえば、Adblock Warning Removal Listは、最近になってようやく意味のないリストという認識が広まってきたようですが、数年前まであちこちでアンチ広告ブロック対策に推奨されていました。ここまでひどくはないものの、あまり正しく理解されていなさそうなリストとしてFanboy's Enhanced Tracking Listが挙げられます。このリストの最大のパートは許可ルールによるブロッカー検知回避なのですが、ちょっと大雑把すぎて検知と関係ない広告スクリプトまで許可してしまっています。これらは基本的にイニシエイターで、最終的な広告は別のルールでブロックされますが、不要なスクリプトを走らせてまで一部の検知を回避することを、同リストの利用者が求めているかは疑問です<sup>3</sup>。残りの部分もすべてがトラッキング対策ではなく、迷惑要素なども含まれています。あまり意味のないリストについていえば、NoCoinが挙げられるでしょう。コインマイニング自体、絶滅してはいないものの下火ですが、NoCoinでブロックされるものはほぼすべてEasyPrivacy + uBlock filters - Resource abuseでカバーされています。

  一般的なアドバイスとしては、初心者の方はともかく購読しすぎに注意することです。日本用フィルタの複数購読、ソーシャルや迷惑要素用フィルタの多重購読はお勧めしません。おそらく、たくさん購読するとそれだけ多くブロックしてくれるという考えからなのでしょうが、これは必ずしも正しくありません。また、フィルタによる不具合は天災のようなもので、普段はあまり遭遇しませんが忘れたころにやってきます。多く購読すればするほど、メリットは薄くなっていき、不具合の確率ばかり高まります。それにいくらuBlock Originでも、非表示フィルタやトークン化不能正規表現の無駄が多量に積もればパフォーマンスに影響しかねません。

  もう少し具体的に、PCの場合なら（あくまで参考程度にお願いします）
  - 内製フィルタ：基本的にデフォルトのまま。ほかのフィルタに比べると不具合の率が少なく（ないわけではない）、日本語サイト利用者でもメリットは大きいです
  - 広告：海外サイトをよく見る人はEasyListを維持。日本のサイトしか見ないなら、お好みで外してもよい
  - プライバシー：トラッキングを気にしない人、または雪フィルタ使用者は外してもよい。気にする人で雪以外の日本語フィルタ使用なら、平均的なブロック性能が高いが不具合も多いEasyPrivacyを維持するか、不具合は少ないが漏れも多いAdGuard Tracking Protectionから選択
  - マルウェアドメイン：お好みで。デフォルトのOnline Malicious URL Blocklistはブラウザのセキュリティ機能（Google Safe Browsing）とデータ共有しており、大部分はブラウザでブロックされます
  - 迷惑系：ソーシャルボタンを消したい人はAdGuard Social Mediaを追加してもよいでしょう。ただし、もちおさんが提供されている[ことりフィルタ](https://eeii0a5l.github.io/mochifilter_homepage/kotori.html)やこちらで提供しているあられフィルタも検討してみてください（あられはAdGuard Social Mediaとの互換性を意識して作っており、併用も可能です）。ほかの迷惑要素についても同じく、AdGuard Annoyances, [ねぎフィルタ](https://eeii0a5l.github.io/mochifilter_homepage/negi.html), みぞれフィルタからの選択をお勧めします。ちょっと特殊なのがuBlock filters - Annoyancesで、これは主にソフトアンチ広告ブロックと右クリック/コピー禁止系への対策になります。Fanboy系は不具合の率が高く、初心者にはお勧めしません
  - 多目的：デフォルトのPeter Lowe'sはフィルタ数のわりに良い仕事を（主に海外サイトで）してくれているのですが、たまに誤爆することがあります。日本のサイトを中心に見るなら好みで外してもよい
  - 地域、言語：英語、日本語以外のサイトをよく見る人はその言語のフィルタを追加。日本語については別途日本用フィルタを購読するのであればAdGuard Japaneseを外す
  - カスタム：お好みでもちフィルタ、豆腐フィルタ、雪フィルタの中から一つを追加

  フィルタ構成とは別に、中級者以上の方であれば「汎用的な要素隠蔽フィルターを無視する」はお勧めできるオプションです。パフォーマンスの向上に加え、誤爆やアンチ広告ブロックへの遭遇率を下げることもできます。その代わり広告枠やテキスト広告が隠し切れないケースも出てきます。

  <sub>3: 一般非表示が有効なら、結局検知されてしまうことが多いです。</sub>

11. EasyListやEasyPrivacyは不具合が多いと聞きます。
  事実です。私もこれまでいろいろな形で、おそらく数十件は報告しています。なお、ルールが多いから不具合が多いわけではありません。80対20の法則ではありませんが、大部分のルールは不具合と無関係な一方、誤爆しやすいルールというのがあります。雪フィルタではこの点を逆手にとり、誤爆しやすいルールをなるべく外すことにしました<sup>4</sup>。またアンチ広告ブロックを惹起しやすいという議論も聞きます。これは間違ってはいませんが、「それほど違わない」という印象です。もっとも一般的なトリガーは非表示、とくに`##.adsbygoogle`ですが、これは主要な日本用フィルタすべてに含まれています。EasyList側も当然気づいており、[変更してみたり](https://github.com/easylist/easylist/commit/216979ef1f3643405c9d2dba077807e114def71c)（失敗）、uBlock Origin限定ですが`*##.adsbygoogle:style(width:1px!important;height:1px!important;)`を検討してみたり（レイアウトが崩れるケース有り、断念）、世界的なアンチブロックの潮流についてはむしろ日本用フィルタより対策が進んでいるかもしれません。もちろん`/adspace.`など日本で多いトリガーもありますが、それを言い出すと日本用フィルタでのみトリガーされるものもあります。ところで、不具合が多い理由の一つは日本のユーザーからの報告がほとんどないことです。EasyListでなくとも、日本では280blockerさんを唯一の例外として、フィルタ作者への報告自体がまばらな印象です。すべてのユーザーが不具合を自己修正できるとは思えないため、ブロックをそのサイトで無効にしたり、dynamic filteringの緑で上書きしたりといった対処をされている方が多いのではないかと思います。フィルタ作者はそういった「荒療治」より効果的な対処ができますし、あなたの報告がほかの多くのユーザーを助けるかもしれません。ぜひ積極的な報告をお願いします。なお、当サイトおよびしたらばの[簡易報告掲示板](https://jbbs.shitaraba.net/bbs/read.cgi/internet/25463/1598352715/)では、EasyList等外部フィルタ併用時の不具合も受けつけ、可能であれば関係先にフィードバックを送ります。

  <sup>4: imasdkなど、メリットとの兼ね合いから誤爆が多くても採用したルールもあります。</sup>

</details>

<details>

<summary><strong>当サイトのフィルタ</strong></summary>

12. 雪フィルタの中を見ると、海外サイト用のルールが結構あります。どのようなサイトが対象なのでしょうか？
  New York Timesなどの大手英語メディアや日本人利用者が多い海外マンガ、アニメ、あるいはポルノサイトに加え、以下のようなサイトを対象にしています：
  - 他の日本用フィルタで個別対応されているもの
  - 日本語のブログや記事などで紹介されている海外サイトで、ある程度トラフィックが高そうなもの
  - 特定のテーマに興味を持つ日本人が検索しそうな単語でGoogle検索したとき、検索上位に出てくるサイトでトラフィックが高そうなもの
  - 上記に該当するサイトの姉妹/系列サイトや、直接リンクされているサイトの一部
  例外は短縮プレミアムリンク系です。日本でメジャーなものは`sh.*`, `shorten.*`, `ouo.*`などだと思いますが、目的地につくまでに様々な短縮リンクをたらい回しにされることがあるため、インターフェースが英語のものについてはある程度網羅的に対応しています。

  英語以外ではロシアと中国/広東語のサイトがやや多いですが、これらの言語をよく利用する方には到底足りません。EasyListや各言語用フィルタを使用してください。

13. 雪フィルタでCNAMEトラッカー（ファーストパーティートラッカー）はブロックできますか？
  はい、ほとんどはブロックされます。大雪併用ならほぼすべてといってもよいです。一部メディアが騒ぎ立てたため、CNAMEトラッカーをなにか特別なもののように思っている人がいるようですが、実際はEasyPrivacyなどは以前からとくに区別せずブロックしていました。日本では豆腐さんもgenieesspvのCNAMEトラッカーを以前よりブロックされています。Eulerianが少し厄介だったのはCNAMEの利用そのものではなく、CNAMEとランダムにみえるサブドメインの組合せでした。多くのCNAMEトラッカーは、たとえば`smetrics`といった、決まったサブドメインを使います。そしてなにも`||smetrics.`のようなルールを使わずとも、一般ルールで簡単に全部ブロックできます（誤爆があるため雪では一部しか採用していません）。なお、ファーストパーティートラッカーという呼称が使われることもありますが、CNAMEトラッカーには純粋なサードパーティーのものも少なくないですし、一部メディアが書いたような「ファーストパーティーだとブロックしにくい」などということもありません。ちなみに、`ad-cloud.jp`と`genieesspv.jp`の[CNAMEトラッカー](https://ln2.sync.com/dl/fa3ee4fc0/hbx7nuxm-u93hrvur-6pqd7ksx-4a43i6dq/view/text/10872149110008)[一覧](https://ln2.sync.com/dl/37297af50/view/text/10550679950008#qm9yf8hs-vk8m52pe-5ruzkqn9-ssa6cv2b)を公開しています（ここに含まれるすべてが実際に使われているわけではありません）。他に`a8.net`, `ebis.ne.jp`, `omtrdc.net`などのCNAMEトラッカー一覧もありますが、`sync.com`の共有リンク数制限により公開を取りやめました。ただしこれらはデータが少し古く、リストに含まれていないトラッカーも確認しています。

14. なにか言い残したことは？
  AdGuardに関する某掲示板で私を指名するのはやめてください。ちゃんと報告していただければAdGuardチームの誰かが対処するはずです。私を含めチームの何名かはただの無償ボランティア<sup>5<sup>で、チームの誰かから依頼された場合は別として、空き時間で適当に目についた問題に対処しているだけです。ところで、スクリーンショットのみで説明がなく、何をしてほしいのか不明瞭な報告がたまにあります。大抵、チームから呼ばれて私がエスパーするはめになります。日本語で構いませんので（スクリーンショット中に日本語を入れるのは控えてください）、一言説明を入れてください。できればスクリーンショットにもマーキングをしていただけるとなおよいです。

<sub>5: 永久ライセンスはもらえますが、公式にある５件程度でいいというのはウソです。ライセンス目当てにContributorを目指すのはやめた方がいいでしょう。ですがContributorは欲しいです、切実に。</sub>

</details>

### 謝辞

このFAQの作成に当たっては、@280blockerさんから貴重なご意見をいただきました。ここに感謝申し上げます。
（元々見ていただくことを想定していたわけではなく、たまたま別件で話していたときにタイミングがあったため、ご意見をいただくことができました。間違い等の文責はすべて@Yuki2718にあります）