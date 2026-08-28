---
category: general
date: 2026-08-09
description: Aspose.BarCode を使用して Python で QR バーコードを作成します。拡張コードテキストの構築方法、外観の調整、画像の保存方法をすべて一つのチュートリアルで学びましょう。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create QR barcode
- Aspose.BarCode Python
- extended codetext QR
- QR code generation Python
- barcode visual customization
language: ja
lastmod: 2026-08-09
og_description: Aspose.BarCode を使用して Python で QR バーコードを作成します。このガイドでは、拡張コードテキストの構築、視覚パラメータの設定、画像のエクスポート方法を示します。
og_image_alt: Screenshot of a generated QR barcode created with Aspose.BarCode in
  Python
og_title: PythonでAspose.BarCodeを使用してQRバーコードを作成する – 完全コード例
schemas:
- author: Aspose
  dateModified: '2026-08-09'
  description: Create QR barcode in Python using Aspose.BarCode. Learn how to build
    extended codetext, adjust appearance, and save the image—all in one tutorial.
  headline: Create QR barcode with Aspose.BarCode in Python – step‑by‑step guide
  type: TechArticle
- description: Create QR barcode in Python using Aspose.BarCode. Learn how to build
    extended codetext, adjust appearance, and save the image—all in one tutorial.
  name: Create QR barcode with Aspose.BarCode in Python – step‑by‑step guide
  steps:
  - name: Common variations
    text: '- **Multiple ECI segments:** Call `add_eci_codetext` multiple times to
      mix several languages. - **Different ECI identifiers:** Use `27` for ISO‑8859‑1,
      `28` for ISO‑8859‑2, etc., depending on your target encoding.'
  - name: Edge case handling
    text: '- **High‑density data:** If the encoded data is large, you may need to
      increase `x_dimension` or choose a higher error‑correction level (via `qr_generator.parameters.qr.error_correction_level`).
      - **Transparent background:** Set `qr_generator.parameters.barcode.bg_color
      = Color.Transparent` for PNGs'
  - name: Verifying the result
    text: 'Open the saved file in any image viewer. You should see a QR code that,
      when scanned, returns the combined string:'
  type: HowTo
tags:
- QR code
- Python
- Aspose
- Barcode generation
title: PythonでAspose.BarCodeを使ってQRバーコードを作成する – ステップバイステップガイド
url: /ja/python/general/create-qr-barcode-with-aspose-barcode-in-python-step-by-step/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# PythonでAspose.BarCodeを使用してQRバーコードを作成する – ステップバイステップガイド

Pythonで**QRバーコードを作成**する必要がある場合、このチュートリアルではAspose.BarCodeライブラリを使用した全プロセスを順を追って説明します。製品ID、多言語テキスト、カスタムデータのエンコードなど、拡張コードテキストの構築、ビジュアル設定の調整、最終画像の保存を単一の実行可能スクリプトで行う方法が分かります。

この例ではライブラリのバージョン表示方法も示しており、互換性のあるリリースを使用しているか確認できます。このガイドの最後までに、すぐに使用できるQRバーコード画像と各設定オプションの明確な理解が得られます。

## 前提条件

- Python 3.8+ がインストールされていること。
- `aspose-barcode` パッケージ（`pip install aspose-barcode` でインストール）。
- Python構文の基本的な知識があること。
- PNGファイルを保存する出力ディレクトリへの書き込み権限があること。

> **プロのコツ:** 仮想環境を使用して、他のプロジェクトとのバージョン競合を回避しましょう。

## 手順 1: Aspose.BarCode ライブラリのバージョンを確認する

ライブラリのバージョンを表示することで、拡張コードテキストとQRエンコードをサポートするリリースを使用していることが確認できます。

```python
from asposebarcode import BuildVersionInfo

# Show the current Aspose.BarCode version
version_info = BuildVersionInfo()
print(
    f"Aspose.BarCode version: {version_info.PRODUCT} "
    f"{version_info.PRODUCT_MAJOR}.{version_info.PRODUCT_MINOR} "
    f"(released {version_info.RELEASE_DATE})"
)
```

