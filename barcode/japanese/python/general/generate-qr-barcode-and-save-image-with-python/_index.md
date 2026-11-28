---
category: general
date: 2026-11-27
description: Aspose.Barcode を使用して Python で QR バーコードを生成し、バーコード画像をすばやくディスクに保存する方法を学びましょう。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate QR barcode
- save barcode image
- Aspose.Barcode Python
- extended codetext QR
- barcode version information
language: ja
lastmod: 2026-11-27
og_description: Aspose.Barcode を使用して Python で QR バーコードを生成し、すぐにバーコード画像を保存します。完全なサンプルに従って、QR
  コードの作成、カスタマイズ、保存を行いましょう。
og_image_alt: Screenshot of a generated QR barcode created with Python
og_title: PythonでQRコードを生成し画像を保存する – ステップバイステップガイド
schemas:
- author: Aspose
  dateModified: '2026-11-27'
  description: Generate QR barcode in Python using Aspose.Barcode and learn how to
    save barcode image to disk quickly.
  headline: Generate QR barcode and save image with Python
  type: TechArticle
tags:
- QR code
- Python
- Aspose
- Barcode generation
title: PythonでQRコードを生成し、画像として保存する
url: /ja/python/general/generate-qr-barcode-and-save-image-with-python/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# PythonでQRバーコードを生成し、画像として保存する

Python アプリケーションで **QR バーコードを生成** したい場合は、このガイドで Aspose.Barcode ライブラリを使用した方法をご紹介します。また、**バーコード画像をローカルフォルダーに保存** する正しい手順や、ライブラリのバージョン情報取得、拡張コーデテキスト セグメントの扱い方も学べます。

QR コードの作成は、チケットシステム、モバイル決済、製品トラッキングなどで一般的な要件です。このチュートリアルの最後までに、QR バーコード画像ファイルを生成し、デバッグやコンプライアンス目的でバージョン情報を出力する、すぐに実行できるスクリプトが手に入ります。

## 前提条件

開始する前に、以下が揃っていることを確認してください。

* Python 3.8 以上がインストールされていること。
* `aspose-barcode` パッケージ。`pip install aspose-barcode` でインストールできます。
* バーコード画像を保存するディレクトリへの書き込み権限。

追加の外部サービスは不要です。すべてローカルで完結します。

## 手順 1: `ExtCodetextBuilder` で拡張コーデテキストを構築する

拡張コーデテキストを使用すると、プレーンテキストと ECI（Extended Channel Interpretation）セグメントを同一 QR コードに混在させられます。たとえばユーロ記号など、異なる文字セットの文字を埋め込む必要がある場合に便利です。

```python
import aspose.barcode as bc
from aspose.barcode.generation import ExtCodetextBuilder, BuildVersionInfo

# Create the builder instance
ext_builder = ExtCodetextBuilder()

# Add a plain text segment
ext_builder.add_plain_codetext("ABC123")

# Add an ECI segment that uses ISO‑IEC 8859‑1 (code page 3)
ext_builder.add_eci_codetext(3, "€123")
```

**この手順が重要な理由:**  
`ExtCodetextBuilder` は QR エンコーダが処理する最終文字列を組み立てます。拡張コーデテキストを構築しないと、バーコードはプレーン ASCII 文字だけになり、ロケール固有の記号を表現できません。

## 手順 2: 結合された拡張コーデテキスト文字列を取得する

```python
# Get the final extended codetext that will be encoded
extended_codetext = ext_builder.get_extended_codetext()
print("Extended codetext:", extended_codetext)
```

出力例は次のとおりです。

```
Extended codetext: ABC123[ECI3]€123
```

角括弧で囲まれた `[ECI3]` マーカーは、QR エンコーダに対して以降の文字を指定された文字セットに切り替えるよう指示します。

## 手順 3: 拡張コーデテキストを使用して QR バーコードを生成する

```python
# Create a QR barcode generator with the extended codetext
barcode = bc.BarcodeGenerator(bc.EncodeTypes.QR, extended_codetext)
```

**解説:**  
`BarcodeGenerator` は 2 つの引数を受け取ります。バーコードの種類（`QR`）とエンコードするデータ（`extended_codetext`）です。ジェネレータは描画に必要な内部構造をすべて準備します。

## 手順 4: 生成したバーコード画像を保存する

```python
# Define the output path – adjust the folder as needed
output_path = "output/qr_extended.png"

# Save the image in PNG format
barcode.save(output_path)
print(f"Barcode image saved to {output_path}")
```

**このアプローチを推奨する理由:**  
`save` を直接呼び出すと、ファイル拡張子から推測された形式で画像がディスクに書き込まれます。PNG、JPEG、BMP、TIFF がサポートされており、下流の利用者に合わせた柔軟な出力が可能です。

### 保存された画像の確認

任意の画像ビューアで `output/qr_extended.png` を開いてください。QR コードが表示され、スキャンすると文字列 `ABC123€123` が返ります。ほとんどの最新モバイル QR スキャナは ECI セグメントを自動的に処理します。

## 手順 5: Aspose.BarCode のバージョン情報を取得する（任意だが便利）

