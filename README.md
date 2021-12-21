# CrossSum

This repository contains the code, data, and models of the paper titled [**"CrossSum: Beyond English-Centric Cross-Lingual Abstractive Text Summarization for 1500+ Language Pairs"**](https://arxiv.org/abs/2112.08804).


## Table of Contents

- [CrossSum](#crosssum)
  - [Table of Contents](#table-of-contents)
  - [Datasets](#datasets)
  - [Models](#models)
  - [Benchmarks](#benchmarks)
  - [Language-agnostic Summary Evaluation](#language-agnostic-summary-evaluation)
  - [Training & Evaluation](#training--evaluation)
  - [License](#license)
  - [Citation](#citation)


## Datasets
  
***Disclaimer: You must agree to the [license](#license) and terms of use before using the dataset.***

We are currently releasing a preliminary version of the dataset which has been used for the experiments in the paper. Currently the dataset contains a good amount of data leakage from the training set to the evaluation sets. We will release a cleaner version of the dataset shortly.

An example article-summary pair from the `Japanese-Bengali` pair of the ***CrossSum*** dataset with corresponding English translations is given below:

![Example datapoint](figs/crossum_example.png)

The corresponding complete datapoint in the dataset is as follows:
```
{
    "source_url": "https://www.bbc.com/japanese/53074000",
    "target_url": "https://www.bbc.com/bengali/news-53064712",
    "summary": "বিজ্ঞানীরা বলছেন ডেক্সামেথাসোন নামে সস্তা ও সহজলভ্য একটি ওষুধ করোনাভাইরাসে গুরুতর অসুস্থ রোগীদের জীবন রক্ষা করতে সাহায্য করবে।",
    "text": "ミシェル･ロバーツ、BBCニュースオンライン健康担当編集長 英オックスフォード大学の研究チームによると、低用量のデキサメタゾンは新型ウイルスとの戦いで画期的な突破口になる。 新型コロナウイルスに対し、様々な既存の治療法の効果を試す世界的規模の臨床試験の一貫として、デキサメタゾンが試された。 その結果、人工呼吸器を必要とする重症患者の致死率が3割下がり、酸素供給を必要とする患者の場合は2割下がった。 新型ウイルスのパンデミック（世界的流行）の初期からイギリスでデキサメタゾンを治療に使用していた場合、最大5000人の命が救えたはずだと研究者たちは言う。 さらに、新型コロナウイルスによる感染症「COVID-19」の患者が多く出ている貧しい国にとっても、安価なデキサメタゾンを使う治療は大いに役立つと期待される。 重症者の致死率が大幅に下がる イギリス政府は20万人分の投与量を備蓄しており、国民医療制度の国民保健サービス（NHS）で患者への使用を開始する方針を示した。 ボリス･ジョンソン英首相は「イギリス科学界の素晴らしい成果」を歓迎し、「たとえ感染の第2波が来ても備蓄が足りるよう、数を確保するための措置をとった」と述べた。 イングランド首席医務官クリス・ウィッティー教授は、「COVID-19にとってこれまでで一番重要な臨床試験結果だ。手に入りやすく安全でなじみのある薬によって、酸素供給や人工呼吸器が必要な人の致死率が大幅に下がった。（中略）この発見が世界中で人命を救う」と評価した。 ＜関連記事＞ 新型コロナウイルスに20人が感染した場合、19人は入院しないまま回復する。入院する人もほとんどは回復するものの、重症化して酸素供給や人工呼吸器を必要とする人もいる。 デキサメタゾンはこうした重症患者の治療に効果があるもよう。 新型ウイルスに感染した患者の体内では、ウイルスと戦う免疫系が暴走することがある。その免疫系の過剰反応による体の損傷を、デキサメタゾンが緩和するものとみられる。 「サイトカイン・ストーム」と呼ばれる免疫系の過剰反応が、患者の命を奪うこともある。 デキサメタゾンはすでに抗炎症剤として、ぜんそくや皮膚炎など様々な症状の治療に使われている。 初めて致死率を下げる薬 オックスフォード大学が主導する臨床試験は、約2000人の入院患者にデキサメタゾンを投与。それ以外の4000人以上の患者と容体を比較した。 人工呼吸器を使用する患者については、死亡リスクが40％から28％に下がった。 酸素供給する患者は、死亡リスクが25％から20％に下がった。 研究チームのピーター・ホービー教授は、「今のところ、致死率を実際に下げる結果が出たのは、この薬だけだ。しかも、致死率をかなり下げる。画期的な突破口だ」と話した。 研究を主導するマーティン・ランドレイ教授によると、人工呼吸器を使う患者の8人に1人、ならびに酸素供給治療を受ける患者の20-25人に1人が、デキサメタゾンで救えることが分かったという。 「これはきわめて明確なメリットだ」と教授は言う。 「最大10日間、デキサメタゾンを投与するという治療法で、費用は患者1人あたり1日約5ポンド（約670円）。つまり、35ポンド（約4700円）で人ひとりの命が救える」 「しかもこれは、世界中で手に入る薬だ」 状況が許す限り、新型コロナウイルスで入院中の患者にはただちに投与を開始すべきだと、ランドレイ教授は促した。 ただし、自宅で自己治療するために薬局に買いに行くべきではないと言う。 デキサメタゾンは、呼吸補助を必要としない軽症の患者には効果がないもよう。 3月に始動した新型コロナウイルス治療薬の無作為化臨床試験「リカバリー・トライアル」は、抗マラリア薬「ヒドロキシクロロキン」も調べたものの、心臓疾患や致死率の悪化につながるという懸念から、ヒドロキシクロロキンについては試験を中止した。 一方で、感染者の回復にかかる時間を短縮するとみられるレムデシビルは、すでにNHSの保険対象になり治療現場で使われている。 ＜解説＞ ファーガス・ウォルシュBBC健康担当編集委員 COVID-19の死者を減らすと初めて立証された薬は、高価な新しい薬ではなく、古くからずっと使われてきた、きわめて安いステロイド剤だった。 世界中の患者が直ちにその恩恵を受けることになるので、これは歓迎すべき発見だ。 この臨床試験の最新成果がこれほど急いで発表されたのは、そのためだ。とてつもない影響を世界中にもたらすので。 デキサメタゾンは1960年代初めから、関節リウマチやぜんそくなど、幅広い症状の治療に使われてきた。 これまでは、人工呼吸器を必要とするCOVID-19患者の半数が亡くなってきた。その致死率を3割減らすというのは、絶大な効果だ。 集中治療室では点滴で投与する。もう少し軽症な患者には、錠剤で与える。 これまでのところ、COVID-19患者に効果があると証明された薬は、エボラ治療薬のレムデシビルだけだった。 レムデシビルは症状の回復期間を15日から11日に短縮する。しかし、致死率を下げると言えるだけの証拠は出ていなかった。 デキサメタゾンと異なり、レムデシビルは数の少ない新薬で、薬価もまだ公表されていない。"
}
```

The dataset files are organized in `.jsonl` format  i.e. one JSON per line. **Download the dataset from [here](https://drive.google.com/file/d/1GeMSiUsMW7X156FRXa8GaiihfA17psoO/view?usp=sharing).**


No. of total examples for each language pair are as follows:


Language (ISO 639-1-Code) | am | ar | az | bn | my | zh-CN | zh-TW | en | fr | gu | ha | hi | ig | id | ja | rn | ko | ky | mr | ne | om | ps | fa | pcm | pt | pa | ru | gd | sr | sr | si | so | es | sw | ta | te | th | ti | tr | uk | ur | uz | vi | cy | yo 
-----|-----|-----|-----|-----|-----|-----|-----|-----|-----|-----|-----|-----|-----|-----|-----|-----|-----|-----|-----|-----|-----|-----|-----|-----|-----|-----|-----|-----|-----|-----|-----|-----|-----|-----|-----|-----|-----|-----|-----|-----|-----|-----|-----|-----|-----
am | -- | 634 | 96 | 244 | 91 | 150 | 146 | 1548 | 334 | 138 | 199 | 296 | 27 | 423 | 261 | 381 | 218 | 90 | 192 | 297 | 30 | 173 | 390 | 179 | 238 | 152 | 293 | 0 | 332 | 365 | 54 | 283 | 282 | 352 | 338 | 282 | 101 | 246 | 352 | 277 | 325 | 37 | 227 | 1 | 50 
ar | 634 | -- | 718 | 716 | 614 | 2904 | 2620 | 9776 | 991 | 383 | 699 | 3263 | 76 | 5796 | 1158 | 792 | 656 | 280 | 472 | 782 | 8 | 2219 | 4154 | 385 | 2336 | 466 | 5123 | 1 | 1015 | 1074 | 288 | 979 | 3566 | 1087 | 1147 | 761 | 326 | 24 | 3729 | 3239 | 4648 | 362 | 2375 | 33 | 120 
az | 96 | 718 | -- | 262 | 76 | 314 | 250 | 1258 | 187 | 181 | 122 | 741 | 24 | 1135 | 240 | 174 | 147 | 209 | 169 | 227 | 1 | 228 | 816 | 77 | 693 | 163 | 2163 | 3 | 288 | 278 | 113 | 342 | 680 | 514 | 486 | 220 | 123 | 2 | 1527 | 1424 | 971 | 202 | 729 | 34 | 37 
bn | 244 | 716 | 262 | -- | 124 | 240 | 205 | 1402 | 307 | 540 | 210 | 1435 | 28 | 1070 | 301 | 257 | 321 | 126 | 557 | 667 | 1 | 270 | 737 | 110 | 753 | 525 | 780 | 0 | 525 | 528 | 143 | 373 | 650 | 456 | 869 | 720 | 216 | 3 | 822 | 656 | 1450 | 85 | 495 | 43 | 60 
my | 91 | 614 | 76 | 124 | -- | 338 | 283 | 679 | 83 | 74 | 70 | 492 | 11 | 714 | 152 | 94 | 108 | 50 | 73 | 150 | 2 | 219 | 421 | 37 | 217 | 74 | 499 | 0 | 100 | 108 | 79 | 76 | 412 | 77 | 168 | 140 | 67 | 2 | 399 | 337 | 553 | 57 | 403 | 3 | 9 
zh-CN | 150 | 2904 | 314 | 240 | 338 | -- | 44684 | 5068 | 304 | 138 | 135 | 1028 | 33 | 2462 | 1084 | 204 | 399 | 134 | 170 | 235 | 11 | 480 | 954 | 128 | 1145 | 176 | 2126 | 0 | 381 | 469 | 130 | 279 | 1874 | 343 | 385 | 280 | 230 | 11 | 1123 | 1346 | 1224 | 150 | 1539 | 25 | 38 
zh-TW | 146 | 2620 | 250 | 205 | 283 | 44683 | -- | 4816 | 279 | 108 | 115 | 792 | 31 | 1958 | 970 | 178 | 361 | 120 | 146 | 196 | 16 | 409 | 715 | 118 | 973 | 142 | 1655 | 0 | 335 | 418 | 116 | 242 | 1621 | 289 | 326 | 247 | 199 | 11 | 829 | 1091 | 947 | 124 | 1233 | 17 | 34 
en | 1548 | 9776 | 1258 | 1402 | 679 | 5068 | 4816 | -- | 1856 | 797 | 921 | 4050 | 132 | 9817 | 3674 | 1877 | 1817 | 478 | 990 | 1538 | 80 | 1460 | 4500 | 1120 | 4416 | 1162 | 8536 | 161 | 3767 | 3904 | 518 | 2171 | 6926 | 2676 | 2864 | 1943 | 1021 | 123 | 5167 | 6327 | 5850 | 434 | 4473 | 2906 | 224 
fr | 334 | 991 | 187 | 307 | 83 | 304 | 279 | 1856 | -- | 191 | 494 | 599 | 98 | 1027 | 264 | 717 | 254 | 118 | 215 | 313 | 6 | 153 | 611 | 416 | 963 | 215 | 820 | 2 | 538 | 565 | 88 | 483 | 1007 | 866 | 402 | 355 | 164 | 4 | 832 | 705 | 738 | 67 | 437 | 45 | 162 
gu | 138 | 383 | 181 | 540 | 74 | 138 | 108 | 797 | 191 | -- | 127 | 5190 | 29 | 657 | 167 | 165 | 230 | 82 | 2025 | 545 | 0 | 202 | 487 | 59 | 496 | 2119 | 506 | 0 | 307 | 298 | 124 | 233 | 477 | 276 | 1654 | 1921 | 120 | 2 | 575 | 477 | 1640 | 59 | 434 | 20 | 43 
ha | 199 | 699 | 122 | 210 | 70 | 135 | 115 | 921 | 494 | 127 | -- | 451 | 217 | 932 | 150 | 493 | 130 | 58 | 144 | 235 | 6 | 208 | 493 | 528 | 388 | 129 | 493 | 1 | 239 | 248 | 45 | 386 | 458 | 583 | 266 | 217 | 77 | 9 | 500 | 390 | 506 | 57 | 358 | 30 | 370 
hi | 296 | 3263 | 741 | 1435 | 492 | 1028 | 792 | 4050 | 599 | 5190 | 451 | -- | 56 | 5688 | 536 | 449 | 467 | 188 | 3843 | 1401 | 4 | 1450 | 5444 | 142 | 6689 | 4006 | 4457 | 3 | 765 | 714 | 446 | 702 | 2806 | 864 | 3675 | 3748 | 300 | 7 | 3766 | 3938 | 16118 | 308 | 3759 | 89 | 62 
ig | 27 | 76 | 24 | 28 | 11 | 33 | 31 | 132 | 98 | 29 | 217 | 56 | -- | 112 | 21 | 103 | 24 | 13 | 40 | 35 | 4 | 10 | 42 | 272 | 60 | 26 | 73 | 0 | 38 | 47 | 8 | 76 | 77 | 150 | 46 | 41 | 17 | 7 | 78 | 69 | 48 | 11 | 60 | 7 | 321 
id | 423 | 5796 | 1135 | 1070 | 714 | 2462 | 1958 | 9817 | 1027 | 657 | 932 | 5688 | 112 | -- | 1274 | 1001 | 764 | 323 | 707 | 1123 | 12 | 1297 | 3973 | 289 | 4762 | 643 | 7416 | 8 | 1352 | 1344 | 444 | 1301 | 4585 | 1922 | 1809 | 1052 | 572 | 5 | 5785 | 4855 | 6606 | 413 | 4921 | 177 | 168 
ja | 261 | 1158 | 240 | 301 | 152 | 1084 | 970 | 3674 | 264 | 167 | 150 | 536 | 21 | 1274 | -- | 353 | 756 | 137 | 255 | 420 | 3 | 210 | 1048 | 132 | 737 | 215 | 1434 | 2 | 562 | 606 | 95 | 356 | 959 | 443 | 554 | 389 | 294 | 3 | 1238 | 955 | 722 | 50 | 879 | 21 | 23 
rn | 381 | 792 | 174 | 257 | 94 | 204 | 178 | 1877 | 717 | 165 | 493 | 449 | 103 | 1001 | 353 | -- | 264 | 100 | 204 | 362 | 20 | 201 | 623 | 355 | 501 | 183 | 642 | 2 | 416 | 420 | 59 | 570 | 585 | 1193 | 449 | 302 | 130 | 11 | 687 | 565 | 552 | 50 | 619 | 21 | 168 
ko | 218 | 656 | 147 | 321 | 108 | 399 | 361 | 1817 | 254 | 230 | 130 | 467 | 24 | 764 | 756 | 264 | -- | 85 | 279 | 433 | 2 | 132 | 581 | 109 | 567 | 216 | 614 | 0 | 506 | 550 | 74 | 211 | 589 | 298 | 470 | 397 | 177 | 4 | 643 | 596 | 480 | 54 | 514 | 12 | 44 
ky | 90 | 280 | 209 | 126 | 50 | 134 | 120 | 478 | 118 | 82 | 58 | 188 | 13 | 323 | 137 | 100 | 85 | -- | 99 | 151 | 7 | 95 | 230 | 59 | 228 | 93 | 1031 | 1 | 183 | 186 | 45 | 134 | 264 | 144 | 177 | 145 | 106 | 4 | 318 | 496 | 228 | 118 | 172 | 7 | 22 
mr | 192 | 472 | 169 | 557 | 73 | 170 | 146 | 990 | 215 | 2025 | 144 | 3843 | 40 | 707 | 255 | 204 | 279 | 99 | -- | 602 | 0 | 196 | 542 | 111 | 477 | 1674 | 592 | 0 | 374 | 387 | 116 | 234 | 541 | 302 | 1646 | 1803 | 155 | 9 | 632 | 536 | 1348 | 69 | 435 | 18 | 36 
ne | 297 | 782 | 227 | 667 | 150 | 235 | 196 | 1538 | 313 | 545 | 235 | 1401 | 35 | 1123 | 420 | 362 | 433 | 151 | 602 | -- | 4 | 284 | 922 | 111 | 699 | 513 | 816 | 2 | 529 | 525 | 160 | 396 | 646 | 494 | 971 | 707 | 193 | 8 | 924 | 744 | 1194 | 72 | 694 | 36 | 55 
om | 30 | 8 | 1 | 1 | 2 | 11 | 16 | 80 | 6 | 0 | 6 | 4 | 4 | 12 | 3 | 20 | 2 | 7 | 0 | 4 | -- | 1 | 0 | 13 | 4 | 2 | 7 | 0 | 5 | 9 | 1 | 8 | 10 | 5 | 3 | 4 | 1 | 161 | 3 | 12 | 1 | 5 | 1 | 0 | 10 
ps | 173 | 2219 | 228 | 270 | 219 | 480 | 409 | 1460 | 153 | 202 | 208 | 1450 | 10 | 1297 | 210 | 201 | 132 | 95 | 196 | 284 | 1 | -- | 2914 | 78 | 497 | 212 | 1061 | 1 | 198 | 215 | 128 | 300 | 691 | 272 | 381 | 275 | 68 | 10 | 847 | 745 | 2899 | 154 | 544 | 6 | 19 
fa | 390 | 4154 | 816 | 737 | 421 | 954 | 715 | 4500 | 611 | 487 | 493 | 5444 | 42 | 3973 | 1048 | 623 | 581 | 230 | 542 | 922 | 0 | 2914 | -- | 148 | 5683 | 494 | 4236 | 0 | 996 | 1001 | 264 | 791 | 2478 | 972 | 1181 | 719 | 305 | 8 | 3784 | 3616 | 6931 | 296 | 3236 | 74 | 63 
pcm | 179 | 385 | 77 | 110 | 37 | 128 | 118 | 1120 | 416 | 59 | 528 | 142 | 272 | 289 | 132 | 355 | 109 | 59 | 111 | 111 | 13 | 78 | 148 | -- | 170 | 80 | 243 | 0 | 198 | 223 | 20 | 185 | 287 | 358 | 172 | 113 | 63 | 30 | 209 | 218 | 146 | 15 | 138 | 8 | 505 
pt | 238 | 2336 | 693 | 753 | 217 | 1145 | 973 | 4416 | 963 | 496 | 388 | 6689 | 60 | 4762 | 737 | 501 | 567 | 228 | 477 | 699 | 4 | 497 | 5683 | 170 | -- | 489 | 4614 | 8 | 1354 | 1330 | 205 | 593 | 7424 | 987 | 944 | 719 | 448 | 2 | 3723 | 4584 | 6827 | 172 | 3930 | 151 | 82 
pa | 152 | 466 | 163 | 525 | 74 | 176 | 142 | 1162 | 215 | 2119 | 129 | 4006 | 26 | 643 | 215 | 183 | 216 | 93 | 1674 | 513 | 2 | 212 | 494 | 80 | 489 | -- | 539 | 0 | 360 | 357 | 108 | 240 | 510 | 309 | 1558 | 1738 | 148 | 6 | 557 | 496 | 1484 | 55 | 378 | 11 | 33 
ru | 293 | 5123 | 2163 | 780 | 499 | 2126 | 1655 | 8536 | 820 | 506 | 493 | 4457 | 73 | 7416 | 1434 | 642 | 614 | 1031 | 592 | 816 | 7 | 1061 | 4236 | 243 | 4614 | 539 | -- | 6 | 1459 | 1395 | 338 | 1077 | 4753 | 1559 | 1427 | 767 | 527 | 3 | 6043 | 21011 | 5111 | 777 | 3843 | 163 | 102 
gd | 0 | 1 | 3 | 0 | 0 | 0 | 0 | 161 | 2 | 0 | 1 | 3 | 0 | 8 | 2 | 2 | 0 | 1 | 0 | 2 | 0 | 1 | 0 | 0 | 8 | 0 | 6 | -- | 3 | 3 | 1 | 2 | 4 | 1 | 0 | 0 | 0 | 0 | 10 | 7 | 2 | 1 | 7 | 47 | 1 
sr | 332 | 1015 | 288 | 525 | 100 | 381 | 335 | 3767 | 538 | 307 | 239 | 765 | 38 | 1352 | 562 | 416 | 506 | 183 | 374 | 529 | 5 | 198 | 996 | 198 | 1354 | 360 | 1459 | 3 | -- | 9004 | 109 | 359 | 1170 | 549 | 692 | 614 | 312 | 9 | 1228 | 1517 | 989 | 113 | 651 | 46 | 61 
sr | 365 | 1074 | 278 | 528 | 108 | 469 | 418 | 3904 | 565 | 298 | 248 | 714 | 47 | 1344 | 606 | 420 | 550 | 186 | 387 | 525 | 9 | 215 | 1001 | 223 | 1330 | 357 | 1395 | 3 | 9005 | -- | 115 | 365 | 1232 | 549 | 702 | 638 | 320 | 15 | 1200 | 1453 | 960 | 112 | 592 | 38 | 64 
si | 54 | 288 | 113 | 143 | 79 | 130 | 116 | 518 | 88 | 124 | 45 | 446 | 8 | 444 | 95 | 59 | 74 | 45 | 116 | 160 | 1 | 128 | 264 | 20 | 205 | 108 | 338 | 1 | 109 | 115 | -- | 123 | 242 | 167 | 329 | 163 | 59 | 4 | 271 | 277 | 500 | 37 | 193 | 7 | 10 
so | 283 | 979 | 342 | 373 | 76 | 279 | 242 | 2171 | 483 | 233 | 386 | 702 | 76 | 1301 | 356 | 570 | 211 | 134 | 234 | 396 | 8 | 300 | 791 | 185 | 593 | 240 | 1077 | 2 | 359 | 365 | 123 | -- | 666 | 1017 | 630 | 333 | 136 | 21 | 906 | 835 | 944 | 79 | 693 | 21 | 115 
es | 282 | 3566 | 680 | 650 | 412 | 1874 | 1621 | 6926 | 1007 | 477 | 458 | 2806 | 77 | 4585 | 959 | 585 | 589 | 264 | 541 | 646 | 10 | 691 | 2478 | 287 | 7424 | 510 | 4753 | 4 | 1171 | 1232 | 242 | 666 | -- | 1024 | 938 | 716 | 433 | 4 | 3590 | 3096 | 2923 | 259 | 2282 | 69 | 124 
sw | 352 | 1087 | 514 | 456 | 77 | 343 | 289 | 2676 | 866 | 276 | 583 | 864 | 150 | 1922 | 443 | 1193 | 298 | 144 | 302 | 494 | 5 | 272 | 972 | 358 | 987 | 309 | 1559 | 1 | 549 | 549 | 167 | 1017 | 1024 | -- | 856 | 415 | 219 | 7 | 1342 | 1306 | 1213 | 83 | 945 | 36 | 200 
ta | 338 | 1147 | 486 | 869 | 168 | 385 | 326 | 2864 | 402 | 1654 | 266 | 3675 | 46 | 1809 | 554 | 449 | 470 | 177 | 1645 | 971 | 3 | 381 | 1181 | 172 | 944 | 1558 | 1427 | 0 | 692 | 702 | 329 | 630 | 938 | 856 | -- | 2159 | 324 | 11 | 1395 | 1299 | 2370 | 109 | 1026 | 30 | 53 
te | 282 | 761 | 220 | 720 | 140 | 280 | 247 | 1943 | 355 | 1921 | 217 | 3748 | 41 | 1052 | 389 | 302 | 397 | 145 | 1803 | 707 | 4 | 275 | 719 | 113 | 719 | 1738 | 767 | 0 | 614 | 638 | 163 | 333 | 716 | 415 | 2159 | -- | 240 | 9 | 796 | 751 | 1702 | 86 | 575 | 21 | 44 
th | 101 | 326 | 123 | 216 | 67 | 230 | 199 | 1021 | 164 | 120 | 77 | 300 | 17 | 572 | 294 | 130 | 177 | 106 | 155 | 193 | 1 | 68 | 305 | 63 | 448 | 148 | 527 | 0 | 312 | 320 | 59 | 136 | 433 | 219 | 324 | 240 | -- | 6 | 418 | 448 | 367 | 33 | 332 | 9 | 17 
ti | 246 | 24 | 2 | 3 | 2 | 11 | 11 | 123 | 4 | 2 | 9 | 7 | 7 | 5 | 3 | 11 | 4 | 4 | 9 | 8 | 161 | 10 | 8 | 30 | 2 | 6 | 3 | 0 | 9 | 15 | 4 | 21 | 4 | 7 | 11 | 9 | 6 | -- | 5 | 5 | 4 | 4 | 1 | 0 | 5 
tr | 352 | 3729 | 1527 | 822 | 399 | 1123 | 829 | 5167 | 832 | 575 | 500 | 3766 | 78 | 5785 | 1238 | 687 | 643 | 318 | 632 | 924 | 3 | 847 | 3784 | 209 | 3723 | 557 | 6043 | 10 | 1228 | 1200 | 271 | 906 | 3590 | 1342 | 1395 | 796 | 418 | 5 | -- | 4161 | 4381 | 332 | 3010 | 148 | 123 
uk | 277 | 3239 | 1424 | 656 | 337 | 1346 | 1091 | 6327 | 705 | 477 | 390 | 3938 | 69 | 4855 | 955 | 565 | 596 | 496 | 536 | 744 | 12 | 745 | 3616 | 218 | 4584 | 496 | 21013 | 7 | 1517 | 1453 | 277 | 835 | 3096 | 1306 | 1299 | 751 | 448 | 5 | 4161 | -- | 4336 | 450 | 3078 | 132 | 80 
ur | 325 | 4648 | 971 | 1450 | 553 | 1224 | 947 | 5850 | 738 | 1640 | 506 | 16118 | 48 | 6606 | 722 | 552 | 480 | 228 | 1348 | 1194 | 1 | 2899 | 6931 | 146 | 6827 | 1484 | 5111 | 2 | 989 | 960 | 500 | 944 | 2923 | 1213 | 2370 | 1702 | 367 | 4 | 4381 | 4336 | -- | 358 | 3737 | 83 | 76 
uz | 37 | 362 | 202 | 85 | 57 | 150 | 124 | 434 | 67 | 59 | 57 | 308 | 11 | 413 | 50 | 50 | 54 | 118 | 69 | 72 | 5 | 154 | 296 | 15 | 172 | 55 | 777 | 1 | 113 | 112 | 37 | 79 | 259 | 83 | 109 | 86 | 33 | 4 | 332 | 450 | 358 | -- | 237 | 9 | 17 
vi | 227 | 2375 | 729 | 495 | 403 | 1539 | 1233 | 4473 | 437 | 434 | 358 | 3759 | 60 | 4921 | 879 | 619 | 514 | 172 | 435 | 694 | 1 | 544 | 3236 | 138 | 3930 | 378 | 3843 | 7 | 651 | 592 | 193 | 693 | 2282 | 945 | 1026 | 575 | 332 | 1 | 3010 | 3078 | 3737 | 237 | -- | 121 | 76 
cy | 1 | 33 | 34 | 43 | 3 | 25 | 17 | 2906 | 45 | 20 | 30 | 89 | 7 | 177 | 21 | 21 | 12 | 7 | 18 | 36 | 0 | 6 | 74 | 8 | 151 | 11 | 163 | 47 | 46 | 38 | 7 | 21 | 69 | 36 | 30 | 21 | 9 | 0 | 148 | 132 | 83 | 9 | 121 | -- | 10 
yo | 50 | 120 | 37 | 60 | 9 | 38 | 34 | 224 | 162 | 43 | 370 | 62 | 321 | 168 | 23 | 168 | 44 | 22 | 36 | 55 | 10 | 19 | 63 | 505 | 82 | 33 | 102 | 1 | 61 | 64 | 10 | 115 | 124 | 200 | 53 | 44 | 17 | 5 | 123 | 80 | 76 | 17 | 76 | 10 | -- 


## Training & Evaluation
  * See [training and evaluation module.](seq2seq/)

## Language-agnostic Summary Evaluation
  * See [LaSE module.](LaSE/)

## Models

To be announced.

## Benchmarks

To be announced.
  
## License
Contents of this repository are restricted to only non-commercial research purposes under the [Creative Commons Attribution-NonCommercial-ShareAlike 4.0 International License (CC BY-NC-SA 4.0)](https://creativecommons.org/licenses/by-nc-sa/4.0/). Copyright of the dataset contents belongs to the original copyright holders.

## Citation
If you use any of the datasets, models or code modules, please cite the following paper:
```
@article{hasan2021crosssum,
  author    = {Tahmid Hasan and Abhik Bhattacharjee and Wasi Uddin Ahmad and Yuan-Fang Li and Yong-bin Kang and Rifat Shahriyar},
  title     = {CrossSum: Beyond English-Centric Cross-Lingual Abstractive Text Summarization for 1500+ Language Pairs},
  journal   = {CoRR},
  volume    = {abs/2112.08804},
  year      = {2021},
  url       = {https://arxiv.org/abs/2112.08804},
  eprinttype = {arXiv},
  eprint    = {2112.08804}
}
```
