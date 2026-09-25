---
category: general
date: 2026-08-19
description: Aspose.Barcode for Python を使用して ECI 付きバーコードを生成する方法。ECI データの追加、プレーンテキストとの混合、画像の保存方法を一つの分かりやすいガイドで学びましょう。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to generate barcode
- how to add eci
- Aspose.Barcode Python
- extended codetext barcode
- ECI encoding Python
language: ja
lastmod: 2026-08-19
og_description: Aspose.Barcode for Python を使用して ECI 付きのバーコードを生成する方法。このチュートリアルで、ECI
  データの追加方法、外観のカスタマイズ、結果の保存方法を学びましょう。
og_image_alt: Screenshot showing a barcode generated with how to generate barcode
  example
og_title: Aspose.Barcode Python を使用して ECI 付きバーコードを生成する方法 – ステップバイステップ
schemas:
- author: Aspose
  dateModified: '2026-08-19'
  description: How to generate barcode with ECI using Aspose.Barcode for Python. Learn
    how to add eci data, mix plain text, and save the image in one clear guide.
  headline: How to generate barcode with ECI using Aspose.Barcode Python
  type: TechArticle
- description: How to generate barcode with ECI using Aspose.Barcode for Python. Learn
    how to add eci data, mix plain text, and save the image in one clear guide.
  name: How to generate barcode with ECI using Aspose.Barcode Python
  steps:
  - name: Expected result
    text: When you open `extended_codetext.png`, you should see a Code 128 barcode
      that encodes the numeric string `1234567890` followed by the Chinese characters
      “特殊字符”. Scanning the barcode with a modern scanner that respects ECI will return
      the original mixed string.
  - name: What if I need a different character set?
    text: Choose the appropriate ECI value from the ISO/IEC 18004 table. For example,
      ECI 27 represents ISO‑8859‑1 (Latin‑1). Replace the numeric identifier in `add_eci_codetext`
      accordingly.
  - name: Can I embed more than one ECI block?
    text: Yes. Call `add_eci_codetext` multiple times. The builder inserts the necessary
      ECI switch codes between blocks, preserving the order you add them.
  - name: Does the generator support QR codes with ECI?
    text: Absolutely. Replace `barcode.Symbology.CODE_128` with `barcode.Symbology.QR`
      and adjust any QR‑specific parameters (e.g., error correction level) via `generator.parameters.qr`.
  - name: How to handle very long data strings?
    text: For linear barcodes like Code 128, the maximum length is about 80 characters
      when using extended codetext. If you exceed that, consider switching to a two‑dimensional
      symbology such as QR or Data Matrix, which can store thousands of characters.
  type: HowTo
tags:
- barcode
- Python
- Aspose
title: Aspose.Barcode Python を使用して ECI 付きバーコードを生成する方法
url: /ja/python/general/how-to-generate-barcode-with-eci-using-aspose-barcode-python/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Barcode Python を使用した ECI 付きバーコードの生成方法

プレーン文字と ECI エンコードされたデータの両方を含む **バーコードの生成方法** を知りたい場合、このガイドでは全工程を示します。**ECI を追加する方法**、サイズ調整、画像をディスクに書き出す単一の実行可能スクリプトの手順が正確に分かります。

このチュートリアルで扱う内容:

* Aspose.Barcode ライブラリのバージョン取得（オプションだがデバッグに便利）。
* プレーン文字と ECI エンコード文字を混在させた拡張コードテキスト文字列の構築。
* 拡張コードテキストをサポートするシンボロジー用のバーコードジェネレータの作成。
* バーコードのサイズカスタマイズと最終 PNG ファイルの保存。

外部ドキュメントは不要です。コードをコピーして実行すれば、ECI 26（UTF‑8）でエンコードされた中国語文字を含むバーコード画像が得られます。

## 前提条件

開始する前に、以下が揃っていることを確認してください。

* Python 3.8 以上がインストールされていること。  
* `aspose-barcode` パッケージがインストールされていること（`pip install aspose-barcode`）。  
* PNG ファイルを保存するフォルダーへの書き込み権限があること。