Aspose.BarCode ライブラリの正確なバージョンを把握しておくと、バグ報告や互換性確認がスムーズになります。

```python
# Retrieve version details
version_info = BuildVersionInfo()
print("Aspose.BarCode version:")
print(f"  Assembly version : {version_info.ASSEMBLY_VERSION}")
print(f"  File version     : {version_info.FILE_VERSION}")
print(f"  Product          : {version_info.PRODUCT}")
print(f"  Release date     : {version_info.RELEASE_DATE}")
```

典型的な出力例:

```
Aspose.BarCode version:
  Assembly version : 23.9.0.0
  File version     : 23.9.0
  Product          : Aspose.BarCode for Python via .NET
  Release date     : 2023-09-15
```

## 完全なスクリプト – コピーして貼り付け、実行するだけ

```python
import aspose.barcode as bc
from aspose.barcode.generation import ExtCodetextBuilder, BuildVersionInfo

# 1️⃣ Build extended codetext
ext_builder = ExtCodetextBuilder()
ext_builder.add_plain_codetext("ABC123")
ext_builder.add_eci_codetext(3, "€123")
extended_codetext = ext_builder.get_extended_codetext()
print("Extended codetext:", extended_codetext)

# 2️⃣ Generate QR barcode
barcode = bc.BarcodeGenerator(bc.EncodeTypes.QR, extended_codetext)

# 3️⃣ Save barcode image
output_path = "output/qr_extended.png"
barcode.save(output_path)
print(f"Barcode image saved to {output_path}")

# 4️⃣ Display version information
version_info = BuildVersionInfo()
print("Aspose.BarCode version:")
print(f"  Assembly version : {version_info.ASSEMBLY_VERSION}")
print(f"  File version     : {version_info.FILE_VERSION}")
print(f"  Product          : {version_info.PRODUCT}")
print(f"  Release date     : {version_info.RELEASE_DATE}")
```

スクリプトを実行すると QR コード画像が生成され、拡張コーデテキストとバージョン情報がコンソールに出力されます。

## よくあるバリエーションとエッジケース

| 状況 | 推奨される調整 |
|-----------|------------------------|
| **異なる文字セット** | `add_eci_codetext` に渡す ECI 識別子を変更します。UTF‑8 の場合は `5` を使用します。 |
| **エラー訂正レベルを上げる** | `barcode.parameters.barcode.qr_error_level = bc.QRErrorLevel.H` を `save` 呼び出し前に設定します。 |
| **カスタム画像サイズ** | `barcode.parameters.image_width` と `barcode.parameters.image_height` でピクセル寸法を制御します。 |
| **PNG 以外の出力** | `output_path` の拡張子を `.jpg` や `.bmp` に変更します。ライブラリが自動で適切なエンコーダを選択します。 |

## プロのコツ

* **出力フォルダーをプログラムで作成**（存在しない場合）:

  ```python
  import os
  os.makedirs(os.path.dirname(output_path), exist_ok=True)
  ```

* **生成後に QR コードを検証** するには `aspose.barcode.BarcodeReader` で再読取します。これにより、特に ECI セグメントを使用した場合にエンコードデータが期待通りか確認できます。

  ```python
  reader = bc.BarcodeReader(output_path, bc.DecodeType.QR)
  for result in reader.read():
      print("Decoded text:", result.code_text)
  ```

* **パフォーマンスのヒント** – ループで多数の QR コードを生成する場合は、`BarcodeGenerator` インスタンスを再利用してください。各イテレーションで新規オブジェクトを作成する代わりに `code_text` プロパティをリセットします。

## 結論

これで Python と Aspose.Barcode を使って **QR バーコードを生成**し、プレーンテキストと ECI セグメントを混在させた拡張コーデテキストを構築し、**バーコード画像をディスクに正しく保存**する方法が分かりました。また、トラブルシューティングに役立つライブラリのバージョン情報取得方法も示しました。

次に試すべきステップ:

* ロゴのオーバーレイやカスタムカラーを QR コードに追加する。
* Aspose.PDF を使って QR バーコードを PDF に直接埋め込む。
* 大規模データセット向けにバッチ生成を自動化する。

さまざまなデータペイロード、エラー訂正レベル、画像フォーマットで実験してみてください。コーディングを楽しんでください！

## 次に学ぶべきこと

以下のチュートリアルは、本ガイドで示したテクニックを基にした関連トピックを扱っています。各リソースには、完全な動作コード例とステップバイステップの解説が含まれており、追加の API 機能を習得したり、独自プロジェクトで代替実装アプローチを探求したりするのに役立ちます。

- [How to Generate QR Code Image in Python with Aspose.Barcode – Full Guide](/barcode/english/python/general/how-to-generate-qr-code-image-in-python-with-aspose-barcode/)
- [How to generate Code 128 barcode and save barcode image with Aspose.BarCode](/barcode/english/python/general/how-to-generate-code-128-barcode-and-save-barcode-image-with/)
- [How to generate DataMatrix barcode in Python with Aspose.BarCode](/barcode/english/python/general/how-to-generate-datamatrix-barcode-in-python-with-aspose-bar/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}