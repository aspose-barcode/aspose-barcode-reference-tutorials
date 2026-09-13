---
category: general
date: 2026-09-13
description: C#でバーコードを生成し、サイズをカスタマイズし、Aspose.BarCodeを使用してバーコード画像をPNG形式で保存する方法を学びましょう。完全なステップバイステップガイドです。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to generate barcode
- custom barcode size
- save barcode image
- Aspose.BarCode C#
- barcode image format
language: ja
lastmod: 2026-09-13
og_description: C#でカスタムサイズのバーコードを生成し、バーコード画像をPNGとして保存する方法。Aspose.BarCodeの完全ガイドをご覧ください。
og_image_alt: Screenshot of a DataBar stacked omnidirectional barcode generated in
  C#
og_title: C#でバーコードを生成し、カスタムサイズを設定し、画像を保存する方法
schemas:
- author: Aspose
  dateModified: '2026-09-13'
  description: Learn how to generate barcode in C#, customize barcode size, and save
    barcode image as PNG using Aspose.BarCode. Complete step‑by‑step guide.
  headline: How to generate barcode set custom size and save image in C#
  type: TechArticle
tags:
- barcode
- C#
- Aspose
title: C#でバーコードを生成し、カスタムサイズを設定して画像を保存する方法
url: /ja/python-java/general/how-to-generate-barcode-set-custom-size-and-save-image-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# C#でバーコードセットのカスタムサイズを生成し、画像を保存する方法

.NET アプリケーションで **バーコードの生成方法** が必要な場合、このチュートリアルでは完全なソリューションを示します。数行の C# コードで **カスタムバーコードサイズ** を調整し、**バーコード画像の保存** ファイルを作成する方法が分かります。

バーコードの生成は、在庫管理システム、出荷ラベル、POS アプリケーションで一般的な要件です。このガイドの最後までに、異なるアスペクト比を持つ 2 つの DataBar‑Stacked‑Omnidirectional バーコードを作成し、ディスク上の PNG ファイルに書き出す実行可能なプログラムが手に入ります。

**前提条件**

- .NET 6.0 以上（コードは .NET Framework 4.7+ でも動作します）
- Visual Studio 2022 または任意の C# IDE
- Aspose.BarCode for .NET（無料トライアルまたはライセンス済み NuGet パッケージ）

---

## Aspose.BarCode を使用したバーコードの生成方法

