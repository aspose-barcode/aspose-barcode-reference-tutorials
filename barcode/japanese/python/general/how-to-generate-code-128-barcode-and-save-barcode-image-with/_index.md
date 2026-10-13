---
category: general
date: 2026-09-23
description: PythonでAspose.BarCodeを使用してCode 128バーコードを生成し、バーコード画像を保存する方法を学ぶ – ステップバイステップガイド
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate code 128 barcode
- save barcode image
- Aspose.BarCode Python
- extended codetext builder
- barcode PNG export
language: ja
lastmod: 2026-09-23
og_description: PythonでAspose.BarCodeを使用してCode 128バーコードを生成し、バーコード画像を保存します。この完全な例に従って、バーコードを作成・カスタマイズし、PNGファイルとしてエクスポートしてください。
og_image_alt: Python-generated Code 128 barcode saved as PNG image
og_title: Code 128バーコードを生成して画像として保存 – Pythonガイド
schemas:
- author: Aspose
  dateModified: '2026-09-23'
  description: Learn how to generate Code 128 barcode and save barcode image using
    Aspose.BarCode in Python – step‑by‑step guide.
  headline: How to generate Code 128 barcode and save barcode image with Aspose.BarCode
  type: TechArticle
tags:
- barcode
- Code 128
- Python
- Aspose
title: Aspose.BarCode を使用して Code 128 バーコードを生成し、バーコード画像を保存する方法
url: /ja/python/general/how-to-generate-code-128-barcode-and-save-barcode-image-with/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Code 128 バーコードを生成し、Aspose.BarCodeでバーコード画像を保存する方法

Python プロジェクトで **Code 128 バーコードを生成** し **バーコード画像を保存** する必要がある場合、このチュートリアルでは正確な手順を示します。Aspose.BarCode の `ExtCodetextBuilder` を使用すると、プレーンテキストと Unicode セグメントを単一のペイロードに埋め込み、結果を PNG ファイルとしてレンダリングできます。

完全な実行可能スクリプト、各行の説明、ECI エンコーディングの処理や適切な出力フォルダーの選択など、一般的な落とし穴に関するヒントが確認できます。外部ドキュメントは不要です—コピーして貼り付け、実行するだけです。

## 前提条件

* Python 3.8+ がインストールされていること。
* `aspose.barcode` パッケージ（`pip install aspose-barcode` でインストール）。
* PNG を保存するディレクトリへの書き込み権限。

このコードは Aspose.BarCode がサポートするすべてのシンボロジーで動作しますが、例では **Code 128** に焦点を当てています。これは英数字データを効率的にエンコードし、拡張文字セットをサポートするためです。

## 手順 1: 必要なクラスをインポートする

```python
import barcode                     # Core Aspose.BarCode namespace
from barcode import BarCodeWriter, BarCodeEncodeMode, BarCodeImageFormat
from barcode import ExtCodetextBuilder, BuildVersionInfo
```

*この手順の目的は？* クラスをインポートすることで、拡張コーデテキスト用のビルダー、画像を作成するライター、そしてライブラリの更新時にデバッグに役立つバージョンヘルパーにアクセスできます。

## 手順 2: 拡張コーデテキストを構築する

```python
# Create a builder for extended codetext
builder = ExtCodetextBuilder()

# Add plain text (no ECI) – this part is simple ASCII
builder.add_plain_codetext("ABC123")

# Add a Unicode segment with ECI 0x03 (UTF‑8). The word “Пример” means “Example” in Russian.
builder.add_eci_codetext(0x03, "Пример")

# Retrieve the full extended codetext string
extended_codetext = builder.get_extended_codetext()
print("Extended codetext:", extended_codetext)
```

`ExtCodetextBuilder` を使用すると、単一のバーコードペイロード内でプレーン ASCII と Unicode データを混在させることができます。ECI (Extended Channel Interpretation) バイト `0x03` は、スキャナーに続くバイトが UTF‑8 エンコードであることを示し、ロシア語、中国語、アラビア語などの言語に必須です。

## 手順 3: Code 128 用にバーコードライターを設定する

```python
writer = BarCodeWriter()
writer.encode_type = BarCodeEncodeMode.CODE_128   # Choose Code 128 symbology
writer.code_text = extended_codetext
```

`encode_type` を `CODE_128` に設定することで、ライターは **Code 128 バーコード** を描画します。`code_text` プロパティは前の手順で構築した拡張文字列を受け取ります。

## 手順 4: バーコード画像を PNG として保存する

