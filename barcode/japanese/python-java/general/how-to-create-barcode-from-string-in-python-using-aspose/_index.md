---
category: general
date: 2026-10-15
description: Aspose.Barcode for Python を使用して文字列からバーコードを作成します。バーコードの生成方法、サイズ設定、PNG
  への保存を数分で学びましょう。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode from string
- how to generate barcode
- barcode generator example
- generate postal barcode
- aspose barcode python
language: ja
lastmod: 2026-10-15
og_description: Aspose.Barcode for Python を使用して文字列からバーコードを作成します。このチュートリアルでは、郵便バーコードを生成し、PNG
  形式で保存する手順をステップバイステップで示します。
og_image_alt: Screenshot of a generated postal barcode saved as PNG
og_title: Pythonで文字列からバーコードを作成 – Asposeガイド
schemas:
- author: Aspose
  dateModified: '2026-10-15'
  description: Create barcode from string with Aspose.Barcode for Python. Learn how
    to generate barcode, set dimensions, and save as PNG in minutes.
  headline: How to create barcode from string in Python using Aspose
  type: TechArticle
tags:
- barcode
- python
- Aspose
title: Aspose を使用して Python で文字列からバーコードを作成する方法
url: /ja/python-java/general/how-to-create-barcode-from-string-in-python-using-aspose/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Python で文字列からバーコードを作成する方法（Aspose 使用）

文字列から **バーコードを作成** したい場合、Aspose.Barcode for Python を使えば簡単に実現できます。このガイドでは、**バーコードを生成** する方法、X‑ディメンションの調整方法、PNG ファイルとして保存する手順を数行のコードで紹介します。

また、**バーコードジェネレータのサンプル** も提供しているので、そのままコピーしてプロジェクトに組み込めます。外部スクリプトや複雑な設定は不要で、現在の Aspose.Barcode 23.10 リリースで動作します。

## 前提条件

開始する前に、以下を用意してください。

- Python 3.8 以上がインストールされていること  
- 有効な Aspose.Barcode for Python ライセンス（評価用の無料トライアルでも可）  
- 仮想環境で `pip install aspose-barcode` を実行済み  

これらが揃っていれば、インポートエラーなくコードを実行できます。

## Aspose.Barcode（Python）で文字列からバーコードを作成する

まず、目的のシンボロジー（ここでは **Planet** 郵便バーコード）とエンコードしたい文字列で `BarcodeGenerator` をインスタンス化します。

```python
# Step 1: Import the required classes
from asposebarcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat

# Step 2: Create a barcode generator for the Planet symbology with data "123456"
# This is the core of the "create barcode from string" operation.
generator = BarcodeGenerator(EncodeTypes.Planet, "123456")
```

**ポイント:**  
`EncodeTypes.Planet` は Aspose に Planet 郵便シンボロジーを使用させる指示です。第2引数の (`"123456"`) が実際にバーコードにエンコードされる文字列です。この値を変更すれば、任意の郵便番号や追跡番号に対して **文字列からバーコードを作成** できます。

## カスタム寸法でバーコードを生成する方法

郵便バーコードのモジュール幅（X‑ディメンション）は、印刷仕様に合わせて調整する必要があります。Aspose では幅をピクセル単位で指定でき、高さは自動計算されます。

```python
# Step 3: Set the X dimension (module width) in pixels; height is calculated automatically
generator.parameters.barcode.x_dimension.pixels = 4
```

**調整する理由:**  
X‑ディメンションを大きくするとバーが太くなり、低解像度プリンターでも読み取り信頼性が向上します。逆に小さくすればウェブ用に画像サイズを削減できます。この行は **バーコードを生成** して正確なサイズ要件を満たす方法を示しています。

## バーコード画像を保存する

ジェネレータの設定が完了したら、`save` メソッドを呼び出すだけです。メソッドには出力パスと画像形式を指定します。

```python
# Step 4: Save the generated barcode as a PNG image
output_path = "YOUR_DIRECTORY/PostalPlanetAuto.png"
generator.save(output_path, BarCodeImageFormat.PNG)
print(f"Barcode saved to {output_path}")
```

**結果:**  
`PostalPlanetAuto.png` という名前の PNG ファイルが作成され、`"123456"` をエンコードした Planet バーコードが格納されます。任意の画像ビューアで開いて結果を確認できます。

![Screenshot of a generated postal barcode saved as PNG](barcode_example.png){.align-center alt="生成された郵便バーコードの PNG スクリーンショット"}

## 完全なバーコードジェネレータ例

以下は、上記手順をすべて含んだ実行可能なスクリプトです。`generate_postal_barcode.py` という名前で保存し、`python generate_postal_barcode.py` を実行してください。

