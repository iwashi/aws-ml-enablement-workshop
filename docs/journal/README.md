<p align="center">
  <img src="images/top.jpg" width=300>
  <h2 align="center">
    データサイエンスを活用するプロダクトマネージャーを訪ねて
  </h2>
</p>


本記事では、機械学習やデータをプロダクトで活用するときの Q&A をまとめています。質問 (Q) の例としては、「機械学習を使った機能の発見から実装までどんな流れで進めればいいですか ? 」などです。回答 (A) は、 [Product School](https://www.youtube.com/@ProductSchoolSanFrancisco) で公開されている世界各国の著名なプロダクトマネージャーの方のプレゼンテーションやインタビューからまとめています。 Product School は、グローバルのプロダクトマネージャーコミュニティです。

本記事に掲載しているプロダクトマネージャーの発言は、会社を代表しているとは限らない点にご注意ください。新しい質問の追加や誤字等の修正があれば [Issue](https://github.com/aws-samples/aws-ml-enablement-workshop/issues) にてご連絡ください。

海外のプロダクトマネージャーがどんな職歴や経歴なのか、あまり知られていないと思うので判別可能な限り LinkedIn のプロフィールへのリンクを載せています。なお、肩書は当時のものです。

**新着 Q&A を見逃したくない方は[トップページ](https://github.com/aws-samples/aws-ml-enablement-workshop)で Star すればお気に入りから参照できます！**。Watch をすることで GitHub 上で通知を受け取ることもできます。

![star_and_watch.png](./images/star_and_watch.png)

## Q&A 一覧

* 機械学習を使った機能の発見から実装まではどんな流れですか ?
* プロダクトの中で機械学習やデータサイエンスはどんな役割を果たしていますか ?
* 顧客から信頼される AI 機能を作るために気を付けるべきことは ? 
* AI の登場で人間のプロダクトマネージャーは不要になりますか ?
* データサイエンティストの仕事をどのように定義すればよいですか ?

## Q&A

### 機械学習を使った機能の発見から実装まではどんな流れですか ?

**Spotify の Product Leader [Derya Isler](https://www.linkedin.com/in/deryaisler/details/experience/) の場合**

ユーザーからの要望があったとき ( Mr.Children が好きなので似た曲を聞きたい、など ) 、次の図のように 1) プロダクトの実現したい体験に沿うか、 2) 成功を計測できるか、 3) より良い体験を創るのに必要なことか / スケールするか、 4) データはあるか/偏りはないか、 5) 求める精度を達成できるか、 6) ユーザーへどのように提供するか、の 6 つのステップで検討している。

![spotify_derya_Isler](./images/spotify_derya_Isler.png)

([Webinar: Managing Machine Learning Products by Spotify Product Leader, Derya Isler](https://youtu.be/EhlHKhQv0Qg?t=1343) (2020) より引用)

### プロダクトの中で機械学習やデータサイエンスはどんな役割を果たしていますか ?

**Uber の Product Lead [Tanvi Surti](https://www.linkedin.com/in/tanvisurti/) の場合**

前提として、 Software 型のプロダクトと、 Marketplace 型のプロダクトは異なる。 Uber は Marketplace のプロダクトであり、そこでは需要者と供給者のマッチングが肝になる。 Software 型ではクリック数やユーザー数などサービス上で計測可能な値を重視するが、 Marketplace では市場自体を成立させる需要者と供給者、それらを結び付けるアルゴリズムを重視する。だいたい 50% のデータサイエンス (ML) と、 50% の Ops (実行) で運営されている。

([What is Marketplace Product Management by Uber Product Manager](https://youtu.be/t4cnrwu465Q?t=2131) (2019) より)

**[The Lean Product Playbook](https://leanproductplaybook.com/) の著者 [Dan Olsen](https://www.linkedin.com/in/danolsen98/) の場合**

定量、定性の分析は Product Market Fit (PMF) とその先の成長に向けたフェーズの課題を解決するのに不可欠である。プロダクトのフェーズは PMF の前段階として 1) Before release, 2) After release, PMF した後として 3) After PMF の 3 段階に分けることができる。 3) に至るため PMF がまず目指すべき点であり、 PMF しているかどうかのシグナルは顧客の利用継続率を表す AARRR モデルで言うところの **Retention** から得られる (下図左)。 1) の段階では想定顧客の要求や感情など内面を知るための直接的なインタビューなどが有効であり、 2) の段階では 1) の定性的な手法に加え Release したプロダクトから定量的なデータを取るユーザーテストなどが有効になる (下図右)。 3) のフェーズでは定量的な分析が中心となり、顧客サーベイや A/B テストが主になる。

