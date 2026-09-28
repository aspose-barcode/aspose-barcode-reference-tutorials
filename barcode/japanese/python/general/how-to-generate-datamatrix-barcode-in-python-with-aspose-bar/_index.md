---
category: general
date: 2026-08-22
description: PythonでDataMatrixバーコードを生成し、Aspose.BarCodeを使用してロシア語テキストをエンコードする方法 – ステップバイステップガイド
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate DataMatrix barcode
- encode Russian text
language: ja
lastmod: 2026-08-22
og_description: PythonでDataMatrixバーコードを生成し、Aspose.BarCodeでロシア語テキストをエンコードします。完全なサンプルに従ってすぐに実行できます。
og_image_alt: Python script that generate DataMatrix barcode with encoded Russian
  text
og_title: PythonでDataMatrixバーコードを生成する – 完全なAspose.BarCodeチュートリアル
schemas:
- author: Aspose
  dateModified: '2026-08-22'
  description: Learn to generate DataMatrix barcode in Python and encode Russian text
    using Aspose.BarCode – step‑by‑step guide.
  headline: How to generate DataMatrix barcode in Python with Aspose.BarCode
  type: TechArticle
- description: Learn to generate DataMatrix barcode in Python and encode Russian text
    using Aspose.BarCode – step‑by‑step guide.
  name: How to generate DataMatrix barcode in Python with Aspose.BarCode
  steps:
  - name: '**ABC123** – the plain identifier.'
    text: '**ABC123** – the plain identifier.'
  - name: '**Привет** – the Russian greeting, correctly decoded as UTF‑8.'
    text: '**Привет** – the Russian greeting, correctly decoded as UTF‑8.'
  - name: Open the PNG file in an image viewer.
    text: Open the PNG file in an image viewer.
  - name: Use any DataMatrix scanning app (many mobile apps support it) or a hardware
      scanner.
    text: Use any DataMatrix scanning app (many mobile apps support it) or a hardware
      scanner.
  - name: The decoded string should display `ABC123Привет` (or the two parts separated
      depending on the scanner UI).
    text: The decoded string should display `ABC123Привет` (or the two parts separated
      depending on the scanner UI).
  type: HowTo
tags:
- Aspose.BarCode
- Python
- barcode generation
title: Aspose.BarCode を使用して Python で DataMatrix バーコードを生成する方法
url: /ja/python/general/how-to-generate-datamatrix-barcode-in-python-with-aspose-bar/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Python と Aspose.BarCode で DataMatrix バーコードを生成する方法

Python で **DataMatrix バーコードを生成** しながら **ロシア語テキストをエンコード** したい場合、このガイドでは正確な手順を示します。拡張コーデテキストを構築し、バーコードを設定し、画像を単一のスクリプトで保存する、完全で実行可能な例をご覧いただけます。

非 ASCII 文字を含むバーコードを作成すると、文字セットやデータエンコーディングに関する疑問が生じがちです。Aspose.BarCode の `ExtCodetextBuilder` を使用すれば、キリル文字などの UTF‑8 テキストを DataMatrix シンボル内に安全に埋め込むことができます。結果は DataMatrix 標準に対応した任意のスキャナーで読み取れます。

このチュートリアルで学べること:

* 必要な Aspose.BarCode パッケージをインストールする。
* プレーンデータとロシア語テキストを混在させた拡張コーデテキストを構築する。
* 拡張文字列で **DataMatrix バーコードを生成** する。
* モジュールサイズなどのバーコードパラメータを調整する。
* バーコードを PNG ファイルとして保存する。

外部サービスは不要です。すべてローカル環境で実行できます。

## 前提条件

開始する前に、以下が揃っていることを確認してください:

* Python 3.8 以上がインストールされていること。
* 有効な Aspose.BarCode for Python ライセンス（開発用の無料トライアルでも可）。
* Python スクリプトの基本的な知識。

Aspose.BarCode ライブラリは pip でインストールできます:

```bash
pip install aspose-barcode
```

## ステップ 1: 拡張コーデテキスト文字列を構築する

最初のタスクは、プレーンな製品識別子とロシア語フレーズの両方を含む単一の文字列を作成することです。`ExtCodetextBuilder` を使うと、エンコーディング情報を保持したまま複数のコーデテキスト部分を連結できます。

