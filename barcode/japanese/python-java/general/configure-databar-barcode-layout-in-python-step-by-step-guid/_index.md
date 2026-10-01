---
category: general
date: 2026-08-12
description: PythonでDatabarバーコードのレイアウトを素早く設定します。列や行の設定方法、バーコードジェネレーターライブラリを使った画像の保存方法を学びましょう。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- configure databar barcode layout
- Databar Expanded Stacked
- barcode generator Python
- set barcode columns
- set barcode rows
language: ja
lastmod: 2026-08-12
og_description: PythonでDatabarバーコードのレイアウトを設定し、列・行・画像出力を制御します。すぐに実行できるソリューションのガイドに従ってください。
og_image_alt: Screenshot of a Databar Expanded Stacked barcode with custom column
  layout
og_title: PythonでDatabarバーコードのレイアウトを設定する – 完全チュートリアル
schemas:
- author: Aspose
  dateModified: '2026-08-12'
  description: Configure Databar barcode layout in Python quickly. Learn to set columns,
    rows, and save images with the barcode generator library.
  headline: Configure Databar barcode layout in Python – step‑by‑step guide
  type: TechArticle
- description: Configure Databar barcode layout in Python quickly. Learn to set columns,
    rows, and save images with the barcode generator library.
  name: Configure Databar barcode layout in Python – step‑by‑step guide
  steps:
  - name: Import the required classes
    text: '```python from aspose.barcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat
      ```'
  - name: Create a barcode generator for Databar Expanded Stacked
    text: '```python # Initialize the generator with the desired symbology and value
      barcode_generator = BarcodeGenerator( EncodeTypes.DatabarExpandedStacked, "Databar
      Expanded Stacked long" ) ```'
  - name: Set the number of columns (horizontal layout)
    text: '```python # Configure the layout to use 4 columns barcode_generator.parameters.barcode.data_bar.columns
      = 4 ```'
  - name: Save the barcode image with the column layout
    text: '```python # Save the image as a PNG file barcode_generator.save("output/ExpandedCols4.png",
      BarCodeImageFormat.Png) ```'
  - name: Create a second generator for the same barcode type (row layout)
    text: If you prefer a vertical stack, you work with rows instead of columns. The
      code below re‑uses the same value but creates a fresh `BarcodeGenerator` instance
      to avoid mixing column and row settings.
  - name: Set the number of rows (vertical layout)
    text: '```python # Configure the layout to use 3 rows barcode_generator.parameters.barcode.data_bar.rows
      = 3 ```'
  - name: Save the barcode image with the row layout
    text: '```python # Save the vertically stacked barcode barcode_generator.save("output/ExpandedRows3.png",
      BarCodeImageFormat.Png) ```'
  type: HowTo
tags:
- barcode
- Python
- Databar
- image generation
title: PythonでDatabarバーコードのレイアウトを設定する – ステップバイステップガイド
url: /ja/python-java/general/configure-databar-barcode-layout-in-python-step-by-step-guid/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# PythonでDatabarバーコードレイアウトを設定する – ステップバイステップガイド

If you need to **configure Databar barcode layout in Python**, this guide walks you through the entire process. You’ll see how to set the number of columns or rows for a Databar Expanded Stacked barcode and how to save the resulting image with a single call to the barcode generator library.

**PythonでDatabarバーコードレイアウトを設定**する必要がある場合、このガイドが全工程を案内します。Databar Expanded Stackedバーコードの列数または行数の設定方法と、バーコードジェネレーターライブラリを1回呼び出すだけで結果の画像を保存する方法が分かります。

Controlling the layout is essential when you embed barcodes on narrow packaging, receipts, or mobile screens. In the sections below we’ll cover the required imports, the two layout options (columns and rows), and the best practices for saving a clean PNG image.

レイアウトの制御は、狭い包装材、レシート、モバイル画面にバーコードを埋め込む際に重要です。以下のセクションでは、必要なインポート、2つのレイアウトオプション（列と行）、そしてクリーンなPNG画像を保存するベストプラクティスを解説します。

## 必要なもの

* Python 3.8 以上
* `aspose.barcode`（または互換性のあるバーコード生成パッケージ）をインストール  
  ```bash
  pip install aspose-barcode
  ```
* PNGファイルを保存するフォルダーへの書き込み権限

No additional external tools are required—the library handles rendering, scaling, and image encoding internally.

追加の外部ツールは不要です。ライブラリが内部でレンダリング、スケーリング、画像エンコードを処理します。

## PythonでDatabarバーコードレイアウトを設定する方法

The core of the solution is the `BarcodeGenerator` class. It accepts an `EncodeTypes` enum that identifies the barcode symbology—in this case `EncodeTypes.DatabarExpandedStacked`. After creating the generator you can adjust the layout by setting the `columns` or `rows` properties on the `data_bar` parameter object.

このソリューションの中心は `BarcodeGenerator` クラスです。バーコードシンボロジーを識別する `EncodeTypes` 列挙体を受け取り、ここでは `EncodeTypes.DatabarExpandedStacked` を使用します。ジェネレーターを作成した後、`data_bar` パラメータオブジェクトの `columns` または `rows` プロパティを設定してレイアウトを調整できます。

### 手順 1: 必要なクラスをインポート

```python
from aspose.barcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat
```

These imports give you access to the generator, the enumeration for Databar types, and the PNG image format constant.

これらのインポートにより、ジェネレーター、Databarタイプ用の列挙体、そして PNG 画像フォーマット定数にアクセスできます。

### 手順 2: Databar Expanded Stacked 用のバーコードジェネレーターを作成

```python
# Initialize the generator with the desired symbology and value
barcode_generator = BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked,
    "Databar Expanded Stacked long"
)
```

*Why this step?*  
`EncodeTypes.DatabarExpandedStacked` は、ライブラリに **Databar Expanded Stacked** シンボロジーを生成させます。これにより、コンパクトなフットプリントを保ちつつ、長い数値文字列をサポートできます。第2引数はエンコードするデータで、Databar 仕様を満たす任意の文字列を指定できます。

### 手順 3: 列数を設定（水平レイアウト）

```python
# Configure the layout to use 4 columns
barcode_generator.parameters.barcode.data_bar.columns = 4
```

**set barcode columns** はこの操作のキーフレーズです。列数を増やすと、バーコードが水平に広がり、幅の広いラベルに有用です。ライブラリは全体サイズを一定に保つためにモジュール幅を自動的に再計算します。

#### プロのコツ

The maximum column count for Databar Expanded Stacked is 8. Setting a value higher than the limit will clamp it to the maximum, but it’s better to validate your input beforehand.

Databar Expanded Stacked の最大列数は 8 です。上限を超える値を設定すると最大値にクランプされますが、事前に入力を検証する方が望ましいです。

### 手順 4: 列レイアウトでバーコード画像を保存

```python
# Save the image as a PNG file
barcode_generator.save("output/ExpandedCols4.png", BarCodeImageFormat.Png)
```

**save barcode image** は、レンダリングされたバーコードをディスクに書き込む操作です。PNG はロスレス形式で、信頼できるスキャンに必要なシャープなエッジを保持します。

### 手順 5: 同じバーコードタイプの2番目のジェネレーターを作成（行レイアウト）

If you prefer a vertical stack, you work with rows instead of columns. The code below re‑uses the same value but creates a fresh `BarcodeGenerator` instance to avoid mixing column and row settings.

垂直スタックを好む場合は、列ではなく行を使用します。以下のコードは同じ値を再利用しますが、列と行の設定が混在しないように新しい `BarcodeGenerator` インスタンスを作成します。

```python
# New generator instance for row configuration
barcode_generator = BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked,
    "Databar Expanded Stacked long"
)
```

### 手順 6: 行数を設定（垂直レイアウト）

```python
# Configure the layout to use 3 rows
barcode_generator.parameters.barcode.data_bar.rows = 3
```

**set barcode rows** はバーコードモジュールを垂直に配置します。3 行のレイアウトは各スタックの高さを減らし、狭いレシートやモバイル画面に適したバーコードになります。

#### エッジケース

If you set `rows` to 1, the library generates a single‑row Databar (equivalent to a standard Databar). Values below 1 are ignored and reset to the default (1 row).

`rows` を 1 に設定すると、ライブラリはシングルロウ Databar（標準の Databar と同等）を生成します。1 未満の値は無視され、デフォルト（1 行）にリセットされます。

### 手順 7: 行レイアウトでバーコード画像を保存

```python
# Save the vertically stacked barcode
barcode_generator.save("output/ExpandedRows3.png", BarCodeImageFormat.Png)
```

Again, we **save barcode image** using PNG to keep the output crisp.

再び、PNG を使用して **save barcode image** を実行し、出力を鮮明に保ちます。

## 完全に実行可能な例

Putting all the pieces together gives you a self‑contained script you can drop into any Python project.

すべての要素を組み合わせると、任意の Python プロジェクトに組み込める自己完結型スクリプトが得られます。

```python
# ------------------------------------------------------------
# configure_databar_layout.py
# Demonstrates how to configure Databar barcode layout in Python
# ------------------------------------------------------------

