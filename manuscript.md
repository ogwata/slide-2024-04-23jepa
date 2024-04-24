---
author: Katsuhiro Ogata
lang: ja
title: 各社のEPUBリーダーは、現行CSS仕様やアクセシビリティをどれだけサポートしているのか？
---

# 各社のEPUBリーダーは、<br/>現行CSS仕様やアクセシビリティを<br/>どれだけサポートしているのか？


小形克宏<br/>
2024年4月24日<br/>
JAGAT 次世代パブリッシング研究会<br/>
（Vivliostyle Foundation）

# 次世代パブリッシング研究会のご紹介①

- JAGAT（日本印刷技術協会）の研究会
- JAGATさんの会議室を借りて運営している、自主的な勉強会（月1回）
- XMLコンソーシアム／クロスメディアパブリッシング部会が母体
- 2010年4月に「XMLパブリッシング（準）研究会」として発足
- 2022年に現在のグループ名に改称
- 現在のテーマは「コンピュータ、印刷、出版」
- 活動内容は「作ってみる系」と「調べてみる系」

# 次世代パブリッシング研究会のご紹介②

- いつもは[Discord: jagat-xpub](https://discord.gg/DXK3TPZT)でコミュニケーション
- [Facebook: JAGAT 次世代パブリッシング研究会](https://www.facebook.com/groups/288790814553206)
- 現在活動中のメンバーは6名
- コロナによる会員減から立ち直れない現状が課題
- 一緒に活動する人、大募集❗
- ただ今、今年の活動内容を検討中
- 5月24日「市谷の杜 本と活字館」に遠足の予定😊

# 次世代パブリッシング研究会のご紹介③

- 入会希望者は以下の方法で！
  - [Discord: jagat-xpub招待リンク](https://discord.gg/DXK3TPZT)
  - [研究会のアドレス（fantastikk.2010@gmail.com）](mailto:fantastikk.2010@gmail.com)にメールを出す
  - [Facebook: JAGAT 次世代パブリッシング研究会](https://www.facebook.com/groups/288790814553206)に参加する

# EPUBリーダー表示テスト報告書（2023年度）

- 報告書制作リポジトリ（GitHub）
  - [EPUBリーダー表示テスト報告書（2023年度）](https://github.com/jagat-xpub/viewer-test-2023?tab=readme-ov-file)
- テストファイル開発リポジトリ（GitHub）
  - [EPUBリーダーのCSS仕様適合性テスト](https://github.com/jagat-xpub/epub-css-test/tree/main)
- テスト結果（Googleスプレッドシート）
  - [EPUBリーダー表示チェック（JAGAT次世代パブリッシング研究会）2023公開用](https://docs.google.com/spreadsheets/u/1/d/e/2PACX-1vSPaWWfqx2bZiRqK__XG_v_NEGY5OjB-lIcoG9Ll_D1aG5UA7RwpUi3dOq4fLTt40flSuFGhu38Iv7o/pubhtml#)



# CSS表示テストの目的

- EPUB 3.3では最新CSSモジュールのセット [“CSS Snapshot”](https://www.w3.org/TR/CSS/) の実装を義務づけている
  - **テーマ①**：現在日本国内で利用されているEPUBリーダーは、“CSS Snapshot” をどのくらいサポートしているのか
- EPUB 3.3では-epub-接頭辞なしで縦書き用プロパティを書くことを推奨
  - **テーマ②**：現在使われているEPUBリーダーは、本当に-epub-接頭辞なしで表示できるのか

# “CSS Snapshot”とは？

- W3CでCSS仕様を作成しているCSS WGが作成
- CSSモジュールを、機能の安定性の程度によって評価・分類したリスト
  1. CSSの公式的な定義に含まれるCSSモジュール：**82項目**
  2. かなり安定しているが実装経験が限定的なCSSモジュール：**25項目**
  3. 大まかな相互運用性のあるCSSモジュール：**3項目**
  4. CSS Snapshot 2023に載っていないが最新のブラウザで利用できるCSSモジュール：**3項目**
- そのうち、報告書には上記1.だけを掲載
- それ以外の結果はGoogleスプレッドシートを参照

# CSS表示テストの方法

- 対応の可否が一目で識別できる[テスト用EPUBファイル](https://github.com/jagat-xpub/epub-css-test/tree/main)を制作
- 当研究会のメンバーごとに割り振って各自がテスト
- その結果を以下のGoogleスプレッドシートに記入
  - [EPUBリーダー表示チェック（JAGAT次世代パブリッシング研究会）2023公開用](https://docs.google.com/spreadsheets/u/1/d/e/2PACX-1vSPaWWfqx2bZiRqK__XG_v_NEGY5OjB-lIcoG9Ll_D1aG5UA7RwpUi3dOq4fLTt40flSuFGhu38Iv7o/pubhtml#)

# CSS表示テストの結果（村上）へ→

# 本テストの成果①

- 現在使われているEPUBリーダーのレイアウトエンジンは、モダンブラウザー系と独自エンジン系の2種に分かれる
- この2種のレイアウトエンジンは互いに開発方針が大きく異なる

# 本テストの成果②

- モダンブラウザー系リーダーは、おおむね “CSS Snapshot” をサポート
  - EPUB 3.3が規定したCSSの要件を満たしている
- 独自エンジン系リーダーは “CSS Snapshot” のサポートはきわめて貧弱
  - EPUB 3.3が規定したCSSの要件を満たしていない

# 本テストの成果③

- -epub-接頭辞なしでは「writing-mode プロパティ vertical-rl」をサポートできなかったリーダー
  - Kindle（Windows版のみ）
  - kobo（Mac版、Windows版）
  - 超縦書（Windows版）