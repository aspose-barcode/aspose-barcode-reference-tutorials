---
category: general
date: 2026-07-15
description: Aspose.Barcode を使用して Python で QR コード画像を生成する方法。拡張コードテキスト、ECI エンコーディング、Unicode
  対応のステップバイステップ QR コード作成を学びましょう。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to generate qr code image
- Aspose.Barcode QR
- Python barcode generation
- extended codetext builder
- ECI encoding in QR
- QR code with Unicode
language: ja
lastmod: 2026-07-15
og_description: Aspose.Barcode を使用して Python で QR コード画像を生成する方法。このガイドでは、拡張コードテキスト、ECI
  エンコーディング、Unicode 文字を使用した QR コードの作成手順を説明します。
og_image_alt: Python script generating a QR code image with extended codetext via
  Aspose.Barcode
og_title: PythonでQRコード画像を生成する方法 – Aspose.Barcode 完全チュートリアル
schemas:
- author: Aspose
  dateModified: '2026-07-15'
  description: How to generate QR code image in Python using Aspose.Barcode. Learn
    step‑by‑step QR code creation with extended codetext, ECI encoding, and Unicode
    support.
  headline: How to Generate QR Code Image in Python with Aspose.Barcode – Full Guide
  type: TechArticle
- description: How to generate QR code image in Python using Aspose.Barcode. Learn
    step‑by‑step QR code creation with extended codetext, ECI encoding, and Unicode
    support.
  name: How to Generate QR Code Image in Python with Aspose.Barcode – Full Guide
  steps:
  - name: 1. *What if I need more than two segments?*
    text: Simply call `add_plain_codetext` or `add_eci_codetext` as many times as
      you like. The builder maintains the correct ordering, so the QR code will contain
      each segment in the sequence you add them.
  - name: 2. *Can I embed emojis?*
    text: "Yes—emojis are just Unicode characters. Use the UTF‑8 ECI (value 26) and
      pass the emoji string, e.g., `builder.add_eci_codetext(26, \"\U0001F680\")`.
      The QR will display the rocket emoji on supporting scanners."
  - name: 3. *What if the QR becomes too dense?*
    text: 'QR codes have version limits. If you exceed the data capacity, Aspose will
      automatically bump the version up to the next size, but the image might become
      larger. To control size, you can lower the error correction level:'
  - name: 4. *Do I need to worry about character sets other than UTF‑8?*
    text: Only if you have legacy systems that require a specific encoding (e.g.,
      ISO‑8859‑1). In that case, replace `26` with the appropriate ECI value (see
      Aspose’s ECI table). For most modern apps, UTF‑8 is the safest bet.
  - name: 5. *How do I add a logo in the center?*
    text: 'Aspose.Barcode supports `barcode.generator.QRCodeParameters.logo_image`.
      Load an image with Pillow (`from PIL import Image`) and assign it:'
  type: HowTo
tags:
- QR code
- Python
- Aspose
title: Aspose.Barcode を使用した Python での QR コード画像生成方法 – 完全ガイド
url: /ja/python/general/how-to-generate-qr-code-image-in-python-with-aspose-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Python で Aspose.Barcode を使用して QR コード画像を生成する方法 – 完全ガイド

何十ものライブラリを探さずに **Python で QR コード画像を生成する方法** を知りたくありませんか？ あなたは一人ではありません。多くの開発者が、ロシア語、アラビア語、絵文字などの多言語テキストを QR コードに埋め込む信頼できる方法を必要としており、標準ライブラリだけでは足りないことが多いです。

実は、Aspose.Barcode for Python を使えば驚くほど簡単に実現できます。このチュートリアルでは、パッケージのインストールから、プレーン ASCII と ECI エンコードされた Unicode を混在させた拡張コードテキスト文字列の作成まで、正確な手順を順に解説します。最後には、ディスク上に保存された使用可能な QR コード画像が手に入ります。

## 本ガイドでカバーする内容

- Python 用 **Aspose.Barcode** のインストール（Python 3.8+ 対応）
- プレーンと Unicode セグメントを組み合わせた **拡張コードテキスト** の構築
- ロシア語文字を正しく表示するための **ECI エンコード** の使用
- QR コード生成のための `BarcodeGenerator` の設定
- PNG 形式での出力画像の保存
- ヒント、よくある落とし穴、次のステップのアイデア（ロゴの追加や誤り訂正レベルの調整など）

Aspose の事前知識は不要です。基本的な Python 環境と QR コードへの興味さえあれば始められます。

---

## 前提条件

作業を始める前に、以下を確認してください。

