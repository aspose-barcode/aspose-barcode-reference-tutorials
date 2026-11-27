---
category: general
date: 2026-11-27
description: DataBar Omni‑Directional バーコードジェネレータでバーコードのバー高さを調整する方法を学びましょう。ステップバイステップのコードで高さを30 pxと60 pxに設定する方法を示します。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- adjust barcode bar height
- DataBar Omni‑Directional barcode
- set XDimension
- barcode image format
- BarCodeImageFormat
- barcode generator python
language: ja
lastmod: 2026-11-27
og_description: Python を使用した DataBar Omni‑Directional バーコードジェネレータでバーの高さを調整します。高さや
  X‑ディメンションの設定方法、PNG 画像の保存手順を網羅した完全ガイドに従ってください。
og_image_alt: Screenshot of a DataBar Omni‑Directional barcode with adjusted bar height
og_title: DataBar Omni‑Directional ジェネレータでバーコードのバー高さを調整
schemas:
- author: GroupDocs
  dateModified: '2026-11-27'
  description: Learn how to adjust barcode bar height in a DataBar Omni‑Directional
    barcode generator. Step‑by‑step code shows setting heights to 30 px and 60 px.
  headline: How to adjust barcode bar height in DataBar Omni‑Directional generator
  type: TechArticle
tags:
- barcode
- python
- DataBar
- imaging
title: DataBar Omni‑Directional ジェネレーターでバーコードのバー高さを調整する方法
url: /ja/python-java/general/how-to-adjust-barcode-bar-height-in-databar-omni-directional/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# DataBar Omni‑Directional ジェネレータでバーコードのバー高さを調整する方法

DataBar Omni‑Directional バーコードの **バー高さを調整** したい場合は、このガイドで手順を確認できます。X‑ディメンションと画像形式はそのままに、バー高さを 30 px から 60 px に変更する完全な実行可能 Python サンプルを紹介します。

バーコードの視覚的寸法を変更することは、ラベルサイズやデザインガイドラインに合わせる必要がある場合に一般的な要件です。バー高さに加えて、**X‑ディメンション**（モジュールサイズ）を調整したり、PNG や JPEG など別の **バーコード画像形式** を選択したりすることもできます。

このチュートリアルで学べること：

* 必要なライブラリ（GroupDocs.Barcode for Python）のインストール
* DataBar Omni‑Directional バーコードジェネレータの作成
* `XDimension` でモジュールサイズを設定
* バー高さプロパティを 2 回調整
* 希望する **BarCodeImageFormat** で画像を保存

GroupDocs API の事前知識は不要です。Python の基本が分かっていればすぐに始められます。

## 前提条件

開始する前に以下を確認してください：

* Python 3.8 以上がインストール済み
* `groupdocs.barcode` パッケージ（`pip install groupdocs-barcode`）  
* PNG ファイルを書き込むフォルダーへの書き込み権限

**DataBar Omni‑Directional バーコード** に馴染みがない場合、これは 14 桁の GTIN をエンコードし、任意の向きからスキャンできるため小売業で広く使用されています。

## 手順 1: DataBar Omni‑Directional バーコードジェネレータをセットアップ

まず、必要なクラスをインポートし、エンコードしたい GTIN データでジェネレータをインスタンス化します。

```python
from groupdocs.barcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat

# Create a generator for a DataBar Omni‑Directional barcode
# The string "(01)12345678901231" follows the GS1 Application Identifier syntax
gen = BarcodeGenerator(EncodeTypes.DatabarOmniDirectional, "(01)12345678901231")
```

*ポイント:* `EncodeTypes.DatabarOmniDirectional` 定数は、ライブラリに Omni‑Directional シンボロジーを生成させる指示です。データ文字列には GTIN‑14 値を示す AI `(01)` が含まれます。

## 手順 2: X‑ディメンション（モジュールサイズ）を定義

X‑ディメンションは最細バーの幅を制御します。画面表示向けの一般的な値は **モジュールあたり 2 px** です。

```python
# Set the module (X‑dimension) size – 2 px per module
gen.parameters.barcode.x_dimension.pixels = 2
```

一貫した **set XDimension** を使用することで、異なるプリンターやスキャナーでもバーコードが正しくスケーリングされます。

## 手順 3: バー高さを 30 px に設定して画像を保存

まずバー高さプロパティを変更します。最初に使用する高さは **30 px** で、小さなラベルに適しています。

```python
# Define the first bar height (30 px)
gen.parameters.barcode.bar_height.pixels = 30

# Save the barcode as a PNG image
gen.save("output/DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png)
```

`BarCodeImageFormat.Png` 定数は、**バーコード画像形式** として PNG を選択し、ロスレス品質を保持します。

### 期待される結果

`DatabarBarHeight30Pixels.png` には、バー高さが 30 px の DataBar Omni‑Directional バーコードが含まれます。以下はプレースホルダーのプレビューです：

![30 px のバー高さを持つ DataBar バーコード](images/databar_30px.png "30 px のバー高さを持つ DataBar バーコード")

