---
category: general
date: 2026-07-30
description: PythonでAspose.BarCodeを使用してバーコードを生成する方法 – 寸法の設定、塗りつぶしの変更、PNG画像の保存を数分で学びましょう。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to generate barcode
- how to set dimensions
- how to change fill
- generate barcode with aspose
language: ja
lastmod: 2026-07-30
og_description: PythonでAspose.BarCodeを使用してバーコードを迅速に生成する方法。サイズの設定、塗りつぶしの変更、任意のアプリ向けにPNGファイルをエクスポートする方法をご紹介します。
og_image_alt: Screenshot showing a filled Planet barcode and an empty Planet barcode
  generated with Aspose.BarCode
og_title: Aspose.BarCodeでバーコードを生成する方法 – Pythonガイド
schemas:
- author: Aspose
  dateModified: '2026-07-30'
  description: How to generate barcode using Aspose.BarCode in Python – learn how
    to set dimensions, change fill, and save PNG images in minutes.
  headline: How to generate barcode with Aspose.BarCode in Python
  type: TechArticle
- description: How to generate barcode using Aspose.BarCode in Python – learn how
    to set dimensions, change fill, and save PNG images in minutes.
  name: How to generate barcode with Aspose.BarCode in Python
  steps:
  - name: Why set `x_dimension.pixels`?
    text: Even though the default works, you often need to **how to set dimensions**
      to match printer DPI or UI constraints. The `x_dimension` property controls
      the width of a single bar in pixels; larger numbers yield a thicker barcode,
      while smaller numbers make it more compact.
  - name: Expected output
    text: 'Running the script prints something like:'
  - name: 5.1 Making the barcode larger for print
    text: 'If you’re printing on a 300 dpi label printer, a 4‑pixel bar might look
      tiny. Increase the `x_dimension` to, say, 8 pixels:'
  - name: 5.2 Making the barcode smaller for mobile screens
    text: Conversely, for a mobile app you might want a tighter barcode. Setting `x_dimension`
      to 2 pixels reduces the width without breaking readability (Aspose handles the
      scaling automatically).
  type: HowTo
tags:
- barcode
- Aspose
- Python
title: PythonでAspose.BarCodeを使用してバーコードを生成する方法
url: /ja/python-java/general/how-to-generate-barcode-with-aspose-barcode-in-python/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.BarCode を使用した Python でのバーコード生成方法

Python プロジェクトで低レベルの画像ライブラリと格闘せずに **バーコードを生成する方法** を考えたことはありませんか？ あなただけではありません。配送ラベルシステム、チケットプラットフォームの構築、あるいはデモ用に手軽な QR コードが必要な場合でも、バーコード生成をマスターすれば試行錯誤に費やす時間を大幅に削減できます。

このチュートリアルでは、Aspose.BarCode ライブラリを使用して **バーコードを生成する方法** を示す、完全に実行可能なサンプルをステップバイステップで解説します。次元の設定方法や塗りつぶしの変更方法もカバーします。最後には、出力フォルダーに塗りつぶしバーと空白バーの 2 つの PNG ファイルが生成されます。

## 前提条件

始める前に、以下が揃っていることを確認してください。

* Python 3.8+ がインストールされていること（コードは Windows、macOS、Linux で動作します）
* 有効な Aspose.BarCode for Python via .NET ライセンス（無料トライアルから開始可能）
* 仮想環境で `pip install aspose-barcode` を実行したこと
* 書き込み可能なフォルダー（例では `YOUR_DIRECTORY` と呼びます）

他のサードパーティパッケージは必要ありません。

## 手順 1: Aspose.BarCode のインストールとインポート

まず最初に、ライブラリ自体が必要です。ターミナルで以下を一度実行してください：

```bash
pip install aspose-barcode
```

これで使用するクラスをインポートできます。ここが **バーコードを生成する方法** が本格的に始まる部分で、正しいインポートがなければジェネレータを呼び出すことすらできません。

```python
# Import the required Aspose.BarCode classes
from aspose.barcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat
```

> **プロのコツ:** 仮想環境を使用している場合は、`pip install` を実行する前に環境をアクティブにしてください。グローバルな Python が整理された状態を保てます。

## 手順 2: Planet バーコードの作成 – デフォルト（塗りつぶし）バージョン

Planet バーコードは郵便サービスで使用される古典的な 2‑of‑5 シンボロジーです。まずは最もシンプルなケース、塗りつぶしバーコードから始めましょう。このステップはデフォルト設定で **バーコードを生成する方法** を示します。