仮想環境を使用している場合は、依存関係を分離するためにまずそれをアクティブ化してください。

## 手順 1: Aspose.Barcode のバージョンを確認する（オプション）

正確なライブラリバージョンを把握しておくと、バグ報告やリリース間の機能比較に役立ちます。

```python
import aspose.barcode as barcode
from aspose.barcode.generation import BuildVersionInfo

ver = BuildVersionInfo()
print("Assembly version :", ver.ASSEMBLY_VERSION)
print("Product version  :", f"{ver.PRODUCT_MAJOR}.{ver.PRODUCT_MINOR}")
print("Release date     :", ver.RELEASE_DATE)
```

*なぜ重要か*: バージョン出力は、実行環境が参照しているドキュメントと一致していることを確認します。バージョンによってサポートされる ECI 値が異なる可能性があるため、簡単なチェックになります。

## 手順 2: プレーン部分と ECI エンコード部分を組み合わせた拡張コードテキストの構築

Aspose.Barcode は `ExtCodetextBuilder` を提供し、プレーンデータと ECI エンコードセグメントを連結できます。この例では数値文字列と中国語文字を混在させます。

```python
from aspose.barcode.generation import ExtCodetextBuilder

builder = ExtCodetextBuilder()
builder.add_plain_codetext("1234567890")          # plain numeric data
builder.add_eci_codetext(26, "特殊字符")          # Chinese characters using ECI 26 (UTF‑8)
extended_codetext = builder.get_extended_codetext()
print("Extended codetext :", extended_codetext)
```

*説明*:
* `add_plain_codetext` は、バーコードシンボロジーが通常の文字として扱うデータを挿入します。  
* `add_eci_codetext` は、提供されたテキストの前に ECI インジケータ（ここでは UTF‑8 に対応する **26**）を付加するようジェネレータに指示します。これがバーコードに **ECI データを追加する方法** です。

`add_eci_codetext` を複数回呼び出すことで、複数の異なる言語ブロックを埋め込むことができます。ビルダーは必要なエスケープシーケンスを自動的に処理します。

## 手順 3: 拡張コードテキストをサポートするシンボロジーを選択する

すべてのバーコードタイプが ECI セグメントを格納できるわけではありません。Code 128、QR、Data Matrix が一般的な選択肢です。例では、広くサポートされており、プレーンとエンコードされたデータの混在に適した Code 128 を使用します。

```python
generator = barcode.generator.BarcodeGenerator(
    barcode.Symbology.CODE_128,   # Code128 supports extended codetext
    extended_codetext
)
```

*なぜ Code 128 か*: ビルダーが生成する ECI エスケープシーケンスと全 ASCII 範囲を受け入れるため、プレーンテキストとエンコードテキストを混在させる「バーコード生成」シナリオに最適です。

## 手順 4: バーコードの外観を調整する

`parameters` オブジェクトを介してサイズ、高さ、余白など多くの視覚的側面を制御できます。

```python
# Width of a single module (the smallest bar)
generator.parameters.barcode.x_dimension = 2   # 2 pixels per module

# Height of the bars (for linear barcodes)
generator.parameters.barcode.bar_height = 50  # 50 pixels tall

# Optional: add quiet zone (margin) if required by a scanner
generator.parameters.barcode.is_quiet_zone_visible = True
generator.parameters.barcode.quiet_zone = 10   # 10 pixels margin on each side
```

*ヒント*: バーコードを印刷する場合は、目標 DPI での可読性を保つために `x_dimension` と `bar_height` を比例して増やしてください。

## 手順 5: バーコード画像を保存する

最後に、生成された画像をファイルに書き出します。Aspose.Barcode は PNG、JPEG、BMP など多数の形式をサポートしています。

```python
output_path = "output/extended_codetext.png"
generator.save(output_path)
print(f"Barcode saved as {output_path}")
```

`save` を呼び出す前に、`output` フォルダーが存在することを確認するか、`os.makedirs("output", exist_ok=True)` で作成してください。

### 期待される結果

`extended_codetext.png` を開くと、数値文字列 `1234567890` の後に中国語文字「特殊字符」をエンコードした Code 128 バーコードが表示されます。ECI を認識する最新のスキャナーで読み取ると、元の混合文字列が返ります。