1. **Python 3.8 以上** がマシンにインストールされていること。  
2. **仮想環境**（任意だが推奨）を使用して依存関係を整理できること。  
3. `aspose-barcode` パッケージをインストールできる **pip** のアクセス権があること。  
4. 生成した PNG を保存するフォルダーへの書き込み権限があること。

これらに心当たりがない場合は、ここで一度設定を済ませてください。準備が整えば、後は簡単です。

---

## 手順 1: Aspose.Barcode for Python をインストール

最初のハードルはライブラリの取得です。Aspose は PyPI にパッケージを配布しているので、`pip` コマンド一つで完了します。

```bash
pip install aspose-barcode
```

> **プロのコツ:** 仮想環境内で実行すれば、グローバルの site‑packages を汚さずに済みます。権限エラーが出た場合は `--user` を付けるか、`sudo` で実行してください（ただし、最新の環境ではほとんど必要ありません）。

インストールが完了したら、以下で確認できます。

```python
import aspose.barcode as barcode
print(barcode.__version__)   # Should print something like 23.12.0
```

バージョンが問題なく表示されれば、準備完了です。

---

## 手順 2: **拡張コードテキスト ビルダー** インスタンスを作成

Aspose.Barcode には、複雑な QR ペイロードを組み立てるための `ExtCodetextBuilder` クラスが用意されています。各セグメントに適切な制御文字を自動で付加してくれる、ミニテキストエディタのようなものです。

```python
# Step 2: Initialise the builder
builder = barcode.generation.ExtCodetextBuilder()
```

ビルダーを使う理由は何ですか？ 生のバイト列を手作業で連結するとミスが起きやすいですが、ビルダーは正しい ECI（拡張チャネル解釈）スイッチを保証するので、スキャナがすべての言語を正しくデコードできます。

---

## 手順 3: 新規作成（任意だがクリーンに）

同じビルダーインスタンスを再利用する場合は、`clear()` を呼び出すことで以前のデータをすべて消去できます。これにより、前回のセグメントが次の QR に混入するのを防げます。

```python
# Step 3: Ensure the builder is empty
builder.clear()
```

最初の実行時にこの行を省いても構いませんが、関数内で繰り返し呼び出す場合は冪等性を保つために残しておくと便利です。

---

## 手順 4: プレーン（エンコードなし）セグメントを追加

多くの QR コードはシンプルな ASCII 文字列から始まります。たとえば識別子や URL です。`add_plain_codetext` メソッドは、ECI マーカーを付けずにその文字列を追加します。

```python
# Step 4: Add plain ASCII text
builder.add_plain_codetext("HelloWorld")
```

この例ではプレースホルダーとして `"HelloWorld"` を使用しています。必要に応じて製品 SKU や短いメッセージに置き換えてください。

---

## 手順 5: **ECI エンコード** セグメントを追加（UTF‑8 = 26）

ここから多言語対応です。ECI 値 **26** は UTF‑8 に対応しており、Unicode の事実上の標準です。`26` とロシア語フレーズを渡すことで、QR スキャナに UTF‑8 に切り替えてから文字を読むよう指示します。

```python
# Step 5: Append a Russian phrase using UTF‑8 ECI (value 26)
builder.add_eci_codetext(26, "Привет")   # "Privet" means "Hello" in Russian
```

別のエンコードが必要な場合は、たとえば ISO‑8859‑1 用に `27` など、他の ECI 値に置き換えてください。ビルダーが自動で適切な制御文字を挿入します。

---

## 手順 6: 結合された拡張コードテキストを取得

すべてのセグメントを追加したら、QR ジェネレータが使用する最終文字列を取得します。この文字列には目に見えない制御シーケンスが含まれますが、デバッグ用に出力は可能です。

```python
# Step 6: Get the full extended codetext
extended_codetext = builder.get_extended_codetext()
print("Extended codetext:", extended_codetext)
```

コンソールには文字化けしたように見えるはずです（制御バイトが埋め込まれているため）。重要なのは、ビルダーがプレーン部分と Unicode 部分を正しくつなげていることです。

---

## 手順 7: バーコードジェネレータを設定

拡張コードテキストを Aspose の `BarcodeGenerator` に渡します。シンボロジーを `QR` に設定し、結合文字列を `code_text` に割り当てます。

```python
# Step 7: Initialise the QR code generator
generator = barcode.generation.BarcodeGenerator()
generator.symbology = barcode.Symbology.QR          # Choose QR symbology
generator.code_text = extended_codetext           # Use the extended codetext
```

ここで `resolution`、`error_correction_level`、`foreground_color` などの追加プロパティも調整できます。基本的な画像生成ではデフォルトで十分です。

