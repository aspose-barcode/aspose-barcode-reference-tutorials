---
category: general
date: 2026-11-14
description: Aspose.BarCode を使用して C# でバーコード画像を作成する方法を学びましょう。このステップバイステップガイドでは、バーコードジェネレーターの
  C# 設定、GS1 フォーマット、PNG エクスポートについて解説します。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode image
- how to generate barcode
- barcode generator c#
- create gs1 barcode
- barcode image from data
language: ja
lastmod: 2026-11-14
og_description: C#でバーコード画像を素早く作成します。このガイドに従って、バーコードの生成方法、C#のバーコードジェネレーターの使用方法、そしてGS1
  MicroPDF417 PNGのエクスポート方法を学びましょう。
og_image_alt: Screenshot of a GS1 MicroPDF417 barcode generated in C#
og_title: C#でバーコード画像を作成する – GS1 MicroPDF417 完全ガイド
schemas:
- author: Aspose
  dateModified: '2026-11-14'
  description: Learn how to create barcode image in C# using Aspose.BarCode. This
    step‑by‑step guide covers barcode generator c# setup, GS1 formatting and PNG export.
  headline: How to create barcode image in C# with GS1 MicroPDF417
  type: TechArticle
tags:
- barcode
- C#
- Aspose
title: C#でGS1 MicroPDF417を使用してバーコード画像を作成する方法
url: /ja/net/gs1-barcode-encoding/how-to-create-barcode-image-in-c-with-gs1-micropdf417/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# C#でGS1 MicroPDF417のバーコード画像を作成する方法

C#で**バーコード画像を作成**する必要がある場合、このガイドでは完全な、すぐに実行できるソリューションを示します。**バーコードを生成**する方法を、GS1標準に従ったデータの生成、ジェネレータの設定、そして高品質なPNGファイルのエクスポートまで確認できます。

このチュートリアルでは、必要なライブラリのインストールから一般的なデータ形式の落とし穴の対処までを網羅しています。最後まで読むと、数行のコードだけで**データからバーコード画像**を生成でき、各設定が重要な理由も理解できるようになります。

## 前提条件

* .NET 6.0以降がインストールされていること（コードは.NET Framework 4.7+でも動作します）。
* Visual Studio 2022やVisual Studio CodeなどのIDE。
* **Aspose.BarCode for .NET** NuGet パッケージ。以下でインストールします：

```bash
dotnet add package Aspose.BarCode
```

* C#の構文とGS1アプリケーション識別子（AI）形式に関する基本的な知識。

> **プロのコツ:** ライブラリのバージョンは常に最新に保ちましょう。最新リリースでは新しいバーコードシンボロジーのサポートやパフォーマンス向上が追加されています。

## BarcodeGeneratorでバーコード画像を作成する

このセクションではコア実装を示します。コードは**barcode generator c#**インスタンスを作成し、可読性のためにX‑dimensionを設定し、結果をPNGファイルとして保存します。

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

// Step 1: Initialise the generator with the GS1 MicroPDF417 symbology
// The data string follows the GS1 syntax: (01)GTIN(21)SerialNumber
BarcodeGenerator generator = new BarcodeGenerator(
    EncodeTypes.MicroPdf417,
    "(01)12345678901234(21)ABC123");

// Step 2: Adjust the module width (X‑dimension) to improve scan reliability
// A value of 2 pixels works well for most screen‑displayed barcodes.
generator.Parameters.Barcode.XDimension.Pixels = 2;

// Step 3: Export the barcode as a PNG image
string outputPath = Path.Combine(
    Environment.GetFolderPath(Environment.SpecialFolder.Desktop),
    "GS1MicroPdf417.png");
generator.Save(outputPath, BarCodeImageFormat.Png);
```

### 各行が重要な理由

* **EncodeTypes.MicroPdf417** は、ライブラリにGS1 MicroPDF417シンボロジーを使用するよう指示します。このシンボロジーはコンパクトでモバイルスキャンに最適です。
* **data string** は、GTIN（Global Trade Item Number）用のGS1 AI `(01)` で始まり、続いてシリアル番号用の `(21)` が必要です。形式が正しくないと、ジェネレータは例外をスローします。
* **XDimension.Pixels** は最小バーの幅を制御します。値を大きくすると低解像度ディスプレイでの可読性が向上し、値を小さくすると画像サイズが縮小します。
* **BarCodeImageFormat.Png** はロスレス画像を生成し、信頼できるスキャンに必要な鮮明なエッジを保持します。

プログラムを実行すると、デスクトップに `GS1MicroPdf417.png` が作成されます。ファイルを開くと、GTIN `12345678901234` とシリアル `ABC123` をエンコードした、濃密な黒オンホワイトのバーコードが表示されます。

## GS1 MicroPDF417を使用してバーコードを生成する方法

GS1フォーマットが初めての場合、以下の基本ルールをご確認ください。

| GS1 AI | 意味                     | 例               |
|--------|--------------------------|------------------|
| (01)   | Global Trade Item Number | 12345678901234   |
| (21)   | Serial number (optional) | ABC123           |

AIとその値を連結する際は、各AIを丸括弧で囲み、値をすぐ後ろに置きます。生成された文字列は、**barcode generator c#** に追加のエンコードなしで渡すことができます。

### よくある落とし穴

* **括弧の欠落** – ジェネレータは文字列を生データとして扱い、GS1チェックを適用しません。
* **長さ制限超過** – MicroPDF417は最大155文字をサポートします。不要な空白は削除してください。
* **無効な文字** – GTINには数字のみが許可され、シリアルには大文字アルファベットと数字が含められます。

## データからバーコード画像をカスタマイズする

基本的なX‑dimensionに加えて、Aspose.BarCodeは多数のビジュアル調整機能を提供します。以下はプロジェクトの要件に応じて適用できるいくつかの調整例です。

```csharp
// Set background to transparent (useful for overlaying on UI)
generator.Parameters.ImageBackgroundColor = Color.Transparent;

