---
category: general
date: 2026-10-28
description: Aspose.BarCode を使用してカスタムテキストでバーコードを生成する方法 – .NET 開発者向けのステップバイステップガイド、バーコードの
  Aspose 画像を作成する。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to generate barcode
- generate barcode custom text
- create barcode aspose
language: ja
lastmod: 2026-10-28
og_description: .NETでAspose.BarCodeを使用してカスタムテキスト付きバーコードを生成する方法。Macro PDF417バーコードを作成し保存する完全ガイドをご覧ください。
og_image_alt: how to generate barcode example PNG image showing a Macro PDF417 barcode
og_title: カスタムテキストでバーコードを生成する方法 – Aspose.BarCode チュートリアル
schemas:
- author: Aspose
  dateModified: '2026-10-28'
  description: How to generate barcode with custom text using Aspose.BarCode – step‑by‑step
    guide for .NET developers to create barcode Aspose images.
  headline: How to generate barcode with custom text using Aspose.BarCode for .NET
  type: TechArticle
- description: How to generate barcode with custom text using Aspose.BarCode – step‑by‑step
    guide for .NET developers to create barcode Aspose images.
  name: How to generate barcode with custom text using Aspose.BarCode for .NET
  steps:
  - name: Why each line matters
    text: '* **EncodeTypes.MacroPdf417** – selects the Macro PDF417 symbology, which
      supports segmented data and metadata. * **XDimension.Pixels** – controls the
      size of each module; a value of 2 pixels yields a clear, scannable image. *
      **Pdf417.Columns** – reduces the overall width, making the barcode more c'
  - name: Using a different barcode type
    text: If you need to **generate barcode custom text** for a QR code instead of
      Macro PDF417, replace `EncodeTypes.MacroPdf417` with `EncodeTypes.QR`. The rest
      of the parameter structure stays the same, but QR codes do not support Macro
      metadata fields.
  - name: Handling Unicode characters
    text: The example already includes Unicode characters (`Å`, `ó`, `©`). Aspose.BarCode
      handles UTF‑8 input out of the box, but you should ensure the source file is
      saved with UTF‑8 encoding to avoid compile‑time warnings.
  - name: Saving to other image formats
    text: 'Aspose.BarCode supports BMP, JPEG, TIFF, and SVG in addition to PNG. Change
      the `BarCodeImageFormat` enum value accordingly:'
  - name: Large data sets
    text: Macro PDF417 can split data across multiple segments. When the text exceeds
      the capacity of a single segment, increment `MacroPdf417SegmentID` and keep
      `MacroPdf417SegmentsCount` consistent across all generated parts. This approach
      is essential for **create barcode aspose** scenarios where the paylo
  - name: Error handling
    text: 'Wrap the generation logic in a try‑catch block to surface runtime issues
      such as invalid file paths or unsupported characters:'
  type: HowTo
tags:
- barcode
- Aspose.BarCode
- .NET
title: .NET 用 Aspose.BarCode を使用してカスタムテキストでバーコードを生成する方法
url: /ja/net/one-dimensional-barcode-types/how-to-generate-barcode-with-custom-text-using-aspose-barcod/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.BarCode for .NET を使用したカスタムテキスト付きバーコードの生成方法

カスタムテキスト付きバーコードを生成することは、識別子やタイムスタンプ、その他のメタデータを視覚コードに直接埋め込む必要がある場合に頻繁に求められる要件です。このチュートリアルでは、**Aspose.BarCode** ライブラリ for .NET を使用して、カスタムテキストと完全なメタデータを保持する Macro PDF417 バーコードの生成方法を示します。

このチュートリアルを通じて、ジェネレータの設定方法、カスタムテキストの適用、Macro PDF417 固有のフィールド設定、そして PNG 画像として保存する手順を学びます。外部ツールは不要で、Aspose.BarCode の NuGet パッケージと .NET 開発環境さえあれば完了します。

## 前提条件

開始する前に、以下がインストールされていることを確認してください。