```python
output_path = "YOUR_DIRECTORY/extended_codetext.png"
writer.save(output_path, BarCodeImageFormat.PNG)
print(f"Barcode image saved to {output_path}")
```

`save` メソッドはバーコードをファイルに書き込みます。`BarCodeImageFormat.PNG` を使用することで、ロスレス圧縮とウェブやモバイルアプリケーションでの広範な互換性が確保されます。

## 手順 5（オプション）: Aspose.BarCode ライブラリのバージョンを確認する

```python
version_info = BuildVersionInfo()
print("Assembly version :", version_info.ASSEMBLY_VERSION)
print("Product version   :", f"{version_info.PRODUCT_MAJOR}.{version_info.PRODUCT_MINOR}")
print("Release date      :", version_info.RELEASE_DATE)
```

正確なライブラリバージョンを把握しておくと、バグを報告したり、リリース間の動作を比較したりする際に役立ちます。

## 期待される出力

スクリプトを実行すると、以下のようなコンソール出力が得られます。

```
Extended codetext: ABC123[ECI=03]Пример
Assembly version : 23.12.0.0
Product version   : 23.12
Release date      : 2023-12-01
Barcode image saved to YOUR_DIRECTORY/extended_codetext.png
```

生成された PNG（`extended_codetext.png`）は次のようになります。

![Pythonで生成された Code 128 バーコード（PNG画像として保存）](images/code128_extended.png)

*この画像は、ASCII 文字列 `ABC123` とロシア語の単語 “Пример” の両方をエンコードした Code 128 バーコードを示しています。*

## よくある質問とエッジケースの対処法

| Question | Answer |
|----------|--------|
| **別のシンボロジーを使用できますか？** | はい。`BarCodeEncodeMode.CODE_128` を `QR`、`EAN_13`、`PDF_417` など、サポートされている他のモードに置き換えてください。 |
| **Unicode テキストに絵文字が含まれている場合はどうなりますか？** | 絵文字も UTF‑8 文字の一種なので、同じ `add_eci_codetext` 呼び出しで機能します。使用する ECI が対象のスキャナーでサポートされていることを確認してください。 |
| **画像サイズを変更するには？** | `save` を呼び出す前に `writer.x_dimension` と `writer.bar_height` を設定します。 |
| **`output_path` にはどのフォルダーを使用すべきですか？** | Python プロセスが書き込み可能な任意のフォルダーです。`os.makedirs` を `exist_ok=True` とともに使用すれば自動的に作成できます。 |

## プロのコツ

* **パスをハードコーディングしないでください。** `os.path.join` と `pathlib` モジュールの `Path` を使用して、クロスプラットフォーム互換性を確保します。
* **バーコードを検証する。** 保存後、`barcode.BarCodeReader` で画像を読み戻し、エンコードされたテキストが `extended_codetext` と一致することを確認できます。
* **パフォーマンスのコツ。** ループで多数のバーコードを生成する場合、単一の `BarCodeWriter` インスタンスを再利用し、各イテレーションで `code_text` のみを更新します。

## 結論

これで、ASCII と Unicode データを混在させた **Code 128 バーコードを生成** し、Aspose.BarCode を使用して PNG として **バーコード画像を保存** する方法が分かりました。完全なスクリプトは、拡張コーデテキストの構築、ライターの設定、画像のエクスポート、ライブラリバージョンの確認を網羅しています。

ここからは以下を検討できます：

* 前景/背景色の追加 (`writer.back_color`、`writer.fore_color`)。
* `Aspose.PDF` を使用してバーコードを PDF に埋め込む。
* `BarCodeReader` クラスを使用して保存した画像をデコードし、内容を自動的に検証する。

コーディングを楽しんで、他のシンボロジーや画像形式でも自由に試してみてください！

## 次に学ぶべきことは？

以下のチュートリアルは、本ガイドで示した手法を基にした密接に関連するトピックを取り上げています。各リソースには、ステップバイステップの解説付きの完全な動作コード例が含まれており、追加の API 機能を習得し、プロジェクトで代替実装アプローチを検討するのに役立ちます。

- [Aspose.Barcode Python で Code128 バーコードを生成 – 完全ガイド](/barcode/english/python/general/generate-code128-barcode-with-aspose-barcode-python-full-gui/)
- [Python でバーコードを生成する方法 – 完全ステップバイステップガイド](/barcode/english/python-java/general/how-to-generate-barcode-in-python-complete-step-by-step-guid/)
- [Aspose.Barcode を使用して Python で QR コード画像を生成する方法 – 完全ガイド](/barcode/english/python/general/how-to-generate-qr-code-image-in-python-with-aspose-barcode/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}