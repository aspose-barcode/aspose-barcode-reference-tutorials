---
category: general
date: 2026-11-23
description: Aspose.BarCode を使用して Python でバーコード画像を生成する方法。Planet バーコードの作成、X ディメンションの調整、空白バーの
  PNG 出力を学びます。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to generate barcode
- Python barcode generation
- Aspose.BarCode library
- Planet barcode symbology
- empty bars barcode
- barcode image PNG
language: ja
lastmod: 2026-11-23
og_description: Aspose.BarCode を使用して Python でバーコードを生成する方法。このチュートリアルでは、空白のバーを持つ Planet
  バーコードを作成し、PNG として保存する手順を説明します。
og_image_alt: Screenshot of Python code that generates a Planet barcode with empty
  bars saved as a PNG file
og_title: Pythonでバーコードを生成する方法 – 完全ガイド
schemas:
- author: Aspose
  dateModified: '2026-11-23'
  description: How to generate barcode images in Python with Aspose.BarCode. Learn
    to create a Planet barcode, adjust X‑dimension, and output an empty‑bars PNG.
  headline: How to generate barcode images in Python using Aspose.BarCode
  type: TechArticle
- description: How to generate barcode images in Python with Aspose.BarCode. Learn
    to create a Planet barcode, adjust X‑dimension, and output an empty‑bars PNG.
  name: How to generate barcode images in Python using Aspose.BarCode
  steps:
  - name: Switching to a different symbology
    text: 'If you need a QR code, Code 128, or any other format, replace `EncodeTypes.Planet`
      with the appropriate enum value:'
  - name: Changing the image format
    text: 'Aspose.BarCode supports PNG, JPEG, BMP, and TIFF. To generate a JPEG instead:'
  - name: Adjusting image size without losing quality
    text: 'You can control the overall image dimensions via the `resolution` property
      or by scaling the X‑dimension and Y‑dimension together. For high‑resolution
      prints, set a higher DPI:'
  - name: Handling long data strings
    text: 'The Planet symbology has a limited data capacity (up to 8 characters).
      If you try to encode a longer string, the generator raises an exception. Validate
      the length before creating the barcode:'
  type: HowTo
tags:
- barcode
- Python
- Aspose
title: Aspose.BarCode を使用して Python でバーコード画像を生成する方法
url: /ja/python-java/general/how-to-generate-barcode-images-in-python-using-aspose-barcod/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# PythonでAspose.BarCodeを使用してバーコード画像を生成する方法

Pythonでバーコード画像を生成するのは、Aspose.BarCodeライブラリを使用すれば簡単です。このガイドでは、Planetシンボロジーを使用してバーコードを生成し、Xディメンションをカスタマイズし、空バー（empty‑bars）スタイルのPNGファイルを作成する手順をステップバイステップで示します。

プロジェクトにコピーできる完全な実行可能スクリプトが示されます。また、別のシンボロジーや出力形式への切り替えなど、一般的なバリエーションもカバーしているので、要件に合わせてソリューションを適用できます。

## 前提条件

* Python 3.8以上がインストールされていること。
* ターミナルまたはコマンドプロンプトへのアクセスがあること。
* 有効なAspose.BarCode for Pythonライセンス（無料評価版でもテストは可能）。
* `pip`によるPythonパッケージ管理の基本的な知識。

## 手順 1: Aspose.BarCode パッケージのインストール

AsposeはPython APIをPyPIで配布しています。標準のパッケージマネージャでインストールします。

```bash
pip install asposebarcode
```

> **プロのコツ:** 仮想環境（`python -m venv venv`）を使用して、依存関係を他のプロジェクトから分離しましょう。

## 手順 2: 必要な Aspose.BarCode クラスのインポート

インポート文で、ジェネレータ、シンボロジーの列挙、画像フォーマットの列挙を取得します。

```python
from asposebarcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat
```

* `BarcodeGenerator` はバーコードオブジェクトを作成します。
* `EncodeTypes` はサポートされているすべてのシンボロジーを列挙します。ここでは `Planet` を使用します。
* `BarCodeImageFormat` は出力ファイルタイプ（PNG、JPEG など）を定義します。

## 手順 3: Planet シンボロジー用のバーコードジェネレータを作成

目的のシンボロジーとエンコードしたいデータでジェネレータをインスタンス化します。

```python
# Create a generator for the Planet symbology with the value "123456"
barcode = BarcodeGenerator(EncodeTypes.Planet, "123456")
```

`Planet` シンボロジーは円形のパターンを生成し、装飾やブランディングに最適です。

## 手順 4: X ディメンション（モジュール幅）の調整

X ディメンションは最小バー（モジュール）の幅を制御します。4 ピクセルに設定すると、鮮明で高解像度の画像が得られます。

```python
# Set the module width to 4 pixels
barcode.parameters.barcode.x_dimension.pixels = 4
```

印刷や画面表示でスケーラブルなバーコードが必要な場合、X ディメンションの変更が有用です。

## 手順 5: 空バー（empty‑bars）スタイルのために塗りつぶしバーを無効化

空バーのバーコードはバーの輪郭だけを表示し、デザイン重視のアプリケーションで役立ちます。

```python
# Produce an empty‑bars barcode by disabling filled bars
barcode.parameters.barcode.filled_bars = False
```

