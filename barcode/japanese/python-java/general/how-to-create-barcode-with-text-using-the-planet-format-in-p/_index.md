---
category: general
date: 2026-11-27
description: テキスト付きバーコードの作成方法と、Pythonでプラネットバーコードを生成する方法を学びましょう—高解像度PNG出力のためのステップバイステップガイド。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode with text
- how to generate barcode
- generate planet barcode
- Python barcode generation
- high‑resolution barcode PNG
language: ja
lastmod: 2026-11-27
og_description: テキスト付きバーコードを作成し、Pythonでプラネットバーコードを生成します。高解像度PNGを出力する完全ガイドに従ってください。
og_image_alt: Screenshot showing how to create barcode with text using the Planet
  barcode generator
og_title: Pythonでテキスト付きバーコードを作成 – Planetバーコードを簡単に生成
schemas:
- author: Aspose
  dateModified: '2026-11-27'
  description: Learn how to create barcode with text and generate planet barcode in
    Python—step‑by‑step guide for high‑resolution PNG output.
  headline: How to create barcode with text using the Planet format in Python
  type: TechArticle
tags:
- barcode
- Python
- Planet format
- image generation
title: PythonでPlanetフォーマットを使用してテキスト付きバーコードを作成する方法
url: /ja/python-java/general/how-to-create-barcode-with-text-using-the-planet-format-in-p/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# PythonでPlanetフォーマットを使用してテキスト付きバーコードを作成する方法

メールシステム用に**テキスト付きバーコードを作成**する必要がある場合、このチュートリアルではその手順を正確に示します。Planetバーコードを生成し、解像度を調整し、結果をPNG画像として保存する簡潔なエンドツーエンドの例をご覧いただけます。

バーコードの生成は、物流、在庫管理、チケット発行アプリケーションで一般的な要件です。このガイドでは、**バーコードを生成する方法**だけでなく、各設定ステップが重要な理由と典型的な落とし穴を回避する方法も学びます。

## 学べること

* カスタムテキストでPlanetバーコードジェネレータを設定する。
* X‑dimension を調整して画像の鮮明さを向上させる。
* バーコードをPNGファイルとして保存し、印刷やウェブ表示に利用できるようにする。
* 例を他のバーコードタイプや出力フォーマットに拡張する。

**前提条件**

* Python 3.8 以上。
* `aspose-barcode` パッケージ（または `BarcodeGenerator`、`EncodeTypes`、`BarCodeImageFormat` を提供する互換ライブラリ）。
* Python スクリプトの基本的な知識。

必要なパッケージは以下のコマンドでインストールできます。

```bash
pip install aspose-barcode
```

---

## ステップ 1: テキスト付きバーコードを作成 – ジェネレータの初期化

最初に行うべきことは、使用するシンボロジーとエンコードするテキストを認識した `BarcodeGenerator` インスタンスを作成することです。Planetバーコードの場合、`EncodeTypes.Planet` 列挙値がライブラリにUSPS Planet 仕様に従うよう指示します。

```python
# Import the necessary classes from the Aspose.BarCode library
from aspose.barcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat

# Step 1: Initialize the generator with the desired text
# The text "123456" will appear beneath the Planet barcode pattern.
gen = BarcodeGenerator(EncodeTypes.Planet, "123456")
```

**なぜ重要か:**  
`BarcodeGenerator` オブジェクトはバーコードのすべての設定をカプセル化します。コンストラクタでテキストを渡すことで、エンコードされた値が以降のプロセス全体で不変になることが保証され、後での不一致を防止します。

---

## ステップ 2: 設定を調整 – 高解像度バーコードを生成する方法

低解像度のバーコードはラベルプリンタで印刷するとぼやけて見えることがあります。X‑dimension（モジュール幅）は各バーのサイズを制御します。4ピクセルに設定すると、ほとんどの最新プリンタに適した鮮明で高解像度の画像が得られます。

```python
# Step 2: Increase the X‑dimension to 4 pixels for better clarity
gen.parameters.barcode.x_dimension.pixels = 4
```

**説明:**  
* `gen.parameters.barcode.x_dimension.pixels` は単一モジュールの実際の幅に直接対応します。  
* **4** の値は各バーが4ピクセル幅であることを意味し、300 dpi で約0.127 mm に相当します—USPS Planet バーコードの推奨範囲内です。  

**プロのコツ:** 別の DPI が必要な場合は、ピクセル幅をそれに合わせて計算してください（例: 150 dpi では2ピクセル、600 dpi では8ピクセル）。

---

## ステップ 3: 画像を保存 – PlanetバーコードをPNGとして生成

ジェネレータの設定が完了したら、バーコードを画像ファイルとしてレンダリングできます。PNG はロスレス形式で、正確なモジュールパターンが保持されます。

```python
# Step 3: Save the generated barcode as a PNG image
output_path = "output/PostalPlanetBarHeightNone.png"
gen.save(output_path, BarCodeImageFormat.Png)
print(f"Barcode saved to {output_path}")
```

**結果:**  
スクリプトを実行すると `PostalPlanetBarHeightNone.png` という名前のファイルが作成され、文字列 “123456” をエンコードした Planet バーコードが含まれます。画像サイズは選択した X‑dimension に応じておおよそ 200 × 100 ピクセルになります。

---

## オプション: バーコードを目視で確認

