---
category: general
date: 2026-08-12
description: Python を使ってバーコードを素早く生成する方法。データからバーコードを作成し、単一のライブラリでバーコード画像をエクスポートする方法を学びましょう。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to generate barcode
- create barcode from data
- export barcode image
- Python barcode generation
- Aspose.BarCode tutorial
language: ja
lastmod: 2026-08-12
og_description: Aspose.BarCode を使用して Python でバーコードを生成する方法。データからバーコードを作成し、バーコード画像を
  PNG としてエクスポートするガイドです。
og_image_alt: Screenshot showing how to generate barcode with Python code
og_title: Pythonでバーコードを生成する方法 – 速くて信頼できるガイド
schemas:
- author: Aspose
  dateModified: '2026-08-12'
  description: How to generate barcode quickly using Python. Learn to create barcode
    from data and export barcode image with a single library.
  headline: How to generate barcode in Python – complete step‑by‑step guide
  type: TechArticle
- description: How to generate barcode quickly using Python. Learn to create barcode
    from data and export barcode image with a single library.
  name: How to generate barcode in Python – complete step‑by‑step guide
  steps:
  - name: 1. Import the required classes
    text: '```python from aspose.barcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat
      ```'
  - name: 2. Create barcode from data
    text: The first step is to **create barcode from data**. The `BarcodeGenerator`
      constructor takes the symbology and the raw string you want to encode.
  - name: 3. Adjust the X‑dimension (module width)
    text: The X‑dimension controls the width of each barcode module (the thin bar).
      Setting it to 4 pixels gives a clear, readable image without making the file
      too large.
  - name: 4. Export barcode image (filled style)
    text: Now you can **export barcode image** using the `save` method. The example
      saves a PNG file, but you can choose JPEG, BMP, or TIFF by changing the `BarCodeImageFormat`
      enum.
  - name: 5. Create a second generator for an outline‑only barcode
    text: If you need an outline version (empty bars), you must create a new generator
      because the `filled_bars` flag cannot be toggled after the image is saved.
  - name: 6. Apply the same X‑dimension setting
    text: When you create a second generator, you must repeat any visual settings
      you want to keep consistent.
  - name: 7. Disable filled bars for an outline barcode
    text: Setting `filled_bars` to `False` tells the renderer to draw only the outlines
      of each module, producing a lighter image that can be useful for design purposes.
  - name: 8. Export the outline barcode image
    text: Finally, **export barcode image** again, this time storing the outline version.
  - name: Next steps
    text: '* Explore other symbologies such as QR, Code‑128, or DataMatrix by swapping
      `EncodeTypes.Planet` with the desired value. * Integrate the generated PNG files
      into PDF reports using libraries like `ReportLab` or `PyPDF2`. * Experiment
      with dynamic X‑dimension values to adapt barcode size based on scre'
  type: HowTo
tags:
- barcode
- Python
- image export
title: Pythonでバーコードを生成する方法 – 完全ステップバイステップガイド
url: /ja/python-java/general/how-to-generate-barcode-in-python-complete-step-by-step-guid/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Pythonでバーコードを生成する方法 – 完全ステップバイステップガイド

Pythonアプリケーションで **バーコードの生成方法** が必要な場合、このチュートリアルでは必要な正確なコードを示します。**データからバーコードを作成** し、外観を調整し、**バーコード画像をPNGファイルとしてエクスポート** する方法を学びます—すべて10行未満のコードで実現できます。

バーコードの生成はビジネスロジックの別個の関心事のように感じられるかもしれませんが、単一のライブラリを使用すれば既存のコードベースに組み込んで処理を行うことができます。以下のセクションでは、完全に実行可能な例を示し、各行が重要な理由を理解し、モジュール幅の変更やアウトラインのみのバーコード描画といった一般的なバリエーションを紹介します。

## Aspose.BarCode ライブラリでバーコードを生成する方法

Python 用 (via .NET) の Aspose.BarCode ライブラリは、この記事で使用する Planet バーコードを含む多くのシンボロジーに対してシンプルな API を提供します。開始する前に、パッケージがインストールされていることを確認してください：

```bash
pip install aspose-barcode
```

> **プロのコツ:** 仮想環境を使用して、他のプロジェクトとのバージョン競合を回避しましょう。

### 1. 必要なクラスをインポートする

```python
from aspose.barcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat
```

これらのインポートにより、ジェネレータクラス、バーコードタイプの列挙、および結果を保存する際に使用する画像フォーマット列挙にアクセスできます。

### 2. データからバーコードを作成する

最初のステップは **データからバーコードを作成** することです。`BarcodeGenerator` コンストラクタはシンボロジーとエンコードしたい生文字列を受け取ります。

```python
# Step 1: Create a barcode generator for the Planet symbology with data "123456"
barcode_filled = BarcodeGenerator(EncodeTypes.Planet, "123456")
```

`EncodeTypes.Planet` の値は Planet バーコードを選択し、`"123456"` は最終画像に表示されるペイロードです。

### 3. X‑dimension（モジュール幅）を調整する

X‑dimension は各バーコードモジュール（細いバー）の幅を制御します。4 ピクセルに設定すると、ファイルサイズが大きくなりすぎず、クリアで読みやすい画像になります。

```python
# Step 2: Set the X‑dimension (module width) to 4 pixels
barcode_filled.parameters.barcode.x_dimension.pixels = 4
```

> **重要な理由:** 大きな X‑dimension は低解像度プリンターでのスキャン信頼性を向上させ、逆に小さな値はウェブ使用時のファイルサイズを削減します。

### 4. バーコード画像をエクスポートする（塗りつぶしスタイル）

これで `save` メソッドを使用して **バーコード画像をエクスポート** できます。例では PNG ファイルを保存していますが、`BarCodeImageFormat` 列挙を変更すれば JPEG、BMP、TIFF も選択可能です。

```python
# Step 3: Save the barcode using the default filled‑bars style
barcode_filled.save("YOUR_DIRECTORY/PlanetFilled.png", BarCodeImageFormat.Png)
```

ファイル `PlanetFilled.png` には完全に塗りつぶされた Planet バーコードが含まれており、印刷や PDF への埋め込みにすぐ使用できます。

### 5. アウトラインのみのバーコード用に2つ目のジェネレータを作成する

アウトラインバージョン（バーが空）の必要がある場合、画像保存後に `filled_bars` フラグを切り替えることはできないため、新しいジェネレータを作成する必要があります。

```python
# Step 4: Create a second generator for the same data to illustrate empty bars
barcode_empty = BarcodeGenerator(EncodeTypes.Planet, "123456")
```

### 6. 同じ X‑dimension 設定を適用する

2つ目のジェネレータを作成する際は、一貫性を保つために視覚設定を再度適用する必要があります。

```python
# Step 5: Apply the same X‑dimension setting
barcode_empty.parameters.barcode.x_dimension.pixels = 4
```

### 7. アウトラインバーコードの塗りつぶしバーを無効にする

`filled_bars` を `False` に設定すると、レンダラは各モジュールのアウトラインのみを描画し、デザイン目的で役立つ軽い画像が生成されます。

```python
# Step 6: Disable filled bars to produce an outline‑only barcode
barcode_empty.parameters.barcode.filled_bars = False
```

### 8. アウトラインバーコード画像をエクスポートする

最後に、再度 **バーコード画像をエクスポート** し、今回はアウトラインバージョンを保存します。

```python
# Step 7: Save the outline barcode
barcode_empty.save("YOUR_DIRECTORY/PlanetEmpty.png", BarCodeImageFormat.Png)
```

これで 2 つの PNG ファイルが作成されました：実線バーの `PlanetFilled.png` とアウトラインのみの `PlanetEmpty.png` です。

## 他の形式でバーコード画像をエクスポートする（オプション）

`save` メソッドは複数の形式をサポートしています。90 % の品質で JPEG としてエクスポートするには：

```python
barcode_filled.save(
    "YOUR_DIRECTORY/PlanetFilled.jpg",
    BarCodeImageFormat.Jpeg,
    quality=90
)
```

ウェブ用に透過背景が必要な場合は、アルファチャンネル付きの PNG を選択してください：

```python
barcode_filled.parameters.background_color = None  # disables background fill
barcode_filled.save("YOUR_DIRECTORY/PlanetTransparent.png", BarCodeImageFormat.Png)
```

## 一般的なバリエーションとエッジケース

| シナリオ | 必要な変更 | コードスニペット |
|----------|---------------|--------------|
| **異なるシンボロジー**（例：QR） | 別の `EncodeTypes` 値を使用する | `BarcodeGenerator(EncodeTypes.QR, "https://example.com")` |
| **カスタム前景色** | `fore_color` を設定する | `barcode_filled.parameters.barcode.fore_color = Color.Blue` |
| **高解像度** | `image_width` と `image_height` で DPI を上げる | `barcode_filled.parameters.image_width = 300; barcode_filled.parameters.image_height = 150` |
| **大きなデータ文字列** | データ長がシンボロジー仕様に合うことを確認する | ジェネレータ作成前に長さを検証する |

> **注意:** 選択したシンボロジーの最大長を超えるデータを提供すると、ランタイム例外が発生します。常に文字列長を検証するか、`ArgumentException` を捕捉してください。

## 完全な実行可能サンプル

以下は `generate_planet_barcode.py` という名前のファイルにコピー＆ペーストできる完全なスクリプトです。`YOUR_DIRECTORY` を、マシン上に存在するフォルダーに変更してください。

```python
# generate_planet_barcode.py
from aspose.barcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat

