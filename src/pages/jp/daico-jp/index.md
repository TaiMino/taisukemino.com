---
title: DAICOとは何か
description: >-
  2014年9月にEthereumが初めてのICOを行ってから、ICOは民主的かつオープンな、新しい資金調達方法として注目されてきました。例えば今年の初めには、LoopXというP2Pのトレーディングプラットフォームが約450万ドル調達しています。暗号通貨業界にどっぷり浸かっている人…
date: '2018-06-20T16:05:16.336Z'
keywords: []
slug: /@taisukemino/daico-jp
language: jp
translations: [ "en", "daico" ]
---

2014年9月にEthereumが初めてのICOを行ってから、ICOは民主的かつオープンな、新しい資金調達方法として注目されてきました。例えば今年の初めには、LoopXというP2Pのトレーディングプラットフォームが約450万ドル調達しています。暗号通貨業界にどっぷり浸かっている人にとって、この数字は些細なものに思われるかもしれないですが、従来の資金調達方法と比較するとこれでも大きな数字と言えます。実際2017年7月時点で、ICOによる資金調達額をVCからの資金調達額と比較すると、[エンジェル及びシード段階のインターネット企業においてはすでにICOが優っています](https://www.cnbc.com/2017/08/09/initial-coin-offerings-surpass-early-stage-venture-capital-funding.html)。

![](https://cdn-images-1.medium.com/max/800/1*r3CKE8w9NxzrCnWLvhW3oQ.png)

さらに、[ICOを含めた クラウドファンディングの調達額トップ30](https://en.wikipedia.org/wiki/List_of_highest_funded_crowdfunding_projects)を見てみると、そのうちの23つをICOが占めています(2018年6月14日時点)。Kickstarterに代表される従来のクラウドファンディングの仕組みは10年以上前からあったにも関わらず、たった4年ほど前に出てきたICOがトップ30をほぼ独占してしまっているというわけです。

ICOが革新的であるのは、スタートアップの資金調達を非中心的かつ民主的にした点です。VCやエンジェルなどの裕福な層に独占されることなく、リスクも報酬もより均等に分配されたオープンな市場で、誰でも参加することができるようになったのです。

しかし残念なことに、ICOには悪いニュースも付きまとってきました。最初にあげたLoopXというプロジェクトですが、実はこれは詐欺でした。彼らのICO後すぐにウェブサイトが閉鎖され、[投資家から約450万ドルが奪われたと報じられています](https://thenextweb.com/hardfork/2018/02/12/cryptocurrency-loopx-scam-ico/)。詐欺事件はこれら以外にも報じられており、検索すれば簡単に見つけることができます。さらにいえば、詐欺ではなくとも、約束を守らないプロジェクトもあります。これに関しては従来のクラウドファンディングの場合でも、製品が送られてこないなどのケースが散見されていますが、ICOの場合は資金が膨大なためより深刻な問題と言えるでしょう。

これらの状況を踏まえると、ICO市場は投資家にとってリスクが高く、安全な投資環境とはいえません。ではどうやって彼らの権利を護ればよいでしょう？ほとんどの政府はまだ明快な解を出せていませんが、すでに積極的な政策をとっている政府もあります。[中国の例にならって](https://techcrunch.com/2017/09/04/chinas-central-bank-has-banned-icos/)、 [韓国は全てのICOを禁止し](http://uk.businessinsider.com/ico-south-korea-bans-icos-2017-9)、また[SECも現状を楽観的には受け止めていないようです](https://techcrunch.com/2017/07/25/sec-regulators-are-coming-after-icos/)。こういった政府の市場への介入が必要なケースはあると思います。ただ一方で、市場で自主規制することができれば、革新的な試みの種を潰すことなく規制よりも柔軟かつ迅速に対応できるというメリットがあります。

ここで登場するのがDAICOです。[DAICO](https://ethresear.ch/t/explanation-of-daicos/465)は、今年の初めにEthereumの[Vitalik Buterin](https://twitter.com/vitalikbuterin)が提唱した新しいICOのモデルです。このモデルは、トークン発行主体の資金調達をサポートしながらも投資家のリスクを軽減する、ICOの自主規制のためのフレームワークです。

DAICOにおいて大事な概念は２つあります。まず最初がtap(蛇口)です。まずトークン発行主体は、ロックされた資金から毎秒いくらのweiを引き出せるか事前に決定します。この引き出せる額のことをtapといいます。それを設定した後は、自分でセール形態を選んでICOを開始することができます(キャップ付きかキャップなしか、通常のオークションかダッチオークションか、など)。ICOが終了した後、tapが設定されていることで資金の引き出しに制限がつくため、トークン発行者は資金を全て持ち出して逃げることができないというわけです。次が投票です。トークン保有者はICO後に２つの投票権を持ちます。一つ目が資金の返済、二つ目がtapの引き上げです。トークン保有者が投票の提案をし、それが過半数の賛成票を得た場合、提案に応じて資金の返済もしくはtapの引き上げがスマートコントラクトによって実行されます。資金の返済の場合は、スマートコントラクトにプールされている残りの資金が投資家に返済されます。tapが引き上げられる場合、トークン発行者はより多くのETHを引き出すことが可能になります。つまり投資家は、トークン発行主体が製品を作らなかったりした場合に、民主的にお金を取り返すことができるというわけです。逆にプロジェクトが順調である場合は、成長を加速させるためtapを引き上げることもでき、これがトークン発行者のプロジェクトへの意欲を高めるものとしても機能しているというわけです。DAICOのコアな部分は以上のようなシンプルな仕組みであり、それがDAICOの良さでもあります

DAICOは現状の市場で抱える問題を解決する大きな一歩ではあるものの、まだ残された課題もあります。それらの課題に関しては今後の投稿でカバーしていこうと思います！
