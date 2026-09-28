---
category: general
date: 2026-08-12
description: Pythonで全方向データバーを作成し、Aspose.BarCode を使用して Python のバーコード画像の作成方法を学びましょう。完全なソリューションのためのステップバイステップガイドをご確認ください。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create omni directional databar
- create barcode image python
language: ja
lastmod: 2026-08-12
og_description: Pythonで全方向データバーを作成し、数分でバーコード画像を生成します。このチュートリアルは、完全な実行可能な例を示しています。
og_image_alt: example of create omni directional databar barcode image in Python
og_title: 全方向データバーの作成 – 完全Pythonガイド
schemas:
- author: Aspose
  dateModified: '2026-08-12'
  description: Create omni directional databar with Python and learn how to create
    barcode image python using Aspose.BarCode. Follow the step‑by‑step guide for a
    complete solution.
  headline: Create omni directional databar and barcode image in Python
  type: TechArticle
tags:
- barcode
- Python
- Aspose
- DataBar
title: Pythonで全方向データバーとバーコード画像を作成する
url: /ja/python-java/general/create-omni-directional-databar-and-barcode-image-in-python/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Python でオムニ方向データバーとバーコード画像を作成する

Python プロジェクトで **オムニ方向データバーを作成** したい場合、このガイドではその手順と **Python でバーコード画像を作成** する方法を Aspose.BarCode ライブラリを使って解説します。実行可能なスクリプトが提供され、異なるアスペクト比の PNG ファイルが 2 つ生成されます。

オムニ方向仕様に準拠した DataBar の生成は、小売や物流アプリケーションで一般的な要件です。本チュートリアルではインストール方法、X‑ディメンションの設定、アスペクト比の調整、最終画像の保存までをカバーします。外部サービスは不要で、すべてローカルで実行できます。

## 必要なもの

開始する前に以下を確認してください。

* Python 3.8 以上がインストールされていること。
* ターミナルまたはコマンドプロンプトが使用できること。
* バーコード画像を保存するフォルダーへの書き込み権限があること。

唯一のサードパーティ依存は **Aspose.BarCode for Python via .NET** で、オムニ方向 DataBar タイプを標準でサポートしています。

## 手順 1: Aspose.BarCode for Python をインストール

Aspose.BarCode はサンプルコードで使用する `BarcodeGenerator` クラスを提供します。`pip` でパッケージをインストールします。

```bash
pip install aspose-barcode
```

このパッケージには必要な .NET ランタイムバインディングが含まれているため、別途 .NET SDK をインストールする必要はありません。

## 手順 2: ライブラリをインポートしジェネレータを作成

スクリプトの最初の行で、スタックされたオムニ方向 DataBar 用のジェネレータを作成します。サンプルデータとして GTIN‑14 値 `(01)12345678901231` を使用しています。

```python
# Step 2: Import classes and create the generator
from aspose.barcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat

# Create a generator for a stacked Omni‑directional DataBar with the required data
barcode_generator = BarcodeGenerator(
    EncodeTypes.DATABAR_STACKED_OMNIDIRECTIONAL,
    "(01)12345678901231"
)
```

*このステップが重要な理由*: `EncodeTypes.DATABAR_STACKED_OMNIDIRECTIONAL` 定数は、ライブラリに値をオムニ方向 DataBar としてエンコードさせます。これは多くの POS スキャナで要求されるフォーマットです。

## 手順 3: X‑ディメンション（モジュール幅）を設定

X‑ディメンションは最小バー モジュールの幅を定義します。`2` ピクセルに設定すると、ファイルサイズが過大になることなく、読み取りやすいバーコードが生成されます。

```python
# Step 3: Set the basic X‑dimension (width of the smallest module) in pixels
barcode_generator.parameters.barcode.x_dimension.pixels = 2
```

*このステップが重要な理由*: X‑ディメンションを調整することで、可読性と画像サイズのバランスを取れます。小さすぎると低解像度プリンタでの印刷品質が低下します。

## 手順 4: アスペクト比を設定し最初の画像を保存

アスペクト比は DataBar の全体的な高さと幅の比率に影響します。`15` のアスペクト比はコンパクトなビジュアルスタイルを作り出します。

```python
# Step 4: Configure an aspect ratio of 15 and save the first image
barcode_generator.parameters.barcode.data_bar.aspect_ratio = 15
barcode_generator.save("output/StackedAR15.png", BarCodeImageFormat.Png)
```

> **プロのコツ**: `pathlib.Path` を使って出力パスを構築すると、欠落しているディレクトリが自動的に作成されます。

```python
from pathlib import Path

output_dir = Path("output")
output_dir.mkdir(parents=True, exist_ok=True)
barcode_generator.save(output_dir / "StackedAR15.png", BarCodeImageFormat.Png)
```

## 手順 5: アスペクト比を変更して別のビジュアルスタイルを作成し、別画像を保存

アスペクト比を `30` に変更すると、特定のスキャナハードウェアで必要とされる高さのあるバーコードが生成されます。

```python
# Step 5: Change the aspect ratio to 30 and save the second image
barcode_generator.parameters.barcode.data_bar.aspect_ratio = 30
barcode_generator.save(output_dir / "StackedAR30.png", BarCodeImageFormat.Png)
```

