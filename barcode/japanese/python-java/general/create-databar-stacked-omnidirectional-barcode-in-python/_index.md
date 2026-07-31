---
category: general
date: 2026-07-30
description: PythonでDatabar Stacked Omnidirectionalバーコードを作成します。このステップバイステップガイドに従って、アスペクト比とXDimensionを設定し、Pythonのバーコードジェネレーターを使用してPNGをエクスポートしてください。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create databar stacked omnidirectional
- python barcode generator
- databar aspect ratio
- xdimension pixel size
- barcodeimageformat png
language: ja
lastmod: 2026-07-30
og_description: PythonでDatabar Stacked Omnidirectionalバーコードを作成します。このチュートリアルでは、XDimensionの設定方法、DataBarのアスペクト比の調整方法、そしてBarCodeImageFormatを使用してPNGとして保存する方法を示します。
og_image_alt: Screenshot of a Databar Stacked Omnidirectional barcode saved as a PNG
  file
og_title: Databar Stacked Omnidirectional バーコードの作成 – Pythonチュートリアル
schemas:
- author: Aspose
  dateModified: '2026-07-30'
  description: Create Databar Stacked Omnidirectional barcode in Python. Follow this
    step‑by‑step guide to configure aspect ratio, XDimension, and export PNG using
    a python barcode generator.
  headline: Create Databar Stacked Omnidirectional Barcode in Python
  type: TechArticle
tags:
- barcode
- python
- databar
title: Pythonでデータバー・スタックド・オムニディレクショナルバーコードを作成する
url: /ja/python-java/general/create-databar-stacked-omnidirectional-barcode-in-python/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# PythonでDatabar Stacked Omnidirectionalバーコードを作成する

Pythonで **databar stacked omnidirectional** バーコードを **作成したい** が、どこから始めればよいか分からないことはありませんか？ あなたは一人ではありません。多くの開発者が `BarcodeGenerator` クラスに初めて触れるときに同じ壁にぶつかります。 キーとなるプロパティを理解すれば、全体の流れはとてもシンプルです。

このガイドでは、 **python barcode generator** を使って XDimension を設定し、DataBar のアスペクト比を調整し、最終的に PNG ファイルを 2 つエクスポートする、 完全に実行可能なサンプルを順を追って解説します。 終了時には、在庫管理や物流プロジェクト向けに高品質な stacked omnidirectional シンボルを生成する方法をしっかりと身につけられます。

## 学べること

- GTIN‑14 ペイロードで **databar stacked omnidirectional** ジェネレータをインスタンス化する方法  
- **XDimension pixel size** がスキャンの信頼性に与える影響  
- **DataBar aspect ratio** が行の幅と高さに与える効果  
- 結果を **BarCodeImageFormat PNG** ファイルとして保存する方法  
- 同じジェネレータオブジェクトを再利用し、余分なメモリ消費なしで複数バリエーションを生成するコツ  

### 前提条件

- Python 3.8+（使用するライブラリは純粋な Python 実装で、コンパイル済みホイールは不要）  
- `barcode-generator` パッケージ（`pip install barcode-generator` でインストール）  
- 書き込み可能なフォルダー – スクリプトはそこに PNG 画像を 2 枚出力します  

基本的な Python のインポートやオブジェクト指向コードに慣れていれば、すぐに取り掛かれます。

## Create Databar Stacked Omnidirectional Barcode – Step Overview

以下ではワークフローを 6 つの小さなステップに分解します。各ステップは REPL やスクリプトファイルにコピペできる独立したコード片です。 アスペクト比や XDimension を変更すれば、すぐに別のビジュアルスタイルが得られます。

---

## Step 1: Create Databar Stacked Omnidirectional Generator

最初に **databar stacked omnidirectional** ジェネレータインスタンスを作成し、適切な `EncodeTypes` 列挙体とデータ文字列を渡します。

```python
from barcode_generator import BarcodeGenerator, EncodeTypes, BarCodeImageFormat

# Step 1 – initialize the generator with a GTIN‑14 payload
barcode_generator = BarcodeGenerator(
    EncodeTypes.DatabarStackedOmniDirectional,
    "(01)12345678901231"
)
```

> **Why this matters:** `EncodeTypes.DatabarStackedOmniDirectional` フラグは、ライブラリに stacked omnidirectional シンボルを生成させます。これは、最大 14 桁までエンコードでき、どの角度からでも読み取れる唯一の DataBar バリアントです。

---

## Configure XDimension Pixel Size

**XDimension pixel size** は最小モジュール（最も細い黒バー）のサイズを制御します。`2` ピクセルの値は、ほとんどの画面表示シナリオでうまく機能します。

```python
# Step 2 – set the smallest module to 2 pixels
barcode_generator.Parameters.Barcode.XDimension.Pixels = 2
```

> **Pro tip:** 高 DPI で印刷する場合は、エッジがぼやけないようにこの値を 3 または 4 に上げてください。

---

## Adjust DataBar Aspect Ratio (15)