生成された PNG を任意の画像ビューアで開き、バーコードが鮮明で、パターンの下に人が読めるテキストが表示されていることを確認できます。

```python
from PIL import Image

img = Image.open(output_path)
img.show()
```

画像がぼやけている場合は、**ステップ 2** に戻り、バーがはっきりと定義されるまで X‑dimension を増やしてください。

---

## 一般的なバリエーションとエッジケース

| 状況 | 調整 |
|-----------|------------|
| **Different text length** | Planet バーコードは最大 12 桁の数字をサポートします。これを超えると、ライブラリが例外をスローします。 |
| **Alternative output format** | `BarCodeImageFormat.Png` を `BarCodeImageFormat.Jpeg` または `BarCodeImageFormat.Bmp` に置き換えて、他の用途に対応します。 |
| **Custom foreground/background colors** | `gen.parameters.barcode.barcode_color = Color.Blue` と `gen.parameters.barcode.back_color = Color.White` を使用します。 |
| **No human‑readable text** | `gen.parameters.barcode.hide_code_text = True` を設定すると、下部のキャプションなしでバーコードを生成できます。 |
| **Batch generation** | 文字列のリストをループし、各文字列に対して新しい `BarcodeGenerator` を作成し、固有の名前のファイルに保存します。 |

これらのバリエーションにより、幅広いビジネス要件に合わせた **planet バーコード** ファイルを生成できます。

---

## 完全なスクリプト – 実行準備完了

以下は、コピーして貼り付けて実行できる、完全な自己完結型スクリプトです。すべてのインポート、エラーハンドリング、コメントが含まれています。

```python
"""
Complete example: create barcode with text and generate a Planet barcode PNG.
Author: Your Name
Date: 2026-11-27
"""

import os
from aspose.barcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat
from aspose.barcode import Color  # optional, for color customization
from PIL import Image

def create_planet_barcode(text: str, output_dir: str, x_dim_pixels: int = 4) -> str:
    """
    Generates a Planet barcode with the given text and saves it as a PNG.
    
    Args:
        text: Numeric string to encode (max 12 characters for Planet).
        output_dir: Directory where the PNG will be stored.
        x_dim_pixels: Width of a single module in pixels (default 4 for high resolution).
    
    Returns:
        Full path to the saved PNG file.
    """
    if not text.isdigit():
        raise ValueError("Planet barcode requires numeric text only.")
    if len(text) > 12:
        raise ValueError("Planet barcode supports up to 12 digits.")
    
    # Ensure the output directory exists
    os.makedirs(output_dir, exist_ok=True)
    
    # Initialize the generator with the desired text
    gen = BarcodeGenerator(EncodeTypes.Planet, text)
    
    # Adjust resolution via X‑dimension
    gen.parameters.barcode.x_dimension.pixels = x_dim_pixels
    
    # Build the output file path
    file_name = f"Planet_{text}.png"
    full_path = os.path.join(output_dir, file_name)
    
    # Save as PNG
    gen.save(full_path, BarCodeImageFormat.Png)
    
    return full_path

if __name__ == "__main__":
    try:
        result_path = create_planet_barcode("123456", "output")
        print(f"Barcode successfully generated: {result_path}")
        
        # Open the image for a quick visual check
        Image.open(result_path).show()
    except Exception as e:
        print(f"Error: {e}")
```

**スクリプトの説明**

* `create_planet_barcode` 関数は 3 つの主要ステップをカプセル化し、コードの再利用性を高めます。
* 入力検証により、Planet 仕様（数値のみ、最大 12 桁）に従っていることが保証されます。
* 関数は出力フォルダを自動的に作成するため、ディレクトリを手動で管理する必要がありません。
* 生成後、スクリプトは Pillow（`PIL`）を使用して画像を開き、すぐに確認できます。

---

## 結論

これで、Python で **テキスト付きバーコードを作成**し、**planet バーコード**ファイルを生成する方法が分かりました。ガイドでは、初期化、解像度調整、ファイル出力に加えて、オプションのカスタマイズや一般的なエッジケースも取り上げました。

ここからは次のことができます：

* `EncodeTypes.Planet` を他のシンボロジー（例: `EncodeTypes.Code128`）に置き換えて、同じパターンを再利用する。
* 関数をウェブサービスに組み込み、要求に応じてバーコード画像を返す。
* バッチ処理を試して、数千枚のバーコードを大量郵送用に生成する。

スクリプトをプロジェクトの要件に合わせて自由にカスタマイズし、結果をコメントで共有してください。コーディングを楽しんで！

## 次に学ぶべきことは？

以下のチュートリアルは、本ガイドで示した手法を基にした密接に関連するトピックをカバーしています。各リソースには、ステップバイステップの解説付きの完全な動作コード例が含まれており、追加の API 機能を習得し、プロジェクトで代替実装アプローチを検討するのに役立ちます。

- [Pythonでバーコードを生成する方法 – 完全ステップバイステップガイド](/barcode/english/python-java/general/how-to-generate-barcode-in-python-complete-step-by-step-guid/)
- [PythonでバーコードPNGを作成 – ステップバイステップガイド](/barcode/english/python-java/general/create-barcode-png-in-python-step-by-step-guide/)
- [PythonでPlanetバーコードPNGを作成する方法](/barcode/english/python-java/general/how-to-create-planet-barcode-png-with-python/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}