```python
# Import required Aspose.BarCode classes
import aspose.barcode as barcode
from aspose.barcode.generation import ExtCodetextBuilder, BarcodeGenerator, EncodeTypes

# Initialize the extended codetext builder
builder = ExtCodetextBuilder()

# Add a plain ASCII identifier – this could be a SKU, part number, etc.
builder.add_plain_codetext("ABC123")

# Add Russian text using ECI (Extended Channel Interpretation) encoding.
# The eci_encoding value 3 corresponds to UTF‑8.
builder.add_eci_codetext(eci_encoding=3, codetext="Привет")

# Retrieve the combined string that Aspose.BarCode will use.
extended_text = builder.get_extended_codetext()
print("Generated extended codetext:", extended_text)
```

**このステップが重要な理由** – DataMatrix シンボルは生バイトを格納します。複数の文字体系を混在させる場合、各セグメントに適用すべき文字セットをエンコーダに指示する必要があります。`add_eci_codetext` メソッドはロシア語テキストの前に ECI インジケータを挿入し、スキャナーがバイト列を UTF‑8 として解釈できるようにします。ECI が無いと、キリル文字は文字化けしてしまいます。

## ステップ 2: DataMatrix バーコードジェネレータを作成する

拡張コーデテキストが準備できたら、`EncodeTypes.DATA_MATRIX` タイプを指定して `BarcodeGenerator` をインスタンス化します。

```python
# Create a DataMatrix barcode generator using the extended codetext
generator = BarcodeGenerator(EncodeTypes.DATA_MATRIX, extended_text)
```

**なぜ DataMatrix か？** – DataMatrix は 2 次元バーコードで、最大 2,335 文字の英数字または 1,556 バイトを格納できます。小型部品や工業部品、マルチリンガルテキストを埋め込む必要があるシーンに最適です。

## ステップ 3: (オプション) バーコードパラメータを設定する

Aspose.BarCode には多数のパラメータが公開されています。ほとんどのユースケースではデフォルト設定で読み取り可能なシンボルが生成されますが、印刷要件に合わせて各モジュール（マトリックス内の最小正方形）のサイズを調整したくなることがあります。

```python
# Set the module (pixel) size to 2.5 points – adjust as needed for your printer DPI
generator.parameters.barcode.x_dimension = 2.5
```

その他の便利なパラメータとして、誤り訂正レベル、余白、背景色などがあります。これらはスキャン環境が特定の許容範囲を要求する場合にのみ調整してください。

## ステップ 4: バーコード画像を保存する

最後に、バーコードをファイルに書き出します。`save` メソッドは PNG、JPEG、BMP、そしていくつかのベクターフォーマットをサポートしています。

```python
# Save the barcode image to the desired folder
output_path = "YOUR_DIRECTORY/extended_codetext.png"
generator.save(output_path)
print(f"Barcode saved as {output_path}")
```

`extended_codetext.png` を開くと、鮮明な DataMatrix シンボルが表示されます。標準的な DataMatrix リーダーでスキャンすると、次の 2 部分が取得できます:

1. **ABC123** – プレーンな識別子。
2. **Привет** – 正しく UTF‑8 としてデコードされたロシア語の挨拶。

## 完全な実行可能サンプル

以下は `generate_datamatrix.py` というファイル名でコピー＆ペーストできる完全なスクリプトです。`YOUR_DIRECTORY` をシステム上の既存フォルダーに置き換えてください。

```python
# generate_datamatrix.py
# -------------------------------------------------
# Complete example: generate DataMatrix barcode and encode Russian text
# -------------------------------------------------

import aspose.barcode as barcode
from aspose.barcode.generation import ExtCodetextBuilder, BarcodeGenerator, EncodeTypes

def main():
    # Step 1: Build extended codetext
    builder = ExtCodetextBuilder()
    builder.add_plain_codetext("ABC123")
    builder.add_eci_codetext(eci_encoding=3, codetext="Привет")
    extended_text = builder.get_extended_codetext()
    print("Generated extended codetext:", extended_text)

    # Step 2: Create DataMatrix generator
    generator = BarcodeGenerator(EncodeTypes.DATA_MATRIX, extended_text)

    # Step 3: Optional parameters (adjust module size if needed)
    generator.parameters.barcode.x_dimension = 2.5

    # Step 4: Save the image
    output_path = "YOUR_DIRECTORY/extended_codetext.png"
    generator.save(output_path)
    print(f"Barcode saved as {output_path}")

if __name__ == "__main__":
    main()
```

