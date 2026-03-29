# techmujin-planning

テック無尽の企画書ドキュメント管理リポジトリです。Markdownで記述した企画書を [Vivliostyle](https://vivliostyle.org/) でPDFに変換します。

## 開発環境のセットアップ

### 必要なもの

- [Node.js](https://nodejs.org/) v18 以上
- [pnpm](https://pnpm.io/)

### インストール

```bash
pnpm install
```

## 使い方

### PDF のビルド

```bash
pnpm build
```

`output.pdf` が生成されます。

### プレビュー

```bash
pnpm preview
```

ブラウザでリアルタイムプレビューが開きます。Markdownを編集すると自動で反映されます。

## ドキュメント構成

企画書の各セクションは `docs/` 配下のMarkdownファイルで管理しています。ファイルの順序や構成は `vivliostyle.config.js` の `entry` 配列で定義しています。

### ページの追加

1. `docs/` に新しいMarkdownファイルを作成する
2. `vivliostyle.config.js` の `entry` 配列の任意の位置に追加する

### ページの削除・並び替え

`vivliostyle.config.js` の `entry` 配列を編集してください。
