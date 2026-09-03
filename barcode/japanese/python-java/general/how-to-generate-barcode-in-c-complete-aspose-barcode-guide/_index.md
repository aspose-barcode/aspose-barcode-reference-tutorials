---
category: general
date: 2026-07-21
description: Aspose.BarCode for C# を使用してバーコードを素早く生成する方法。Asposeでバーコードを作成し、アスペクト比を調整し、数分で
  PNG として保存する方法を学びましょう。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to generate barcode
- create barcode with aspose
- Aspose.BarCode example
- DataBar stacked omnidirectional
- barcode aspect ratio C#
language: ja
lastmod: 2026-07-21
og_description: Aspose.BarCode for C# を使用したバーコードの生成方法。このステップバイステップガイドでは、Asposeでバーコードを作成し、設定を調整し、画像をエクスポートする方法を示します。
og_image_alt: Screenshot of generated DataBar barcode showing different aspect ratios
og_title: C#でバーコードを生成する方法 – 高速 Aspose.BarCode チュートリアル
schemas:
- author: Aspose
  dateModified: '2026-07-21'
  description: How to generate barcode quickly using Aspose.BarCode for C#. Learn
    to create barcode with Aspose, adjust aspect ratios, and save PNGs in minutes.
  headline: How to Generate Barcode in C# – Complete Aspose.BarCode Guide
  type: TechArticle
tags:
- barcode
- Aspose
- C#
- DataBar
title: C#でバーコードを生成する方法 – 完全なAspose.BarCodeガイド
url: /ja/python-java/general/how-to-generate-barcode-in-c-complete-aspose-barcode-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# C# でバーコードを生成する方法 – 完全 Aspose.BarCode ガイド

.NET アプリで低レベルの画像コードに悩まされずに **バーコードを生成する方法** を知りたくありませんか？ あなたは一人ではありません。多くのエンタープライズプロジェクトで、請求書、出荷ラベル、在庫管理のために **Aspose を使ってバーコードを作成** する必要があり、ライブラリは驚くほど手軽です。

このチュートリアルでは、DataBar Stacked Omnidirectional バーコードを作成し、アスペクト比を調整し、2 つの PNG ファイルとして保存する実践的な例を順に解説します。最後まで読めば、すぐに実行できるコンソール プログラムと、制御可能な主要プロパティの明確な理解が得られます。

## 学べること

- C# プロジェクトへの Aspose.BarCode の導入方法（NuGet、ライセンスの基本）
- **DataBar stacked omnidirectional** ジェネレータの初期化
- X‑dimension（ピクセルサイズ）とアスペクト比の調整
- バーコードを PNG 画像として保存
- 他のバーコードタイプや出力形式への拡張例

Aspose の事前知識は不要です。.NET 6（以降）SDK とお好みの IDE があれば始められます。

## 前提条件

| 要件 | 理由 |
|------|------|
| .NET 6 SDK 以上 | 最新の言語機能と簡単なプロジェクト作成 |
| Visual Studio 2022（または VS Code） | ビルドとデバッグ用 IDE |
| Aspose.BarCode for .NET NuGet パッケージ | 重厚な処理を担うコア ライブラリ |
| 有効な Aspose ライセンス（または評価版） | 評価ウォーターマークの除去とフル機能の解放 |

まだ NuGet パッケージをインストールしていない場合は、次を実行してください。

```bash
dotnet add package Aspose.BarCode
```

準備が整ったので、コードに入りましょう。

## 手順 1: 新しいコンソール プロジェクトを作成

まず、フレッシュなコンソール アプリを作ります。ターミナルで次を入力してください。

```bash
dotnet new console -n BarcodeDemo
cd BarcodeDemo
```

これで `Program.cs` と `.csproj` が生成されます。エディタでプロジェクトを開き、上記のように Aspose 参照を追加します。

## 手順 2: BarcodeGenerator の初期化

処理の中心は `BarcodeGenerator` クラスです。**DataBar stacked omnidirectional** シンボルを指定し、サンプルの GS1‑128 文字列を渡します。

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;
using System;