* .NET 6.0 SDK 以降がインストール済み  
* Visual Studio 2022（または .NET をサポートする任意の IDE）  
* **Aspose.BarCode for .NET** NuGet パッケージ (`Install-Package Aspose.BarCode`)  

これらの前提条件により、コードが追加設定なしでコンパイルおよび実行できるようになります。

## 手順 1: Aspose.BarCode パッケージのインストール

プロジェクト フォルダーでターミナルを開き、次のコマンドを実行します。

```bash
dotnet add package Aspose.BarCode
```

このコマンドは Aspose.BarCode の最新安定版をプロジェクトに追加し、`BarcodeGenerator` クラスや関連パラメータへのアクセスを可能にします。

## 手順 2: 新しいコンソール アプリケーションの作成

バーコード生成ロジックをホストする最小限のコンソール アプリを作成します。

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

namespace BarcodeDemo
{
    internal class Program
    {
        private static void Main()
        {
            // The full barcode generation flow is encapsulated in a separate method
            GenerateMacroPdf417Barcode();
        }

        /// <summary>
        /// Generates a Macro PDF417 barcode with custom text and metadata, then saves it as PNG.
        /// </summary>
        private static void GenerateMacroPdf417Barcode()
        {
            // Step 1: Instantiate the generator with the desired encode type and data
            using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MacroPdf417, "Åspóse.Barcóde©"))
            {
                // Step 2: Define the visual appearance of the barcode
                generator.Parameters.Barcode.XDimension.Pixels = 2;          // Size of a single module
                generator.Parameters.Barcode.Pdf417.Columns = 5;            // Number of columns in the symbol

                // Step 3: Populate Macro PDF417 specific metadata fields
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
                generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;
                generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";
                generator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234; // CCITT‑16 example value
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000;
                generator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2019, 11, 1);
                generator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
                generator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
                generator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;

