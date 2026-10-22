---
category: general
date: 2026-10-21
description: C#でBarcodeGeneratorを使用して、データバー拡張スタックバーコード画像を生成します。このステップバイステップガイドに従って、バーコード画像を作成し、行と列をカスタマイズし、PNGファイルとしてエクスポートしてください。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- databar expanded stacked
- generate barcode image
- barcode generator c#
- how to generate databar
- create databar barcode
language: ja
lastmod: 2026-10-21
og_description: このチュートリアルでC#を使い、データバー拡張スタックバーコードを生成します。BarcodeGeneratorの使用方法、行と列の設定、PNG画像の保存方法を学びましょう。
og_image_alt: Sample databar expanded stacked barcode image generated with C#
og_title: C#でデータバー拡張スタックバーコードを生成する – 完全ガイド
schemas:
- author: Aspose
  dateModified: '2026-10-21'
  description: Generate a databar expanded stacked barcode image in C# using BarcodeGenerator.
    Follow this step‑by‑step guide to create barcode images, customize rows and columns,
    and export PNG files.
  headline: How to generate a databar expanded stacked barcode in C#
  type: TechArticle
- description: Generate a databar expanded stacked barcode image in C# using BarcodeGenerator.
    Follow this step‑by‑step guide to create barcode images, customize rows and columns,
    and export PNG files.
  name: How to generate a databar expanded stacked barcode in C#
  steps:
  - name: Basic barcode generation
    text: The simplest way to generate a **databar expanded stacked** image is to
      instantiate `BarcodeGenerator` with the desired `EncodeTypes` value and a plain
      text payload.
  - name: Customizing columns – create databar barcode with 4 columns
    text: You can control the number of columns using the `Parameters.Barcode.DataBar.Columns`
      property. The following example creates a barcode with **4 columns** while keeping
      the default row count.
  - name: Customizing rows – create databar barcode with 3 rows
    text: Similarly, you can adjust the row count via `Parameters.Barcode.DataBar.Rows`.
      The code below generates a barcode with **3 rows** and the default column count
      (4).
  - name: Exporting to other formats
    text: 'If you need a different image type (e.g., JPEG, BMP, or SVG), replace `BarCodeImageFormat.Png`
      with the appropriate enum value:'
  - name: Saving to a memory stream
    text: 'Sometimes you want to embed the barcode directly into a web response or
      a PDF without touching the file system. Use a `MemoryStream`:'
  - name: Handling invalid input
    text: 'The `BarcodeGenerator` validates the payload against the chosen symbology.
      If the data contains prohibited characters, an `ArgumentException` is thrown.
      Wrap the generation code in a try‑catch block to provide a friendly error message:'
  - name: Scaling the barcode image
    text: 'You can change the image size without altering the encoded data by setting
      `Parameters.Image.Width` and `Parameters.Image.Height`:'
  type: HowTo
tags:
- barcode
- C#
- Aspose.BarCode
title: C#でデータバー拡張スタック型バーコードを生成する方法
url: /ja/python-java/general/how-to-generate-a-databar-expanded-stacked-barcode-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# C#でdatabar expanded stackedバーコードを生成する方法

C#で**databar expanded stacked**バーコードを生成する必要がある場合、このガイドで方法を示します。databar expanded stackedシンボルは大量のデータをコンパクトにエンコードするのに最適で、数行のコードだけで画像を作成できます。また、**generate barcode image**ファイルをさまざまな形式で生成し、スキャン環境に合わせて行や列をカスタマイズする方法も学べます。

このチュートリアルでは、databarバーコードの作成に必要なすべてをカバーします：必要なライブラリのインストール、出力フォルダーの準備、カスタム行または列でのバーコード作成、そして結果をPNGファイルとして保存する方法です。最後まで読むと、プログラムで**create databar barcode**画像を生成し、他の画像形式や実行時シナリオに合わせてコードを適応させることができます。

## 前提条件

* .NET 6.0 SDK またはそれ以降（コードは .NET Core 3.1 および .NET Framework 4.7+ でも動作します）
* Visual Studio 2022、Visual Studio Code、または Rider などの開発環境
* インターネット接続があり、**Barcode Generator C#** NuGet パッケージ（Aspose.BarCode for .NET）をインストールできること

> **プロのコツ:** CI/CD パイプラインを使用している場合、ビルドの再現性を確保するためにプロジェクト ファイルに NuGet パッケージ参照を追加してください。

