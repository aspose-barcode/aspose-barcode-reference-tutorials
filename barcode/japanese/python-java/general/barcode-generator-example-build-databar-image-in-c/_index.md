---
category: general
date: 2026-07-18
description: C#でサイズを設定し、DataBar Stacked Omni‑Directional バーコード画像を生成するバーコードジェネレータの例です。バーコードのエンコードタイプをすぐに学べます。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- barcode generator example
- how to set dimensions
- how to generate databar
- barcode encode types
- create barcode image c#
language: ja
lastmod: 2026-07-18
og_description: バーコードジェネレータの例では、寸法の設定方法、バーコードエンコードタイプの選択方法、そして最小限のコードでバーコード画像を作成するC#プロジェクトの作成方法を案内します。
og_image_alt: Barcode generator example output showing DataBar barcode with aspect
  ratio 15
og_title: バーコードジェネレータ例 – C#での高速DataBar画像作成
schemas:
- author: Aspose
  dateModified: '2026-07-18'
  description: Barcode generator example showing how to set dimensions and generate
    a DataBar Stacked Omni‑Directional barcode image in C#. Learn barcode encode types
    quickly.
  headline: Barcode Generator Example – Build DataBar Image in C#
  type: TechArticle
tags:
- barcode
- C#
- Aspose
- image generation
title: バーコードジェネレーター例 – C#でDataBar画像を作成
url: /ja/python-java/general/barcode-generator-example-build-databar-image-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Barcode Generator Example – Build DataBar Image in C#

実際に使える **barcode generator example** が欲しくて、髪の毛を抜きそうになったことはありませんか？ あなたは一人ではありません。多くの開発者が、DataBar Stacked Omni‑Directional バーコードの **how to set dimensions** を把握しようとしたときに、ドキュメントが専門用語の山に埋もれて壁にぶつかります。

このチュートリアルでは、**databar** 画像を生成し、適切な **barcode encode types** を選択し、最終的に **create barcode image c#** ファイルを作成できる、完全に実行可能な C# プログラムを順を追って解説します。余計な説明は省き、コピー＆ペーストできるコードと各行の理由を示します。

## What You’ll Need

- **.NET 6**（または最近の .NET バージョン） – 使用する API は .NET Standard を対象としているため、.NET Framework でも動作します。  
- **Aspose.BarCode for .NET** – `BarcodeGenerator` を提供するライブラリです。`Install-Package Aspose.BarCode` で NuGet から取得できます。  
- **C# IDE** – Visual Studio、Rider、または VS Code があれば OK。  
- PNG ファイルを保存するフォルダー（コードは `DatabarAspectRatio15.png` と `DatabarAspectRatio30.png` を作成します）。

すべて揃いましたか？ では、始めましょう。

## Barcode Generator Example – Initialize the Generator

まず最初に、**DataBar Stacked Omni‑Directional** シンボロジー用に設定された `BarcodeGenerator` のインスタンスが必要です。これが今回扱う **barcode encode type** です。

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        // Step 1: Create a DataBar Stacked Omni‑Directional barcode generator
        // with the desired GTIN content.
        var generator = new BarcodeGenerator(
            EncodeTypes.DatabarStackedOmniDirectional,
            "(01)12345678901231");   // GTIN‑14 example
```

> **Why this matters:** `EncodeTypes.DatabarStackedOmniDirectional` は、Aspose に対してどのシンボロジーを描画すべきか正確に指示します。間違ったタイプを選んでも、画像が綺麗でもスキャナはバーコードを認識できません。

## How to Set Dimensions for the Barcode

バーコードの読み取りやすさは **X‑dimension**（最細バーの幅）に依存します。多くの場合、2 ピクセルが適切ですが、プリンタや画面に合わせて調整可能です。

```csharp
        // Step 2: Set a common X‑dimension (pixel width of the narrowest bar)
        generator.Parameters.Barcode.XDimension.Pixels = 2;
```

> **Pro tip:** 別のバーコードファミリーで **how to set dimensions** を調べたいときは、同じプロパティチェーン（`Parameters.Barcode.XDimension`）を使い、`Pixels` の値だけ変更すれば OK です。

## How to Generate DataBar Stacked Omni‑Directional Barcode

ジェネレータの準備ができたら、**aspect ratio** プロパティを操作します。これにより DataBar の高さと幅の比率を調整でき、短くて四角いシンボルや、細長いシンボルを作成できます。

```csharp
        // Step 3: Generate and save a barcode with aspect ratio 15
        generator.Parameters.Barcode.DataBar.AspectRatio = 15;
        generator.Save("DatabarAspectRatio15.png", BarCodeImageFormat.Png);
