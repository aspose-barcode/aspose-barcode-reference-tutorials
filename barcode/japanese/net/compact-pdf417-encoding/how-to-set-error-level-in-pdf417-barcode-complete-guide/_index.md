---
category: general
date: 2026-07-18
description: Aspose.BarCode を使用して PDF417 バーコードのエラーレベルを設定する方法。カスタムテキストで PDF417 バーコードを生成し、数分でエラー訂正を調整する方法を学びましょう。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to set error
- generate pdf417 barcode
- how to generate pdf417
- barcode with custom text
language: ja
lastmod: 2026-07-18
og_description: PDF417バーコードのエラーレベルをすばやく設定する方法。このチュートリアルでは、カスタムテキストと異なるエラー訂正レベルを使用してPDF417バーコードを生成する手順を解説します。
og_image_alt: how to set error level in PDF417 barcode example
og_title: PDF417バーコードのエラーレベル設定方法 – ステップバイステップガイド
schemas:
- author: Aspose
  dateModified: '2026-07-18'
  description: how to set error level in PDF417 barcode using Aspose.BarCode. Learn
    to generate PDF417 barcode with custom text and tweak error correction in minutes.
  headline: How to Set Error Level in PDF417 Barcode – Complete Guide
  type: TechArticle
- description: how to set error level in PDF417 barcode using Aspose.BarCode. Learn
    to generate PDF417 barcode with custom text and tweak error correction in minutes.
  name: How to Set Error Level in PDF417 Barcode – Complete Guide
  steps:
  - name: What if my text contains line breaks?
    text: 'PDF417 automatically encodes line‑feed (`

      `) characters. Just include them in the string:'
  - name: Can I use a different image format?
    text: Absolutely. Replace `BarCodeImageFormat.Png` with `Jpeg`, `Bmp`, or `Svg`
      depending on your downstream workflow.
  - name: Does changing the X‑dimension affect error correction?
    text: Indirectly, yes. A larger X‑dimension yields bigger modules, which can improve
      scanning reliability but does **not** alter the logical error‑correction level.
      Adjust both parameters independently for best results.
  - name: How to generate PDF417 barcode in a web API?
    text: Wrap the same code in an ASP.NET Core controller and stream the PNG back
      as a `FileResult`. The core logic stays unchanged, which means **how to generate
      PDF417** remains consistent across desktop and web environments.
  type: HowTo
tags:
- PDF417
- barcode
- error correction
title: PDF417バーコードのエラーレベル設定方法 – 完全ガイド
url: /ja/net/compact-pdf417-encoding/how-to-set-error-level-in-pdf417-barcode-complete-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# PDF417 バーコードのエラーレベル設定方法 – 完全ガイド

PDF417 バーコードを生成するときに **エラーを設定する方法** を知りたくありませんか？ 同じ悩みを抱える開発者は多く、過酷な環境でのスキャンに耐えるバーコードが必要になることがあります。 良いニュースは、Aspose.BarCode を使えばエラ―補正レベルの調整はとても簡単で、**PDF417 を生成する方法** も同時に学べます。

このチュートリアルでは、特殊文字を含むバーコードジェネレータの作成から、異なるエラ―補正レベルを示す 2 つの PNG ファイルの保存まで、すべての手順を解説します。 最後まで読めば、**PDF417 バーコードの生成**、X‑ディメンションや列数の調整、そして最も重要な **エラー設定** が自在にできるようになります。

## 前提条件

- .NET 6.0 以降（.NET Framework でも動作します）
- Aspose.BarCode for .NET がインストール済み（NuGet で `Install-Package Aspose.BarCode`）
- 画像を書き込めるフォルダー（サンプル中の `YOUR_DIRECTORY/` を実際のパスに置き換えてください）
- 基本的な C# の知識 – `Console.WriteLine` が書ければ問題ありません

> **プロのコツ:** モバイルスキャンを対象とする場合は、汚れや傷、低照度環境に耐えるために高いエラーレベル（Level 5）を選択しましょう。

## 手順 1: カスタムテキストでバーコードジェネレータを作成

まずは **PDF417 バーコード** を生成することを Aspose に伝え、エンコードしたいテキストを渡す `BarcodeGenerator` インスタンスを作ります。 アクセント付き文字や著作権記号を使用しているので、Unicode がそのまま扱えることが確認できます。

```csharp
using Aspose.BarCode.Generation;

// Step 1: Create a PDF417 barcode generator with the desired text
BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Åspóse.Barcóde©");
```

*ポイント:* `EncodeTypes.Pdf417` フラグが 2‑D スタック型バーコードであることを Aspose に指示し、文字列引数がデータペイロードになります。このステップを省くと、デフォルトの Code128 バーコードが生成されてしまいます。

## 手順 2: ビジュアルパラメータを微調整

PDF417 バーコードはデータだけでなく視覚的パターンでもあります。 **X‑ディメンション**（最小バー幅）と **列数** を調整することで、バーコードの実際のサイズと読み取りやすさをコントロールできます。

```csharp
// Step 2: Adjust visual parameters – set the X‑dimension and number of columns
generator.Parameters.Barcode.XDimension.Pixels = 2;   // each module is 2 pixels wide
generator.Parameters.Barcode.Pdf417.Columns = 3;    // three columns across the page
```

*ポイント:* X‑ディメンションを小さくすると画像はコンパクトになりますが、低解像度スキャナでは読めなくなる可能性があります。 3 列は多くのラベルサイズでバランスの取れたアスペクト比を提供します。

## 手順 3: エラ―補正レベルを 2 に設定して保存

エラ―補正は **PDF417 のエラー設定方法** の核心です。 `Pdf417ErrorLevel` 列挙体は `Level0`（余分なデータなし）から `Level5`（最大冗長性）まであります。 ここでは **Level 2** を使用し、画像サイズを大きくしすぎずに適度なエラ―耐性を追加します。

```csharp
// Define the output folder (replace with your actual path)
string outputFolder = "YOUR_DIRECTORY/";

