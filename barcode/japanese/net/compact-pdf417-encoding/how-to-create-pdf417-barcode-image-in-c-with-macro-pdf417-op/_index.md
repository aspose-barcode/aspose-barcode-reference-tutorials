---
category: general
date: 2026-09-13
description: BarcodeGenerator と Macro PDF417 オプションを使用して C# で PDF417 バーコード画像を作成する方法を学びましょう。ステップバイステップのコード、ヒント、完全なサンプル。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create PDF417 barcode image
- macro PDF417 options
- BarcodeGenerator class
- C# barcode generation
- barcode image format
language: ja
lastmod: 2026-09-13
og_description: BarcodeGenerator を使用して C# で PDF417 バーコード画像を作成します。マクロ PDF417 のオプションを設定し、PNG
  バーコードを保存する詳細なチュートリアルをご覧ください。
og_image_alt: Screenshot of a generated PDF417 barcode image created with C# code
og_title: C#でPDF417バーコード画像を作成する – 完全ガイド
schemas:
- author: Aspose
  dateModified: '2026-09-13'
  description: Learn how to create PDF417 barcode image in C# using BarcodeGenerator
    and Macro PDF417 options. Step‑by‑step code, tips, and full example.
  headline: How to create PDF417 barcode image in C# with Macro PDF417 options
  type: TechArticle
- description: Learn how to create PDF417 barcode image in C# using BarcodeGenerator
    and Macro PDF417 options. Step‑by‑step code, tips, and full example.
  name: How to create PDF417 barcode image in C# with Macro PDF417 options
  steps:
  - name: '**Create the generator** – instantiate `BarcodeGenerator` with `EncodeTypes.MacroPdf417`
      and the data you want to encode.'
    text: '**Create the generator** – instantiate `BarcodeGenerator` with `EncodeTypes.MacroPdf417`
      and the data you want to encode.'
  - name: '**Define the module size** – set `XDimension.Pixels` to control the physical
      width of each barcode element.'
    text: '**Define the module size** – set `XDimension.Pixels` to control the physical
      width of each barcode element.'
  - name: '**Configure Macro PDF417 options** – specify columns, file identifiers,
      segment numbers, and optional checksum.'
    text: '**Configure Macro PDF417 options** – specify columns, file identifiers,
      segment numbers, and optional checksum.'
  - name: '**Save the barcode** – write the generated image to disk using a supported
      **barcode image format** such as PNG.'
    text: '**Save the barcode** – write the generated image to disk using a supported
      **barcode image format** such as PNG.'
  - name: Create a new .NET 6 (or later) console project.
    text: Create a new .NET 6 (or later) console project.
  - name: Add the Aspose.BarCode NuGet package (`dotnet add package Aspose.BarCode`).
    text: Add the Aspose.BarCode NuGet package (`dotnet add package Aspose.BarCode`).
  - name: Replace the generated `Program.cs` with the code above.
    text: Replace the generated `Program.cs` with the code above.
  - name: Adjust `outputPath` to a folder you have write access to.
    text: Adjust `outputPath` to a folder you have write access to.
  - name: Build and run – the console will confirm the image location.
    text: Build and run – the console will confirm the image location.
  type: HowTo
tags:
- PDF417
- C#
- Barcode
title: C#でMacro PDF417オプションを使用してPDF417バーコード画像を作成する方法
url: /ja/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-image-in-c-with-macro-pdf417-op/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# C# で Macro PDF417 オプションを使用して PDF417 バーコード画像を作成する方法

C# で **PDF417 バーコード画像を作成** したい場合は、このガイドで **BarcodeGenerator クラス** を使った手順をすべて解説します。ドキュメント追跡システムの構築や大容量ファイルのエンコードなど、Macro PDF417 オプションの設定から最終的な PNG の保存まで、ステップバイステップで説明します。

バーコードの生成は、主要パラメータを理解すれば簡単です。このチュートリアルで学べることは次のとおりです。

* **Macro PDF417** 用の `BarcodeGenerator` を初期化する方法  
* バーコードモジュールサイズ（`XDimension`）の調整方法  
* ファイル ID、セグメント ID、チェックサムなど、セグメント固有の設定方法  
* 任意の **バーコード画像形式**（PNG）で結果を保存し、UI に表示できるようにする方法  

