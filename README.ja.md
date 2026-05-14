# docx2txt

Microsoft Word (`.docx`) ファイルからプレーンテキストを抽出するコマンドラインツールです。

## 機能

- `.docx` ファイルからテキストデータを抽出します。
- 抽出したテキストを、元のファイルと同じ名前の新しい `.txt` ファイルとして保存します。
- ディレクトリ内のすべての `.docx` ファイルを一括処理するための Deno スクリプトが含まれています。
- 安定した変換処理を実現するために [mammoth](https://www.npmjs.com/package/mammoth) を使用しています。

## 前提条件

- [Node.js](https://nodejs.org/)
- [Deno](https://deno.land/)

## インストール

1. このリポジトリをクローンし、ディレクトリに移動します。
2. Node.js の依存関係をインストールします:
    ```sh
    npm install
    ```

## 使い方

本プロジェクトには、用途に応じた2つのスクリプトが含まれています。変換のコアロジックは `docx2txt.js` (Node.js) に実装されており、一括処理用のラッパースクリプト `docx2txt_r.js` (Deno) から呼び出されます。

### 単一ファイルの変換

単一の `.docx` ファイルを変換するには、Node.js スクリプトを使用します:

```sh
node docx2txt.js path/to/your/document.docx
```

これにより、同じディレクトリに `path/to/your/document.txt` が作成されます。

### ディレクトリ内の一括変換

ディレクトリ内のすべての `.docx` ファイルを変換するには、Deno スクリプトを使用します:

```sh
deno run -A docx2txt_r.js path/to/your/directory/
```

このスクリプトは、対象ディレクトリ内のすべての `.docx` ファイルを検索して変換します。

#### 例

同梱されているサンプルファイルを変換する場合:

```sh
# 注: お使いのシェルによっては、ファイル名の '&' をエスケープする必要があります
node docx2txt.js sample/惣so\&BOB.docx
```

`sample/` ディレクトリ内のすべてのファイルを処理する場合:

```sh
deno run -A docx2txt_r.js sample/
```

## ライセンス

MIT License — 詳細は [LICENSE](LICENSE) を参照してください。
