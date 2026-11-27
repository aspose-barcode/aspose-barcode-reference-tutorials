---
category: general
date: 2026-11-27
description: Aspose.BarCode を使用して C# で PDF417 バーコードを生成する方法を学びましょう。寸法を調整し、列数を設定し、数行のコードで
  PNG として保存できます。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate PDF417 barcode
- Aspose.BarCode C#
- PDF417 barcode dimensions
- barcode image PNG
- BarcodeGenerator usage
language: ja
lastmod: 2026-11-27
og_description: C#でPDF417バーコードを瞬時に生成します。このチュートリアルでは、サイズや列数の設定方法と、結果をPNG画像として保存する方法を示します。
og_image_alt: Screenshot showing a generated PDF417 barcode saved as a PNG file
og_title: C#でPDF417バーコードを生成 – Aspose.BarCodeによるクイックガイド
schemas:
- author: Aspose
  dateModified: '2026-11-27'
  description: Learn how to generate PDF417 barcode in C# using Aspose.BarCode. Adjust
    dimensions, set column count, and save as PNG in a few lines of code.
  headline: How to generate PDF417 barcode in C# with Aspose.BarCode
  type: TechArticle
- description: Learn how to generate PDF417 barcode in C# using Aspose.BarCode. Adjust
    dimensions, set column count, and save as PNG in a few lines of code.
  name: How to generate PDF417 barcode in C# with Aspose.BarCode
  steps:
  - name: Why each line matters
    text: '* **BarcodeGenerator** – the core class that creates a barcode image. Passing
      `EncodeTypes.Pdf417` selects the PDF417 symbology. * **XDimension.Pixels** –
      determines the smallest bar width. Smaller values shrink the image; larger values
      improve readability on low‑resolution scanners. * **Pdf417.Colu'
  - name: Changing the encoded data
    text: 'Replace the second argument of `BarcodeGenerator` with any UTF‑8 string,
      e.g.:'
  - name: Adjusting image size without losing quality
    text: 'If you need a larger image for printing, increase `XDimension.Pixels`:'
  - name: Handling very long inputs
    text: 'PDF417 can encode up to 1 850 characters. For extremely long strings, you
      may want to increase the column count:'
  - name: Saving in other formats
    text: 'Aspose.BarCode supports BMP, JPEG, TIFF, and SVG. Change the format like
      this:'
  type: HowTo
tags:
- barcode
- PDF417
- C#
- Aspose
title: Aspose.BarCode を使用して C# で PDF417 バーコードを生成する方法
url: /ja/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-with-aspose-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# C# と Aspose.BarCode を使用して PDF417 バーコードを生成する方法

.NET アプリケーションで **PDF417 バーコードを生成** する必要がある場合、本ガイドでは簡潔なエンドツーエンドのソリューションを示します。バーコードの作成方法、サイズの微調整、PNG ファイルへの書き出しまで、すべて Aspose.BarCode ライブラリで実現できます。

PDF417 バーコードの生成は、モバイル端末でのスキャン、搭乗券、在庫タグなど、大量のデータをエンコードする必要があるシーンで一般的です。このチュートリアルを終える頃には、コンソール プログラムを実行するだけで高品質な PNG 画像を生成できるようになります。

## 前提条件

開始する前に、以下が揃っていることを確認してください。

* .NET 6.0 SDK 以降がインストール済み  
* 最新版の **Aspose.BarCode for .NET**（NuGet パッケージ `Aspose.BarCode`）  
* IDE またはエディタ（Visual Studio、VS Code、Rider など）  

Aspose.BarCode はクロスプラットフォーム対応のため、コードは Windows、Linux、macOS で動作します。

## 手順 1: 新しいコンソール プロジェクトを作成

ターミナルを開き、次のコマンドを実行します。

```bash
dotnet new console -n Pdf417Demo
cd Pdf417Demo
dotnet add package Aspose.BarCode
```

これにより **Pdf417Demo** という名前の最小限の C# プロジェクトが作成され、`Aspose.BarCode` の依存関係が追加されます。

## 手順 2: バーコード生成コードを記述

