---
category: general
date: 2026-10-05
description: C# のバーコードジェネレータ例で、プラネットバーコードの生成方法とバーコード画像の作成方法を示します。ステップバイステップのガイドに従ってください。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- barcode generator example
- generate planet barcode
- create barcode image c#
language: ja
lastmod: 2026-10-05
og_description: C# のバーコードジェネレータ例では、プラネットバーコードの生成方法とバーコード画像の作成方法を順を追って説明します。完全な実行可能なソリューションを入手できます。
og_image_alt: Screenshot of a generated Planet barcode image created by a C# barcode
  generator example
og_title: C#でのバーコードジェネレーター例 – Planetバーコードをすばやく生成
schemas:
- author: Aspose
  dateModified: '2026-10-05'
  description: barcode generator example in C# that shows you how to generate planet
    barcode and create barcode image c#. Follow this step‑by‑step guide.
  headline: How to build a barcode generator example in C# with Planet symbology
  type: TechArticle
tags:
- barcode
- C#
- Aspose.BarCode
title: C# と Planet シンボロジーでバーコードジェネレータのサンプルを作成する方法
url: /ja/python-java/general/how-to-build-a-barcode-generator-example-in-c-with-planet-sy/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# C# のバーコードジェネレータ例 – Planet バーコードを生成しバーコード画像を作成

C# で **barcode generator example** が必要な場合、このガイドでは数行のコードだけで Planet バーコードを生成し、バーコード画像を作成する方法を正確に示します。任意の .NET プロジェクトに組み込める、完全で実行可能なソリューションをご覧いただけます。

Planet バーコードは郵便サービスでルーティング情報を符号化するために使用されます。このチュートリアルの最後までに、ライブラリがバーコードの高さを自動的に決定する理由、X 次元の制御方法、結果を PNG ファイルとして保存する方法が理解できるようになります。外部ツールは不要で、Aspose.BarCode for .NET パッケージと .NET 開発環境だけで完結します。

## 前提条件

* .NET 6.0 SDK 以降がインストールされていること  
* Visual Studio 2022（または .NET をサポートする任意の IDE）  
* **Aspose.BarCode for .NET** NuGet パッケージ（`Aspose.BarCode`）  

コマンドラインからパッケージをインストールできます：

```bash
dotnet add package Aspose.BarCode
```

## ステップ 1: Planet エンコード用にバーコードジェネレータを初期化する

任意の **barcode generator example** の最初のステップは、`BarcodeGenerator` インスタンスを作成し、エンコードタイプを指定することです。Planet バーコードの場合は `EncodeTypes.Planet` を使用し、エンコードしたいデータ文字列を渡します。

```csharp
using Aspose.BarCode.Generation;

// Create a Planet barcode generator with the data to encode
BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Planet, "123456");
```

**重要な理由:** `EncodeTypes.Planet` 列挙体は、ライブラリに Planet シンボロジーを使用するよう指示します。このシンボロジーは郵便規格で要求される固定モジュールパターンを持ちます。データ（この例では `"123456"`）を提供することで、バーコードに正しい数値ルーティングコードが含まれることが保証されます。

## ステップ 2: X 次元（モジュール幅）をピクセル単位で設定する

X 次元は各モジュール（最小のバー）の幅を制御します。これを調整することで、可読性に影響を与えることなくバーコード全体のサイズを変更できます。

```csharp
// Set the X dimension (module width) to 4 pixels
generator.Parameters.Barcode.XDimension.Pixels = 4;
```

**重要な理由:** X 次元を大きくするとバーコードが大きくなり、大きな封筒に印刷する際に便利です。ライブラリは Planet バーコードの正しいアスペクト比を保つように高さを自動的にスケーリングします。

## ステップ 3: バーコード画像をディスクに保存する

最後に、生成した画像を保存します。ライブラリが最適な高さを決定するため、出力パスとフォーマットだけを指定すれば済みます。

```csharp
using Aspose.BarCode;

// Define the output file path
string outputFile = @"C:\Barcodes\PlanetAutoHeight.png";

// Save the barcode as a PNG image
generator.Save(outputFile, BarCodeImageFormat.Png);
```

**重要な理由:** PNG で保存するとバーコードの鮮明なエッジが保たれ、信頼性の高いスキャンに不可欠です。`Save` メソッドは、別の出力が必要な場合に JPEG、BMP、TIFF など他のフォーマットもサポートしています。

### 期待される出力

コードを実行すると、`C:\Barcodes` に **PlanetAutoHeight.png** という名前のファイルが作成されます。画像は以下のイラストに似たものになります（代替テキスト: *barcode generator example showing a Planet barcode*）。

