---
category: general
date: 2026-08-15
description: C# の BarCodeReader を使用して画像からバーコードを読み取ります。C# で複数のバーコードを読み取る方法、PDF417 バーコードの読み取り方法、そして完全な
  C# BarCodeReader のサンプルをご覧ください。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- read barcode from image
- read multiple barcodes c#
- how to read pdf417 barcode
- c# barcodereader example
language: ja
lastmod: 2026-08-15
og_description: ステップバイステップのガイドでC#を使って画像からバーコードを読み取ります。C#で複数のバーコードを読み取る方法、PDF417シンボルをデコードする方法、そして完全なC#
  BarCodeReader のサンプルを実行する方法をご紹介します。
og_image_alt: Screenshot of C# code that reads barcode from image using BarCodeReader
og_title: C#で画像からバーコードを読み取る – BarCodeReaderチュートリアル
schemas:
- author: Aspose
  dateModified: '2026-08-15'
  description: Read barcode from image in C# using BarCodeReader. Learn how to read
    multiple barcodes C#, read PDF417 barcode, and see a full C# BarCodeReader example.
  headline: Read barcode from image in C# – BarCodeReader tutorial
  type: TechArticle
tags:
- barcode
- C#
- .NET
- image processing
title: C#で画像からバーコードを読み取る – BarCodeReaderチュートリアル
url: /ja/net/one-dimensional-barcode-types/read-barcode-from-image-in-c-barcodereader-tutorial/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 画像からバーコードを読み取る（C#） – BarCodeReader チュートリアル

.NET アプリケーションで **画像からバーコードを読み取る** 必要がある場合、このガイドでは `BarCodeReader` クラスを使った具体的な手順を示します。**C# で複数のバーコードを読み取る** 方法や PDF417 シンボルのデコード、プロジェクトにそのまま貼り付けられる **C# BarCodeReader の完全サンプル** も紹介します。

チュートリアルは、必要な NuGet パッケージの追加から拡張 PDF417 フィールドの出力まで、すべての手順を網羅しています。外部ドキュメントは不要で、コードと解説がすべて含まれています。

## 必要な環境

開始する前に、以下を用意してください。

* .NET 6.0 SDK 以降（コードは .NET Core と .NET Framework でも動作します）
* Visual Studio 2022 または任意の C# 対応エディタ
* `Aspose.BarCode` NuGet パッケージ（または `BarCodeReader` を提供する同等のライブラリ）
* Macro PDF417 バーコードを含む画像ファイル（例: `ExtPDF417Meta.png`）

これらの前提条件が揃っていれば、追加設定なしでサンプルをコンパイルできます。

## BarCodeReader で画像からバーコードを読み取る

最初のステップは、画像ファイルを指し示し、対象のバーコードタイプを指定した `BarCodeReader` インスタンスを作成することです。

```csharp
using System;
using Aspose.BarCode;               // Namespace for BarCodeReader
using Aspose.BarCode.BarCodeRecognition; // DecodeType enum

class Program
{
    static void Main()
    {
        // Path to the image that holds the Macro PDF417 barcode
        const string imagePath = @"YOUR_DIRECTORY/ExtPDF417Meta.png";

        // Initialize the reader for Macro PDF417 barcodes only
        using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
        {
            // Read all barcodes present in the image
            foreach (BarCodeResult result in reader.ReadBarCodes())
            {
                // Basic barcode information
                Console.WriteLine($"Code Type : {result.CodeTypeName}");
                Console.WriteLine($"Code Text : {result.CodeText}");

                // Extended Macro PDF417 fields (available only for this type)
                Console.WriteLine($"File ID          : {result.Extended.Pdf417.MacroPdf417FileID}");
                Console.WriteLine($"Segment ID       : {result.Extended.Pdf417.MacroPdf417SegmentID}");
                Console.WriteLine($"Segments Count   : {result.Extended.Pdf417.MacroPdf417SegmentsCount}");
                Console.WriteLine($"File Name        : {result.Extended.Pdf417.MacroPdf417FileName}");
                Console.WriteLine($"Checksum         : {result.Extended.Pdf417.MacroPdf417Checksum}");
                Console.WriteLine($"File Size        : {result.Extended.Pdf417.MacroPdf417FileSize}");
                Console.WriteLine($"Time Stamp       : {result.Extended.Pdf417.MacroPdf417TimeStamp}");
                Console.WriteLine($"Addressee        : {result.Extended.Pdf417.MacroPdf417Addressee}");
                Console.WriteLine($"Sender           : {result.Extended.Pdf417.MacroPdf417Sender}");
                Console.WriteLine($"Terminator Flag  : {result.Extended.Pdf417.MacroPdf417Terminator}");
                Console.WriteLine(new string('-', 40));
            }
        }
    }
}
```

**このコードが機能する理由:**  
`BarCodeReader` は画像を開き、指定した `DecodeType` をスキャンし、`BarCodeResult` オブジェクトのコレクションを返します。各結果には汎用バーコードデータ（`CodeTypeName`、`CodeText`）が含まれ、Macro PDF417 の場合は標準で定義されたすべての追加フィールドを公開する `Extended.Pdf417` オブジェクトが取得できます。

## 1 つの画像から複数のバーコードを C# で読み取る

画像に複数のバーコードが含まれることがあります（例: QR コードと PDF417 が隣り合っている場合）。そのようなシナリオでは、明示的な `DecodeType` を省略するか `DecodeType.AllSupported` を渡して結果をループ処理します。

```csharp
using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.AllSupported))
{
    foreach (BarCodeResult result in reader.ReadBarCodes())
    {
        Console.WriteLine($"Found {result.CodeTypeName}: {result.CodeText}");
    }
}
```

