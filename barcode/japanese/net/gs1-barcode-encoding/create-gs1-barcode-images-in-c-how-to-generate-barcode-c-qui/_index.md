---
category: general
date: 2026-07-18
description: Aspose.BarCode を使用して C# で GS1 バーコード画像を作成するステップバイステップのガイドです – 無駄な説明は省き、動作するコードだけを提供します。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create gs1 barcode images
- how to generate barcode c#
language: ja
lastmod: 2026-07-18
og_description: この簡潔なチュートリアルでC#を使ってGS1バーコード画像を作成しましょう。Aspose.BarCodeを利用してC#でバーコードを生成し、数秒でPNGファイルとして保存する方法を学べます。
og_image_alt: Screenshot of a generated GS1‑MicroPDF417 barcode saved as a PNG file
og_title: C#でGS1バーコード画像を作成する – 完全ハウツーガイド
schemas:
- author: Aspose
  dateModified: '2026-07-18'
  description: Create GS1 barcode images in C# with this step‑by‑step guide on how
    to generate barcode C# using Aspose.BarCode – no fluff, just working code.
  headline: Create GS1 Barcode Images in C# – How to Generate Barcode C# Quickly
  type: TechArticle
tags:
- barcode
- csharp
- gs1
- aspose
title: C#でGS1バーコード画像を作成 – バーコードをC#で素早く生成する方法
url: /ja/net/gs1-barcode-encoding/create-gs1-barcode-images-in-c-how-to-generate-barcode-c-qui/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# C#でGS1バーコード画像を作成 – バーコードC#の生成方法

Ever needed to **gs1バーコード画像を作成** for a packing label but weren’t sure where to start? You’re not alone. In this tutorial you’ll see exactly **バーコードC#の生成方法** code that produces GS1‑MicroPDF417 images in a matter of minutes.

We’ll walk through the whole process—installing the library, configuring the generator, swapping AI (Application Identifier) data, and finally saving a set of PNG files. By the end you’ll have a ready‑to‑run console app that spits out a handful of GS1 barcode images, each reflecting a different AI combination.

---

## 必要なもの

- **.NET 6+**（or .NET Framework 4.6+）。The latest runtime works best with Aspose.BarCode.
- **Aspose.BarCode for .NET** – install via NuGet (`Install-Package Aspose.BarCode`).
- A folder on disk where the PNG files will be written (we’ll call it `YOUR_DIRECTORY`).
- A basic understanding of C# syntax—nothing fancy required.

If you already have those, great. If not, grab the NuGet package first; it’s a single line in the Package Manager Console and takes care of all dependencies.

## 手順 1: 最小限のコンソールプロジェクトを設定

Open your favorite IDE (Visual Studio, Rider, or VS Code) and create a new console project:

```bash
dotnet new console -n Gs1BarcodeDemo
cd Gs1BarcodeDemo
dotnet add package Aspose.BarCode
```

Replace the auto‑generated `Program.cs` with the code shown in the next steps. This skeleton gives us a clean slate to **gs1バーコード画像を作成** without extra clutter.

## 手順 2: gs1バーコード画像の作成方法 – ジェネレータの初期化

The heart of the operation is `BarcodeGenerator`. We’ll start it with an initial GS1‑MicroPDF417 value, for example `(17)991231(10)ABCD`. That string encodes two AIs: expiration date (17) and batch/lot (10).

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        // Initialize the generator with a GS1‑MicroPDF417 barcode type
        BarcodeGenerator barcodeGen = new BarcodeGenerator(
            EncodeTypes.GS1MicroPdf417,
            "(17)991231(10)ABCD");
```

**この重要性:** The `EncodeTypes.GS1MicroPdf417` tells Aspose we’re dealing with a compact, high‑density GS1 format. Starting with a valid AI string ensures the first PNG we save already complies with GS1 standards.

## 手順 3: ビジュアルパラメータの調整 – サイズとレイアウトの微調整

A barcode that’s too tiny or oddly shaped won’t scan. Here we set the X‑dimension (module width) to 2 pixels, limit the number of columns to keep the image narrow, and enable linking so multiple barcodes can be concatenated later if needed.

```csharp
        // Set visual parameters for a crisp, scannable image
        barcodeGen.Parameters.Barcode.XDimension.Pixels = 2;      // module width
        barcodeGen.Parameters.Barcode.Pdf417.Columns = 2;        // column count
        barcodeGen.Parameters.Barcode.Pdf417.IsLinked = true;   // enable linking
```

**ヒント:** If you need a taller barcode, increase `Rows` instead of columns. Play with `XDimension` to meet the 0.33 mm minimum module size required by most scanners.

## 手順 4: 最初のバーコードを保存 – AI 17 + AI 10

Now we actually write the image to disk. The file name reflects the AIs used, making it easy to locate later.

```csharp
        // Save the first image (AI 17 + AI 10)
        barcodeGen.Save(@"YOUR_DIRECTORY\GS1MicroPdf417_17_10.png",
                        BarCodeImageFormat.Png);
