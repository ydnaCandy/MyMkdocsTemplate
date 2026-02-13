# MyMkdocsTemplate


## mkdocs環境設定

```bash
# uv環境作成
uv init --vcs none

# 仮想環境作成
uv sync

# 仮想環境起動
source .venv/bin/activate

# ライブラリのインストール
uv add mkdocs mkdocs-material

```

## vscodeでのmarp表示とcssを適用する方法

1. vscodeのmarpの拡張機能をインストール

2. marpを適用するmdの冒頭に下記を入力

    ```md
    ---
    marp: true
    theme: default
    style: @import url("path/to/your-style.css");
    ---

    ```
3. cssを適用する(プロジェクト全体で特定のCSSを常に適用したい場合は、VS Codeの settings.json に設定を追加します。)

    1. Ctrl + , (Macは Cmd + ,) で設定を開く
    2. markdown.marp.themes を検索
    3. 項目の追加からcssへのパスを追加

## marpで作ったスライドをhtmlに変換する

```bash

# プロジェクト初期化（package.json作成）
npm init -y

# marp-cliをインストール
npm install --save-dev @marp-team/marp-cli

# marp内にcssへの記載がある状態で実行
npx marp index.md --theme my-style.css -o index.html
```