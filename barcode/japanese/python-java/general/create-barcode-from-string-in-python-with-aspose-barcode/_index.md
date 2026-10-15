---
category: general
date: 2026-10-15
description: Aspose.BarCode を使用して Python で文字列からバーコードを作成し、Code 128 バーコードの生成方法と数行でバーコード
  PNG を保存する方法を学びましょう。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode from string
- generate code 128 barcode
- how to save barcode
- generate barcode png
- encode data into barcode
language: ja
lastmod: 2026-10-15
og_description: Pythonで文字列からバーコードを作成し、データをCode 128バーコードにエンコードして、Aspose.BarCodeでPNGファイルとして保存する。
og_image_alt: Screenshot of a generated Code 128 barcode saved as a PNG image
og_title: Pythonで文字列からバーコードを作成する – ステップバイステップガイド
schemas:
- author: Aspose
  dateModified: '2026-10-15'
  description: Create barcode from string in Python using Aspose.BarCode, learn how
    to generate Code 128 barcode and save barcode PNG in just a few lines.
  headline: Create barcode from string in Python with Aspose.BarCode
  type: TechArticle
- questions:
  - answer: Replace `EncodeTypes.CODE_128` with another enum value such as `EncodeTypes.QR`,
      `EncodeTypes.EAN_13`, or `EncodeTypes.PDF_417`. The rest of the code remains
      the same.
    question: What if I need a different symbology?
  - answer: Code 128 supports the full 128‑character ASCII set. For Unicode data,
      consider using QR Code (`EncodeTypes.QR`) which handles UTF‑8 natively.
    question: Can I generate a barcode from non‑ASCII characters?
  - answer: Pass a different member of `BarCodeImageFormat` to `save`, e.g., `BarCodeImageFormat.JPEG`
      or `BarCodeImageFormat.BMP`.
    question: How do I change the image format?
  - answer: Wrap the `save` call in a try/except block and handle `PermissionError`
      gracefully, perhaps by prompting the user for an alternative path.
    question: What if the output directory is read‑only?
  type: FAQPage
tags:
- barcode
- Python
- Aspose
- Code128
title: Aspose.BarCode を使用して Python で文字列からバーコードを作成する
url: /ja/python-java/general/create-barcode-from-string-in-python-with-aspose-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Pythonで文字列からバーコードを作成する (Aspose.BarCode)

Pythonで**文字列からバーコードを作成**する必要がある場合、このガイドではAspose.BarCodeを使用した正確な手順を示します。**Code 128バーコードの生成**、外観の調整、**バーコードPNGの保存**方法を学べます。このソリューションはPython 3.9+ をサポートする任意のプラットフォームで動作し、数行のコードだけで実現できます。

バーコードをプログラムで生成することで、手動入力エラーを排除し、在庫管理、チケット発行、ラベル印刷などのワークフローを効率化できます。このチュートリアルの最後までに、**データをバーコードにエンコード**し、サイズをカスタマイズし、必要な場所に画像を保存できるようになります。

## 前提条件

- Python 3.9 以上がインストールされていること  
- Aspose.BarCode パッケージをダウンロードするためのインターネット接続  
- PNG ファイルを保存するディレクトリへの書き込み権限  

仮想環境を使用している場合（強く推奨）、今すぐアクティベートしてください。

## Aspose.BarCode Python パッケージのインストール

Aspose は、Code 128 を含むすべての一般的なバーコードシンボロジーを処理できる純粋な Python ライブラリを提供しています。pip でインストールします：

```bash
pip install aspose-barcode
```

*プロのコツ:* バージョンを固定（例: `aspose-barcode==23.9`）して、運用環境で予期しない破壊的変更を防ぎましょう。

## Pythonで文字列からバーコードを作成する

最初の実装ステップは、必要なクラスをインポートし、目的のシンボロジー用のジェネレータをインスタンス化することです。この例では **Code 128** を使用します。Code 128 は英数字データに最適です。

```python
# Step 1: Import the Aspose.BarCode classes
from asposebarcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat

# Step 2: Create a generator for Code 128 and provide the data string
barcode_generator = BarcodeGenerator(EncodeTypes.CODE_128, "1234567890")
```

**なぜ重要か:** `EncodeTypes.CODE_128` はライブラリに適用するバーコード規格を指示し、2 番目の引数（`"1234567890"`）は **バーコードにエンコードしたい文字列** です。Code 128 用に最大 80 文字の任意の ASCII 文字列に置き換えることができます。

## Code 128 バーコードの生成

ジェネレータの準備ができたら、メモリ上でバーコード画像を生成できます。ライブラリは提供されたデータに基づいて自動的にバーコードを描画します。

```python
# Step 3: Render the barcode to an image object (in memory)
barcode_image = barcode_generator.generate_barcode_image()
```

この時点で `barcode_image` は `System.Drawing.Image` のインスタンス（Windows の場合）または他のプラットフォーム上の互換画像オブジェクトです。GUI に直接表示したり、PDF に埋め込んだり、さらにカスタマイズを続けることができます。

## バーコードの外観調整

視覚的プロパティを微調整することで、特定の環境でバーコードが確実に読み取れるようになります。一般的な調整項目は X ディメンション（最細バーの幅）と全体のバー高さです。

```python
# Step 4: Adjust appearance – X dimension and bar height
barcode_generator.parameters.barcode.x_dimension.pixels = 2   # width of the smallest bar
barcode_generator.parameters.barcode.bar_height.pixels = 100  # height of the bars (optional)
```

*なぜこれらの値を調整するのか？*  
- **X ディメンション** はバーコードの密度に影響し、値が小さいほど小さなラベルに収まる密なバーコードになります。  
- **バー高さ** は可読性に影響し、バーが高いほどスキャナが遠距離から検出しやすくなります。

