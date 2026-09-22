---
category: general
date: 2026-07-18
description: extcodetextbuilder aspose を使用して、プレーン ASCII と UTF‑8 ロシア語テキストを組み合わせた QR
  コードを作成します。Python で Aspose.Barcode の QR コード生成を学びましょう。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- use extcodetextbuilder aspose
- Aspose.Barcode
- ECI encoding
- QR Code generation
- mixed codetext
language: ja
lastmod: 2026-07-18
og_description: extcodetextbuilder（Aspose）を使用すると、QRコード内でプレーンテキストとUTF‑8エンコードされたフラグメントを混在させることができます。Python
  用 Aspose.Barcode のステップバイステップガイドをご覧ください。
og_image_alt: use extcodetextbuilder aspose QR code example showing mixed ECI text
og_title: extcodetextbuilder aspose を使用 – 混合 ECI テキストで QR コードを構築
schemas:
- author: Aspose
  dateModified: '2026-07-18'
  description: use extcodetextbuilder aspose to create QR codes that combine plain
    ASCII and UTF‑8 Russian text. Learn Aspose.Barcode QR Code generation in Python.
  headline: 'use extcodetextbuilder aspose: Generate QR Codes with Mixed ECI Text'
  type: TechArticle
- description: use extcodetextbuilder aspose to create QR codes that combine plain
    ASCII and UTF‑8 Russian text. Learn Aspose.Barcode QR Code generation in Python.
  name: 'use extcodetextbuilder aspose: Generate QR Codes with Mixed ECI Text'
  steps:
  - name: What if my scanner doesn’t recognize the Cyrillic part?
    text: Make sure the scanning app advertises ECI support. Older hardware may ignore
      the ECI segment and treat the bytes as ISO‑8859‑1, resulting in garbled characters.
  - name: Can I add more than two fragments?
    text: Absolutely. Call `add_plain_codetext` or `add_eci_codetext` as many times
      as you need. The builder will concatenate them in the order you invoke the methods.
  - name: How do I change the QR Code size or foreground color?
    text: 'Use the `qr_generator.parameters` object:'
  - name: Is there a way to embed binary data (e.g., a small file) alongside text?
    text: Yes. Use `add_binary_codetext` with a byte array, and pair it with an appropriate
      ECI if the binary represents a specific character set. The builder will handle
      the necessary mode switches.
  type: HowTo
tags:
- barcode
- Aspose
- Python
- QR Code
- ECI
title: 'extcodetextbuilder aspose を使用: 混合 ECI テキストで QR コードを生成'
url: /ja/python/general/use-extcodetextbuilder-aspose-generate-qr-codes-with-mixed-e/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# extcodetextbuilder aspose を使用 – 混合 ECI テキストで QR コードを構築する

単一の QR コードにプレーンな英語とキリル文字の両方を埋め込む方法として **use extcodetextbuilder aspose** を使うことを考えたことはありますか？ あなたは一人ではありません。ASCII と非 ASCII データを混在させる必要があるとき、多くの開発者が壁にぶつかります。特に、対象のスキャナーが適切な ECI（Extended Channel Interpretation）マーカーを期待している場合はなおさらです。

このチュートリアルでは、“HELLO123” **and** ロシア語の単語 “Привет” を含む QR コードを Aspose.Barcode の Python API で作成する正確な手順を解説します。最後まで読むと、すぐに実行できるスクリプトが手に入り、各呼び出しがなぜ重要かが理解でき、他の言語やデータ形式に合わせてプロセスを調整する方法が分かります。

## 学べること

- **initialize ExtCodetextBuilder** とプレーンテキストおよび ECI エンコードされたフラグメントを追加する方法。  
- **ECI encoding** の値 `3` が UTF‑8 に対応している理由と、スキャンに与える影響。  
- Aspose.Barcode を使用して **QR Code generator** を設定する正確な手順。  
- 生成された画像を保存し、混合コンテンツを検証する方法。  

**Prerequisites** – Python 3.8+ と `aspose-barcode` パッケージがインストールされていること（`pip install aspose-barcode`）、そして画像を書き込めるフォルダーが必要です。それ以外は不要です。