def generate_barcodes(output_dir: str):
    # Filled‑bars barcode
    filled = BarcodeGenerator(EncodeTypes.Planet, "123456")
    filled.parameters.barcode.x_dimension.pixels = 4
    filled.save(f"{output_dir}/PlanetFilled.png", BarCodeImageFormat.Png)

    # Outline‑only barcode
    empty = BarcodeGenerator(EncodeTypes.Planet, "123456")
    empty.parameters.barcode.x_dimension.pixels = 4
    empty.parameters.barcode.filled_bars = False
    empty.save(f"{output_dir}/PlanetEmpty.png", BarCodeImageFormat.Png)

if __name__ == "__main__":
    import os
    output_path = "YOUR_DIRECTORY"
    os.makedirs(output_path, exist_ok=True)
    generate_barcodes(output_path)
    print("Barcodes generated successfully.")
```

このスクリプトを実行すると、指定ディレクトリに 2 つの PNG ファイルが生成されます。任意の画像ビューアで画像を開いて出力を確認してください。どちらも文字列 `123456` をエンコードした Planet バーコードが表示されます。

## 結論

これで、Aspose.BarCode を使用して Python で **バーコードを生成する方法**、**データからバーコードを作成する方法**、そして塗りつぶしスタイルとアウトラインスタイルの両方で **バーコード画像をエクスポートする方法** が分かりました。同じパターンは他のシンボロジー、画像形式、視覚カスタマイズにも適用でき、アプリケーション内のあらゆるバーコード関連機能の柔軟な基盤となります。

### 次のステップ

* QR、Code‑128、DataMatrix などの他のシンボロジーを調査し、`EncodeTypes.Planet` を目的の値に置き換えてみてください。  
* `ReportLab` や `PyPDF2` などのライブラリを使用して、生成した PNG ファイルを PDF レポートに統合します。  
* 画面解像度やプリンター DPI に応じてバーコードサイズを調整できるよう、動的な X‑dimension 値を試してみてください。

コーディングを楽しんでください。また、例を自由にカスタマイズしてご自身のプロジェクト要件に合わせてください！

## 次に学ぶべきことは？

以下のチュートリアルは、本ガイドで示した手法を基にした密接に関連するトピックを扱っています。各リソースには、ステップバイステップの解説と完全な動作コード例が含まれており、追加の API 機能を習得し、プロジェクトで代替実装アプローチを検討するのに役立ちます。

- [JavaでAspose.BarCodeを使用してバーコード画像を生成する方法](/barcode/english/java/barcode-rendering-techniques/)
- [Javaでバーコードを生成する – 完全設定ガイド](/barcode/english/java/barcode-configuration/)
- [JavaでAspose.BarCodeを使用してcode128バーコード画像を作成する方法](/barcode/english/java/advanced-settings-and-optimization/saving-barcode-images-different-formats/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}