**なぜ重要か:**  
古いリリースには、プレーンとECIセグメントの混在に必要な `ExtCodetextBuilder` クラスが含まれていない場合があります。バージョンを確認することで、後のワークフローでのランタイムエラーを防止できます。

## 手順 2: 拡張コードテキスト文字列を構築する

拡張コードテキストを使用すると、プレーンなASCIIデータとUnicode（ECI）セグメントを組み合わせることができ、マルチリンガルQRコードに必須です。

```python
from asposebarcode import ExtCodetextBuilder

# Initialize the builder
ext_builder = ExtCodetextBuilder()

# Add a plain segment – typically a product ID or numeric code
ext_builder.add_plain_codetext("ABC12345")

# Add an ECI segment – here we embed Japanese greeting "こんにちは"
# 26 is the ECI identifier for UTF‑8 encoding
ext_builder.add_eci_codetext(26, "こんにちは")

# Retrieve the full extended codetext that the QR generator will use
extended_codetext = ext_builder.get_extended_codetext()
print(f"Generated extended codetext: {extended_codetext}")
```

**なぜ重要か:**  
`add_plain_codetext` メソッドはデータを標準ASCIIとして保存し、`add_eci_codetext` は適切なECI識別子を付けてUnicodeブロックを前置します。このアプローチにより、QRスキャナーは日本語テキストを正しく解釈し、文字化けを防止します。

### 一般的なバリエーション

- **複数のECIセグメント:** `add_eci_codetext` を複数回呼び出して複数言語を混在させます。
- **異なるECI識別子:** ターゲットのエンコーディングに応じて、`27` を ISO‑8859‑1、`28` を ISO‑8859‑2 などに使用します。

## 手順 3: 拡張コードテキストを使用してQRバーコードを生成する

適切にフォーマットされた文字列が用意できたので、QRコードを作成できます。

```python
from asposebarcode import BarCodeGenerator, EncodeTypes, BarCodeImageFormat

# Create the QR generator with the extended codetext
qr_generator = BarCodeGenerator(EncodeTypes.QR, extended_codetext)
```

**なぜ重要か:**  
`EncodeTypes.QR` はAspose.BarCodeにQRシンボルを使用させます。`extended_codetext` を直接渡すことで、混在データがQRマトリックスに結び付けられ、プレーン部分とUnicode部分の両方が保持されます。

## 手順 4: ビジュアル外観を調整する（任意だが推奨）

バーコードのビジュアルパラメータを微調整することで、スキャンの信頼性が向上し、ブランドガイドラインに合わせることができます。

```python
# Set module (pixel) size – larger values increase overall image size
qr_generator.parameters.barcode.x_dimension = 4      # each module = 4 pixels

# Set border thickness – a thin white border helps scanners isolate the QR code
qr_generator.parameters.barcode.border_width = 2    # 2-pixel border
```

**なぜ重要か:**  
- **`x_dimension`** は各QRモジュールのサイズを制御します。小さすぎると低解像度デバイスで読み取りエラーが発生する可能性があります。  
- **`border_width`** はクワイエットゾーン（余白）を追加します。一部のスキャナーは最低でも4モジュールのクワイエットゾーンを必要とします。ライブラリは自動で追加しますが、さらなる安全のために増やすこともできます。

### エッジケースの処理

- **高密度データ:** エンコードするデータが大きい場合、`x_dimension` を増やすか、より高いエラーレベル（`qr_generator.parameters.qr.error_correction_level` 経由）を選択する必要があります。  
- **透過背景:** アルファチャンネル付きPNGの場合、`qr_generator.parameters.barcode.bg_color = Color.Transparent` を設定します。

## 手順 5: QRバーコード画像を保存する

最後に、画像を好みの形式でディスクに書き込みます。

```python
# Define output path – replace YOUR_DIRECTORY with an actual folder
output_file = "YOUR_DIRECTORY/extended_qr.png"

# Save as PNG; other formats include JPEG, BMP, GIF, TIFF
qr_generator.save(output_file, BarCodeImageFormat.PNG)
print(f"Barcode saved to {output_file}")
```