![Barcode generated with how to generate barcode example](https://example.com/images/barcode-sample.png){: .align-center alt="バーコード生成例の画像"}

## よくある質問とエッジケース

### 別の文字セットが必要な場合は？

ISO/IEC 18004 テーブルから適切な ECI 値を選択してください。例として、ECI 27 は ISO‑8859‑1（Latin‑1）を表します。`add_eci_codetext` の数値識別子をそれに合わせて置き換えます。

### 複数の ECI ブロックを埋め込めますか？

はい。`add_eci_codetext` を複数回呼び出します。ビルダーはブロック間に必要な ECI スイッチコードを挿入し、追加した順序を保持します。

### ジェネレータは ECI を使用した QR コードをサポートしていますか？

もちろんです。`barcode.Symbology.CODE_128` を `barcode.Symbology.QR` に置き換え、`generator.parameters.qr` を介して QR 固有のパラメータ（例: 誤り訂正レベル）を調整してください。

```python
generator.parameters.qr.error_correction_level = barcode.QRErrorLevel.H
```

### 非常に長いデータ文字列を扱うには？

Code 128 のような一次元バーコードでは、拡張コードテキスト使用時の最大長は約 80 文字です。それを超える場合は、数千文字を格納できる QR や Data Matrix といった二次元シンボロジーへの切り替えを検討してください。

## 完全な実行可能スクリプト

以下は `generate_extended_barcode.py` というファイル名でコピー＆ペーストし、直接実行できる完全なプログラムです。

```python
import os
import aspose.barcode as barcode
from aspose.barcode.generation import ExtCodetextBuilder, BuildVersionInfo

# ------------------------------------------------------------------
# Optional: print library version – useful for troubleshooting
# ------------------------------------------------------------------
ver = BuildVersionInfo()
print("Assembly version :", ver.ASSEMBLY_VERSION)
print("Product version  :", f"{ver.PRODUCT_MAJOR}.{ver.PRODUCT_MINOR}")
print("Release date     :", ver.RELEASE_DATE)

# ------------------------------------------------------------------
# Build extended codetext: plain numbers + Chinese characters (ECI 26)
# ------------------------------------------------------------------
builder = ExtCodetextBuilder()
builder.add_plain_codetext("1234567890")          # plain numeric data
builder.add_eci_codetext(26, "特殊字符")          # Chinese characters using UTF‑8
extended_codetext = builder.get_extended_codetext()
print("Extended codetext :", extended_codetext)

# ------------------------------------------------------------------
# Create a Code128 generator – supports the extended codetext format
# ------------------------------------------------------------------
generator = barcode.generator.BarcodeGenerator(
    barcode.Symbology.CODE_128,
    extended_codetext
)

# ------------------------------------------------------------------
# Customize appearance (size, quiet zone, etc.)
# ------------------------------------------------------------------
generator.parameters.barcode.x_dimension = 2
generator.parameters.barcode.bar_height = 50
generator.parameters.barcode.is_quiet_zone_visible = True
generator.parameters.barcode.quiet_zone = 10

# ------------------------------------------------------------------
# Ensure output directory exists and save the image
# ------------------------------------------------------------------
output_dir = "output"
os.makedirs(output_dir, exist_ok=True)
output_path = os.path.join(output_dir, "extended


## 次に学ぶべきことは？

以下のチュートリアルは、本ガイドで示した手法を基にした密接に関連するトピックをカバーしています。各リソースには、ステップバイステップの解説と完全な動作コード例が含まれており、追加の API 機能を習得し、独自プロジェクトで代替実装アプローチを探求するのに役立ちます。

- [Aspose.BarCode を使用した補足スペースカスタマイズ付きバーコード画像の生成方法](/barcode/english/net/supplemental-barcode-data/supplemental-barcode-space-customization/)
- [Aspose.BarCode を使用した Java でのバーコード画像生成方法](/barcode/english/java/barcode-rendering-techniques/)
- [.NET 用 Aspose.BarCode で DataMatrix バーコードを生成する方法](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-macro-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}