                // Step 4: Save the barcode image to disk
                string outputPath = @"ExtPDF417Meta.png";
                generator.Save(outputPath, BarCodeImageFormat.Png);
                Console.WriteLine($"Barcode saved to {outputPath}");
            }
        }
    }
}
```

### 各行の重要性

* **EncodeTypes.MacroPdf417** – セグメント化されたデータとメタデータをサポートする Macro PDF417 シンボルを選択します。  
* **XDimension.Pixels** – 各モジュールのサイズを制御します。2 ピクセルの値は、鮮明でスキャンしやすい画像を生成します。  
* **Pdf417.Columns** – 全体の幅を縮小し、印刷ラベル向けにバーコードをコンパクトにします。  
* **MacroPdf417* properties** – ファイルレベルの情報（ID、セグメント数、タイムスタンプなど）をバーコードに直接埋め込みます。この機能は Macro PDF417 固有で、物流や文書管理システムで頻繁に利用されます。  
* **Save(..., BarCodeImageFormat.Png)** – ロスレス PNG ファイルを書き出し、バーコードのエッジを鮮明に保ち、信頼性の高いスキャンを実現します。

## 手順 3: プログラムを実行して出力を確認する

コンソール アプリをビルドして実行します。

```bash
dotnet run
```

プログラムはプロジェクトの作業ディレクトリに `ExtPDF417Meta.png` を作成します。ファイルを開くと、カスタムテキスト **“Åspóse.Barcóde©”** と、指定したメタデータをエンコードした Macro PDF417 バーコードが表示されます。

**期待される出力** – 以下のような PNG 画像です。

![Macro PDF417 バーコードを示す、バーコード生成例の出力 PNG 画像](ExtPDF417Meta.png)

*画像の alt テキスト（“Macro PDF417 バーコードを示す、バーコード生成例の出力 PNG 画像”）は、アクセシビリティと SEO のために主要キーワードを強調しています。*

## 一般的なバリエーションとエッジケース

### 別のバーコードタイプを使用する場合

Macro PDF417 の代わりに QR コードで **generate barcode custom text** が必要な場合は、`EncodeTypes.MacroPdf417` を `EncodeTypes.QR` に置き換えます。パラメータ構造は同じですが、QR コードは Macro メタデータ フィールドをサポートしません。

### Unicode 文字の取り扱い

この例にはすでに Unicode 文字（`Å`, `ó`, `©`）が含まれています。Aspose.BarCode は UTF‑8 入力を標準で処理しますが、コンパイル時の警告を回避するためにソース ファイルを UTF‑8 エンコーディングで保存してください。

### 他の画像形式で保存する

Aspose.BarCode は PNG に加えて BMP、JPEG、TIFF、SVG もサポートしています。`BarCodeImageFormat` 列挙体の値を以下のように変更してください。

```csharp
generator.Save("barcode.svg", BarCodeImageFormat.Svg);
```

### 大規模データセット

Macro PDF417 はデータを複数のセグメントに分割できます。テキストが単一セグメントの容量を超える場合は、`MacroPdf417SegmentID` をインクリメントし、すべての生成パートで `MacroPdf417SegmentsCount` を一貫させます。この手法は、ペイロードが単一バーコードの容量を超える **create barcode aspose** シナリオで必須です。

### エラーハンドリング

生成ロジックを try‑catch ブロックでラップし、無効なファイル パスやサポート外文字などの実行時エラーを検出できるようにします。

```csharp
try
{
    GenerateMacroPdf417Barcode();
}
catch (Exception ex)
{
    Console.Error.WriteLine($"Barcode generation failed: {ex.Message}");
}
```

## 信頼性の高いバーコード生成のためのプロのコツ

* **Validate the barcode** を `BarCodeReader` で実行し、作成後にバーコードを検証します。この追加ステップにより、エンコードされたデータが期待通りであることを確認できます。

  ```csharp
  using (BarCodeReader reader = new BarCodeReader("ExtPDF417Meta.png", DecodeType.MacroPdf417))
  {
      if (reader.Read())
          Console.WriteLine($"Decoded text: {reader.GetCodeText()}");
  }
  ```

* **X‑dimension を 2 – 4 ピクセル** の範囲に保つと、ほとんどのスキャナで最適に読み取れます。小さすぎる値は低解像度デバイスで読めない画像になる可能性があります。

* `MacroPdf417FileName` に **非常に長いファイル名** を使用しないでください。仕様上、フィールドは最大 32 文字に制限されています。

* 複数セグメントを生成する際は **UTC の一貫したタイムスタンプ** を使用し、下流処理をシンプルに保ちます。

## 結論

これで、Aspose.BarCode for .NET を使用してカスタムテキスト付きバーコードを生成し、Macro PDF417 メタデータを設定し、PNG 画像として保存する方法が分かりました。完全な実行可能サンプルは、NuGet パッケージのインストールから Unicode 文字の取り扱い、出力の保存まで、必要なすべての手順を示しています。

ここからは次のことが可能です。

* 他のシンボル（QR、DataMatrix など）向けに **Generate barcode custom text** を実装する  
* 数千枚の画像をバッチ処理する **Create barcode Aspose** ワークフローを構築する  
* バーコード生成コードを ASP.NET Core サービス、Windows サービス、または Azure Functions に統合する  

さまざまなパラメータを試し、追加のメタデータ フィールドを探索し、ドキュメント自動化パイプラインにバーコードを組み込んでみてください。コーディングを楽しんでください！

## 次に学ぶべきことは？

以下のチュートリアルは、本ガイドで示した手法を基にした密接に関連するトピックを扱っています。各リソースには、完全な動作コード例とステップバイステップの解説が含まれており、追加の API 機能を習得し、独自プロジェクトで代替実装アプローチを探求するのに役立ちます。

- [How to Create PDF417 Barcode with Aspose – Complete Step‑by‑Step Guide](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-with-aspose-complete-step-by-st/)
- [Generate barcode from text using Aspose.BarCode – C# Guide](/barcode/english/net/one-dimensional-barcode-types/generate-barcode-from-text-using-aspose-barcode-c-guide/)
- [How to use Aspose.BarCode to create DataMatrix code text in .NET](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-extended-code-text-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}