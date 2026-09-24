---
category: general
date: 2026-08-15
description: C#でバーコード画像PNG – 郵便バーコードの生成方法、Planetバーコードの作成方法、シンプルなジェネレータでバーコードの高さを変更する方法を学びましょう。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- barcode image png
- barcode generator c#
- generate postal barcode
- create planet barcode
- change barcode height
language: ja
lastmod: 2026-08-15
og_description: C# のチュートリアル「Barcode image PNG」では、郵便バーコードの生成、Planet バーコードの作成、そして BarcodeGenerator
  API を使用したバーコードの高さ変更方法を紹介しています。
og_image_alt: Screenshot of generated PNG barcode with custom height using C# BarcodeGenerator
og_title: C#でバーコード画像PNGを生成・調整
schemas:
- author: Aspose
  dateModified: '2026-08-15'
  description: Barcode image PNG in C# – learn how to generate postal barcodes, create
    a Planet barcode, and change barcode height with a simple generator.
  headline: Barcode image PNG in C# generate barcodes, change height
  type: TechArticle
tags:
- barcode
- C#
- PNG
- postal
- generator
title: C#でバーコード画像PNGを生成し、バーコードの高さを変更
url: /ja/python-java/general/barcode-image-png-in-c-generate-barcodes-change-height/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# C# でのバーコード画像 PNG – バーコード生成と高さ変更

C# で **barcode image PNG** が必要な場合、このガイドはプロセス全体を順を追って説明します。郵便バーコードの生成方法、Planet バーコードの作成方法、IDE を離れずにバーコードの高さを変更する方法を学べます。

信頼性の高い PNG バーコードの生成は、出荷ラベル、在庫システム、そして自動郵送ソリューションで一般的な要件です。このチュートリアルの最後までに、Planet と RM4SCC の両フォーマット向けに高品質な PNG ファイルを生成する再利用可能なコードスニペットを手に入れ、郵便規格に合わせてバーの高さを調整する方法を理解できるようになります。

## 必要なもの

- .NET 6+ または .NET Framework 4.7.2（BarcodeGenerator API は最新の .NET ランタイムで動作します）  
- **Aspose.BarCode for .NET** NuGet パッケージへの参照（または `BarcodeGenerator`、`EncodeTypes`、`BarCodeImageFormat` を提供する互換ライブラリ）  
- C# の構文とファイル I/O に関する基本的な知識  

追加ツールは不要です。コードは Visual Studio、Rider、または `dotnet` CLI で実行できます。

## Barcode image PNG – 基本生成

最初のステップは、デフォルトの寸法で **barcode image PNG** を作成することです。これにより、後でカスタマイズできるベースラインファイルが確立されます。

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

// Define the output folder (replace with your own path)
string outputFolder = @"C:\Barcodes";

// Ensure the folder exists
Directory.CreateDirectory(outputFolder);

// 1️⃣ Create a Planet barcode generator with default height
BarcodeGenerator planetGenerator = new BarcodeGenerator(EncodeTypes.Planet, "123456");

// Set the module width (X‑dimension) to 4 pixels – this defines the thin bar size
planetGenerator.Parameters.Barcode.XDimension.Pixels = 4;

// Save the image as PNG; this is the first **barcode image PNG** you’ll produce
planetGenerator.Save(Path.Combine(outputFolder, "PlanetBarHeightDefault.png"),
                     BarCodeImageFormat.Png);
```

**このコードが機能する理由:**  
- `EncodeTypes.Planet` はジェネレータに Planet シンボルを使用させます。これは多くの郵便サービスで必須です。  
- `XDimension.Pixels` は最小バーの幅を制御し、4 px の値は一般的なラベルサイズで読み取り可能なバーコードを生成します。  
- `Save` メソッドは **barcode image PNG** ファイルをディスクに書き込み、ベクタ情報をラスタピクセルとして保存します。

## バーコードの高さ変更 – 視覚的ウェイトのカスタマイズ

郵便ガイドラインでは特定のバー高さが求められることがあります。以下のスニペットは、同じ Planet バーコードに対してカスタム 100 ピクセルの高さを設定する方法を示します。

```csharp
// 2️⃣ Apply a custom 100‑pixel bar height
planetGenerator.Parameters.Barcode.BarHeight.Pixels = 100;

