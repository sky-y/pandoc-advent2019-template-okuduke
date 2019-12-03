# Pandocのテンプレート機能でYAMLから本の奥付を自動生成する

[Pandoc Advent Calendar 2019](https://adventar.org/calendars/4338)の記事のためのリポジトリです。
詳細は本文をお読みください：

[Pandocのテンプレート機能でYAMLから本の奥付を自動生成する - Qiita](https://qiita.com/sky_y/items/47da01623f50380c2023)

## 使い方

1行ずつ実行するなら下記の通りにコマンドを打ってください。

```
$ pandoc -f markdown+raw_tex src/metadata.yaml --template=src/template-okuduke.tex -o okuduke.tex
$ pandoc -s -N -f markdown+raw_tex --pdf-engine=lualatex \
  -A ./okuduke.tex --metadata-file=src/metadata.yaml \
  src/body.md -o book.pdf
```

`make` を使うと一気に実行できます。

```
$ make
$ make clean  # 生成ファイルを削除
```
