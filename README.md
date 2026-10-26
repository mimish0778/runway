# RUNWAY

作業を始めるまでの助走と、作業の継続を手助けするタイマーアプリです。1 分の準備時間のあとで「続ける」か「休む」かを選び、作業時間を記録します。個人で使うために作りました。

HTML ファイル 1 つで動作し、インストールやビルドは不要です。

**デモ:** https://mimish0778.github.io/runway/

## 特徴

- 準備（IDLE）、作業（WORK）、休憩（BREAK）の 3 つのフェーズを、ボタン 1 つで切り替え
- いきなり作業を始めず、まず 1 分の準備時間を置く
- 作業時間は上限なしで計測し、作業の回数と合計時間を表示
- 合計作業時間の 2 時間の目標に対する進み具合をバーで表示
- 各フェーズの開始・終了を効果音で知らせる（オフにもできる）

## 使い方

1. [デモページ](https://mimish0778.github.io/runway/) を開き、`START` を押します。
2. **IDLE（準備）** — 1 分のカウントダウンが始まります。作業に入る前の準備時間なので、何もしなくてもかまいません。`SKIP TO BREAK` を押すと、すぐに休憩に移ります。
3. カウントダウンが終わったら、次のどちらかを選びます。
   - `KEEP GOING` — 作業を始めます。
   - `TAKE A BREAK` — 休憩に入ります。
4. **WORK（作業）** — 作業時間の計測が始まります。区切りのよいところで `TAKE A BREAK` を押すと、作業の記録が残り、休憩に移ります。
5. **BREAK（休憩）** — 1 分のカウントダウンが始まります。終わるか `SKIP` を押すと待機状態（STANDING BY）に戻るので、もう一度 `START` から始めます。

### ローカルで動かす

```bash
git clone https://github.com/mimish0778/runway.git
```

クローンした `index.html` をブラウザで開くだけで使えます。

## 画面の見方

| 表示 | 内容 |
| --- | --- |
| SESSIONS | 終えた作業（WORK）の回数 |
| TOTAL TIME | 作業時間の合計 |
| TODAY | 作業時間の合計の、2 時間の目標に対する割合 |
| LOG | 直近 10 件の IDLE / WORK / BREAK の記録（終えた時刻と長さ） |
| SFX ON / OFF | 効果音のオン・オフの切り替え |

中央のリングは、IDLE と BREAK では 1 分の残り時間を、WORK では 1 時間で一周する経過時間を表します。

記録はページの中にだけ保持され、ページを閉じたり再読み込みしたりするとリセットされます。データを外部に送信することはありません。

## 技術構成

- HTML / CSS / JavaScript（ライブラリやフレームワークは不使用）
- 効果音: Web Audio API で生成
- フォント: [Black Ops One](https://fonts.google.com/specimen/Black+Ops+One)、[Share Tech Mono](https://fonts.google.com/specimen/Share+Tech+Mono)（Google Fonts）

## 参考

次の記事で紹介されている考え方を参考にしています。

https://note.com/awawa_adhd/n/n203716fd6e8b