| AARRR モデル   | ログイン行動分析例 |
| ---- | ---- |
|  ![lean_product_playbook_dan_olsen_001](./images/lean_product_playbook_dan_olsen_001.png)  |  ![lean_product_playbook_dan_olsen_002](./images/lean_product_playbook_dan_olsen_002.png)  |


([Webinar: Actionable Advice for Integrating Quantitative and Qualitative Insights by Heap](https://youtu.be/ZYJij0RsQeg0) (2023) より引用)


### 顧客から信頼される AI 機能を作るために気を付けるべきことは ? 

**Shopify の Senior Product Manager [Ellen Dunne](https://www.linkedin.com/in/ellendunne/) の場合**

対話型 UI 構築に際しては、単一目的に絞る、提案型にする、フィードバックを得るなど 7 つの構築指針が必要。 UI/UX として挨拶、わからない場合の回答方法など 5 つの構成要素を実装する必要があり、それが意図したとおり動いているか、計測するメトリクスが必要。詳細は [Shopify プロダクトマネージャーによる対話型UX構築のポイント](https://note.com/piqcy/n/n63f3f3dd9539) をご参照。

([The Future is Conversational by Shopify Sr. PM](https://www.youtube.com/watch?v=0epxFiYhBQA) (2018) より)

**KAYAK の Director of Global Mobile Monetization [Chris Butler](https://www.linkedin.com/in/chrisbu/) の場合**

機械学習は目標値を最大/最小化するよう学習するが、最適な体験は数値だけでなくプロトタイプを通じたメンタルモデルの観察から理解する必要がある。 AI のエラーは想像以上に不信感を生むため、合目的な利用と説明性が不可欠。

([#ProductCon NYC: How to Build Trustworthy AI Products by Philosophie Director of AI](https://www.youtube.com/watch?v=DIwyKwPzrjc) (2018) より)

### AI の登場で人間のプロダクトマネージャーは不要になりますか ?

**Amazon の Senior Product Manager [Siddharth Ilangovan](https://www.linkedin.com/in/sid-i/) の場合**

次のように Associate PM、PM、Senior PM、Product Lead の 4 段階で役割とスキルが定義でき、 PM が行う PRD 執筆やサーベイは AI への委譲が進む一方、 Senior や Product Leader が担う機会の発見やリーダーシップなどは人間力が必要。

|  PM の種別  | PM の役割 |
| ---- | ---- |
|  ![amazon_siddharth_llangovan_001](./images/amazon_siddharth_llangovan_001.png)  |  ![amazon_siddharth_llangovan_002](./images/amazon_siddharth_llangovan_002.png)  |

Associate PM はユーザーストーリーを課題や機能に落とし込むこと、 PM は新しい機能のリリース、 Senior PM は新しいプロダクトのリリース、 Product Leader は複数プロダクトのポートフォリオの実現に責任を持つイメージ。

([Webinar: Will AI Make Human Product Managers Obsolete? by Amazon Sr PM, Siddharth Ilangovan](https://youtu.be/7RmHV-XYM48?t=354) (2023) より)

### データサイエンティストの仕事をどのように定義すればよいですか ?

**Airbnb の Director, Head of Data Science [Elena Tej Grewal](https://www.linkedin.com/in/elena-grewal/) の場合**

Airbnb では、データサイエンティストを Analytics 、 Inference 、 Algorithms の 3 つの職種に分けている。 Analytics はモニタリングするビジネスメトリクスを決めてダッシュボードの作成や可視化を通じビジネス状況を表すこと、 Inference は統計検定や因果推論によりデータから意思決定の支援を行うこと、 Altorithms は機械学習アルゴリズムを用いてデータから Airbnb のサービスやプロセスを改善することを主な役割とする。このように役割を分けた背景には、 2015 年から 2018 年にかけてある時はデータ分析、ある時は機械学習など異なるビジネスニーズに応じて採用を続けた結果、職掌の異なるデータサイエンティストが混在し何をなすべきか個々人が自信を持てなくなったことがある。そのため、会社にとってのデータサイエンスの価値を提議しそれぞれに専門的にコミットするロールを 3 つ提議した。現在 (2018年時点) では Analytics が 34% 、 Inference が 47% 、 Algorithms が 28% となっている。ただ、組織が小さい頃は分ける必要がないと思う。Airbnb では 2015 年の 30 人の段階では分けておらず、 2018 年に 100 人を超えてからロールを定義した。

([One Data Science Job Doesn’t Fit All](https://www.linkedin.com/pulse/one-data-science-job-doesnt-fit-all-elena-grewal/) (2018) より)