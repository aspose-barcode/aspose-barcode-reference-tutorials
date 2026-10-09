---
category: general
date: 2026-10-08
description: C#で空のプラネットバーコードを作成し、Aspose.BarCodeを使用して郵便バーコードの生成方法を学びましょう。ステップバイステップのコードとヒントが含まれています。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create empty planet barcode
- how to generate postal barcode
- Aspose.BarCode C#
- postal barcode example
- barcode XDimension setting
language: ja
lastmod: 2026-10-08
og_description: C# の Aspose.BarCode を使用して空のプラネットバーコードを作成し、郵送アプリケーション向けの郵便バーコード画像の生成方法をご確認ください。
og_image_alt: Screenshot of generated empty Planet barcode and filled RM4SCC barcode
og_title: 空のプラネットバーコードを作成 – C# 郵便バーコードガイド
schemas:
- author: Aspose
  dateModified: '2026-10-08'
  description: Create empty planet barcode with C# and learn how to generate postal
    barcode using Aspose.BarCode. Step‑by‑step code and tips included.
  headline: Create empty planet barcode, generate postal barcode in C#
  type: TechArticle
tags:
- barcode
- C#
- Aspose.BarCode
- postal
title: 空のプラネットバーコードを作成し、C#で郵便バーコードを生成する
url: /ja/python-java/general/create-empty-planet-barcode-generate-postal-barcode-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 空のプラネットバーコードを作成し、C#で郵便バーコードを生成する

If you need to **create empty planet barcode** for a mailing system, this guide shows you exactly how to do it with Aspose.BarCode for .NET. You will also learn **how to generate postal barcode** images such as Planet and RM4SCC, customize bar width, and control the filled‑bars option.

Generating postal barcodes does not require a separate graphics library. The Aspose.BarCode SDK provides a single API that handles encoding, image rendering, and image format selection. By the end of this tutorial you will have three ready‑to‑use PNG files:

* `PostalPlanetEmptyBars.png` – 空のバーの Planet バーコード  
* `PostalPlanetFilledBars.png` – デフォルトの filled‑bars Planet バーコード  
* `PostalRM4SCCFilledBars.png` – filled‑bars RM4SCC バーコード  

You can drop these files into any mailing label template, print them on envelopes, or pass them to a third‑party service.

## 前提条件

* .NET 6.0 以降（コードは .NET Framework 4.7+ でも動作します）。  
* Visual Studio 2022 または任意の C# IDE。  
* Aspose.BarCode for .NET – NuGet でインストール：

```bash
dotnet add package Aspose.BarCode
```

No additional dependencies are required.

## Aspose.BarCode で空のプラネットバーコードを作成する

The Planet symbology is part of the United States Postal Service (USPS) barcode family. By default the SDK draws **filled** bars. To **create empty planet barcode**, you disable the `FilledBars` flag.

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;

// Step 1 – instantiate a Planet barcode generator with the data to encode.
BarcodeGenerator planetEmpty = new BarcodeGenerator(EncodeTypes.Planet, "123456");

// Step 2 – set the width of a single bar. XDimension defines the pixel size of one bar.
planetEmpty.Parameters.Barcode.XDimension.Pixels = 4;

// Step 3 – disable the FilledBars option to get empty (hollow) bars.
planetEmpty.Parameters.Barcode.FilledBars = false;

// Step 4 – save the image. The PNG format is widely supported by printers and browsers.
planetEmpty.Save("YOUR_DIRECTORY/PostalPlanetEmptyBars.png", BarCodeImageFormat.Png);
```

**この動作の理由:**  
`EncodeTypes.Planet` はジェネレータに Planet シンボルを使用させます。`XDimension.Pixels` は各バーの物理的な幅を制御し、特定のモジュールサイズを期待する郵便スキャナにとって重要です。`FilledBars` を `false` に設定すると、レンダラは各バーの輪郭だけを描画し、いくつかの郵便規格で求められる *empty* な外観を生成します。

### 期待される出力

You will find `PostalPlanetEmptyBars.png` in the target folder. The image shows a Planet barcode where each bar is an outline rather than a solid rectangle.

![Empty Planet barcode example](empty-planet.png){: .align-center alt="空のプラネットバーコード – 空のバーの Planet バーコードの例"}

## 郵便バーコード画像を生成する方法（filled バージョン）

Most postal workflows use the default filled‑bars version. The same API can generate a filled Planet barcode and an RM4SCC barcode with just a few lines of code.

```csharp
// Filled Planet barcode (default behavior)
BarcodeGenerator planetFilled = new BarcodeGenerator(EncodeTypes.Planet, "123456");
planetFilled.Parameters.Barcode.XDimension.Pixels = 4;
planetFilled.Save("YOUR_DIRECTORY/PostalPlanetFilledBars.png", BarCodeImageFormat.Png);

// RM4SCC barcode – another USPS format that always uses filled bars
BarcodeGenerator rm4sccFilled = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");
rm4sccFilled.Parameters.Barcode.XDimension.Pixels = 4;
rm4sccFilled.Save("YOUR_DIRECTORY/PostalRM4SCCFilledBars.png", BarCodeImageFormat.Png);
```

**なぜ RM4SCC が必要になるか:**  
RM4SCC は Planet と同じデータをエンコードしますが、密度が高い新しい USPS バーコードです。一部のキャリアは大量郵送割引のために RM4SCC を要求します。上記のコードは、全体のワークフローを変更せずに両方の規格向けに **郵便バーコードを生成する方法** を示しています。

### 期待される出力

* `PostalPlanetFilledBars.png` – クラシックな filled‑bars Planet バーコード。  
* `PostalRM4SCCFilledBars.png` – filled‑bars RM4SCC バーコード。見た目は似ていますが、間隔がより狭くなっています。

Both files can be opened in any image viewer to verify the bar patterns.

## 異なる印刷解像度に合わせたバー幅の調整

Postal scanners often specify a minimum module width (e.g., 0.013 inches). If your printer works at 300 dpi, a 4‑pixel module corresponds to 0.013 inches. Adjust the `XDimension.Pixels` value to match your hardware:

| 希望モジュール (インチ) | DPI | 必要ピクセル数 (`XDimension`) |
|--------------------------|-----|------------------------------|
| 0.013                    | 300 | 4                            |
| 0.013                    | 600 | 8                            |
| 0.015                    | 300 | 5                            |

**プロのコツ:** Always test a

## 次に学ぶべきことは？

The following tutorials cover closely related topics that build on the techniques demonstrated in this guide. Each resource includes complete working code examples with step-by-step explanations to help you master additional API features and explore alternative implementation approaches in your own projects.

- [C# でプラネットバーコード PNG を作成する方法 – ステップバイステップガイド](/barcode/english/python-java/general/how-to-create-planet-barcode-png-with-c-step-by-step-guide/)
- [C# で郵便バーコードを生成する – Planet バーコード付き完全ガイド](/barcode/english/python-java/general/generate-postal-barcode-in-c-complete-guide-with-planet-barc/)
- [Aspose.BarCode を使用して C# で郵便バーコードを生成する方法](/barcode/english/python-java/general/how-to-generate-postal-barcode-in-c-with-aspose-barcode/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}