前提条件は .NET 開発環境（Visual Studio 2022 以降）と、サンプルで使用する `BarcodeGenerator` API を提供する Aspose.BarCode for .NET NuGet パッケージだけです。

---

## C# で PDF417 バーコード画像を作成する概要

PDF417 バーコード画像の作成は、以下の 4 つの論理的ステップで構成されます。

1. **ジェネレータの作成** – `BarcodeGenerator` を `EncodeTypes.MacroPdf417` とエンコードしたいデータでインスタンス化します。  
2. **モジュールサイズの定義** – `XDimension.Pixels` を設定し、各バーコード要素の実際の幅を制御します。  
3. **Macro PDF417 オプションの設定** – 列数、ファイル識別子、セグメント番号、オプションのチェックサムを指定します。  
4. **バーコードの保存** – PNG などのサポートされた **バーコード画像形式** で生成画像をディスクに書き出します。

各ステップは以下で詳しく解説し、完全に実行可能な C# コードを掲載しています。

---

## ステップ 1: Macro PDF417 用に BarcodeGenerator を初期化する

最初の行で **Macro PDF417** バーコードを生成することを示す `BarcodeGenerator` オブジェクトを作成します。コンストラクタはエンコードタイプと生データ文字列の 2 つの引数を受け取ります。

```csharp
using Aspose.BarCode.Generation;   // NuGet: Aspose.BarCode
using System.Drawing.Imaging;      // For ImageFormat if you prefer System.Drawing

// Step 1 – create a barcode generator for Macro PDF417
using (var barcodeGenerator = new BarcodeGenerator(EncodeTypes.MacroPdf417, "Sample data"))
{
    // Subsequent configuration goes here
}
```

**重要ポイント:**  
`EncodeTypes.MacroPdf417` は、ライブラリに対してこのバーコードがマルチセグメントコンテナであることを指示します。大きなファイルを複数シンボルに分割する必要がある場合に必須です。`BarcodeGenerator` は `IDisposable` なので、`using` ブロックで囲むことで画像保存後にすべてのアンマネージドリソースが解放されます。

---

## ステップ 2: バーコードモジュールサイズ (XDimension) を設定する

`XDimension` は単一バーコードモジュール（最小の黒または白のバー）のピクセル幅を制御します。**2 ピクセル** の値は、コンパクトでありながら読み取りやすい画像を生成します。

```csharp
    // Step 2 – define the size of each barcode module (pixel width)
    barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

**実践的なヒント:**  
ターゲットプリンタの DPI が低い場合は、ピクセル数を増やす（例: `3` や `4`）ことでにじみを防げます。逆に画面表示だけなら低めに設定してファイルサイズを削減できます。

---

## ステップ 3: Macro PDF417 固有のオプションを設定する

Macro PDF417 は、スキャナが複数のバーコードセグメントから元のファイルを復元できるようにメタデータを付加します。最も一般的なオプションは次のとおりです。

| プロパティ | 意味 |
|----------|------|
| `Columns` | 各シンボルの列数（幅に影響）。 |
| `MacroPdf417FileID` | ファイル全体を識別するユニーク ID。 |
| `MacroPdf417SegmentID` | 現在のセグメント番号（1 から開始）。 |
| `MacroPdf417SegmentsCount` | ファイルを構成する総セグメント数。 |
| `MacroPdf417FileName` | 元ファイル名（任意、表示用）。 |
| `MacroPdf417Checksum` | 整合性検証用のオプション 16 ビットチェックサム。 |

```csharp
    // Step 3 – configure Macro PDF417 specific options
    barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 5;                     // Number of columns in the symbol
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;    // Unique file identifier
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 1;       // Current segment number
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 10; // Total number of segments
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "report.pdf"; // Original file name
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 0x1A2B;    // Optional checksum
```

**これらの設定が重要な理由:**  
- **Columns** は可読性と画像全体のサイズに直結します。  
- **FileID** はすべてのセグメントで同一である必要があり、デコーダが同一ファイルとして認識します。  
- **SegmentID** と **SegmentsCount** により、スキャナは正しい順序でセグメントを組み立てられます。  
- **FileName** と **Checksum** は任意ですが、ユーザー体験とデータ整合性を向上させます。

**エッジケース:** 999 セグメントを超える場合、`SegmentID` フィールドがオーバーフローします。その際はデータを複数ファイルに分割してください。

---

## ステップ 4: 生成したバーコードを PNG 画像として保存する

最終ステップでは、バーコードをディスクに書き出します。`BarCodeImageFormat.Png` はロスレス画像を生成し、Web、デスクトップ、モバイルのすべてのプラットフォームで利用可能です。

```csharp
    // Step 4 – save the generated barcode as a PNG image
    barcodeGenerator.Save("YOUR_DIRECTORY/MacroPdf417.png", BarCodeImageFormat.Png);
}
```

**代替フォーマット:**  
下位互換性が必要な場合は `BarCodeImageFormat.Png` を `Jpeg`、`Bmp`、`Gif` に置き換えられます。ただし JPEG は圧縮アーティファクトが発生し、スキャン信頼性が低下する可能性があります。

**期待される出力:**  
`MacroPdf417.png` というファイルには、高コントラストでマルチセグメントの PDF417 バーコードが格納されます。開くと以下のイラストと同様の外観になるはずです。

![Create PDF417 barcode image example](image.png){: .align-center alt="C# コードで生成された PDF417 バーコード画像例"}

---

## 完全なソースコード – コピーしてすぐ実行可能

以下は、必要な `using` ディレクティブ、`Main` メソッド、そして各行の説明コメントを含む、自己完結型のサンプルプログラムです。

```csharp
using System;
using Aspose.BarCode.Generation;   // Install-Package Aspose.BarCode
// No other external dependencies are required.