Aspose.BarCode ライブラリはバーコード規格の低レベルな詳細を抽象化し、エンコードしたいデータと必要な視覚的外観に集中できるようにします。

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        // 1️⃣ Create a DataBar stacked omnidirectional barcode generator
        var generator = new BarcodeGenerator(
            EncodeTypes.DatabarStackedOmniDirectional,
            "(01)12345678901231"); // GS1‑128 format example

        // 2️⃣ Set a basic module width – this influences the overall **custom barcode size**
        generator.Parameters.Barcode.XDimension.Pixels = 2;

        // 3️⃣ First aspect ratio (15) → save the image
        generator.Parameters.Barcode.DataBar.AspectRatio = 15;
        generator.Save("DatabarAspectRatio15.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved barcode with aspect ratio 15.");

        // 4️⃣ Change aspect ratio to 30 → **save barcode image** again
        generator.Parameters.Barcode.DataBar.AspectRatio = 30;
        generator.Save("DatabarAspectRatio30.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved barcode with aspect ratio 30.");
    }
}
```

### 各行が重要な理由

| Step | Explanation |
|------|-------------|
| **1️⃣ ジェネレーターの作成** | `EncodeTypes.DatabarStackedOmniDirectional` 列挙体は、Aspose に使用するバーコードシンボルを指示します。文字列 `"(01)12345678901231"` は GS1‑128 データ形式に従っており、`(01)` は GTIN のアプリケーション識別子です。 |
| **2️⃣ X‑dimension の設定** | `XDimension.Pixels` は単一のバーコードモジュール（最小のバー）の幅を定義します。この値を変更することは、エンコードされたデータを変更せずに **カスタムバーコードサイズ** を実現する主な方法です。 |
| **3️⃣ アスペクト比の設定と保存** | `DataBar.AspectRatio` は DataBar シンボルの高さと幅の比率を制御します。アスペクト比 15 は比較的短く幅の広いバーコードを生成し、30 はより高くなります。`Save` は視覚的表現を PNG ファイルに書き込み、**バーコード画像の保存** 要件を満たします。 |
| **4️⃣ アスペクト比を変更して再保存** | 同じジェネレーターインスタンスを再利用することで、データを一定に保ちつつ、異なる視覚的特性を持つ複数の画像を生成できます。 |

---

## X‑dimension 以外でカスタムバーコードサイズを調整する

`XDimension.Pixels` がモジュール幅を設定する一方で、2 つのプロパティを組み合わせることでバーコード全体の寸法を微調整できます。

1. **`BarHeight`** – ピクセル単位の明示的な高さ。  
2. **`BarWidth`** – ピクセル単位の明示的な幅（X‑dimension を上書き）。

```csharp
// Example: make a larger, more readable barcode
generator.Parameters.Barcode.XDimension.Pixels = 4;      // wider modules
generator.Parameters.Barcode.BarHeight.Pixels = 120;    // taller bars
generator.Parameters.Barcode.DataBar.AspectRatio = 20; // balanced ratio
generator.Save("LargeCustomSize.png", BarCodeImageFormat.Png);
Console.WriteLine("Saved large custom size barcode.");
```

> **Pro tip:** バーコードを印刷する際は、必ず最終印刷サイズで生成画像をテストしてください。モジュール幅 2 px は画面表示には適していますが、印刷ラベルではスキャン可能性を保つために少なくとも 4 px が必要になることが多いです。

---

## バーコード画像保存に適した画像フォーマットの選択

Aspose.BarCode は PNG、JPEG、BMP、GIF、TIFF をサポートしています。PNG はロスレスでエッジが鮮明に保たれるため、ほとんどのアプリケーションで最も安全な選択です。ウェブ用にファイルサイズを小さくしたい場合は、品質 90 の JPEG が有効ですが、圧縮アーティファクトがスキャンの信頼性に影響する可能性があることに注意してください。

```csharp
generator.Save("DatabarAspectRatio15.jpg", BarCodeImageFormat.Jpeg, 90);
Console.WriteLine("Saved JPEG version with quality 90.");
```

---

## 完全な実行可能サンプル

以下はコピーして貼り付け、実行できる単体のコンソールアプリケーションです。**バーコードの生成方法** を示し、**カスタムバーコードサイズ** を変更し、**バーコード画像の保存** を 2 つの異なるフォーマットで行う例です。

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // Initialize the generator with the desired symbology and data
            var generator = new BarcodeGenerator(
                EncodeTypes.DatabarStackedOmniDirectional,
                "(01)12345678901231");

            // ---- Custom size configuration ----
            generator.Parameters.Barcode.XDimension.Pixels = 2;      // module width
            generator.Parameters.Barcode.BarHeight.Pixels = 80;    // optional explicit height
            generator.Parameters.Barcode.DataBar.AspectRatio = 15; // first aspect ratio

            // Save first image as PNG
            string pngPath1 = "DatabarAspectRatio15.png";
            generator.Save(pngPath1, BarCodeImageFormat.Png);
            Console.WriteLine($"Saved {pngPath1}");

            // Change aspect ratio for a taller barcode
            generator.Parameters.Barcode.DataBar.AspectRatio = 30;
            string pngPath2 = "DatabarAspectRatio30.png";
            generator.Save(pngPath2, BarCodeImageFormat.Png);
            Console.WriteLine($"Saved {pngPath2}");

            // ---- Larger custom size example ----
            generator.Parameters.Barcode.XDimension.Pixels = 4;
            generator.Parameters.Barcode.BarHeight.Pixels = 120;
            generator.Parameters.Barcode.DataBar.AspectRatio = 20;
            string largePath = "LargeCustomSize.png";
            generator.Save(largePath, BarCodeImageFormat.Png);
            Console.WriteLine($"Saved {largePath}");

            // ---- Save as JPEG for web use ----
            string jpegPath = "DatabarAspectRatio15.jpg";
            generator.Save(jpegPath, BarCodeImageFormat.Jpeg, 90);
            Console.WriteLine($"Saved {jpegPath}");
        }
    }
}
```

**コンソール上の期待出力**

```
Saved DatabarAspectRatio15.png
Saved DatabarAspectRatio30.png
Saved LargeCustomSize.png
Saved DatabarAspectRatio15.jpg
```

4 つの画像ファイルがプログラムの実行ディレクトリに作成されます。

## 次に学ぶべきことは？

以下のチュートリアルは、本ガイドで示した手法を基にした密接に関連するトピックを取り上げています。各リソースには、ステップバイステップの解説と完全な動作コード例が含まれており、追加の API 機能を習得し、独自プロジェクトで代替実装アプローチを検討するのに役立ちます。

- [Aspose.BarCode for .NET を使用した DataMatrix バーコードの生成方法 – ステップバイステップガイド](/barcode/english/net/datamatrix-barcode-configuration/)
- [Aspose を使用した PDF417 バーコードの生成 – 完全ガイド](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-with-aspose-complete-guide/)
- [Aspose.BarCode for .NET を使用したカスタムアスペクト比の Aztec バーコード生成](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}