## Barcode Generator C# ライブラリのインストール

この例では Aspose.BarCode ライブラリを使用します。このライブラリは `BarcodeGenerator` クラスと `EncodeTypes.DatabarExpandedStacked` 列挙体を提供します。

```bash
dotnet add package Aspose.BarCode
```

このコマンドは最新の安定版をプロジェクトに追加します。インストール後、C# ファイルで名前空間をインポートできます。

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;
```

## 出力フォルダーの準備

信頼できるファイルパスは、ライブラリが画像を書き込もうとしたときのランタイムエラーを防ぎます。以下のコードは、ディレクトリが存在しない場合に作成します。

```csharp
using System;
using System.IO;

// Define the folder where barcode images will be saved
string outputFolder = Path.Combine(Environment.CurrentDirectory, "Barcodes");

// Ensure the folder exists
Directory.CreateDirectory(outputFolder);
```

> **なぜ重要か:** 存在しないディレクトリに保存しようとすると `IOException` がスローされます。事前にフォルダーを作成することで、ローカル開発と本番環境の両方でコードが堅牢になります。

## databar expanded stackedバーコード画像の生成

### 基本的なバーコード生成

**databar expanded stacked**画像を生成する最も簡単な方法は、目的の `EncodeTypes` 値とプレーンテキストのペイロードで `BarcodeGenerator` をインスタンス化することです。

```csharp
// Create a barcode that encodes a long numeric string
var basicGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked,
    "01234567890123456789");

// Save the barcode as PNG
basicGenerator.Save(Path.Combine(outputFolder, "DatabarBasic.png"),
    BarCodeImageFormat.Png);
```

スニペットを実行すると、*Barcodes* フォルダーに `DatabarBasic.png` が生成されます。この画像は、デフォルトのレイアウト（4列 × 4行）で標準的な databar expanded stacked シンボルを含みます。

### 列のカスタマイズ – 4列のdatabarバーコードを作成

`Parameters.Barcode.DataBar.Columns` プロパティを使用して列数を制御できます。以下の例は、デフォルトの行数を維持しつつ **4 columns** のバーコードを作成します。

```csharp
// Step 1: Define a generator with custom column count
var columnGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked,
    "Databar Expanded Stacked long");

// Set the column count to 4 (default rows = 4)
columnGenerator.Parameters.Barcode.DataBar.Columns = 4;

// Save the image
columnGenerator.Save(Path.Combine(outputFolder, "DatabarCols4.png"),
    BarCodeImageFormat.Png);
```

生成されたファイル **DatabarCols4.png** は次のようになります：

![Databar expanded stacked barcode with 4 columns](databar_cols4.png "Databar expanded stacked barcode with 4 columns – generated with C#")

*画像の alt テキスト (og_image_alt):* **Sample databar expanded stacked barcode image generated with C#** – これは画像の alt テキストに関する SEO 要件を満たします。

### 行のカスタマイズ – 3行のdatabarバーコードを作成

同様に、`Parameters.Barcode.DataBar.Rows` で行数を調整できます。以下のコードは **3 rows** とデフォルトの列数（4）でバーコードを生成します。

```csharp
// Step 2: Define a generator with custom row count
var rowGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked,
    "Databar Expanded Stacked long");

// Set the row count to 3 (default columns = 4)
rowGenerator.Parameters.Barcode.DataBar.Rows = 3;

// Save the image
rowGenerator.Save(Path.Combine(outputFolder, "DatabarRows3.png"),
    BarCodeImageFormat.Png);
```

ファイル **DatabarRows3.png** には、縦方向にやや短い databar expanded stacked シンボルが含まれており、スペースが限られたラベルに有用です。

### 他のフォーマットへのエクスポート

別の画像タイプ（例：JPEG、BMP、SVG）が必要な場合は、`BarCodeImageFormat.Png` を適切な列挙値に置き換えてください。

```csharp
columnGenerator.Save(Path.Combine(outputFolder, "DatabarCols4.jpg"),
    BarCodeImageFormat.Jpeg);
```

このライブラリは SVG のようなベクターフォーマットもサポートしており、高解像度印刷に最適です。

## 高度なシナリオ

### メモリストリームへの保存

場合によっては、ファイルシステムに触れずにバーコードをウェブレスポンスや PDF に直接埋め込みたいことがあります。その際は `MemoryStream` を使用します。

```csharp
using System.IO;