**この手法が必要な理由:**  
`AllSupported` を指定すると、エンジンはサポートしているすべてのバーコード形式を試行します。これにより、画像内のすべてのシンボルを確実に取得でき、事前にバーコードタイプを予測できない場合に推奨されます。

## C# で PDF417 バーコードを読み取る方法

クラシックな PDF417（マクロなし）だけが必要な場合は、`DecodeType` を `Pdf417` に変更します。残りのコードは同一ですが、拡張フィールドは利用できません。

```csharp
using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.Pdf417))
{
    foreach (BarCodeResult result in reader.ReadBarCodes())
    {
        Console.WriteLine($"PDF417 text: {result.CodeText}");
    }
}
```

**この違いが重要な理由:**  
クラシック PDF417 ではマクロ固有のプロパティが公開されないため、`Extended.Pdf417` ブロックは不要です。正確な `DecodeType` を指定することで、未対応アルゴリズムをスキップし、スキャン速度が向上します。

## コピー可能な完全 C# BarCodeReader サンプル

以下は、上記 3 つのシナリオを 1 つの実行可能なコンソール アプリケーションに統合した完全プログラムです。`YOUR_DIRECTORY/ExtPDF417Meta.png` を実際の画像パスに置き換えてください。

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

class Program
{
    static void Main()
    {
        const string imagePath = @"YOUR_DIRECTORY/ExtPDF417Meta.png";

        // 1️⃣ Read Macro PDF417 and show extended fields
        Console.WriteLine("=== Macro PDF417 ===");
        ReadMacroPdf417(imagePath);

        // 2️⃣ Read any barcode type present (multiple barcodes)
        Console.WriteLine("\n=== All supported barcodes ===");
        ReadAllBarcodes(imagePath);

        // 3️⃣ Read classic PDF417 only
        Console.WriteLine("\n=== Classic PDF417 ===");
        ReadClassicPdf417(imagePath);
    }

    static void ReadMacroPdf417(string path)
    {
        using (BarCodeReader reader = new BarCodeReader(path, DecodeType.MacroPdf417))
        {
            foreach (BarCodeResult result in reader.ReadBarCodes())
            {
                Console.WriteLine($"Code Type : {result.CodeTypeName}");
                Console.WriteLine($"Code Text : {result.CodeText}");
                Console.WriteLine($"File ID   : {result.Extended.Pdf417.MacroPdf417FileID}");
                // ... other extended fields omitted for brevity
                Console.WriteLine(new string('-', 30));
            }
        }
    }

    static void ReadAllBarcodes(string path)
    {
        using (BarCodeReader reader = new BarCodeReader(path, DecodeType.AllSupported))
        {
            foreach (BarCodeResult result in reader.ReadBarCodes())
            {
                Console.WriteLine($"{result.CodeTypeName}: {result.CodeText}");
            }
        }
    }

    static void ReadClassicPdf417(string path)
    {
        using (BarCodeReader reader = new BarCodeReader(path, DecodeType.Pdf417))
        {
            foreach (BarCodeResult result in reader.ReadBarCodes())
            {
                Console.WriteLine($"PDF417 text: {result.CodeText}");
            }
        }
    }
}
```

### 期待される出力

サンプル画像に Macro PDF417 バーコードが含まれている場合、コンソールには次のような内容が表示されます。

```
=== Macro PDF417 ===
Code Type : MacroPdf417
Code Text : 1234567890
File ID   : 5
Segment ID       : 2
Segments Count   : 3
File Name        : report.pdf
Checksum         : 0x1A2B
File Size        : 84212
Time Stamp       : 2024-03-15T10:22:31Z
Addressee        : John Doe
Sender           : Acme Corp
Terminator Flag  : True
------------------------------

=== All supported barcodes ===
MacroPdf417: 1234567890
QrCode: https://example.com

=== Classic PDF417 ===
PDF417 text: 0987654321
```

画像が通常の PDF417 のみの場合は、「Macro PDF417」セクションは空になり、「Classic PDF417」セクションにデコードされたテキストが表示されます。

## 結論

これで、`BarCodeReader` を使用した **C# で画像からバーコードを読み取る** 方法、**1 つのファイルで複数のバーコードを読み取る** 方法、そして **PDF417 バーコード（マクロ版・クラシック版）を読み取る** 正確な手順が分かりました。完全な **C# BarCodeReader サンプル** は任意の .NET プロジェクトに貼り付けてすぐに使用でき、他のフォーマットへの拡張や画像処理パイプラインへの統合も容易です。

**次のステップ**

* `try / catch` を使用したエラーハンドリング パターンをリーダー ブロック周辺に実装してみましょう。  
* `ReaderParameters` オブジェクトで検出速度と精度を調整してみてください。  
* バーコード読み取りと画像前処理ライブラリを組み合わせて（

## 次に学ぶべきことは？

以下のチュートリアルは、本ガイドで示したテクニックを基にした関連トピックを扱っています。各リソースには、ステップバイステップの解説と完全な動作コード例が含まれており、API の追加機能を習得したり、独自の実装アプローチを探求したりするのに役立ちます。

- [Aspose.BarCode for .NET で DataMatrix バーコードを読む方法](/barcode/english/net/datamatrix-barcode-reading/)
- [DataMatrix バーコード C# で読み取る – DataMatrix モード（自動）を生成](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-auto/)
- [画像からバーコードを読み取る – Java で Aspose.BarCode を使用したバーコード領域抽出のマスター](/barcode/english/java/advanced-settings-and-optimization/extracting-barcode-region-information/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}