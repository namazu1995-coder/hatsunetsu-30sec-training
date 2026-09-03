# 院内発熱トレーニング

[![Built with Claude Code](https://img.shields.io/badge/Built%20with-Claude%20Code-D97757?logo=anthropic&logoColor=white)](https://claude.com/claude-code)

初期研修医が当直中に遭遇しやすい「院内発熱」の初動を、短い症例で繰り返し学ぶためのスマートフォン向けWebアプリです。このリポジトリのコード・症例・イラストはすべて [Claude Code](https://claude.com/claude-code) との対話で作成しました。

診療支援や正解の暗記が目的ではなく、緊急時に重要な考え方を**自力で取り出せるようにすること**を目的としています。

## ▶ アプリを開く

**[namazu1995-coder.github.io/hatsunetsu-30sec-training](https://namazu1995-coder.github.io/hatsunetsu-30sec-training/)**

ログイン不要・誰でもこのリンクから開けます。GitHub上で `hatsunetsu-training.html` を直接開いてもソースコードが表示されるだけで、アプリとしては動きません。上のリンクから開くか、下のQRコードをスマホのカメラで読み取ってください。

<img src="hatsunetsu_qr.png" alt="アプリへのQRコード" width="200">

Claudeでの試作段階で作った版はこちら: [claude.ai/code/artifact/5e58a2f8-b10e-47b5-860d-464c63b2a462](https://claude.ai/code/artifact/5e58a2f8-b10e-47b5-860d-464c63b2a462)(閲覧にはClaudeへのログインが必要な場合があります)

## 使い方

各症例で、答えを見る前に自分の言葉で次の3つを入力します。

1. 最初に確認すること
2. 見落とすと危険な病態
3. 必要な検査・対応

その後、重要点を強調した模範解答と照らし合わせ、「自力で言えた」「一部抜けた」「ほぼ言えなかった」で自己評価します。「一部抜けた」「ほぼ言えなかった」を選んだ症例は復習リストに残り、後から再挑戦できます。進捗はブラウザのlocalStorageに保存されます。

全症例共通の最後に、院内発熱の初動を貫く「型」を提示します。

> バイタルサイン → 重症度 → 原因検索 → 必要検査 → 抗菌薬 → 上級医への早期共有

## 収録症例(8例)

**感染性の原因**

| # | 症例 |
|---|---|
| 1 | 肺炎 |
| 2 | 尿路感染症 |
| 3 | SSI(手術部位感染)・デバイス感染 |
| 4 | CDI(Clostridioides difficile感染症) |
| 5 | CRBSI合併の発熱性好中球減少症(複合問題) |

**非感染性の原因**

| # | 症例 |
|---|---|
| 6 | DVT(深部静脈血栓症) |
| 7 | 偽痛風・結晶性関節炎(化膿性関節炎の除外) |
| 8 | 薬剤熱・薬疹 |

症例カードには診断名を出さず、デバイス留置や発熱パターンなど軽いヒントのみを表示します。診断名は自己評価の後、模範解答とともに初めて開示されます。

## オフラインで使う場合

`hatsunetsu-training.html` はこのリポジトリをクローン(またはダウンロード)して、ブラウザで直接開くだけで単体で動作します(外部通信不要、進捗はブラウザのlocalStorageに保存されます)。

## ファイル構成

```
hatsunetsu-training.html   アプリ本体(HTML/CSS/JS 単一ファイル)
index.html                 GitHub Pages用のリダイレクト(hatsunetsu-training.htmlへ転送)
images/                    症例イラスト(症例ごとのJPEG、8枚)
hatsunetsu_qr.png          アプリへのQRコード
```

## 技術メモ

- ビルド不要の単一HTMLファイル。外部ライブラリなし、フォントのみGoogle Fontsを使用
- 症例イラストは`images/`フォルダの写真(AI生成、外部CDN不使用・同梱ファイル)。**オフラインで使う場合はリポジトリ全体をクローン/ダウンロードしてください**(HTMLファイル単体だけを保存すると画像が表示されません)
- 進捗・自己評価履歴はlocalStorageに保存(サーバーなし)
