---
category: general
date: 2026-09-13
description: Aspose.Barcode を使用して C# でデータバー スタック型バーコードを素早く作成し、列・行の設定方法と画像の保存方法を学びましょう。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create databar stacked barcode
- Databar Expanded Stacked
- barcode columns
- barcode rows
- Aspose.Barcode for .NET
- C# barcode generator
language: ja
lastmod: 2026-09-13
og_description: Aspose.Barcode を使用して C# でデータバー スタック型バーコードを作成します。このガイドでは、列と行の設定方法と
  PNG 画像へのエクスポート方法を示します。
og_image_alt: Screenshot of a generated Databar stacked barcode saved as PNG
og_title: C#でデータバー スタック型バーコードを作成する – 完全ステップバイステップガイド
schemas:
- author: Aspose
  dateModified: '2026-09-13'
  description: Create databar stacked barcode in C# quickly using Aspose.Barcode –
    learn to set columns, rows, and save images.
  headline: How to create databar stacked barcode in C# with Aspose.Barcode
  type: TechArticle
- description: Create databar stacked barcode in C# quickly using Aspose.Barcode –
    learn to set columns, rows, and save images.
  name: How to create databar stacked barcode in C# with Aspose.Barcode
  steps:
  - name: 'Create a new Console App project:'
    text: 'Create a new Console App project:'
  - name: 'Add the Aspose.Barcode package:'
    text: 'Add the Aspose.Barcode package:'
  - name: 'Open **Program.cs** and add the required `using` statements:'
    text: 'Open **Program.cs** and add the required `using` statements:'
  type: HowTo
tags:
- barcode
- C#
- Aspose
- Databar
title: C# と Aspose.Barcode でデータバー スタック型バーコードを作成する方法
url: /ja/python-java/general/how-to-create-databar-stacked-barcode-in-c-with-aspose-barco/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# C# と Aspose.Barcode を使用して Databar Stacked バーコードを作成する方法

.NET アプリケーションで **databar stacked barcode** を作成する必要がある場合、このガイドは完全な実行可能なソリューションを提供します。列数の設定、行の調整、結果を PNG ファイルとして保存する方法を、すべて Aspose.Barcode for .NET ライブラリを使って正確に示します。

**Databar Expanded Stacked** バーコードの生成は、3 ステップのワークフロー（ジェネレータのインスタンス化、希望のサイズ設定、画像のディスクへの書き込み）を理解すれば謎ではありません。以下のセクションで各パートを順に解説し、設定が重要な理由を説明し、すぐに確認できる最終出力を示します。

## 前提条件

- **Visual Studio 2022**（または任意の C# IDE）と .NET 6+ がインストールされていること。
- **Aspose.Barcode for .NET** NuGet パッケージ（`Install-Package Aspose.Barcode`）。
- PNG ファイルを保存するフォルダーへの書き込み権限があること。

追加の依存関係は必要ありません。

## 手順 1: プロジェクトのセットアップと Aspose.Barcode の追加

1. 新しいコンソール アプリ プロジェクトを作成します：

   ```bash
   dotnet new console -n DatabarStackedDemo
   cd DatabarStackedDemo
   ```

2. Aspose.Barcode パッケージを追加します：

   ```bash
   dotnet add package Aspose.Barcode
   ```

3. **Program.cs** を開き、必要な `using` ステートメントを追加します：

   ```csharp
   using Aspose.BarCode;
   using Aspose.BarCode.Generation;
   using System;
   ```

これらの手順により、**C# barcode generator** クラスがコードで利用可能になります。

## 手順 2: Databar Stacked バーコード用ジェネレータの作成

最初に必要なのは、**Databar Expanded Stacked** シンボロジー用に設定された `BarcodeGenerator` オブジェクトです。このオブジェクトはすべてのバーコード関連操作のエントリーポイントとなります。

```csharp
// Step 2: Initialize a generator for Databar Expanded Stacked
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked, // Symbology
    "Databar Expanded Stacked long");   // Human‑readable text (optional)
```

**この設定が重要な理由:**  
`EncodeTypes.DatabarExpandedStacked` は Aspose.Barcode に DataBar ファミリーのスタック版を使用するよう指示し、レシートのような高さが制限されたスペースに最適です。第2引数はバーコードにエンコードするデータを提供します。DataBar 標準に準拠した任意の数値または英数字文字列に置き換えることができます。