---

## extcodetextbuilder aspose を使用して混合 codetext を構築する

最初に必要なのは `ExtCodetextBuilder` のインスタンスです。これは、さまざまなテキスト片を連結し、裏で適切な ECI マーカーを自動的に挿入するビルダーパターンと考えてください。

```python
# Step 1: Build an extended codetext that mixes plain and ECI‑encoded fragments
from aspose.barcode import BarcodeGenerator, Symbology
from aspose.barcode.generation import ExtCodetextBuilder

# Create the builder object
ext_builder = ExtCodetextBuilder()

# Add plain ASCII text – this part needs no special handling
ext_builder.add_plain_codetext("HELLO123")                     # Plain ASCII text

# Add UTF‑8 encoded Russian text – ECI value 3 signals UTF‑8 to the scanner
ext_builder.add_eci_codetext(eci_encoding=3, codetext="Привет")  # UTF‑8 encoded Russian text

# Retrieve the combined string that Aspose.Barcode will consume
extended_codetext = ext_builder.get_extended_codetext()
```

**Why this matters:**  
- `add_plain_codetext` はデータをそのまま保持し、数字や英字に最適です。  
- `add_eci_codetext` は提供された文字列の前に ECI セグメント（`[ECI:3]`）を挿入し、以降のバイトが UTF‑8 であることを準拠リーダーに伝えます。これがないと、スキャナーはキリル文字のバイトをゴミとして解釈します。

> **Pro tip:** 別の文字セットが必要な場合は、ECI テーブルに従って `eci_encoding` の値を変更してください（例: ISO‑8859‑1 の場合は `26`）。

---

## Aspose.Barcode で QR コード生成を初期化する

適切にフォーマットされた `extended_codetext` が用意できたので、QR コードジェネレータに渡すことができます。Aspose.Barcode は低レベルの QR 行列生成を抽象化し、データに集中できるようにします。

```python
# Step 2: Initialise a QR Code generator
qr_generator = BarcodeGenerator()
qr_generator.set_symbology(Symbology.QR)   # Choose QR as the symbology
```

**What’s happening here?**  
- `BarcodeGenerator()` はデフォルト設定（サイズ、解像度など）で新しいジェネレータオブジェクトを作成します。  
- `set_symbology` はエンジンに QR コードを使用したいことを指示します（例: Code128 ではなく）。  

より高いエラー訂正レベルが必要な場合は、codetext を設定する前に `qr_generator.parameters.barcode.qr_error_level = ...` を呼び出すことができます。

---

## 拡張 codetext を QR ジェネレータに割り当てる

ジェネレータの準備ができたら、次のステップは先ほど構築した混合文字列を渡すだけです。

```python
# Step 3: Assign the extended codetext to the generator
qr_generator.set_extended_codetext(extended_codetext)
```

**Why not use `set_codetext`?**  
`set_codetext` は入力をプレーンテキストとして扱い、ECI マーカーを除去します。`set_extended_codetext` は生バイトを保持し、ECI セグメントを含めることで、スキャナーが正しい言語切替を認識できるようにします。

---

## QR コード画像を保存し、結果を検証する

最後に、QR コードをディスクに書き込みます。Aspose.Barcode は PNG、JPEG、BMP などをサポートしており、PNG はロスレスデータを保持できる安全なデフォルトです。

```python
# Step 4: Save the generated QR Code image
qr_generator.save("YOUR_DIRECTORY/qr_extended.png")
```

指定した場所に PNG ファイルが作成されているはずです。ECI に対応した任意の QR スキャナーアプリ（ほとんどの最新スマートフォンが対応）で開いてください。1 回スキャンすると “HELLO123” が表示されます。再度スキャンするか、生データを表示するスキャナーを使用すると “Привет” も取得できます。これら二つの部分は単一のペイロードとして現れ、私たちが構築した通りです。

![extcodetextbuilder aspose QR コード例](YOUR_DIRECTORY/qr_extended.png)

*画像の代替テキスト: 混合 ECI テキストを示す extcodetextbuilder aspose QR コード例*

---

## 完全な、すぐに実行できるスクリプト