> **ヒント:** PNG を画像エディタで開くと、正確なバー高さが確認できます。狭いバーは先ほど定義した通り 2 px の幅です。

## 手順 4: バー高さを 60 px に変更して、より高いバーコードにする

貨物ラベルなど、視覚的に大きなフットプリントが必要な用途では、バー高さを **60 px** に増やすことができます。

```python
# Change the bar height to 60 px for a taller barcode
gen.parameters.barcode.bar_height.pixels = 60
```

変更されるのは `BarHeight` プロパティだけです。X‑ディメンションとエンコードはそのままなので、バーコードは引き続きスキャン可能です。

## 手順 5: 更新したバーコード画像を保存

最後に、より高いバーコードを別の PNG ファイルに書き出します。

```python
# Save the updated barcode image
gen.save("output/DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png)
```

### 期待される結果

`DatabarBarHeight60Pixels.png` は同じデータをエンコードしていますが、各バーの高さが 60 px になっています。視覚的な違いは以下の通りです：

![60 px のバー高さを持つ DataBar バーコード](images/databar_60px.png "60 px のバー高さを持つ DataBar バーコード")

## 完全な実行可能サンプル

すべてをまとめると、以下のスクリプトを `adjust_barcode_height.py` という名前のファイルにコピーして実行できます。

```python
# adjust_barcode_height.py
# Demonstrates how to adjust barcode bar height for a DataBar Omni‑Directional barcode

from groupdocs.barcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat
import os

# Ensure the output directory exists
output_dir = "output"
os.makedirs(output_dir, exist_ok=True)

# 1️⃣ Create the generator with GTIN data
gen = BarcodeGenerator(EncodeTypes.DatabarOmniDirectional, "(01)12345678901231")

# 2️⃣ Set module size (X‑dimension) to 2 px
gen.parameters.barcode.x_dimension.pixels = 2

# 3️⃣ First bar height: 30 px
gen.parameters.barcode.bar_height.pixels = 30
gen.save(os.path.join(output_dir, "DatabarBarHeight30Pixels.png"), BarCodeImageFormat.Png)

# 4️⃣ Second bar height: 60 px
gen.parameters.barcode.bar_height.pixels = 60
gen.save(os.path.join(output_dir, "DatabarBarHeight60Pixels.png"), BarCodeImageFormat.Png)

print(f"Barcodes saved to '{output_dir}'")
```

スクリプトを実行：

```bash
python adjust_barcode_height.py
```

`output` フォルダーに 2 つの PNG ファイルが生成され、それぞれ設定したバー高さが反映されています。

## よくある質問とエッジケース

| 質問 | 回答 |
|----------|--------|
| **JPEG を PNG の代わりに使用できますか？** | はい。`BarCodeImageFormat.Png` を `BarCodeImageFormat.Jpeg` に置き換えてください。JPEG はロスがあるため、正確なスキャンが必要な場合は PNG を推奨します。 |
| **10 の倍数でないバー高さが必要な場合は？** | `BarHeight.Pixels` プロパティは任意の整数を受け付けます。希望のピクセル数（例: `45`）を割り当てれば OK です。 |
| **バー高さを変更するとエンコードされたデータに影響しますか？** | 影響しません。視覚的表現だけが変わり、基になるデータ文字列は同一です。 |
| **最初の画像を保存した後で X‑ディメンションを変更するには？** | `gen.parameters.barcode.x_dimension.pixels` を `save()` を呼び出す前にいつでも変更できます。変更は以降の画像に適用されます。 |
| **ジェネレータはスレッドセーフですか？** | `BarcodeGenerator` インスタンスはスレッドセーフとは保証されていません。並列でバーコードを生成する場合は、スレッドごとに別インスタンスを作成してください。 |

## 結論

Python を使って DataBar Omni‑Directional ジェネレータの **バーコードバー高さ** を調整する方法が分かりました。このチュートリアルでは、ジェネレータの作成、**X‑ディメンション** の設定、**バーコードバー高さ** プロパティの変更、そして希望する **バーコード画像形式** での保存手順を解説しました。

ここからは、他の高さや異なるモジュールサイズを試したり、JPEG や BMP など別の画像形式に切り替えたりできます。また、**barcode generator python** の追加機能として、人間が読めるテキストの追加やカラースキームの変更にも挑戦してみてください。

コーディングを楽しみながら、バーコードを鮮明で最適なサイズに保ちましょう！

## 次に学ぶべきこと

以下のチュートリアルは、本ガイドで示したテクニックを基にした関連トピックを扱っています。各リソースには、完全な動作コード例とステップバイステップの解説が含まれており、API の追加機能を習得したり、プロジェクトで代替実装アプローチを探求したりするのに役立ちます。

- [How to set width and adjust height for a GS1 DataBar Omni‑Directional barcode](/barcode/english/python-java/general/how-to-set-width-and-adjust-height-for-a-gs1-databar-omni-di/)
- [Create omni directional databar and barcode image in Python](/barcode/english/python-java/general/create-omni-directional-databar-and-barcode-image-in-python/)
- [.net barcode generator – change barcode height](/barcode/english/python-java/general/net-barcode-generator-change-barcode-height/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}