## 手順 3: バーコードの列数を設定し画像を保存する

スタックされた DataBar は、設定可能な **列** 数で表示できます。デフォルトは 3 列ですが、データ文字列が長い場合は 4 列が必要になることがあります。保存する前に `Columns` プロパティを調整します。

```csharp
// Step 3: Set the barcode to use 4 columns (default rows) and save the image
barcodeGenerator.Parameters.Barcode.DataBar.Columns = 4;

// Choose an output folder that exists on your machine
string outputPathCols = @"YOUR_DIRECTORY\DatabarCols4.png";
barcodeGenerator.Save(outputPathCols, BarCodeImageFormat.Png);

Console.WriteLine($"Barcode with 4 columns saved to {outputPathCols}");
```

**説明:**  
- `Parameters.Barcode.DataBar.Columns` はバーコードの水平分割に直接影響します。列数を増やすと画像は横に広くなりますが、高さは変わりません。  
- `Save` はバーコードを PNG ファイルとして書き出します。別の `BarCodeImageFormat` 値を渡すことで、JPEG、BMP、SVG など他の形式もサポートされます。

## 手順 4: 別のジェネレータを作成しバーコードの行数を設定する

スキャン環境によっては、より高いバーコードが必要になることがあります。その場合は **行** 数を増やすことで実現できます。以下のスニペットは、2 番目のジェネレータインスタンスを作成し、3 行に設定して結果を保存します。

```csharp
// Step 4: Create a new generator for the same data but with 3 rows
BarcodeGenerator barcodeGeneratorRows = new BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked,
    "Databar Expanded Stacked long");

// Set the barcode to use 3 rows (default columns)
barcodeGeneratorRows.Parameters.Barcode.DataBar.Rows = 3;

// Save the image with rows configured
string outputPathRows = @"YOUR_DIRECTORY\DatabarRows3.png";
barcodeGeneratorRows.Save(outputPathRows, BarCodeImageFormat.Png);

Console.WriteLine($"Barcode with 3 rows saved to {outputPathRows}");
```

**なぜ別インスタンスが必要か:**  
保存呼び出しの後に同じ `BarcodeGenerator` の `Rows` を変更しても動作しますが、新しいインスタンスを作成することで各設定が分離され、コードが読みやすくなります。特に、後でチュートリアルを拡張して別のデータ文字列やエラー訂正レベルなどのバリエーションを扱う場合に有用です。

## 手順 5: 生成されたバーコードを確認する

作成した 2 つの PNG ファイルを開きます。以下が表示されるはずです：

- **DatabarCols4.png** – 4 本の垂直列で構成された、より幅の広いバーコード。  
- **DatabarRows3.png** – 3 本の水平行で構成された、より高いバーコード。

両方の画像は同じテキスト（`"Databar Expanded Stacked long"`）をエンコードしていますが、視覚的構造は異なります。標準的な DataBar スキャナーまたは DataBar をサポートするモバイルアプリでスキャンし、正しくデコードできることを確認してください。

## よくある落とし穴とプロのコツ

| Issue | Why it happens | How to avoid it |
|-------|----------------|-----------------|
| **フォルダー パスが正しくない** | `Save` はディレクトリが存在しない場合に `DirectoryNotFoundException` をスローします。 | `Save` を呼び出す前に `Directory.CreateDirectory(Path.GetDirectoryName(outputPath))` を使用します。 |
| **列/行が多すぎる** | DataBar の仕様では列は最大 4、行は最大 3 に制限されています。 | 許容範囲内に収めてください。範囲外の場合、Aspose.Barcode は `ArgumentOutOfRangeException` をスローします。 |
| **読み取りにくいバーコード** | 画像解像度が低いとバーコードがぼやけます。 | 高品質が必要な場合は `barcodeGenerator.Parameters.ImageResolution` で DPI を上げてください（例: 300 dpi）。 |
| **データ形式が間違っている** | DataBar は特定のモードで最大 13 桁の数値文字列のみ受け付けます。 | ジェネレータに渡す前に入力文字列を検証してください。 |

## 例の拡張