class Program
{
    static void Main()
    {
        // Step 2.1: Choose the barcode type and data
        var generator = new BarcodeGenerator(
            EncodeTypes.DatabarStackedOmniDirectional,
            "(01)12345678901231"); // GS1-128 example

        // Step 2.2: Set the X‑dimension (pixel size) – controls overall size
        generator.Parameters.Barcode.XDimension.Pixels = 2;

        // Continue with aspect ratio adjustments...
        GenerateBarcodes(generator);
    }

    static void GenerateBarcodes(BarcodeGenerator generator)
    {
        // Placeholder for the rest of the steps
    }
}
```

**ポイント:** `EncodeTypes.DatabarStackedOmniDirectional` は小さなラベル向けのコンパクトで高密度なバーコードを生成します。データ文字列は GTIN‑14 値を示す GS1 アプリケーション識別子 `(01)` に従っており、多くのサプライチェーン システムで期待されます。

## 手順 3: アスペクト比を調整して画像を保存

Aspose.BarCode では `Parameters.Barcode.DataBar.AspectRatio` を使って DataBar シンボルの **アスペクト比** を調整できます。この値を変えると、幅と高さの比率が変わり、固定サイズラベルへの収まり具合が大きく変わります。

```csharp
static void GenerateBarcodes(BarcodeGenerator generator)
{
    string outputPath = "GeneratedBarcodes/"; // Ensure this folder exists
    System.IO.Directory.CreateDirectory(outputPath);

    // ---------- First image: Aspect Ratio 15 ----------
    generator.Parameters.Barcode.DataBar.AspectRatio = 15;
    string file15 = $"{outputPath}DatabarAspectRatio15.png";
    generator.Save(file15, BarCodeImageFormat.Png);
    Console.WriteLine($"Saved barcode with aspect ratio 15 to {file15}");

    // ---------- Second image: Aspect Ratio 30 ----------
    generator.Parameters.Barcode.DataBar.AspectRatio = 30;
    string file30 = $"{outputPath}DatabarAspectRatio30.png";
    generator.Save(file30, BarCodeImageFormat.Png);
    Console.WriteLine($"Saved barcode with aspect ratio 30 to {file30}");
}
```

**各行の説明**

- `outputPath` は PNG ファイルの出力先フォルダーを指します。`Directory.CreateDirectory` により、初回実行時でもフォルダーが確実に作成されます。
- `AspectRatio = 15` は比較的縦長のバーコード、`AspectRatio = 30` は横に伸びた形になります。
- `generator.Save(...)` がディスクに画像を書き込みます。`BarCodeImageFormat.Png` 列挙体によりロスレス品質が保証されます。
- `Console.WriteLine` はプログラム実行時に即座にフィードバックを提供します。

### 期待される出力

`dotnet run` を実行すると、次のような出力が表示されます。

```
Saved barcode with aspect ratio 15 to GeneratedBarcodes/DatabarAspectRatio15.png
Saved barcode with aspect ratio 30 to GeneratedBarcodes/DatabarAspectRatio30.png
```

2 つの PNG ファイルを横に並べて開くと、2 番目の画像が幅広くなっていることが分かりますが、高さは同じです。どちらも標準的なバーコードリーダーで読み取れます。

## 手順 4: 完全なサンプルを実行

コピー＆ペーストで使える **完全な実行可能ソース** を以下にまとめました。

```csharp
// Program.cs
using Aspose.BarCode.Generation;
using Aspose.BarCode;
using System;
using System.IO;

class Program
{
    static void Main()
    {
        // Initialise generator with DataBar stacked omnidirectional symbology
        var generator = new BarcodeGenerator(
            EncodeTypes.DatabarStackedOmniDirectional,
            "(01)12345678901231");

        // Set pixel size of the X‑dimension (controls overall size)
        generator.Parameters.Barcode.XDimension.Pixels = 2;

        // Generate two barcodes with different aspect ratios
        GenerateBarcodes(generator);
    }