*このステップが重要な理由*: 小売業者やスキャナデバイスはそれぞれサイズ制約が異なります。1 つのスクリプトで両方のアスペクト比を生成できれば、コードを重複させずに必要なスタイルを作成できます。

## 完全なスクリプト – Python でオムニ方向データバーとバーコード画像を作成

以下はこれまでの手順をすべて組み込んだ実行可能なサンプルです。`generate_databar.py` として保存し、`python generate_databar.py` で実行してください。

```python
#!/usr/bin/env python3
"""
Complete example that creates an omni directional databar
and demonstrates how to create barcode image python using Aspose.BarCode.
"""

# Import required classes
from aspose.barcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat
from pathlib import Path

def main():
    # Define output directory and ensure it exists
    output_dir = Path("output")
    output_dir.mkdir(parents=True, exist_ok=True)

    # Initialize the generator with Omni‑directional DataBar data
    generator = BarcodeGenerator(
        EncodeTypes.DATABAR_STACKED_OMNIDIRECTIONAL,
        "(01)12345678901231"
    )

    # Set X‑dimension to 2 pixels for good readability
    generator.parameters.barcode.x_dimension.pixels = 2

    # First visual style – aspect ratio 15
    generator.parameters.barcode.data_bar.aspect_ratio = 15
    generator.save(output_dir / "StackedAR15.png", BarCodeImageFormat.Png)

    # Second visual style – aspect ratio 30
    generator.parameters.barcode.data_bar.aspect_ratio = 30
    generator.save(output_dir / "StackedAR30.png", BarCodeImageFormat.Png)

    print(f"Images saved to: {output_dir.resolve()}")

if __name__ == "__main__":
    main()
```

### 期待される出力

スクリプトを実行すると次のファイルが作成されます。

```
output/StackedAR15.png   # DataBar with aspect ratio 15
output/StackedAR30.png   # DataBar with aspect ratio 30
```

両方の画像は有効なオムニ方向 DataBar を示しており、標準的な小売機器でスキャン可能です。

![Python で作成したオムニ方向データバーとバーコード画像の例](example_databar.png "Python で作成したオムニ方向データバーとバーコード画像")

*上の画像は、保存された 2 つの PNG ファイルを示すプレースホルダーです。*

## よくある問題の対処法

| 問題 | 原因 | 対策 |
|------|------|------|
| `ImportError: No module named aspose` | Aspose.BarCode がインストールされていない、または別の環境にインストールされている | 正しい仮想環境をアクティブにし、`pip install aspose-barcode` を実行 |
| 保存時の `PermissionError` | スクリプトが対象フォルダーへの書き込み権限を持っていない | 自分が所有するディレクトリを選択するか、適切な権限でスクリプトを実行 |
| バーコードがスキャンできない | X‑ディメンションが小さすぎる、またはアスペクト比がスキャナに合わない | `x_dimension.pixels` を 3 または 4 に増やし、`aspect_ratio` を 20, 25 などで試す |
| .NET ランタイムが見つからない | Aspose.BarCode は Windows/Linux 上で .NET ランタイムに依存している | Microsoft のサイトから最新の .NET ランタイムをインストール。パッケージのドキュメントにプラットフォーム別の手順あり |

## サンプルの拡張

スクリプトを他の DataBar バリアント（例: `DATABAR_STACKED`, `DATABAR_EXPANDED`）に対応させることも可能です。`EncodeTypes` 定数を適切に置き換えてください。

```python
generator = BarcodeGenerator(EncodeTypes.DATABAR_EXPANDED, "(01)12345678901231")
```

PDF にバーコードを埋め込む必要がある場合は、Aspose.PDF for Python が PNG ファイルを直接インポートできるほか、`save` メソッドに `BarCodeImageFormat.Pdf` を指定して保存することもできます。

## 結論

本チュートリアルでは Aspose.BarCode を使用して **オムニ方向データバーを作成** し、**Python でバーコード画像を作成** する方法を示しました。これで、異なるアスペクト比の PNG ファイルを生成し、一般的な落とし穴に対処し、他のバーコード形式へ拡張できる完全なスクリプトが手に入ります。

次は QR コードの生成、PDF 請求書へのバーコード埋め込み、または大規模商品カタログ向けのバッチ処理自動化に挑戦してみてください。ここで学んだ `BarcodeGenerator` パターンを応用すれば、さまざまなシナリオに対応できます。コーディングを楽しんでください！

## 次に学ぶべきこと

以下のチュートリアルは、本ガイドで示した手法をベースにした関連トピックを扱っています。各リソースには完全な動作コード例とステップバイステップの解説が含まれており、API の追加機能習得や代替実装アプローチの探求に役立ちます。

- [Generate barcode image – GS1 Coupon UPC-A Databar](/barcode/english/net/gs1-barcode-encoding/gs1-coupon-upc-a-databar-configuration/)
- [Create DotCode barcode image – rows & columns (Aspose.BarCode)](/barcode/english/net/dotcode-barcode-configuration/dotcode-rows-columns-configuration/)
- [How to create barcode image and render it in Java](/barcode/english/java/barcode-rendering-techniques/rendering-barcode-image-instance/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}