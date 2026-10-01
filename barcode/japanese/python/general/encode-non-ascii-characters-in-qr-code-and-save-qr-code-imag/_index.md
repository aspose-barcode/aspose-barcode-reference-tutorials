---
category: general
date: 2026-09-10
description: 非ASCII文字をQRコードにエンコードし、シンプルなPythonビルダーでQRコード画像を保存します。ExtCodetextBuilder
  と BarcodeGenerator を使用したステップバイステップのガイドに従ってください。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- encode non ascii characters
- save qr code image
- extended codetext builder
- eci encoding python
- barcode generation python
language: ja
lastmod: 2026-09-10
og_description: 非ASCII文字をQRコードにエンコードし、PythonでQRコード画像を保存する。このチュートリアルでは、拡張コードテキストの作成、QRコードの生成、画像の保存方法を示します。
og_image_alt: Diagram showing encode non ASCII characters in QR code and save QR code
  image workflow
og_title: 非ASCII文字をQRコードにエンコードしてQRコード画像を保存する – ステップバイステップ Python ガイド
schemas:
- author: Aspose
  dateModified: '2026-09-10'
  description: Encode non ASCII characters in a QR code and save QR code image with
    a simple Python builder. Follow a step‑by‑step guide using ExtCodetextBuilder
    and BarcodeGenerator.
  headline: Encode non ASCII characters in QR code and save QR code image
  type: TechArticle
tags:
- barcode
- QR code
- Python
title: QRコードに非ASCII文字をエンコードし、QRコード画像を保存する
url: /ja/python/general/encode-non-ascii-characters-in-qr-code-and-save-qr-code-imag/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# QRコードで非ASCII文字をエンコードし、QRコード画像を保存する

QRコードで **非ASCII文字をエンコード** する必要がある場合、このガイドではその手順と **QRコード画像をディスクに保存** する方法を正確に示します。ロシア語、中文、絵文字データを扱う場合でも、ExtCodetextBuilder を使用すれば、プレーンテキストと ECI エンコードされたセグメントを手動でバイト操作することなく混在させることができます。

このチュートリアルでは、拡張コードテキスト文字列の作成方法、その文字列を理解できる QR コードの生成方法、そして最終的にバーコード画像をファイルに書き出す方法を学びます。前提として、基本的な Python の知識と `barcode` SDK がインストールされていることが必要です。

## 前提条件

* Python 3.8+ がインストールされていること。
* `ExtCodetextBuilder`、`CodetextEncodingType`、`BarcodeGenerator` を提供する `barcode` Python パッケージ（または該当する SDK）。
* **QRコード画像を保存** したいディレクトリへの書き込み権限。

SDK は pip でインストールできます（`barcode-sdk` を実際のパッケージ名に置き換えてください）：

```bash
pip install barcode-sdk
```

## ステップ 1: 拡張コードテキストビルダーを作成する

最初のステップは `ExtCodetextBuilder` のインスタンスを作成することです。このオブジェクトは�数のテキストセグメントを収集し、QR コードのシンボロジーが解釈できる単一の文字列を生成します。

```python
from barcode import ExtCodetextBuilder, CodetextEncodingType, BarcodeGenerator, Symbology

# Initialize the builder that will hold all text parts
ext_builder = ExtCodetextBuilder()
```

*Why this matters*: QR コードは **拡張コードテキスト** をサポートしており、1 つのバーコードに複数のエンコーディングモード（プレーン、ECI など）を埋め込むことができます。ビルダーは QR 仕様で必要とされる低レベルのフォーマット処理を抽象化します。

## ステップ 2: プレーンテキストセグメントを追加する

プレーンテキストはデフォルトモードで、ASCII 文字に対応します。最初に追加することで、ECI を無視するスキャナーに対して可読なフォールバックを提供します。

```python
# Add simple ASCII text
ext_builder.add_plain_codetext("HelloWorld")
```

このステップを省略すると、QR コードは ECI セグメントのみを含むことになり、古いリーダーの中には正しくデコードできないものがあります。

## ステップ 3: 非ASCII文字用の ECI エンコードセグメントを追加する

ASCII 範囲外の文字（キリル文字、中文、絵文字など）を含めるには、ECI（Extended Channel Interpretation）エンコーディングを指定する必要があります。ここではロシア語の単語 “Привет” に UTF‑8 を使用しています。

```python
# Add a UTF‑8 encoded segment containing non‑ASCII characters
ext_builder.add_eci_codetext(CodetextEncodingType.UTF_8, "Привет")  # Russian “Hi”
```

*Why this works*: QR 仕様では、スキャナーに適用すべき文字セットを指示する ECI 値が定義されています。ECI マーカーがなければ、生のバイトは ISO‑8859‑1 として解釈され、文字化けした出力になります。

## ステップ 4: 結合された拡張コードテキスト文字列を取得する

すべての必要なセグメントを追加したら、`get_extended_codetext()` を呼び出して、バーコードジェネレータが期待する最終文字列を取得します。

```python
# Combine all parts into one extended codetext string
extended_codetext = ext_builder.get_extended_codetext()
print("Extended codetext:", extended_codetext)
```

出力される値は制御文字の連続に続いて実際のテキストが続くように見えますが、手動で解析する必要はありません。

