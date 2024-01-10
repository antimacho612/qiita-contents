# Qiita Contents

## 参照

- [qiita-cli](https://github.com/increments/qiita-cli)
- [VSCodeでマークダウンの構文と文章を校正してコミット時も自動でlintする - Qiita](https://qiita.com/waicode/items/33311d0a511dc821f53f)

## 記事の新規作成

```bash
npx qiita new [記事のファイルのベース名]
```

## プレビュー

```bash
npm run preview
```

## リント

```bash
# markdownlint
npm run lint:markdown

# textlint
npm run lint:text

# cspell
npm run lint:spell

# all
npm run lint
```