```

After running the program, you should see a crisp PNG in `YOUR_DIRECTORY`. Open it—you’ll spot the tiny bars and the human‑readable text underneath. That’s the first of many **gs1バーコード画像** we’ll generate.

## 手順 5: エンコードデータの変更 – 同じジェネレータを再利用

Instead of creating a new `BarcodeGenerator` for each AI pair, we simply swap the `CodeText` property and call `Save` again. This approach is the most efficient way to **gs1バーコード画像を作成** in bulk.

```csharp
        // AI 15 (best before) + AI 10 (batch)
        barcodeGen.CodeText = "(15)991231(10)ABCD";
        barcodeGen.Save(@"YOUR_DIRECTORY\GS1MicroPdf417_15_10.png",
                        BarCodeImageFormat.Png);

        // AI 13 (production date) + AI 21 (serial)
        barcodeGen.CodeText = "(13)991231(21)ABCD";
        barcodeGen.Save(@"YOUR_DIRECTORY\GS1MicroPdf417_13_21.png",
                        BarCodeImageFormat.Png);

        // AI 11 (manufacture date) + AI 21 (serial)
        barcodeGen.CodeText = "(11)991231(21)ABCD";
        barcodeGen.Save(@"YOUR_DIRECTORY\GS1MicroPdf417_11_21.png",
                        BarCodeImageFormat.Png);

        // Only AI 17 (expiration) – no batch number
        barcodeGen.CodeText = "(17)991231";
        barcodeGen.Save(@"YOUR_DIRECTORY\GS1MicroPdf417_17.png",
                        BarCodeImageFormat.Png);
```

**なぜ再利用するのか？** Changing `CodeText` avoids the overhead of re‑instantiating the generator and guarantees consistent visual settings across all images.

## 手順 6: 実行、検証、調整

Compile and run:

```bash
dotnet run
```

You should now have five PNG files, each named after the AI pair it contains. Open any of them with an image viewer; you’ll see the barcode and the encoded text beneath. To double‑check that the data is correct, use a free GS1 scanner app on your phone—point it at the PNG on your screen and watch the AI values pop up.

**よくある落とし穴と回避方法**

| 問題 | 原因 | 対策 |
|-------|-------|-----|
| バーコードが読めない | `XDimension` が低すぎる（例: 1 ピクセル） | 2 または 3 ピクセルに上げる |
| AI の括弧が欠落 | `CodeText` の形式が正しくない | 常に各 AI を丸括弧で囲む |
| 画像が大きすぎる | 列/行が多すぎる | `Columns` を減らすか、Aspose に自動サイズさせる |
| ランタイムエラー `EncodeTypes` が見つからない | `using Aspose.BarCode.Generation` が不足 | 不足している `using` ディレクティブを追加 |

## 手順 7: サンプルの拡張 – さらに多くの AI 組み合わせを生成

If you need to **gs1バーコード画像を作成** for dozens of product variants, consider loading AI pairs from a CSV file:

```csharp
using System.IO;

string[] lines = File.ReadAllLines(@"ai_pairs.csv"); // format: "(17)991231,(10)ABCD"
foreach (var line in lines)
{
    barcodeGen.CodeText = line.Replace(',', ' ');
    string fileName = $"GS1MicroPdf417_{line.Replace("(", "").Replace(")", "").Replace(",", "_")}.png";
    barcodeGen.Save(Path.Combine(@"YOUR_DIRECTORY", fileName), BarCodeImageFormat.Png);
}
```

This tiny loop reads each line, swaps the data, and saves a PNG with a descriptive name—perfect for large‑scale label printing pipelines.

## 結論

You now have a complete, ready‑to‑run C# program that **gs1バーコード画像を作成** for multiple AI scenarios, demonstrating the most straightforward way to **バーコードC#の生成方法** using Aspose.BarCode. By reusing a single `BarcodeGenerator` instance, tweaking visual parameters, and swapping `CodeText`, you can churn out as many compliant GS1‑MicroPDF417 PNGs as your project demands.

What’s next? Try adding colors (`barcodeGen.Parameters.Barcode.ForeColor`), embedding the barcode in a PDF, or switching to a different GS1 symbology like DataMatrix. The same pattern applies—initialize, configure, set `CodeText`, and save.

Feel free to drop a comment if you hit any snags, or share your own variations. Happy coding, and may your scans always be clean!

## 次に学ぶべきことは？

The following tutorials cover closely related topics that build on the techniques demonstrated in this guide. Each resource includes complete working code examples with step-by-step explanations to help you master additional API features and explore alternative implementation approaches in your own projects.

- [Aspose.BarCode for .NET を使用した Code 16K のバーコードクワイエットゾーンの作成方法](/barcode/english/net/code-16k-encoding/code-16k-quiet-zone-settings/)
- [Aspose.BarCode for .NET を使用した ITF-14 のバーコードクワイエットゾーンの作成方法](/barcode/english/net/itf-14-barcode-customization/itf-14-barcode-quiet-zone-configuration/)
- [Aspose.BarCode を使用したバーコード生成 – Code 39 の設定方法](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-code-39-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}