カスタム列と行で **databar stacked barcode** を作成できるようになったので、以下の項目を試したくなるでしょう：

- **前景/背景色の変更**（`barcodeGenerator.Parameters.Barcode.Color = Color.Blue;`）。  
- **クワイエットゾーンの追加**（`barcodeGenerator.Parameters.Barcode.Qz = 2;`）。  
- **SVG へのエクスポート**（解像度に依存しない描画のため、`BarCodeImageFormat.Svg`）。

これらのオプションはすべて、[Aspose.Barcode for .NET API リファレンス](https://docs.aspose.com/barcode/net/) に記載されています。

## 完全なソースコード

以下は、上記のすべての手順を組み込んだ完全な実行可能プログラムです。`Program.cs` に貼り付け、`YOUR_DIRECTORY` を実際のパスに置き換えて、`dotnet run` を実行してください。

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;
using System;
using System.IO;

class Program
{
    static void Main()
    {
        // Ensure the output directory exists
        string outputDir = @"YOUR_DIRECTORY";
        Directory.CreateDirectory(outputDir);

        // -------------------------------------------------
        // Step 1: Generator for 4‑column stacked barcode
        // -------------------------------------------------
        BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
            EncodeTypes.DatabarExpandedStacked,
            "Databar Expanded Stacked long");

        // Set 4 columns (default rows = 2)
        barcodeGenerator.Parameters.Barcode.DataBar.Columns = 4;

        string colsPath = Path.Combine(outputDir, "DatabarCols4.png");
        barcodeGenerator.Save(colsPath, BarCodeImageFormat.Png);
        Console.WriteLine($"Saved 4‑column barcode to {colsPath}");

        // -------------------------------------------------
        // Step 2: Generator for 3‑row stacked barcode
        // -------------------------------------------------
        BarcodeGenerator barcodeGeneratorRows = new BarcodeGenerator(
            EncodeTypes.DatabarExpandedStacked,
            "Databar Expanded Stacked long");

        // Set 3 rows (default columns = 2)
        barcodeGeneratorRows.Parameters.Barcode.DataBar.Rows = 3;

        string rowsPath = Path.Combine(outputDir, "DatabarRows3.png");
        barcodeGeneratorRows.Save(rowsPath, BarCodeImageFormat.Png);
        Console.WriteLine($"Saved 3‑row barcode to {rowsPath}");
    }
}
```

プログラムを実行すると、**barcode columns** と **barcode rows** が **Databar Expanded Stacked** シンボルの視覚的レイアウトにどのように影響するかを示す 2 つの PNG ファイルが生成されます。

## 結論

これで、Aspose.Barcode for .NET を使用して C# で **databar stacked barcode** を作成する方法が分かりました。`Columns` と `Rows` プロパティを調整することで、さまざまなスペース制約に合わせたバーコードをデータの完全性を保ったまま生成できます。この例はプロジェクトのセットアップからトラブルシューティングまで網羅しており、より高度なバーコードシナリオに取り組むための確固たる基盤を提供します。

**次のステップ:**  
- 異なるデータ文字列で実験し、列/行の制限が可読性に与える影響を確認する。  
- このコードを Web API と組み合わせて、オンデマンドでバーコードを生成する。  
- 同じ `BarcodeGenerator` パターンを使用して、他のシンボロジー（例: QR、Code128）を探求する。

コーディングを楽しんで、スキャンが常に成功しますように！

## 次に学ぶべきことは？

以下のチュートリアルは、本ガイドで示した手法を基にした密接に関連するトピックを取り上げています。各リソースには、ステップバイステップの解説と完全な動作コード例が含まれており、追加の API 機能を習得し、独自プロジェクトで代替実装アプローチを検討するのに役立ちます。

- [バーコードジェネレータ C# – DataBar Expanded Stacked 画像の作成](/barcode/english/python-java/general/barcode-generator-c-create-databar-expanded-stacked-images/)
- [databar expanded stacked バーコードガイド – C# での生成とサイズ設定方法](/barcode/english/python-java/general/databar-expanded-stacked-barcode-guide-how-to-generate-and-s/)
- [.NET API を使用した Aspose.BarCode Databar バーコード生成 – 行と列の設定](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-row-column-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}