**なぜ重要か:**  
PNGで保存するとロスレス品質が保たれ、鮮明なエッジが必要なQRコードに最適です。Webアプリケーションで別の形式が必要な場合は、`BarCodeImageFormat` 列挙体を変更するだけです。

### 結果の検証

任意の画像ビューアで保存されたファイルを開きます。スキャンすると結合された文字列が返されるQRコードが表示されるはずです：

```
ABC12345
こんにちは
```

ほとんどの最新QRスキャナーアプリはプレーンセグメントを先に表示し、続いて日本語の挨拶を正しくレンダリングします。

---

## 完全に実行可能なスクリプト

以下のブロック全体を `create_qr_barcode.py` という名前のファイルにコピーし、`python create_qr_barcode.py` で実行してください。`YOUR_DIRECTORY` をマシン上の書き込み可能なフォルダーに変更します。

```python
# create_qr_barcode.py
from asposebarcode import (
    BuildVersionInfo,
    ExtCodetextBuilder,
    BarCodeGenerator,
    EncodeTypes,
    BarCodeImageFormat,
)

# 1️⃣ Display library version
version_info = BuildVersionInfo()
print(
    f"Aspose.BarCode version: {version_info.PRODUCT} "
    f"{version_info.PRODUCT_MAJOR}.{version_info.PRODUCT_MINOR} "
    f"(released {version_info.RELEASE_DATE})"
)

# 2️⃣ Build extended codetext (plain + Japanese Unicode)
ext_builder = ExtCodetextBuilder()
ext_builder.add_plain_codetext("ABC12345")
ext_builder.add_eci_codetext(26, "こんにちは")
extended_codetext = ext_builder.get_extended_codetext()
print(f"Generated extended codetext: {extended_codetext}")

# 3️⃣ Create QR generator
qr_generator = BarCodeGenerator(EncodeTypes.QR, extended_codetext)

# 4️⃣ Optional visual tweaks
qr_generator.parameters.barcode.x_dimension = 4
qr_generator.parameters.barcode.border_width = 2

# 5️⃣ Save image
output_file = "YOUR_DIRECTORY/extended_qr.png"
qr_generator.save(output_file, BarCodeImageFormat.PNG)
print(f"Barcode saved to {output_file}")
```

このスクリプトを実行すると、バージョン、拡張コードテキストが表示され、PNGファイルが作成されたことが確認できます。

---

## 結論

これで、PythonでAspose.BarCodeを使用して**QRバーコード**画像を作成する方法が分かりました。このチュートリアルでは以下をカバーしました：

1. ライブラリのバージョンを確認する。
2. プレーンとECI（Unicode）セグメントを組み合わせた拡張コードテキストを構築する。
3. QRコードを生成する。
4. モジュールサイズやボーダー幅などのビジュアルパラメータをカスタマイズする。
5. 最終画像をPNG形式で保存する。

ここからは以下を検討できます：

- エラーレベルを変更する（`qr_generator.parameters.qr.error_correction_level`）。
- ロゴや背景画像を追加する（`qr_generator.parameters.qr.logo`）。
- SVGなどの他形式へエクスポートして、スケーラブルなウェブグラフィックにする。
- FlaskやDjangoのエンドポイントに統合し、オンザフライでQRを生成する。

さまざまなデータペイロードやビジュアル設定を試して、アプリケーションのブランドやスキャン要件に合わせてください。コーディングを楽しんで！

## 次に学ぶべきことは？

以下のチュートリアルは、本ガイドで示した手法を基にした密接に関連するトピックを取り上げています。各リソースには、完全な動作コード例とステップバイステップの解説が含まれており、追加のAPI機能を習得し、プロジェクトで代替実装アプローチを検討するのに役立ちます。

- [Aspose.BarCode for .NETでdotcode拡張コードテキストを作成する方法](/barcode/english/net/dotcode-barcode-configuration/dotcode-extended-code-text-configuration/)
- [Aspose .NETでDataMatrixコードテキストを設定してバーコードを作成する](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-extended-code-text-configuration/)
- [Aspose.BarCode for .NETでITF-14のバーコードクワイエットゾーンを作成する方法](/barcode/english/net/itf-14-barcode-customization/itf-14-barcode-quiet-zone-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}