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

`techmujin_planning.pdf` が生成されます。Git tag を切ったビルドでは `techmujin_planning-v1.0.0.pdf` のように version 付きで出力されます。

### GitHub Actions での自動ビルド

`main` ブランチへの push では GitHub Actions が `pnpm build` を実行して検証用 PDF を生成します。`v1.0.0` のような Git tag を push すると、生成された version 付き PDF を Release に公開します。

最新版の PDF は、[イベント企画書＜最新版＞ダウンロードページ](https://techmujin.github.io/techmujin-planning/) または対応する Git tag の Release からダウンロードできます。`v*` tag のリリースが生成されるたびに、ダウンロードページの PDF・バージョン・公開日時も自動更新されます。

Pull Request 作成時・更新時にも GitHub Actions が PDF をビルドし、workflow run の Artifact から対象ブランチ版 PDF をダウンロードできます。PR には別 workflow から最新 run へのリンクを含む bot コメントも自動で付きます。

PR で生成される PDF には「下書き」の透かしが入り、main への push で公開される PDF には入りません。

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