// Change foreground color to dark blue for branding
generator.Parameters.Barcode.BarColor = Color.FromArgb(0, 0, 139);

// Increase image resolution to 300 dpi for print‑ready output
generator.Parameters.ImageResolution = 300;
```

各設定はオプションです。デフォルトでもクリーンでスキャン可能な**barcode image**が生成されます。スキャナがコードを読み取れることを確認した上で、色や解像度の実験を行ってください。

## バーコードを他の形式で保存する

PNGはウェブやモバイルで最も一般的な形式ですが、JPEG、BMP、SVGが必要になる場合もあります。`Save` メソッドは任意の `BarCodeImageFormat` 値を受け取ります。

```csharp
generator.Save("barcode.jpg", BarCodeImageFormat.Jpeg);
generator.Save("barcode.svg", BarCodeImageFormat.Svg);
```

* JPEGはファイルサイズを削減しますが、可読性に影響を与える圧縮アーティファクトが発生します。
* SVGはベクタ品質を保持し、レスポンシブウェブデザインに最適です。

## 生成されたバーコードの検証

**create barcode image** 手順が成功したことを確認する簡単な方法は、GS1 MicroPDF417に対応したモバイルスキャナアプリを使用することです。保存したPNGをスキャンすると、アプリは以下を表示するはずです：

```
GTIN: 12345678901234
Serial: ABC123
```

スキャナがエラーを報告した場合、AIのフォーマットとX‑dimensionの値を再確認してください。

## 完全な例 – 自立したコンソールプログラム

以下は、NuGetインストール手順を除いてそのままコピー＆ペーストで実行できる完全なプログラムです。

```csharp
using System;
using System.IO;
using System.Drawing;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // Initialise the generator with GS1 MicroPDF417 and sample data
            BarcodeGenerator generator = new BarcodeGenerator(
                EncodeTypes.MicroPdf417,
                "(01)12345678901234(21)ABC123");

            // Improve readability by setting module width
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // Optional visual customisation
            generator.Parameters.ImageBackgroundColor = Color.Transparent;
            generator.Parameters.Barcode.BarColor = Color.FromArgb(0, 0, 139);
            generator.Parameters.ImageResolution = 300;

            // Define output path (Desktop folder)
            string outputPath = Path.Combine(
                Environment.GetFolderPath(Environment.SpecialFolder.Desktop),
                "GS1MicroPdf417.png");

            // Save the barcode as PNG
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"Barcode image saved to: {outputPath}");
        }
    }
}
```

プログラムを実行すると、コンソールにフルファイルパスが表示され、PNGがデスクトップに作成されます。この例は、**how to generate barcode** データの生成、外観のカスタマイズ、そして**barcode image from data** のエクスポートを1つの統合ワークフローで示しています。

## よくある質問

| 質問 | 回答 |
|----------|--------|
| *他のGS1シンボロジーを生成できますか？* | はい。`EncodeTypes.MicroPdf417` を `EncodeTypes.Pdf417`、`EncodeTypes.DataMatrix` などに置き換え、データ文字列をそれに合わせて調整してください。 |
| *データがMicroPDF417の容量を超えた場合はどうすればよいですか？* | より長いペイロードをサポートする通常のPDF417シンボロジーに切り替えてください。 |
| *Aspose.BarCodeのライセンスは必要ですか？* | 開発目的であれば無料の評価ライセンスで動作します。製品版では評価用の透かしを除去するためにライセンスを購入してください。 |
| *ラベル印刷にPNGは適していますか？* | `ImageResolution` を300 dpi以上に上げ、産業用プリンター向けにはTIFFで保存することも検討してください。 |

## 結論

これで、**barcode generator c#** アプローチを使用してC#で**barcode image** を作成し、**create gs1 barcode** シナリオ向けにデータをフォーマットし、結果をPNGや他の画像形式でエクスポートする方法が分かりました。完全な例は、データ準備からビジュアルカスタマイズまでのすべての手順を示しているので、任意の.NETアプリケーションにバーコード作成を組み込むことができます。

次に、QRコード向けの**barcode image from data**、単一PDFへの複数バーコードの追加、在庫システム向けのバッチ生成の自動化など、関連トピックを探ってみてください。さまざまなX‑dimensionの値や画像形式を試し、特定のスキャン環境に最適な設定を見つけましょう。

コーディングを楽しんで、アプリケーションが実世界で確実に動作する**barcode images** の作成を開始できるようにしましょう！

## 次に学ぶべきことは？

以下のチュートリアルは、本ガイドで示した手法を基にした密接に関連するトピックを取り上げています。各リソースには、ステップバイステップの解説と完全な動作コード例が含まれており、追加のAPI機能を習得し、独自プロジェクトで代替実装アプローチを検討するのに役立ちます。

- [C#でAspose.Barcodeを使用してバーコード画像を作成する方法](/barcode/english/python-java/general/how-to-create-barcode-image-with-aspose-barcode-in-c/)
- [C#でAspose.BarCodeを使用して郵便バーコード画像を作成する方法](/barcode/english/python-java/general/how-to-create-postal-barcode-image-in-c-using-aspose-barcode/)
- [C#でPDF417バーコード画像を作成する方法 – 完全ガイド](/barcode/english/net/compact-pdf417-encoding/generate-pdf417-barcode-in-c-complete-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}