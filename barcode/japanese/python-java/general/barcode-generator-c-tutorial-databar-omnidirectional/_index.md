---
category: general
date: 2026-11-14
description: DataBar Omnidirectional バーコードの作成方法、X ディメンションの設定、ピクセル単位でのバー高さの調整を示す C#
  バーコードジェネレータチュートリアル。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- barcode generator c# tutorial
- DataBar Omnidirectional
- set bar height
- XDimension pixels
- BarCodeImageFormat PNG
language: ja
lastmod: 2026-11-14
og_description: Barcode generator C# チュートリアルでは、DataBar Omnidirectional バーコードの生成方法、ピクセル単位での
  XDimension の定義、そして PNG 出力時のバー高さの変更方法をステップバイステップで解説しています。
og_image_alt: Screenshot of barcode generator C# tutorial output showing a DataBar
  barcode
og_title: バーコードジェネレーター C# チュートリアル – DataBar バーコードの作成
schemas:
- author: Aspose
  dateModified: '2026-11-14'
  description: Barcode generator C# tutorial that shows how to create DataBar Omnidirectional
    barcodes, set X‑dimension, and adjust bar height in pixels.
  headline: 'Barcode generator C# tutorial: DataBar Omnidirectional'
  type: TechArticle
tags:
- barcode
- C#
- DataBar
- tutorial
title: バーコードジェネレーター C# チュートリアル：DataBar オムニディレクショナル
url: /ja/python-java/general/barcode-generator-c-tutorial-databar-omnidirectional/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Barcode generator C# tutorial – create DataBar Omnidirectional barcodes

**barcode generator C# tutorial** をお探しなら、ここが正解です。本ガイドでは DataBar Omnidirectional バーコードの作成方法、ピクセル単位での XDimension 設定、バー高さの調整による PNG 画像の生成手順を解説します。

完全に実行可能なサンプルを通して、ジェネレーターの初期化から異なるバー高さでの画像保存までを網羅しています。外部ドキュメントは不要です。コードをコピーして実行すれば、すぐに使用できる 2 つのバーコードファイルが生成されます。

## Prerequisites

開始する前に、以下が揃っていることを確認してください。

* .NET 6.0 以降がインストール済み  
* `BarcodeGenerator`、`EncodeTypes`、`BarCodeImageFormat` を提供するバーコードライブラリへの参照（例: Aspose.BarCode for .NET）  
* C# の基本構文と Visual Studio もしくはお好みの IDE に関する基本的な知識  

> **Pro tip:** Aspose.BarCode を使用する場合は、NuGet パッケージ `Aspose.BarCode` をプロジェクトに追加してください。

## Barcode generator C# tutorial – step 1: create the generator

最初のステップは、`DatabarOmniDirectional` エンコードタイプとエンコードしたいデータを指定して `BarcodeGenerator` のインスタンスを作成することです。

```csharp
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Step 1: Create a DataBar Omnidirectional barcode generator with the desired data
        BarcodeGenerator generator = new BarcodeGenerator(
            EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");
```

*Why this matters:* `EncodeTypes.DatabarOmniDirectional` は、任意の方向から読み取れるバーコードを生成するようライブラリに指示します。小売包装や物流での使用に最適です。

## Set XDimension pixels for the barcode

X‑dimension は、バーコード内の最小モジュール（「ピクセル」）の幅を定義します。ピクセル単位で設定することで、バーコードの視覚的密度を正確にコントロールできます。

```csharp
        // Step 2: Define the X‑dimension (module width) in pixels
        generator.Parameters.Barcode.XDimension.Pixels = 2;
```

*Explanation:* `2` ピクセルの値は、ほとんどのスキャナーで十分に読み取り可能な鮮明さを保ちつつ、画像ファイルサイズを抑えるバランスの取れた設定です。

## Adjust bar height and save images

バー高さはバーの縦長さを決定します。`BarHeight.Pixels` プロパティの値を変更し、再度 `Save` を呼び出すことで、異なる高さの画像を複数生成できます。

```csharp
        // Step 3: Set the bar height to 30 px and save the image
        generator.Parameters.Barcode.BarHeight.Pixels = 30;
        string outputPath = @"YOUR_DIRECTORY\DatabarBarHeight30Pixels.png";
        generator.Save(outputPath, BarCodeImageFormat.Png);
```

`BarCodeImageFormat.Png` 列挙値は、出力がロスレスな PNG ファイルになることを保証します。PNG は正確な寸法を保持できるため、バーコード画像の推奨フォーマットです。

## Change bar height to create multiple images