```python
# Step 2: Create a Planet barcode with filled bars (default)
filled_barcode = BarcodeGenerator(EncodeTypes.Planet, "123456")
filled_barcode.parameters.barcode.x_dimension.pixels = 4   # default width per bar
filled_barcode.save("YOUR_DIRECTORY/PostalPlanetFilled.png", BarCodeImageFormat.Png)
```

### なぜ `x_dimension.pixels` を設定するのか？

デフォルトでも動作しますが、プリンターの DPI や UI の制約に合わせて **寸法の設定方法** が必要になることが多いです。`x_dimension` プロパティは 1 本のバーの幅（ピクセル）を制御します。数値が大きいほど太いバーになり、数値が小さいほどコンパクトになります。

## 手順 3: Planet バーコードを空白（塗りつぶしなし）バーで作成

次に **塗りつぶしの変更方法** に答えます。`filled_bars` フラグを切り替えることで、同じデータをエンコードしつつ、実線の黒バーからアウトラインだけのバーへと変更できます。

```python
# Step 3: Create a Planet barcode with empty (unfilled) bars
empty_barcode = BarcodeGenerator(EncodeTypes.Planet, "123456")
empty_barcode.parameters.barcode.x_dimension.pixels = 4   # keep dimensions consistent
empty_barcode.parameters.barcode.filled_bars = False     # turn off fill
empty_barcode.save("YOUR_DIRECTORY/PostalPlanetEmpty.png", BarCodeImageFormat.Png)
```

`PostalPlanetFilled.png` と `PostalPlanetEmpty.png` を横に並べて開くと、視覚的な違いが分かります。塗りつぶしバージョンは実線の黒、空白バージョンはバーが輪郭として表示されます。UI オーバーレイで視覚的負荷を軽減したいときに便利です。

## 手順 4: 完全な実行可能スクリプト（完全なソリューション）

以下は `generate_planet_barcodes.py` というファイル名でコピー＆ペーストできる全プログラムです。インポートから画像保存までをすべて網羅しているので、足りない部分を探す必要はありません。

```python
#!/usr/bin/env python3
"""
Complete example: generate filled and empty Planet barcodes using Aspose.BarCode.
Demonstrates how to generate barcode, how to set dimensions, and how to change fill.
"""

from aspose.barcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat
import os

def ensure_output_dir(path: str) -> None:
    """Create the output directory if it doesn't exist."""
    if not os.path.isdir(path):
        os.makedirs(path)
        print(f"Created output directory: {path}")

def generate_filled_barcode(output_dir: str, data: str = "123456", x_dim: int = 4) -> str:
    """Generate a filled Planet barcode and return the file path."""
    generator = BarcodeGenerator(EncodeTypes.Planet, data)
    generator.parameters.barcode.x_dimension.pixels = x_dim
    file_path = os.path.join(output_dir, "PostalPlanetFilled.png")
    generator.save(file_path, BarCodeImageFormat.Png)
    return file_path

def generate_empty_barcode(output_dir: str, data: str = "123456", x_dim: int = 4) -> str:
    """Generate an empty (unfilled) Planet barcode and return the file path."""
    generator = BarcodeGenerator(EncodeTypes.Planet, data)
    generator.parameters.barcode.x_dimension.pixels = x_dim
    generator.parameters.barcode.filled_bars = False
    file_path = os.path.join(output_dir, "PostalPlanetEmpty.png")
    generator.save(file_path, BarCodeImageFormat.Png)
    return file_path

if __name__ == "__main__":
    # Define where the PNG files will be stored
    output_folder = "YOUR_DIRECTORY"
    ensure_output_dir(output_folder)

    filled_path = generate_filled_barcode(output_folder)
    empty_path = generate_empty_barcode(output_folder)

    print(f"Filled barcode saved to: {filled_path}")
    print(f"Empty barcode saved to: {empty_path}")
```

### 期待される出力

スクリプトを実行すると、以下のような出力が表示されます：

```
Created output directory: YOUR_DIRECTORY
Filled barcode saved to: YOUR_DIRECTORY/PostalPlanetFilled.png
Empty barcode saved to: YOUR_DIRECTORY/PostalPlanetEmpty.png
```

任意の画像ビューアで 2 つの PNG ファイルを開くと、クラシックな Planet バーコード（1 つは実線、もう 1 つは空白）が確認できます。どちらも文字列 `123456` をエンコードしています。

## 手順 5: 用途別に寸法を調整する

**寸法の設定方法** が分かったので、一般的なシナリオをいくつか見てみましょう。