from aspose.barcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat
import os

# Ensure the output directory exists
output_dir = "output"
os.makedirs(output_dir, exist_ok=True)

# -----------------------------------------------------------------
# 1️⃣ Column layout – 4 columns
# -----------------------------------------------------------------
col_generator = BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked,
    "Databar Expanded Stacked long"
)
col_generator.parameters.barcode.data_bar.columns = 4   # set barcode columns
col_path = os.path.join(output_dir, "ExpandedCols4.png")
col_generator.save(col_path, BarCodeImageFormat.Png)   # save barcode image
print(f"Column layout saved to {col_path}")

# -----------------------------------------------------------------
# 2️⃣ Row layout – 3 rows
# -----------------------------------------------------------------
row_generator = BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked,
    "Databar Expanded Stacked long"
)
row_generator.parameters.barcode.data_bar.rows = 3      # set barcode rows
row_path = os.path.join(output_dir, "ExpandedRows3.png")
row_generator.save(row_path, BarCodeImageFormat.Png)   # save barcode image
print(f"Row layout saved to {row_path}")
```

**期待される出力**

Running the script creates two PNG files:

* `output/ExpandedCols4.png` – a barcode stretched across four columns
* `output/ExpandedRows3.png` – a barcode compressed into three rows

Both images can be opened in any image viewer or imported directly into PDF invoices, label templates, or web pages.

スクリプトを実行すると、2 つの PNG ファイルが作成されます：

* `output/ExpandedCols4.png` – 4 列にわたって伸びたバーコード
* `output/ExpandedRows3.png` – 3 行に圧縮されたバーコード

どちらの画像も任意の画像ビューアで開くことができ、PDF 請求書、ラベルテンプレート、ウェブページに直接インポートできます。

## よくある質問とトラブルシューティング

| Question | Answer |
|----------|--------|
| *バーコードがぼやけて見える場合はどうすればいいですか？* | `save` を呼び出す前に `barcode_generator.parameters.image_width` と `image_height` を設定して画像解像度を上げます。 |
| *他の画像形式は使用できますか？* | はい。必要に応じて `BarCodeImageFormat.Png` を `Jpeg`、`Bmp`、または `Gif` に置き換えます。 |
| *データ長に制限はありますか？* | Databar Expanded Stacked は最大 74 桁の数字文字列をサポートします。上限を超えると `ArgumentException` がスローされます。 |
| *前景色を変更するには？* | `barcode_generator.parameters.barcode.color = Color.Blue` を使用します（`System.Drawing.Color` をインポート）。 |
| *列と行を組み合わせられますか？* | いいえ。API は列と行を相互排他的なレイアウトモードとして扱います。バーコードインスタンスごとにどちらか一方を選択してください。 |

## 次のステップ

Now that you can **configure Databar barcode layout**, consider exploring these related topics:

これで **Databarバーコードレイアウトを設定** できるようになったので、以下の関連トピックを検討してください：

* **テキストキャプションを追加** – `barcode_generator.parameters.barcode.code_text` を使用して、エンコードされた値を画像の下に表示します。
* **バーコードを PDF に埋め込む** – 生成した PNG を `aspose.pdf` と組み合わせて印刷可能なドキュメントを作成します。
* **動的サイズ設定** – ラベルの寸法に基づいて実行時に最適な列または行数を計算します。
* **バッチ処理** – 製品コードの CSV をループして、バーコード画像のライブラリを自動生成します。

Experiment with different column and row values to see how they affect scan reliability on your target devices. The more you test, the better you’ll understand the trade‑offs between barcode size, readability, and space constraints.

さまざまな列と行の値を試して、対象デバイスでのスキャン信頼性への影響を確認してください。テストすればするほど、バーコードサイズ、可読性、スペース制約のトレードオフをより深く理解できます。

---

*コーディングを楽しんでください！このチュートリアルが役立ったと思ったら、チームメイトと共有するか、直面したレイアウトの課題についてコメントを残してください。*

## 次に学ぶべきこと？

The following tutorials cover closely related topics that build on the techniques demonstrated in this guide. Each resource includes complete working code examples with step-by-step explanations to help you master additional API features and explore alternative implementation approaches in your own projects.

以下のチュートリアルは、本ガイドで示した手法を基にした密接に関連するトピックを取り上げています。各リソースには、ステップバイステップの解説付きの完全なコード例が含まれており、追加の API 機能を習得し、独自プロジェクトで代替実装アプローチを検討するのに役立ちます。

- [DotCode バーコード画像の作成 – 行と列 (Aspose.BarCode)](/barcode/english/net/dotcode-barcode-configuration/dotcode-rows-columns-configuration/)
- [C# でバーコード画像を作成 – Codablock F の行と列を設定](/barcode/english/net/codablock-f-encoding/codablock-f-row-column-configuration/)
- [一次元 Databar バーコードの高さ調整](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-barcode-height-adjustment/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}