    static void GenerateBarcodes(BarcodeGenerator generator)
    {
        string outputPath = "GeneratedBarcodes/";
        Directory.CreateDirectory(outputPath);

        // Aspect Ratio 15
        generator.Parameters.Barcode.DataBar.AspectRatio = 15;
        string file15 = Path.Combine(outputPath, "DatabarAspectRatio15.png");
        generator.Save(file15, BarCodeImageFormat.Png);
        Console.WriteLine($"Saved barcode with aspect ratio 15 to {file15}");

        // Aspect Ratio 30
        generator.Parameters.Barcode.DataBar.AspectRatio = 30;
        string file30 = Path.Combine(outputPath, "DatabarAspectRatio30.png");
        generator.Save(file30, BarCodeImageFormat.Png);
        Console.WriteLine($"Saved barcode with aspect ratio 30 to {file30}");
    }
}
```

コンパイルして実行:

```bash
dotnet run
```

これで `GeneratedBarcodes/` フォルダーに、完璧に描画された 2 つのバーコード PNG が生成されます。

## 手順 5: サンプルの拡張（任意）

**Aspose でバーコードを生成する方法** が分かったので、次は「他に何が調整できる？」と考えるかもしれません。以下はすぐに試せるアイデアです。

| プロパティ | 機能 | 主な利用シーン |
|------------|------|----------------|
| `generator.Parameters.Barcode.CodeTextParameters.Font.Size` | 人が読むテキストのサイズを変更 | ハンドヘルドスキャナ向けに大きめフォント |
| `generator.Parameters.Barcode.ImageFormat` | 出力形式の全体設定（PNG, JPEG, BMP など） | Web 向けに JPEG でサイズ削減 |
| `generator.Parameters.Barcode.Color` | 前景色を設定 | カラーでカテゴリ分け |
| `generator.Save(..., BarCodeImageFormat.Svg)` | 無限に拡大可能なベクタ出力 | 印刷用 PDF への組み込み |

各 `Save` 呼び出しの直前に対応する行を追加すれば、すぐに効果を確認できます。

## よくある落とし穴とプロのコツ

- **ライセンスの配置:** 有料ライセンスを使用する場合は、ジェネレータ作成前に `License license = new License(); license.SetLicense("Aspose.BarCode.lic");` を呼び出してください。これを忘れると画像にウォーターマークが入ります。
- **無効なデータ文字列:** DataBar シンボルは数値の GS1 データを前提とします。アルファベット文字を渡すと `ArgumentException` がスローされます。
- **スレッド安全性:** `BarcodeGenerator` インスタンスは **スレッドセーフではありません**。並列生成する場合はスレッドごとに新しいインスタンスを作成してください。
- **画像サイズとスキャナの性能:** `XDimension.Pixels` を過度に大きくすると、画像が巨大化し一部スキャナが読み取りにくくなることがあります。対象ハードウェアで必ずテストしてください。

## 結論

本稿では、Aspose.BarCode を使って C# で **バーコードを生成する方法** を、プロジェクトのセットアップから異なるアスペクト比で 2 枚の画像を保存するまで解説しました。ジェネレータの初期化、X‑dimension とアスペクト比の設定、`Save` の呼び出しという基本フローは、Aspose がサポートするすべてのバーコードタイプに応用できます。

これで請求書、出荷ラベル、在庫タグ向けに **Aspose でバーコードを作成** でき、カラー、カスタムフォント、SVG 出力といった高度な機能にも挑戦できる土台が整いました。コードを自由に調整し、他の `EncodeTypes` を試したり、既存サービスに組み込んでみてください。

質問や特定のバーコードスタイルのリクエストがあれば、下のコメントで教えてください。Happy coding!

## 次に学ぶべきこと

以下のチュートリアルは、本ガイドで示した手法を応用した関連トピックを扱っています。各リソースは完全なコード例とステップバイステップの解説を含み、API の追加機能や代替実装アプローチをマスターするのに役立ちます。

- [Aspose.BarCode for .NET でカスタムアスペクト比を持つ Aztec バーコードを生成する方法](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)
- [Aspose.BarCode for .NET で Codablock F のアスペクト比をカスタマイズする方法](/barcode/english/net/codablock-f-encoding/codablock-f-aspect-ratio-customization/)
- [Aspose.BarCode for .NET で DataMatrix バーコード (ECC 200) を生成する方法](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-ecc-200-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}