// Step 3: Set error correction level to 2 and save the image
generator.Parameters.Barcode.Pdf417.ErrorLevel = Pdf417ErrorLevel.Level2;
generator.Save($"{outputFolder}Pdf417ErrorLevel2.png", BarCodeImageFormat.Png);
```

このスニペットを実行すると、フォルダーに `Pdf417ErrorLevel2.png` が作成されます。 開いてみると、3 列のクリーンなバーコードが適度な冗長性を持っていることが確認できます。

## 手順 4: エラ―補正を Level 5 に上げて再度保存

ラベルが擦れやすい倉庫の床など、より過酷なダメージに耐えさせたい場合があります。 **Level 5** に切り替えると、エラ―補正が最大化され、画像はやや大きくなりますが、データ保護が強化されます。

```csharp
// Step 4: Change error correction level to 5 and save the second image
generator.Parameters.Barcode.Pdf417.ErrorLevel = Pdf417ErrorLevel.Level5;
generator.Save($"{outputFolder}Pdf417ErrorLevel5.png", BarCodeImageFormat.Png);
```

これで 2 つの PNG ファイルが並びます：中程度のエラ―補正と最大補正のものです。 比較してみてください。 Level 5 のバージョンは暗いモジュールが増えており、アルゴリズムがデータ保護のために追加した部分です。

![PDF417 バーコードのエラーレベル設定例](image.png)

*画像の説明（代替テキスト）: PDF417 バーコードのエラーレベル設定例 – エラ―補正レベルが異なる 2 つの PNG ファイルを示す。*

## 期待される出力

| ファイル名                     | エラーレベル | 概算サイズ (px) |
|-------------------------------|--------------|-----------------|
| `Pdf417ErrorLevel2.png`       | Level 2      | 150 × 80        |
| `Pdf417ErrorLevel5.png`       | Level 5      | 180 × 95        |

両画像とも文字列 **“Åspóse.Barcóde©”** をエンコードしており、任意の標準 PDF417 リーダー（例: ZXing、Scandit）で読み取れます。 Level 5 の画像は約 30 % の損傷に耐え、Level 2 は約 15 % の損傷に耐えます。

## よくある質問とエッジケース

### テキストに改行が含まれる場合は？
PDF417 は改行文字（`\n`）を自動的にエンコードします。 文字列にそのまま含めてください。

```csharp
new BarcodeGenerator(EncodeTypes.Pdf417, "Line1\nLine2\nLine3");
```

### 別の画像形式は使えますか？
もちろんです。 `BarCodeImageFormat.Png` を `Jpeg`、`Bmp`、`Svg` など、 downstream のワークフローに合わせて置き換えてください。

### X‑ディメンションを変えるとエラ―補正に影響しますか？
間接的には影響します。 大きな X‑ディメンションはモジュールを大きくし、スキャン信頼性を向上させますが、論理的なエラ―補正レベルは変わりません。 両方のパラメータは独立して調整し、最適な結果を得てください。

### Web API で PDF417 バーコードを生成するには？
同じコードを ASP.NET Core コントローラにラップし、PNG を `FileResult` としてストリーム返却すれば OK です。 コアロジックは変わらないので、**PDF417 の生成方法** はデスクトップでも Web でも一貫しています。

## まとめ

**PDF417 バーコードのエラー設定方法** を学び、**カスタム Unicode テキストで PDF417 を生成する方法** を実演し、X‑ディメンションや列数といったビジュアル設定の調整方法も示しました。 `Pdf417ErrorLevel.Level2` と `Level5` を入れ替えるだけで、画像サイズと耐障害性のトレードオフを自在にコントロールできます。

## 次のステップ

- URL や製品 ID を含む **カスタムテキストのバーコード** を試す
- 列数を変更して（例: `generator.Parameters.Barcode.Pdf417.Columns = 5`）形状の変化を確認
- 同一ドキュメント内で PDF417 と他のバーコードタイプを組み合わせ、マルチモーダルスキャンソリューションを構築
- Aspose の [公式ドキュメント](https://docs.aspose.com/barcode/net/) を参照し、マクロ PDF417 やコンパクトモードなど高度な機能を探索

質問や問題があればコメントで教えてください。スキャン結果の共有も歓迎です。バーコード作成、楽しんでください！

## 次に学ぶべきこと

以下のチュートリアルは、本ガイドで示したテクニックを応用した関連トピックを扱っています。 各リソースには完全なコード例とステップバイステップの解説が含まれており、API の追加機能を習得したり、独自プロジェクトで代替実装アプローチを探求したりするのに役立ちます。

- [Compact PDF417 を Aspose.BarCode で作成する方法](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [.NET でエラ―補正付き Aztec バーコードを作成する方法](/barcode/english/net/aztec-barcode-encoding/aztec-error-level-example/)
- [Aspose.BarCode for .NET で DataMatrix (ECC 200) を生成する方法](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-ecc-200-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}