すべてをまとめると、`qr_mixed_eci.py` という名前のファイルにコピー＆ペーストできる完全なプログラムは以下の通りです：

```python
from aspose.barcode import BarcodeGenerator, Symbology
from aspose.barcode.generation import ExtCodetextBuilder

def generate_mixed_eci_qr(output_path: str):
    # Build mixed codetext
    ext_builder = ExtCodetextBuilder()
    ext_builder.add_plain_codetext("HELLO123")
    ext_builder.add_eci_codetext(eci_encoding=3, codetext="Привет")
    extended_codetext = ext_builder.get_extended_codetext()

    # Initialise QR generator
    qr_generator = BarcodeGenerator()
    qr_generator.set_symbology(Symbology.QR)

    # Assign extended codetext
    qr_generator.set_extended_codetext(extended_codetext)

    # Save image
    qr_generator.save(output_path)
    print(f"QR Code saved to {output_path}")

if __name__ == "__main__":
    generate_mixed_eci_qr("qr_extended.png")
```

以下のコマンドで実行します：

```bash
python qr_mixed_eci.py
```

コンソールに保存場所を示すメッセージが表示され、PNG が指定した場所に作成されます。

---

## よくある質問とエッジケース

### スキャナーがキリル文字部分を認識しない場合は？

スキャンアプリが ECI 対応を明示していることを確認してください。古いハードウェアは ECI セグメントを無視し、バイトを ISO‑8859‑1 として扱うため、文字化けが発生します。

### 2 つ以上のフラグメントを追加できますか？

もちろん可能です。必要な回数だけ `add_plain_codetext` または `add_eci_codetext` を呼び出してください。ビルダーは呼び出し順にフラグメントを連結します。

### QR コードのサイズや前景色を変更するには？

`qr_generator.parameters` オブジェクトを使用します：

```python
qr_generator.parameters.barcode.x_dimension = 4   # module size in points
qr_generator.parameters.barcode.qr_error_level = qr_generator.parameters.barcode.QrErrorLevel.QR_ECLEVEL_Q
qr_generator.save("qr_custom.png", BarCodeImageFormat.PNG, 300)  # 300 DPI
```

### テキストと一緒にバイナリデータ（例: 小さなファイル）を埋め込む方法はありますか？

はい。バイト配列とともに `add_binary_codetext` を使用し、バイナリが特定の文字セットを表す場合は適切な ECI と組み合わせます。ビルダーは必要なモード切替を処理します。

---

## 結論

これで **extcodetextbuilder aspose の使い方** をマスターし、プレーンな ASCII と UTF‑8 エンコードされたロシア語テキストをシームレスに組み合わせた QR コードを作成できるようになりました。`ExtCodetextBuilder` を活用し、正しい **ECI encoding** を設定し、結果を **Aspose.Barcode QR Code generator** に渡すことで、標準準拠の単一画像が得られ、最新のスキャナーで動作します。

ここからは、`eci_encoding=3` を他の言語識別子に置き換えたり、追加のプレーンフラグメントで多言語ペイロードを構築したりしてみてください。また、ベクター画像が必要な場合は `BarCodeImageFormat` オプションを使って SVG や PDF を出力することも検討できます。

コーディングを楽しんでください。問題があれば遠慮なくコメントを残してください—皆さんのフィードバックがこのガイドをさらに良くします！

## 次に学ぶべきことは？

以下のチュートリアルは、本ガイドで示した手法を応用した密接に関連するトピックを扱っています。各リソースには、ステップバイステップの解説と完全な動作コード例が含まれており、追加の API 機能を習得し、独自プロジェクトで代替実装アプローチを探求するのに役立ちます。

- [Java でバーコード生成 - Aspose.BarCode を使用したコードテキストの設定](/barcode/english/java/text-and-styling/setting-code-text/)
- [.NET でバーコード作成 - DataMatrix コードテキストの設定](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-extended-code-text-configuration/)
- [.NET 用 Aspose.BarCode の Aztec コードテキストエンコーディング](/barcode/english/net/aztec-barcode-encoding/aztec-code-text-encoding/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}