![C# の例で生成された Planet バーコード](/images/planet-barcode-example.png){alt="Planet バーコードを示すバーコードジェネレータ例"}

## ステップ 4: オプション – 前景色と背景色をカスタマイズする

アプリケーションで別のビジュアルスタイルが必要な場合、保存前にバーコードの色を変更できます。

```csharp
// Set foreground (bars) to dark blue and background to light gray
generator.Parameters.Barcode.BarColor = System.Drawing.Color.DarkBlue;
generator.Parameters.Barcode.BackgroundColor = System.Drawing.Color.LightGray;

// Save the customized image
generator.Save(@"C:\Barcodes\PlanetCustomColors.png", BarCodeImageFormat.Png);
```

**ヒント:** カスタマイズしたバーコードは必ず実際のスキャナでテストし、色の変更が可読性に影響しないことを確認してください。

## ステップ 5: エラー処理とバリデーション

データが Planet シンボロジーの要件（例: 数字以外の文字）を満たさない場合、Aspose.BarCode ライブラリは `ArgumentException` をスローします。生成コードを try‑catch ブロックで囲み、明確なフィードバックを提供しましょう。

```csharp
try
{
    BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Planet, "ABC123");
    generator.Save(@"C:\Barcodes\InvalidPlanet.png", BarCodeImageFormat.Png);
}
catch (ArgumentException ex)
{
    Console.WriteLine($"Invalid data for Planet barcode: {ex.Message}");
}
```

**重要な理由:** Planet バーコードは特定の長さの数値データのみ受け付けます。適切なバリデーションにより、実行時エラーを防ぎ、統合テスト時の時間を節約できます。

## 完全な実行可能サンプル

すべてのステップを組み合わせると、コピーして貼り付け、実行できる自己完結型プログラムが得られます。

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        // Step 1: Initialize the generator with Planet encoding
        BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Planet, "123456");

        // Step 2: Set the X dimension (module width) to 4 pixels
        generator.Parameters.Barcode.XDimension.Pixels = 4;

        // Optional: customize colors (comment out if not needed)
        // generator.Parameters.Barcode.BarColor = System.Drawing.Color.DarkBlue;
        // generator.Parameters.Barcode.BackgroundColor = System.Drawing.Color.LightGray;

        // Step 3: Save the barcode image
        string outputFile = @"C:\Barcodes\PlanetAutoHeight.png";
        generator.Save(outputFile, BarCodeImageFormat.Png);

        Console.WriteLine($"Planet barcode saved to {outputFile}");
    }
}
```

プログラムをコンパイルして実行します：

```bash
dotnet run
```

コンソールにファイルの場所を示すメッセージが表示され、PNG ファイルに生成された Planet バーコードが含まれているはずです。

## 一般的なバリエーションとエッジケース

| バリエーション | 実装方法 | 使用する場面 |
|-----------|------------------|------------|
| **データ長が異なる場合** | `new BarcodeGenerator(EncodeTypes.Planet, "987654321")` の第2引数を変更する | 長いルーティング番号が必要な郵便サービス |
| **高解像度** | `Save` の前に `generator.Parameters.ImageResolution = 300;` を設定する | 高 DPI プリンタでの印刷 |
| **画像フォーマットが異なる場合** | `BarCodeImageFormat.Jpeg` または `BarCodeImageFormat.Tiff` を使用する | PNG がワークフローに適さない場合 |
| **動的ファイル名** | `string outputFile = Path.Combine(folder, $"Planet_{DateTime.Now:yyyyMMdd_HHmmss}.png");` | 複数のバーコードをバッチ処理する場合 |

## 堅牢なバーコードジェネレータ例のためのプロのコツ

* **ジェネレータインスタンスを再利用** すると、同じ設定で多数のバーコードを作成する際に、`EncodeTypes` またはデータ文字列だけを変更してパフォーマンスを向上させられます。  
* **入力をバリデート** する前に `BarcodeGenerator` に渡します。`^\d{6,9}$` のようなシンプルな正規表現でデータが Planet の要件に合致していることを確認できます。  
* **リソースを解放** してください。長時間稼働するサービスで数千枚の画像を生成する場合は、`BarcodeGenerator` は `IDisposable` を実装しているため、適切な場合は `using` ブロックで囲みます。

```csharp
using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Planet, data))
{
    // configure and save...
}
```

## 結論

この **barcode generator example** は、Aspose.BarCode for .NET を使用して **Planet バーコードを生成** し、**C# でバーコード画像を作成** する方法を示しています。ジェネレータの初期化、X 次元の設定、オプションでの色カスタマイズ、バリデーションエラーの処理、PNG ファイルへの保存方法を学びました。完全なソースコードが提供されているので、Planet バーコード生成を任意の C# アプリケーションにすぐに組み込むことができます。

次に、QR、Code128、DataMatrix などの他のシンボロジーを調査するとよいでしょう。いずれも `BarcodeGenerator` の作成、パラメータ設定、`Save` の呼び出しという同じパターンに従います。これらの原則は共通で、さまざまなビジネスシナリオでバーコード生成機能を簡単に拡張できます。コーディングを楽しんでください！

## 次に学ぶべきことは？

- [Planet バーコード画像作成 – ステップバイステップガイド](/barcode/english/python-java/general/create-planet-barcode-image-step-by-step-guide/)
- [Barcode generator C# – Planet バーコードと RM4SCC の例作成](/barcode/english/python-java/general/barcode-generator-c-create-planet-barcode-and-rm4scc-example/)
- [C# でバーコード画像を作成 – barcode generator example](/barcode/english/python-java/general/create-barcode-image-c-with-barcode-generator-example/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}