## ステップ 5: 拡張コードテキストを使用して QR コードを生成する

次に `BarcodeGenerator` を作成し、シンボロジーを QR に設定（拡張コードテキストをサポートする唯一の一般的な 2‑D シンボロジー）し、結合した文字列を渡します。

```python
# Initialize the QR generator
qr_generator = BarcodeGenerator()
qr_generator.set_symbology(Symbology.QR)          # QR supports extended codetext
qr_generator.set_code_text(extended_codetext)
```

*Tip*: 同じ手順を Code‑128 や DataMatrix で試すと、これらのフォーマットは ECI マーカーを解釈できないため、SDK が例外をスローします。

## ステップ 6: QR コード画像を保存する

最後に、バーコードを PNG ファイルに書き出します。ここで **QRコード画像を保存** して後で使用できるようにします。

```python
output_path = "output/qr_extended.png"
qr_generator.save(output_path)

print(f"QR code saved to {output_path}")
```

`save` を呼び出す前に、`output` フォルダーが存在することを確認するか、`os.makedirs('output', exist_ok=True)` で作成してください。

### 完全に実行可能な例

すべてのステップを組み合わせると、すぐに実行できる自己完結型スクリプトが得られます：

```python
import os
from barcode import ExtCodetextBuilder, CodetextEncodingType, BarcodeGenerator, Symbology

# Ensure the output directory exists
os.makedirs("output", exist_ok=True)

# 1️⃣ Create the builder
ext_builder = ExtCodetextBuilder()

# 2️⃣ Add plain ASCII text
ext_builder.add_plain_codetext("HelloWorld")

# 3️⃣ Add UTF‑8 encoded non‑ASCII text (Russian)
ext_builder.add_eci_codetext(CodetextEncodingType.UTF_8, "Привет")

# 4️⃣ Retrieve the combined string
extended_codetext = ext_builder.get_extended_codetext()
print("Extended codetext:", extended_codetext)

# 5️⃣ Generate QR code
qr_generator = BarcodeGenerator()
qr_generator.set_symbology(Symbology.QR)
qr_generator.set_code_text(extended_codetext)

# 6️⃣ Save the image
output_file = "output/qr_extended.png"
qr_generator.save(output_file)
print(f"QR code saved to {output_file}")
```

**期待される出力**（コンソール）:

```
Extended codetext: <binary representation showing ECI markers>
QR code saved to output/qr_extended.png
```

`qr_extended.png` を任意の QR スキャナーで開くと `HelloWorldПривет` が表示されます。ECI を理解するスキャナーはキリル文字を正しく表示し、そうでないものは ASCII 部分のみを表示します。

## よくある質問とエッジケース

| 質問 | 回答 |
|----------|--------|
| *Shift‑JIS のような他のエンコーディングは使用できますか？* | はい。`CodetextEncodingType.UTF_8` を `CodetextEncodingType.SHIFT_JIS` に置き換え、適切なテキストを提供してください。 |
| *結合したデータが QR の容量を超えた場合はどうなりますか？* | QR コードにはバージョン制限があり（最大 177 × 177 モジュール）、ビルダーがサイズ例外をスローした場合は、エラー訂正レベルを上げるか、データを複数の QR コードに分割してください。 |
| *特定の QR バージョンを設定する必要がありますか？* | SDK はデータに最適な最小バージョンを自動的に選択します。必要に応じて `qr_generator.set_qr_version(10)` でバージョンを強制指定できます。 |
| *画像は透明になりますか？* | デフォルトでは SDK は白背景の PNG を出力します。透明が必要な場合は `save` の前に `qr_generator.set_background_color(Color.Transparent)` を使用してください。 |

## 結論

このチュートリアルでは、`ExtCodetextBuilder` を使用して QR コードに **非ASCII文字をエンコード** し、`BarcodeGenerator` で **QRコード画像を保存** する方法を学びました。プロセスは、拡張コードテキスト文字列の構築、プレーンと ECI エンコードセグメントの両方の追加、QR シンボロジーの生成、そして最終的に画像ファイルを書き出すことです。

ここからは以下を検討できます：

* さらに ECI セグメントを追加する（異なる言語や絵文字）。
* 信頼性向上のために QR のエラー訂正レベルを調整する。
* 生成した PNG を PDF やウェブページに埋め込む。

コーディングを楽しんで、多言語 QR コードの作成をお楽しみください！

## 次に学ぶべきことは？

以下のチュートリアルは、本ガイドで示した手法を基にした密接に関連するトピックを取り上げています。各リソースには、ステップバイステップの解説と完全な動作コード例が含まれており、追加の API 機能を習得し、プロジェクトで代替実装アプローチを探求するのに役立ちます。

- [Python で Aspose.Barcode を使用して QR コード画像を生成する方法 – 完全ガイド](/barcode/english/python/general/how-to-generate-qr-code-image-in-python-with-aspose-barcode/)
- [Aspose.Barcode Python で Code128 バーコードを生成する – 完全ガイド](/barcode/english/python/general/generate-code128-barcode-with-aspose-barcode-python-full-gui/)
- [Python バーコードライブラリで製品名を表示する – ステップバイステップガイド](/barcode/english/python/general/display-product-name-using-python-barcode-library-step-by-st/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}