`parameters` オブジェクトを使用して色を変更したり、余白を追加したり、人が読めるテキストを埋め込んだりすることもできます。オプションの全リストは Aspose.BarCode のドキュメントをご参照ください。

## バーコードを PNG として保存する方法

生成した画像を保存することが、**文字列からバーコードを作成**するワークフローの最終ステップです。ライブラリは複数の形式をサポートしており、PNG はロスレスで広くサポートされています。

```python
# Step 5: Save the barcode image to a PNG file
output_path = "output/barcode.png"
barcode_generator.save(output_path, BarCodeImageFormat.PNG)
```

`save` メソッドは指定した形式で画像をファイルシステムに書き込みます。対象ディレクトリ（この例では `output/`）が存在しない場合、Python は `FileNotFoundError` をスローします。事前にディレクトリを作成するか、例外を処理してください：

```python
import os

output_dir = os.path.dirname(output_path)
os.makedirs(output_dir, exist_ok=True)   # ensures the directory exists
barcode_generator.save(output_path, BarCodeImageFormat.PNG)
```

**期待結果:** スクリプトを実行すると、`output/barcode.png` に `"1234567890"` をエンコードしたクリアな Code 128 バーコードが保存されます。任意の画像ビューアでファイルを開くと、スキャン可能な黒オン白のバーコードが表示されます。

## 完全な実行可能サンプル

すべての要素を組み合わせた、コピー＆ペーストで実行できる自己完結型スクリプトを以下に示します。

```python
"""
Complete example: create barcode from string, generate Code 128 barcode,
customize appearance, and save barcode PNG using Aspose.BarCode.
"""

import os
from asposebarcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat

# 1. Define input data and output location
data_to_encode = "1234567890"
output_path = "output/barcode.png"

# 2. Ensure the output directory exists
os.makedirs(os.path.dirname(output_path), exist_ok=True)

# 3. Initialise the generator for Code 128
generator = BarcodeGenerator(EncodeTypes.CODE_128, data_to_encode)

# 4. Optional: tweak visual parameters
generator.parameters.barcode.x_dimension.pixels = 2
generator.parameters.barcode.bar_height.pixels = 100

# 5. Save as PNG
generator.save(output_path, BarCodeImageFormat.PNG)

print(f"Barcode saved to {output_path}")
```

`python create_barcode.py` でスクリプトを実行します。すべて正しくインストールされていれば、次のように表示されます：

```
Barcode saved to output/barcode.png
```

PNG ファイルを開き、任意のバーコードスキャナアプリでバーコードが元の文字列と一致することを確認してください。

## よくある質問とエッジケース

- **別のシンボロジーが必要な場合は？**  
  `EncodeTypes.CODE_128` を `EncodeTypes.QR`、`EncodeTypes.EAN_13`、`EncodeTypes.PDF_417` などの別の enum 値に置き換えます。残りのコードは同じです。

- **非 ASCII 文字からバーコードを生成できますか？**  
  Code 128 は 128 文字の ASCII 全セットをサポートしています。Unicode データの場合は、UTF‑8 をネイティブに扱える QR Code（`EncodeTypes.QR`）の使用を検討してください。

- **画像形式を変更するには？**  
  `save` に `BarCodeImageFormat` の別のメンバーを渡します。例: `BarCodeImageFormat.JPEG` や `BarCodeImageFormat.BMP`。

- **出力ディレクトリが読み取り専用の場合は？**  
  `save` 呼び出しを try/except ブロックで囲み、`PermissionError` を適切に処理します。必要に応じて代替パスをユーザーに促すこともできます。

- **パフォーマンスのコツ:**  
  ループで数千個のバーコードを生成すると CPU に負荷がかかります。単一の `BarcodeGenerator` インスタンスを再利用し、イテレーション間で `generator.parameters.barcode.code_text` のみを更新してください。

## 結論

これで、Python で Aspose.BarCode を使用して **文字列からバーコードを作成**し、**Code 128 バーコードを生成**し、サイズをカスタマイズし、**バーコード PNG をディスクに保存**する方法が分かりました。このエンドツーエンドのソリューションにより、**データをバーコードにエンコード**することが迅速かつ確実に行え、在庫管理システム、チケットプラットフォーム、または機械可読な識別子が必要なあらゆるアプリケーションにバーコードを簡単に統合できます。

**次のステップ**

- QR や DataMatrix など、他のシンボロジー（`generate code 128 barcode` の代替）を調査する。  
- エラーハンドリングロジックを追加し、プロダクションでの使用にスクリプトを堅牢にする（`how to save barcode` の失敗対策）。  
- 生成した PNG を PDF や HTML レポートに埋め込む（Web 用の `generate barcode png`）。

コーディングを楽しんで、プログラムによるバーコード生成のシンプルさを体感してください！

## 次に学ぶべきことは？

以下のチュートリアルは、本ガイドで示した手法を基にした密接に関連するトピックを扱っています。各リソースには、ステップバイステップの解説と完全な動作コード例が含まれており、追加の API 機能を習得し、独自プロジェクトで代替実装アプローチを検討するのに役立ちます。

- [Aspose.BarCode を使用して Code 128 バーコードを生成し、バーコード画像を保存する方法](/barcode/english/python/general/how-to-generate-code-128-barcode-and-save-barcode-image-with/)
- [Aspose.Barcode を使用して Python で QR コード画像を生成する方法 – 完全ガイド](/barcode/english/python/general/how-to-generate-qr-code-image-in-python-with-aspose-barcode/)
- [Python でバーコード PNG を作成する – 完全 Aspose.Barcode ガイド](/barcode/english/python-java/general/create-barcode-png-in-python-full-aspose-barcode-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}