---

## 手順 8: 生成した QR コード画像を保存

最後に QR コードをディスクに書き出します。`save` メソッドはファイルパスとオプションのフォーマットを受け取り、PNG が安全なデフォルトです。

```python
# Step 8: Persist the QR code as a PNG file
output_path = "qr_extended.png"   # Adjust path as needed
generator.save(output_path)
print(f"QR code saved to {output_path}")
```

生成された `qr_extended.png` を任意の画像ビューアで開き、スマートフォンでスキャンすると、2 つのメッセージ「HelloWorld」と「Привет」が表示されます。ほとんどの最新 QR リーダーは自動で ECI スイッチを処理します。

---

## 完全動作サンプル

以下に、コピー＆ペーストしてそのまま実行できる完全なスクリプトを示します。

```python
import aspose.barcode as barcode

# Initialise the extended codetext builder
builder = barcode.generation.ExtCodetextBuilder()
builder.clear()                                   # Ensure a clean start
builder.add_plain_codetext("HelloWorld")          # Plain ASCII segment
builder.add_eci_codetext(26, "Привет")            # Russian UTF‑8 segment
extended_codetext = builder.get_extended_codetext()
print("Extended codetext:", extended_codetext)

# Configure the QR generator
generator = barcode.generation.BarcodeGenerator()
generator.symbology = barcode.Symbology.QR
generator.code_text = extended_codetext

# Save the image
output_file = "qr_extended.png"
generator.save(output_file)
print(f"QR code image saved as {output_file}")
```

**期待されるコンソール出力**:

```
Extended codetext: <binary data>   # appears garbled due to ECI markers
QR code image saved as qr_extended.png
```

`qr_extended.png` を開き → スキャン → 「HelloWorld」に続いて「Привет」が表示されます。

---

## よくある質問とエッジケース

### 1. *セグメントが 2 つ以上必要な場合は？*  
`add_plain_codetext` または `add_eci_codetext` を好きなだけ呼び出せば OK です。ビルダーは順序を正しく保持するので、追加した順に QR に埋め込まれます。

### 2. *絵文字を埋め込めますか？*  
可能です。絵文字も Unicode 文字です。UTF‑8 ECI（値 26）を使い、たとえば `builder.add_eci_codetext(26, "🚀")` とすれば、対応スキャナでロケット絵文字が表示されます。

### 3. *QR が密すぎる場合は？*  
QR にはバージョン上限があります。データ容量を超えると Aspose が自動で次のバージョンに拡大しますが、画像が大きくなることがあります。サイズを抑えたい場合は誤り訂正レベルを下げてみてください。

```python
generator.parameters.qr.error_correction_level = barcode.QRErrorCorrectionLevel.L
```

### 4. *UTF‑8 以外の文字セットは必要ですか？*  
レガシーシステムで特定のエンコードが要求される場合を除き、ほとんどの現代アプリでは UTF‑8 が最適です。その場合は適切な ECI 値に置き換えてください（Aspose の ECI テーブル参照）。

### 5. *中央にロゴを入れるには？*  
Aspose.Barcode は `barcode.generator.QRCodeParameters.logo_image` をサポートしています。Pillow で画像を読み込み、次のように設定します。

```python
from PIL import Image
logo = Image.open("logo.png")
generator.parameters.qr.logo_image = logo
```

ロゴは自動で静寂領域（quiet zone）を調整し、スキャン可能性を保ちます。

---

## 本番環境でのプロ向けヒント

- 同じ QR を頻繁に生成する場合は **ビルダーをキャッシュ** して、毎回文字列を再構築しないようにしましょう。  
- `zxing` や `pyzbar` を使ったユニットテストで出力をデコードし、ECI スイッチが正しいか検証してください。  
- ペイロードのハッシュをファイル名に含めるなど、**決定的なファイル名**を設定して上書きを防止します。  
- **ライセンスに注意**: Aspose.Barcode は商用ソフトウェアです。開発段階は無料評価版で動作しますが、本番デプロイにはライセンスが必要です。

---

## 次のステップ & 関連トピック

今や **QR コードの生成方法** をマスターしたので、以下のチュートリアルでさらにスキルを広げましょう。各リソースは完全なコード例とステップバイステップの解説が付属しています。

- [How to Generate Barcode Image in Java with Aspose.BarCode](/barcode/english/java/barcode-rendering-techniques/)
- [How to generate Aztec barcode with custom aspect ratio using Aspose.BarCode for .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)
- [How to create dotcode extended codetext with Aspose.BarCode for .NET](/barcode/english/net/dotcode-barcode-configuration/dotcode-extended-code-text-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}