### 5.1 印刷用にバーコードを大きくする

300 dpi のラベルプリンターで印刷する場合、4 ピクセルのバーは小さすぎるかもしれません。`x_dimension` を例えば 8 ピクセルに増やします：

```python
filled_barcode.parameters.barcode.x_dimension.pixels = 8
```

### 5.2 モバイル画面用にバーコードを小さくする

逆にモバイルアプリでは、よりコンパクトなバーコードが求められることがあります。`x_dimension` を 2 ピクセルに設定すると、可読性を損なうことなく幅が縮小されます（Aspose が自動的にスケーリングを処理します）。

```python
empty_barcode.parameters.barcode.x_dimension.pixels = 2
```

バーコードの高さはシンボロジーの仕様に基づいて自動的に調整されるため、幅だけを意識すれば大丈夫です。

## 手順 6: 高度な塗りつぶしオプションとその必要性

シンプルな `filled_bars` ブール値に加えて、Aspose.BarCode ではバーの色、背景色、さらにはグラデーションまでカスタマイズできます。**塗りつぶしの変更方法** を「塗りつぶし vs 空白」以上に拡張したい場合は、次のように記述できます：

```python
filled_barcode.parameters.barcode.barcode_color = System.Drawing.Color.from_argb(255, 0, 0, 255)  # blue bars
filled_barcode.parameters.barcode.back_color = System.Drawing.Color.from_argb(255, 255, 255, 255)   # white background
```

*(注: 上記は .NET のカラー構造体を使用しています。純粋な Python では適切な Aspose 列挙型を使用してください。)* これはブランディングに便利です。たとえば、バーコードの背景に企業ロゴをさりげなく埋め込むことが想像できます。

## よくある落とし穴と回避方法

| 症状 | 考えられる原因 | 対策 |
|---------|--------------|-----|
| 保存された PNG のバーコードがぼやけて見える | `x_dimension` が目標 DPI に対して低すぎる | `x_dimension` を増やすか、保存後に画像を拡大してください |
| スキャナーが空白バーコードを読み取れない | `filled_bars = False` が一部の旧式スキャナーでサポートされていない | 最大の互換性のためにデフォルトの塗りつぶしバージョンを使用してください |
| `ImportError: cannot import name 'BarcodeGenerator'` | Aspose.BarCode がインストールされていない、または .NET ランタイムが不一致 | `pip install aspose-barcode` で再インストールし、.NET Core ランタイムが存在することを確認してください |

## まとめ: 本記事でカバーした内容

* **バーコードを生成する方法**（Python の Aspose.BarCode）
* `x_dimension.pixels` を使用した **寸法の設定方法**
* `filled_bars` フラグによる **塗りつぶしの変更方法**（カラーカスタマイズの一例）
* 任意のデータ文字列に合わせてカスタマイズできる、完全なコピー＆ペースト可能スクリプト

## 次は何をすべきか？（次のステップと関連トピック）

このガイドが役立ったと感じたら、以下のテーマもぜひ探求してみてください。

* **QR コードの生成** (`EncodeTypes.QR`) – URL や連絡先情報に最適です。
* バーコード下にテキストキャプションを追加 (`parameters.caption`) して、人が読める値を表示。
* SVG や PDF など他の形式へエクスポート (`BarCodeImageFormat.Svg`, `BarCodeImageFormat.Pdf`) – ベクターグラフィックに最適。
* バッチ生成 – 製品 ID の CSV をループして、一括でバーコードカタログを作成。

これらのトピックはすべて、*generate barcode with aspose* と *how to set dimensions* という二次キーワードにも関連しています。

---

何か問題があればコメントで教えてください。また、独自のバリエーションを共有しても構いません。バーコード作成を楽しんでください！

## 次に学ぶべきことは？

以下のチュートリアルは、本ガイドで示した手法を基にした、密接に関連するトピックをカバーしています。各リソースには、ステップバイステップの解説と完全に動作するコード例が含まれており、追加の API 機能をマスターしたり、プロジェクトで代替実装アプローチを探求したりするのに役立ちます。

- [バーコード生成方法 - 1次元バーコードタイプ](/barcode/english/net/one-dimensional-barcode-types/)
- [Java で Aspose.BarCode を使用して code128 バーコード画像を作成する方法](/barcode/english/java/advanced-settings-and-optimization/saving-barcode-images-different-formats/)
- [Java で Aspose.BarCode を使用してバーコード画像にカラーを付ける方法](/barcode/english/java/image-manipulation/colorizing-barcode-image/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}