```python
# generate_postal_barcode.py
# -------------------------------------------------
# Complete example that shows how to create barcode from string,
# set custom dimensions, and save the result as PNG using Aspose.Barcode for Python.
# -------------------------------------------------

from asposebarcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat

def create_postal_barcode(data: str, output_file: str, x_dim_pixels: int = 4):
    """
    Generates a Planet postal barcode from the supplied string.

    Args:
        data: The raw string to encode (e.g., "123456").
        output_file: Full path where the PNG image will be saved.
        x_dim_pixels: Desired X dimension in pixels (default = 4).

    Returns:
        None. The PNG file is written to disk.
    """
    # Validate data length for Planet symbology (6‑digit numeric is standard)
    if not data.isdigit() or len(data) != 6:
        raise ValueError("Planet barcode requires a 6‑digit numeric string.")

    # Create the generator (this is the core of create barcode from string)
    generator = BarcodeGenerator(EncodeTypes.Planet, data)

    # Adjust module width; height is calculated automatically
    generator.parameters.barcode.x_dimension.pixels = x_dim_pixels

    # Save as PNG
    generator.save(output_file, BarCodeImageFormat.PNG)
    print(f"Barcode saved to {output_file}")

if __name__ == "__main__":
    # Example usage – you can change the values to test other strings
    try:
        create_postal_barcode(
            data="123456",
            output_file="PostalPlanetAuto.png",
            x_dim_pixels=4
        )
    except Exception as e:
        print(f"Error generating barcode: {e}")
```

### 期待される出力

スクリプト実行時のコンソール出力は次のとおりです。

```
Barcode saved to PostalPlanetAuto.png
```

…and creates a file `PostalPlanetAuto.png` that looks like this:

![Generated Planet barcode](barcode_example.png){.align-center alt="生成された Planet バーコード（PNG）"}

## よくあるバリエーションとエッジケース

| 状況 | 変更点 | 理由 |
|-----------|----------------|-----|
| **別のシンボロジー**（例: Code128） | `EncodeTypes.Planet` を `EncodeTypes.Code128` に置き換える | 在庫タグなど、郵便コード以外の **バーコードを生成** できるようになる |
| **長いデータ文字列** | 使用するシンボロジーが長さをサポートしているか確認する。Planet の場合は 6 桁に限定 | 実行時の `ValueError` を防止 |
| **高解像度** | `x_dimension.pixels` を 6 または 8 に増やす | 高 DPI 印刷向けにバーを太くできる |
| **他の画像形式** | `BarCodeImageFormat.JPEG` または `BarCodeImageFormat.GIF` を使用 | PNG が適さないワークフローで便利 |
| **Web サービスでの利用** | ファイルシステムへの `save` 呼び出しを `BytesIO` ストリームに置き換えてバイト列を返す | Flask や Django でオンデマンド生成が可能になる |

**プロのヒント:** `BarcodeGenerator` を呼び出す前に必ず入力文字列を検証してください。Planet 用に長さが合わない、数値でない文字が含まれると例外が発生し、アプリケーションがクラッシュします。

## Flask エンドポイントでバーコードを生成する方法（オプション）

**バーコードジェネレータ例** を REST API として公開したい場合は、`create_postal_barcode` 関数をラップします。

```python
from flask import Flask, send_file, request, abort
import io

app = Flask(__name__)

@app.route("/barcode", methods=["GET"])
def barcode_endpoint():
    data = request.args.get("data", "123456")
    try:
        # Generate barcode into an in‑memory stream
        stream = io.BytesIO()
        generator = BarcodeGenerator(EncodeTypes.Planet, data)
        generator.parameters.barcode.x_dimension.pixels = 4
        generator.save(stream, BarCodeImageFormat.PNG)
        stream.seek(0)
        return send_file(stream, mimetype="image/png", as_attachment=False)
    except Exception as exc:
        abort(400, str(exc))

if __name__ == "__main__":
    app.run(debug=True)
```

このスニペットは、ディスクに書き込まずに **オンデマンドでバーコードを生成** する方法を示しており、マイクロサービスに最適です。

## 結論

これで、Python で Aspose.Barcode を使用して **文字列からバーコードを作成** する方法、カスタム寸法で **バーコードを生成** する方法、そして PNG ファイルとして **保存** する方法が分かりました。完全な **バーコードジェネレータ例** には入力検証、エラーハンドリング、再利用可能な関数が含まれており、より大規模なアプリケーションに組み込むことができます。

次は、他のシンボロジー（`EncodeTypes.Code128`、`EncodeTypes.QR`）を試すか、Flask や Django などの Web フレームワークに組み込んでみましょう。これにより **aspose barcode python** ライブラリの理解が深まり、実務プロジェクトで **郵便バーコードを生成** する幅が広がります。

## 次に学ぶべきこと

以下のチュートリアルは、本ガイドで示したテクニックを応用した関連トピックを扱っています。各リソースには完全なコード例とステップバイステップの解説が含まれており、API の追加機能を習得したり、別の実装アプローチを探求したりするのに役立ちます。

- [Python でバーコードを生成する方法 – 完全ステップバイステップガイド](/barcode/english/python-java/general/how-to-generate-barcode-in-python-complete-step-by-step-guid/)
- [Python でバーコード PNG を作成する – 完全 Aspose.Barcode ガイド](/barcode/english/python-java/general/create-barcode-png-in-python-full-aspose-barcode-guide/)
- [Aspose.Barcode Python で ECI を使用してバーコードを生成する方法](/barcode/english/python/general/how-to-generate-barcode-with-eci-using-aspose-barcode-python/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}