namespace Pdf417BarcodeDemo
{
    class Program
    {
        static void Main(string[] args)
        {
            // Data to encode – can be any UTF‑8 string up to 1,800 characters.
            const string dataToEncode = "Sample data";

            // Output directory – change this to a valid path on your machine.
            const string outputPath = @"C:\Barcodes\MacroPdf417.png";

            // Create a BarcodeGenerator for Macro PDF417.
            using (var barcodeGenerator = new BarcodeGenerator(EncodeTypes.MacroPdf417, dataToEncode))
            {
                // 1️⃣ Define module size (pixel width of each bar).
                barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;

                // 2️⃣ Configure Macro PDF417 options.
                barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 5;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 1;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 10;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "report.pdf";
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 0x1A2B;

                // 3️⃣ Save the barcode as a PNG image.
                barcodeGenerator.Save(outputPath, BarCodeImageFormat.Png);
            }

            Console.WriteLine($"PDF417 barcode image created at: {outputPath}");
        }
    }
}
```

**プログラムの実行手順:**  

1. .NET 6（またはそれ以降）コンソールプロジェクトを新規作成します。  
2. Aspose.BarCode NuGet パッケージを追加します（`dotnet add package Aspose.BarCode`）。  
3. 生成された `Program.cs` を上記コードに置き換えます。  
4. 書き込み権限のあるフォルダに合わせて `outputPath` を調整します。  
5. ビルドして実行すると、コンソールに画像の保存場所が表示されます。

---

## よくある質問とトラブルシューティング

| 質問 | 回答 |
|------|------|
| *ラベルに対してバーコードが幅広すぎる場合は？* | `Columns` を減らすか、`XDimension.Pixels` を増やして幅と可読性のバランスを調整します。 |
| *チェックサムは必須ですか？* | チェックサムはオプションです。データ整合性が重要なシナリオでのみ設定してください。 |

## 次に学ぶべきこと

以下のチュートリアルは、本ガイドで示した手法を応用した関連トピックを扱っています。各リソースには、ステップバイステップの解説と完全なコード例が含まれており、API の追加機能や代替実装方法をマスターするのに役立ちます。

- [Create PDF417 Barcode in C# – Complete Step‑by‑Step Guide](/barcode/english/net/compact-pdf417-encoding/create-pdf417-barcode-in-c-complete-step-by-step-guide/)
- [Create PDF417 Barcode Metadata in C# – Complete Step‑by‑Step Guide](/barcode/english/net/compact-pdf417-encoding/create-pdf417-barcode-metadata-in-c-complete-step-by-step-gu/)
- [Generate barcode with text – Full PDF417 Macro Guide](/barcode/english/net/compact-pdf417-encoding/generate-barcode-with-text-full-pdf417-macro-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}