**Program.cs** を開き、内容を以下に置き換えます。

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace Pdf417Demo
{
    class Program
    {
        static void Main(string[] args)
        {
            // 1️⃣ Create a PDF417 barcode generator with the desired text
            // EncodeTypes.Pdf417 tells Aspose.BarCode which symbology to use.
            BarcodeGenerator generator = new BarcodeGenerator(
                EncodeTypes.Pdf417, "Sample text for PDF417 barcode");

            // 2️⃣ Adjust barcode dimensions and column count
            // XDimension controls the width of a single module (pixel size).
            // Setting it to 2 pixels yields a compact yet readable barcode.
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // Columns define how many data columns the barcode will have.
            // A value of 3 works well for short strings; increase for longer data.
            generator.Parameters.Barcode.Pdf417.Columns = 3;

            // Optional: increase error correction level for more robust scanning.
            generator.Parameters.Barcode.Pdf417.ErrorCorrectionLevel = 2;

            // 3️⃣ Save the generated barcode as a PNG file
            // The output path can be absolute or relative to the project folder.
            string outputPath = "Pdf417Basic.png";
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"PDF417 barcode saved to '{outputPath}'.");
        }
    }
}
```

### 各行の意味

* **BarcodeGenerator** – バーコード画像を生成するコア クラス。`EncodeTypes.Pdf417` を指定すると PDF417 シンボルが選択されます。  
* **XDimension.Pixels** – 最小バー幅を決定します。値を小さくすると画像が縮小され、大きくすると低解像度スキャナでの可読性が向上します。  
* **Pdf417.Columns** – データ列数を制御します。列数を増やすと短くて高いバーコードになり、減らすと横に広がります。  
* **ErrorCorrectionLevel** – レベルが高いほど冗長データが増え、サイズは大きくなりますが、損傷に対する耐性が向上します。  
* **Save(..., BarCodeImageFormat.Png)** – 画像を PNG 形式でディスクに保存します。PNG はロスレス形式で、後続の処理や文書への埋め込みに最適です。

## 手順 3: プログラムをビルドして実行

ターミナルから次のコマンドを実行します。

```bash
dotnet run
```

以下のように表示されます。

```
PDF417 barcode saved to 'Pdf417Basic.png'.
```

プロジェクト フォルダーに **Pdf417Basic.png** というファイルが作成されます。開くと、テキスト *“Sample text for PDF417 barcode”* をエンコードした明瞭な PDF417 バーコードが表示されます。

![PNG ファイルとして保存された生成済み PDF417 バーコード](pdf417-barcode-example.png "PNG 形式の生成済み PDF417 バーコード")

*画像代替テキスト: PNG ファイルとして保存された生成済み PDF417 バーコードのスクリーンショット。PDF417 バーコード生成チュートリアルの結果を示しています。*

## 手順 4: よくあるバリエーションとエッジケース

### エンコードするデータの変更

`BarcodeGenerator` の第2引数を任意の UTF‑8 文字列に置き換えます。例:

```csharp
new BarcodeGenerator(EncodeTypes.Pdf417, "https://example.com/checkout?order=12345")
```

ジェネレータは自動的にデータを行と列に分割します。

### 画質を保ったまま画像サイズを調整

印刷用に大きな画像が必要な場合は、`XDimension.Pixels` を増やします。

```csharp
generator.Parameters.Barcode.XDimension.Pixels = 4; // double the module width
```

### 非常に長い入力の取り扱い

PDF417 は最大 1 850 文字までエンコード可能です。極端に長い文字列の場合は、列数を増やすことを検討してください。

```csharp
generator.Parameters.Barcode.Pdf417.Columns = 5; // more columns, less height
```

内容が最大容量を超えると、Aspose.BarCode は `ArgumentException` をスローします。生成コードを try‑catch ブロックで囲み、ユーザーフレンドリーなエラーメッセージを表示しましょう。

### 他のフォーマットで保存

Aspose.BarCode は BMP、JPEG、TIFF、SVG をサポートしています。以下のようにフォーマットを変更できます。

```csharp
generator.Save("Pdf417Vector.svg", BarCodeImageFormat.Svg);
```

## 手順 5: バーコードを検証

任意の PDF417 リーダー アプリ（例: バーコードスキャンに対応したスマートフォン カメラ アプリ）でスキャンし、デコードされたテキストがジェネレータに渡した文字列と一致することを確認します。

スキャンに失敗した場合:

* 画像が圧縮されていないか確認（PNG またはロスレス SVG を使用）。  
* `ErrorCorrectionLevel` が使用環境に対して十分に高いか確認。  
* バーコードの寸法がスキャナの解像度に適合しているかチェック。

## 結論

これで C# と Aspose.BarCode を使用して **PDF417 バーコードを生成** し、サイズや列数をカスタマイズし、PNG 画像としてエクスポートする方法が分かりました。この手法はモバイル チケットから在庫管理まで、さまざまなシナリオで活用できます。

次に検討できる項目:

* `BarCodeReader` を使った PDF417 バーコードの **読み取り**。  
* QR Code や DataMatrix など、他のシンボルの生成。  
* PNG を PDF、レポート、Web ページに埋め込む方法。  

エラー訂正レベル、画像フォーマット、データペイロードをプロジェクトの要件に合わせて自由に試してみてください。コーディングを楽しんでください！

## 次に学ぶべきこと

以下のチュートリアルは、本ガイドで示したテクニックを基にした、密接に関連するトピックをカバーしています。各リソースには、ステップバイステップの解説と完全な動作コード例が含まれており、API の追加機能を習得したり、代替実装アプローチを自分のプロジェクトで試したりするのに役立ちます。

- [C# と Aspose.BarCode BarcodeGenerator を使用して PDF417 バーコードを生成する方法](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-with-barcodegenerator/)
- [PDF417 バーコードを生成し PNG としてレンダリングする方法](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-and-render-it-as-png/)
- [C# で PDF417 バーコードを生成し、バーコードサイズを設定する方法](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-and-set-barcode-size/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}