// Generate barcode into a memory stream
using var ms = new MemoryStream();
columnGenerator.Save(ms, BarCodeImageFormat.Png);

// Reset stream position before reading
ms.Position = 0;

// Example: return the stream as a file download in ASP.NET Core
// return File(ms.ToArray(), "image/png", "databar.png");
```

### 無効な入力の処理

`BarcodeGenerator` は選択したシンボロジーに対してペイロードを検証します。データに禁止文字が含まれると `ArgumentException` がスローされます。生成コードを try‑catch ブロックでラップし、ユーザーフレンドリーなエラーメッセージを提供してください。

```csharp
try
{
    var gen = new BarcodeGenerator(EncodeTypes.DatabarExpandedStacked, "INVALID*DATA");
    gen.Save(Path.Combine(outputFolder, "Invalid.png"), BarCodeImageFormat.Png);
}
catch (ArgumentException ex)
{
    Console.WriteLine($"Failed to generate barcode: {ex.Message}");
}
```

### バーコード画像のスケーリング

`Parameters.Image.Width` と `Parameters.Image.Height` を設定することで、エンコードされたデータを変更せずに画像サイズを変更できます。

```csharp
columnGenerator.Parameters.Image.Width = 300;   // pixels
columnGenerator.Parameters.Image.Height = 150; // pixels
columnGenerator.Save(Path.Combine(outputFolder, "DatabarLarge.png"),
    BarCodeImageFormat.Png);
```

スケーリングは、スキャナーが特定の DPI 要件を満たす必要がある場合に有用です。

## 完全な動作例

以下は、説明したすべての手順を示す、完全で実行可能なコンソール アプリケーションです。

```csharp
using System;
using System.IO;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace DatabarExpandedStackedDemo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Prepare output folder
            string outputFolder = Path.Combine(
                Environment.CurrentDirectory, "Barcodes");
            Directory.CreateDirectory(outputFolder);

            // 2️⃣ Generate basic barcode
            var basic = new BarcodeGenerator(
                EncodeTypes.DatabarExpandedStacked,
                "01234567890123456789");
            basic.Save(Path.Combine(outputFolder, "DatabarBasic.png"),
                BarCodeImageFormat.Png);

            // 3️⃣ Generate barcode with 4 columns
            var colGen = new BarcodeGenerator(
                EncodeTypes.DatabarExpandedStacked,
                "Databar Expanded Stacked long");
            colGen.Parameters.Barcode.DataBar.Columns = 4;
            colGen.Save(Path.Combine(outputFolder, "DatabarCols4.png"),
                BarCodeImageFormat.Png);

            // 4️⃣ Generate barcode with 3 rows
            var rowGen = new BarcodeGenerator(
                EncodeTypes.DatabarExpandedStacked,
                "Databar Expanded Stacked long");
            rowGen.Parameters.Barcode.DataBar.Rows = 3;
            rowGen.Save(Path.Combine(outputFolder, "DatabarRows3.png"),
                BarCodeImageFormat.Png);

            // 5️⃣ Export to JPEG as an extra format
            colGen.Save(Path.Combine(outputFolder, "DatabarCols4.jpg"),
                BarCodeImageFormat.Jpeg);

            Console.WriteLine("All barcode images have been generated in:");
            Console.WriteLine(outputFolder);
        }
    }
}
```

**期待される出力**

## 次に学ぶべきことは？

以下のチュートリアルは、本ガイドで示した手法を基にした密接に関連するトピックをカバーしています。各リソースには、ステップバイステップの解説と完全な動作コード例が含まれており、追加の API 機能を習得し、プロジェクトで代替実装アプローチを検討するのに役立ちます。

- [Databar Expanded Stacked バーコードの列設定方法 – 完全な C# ガイド](/barcode/english/python-java/general/how-to-set-columns-for-a-databar-expanded-stacked-barcode-co/)
- [DataBar Expanded Stacked を使用した C# のバーコードジェネレータ例の作成方法](/barcode/english/python-java/general/how-to-build-a-barcode-generator-example-in-c-with-databar-e/)
- [databar expanded stacked バーコードガイド – C# での生成とサイズ設定方法](/barcode/english/python-java/general/databar-expanded-stacked-barcode-guide-how-to-generate-and-s/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}