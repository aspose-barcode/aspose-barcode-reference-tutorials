---
category: general
date: 2026-11-20
description: Pythonのバーコードライブラリを使用して、ECIの使い方、テキストからQRコードを生成する方法、ビルダーのクリア、QR画像の保存方法を学びましょう。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to use eci
- generate qr from text
- how to clear builder
- save qr image
- clear qr builder
language: ja
lastmod: 2026-11-20
og_description: ECI を使ってテキストから QR コードを生成し、QR ビルダーをクリアし、QR 画像を保存する方法 – 完全なステップバイステップガイド。
og_image_alt: Diagram illustrating how to use ECI to generate a QR code and save the
  QR image
og_title: PythonでQRコード生成にECIを使用する方法
schemas:
- author: Aspose
  dateModified: '2026-11-20'
  description: Learn how to use ECI, generate QR from text, clear the builder, and
    save QR image using the Python barcode library.
  headline: How to use ECI in QR code generation with Python
  type: TechArticle
tags:
- QR code
- Python
- barcode
- ECI
title: PythonでQRコード生成にECIを使用する方法
url: /ja/python/general/how-to-use-eci-in-qr-code-generation-with-python/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# PythonでQRコード生成にECIを使用する方法

QRコードを作成する際に **how to use eci** が必要な場合、このガイドでは正確な手順を示します。テキストからQRを生成し、ビルダーをクリアし、最終的にQR画像を保存する方法を、Python数行で確認できます。

QRコードに多言語データを含める場合、スキャナーが適用すべき文字セットを認識できるように、拡張チャネル解釈（ECI）セグメントが必要になることがあります。このチュートリアルでは、拡張コードテキストの構築、再利用時のビルダーのクリア、そして結果をPNGファイルとして保存する手順を解説します。

## 前提条件

開始する前に、以下が揃っていることを確認してください。

- Python 3.8+ がインストールされていること。
- Aspose.BarCode for Python via .NET パッケージ（または `ExtCodetextBuilder` と `BarcodeGenerator` を提供する互換性のある `barcode` ライブラリ）。
- QRコードの基本概念に慣れていること。

pipでライブラリをインストールします:

```bash
pip install aspose-barcode
```

> **Pro tip:** バージョン競合を避けるために仮想環境を使用してください。

## ステップ 1: 必要なクラスをインポートする

主に使用するクラスは、拡張コードテキストを構築するための `ExtCodetextBuilder` と、QRコードを描画するための `BarcodeGenerator` です。

```python
from aspose.barcode import barcode
from aspose.barcode.generation import ExtCodetextBuilder
```

これらのインポートにより、ビルダーのメソッド（`add_plain_codetext`, `add_eci_codetext` など）や、ジェネレーターの `set_code_text`, `set_symbology`, `save` 関数にアクセスできます。

## ステップ 2: ExtCodetextBuilder を作成し設定する

新しいビルダーインスタンスを作成することは、 **how to use eci** の最初の具体例です。必要に応じて後でビルダーをクリアして再利用することもできます。

```python
# Create an ExtCodetextBuilder instance
extended_text_builder = ExtCodetextBuilder()

# Optional: clear any previous items (useful when reusing the same builder)
extended_text_builder.clear()   # this demonstrates how to clear builder
```

`clear()` を呼び出すことで、ビルダーがクリーンな状態から開始されるため、ループ内で複数のQRコードを生成する際に重要です。

## ステップ 3: プレーン（非ECI）コードテキストを追加する

プレーンテキストはECIセグメントを必要としません。ASCII互換の文字列には `add_plain_codetext` を使用します。

```python
# Add plain codetext (e.g., an English phrase)
extended_text_builder.add_plain_codetext("HelloWorld")
```

ビルダーにはプレーンセグメント `"HelloWorld"` が保持されます。

## ステップ 4: ECIエンコードされたセグメントを追加する

ここが **how to use eci** の核心です。ECI値（UTF‑8 の場合は 26）を指定し、エンコードしたいUnicode文字列を提供します。これにより、デフォルトの ISO‑8859‑1 ではカバーされないロシア語や中国語などの言語をQRコードに含めることができます。

```python
# Add ECI‑encoded codetext (ECI value 26 = UTF‑8, Russian “Hello”)
extended_text_builder.add_eci_codetext(26, "Привет")
```

> **Why this matters:** ECIインジケータがないと、スキャナーはデフォルト文字セットでバイトを解釈し、非ASCIIテキストは文字化けして表示されます。

## ステップ 5: 結合された拡張コードテキスト文字列を取得する

必要なすべてのセグメントを追加したら、QRジェネレーターに渡す最終文字列を取得します。

```python
combined_extended_text = extended_text_builder.get_extended_codetext()
print("Extended codetext:", combined_extended_text)
```

出力例は次のようになります:

```
Extended codetext: [ECI26]ПриветHelloWorld
```

正確な形式はライブラリによりますが、重要なのは ECIマーカー（`[ECI26]`）が UTF‑8 ペイロードの前に付くことです。

## ステップ 6: 結合テキストを使用してQRコードを生成する

拡張コードテキストを `BarcodeGenerator` に渡すことで、 **generate QR from text** が実行できます。

```python
# Initialize the QR generator
qr_generator = barcode.generation.BarcodeGenerator()

# Assign the combined extended codetext
qr_generator.set_code_text(combined_extended_text)

# Choose QR symbology (the library supports many, QR is the most common)
qr_generator.set_symbology(barcode.Symbology.QR)

# Save the QR image to disk – this demonstrates how to save QR image
output_path = "qr_extended.png"
qr_generator.save(output_path)

print(f"QR code saved to {output_path}")
```