**DataBar aspect ratio** は各行の幅と高さの比率を決定します。アスペクト比 `15` は幅の広い行を生成し、多くのスキャナが高速撮影時に好む設定です。

```python
# Step 3 – make rows wider (aspect ratio = 15)
barcode_generator.Parameters.Barcode.DataBar.AspectRatio = 15
```

> **Why 15?** 公式 GS1 仕様では stacked omnidirectional シンボルの比率を 10〜20 の間と推奨しています。バランスの取れたデフォルトとして `15` を選びました。

---

## Export Barcode as PNG Using BarCodeImageFormat

ジェネレータの設定が完了したら、画像を永続化します。`BarCodeImageFormat.Png` 列挙体はロスレス出力を保証し、下流処理に最適です。

```python
# Step 4 – save the first PNG with the 15 aspect ratio
barcode_generator.Save(
    "YOUR_DIRECTORY/DatabarStackedAR15.png",
    BarCodeImageFormat.Png
)
```

> **What you’ll see:** 生成された PNG を開くと、比較的幅の広い行を持つ、クリーンで高コントラストなバーコードが確認できます。

---

## Change DataBar Aspect Ratio to 30

場合によっては、幅よりも高さが必要になることがあります（狭いラベルに合わせるなど）。**DataBar aspect ratio** を `30` に変更すると、各行がより高くなります。

```python
# Step 5 – increase the aspect ratio to make rows taller
barcode_generator.Parameters.Barcode.DataBar.AspectRatio = 30
```

> **Edge case:** 比率が非常に高い（例: >40）と、バーコードが一般的なラベル高さを超えてしまうことがあるため、実際のプリンタでテストしてから本番に使用してください。

---

## Export Barcode Again with New Aspect Ratio

最後に、同じ `barcode_generator` オブジェクトを再利用して 2 枚目の PNG を書き出します。ジェネレータを作り直す必要はなく、プロパティを変更して `Save` を再度呼び出すだけです。

```python
# Step 6 – save the second PNG with the 30 aspect ratio
barcode_generator.Save(
    "YOUR_DIRECTORY/DatabarStackedAR30.png",
    BarCodeImageFormat.Png
)
```

> **Result:** これで 2 つの PNG ファイルが手に入ります – 幅広い行 (`AR15`) と高さのある行 (`AR30`) のそれぞれです。スキャナ設定に最適な方を横並びで比較してください。

---

## Full Working Example

すべてをまとめた完全なスクリプトを以下に示します。`YOUR_DIRECTORY` を実際の絶対パスに置き換えて実行してください。

```python
from barcode_generator import BarcodeGenerator, EncodeTypes, BarCodeImageFormat

# 1️⃣ Initialize generator
barcode_generator = BarcodeGenerator(
    EncodeTypes.DatabarStackedOmniDirectional,
    "(01)12345678901231"
)

# 2️⃣ Set smallest module (XDimension)
barcode_generator.Parameters.Barcode.XDimension.Pixels = 2

# 3️⃣ First aspect ratio – wider rows
barcode_generator.Parameters.Barcode.DataBar.AspectRatio = 15
barcode_generator.Save("YOUR_DIRECTORY/DatabarStackedAR15.png", BarCodeImageFormat.Png)

# 4️⃣ Second aspect ratio – taller rows
barcode_generator.Parameters.Barcode.DataBar.AspectRatio = 30
barcode_generator.Save("YOUR_DIRECTORY/DatabarStackedAR30.png", BarCodeImageFormat.Png)

print("✅ Two PNG files created – AR15 and AR30")
```

**Expected output** (in your console):

```
✅ Two PNG files created – AR15 and AR30
```

ターゲットフォルダーに 2 つの画像ファイルが生成され、スキャンテストの準備が整います。

---

## Conclusion

私たちは Python で **databar stacked omnidirectional** バーコードを **作成し**、**XDimension pixel size** を調整し、2 つの異なる **DataBar aspect ratio** 設定を試して、結果を **BarCodeImageFormat PNG** ファイルとしてエクスポートしました。全工程は数行のコードに収まりますが、スキャナにとって最も重要な視覚特性をフルコントロールできます。

次は何をしますか？ ペイロードを別の GTIN に差し替えたり、PNG をパレットベースの画像に変換して色を操作したり、2 枚の PNG を横並びで埋め込んだ PDF レポートを生成したりしてみてください。`BarcodeGenerator` クラスはこれらすべてのシナリオに柔軟に対応できるので、自由に実験してみましょう。

特定のユースケースで質問がある、またはエラーが出た場合は下のコメント欄に書き込んでください。喜んでサポートします。Happy coding!

## What Should You Learn Next?

以下のチュートリアルは、本ガイドで示したテクニックを基にした、密接に関連するトピックを扱っています。各リソースには、完全な動作コード例とステップバイステップの解説が含まれており、追加の API 機能を習得したり、独自プロジェクトで代替実装アプローチを探求したりするのに役立ちます。

- [Generate barcode image – GS1 Coupon UPC-A Databar](/barcode/english/net/gs1-barcode-encoding/gs1-coupon-upc-a-databar-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}