// Overwrite or save as a new file to keep both versions
planetGenerator.Save(Path.Combine(outputFolder, "PlanetBarHeight100.png"),
                     BarCodeImageFormat.Png);
```

**高さを変更する理由:**  
- 高いバーは低解像度プリンターでのスキャン信頼性を向上させ、短いバーはラベルのスペースを節約します。  
- `BarHeight.Pixels` プロパティを使用すると、X‑dimension に影響を与えずにこの属性を微調整できます。

## 郵便バーコードの生成 – RM4SCC の例を作成

RM4SCC フォーマットはイギリスで使用されるもう一つの一般的な郵便バーコードです。生成手順は Planet の例と同様で、**barcode generator c#** パターンを強化します。

```csharp
// 3️⃣ Create an RM4SCC barcode generator with default height
BarcodeGenerator rm4sccGenerator = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");

// Keep the same module width for consistency
rm4sccGenerator.Parameters.Barcode.XDimension.Pixels = 4;

// Save the default‑height PNG
rm4sccGenerator.Save(Path.Combine(outputFolder, "RM4SCCBarHeightDefault.png"),
                     BarCodeImageFormat.Png);
```

## バーコードの高さ変更 – RM4SCC バリエーション

Planet バーコードと同様に、RM4SCC のバー高さも調整できます。以下のコードは高さを 100 px に設定し、同じデータ文字列で 2 番目の **barcode image PNG** を生成します。

```csharp
// 4️⃣ Set a custom 100‑pixel bar height for RM4SCC
rm4sccGenerator.Parameters.Barcode.BarHeight.Pixels = 100;

// Save the customized PNG
rm4sccGenerator.Save(Path.Combine(outputFolder, "RM4SCCBarHeight100.png"),
                     BarCodeImageFormat.Png);
```

## 完全な実行可能サンプル

すべての手順を組み合わせると、4 つの PNG ファイルを作成する単一の自己完結型プログラムが完成します:

```csharp
using System;
using System.IO;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        string outputFolder = @"C:\Barcodes";
        Directory.CreateDirectory(outputFolder);

        // Planet barcode – default height
        var planet = new BarcodeGenerator(EncodeTypes.Planet, "123456");
        planet.Parameters.Barcode.XDimension.Pixels = 4;
        planet.Save(Path.Combine(outputFolder, "PlanetBarHeightDefault.png"),
                    BarCodeImageFormat.Png);

        // Planet barcode – custom 100‑pixel height
        planet.Parameters.Barcode.BarHeight.Pixels = 100;
        planet.Save(Path.Combine(outputFolder, "PlanetBarHeight100.png"),
                    BarCodeImageFormat.Png);

        // RM4SCC barcode – default height
        var rm4scc = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");
        rm4scc.Parameters.Barcode.XDimension.Pixels = 4;
        rm4scc.Save(Path.Combine(outputFolder, "RM4SCCBarHeightDefault.png"),
                    BarCodeImageFormat.Png);

        // RM4SCC barcode – custom 100‑pixel height
        rm4scc.Parameters.Barcode.BarHeight.Pixels = 100;
        rm4scc.Save(Path.Combine(outputFolder, "RM4SCCBarHeight100.png"),
                    BarCodeImageFormat.Png);

        Console.WriteLine("All barcode PNG files have been generated in " +


## 次に学ぶべきことは？

以下のチュートリアルは、本ガイドで示したテクニックを基にした密接に関連するトピックを扱っています。各リソースには、ステップバイステップの解説と完全な動作コード例が含まれており、追加の API 機能を習得したり、独自プロジェクトで代替実装アプローチを探求したりするのに役立ちます。

- [バーコード カスタム高さの作成 – 1 次元バーコード](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-barcode-height-adjustment/)
- [バーコード PNG の作成 – DataMatrix アスペクト比 – Aspose.BarCode](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-aspect-ratio-customization/)
- [バーコード画像 C# の作成 – GS1 DataMatrix の例](/barcode/english/net/gs1-barcode-encoding/gs1-datamatrix-example/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}