`filled_bars` が `False` の場合、ジェネレータは実体の代わりに空洞の形状を描画します。

## 手順 6: バーコード画像を PNG ファイルとして保存

最後に、バーコードをディスクに書き込みます。PNG はロスレスで広くサポートされています。

```python
# Save the barcode as a PNG image
barcode.save("output/PlanetEmptyBars.png", BarCodeImageFormat.Png)
```

`save` メソッドは、対象ディレクトリが存在しない場合に自動的に作成します。

## 完全な例 – 実行可能なスクリプト全体

すべての要素を組み合わせると、すぐに実行できる自己完結型プログラムが得られます。

```python
# -*- coding: utf-8 -*-
"""
Generate a Planet barcode with empty bars and save it as PNG.
Requires: asposebarcode (pip install asposebarcode)
"""

from asposebarcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat
import os

# Ensure the output directory exists
output_dir = "output"
os.makedirs(output_dir, exist_ok=True)

# Step 1: Create the generator
barcode = BarcodeGenerator(EncodeTypes.Planet, "123456")

# Step 2: Configure appearance
barcode.parameters.barcode.x_dimension.pixels = 4   # X‑dimension = 4 px
barcode.parameters.barcode.filled_bars = False    # empty‑bars style

# Step 3: Save as PNG
output_path = os.path.join(output_dir, "PlanetEmptyBars.png")
barcode.save(output_path, BarCodeImageFormat.Png)

print(f"Barcode saved to: {output_path}")
```

**期待される出力:** スクリプトを実行すると、`output/PlanetEmptyBars.png` に 200 × 200 ピクセルの Planet バーコード（空バー）の画像が生成されます。任意の画像ビューアでファイルを開くと、内部に数値がエンコードされた円形パターンが表示されます。

## 一般的なバリエーションとエッジケース

### 別のシンボロジーへの切り替え

QR コード、Code 128、またはその他の形式が必要な場合は、`EncodeTypes.Planet` を適切な列挙値に置き換えてください。

```python
barcode = BarcodeGenerator(EncodeTypes.QR, "https://example.com")
```

### 画像フォーマットの変更

Aspose.BarCode は PNG、JPEG、BMP、TIFF をサポートしています。JPEG を生成するには次のようにします。

```python
barcode.save("output/PlanetEmptyBars.jpg", BarCodeImageFormat.Jpeg)
```

### 品質を損なわずに画像サイズを調整

`resolution` プロパティで全体の画像サイズを制御したり、X ディメンションと Y ディメンションを同時にスケーリングしたりできます。高解像度印刷の場合は、DPI を高く設定してください。

```python
barcode.parameters.image.resolution = 300  # 300 dpi for print quality
```

### 長いデータ文字列の処理

Planet シンボロジーはデータ容量が制限されており（最大 8 文字）、長い文字列をエンコードしようとするとジェネレータが例外をスローします。バーコード作成前に長さを検証してください。

```python
data = "123456"
if len(data) > 8:
    raise ValueError("Planet barcode supports a maximum of 8 characters.")
```

## ヒントと落とし穴

* **ライセンスの有効化:** 本番環境では、スクリプトの早い段階で `asposebarcode.License().set_license("Aspose.Total.lic")` を呼び出してライセンスファイルを適用してください。この手順を省略すると、出力画像に透かしが入ります。
* **スレッド安全性:** `BarcodeGenerator` インスタンスはスレッドセーフではありません。並列でバーコードを生成する場合は、スレッドごとに別々のインスタンスを作成してください。
* **パフォーマンス:** `barcode.value = "new data"` のようにジェネレータを再利用して複数の値を処理する方が、毎回新しいオブジェクトを構築するより高速です。
* **ファイルパス:** `os.path.join` を使用してプラットフォームに依存しないパスを構築しましょう。特に Linux や macOS にデプロイする際に有用です。

## 結論

これで、Python で Aspose.BarCode を使用してバーコード画像を生成し、X ディメンションをカスタマイズし、空バー（empty‑bars）スタイルを作成して PNG として保存する方法が分かりました。完全な例は他のシンボロジーや出力フォーマット、ビジュアルスタイルにも適用でき、アプリケーションのあらゆるバーコード関連機能の柔軟な基盤となります。

**次のステップ:** *Python barcode generation* などのキーワードを試しながら異なるエンコーディングを探索したり、*barcode image PNG* の圧縮設定を実験したり、Flask や FastAPI を使って生成した画像をウェブサービスに統合したりしてください。コーディングを楽しんでください！

## 次に学ぶべきことは？

以下のチュートリアルは、本ガイドで示した手法を基にした密接に関連するトピックを扱っています。各リソースには、ステップバイステップの解説と完全な動作コード例が含まれており、追加の API 機能を習得し、独自プロジェクトで代替実装アプローチを検討するのに役立ちます。

- [How to create planet barcode PNG with Python](/barcode/english/python-java/general/how-to-create-planet-barcode-png-with-python/)
- [How to create barcode image in Python with Aspose.BarCode](/barcode/english/python-java/general/how-to-create-barcode-image-in-python-with-aspose-barcode/)
- [How to Generate QR Code Image in Python with Aspose.Barcode – Full Guide](/barcode/english/python/general/how-to-generate-qr-code-image-in-python-with-aspose-barcode/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}