`qr_extended.png` を開くと、プレーンな英語文字列とロシア語の挨拶の両方をエンコードしたQRコードが表示されます。最新のQRスキャナーで読み取ると、正しく “HelloWorld” と “Привет” が表示されます。

### ビルダーを再利用する前に `clear()` を呼び出すべき理由

ループ内で複数のQRコードを生成する場合、ビルダーをクリアし忘れると古いセグメントが新しいものと連結され、無効なコードになります。簡単なパターンは次の通りです:

```python
for text, eci, unicode_str in data_set:
    extended_text_builder.clear()                       # ensures a fresh start
    extended_text_builder.add_plain_codetext(text)
    extended_text_builder.add_eci_codetext(eci, unicode_str)
    qr_generator.set_code_text(extended_text_builder.get_extended_codetext())
    qr_generator.save(f"qr_{text}.png")
```

このスニペットは **how to clear builder** と **how to generate QR from text** を繰り返し実行する方法を示しています。

## エッジケースと一般的な落とし穴

| 状況 | 注意点 | 対処方法 |
|-----------|-------------------|---------------|
| **サポートされていないECI値** | ライブラリが `InvalidArgumentException` をスローします。 | 仕様に記載されたECI値のみを使用してください（例: UTF‑8 は 26、Shift‑JIS は 20）。 |
| **結合テキストが非常に長い** | QRバージョンが最大容量を超える可能性があります。 | QRバージョンを自動的に上げる（`qr_generator.set_qr_version(QRVersion.AUTO)`）か、データを複数のQRコードに分割してください。 |
| **ファイルシステムの権限エラー** | `save` が `IOError` で失敗します。 | 対象ディレクトリが存在し、書き込み権限があることを確認してください。 |
| **文字セット表示が正しくない** | スキャナーが文字化けした文字を表示します。 | 正しいECI値が文字列の実際のエンコーディングと一致しているか確認してください。 |

## 完全に実行可能な例

以下はコピー＆ペーストで実行できる自己完結型スクリプトです。すべてのインポート、エラーハンドリング、コメントが含まれています。

```python
# qr_eci_example.py
# Demonstrates how to use ECI, generate QR from text, clear the builder,
# and save QR image using Aspose.BarCode for Python.

from aspose.barcode import barcode
from aspose.barcode.generation import ExtCodetextBuilder
import os

def generate_qr(plain_text: str, eci_value: int, unicode_text: str, out_file: str):
    """
    Creates a QR code that contains both plain and ECI‑encoded text.
    Parameters:
        plain_text – ASCII‑compatible string.
        eci_value  – Numeric ECI identifier (e.g., 26 for UTF‑8).
        unicode_text – Text that requires the specified ECI.
        out_file – Destination file path for the PNG image.
    """
    # Step 1: instantiate and clear the builder
    builder = ExtCodetextBuilder()
    builder.clear()                       # how to clear builder

    # Step 2: add segments
    builder.add_plain_codetext(plain_text)
    builder.add_eci_codetext(eci_value, unicode_text)

    # Step 3: retrieve combined text
    combined = builder.get_extended_codetext()
    print("Combined extended codetext:", combined)

    # Step 4: generate QR code
    generator = barcode.generation.BarcodeGenerator()
    generator.set_code_text(combined)
    generator.set_symbology(barcode.Symbology.QR)

    # Ensure output directory exists
    os.makedirs(os.path.dirname(out_file), exist_ok=True)

    # Step 5: save QR image – how to save QR image
    generator.save(out_file)
    print(f"QR code saved as {out_file}")

if __name__ == "__main__":
    # Example usage
    generate_qr(
        plain_text="HelloWorld",
        eci_value=26,               # UTF‑8
        unicode_text="Привет",      # Russian "Hello"
        out_file="output/qr_extended.png"
    )
```

このスクリプトを実行すると `output/qr_extended.png` が生成され、英語とロシア語のテキストが正しくエンコードされたQRコードが得られます。

## 結論

これで **how to use eci** を用いたQRコードの構築方法、再利用前に **clear the QR builder** する方法、 **generate QR from text** の手順、そして Python で **save QR image** する正確な手順が分かりました。上記パターンに従えば、ビルダーの状態を予測可能に保ちつつ、任意のUnicode文字列をQRコードに埋め込むことができます。

### 次にやることは？

- 中国語（ECI 20）や ISO‑8859‑5 など、他の言語向けのECI値を調査する。
- エラー訂正レベル（`qr_generator.set_error_correction_level`）を調整してスキャン信頼性を向上させる。
- 単一のQRに複数のECIセグメントを組み合わせて、混在言語メッセージを実現する。

Happy coding, and enjoy creating multilingual QR codes!

## 次に学ぶべきことは？

以下のチュートリアルは、本ガイドで示したテクニックを基にした、密接に関連するトピックをカバーしています。各リソースには、完全な動作コード例とステップバイステップの解説が含まれており、追加の API 機能を習得し、独自プロジェクトで代替実装アプローチを探求するのに役立ちます。

- [Aspose.Barcode PythonでECIを使用してバーコードを生成する方法](/barcode/english/python/general/how-to-generate-barcode-with-eci-using-aspose-barcode-python/)
- [Aspose.Barcodeを使用したPythonでのQRコード画像生成 – 完全ガイド](/barcode/english/python/general/how-to-generate-qr-code-image-in-python-with-aspose-barcode/)
- [Pythonでバーコードを生成する方法 – 完全ステップバイステップガイド](/barcode/english/python-java/general/how-to-generate-barcode-in-python-complete-step-by-step-guid/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}