```

> **What’s happening?** `AspectRatio = 15` は、バーの高さを幅の 15 倍にすることをエンジンに指示します。生成された PNG は実行ファイルと同じディレクトリに保存されます。

## Create Barcode Image C# – Changing the Aspect Ratio

比率を 30 に変えて、2 番目のファイルを保存し、柔軟性を実証しましょう。

```csharp
        // Step 4: Change the aspect ratio to 30 and save another barcode
        generator.Parameters.Barcode.DataBar.AspectRatio = 30;
        generator.Save("DatabarAspectRatio30.png", BarCodeImageFormat.Png);

        Console.WriteLine("Two barcode images have been saved successfully.");
    }
}
```

プログラムを実行すると、次の 2 つの PNG ファイルが生成されます。

| ファイル | アスペクト比 | おおよそのサイズ |
|------|--------------|--------------|
| `DatabarAspectRatio15.png` | 15 | 120 × 180 px |
| `DatabarAspectRatio30.png` | 30 | 120 × 360 px |

任意の画像ビューアで開くと、クリーンでスキャン可能な DataBar シンボルが確認できるはずです。

## Barcode Encode Types Overview (Optional but Handy)

Aspose がサポートする他の **barcode encode types** に興味がある場合、以下の簡易表をご参照ください。

| EncodeTypes Enum | 説明 |
|------------------|------|
| `EncodeTypes.Code128` | 高密度の英数字 |
| `EncodeTypes.QR` | 2‑D マトリックスコード |
| `EncodeTypes.DatabarExpanded` | 小売向け GS1 DataBar |
| `EncodeTypes.DatabarStackedOmniDirectional` | **本チュートリアルの対象** – コンパクトで全方向対応 |

正しい enum を選ぶことで、プロジェクト間の切り替え時に多くの試行錯誤を防げます。

## Common Pitfalls & How to Avoid Them

- **Missing NuGet package** – `Aspose.BarCode` が無いとコードはコンパイルできません。まず `dotnet add package Aspose.BarCode` を実行してください。  
- **Wrong file path** – 絶対パスを使用する場合は、Windows のバックスラッシュ（`\\`）を忘れずに。相対パス（例示通り）を使うと移植性が向上します。  
- **Aspect ratio too extreme** – 50 以上の比率は、一般的なスキャナでは高さが大きすぎて認識できなくなることがあります。ほとんどのユースケースでは 15‑30 が推奨です。

## Full Source Code (Copy‑Paste Ready)

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        // 1️⃣ Initialize generator with DataBar Stacked Omni‑Directional type
        var generator = new BarcodeGenerator(
            EncodeTypes.DatabarStackedOmniDirectional,
            "(01)12345678901231"); // GTIN‑14 sample

        // 2️⃣ Set X‑dimension (how to set dimensions) – 2 pixels is a safe default
        generator.Parameters.Barcode.XDimension.Pixels = 2;

        // 3️⃣ First barcode: aspect ratio 15
        generator.Parameters.Barcode.DataBar.AspectRatio = 15;
        generator.Save("DatabarAspectRatio15.png", BarCodeImageFormat.Png);

        // 4️⃣ Second barcode: aspect ratio 30
        generator.Parameters.Barcode.DataBar.AspectRatio = 30;
        generator.Save("DatabarAspectRatio30.png", BarCodeImageFormat.Png);

        Console.WriteLine("✅ Two barcode images saved – check your project folder.");
    }
}
```

プログラムを実行（`dotnet run` または Visual Studio で **F5**）すると、コンソールにファイルがディスクに保存された旨のメッセージが表示されます。

![Barcode generator example output showing DataBar barcode with aspect ratio 15](placeholder/path/to/image.png){: .align-center alt="Barcode generator example output showing DataBar barcode with aspect ratio 15"}

## Wrapping Up

これで **barcode generator example** が完成し、**how to set dimensions** の方法、適切な **barcode encode types** の選択、そして **create barcode image c#** ファイルの作成手順を実演しました。コードはシンプルで概念は明快です。これを土台に、テキストキャプションの追加、画像の回転、別シンボロジーへの切り替えなど、機能拡張に挑戦してみてください。

### What’s Next?

- **異なる X‑dimension** を試して、スキャナの許容範囲がどう変わるか確認する。  
- `Code128` や `QR` など他の **EncodeTypes** を試し、ツールキットを拡充する。  
- バッチ生成を自動化：CSV の商品 ID をループで処理し、各 ID に対して PNG を出力する。

問題が発生したらコメントを残すか、Aspose.BarCode の公式ドキュメントを参照してください。豊富なサンプルが本チュートリアルを補完しています。

Happy coding, and may your barcodes always scan on the first try!

## What Should You Learn Next?

以下のチュートリアルは、本ガイドで示した手法に基づき、関連トピックを深掘りするためのものです。各リソースには、完全に動作するコード例とステップバイステップの解説が含まれており、API の追加機能を習得したり、別の実装アプローチを自分のプロジェクトで試したりするのに役立ちます。

- [How to Generate Barcode - One-Dimensional Barcode Types](/barcode/english/net/one-dimensional-barcode-types/)
- [Create barcode image C# – GS1 DataMatrix Example](/barcode/english/net/gs1-barcode-encoding/gs1-datamatrix-example/)
- [How to Generate DataMatrix Barcodes (ECC 200) with Aspose.BarCode for .NET](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-ecc-200-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}