同じバーコードを異なるサイズで使用したいケースは多くあります（例: 小さなラベル用と大きなポスター用）。バー高さを変更し、同一のジェネレーターインスタンスを再利用します。

```csharp
        // Step 4: Change the bar height to 60 px and save a second image
        generator.Parameters.Barcode.BarHeight.Pixels = 60;
        outputPath = @"YOUR_DIRECTORY\DatabarBarHeight60Pixels.png";
        generator.Save(outputPath, BarCodeImageFormat.Png);
    }
}
```

*Edge case:* バー高さを極端に低く設定すると（例: 10 px 未満）、一部のスキャナーがコードの読み取りに苦戦する可能性があります。必ず対象スキャナーで生成画像をテストしてください。

## Full source code

以下は新規コンソールプロジェクトに貼り付けて使用できる完全なプログラムです。必要な `using` ディレクティブをすべて含み、バー高さのバリエーションも示しています。

```csharp
using System;
using Aspose.BarCode.Generation;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // Create a DataBar Omnidirectional barcode generator
            BarcodeGenerator generator = new BarcodeGenerator(
                EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");

            // Set XDimension to 2 pixels
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // First image – 30 px bar height
            generator.Parameters.Barcode.BarHeight.Pixels = 30;
            string path30 = @"YOUR_DIRECTORY\DatabarBarHeight30Pixels.png";
            generator.Save(path30, BarCodeImageFormat.Png);
            Console.WriteLine($"Saved 30 px barcode to {path30}");

            // Second image – 60 px bar height
            generator.Parameters.Barcode.BarHeight.Pixels = 60;
            string path60 = @"YOUR_DIRECTORY\DatabarBarHeight60Pixels.png";
            generator.Save(path60, BarCodeImageFormat.Png);
            Console.WriteLine($"Saved 60 px barcode to {path60}");
        }
    }
}
```

プログラムを実行し、`YOUR_DIRECTORY` を有効なフォルダー パスに置き換えると、次の 2 つの PNG ファイルが生成されます。

* `DatabarBarHeight30Pixels.png` – バー高さ 30 px  
* `DatabarBarHeight60Pixels.png` – バー高さ 60 px  

![barcode generator C# tutorial output](images/databar-example.png "Barcode generator C# tutorial showing two DataBar images")

## Common questions

| Question | Answer |
|----------|--------|
| **Can I change the image format?** | Yes. Replace `BarCodeImageFormat.Png` with `Jpeg`, `Bmp`, or `Gif` as needed. PNG is preferred for lossless quality. |
| **What if I need a different XDimension?** | Adjust `generator.Parameters.Barcode.XDimension.Pixels` to any integer. Larger values increase overall barcode width. |
| **Is the DataBar Omnidirectional suitable for mobile scanning?** | It is, provided the printed size meets the scanner’s minimum module size (usually 0.33 mm). The pixel‑based XDimension helps you meet that requirement. |
| **How do I embed the barcode in a PDF?** | After saving the PNG, use a PDF library (e.g., iTextSharp) to insert the image into a PDF page. |

## Conclusion

この **barcode generator C# tutorial** では、DataBar Omnidirectional バーコードの作成、ピクセル単位での XDimension 設定、異なるバー高さでの PNG 生成手順を学びました。これで、任意の C# プロジェクトで再利用可能なコードスニペットが手に入りました。

### What’s next?

* `EncodeTypes` の他の種類（例: `Code128` や `QR`）を試して、バーコードのバリエーションを広げましょう。  
* 生成した PNG を PDF 作成ライブラリと組み合わせ、印刷可能な請求書を作成します。  
* `generator.Parameters.Barcode.Color` を活用し、スキャナー仕様を守りつつカスタムカラーを適用してみてください。

例を自由に改変し、追加のバー高さや出力フォーマットを試してみてください。Happy coding!

## What Should You Learn Next?

以下のチュートリアルは、本ガイドで示した手法を基にした、密接に関連するトピックをカバーしています。各リソースには、完全に動作するコード例とステップバイステップの解説が含まれており、API の追加機能を習得したり、独自の実装アプローチを探求したりするのに役立ちます。

- [How to set width and adjust height for a GS1 DataBar Omni‑Directional barcode](/barcode/english/python-java/general/how-to-set-width-and-adjust-height-for-a-gs1-databar-omni-di/)
- [How to set barcode height, generate DataBar barcode in C#](/barcode/english/python-java/general/how-to-set-barcode-height-generate-databar-barcode-in-c/)
- [How to create omnidirectional Databar barcode in C#](/barcode/english/python-java/general/how-to-create-omnidirectional-databar-barcode-in-c/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}