コマンドラインからスクリプトを実行します:

```bash
python generate_datamatrix.py
```

コンソールに次のような出力が表示されるはずです:

```
Generated extended codetext: (ECI:3)ПриветABC123
Barcode saved as YOUR_DIRECTORY/extended_codetext.png
```

## 結果の検証

バーコードがロシア語フレーズを正しくエンコードしていることを確認する手順:

1. PNG ファイルを画像ビューアで開く。
2. 任意の DataMatrix スキャンアプリ（多くのモバイルアプリが対応）またはハードウェアスキャナーを使用する。
3. デコードされた文字列が `ABC123Привет`（またはスキャナー UI によっては 2 部分に分かれて）と表示されることを確認する。

ロシア語文字が文字化けしている場合は、スキャナーが ECI UTF‑8 に対応しているか再確認してください。最新のリーダーはほとんど対応していますが、レガシーデバイスは明示的な設定が必要な場合があります。

## よくある落とし穴と回避策

| 問題 | 原因 | 対策 |
|------|------|------|
| キリル文字が文字化けする | ECI インジケータが欠如 | `add_eci_codetext` を `eci_encoding=3` で使用する |
| プリンタでバーコードが小さすぎる | デフォルトのモジュールサイズが低 DPI に対して細かすぎる | `x_dimension` を増やす（例: `3.0` または `4.0`） |
| ファイルが保存されない | ディレクトリパスが無効 | `YOUR_DIRECTORY` が存在し書き込み可能であることを確認 |
| スキャナーが読み取れない | データ密度が高すぎる | エンコードデータ量を減らすか、誤り訂正レベルを上げる（`generator.parameters.barcode.error_correction_level`） |

## サンプルの拡張

このパターンは他の言語やデータタイプにも応用できます:

* **日本語やアラビア語テキストをエンコード** – `eci_encoding` を適切な値に変更（例: ISO‑8859‑5 は 5、ISO‑8859‑7 は 6）  
* **複数の ECI セグメントを追加** – `add_eci_codetext` を複数回呼び出し、各セグメントごとにエンコーディングを指定  
* **QR コードに変更** – `EncodeTypes.DATA_MATRIX` を `EncodeTypes.QR` に置き換える  

`ExtCodetextBuilder` が低レベルのバイト処理を抽象化しているため、他の手順は同じままです。

## 結論

これで Python で **DataMatrix バーコードを生成**し、Aspose.BarCode の拡張コーデテキスト機能を使って **ロシア語テキストをエンコード**する方法が分かりました。短いコード数行で文字セット交渉、バーコード生成、画像出力を実現する完全なスクリプトが完成しました。

次は他のバーコードシンボル（PDF417、Aztec）を試すか、PNG 画像をオンデマンドで返す Web サービスにジェネレータを組み込んでみてください。拡張コーデテキストの構築と適切な `EncodeTypes` の選択という原則は、Aspose.BarCode スイート全体に共通です。

コーディングを楽しみながら、多言語バーコード生成の力を活用してください！

## 次に学ぶべきことは？

以下のチュートリアルは、本ガイドで示した手法を基にした、密接に関連するトピックを扱っています。各リソースには、完全な動作コード例とステップバイステップの解説が含まれており、API の追加機能を習得したり、独自プロジェクトで代替実装アプローチを探求したりするのに役立ちます。

- [Aspose.BarCode for .NET で DataMatrix バーコードを生成する方法 – ステップバイステップガイド](/barcode/english/net/datamatrix-barcode-configuration/)
- [Aspose.BarCode for .NET (C#) で ASCII モードの DataMatrix バーコードを生成する](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-ascii/)
- [Aspose.BarCode for .NET で DataMatrix バーコード (ECC 200) を生成する方法](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-ecc-200-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}