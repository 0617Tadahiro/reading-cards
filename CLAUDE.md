# reading-cards（読書カード公開サイト）

公開URL: https://0617tadahiro.github.io/reading-cards/ （GitHub Pages / main / root）

## 構成
- `index.html` … サイト本体。カード追加では触らない
- `cards.json` … `{"files": [...]}`。表示するカードJSONのファイル名一覧（この順で表示）
- `<id>.json` … カード1冊 = 1ファイル。`{"id","title","author","tags":[],"body","cover"}`
- `covers/<id>.jpg` … 表紙画像（幅600px以下のJPEG）。カードの `"cover": "covers/<id>.jpg"` で紐づける。無ければ書名入りの仮表紙が出る

## カードの追加
1. `<id>.json` を作る（idは半角英数字とハイフン。bodyはMarkdown：`##`章、`###`節、`**太字**`、`==ハイライト==`、各章末に`### この章のまとめ`）
2. 表紙画像があれば `covers/<id>.jpg` に置き、`cover` を設定
3. `cards.json` の `files` 末尾にファイル名を追加
4. JSONの妥当性を確認してから commit / push（コミット作成者は Claude <noreply@anthropic.com>）
5. 1〜2分後に公開URLと `<id>.json` が200で返るか確認
