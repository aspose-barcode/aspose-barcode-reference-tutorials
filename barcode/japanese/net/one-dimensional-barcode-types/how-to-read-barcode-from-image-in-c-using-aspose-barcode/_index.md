---
category: general
date: 2026-10-18
description: Aspose.BarCode を使用して C# で画像からバーコードを読み取る方法を学び、Macro PDF417 のメタデータ抽出と完全なサンプルコードをカバーします。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to read barcode from image
- C# barcode reader
- Macro PDF417 metadata
- BarCodeReader class
- DecodeType.MacroPdf417
- barcode metadata extraction
language: ja
lastmod: 2026-10-18
og_description: C# Aspose.BarCode を使用して画像からバーコードを読み取る方法。ステップバイステップのチュートリアルに従って、Macro
  PDF417 のメタデータを抽出し、一般的なシナリオに対応しましょう。
og_image_alt: Screenshot showing output of how to read barcode from image with C#
  Aspose.BarCode
og_title: C#で画像からバーコードを読み取る方法 – 完全なAspose.BarCodeガイド
schemas:
- author: Aspose
  dateModified: '2026-10-18'
  description: Learn how to read barcode from image in C# with Aspose.BarCode, covering
    Macro PDF417 metadata extraction and complete sample code.
  headline: How to read barcode from image in C# using Aspose.BarCode
  type: TechArticle
- description: Learn how to read barcode from image in C# with Aspose.BarCode, covering
    Macro PDF417 metadata extraction and complete sample code.
  name: How to read barcode from image in C# using Aspose.BarCode
  steps:
  - name: Expected console output
    text: '``` CodeType: MacroPdf417 CodeText: https://example.com/document.pdf MacroFileID:
      12345 MacroSegmentID: 1 MacroSegmentsCount: 3 MacroFileName: document.pdf MacroChecksum:
      0x1A2B3C4D MacroFileSize: 204800 MacroTimeStamp: 2023-07-15T10:23:45Z MacroAddressee:
      Acme Corp MacroSender: Warehouse 7 MacroTer'
  - name: Large images
    text: 'Reading very large images can consume significant memory. Use the `BarcodeReader`
      overload that accepts `ReaderParameters` to limit the maximum image size:'
  - name: Missing or corrupted metadata
    text: If any of the Macro fields are missing, the corresponding property returns
      `null` or `0`. Log these cases and decide whether to treat the barcode as incomplete.
  - name: Multiple barcode types in one image
    text: 'If an image may contain other barcode formats, you can pass an array of
      `DecodeType` values:'
  type: HowTo
tags:
- barcode
- C#
- Aspose.BarCode
title: Aspose.BarCode を使用して C# で画像からバーコードを読み取る方法
url: /ja/net/one-dimensional-barcode-types/how-to-read-barcode-from-image-in-c-using-aspose-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# C# と Aspose.BarCode を使用して画像からバーコードを読み取る方法

.NET アプリケーションで **画像からバーコードを読み取る方法** が必要な場合、このガイドでは Aspose.BarCode を使用した正確な手順を示します。スキャンした文書、領収書、在庫タグなどを処理する場合でも、バーコードの読み取り、Macro PDF417 メタデータの取得、一般的なエッジケースの処理方法が分かります。

画像からバーコードを読み取ることは日常的なタスクですが、拡張された Macro PDF417 フィールドを抽出することで複雑さが増します。このチュートリアルでは、プロジェクトのセットアップから完全に実行可能なサンプルまでの全ワークフローをカバーし、コードをコピー＆ペーストしてすぐに結果を確認できるようにします。

## 学べること

- Aspose.BarCode を C# プロジェクトに設定する方法。  
- Macro PDF417 画像用の **C# barcode reader** を正しくインスタンス化する方法。  
- 検出された各バーコードを反復処理し、基本情報を出力する方法。  
- ファイル ID、セグメント ID、チェックサムなどの **Macro PDF417 メタデータ** にアクセスする方法。  
- メタデータの欠落、大きな画像、一般的なデコードエラーの処理に関するヒント。  

**前提条件**

- .NET 6.0（またはそれ以降）がインストールされていること。  
- C# と Visual Studio（任意の IDE 可）に基本的な慣れがあること。  
- Macro PDF417 バーコードを含む画像ファイル（例: `ExtPDF417Meta.png`）が用意されていること。  

## 手順 1: Aspose.BarCode のインストール

プロジェクト フォルダーでターミナルを開き、次のコマンドを実行します。

```bash
dotnet add package Aspose.BarCode
```

このパッケージには **BarCodeReader class** が含まれており、本チュートリアルで必要となる **C# barcode reader** 機能を実装しています。

## 手順 2: 開発環境の設定

まだコンソール アプリケーションがない場合は新規作成します。

```bash
dotnet new console -n BarcodeDemo
cd BarcodeDemo
```

`Program.cs` の先頭に次の `using` ディレクティブを追加します。

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;
```

これらの名前空間により、Macro PDF417 デコードに必要な **BarCodeReader class** と `DecodeType` 列挙型が利用可能になります。

## 手順 3: Macro PDF417 用に BarCodeReader を初期化

**画像からバーコードを読み取る方法** の核心は、特定の `DecodeType` を対象とした `BarCodeReader` インスタンスを作成することです。Macro PDF417 の場合は `DecodeType.MacroPdf417` を渡す必要があります。

```csharp
// Step 3: Create a barcode reader for a Macro PDF417 image
using (BarCodeReader reader = new BarCodeReader(
           "YOUR_DIRECTORY/ExtPDF417Meta.png", DecodeType.MacroPdf417))
{
    // The reader is now ready to scan the image.
}
```

**なぜ重要か:**  
`DecodeType.MacroPdf417` を選択すると、ライブラリは基本的なバーコード データを超える追加フィールドを含む拡張 Macro PDF417 フォーマットを検索します。汎用の `DecodeType.Pdf417` を使用すると、これらの追加フィールドは無視されます。

## 手順 4: 検出されたバーコードを反復処理

1 つの画像に複数のバーコードが含まれることがあります。`ReadBarCodes()` メソッドは `BarCodeResult` オブジェクトの列挙可能なコレクションを返します。これらをループして各バーコードの基本情報を出力します。

```csharp
foreach (BarCodeResult result in reader.ReadBarCodes())
{
    Console.WriteLine($"CodeType: {result.CodeTypeName}");
    Console.WriteLine($"CodeText: {result.CodeText}");
}
```

`CodeTypeName` は正確なバーコード シンボロジー（例: “MacroPdf417”）を示し、`CodeText` はデコードされた文字列を保持します。

## 手順 5: Macro PDF417 メタデータの抽出と表示

バーコードが Macro PDF417 の場合、`Extended.Pdf417` プロパティが豊富なメタデータ フィールドを提供します。以下のように直接アクセスします。

```csharp
Console.WriteLine($"MacroFileID: {result.Extended.Pdf417.MacroPdf417FileID}");
Console.WriteLine($"MacroSegmentID: {result.Extended.Pdf417.MacroPdf417SegmentID}");
Console.WriteLine($"MacroSegmentsCount: {result.Extended.Pdf417.MacroPdf417SegmentsCount}");
Console.WriteLine($"MacroFileName: {result.Extended.Pdf417.MacroPdf417FileName}");
Console.WriteLine($"MacroChecksum: {result.Extended.Pdf417.MacroPdf417Checksum}");
Console.WriteLine($"MacroFileSize: {result.Extended.Pdf417.MacroPdf417FileSize}");
Console.WriteLine($"MacroTimeStamp: {result.Extended.Pdf417.MacroPdf417TimeStamp}");
Console.WriteLine($"MacroAddressee: {result.Extended.Pdf417.MacroPdf417Addressee}");
Console.WriteLine($"MacroSender: {result.Extended.Pdf417.MacroPdf417Sender}");
Console.WriteLine($"MacroTerminator: {result.Extended.Pdf417.MacroPdf417Terminator}");
```

これらのフィールドにより、元のマルチセグメント ファイルの再構築、整合性の検証、特定のドキュメントや送信者との関連付けに必要なすべてが得られます。

### 期待されるコンソール出力

```
CodeType: MacroPdf417
CodeText: https://example.com/document.pdf
MacroFileID: 12345
MacroSegmentID: 1
MacroSegmentsCount: 3
MacroFileName: document.pdf
MacroChecksum: 0x1A2B3C4D
MacroFileSize: 204800
MacroTimeStamp: 2023-07-15T10:23:45Z
MacroAddressee: Acme Corp
MacroSender: Warehouse 7
MacroTerminator: END
```

画像に Macro PDF417 バーコードが含まれていない場合、`Extended.Pdf417` オブジェクトは `null` になります。`NullReferenceException` を回避するために必ずチェックしてください。

```csharp
if (result.Extended?.Pdf417 != null)
{
    // Safe to read metadata
}
else
{
    Console.WriteLine("No Macro PDF417 metadata found.");
}
```

## 手順 6: 一般的なエラーとエッジケースの処理

### 大きな画像

非常に大きな画像を読み込むとメモリ使用量が増大します。`ReaderParameters` を受け取る `BarcodeReader` のオーバーロードを使用して、最大画像サイズを制限してください。

```csharp
ReaderParameters parameters = new ReaderParameters
{
    MaxImageSize = 4096 // pixels
};

using (BarCodeReader reader = new BarCodeReader(
           "large_image.png", DecodeType.MacroPdf417, parameters))
{
    // Process as before
}
```

### メタデータの欠落または破損

Macro フィールドのいずれかが欠落している場合、対応するプロパティは `null` または `0` を返します。これらのケースをログに記録し、バーコードを不完全とみなすかどうかを判断してください。

### 1 つの画像に複数のバーコードタイプがある場合

画像に他のバーコード形式が含まれる可能性がある場合は、`DecodeType` 値の配列を渡すことができます。

```csharp
DecodeType[] types = { DecodeType.MacroPdf417, DecodeType.QR, DecodeType.Code128 };
using (BarCodeReader reader = new BarCodeReader("mixed.png", types))
{
    // Iterate as before
}
```

このアプローチにより、**画像からバーコードを読み取る方法** のロジックを柔軟に保ちつつ、パフォーマンスを犠牲にしません。

## 手順 7: 完全なソースコード

以下に完全な実行可能プログラムを示します。`YOUR_DIRECTORY/ExtPDF417Meta.png` をご自身の画像パスに置き換えてください。

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

namespace BarcodeDemo
{
    class Program
    {
        static void Main(string[] args)
        {
            // Path to the image containing a Macro PDF417 barcode
            const string imagePath = "YOUR_DIRECTORY/ExtPDF417Meta.png";

            // Initialize the C# barcode reader for Macro PDF417
            using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
            {
                // Iterate over all detected barcodes
                foreach (BarCodeResult result in reader.ReadBarCodes())
                {
                    Console.WriteLine($"CodeType: {result.CodeTypeName}");
                    Console.WriteLine($"CodeText: {result.CodeText}");

                    // Safely access Macro PDF417 metadata
                    if (result.Extended?.Pdf417 != null)
                    {
                        Console.WriteLine($"MacroFileID: {result.Extended.Pdf417.MacroPdf417FileID}");
                        Console.WriteLine($"MacroSegmentID: {result.Extended.Pdf417.MacroPdf417SegmentID}");
                        Console.WriteLine($"MacroSegmentsCount: {result.Extended.Pdf417.MacroPdf417SegmentsCount}");
                        Console.WriteLine($"MacroFileName: {result.Extended.Pdf417.MacroPdf417FileName}");
                        Console.WriteLine($"MacroChecksum: {result.Extended.Pdf417.MacroPdf417Checksum}");
                        Console.WriteLine($"MacroFileSize: {result.Extended.Pdf417.MacroPdf417FileSize}");
                        Console.WriteLine($"MacroTimeStamp: {result.Extended.Pdf417.MacroPdf417TimeStamp}");
                        Console.WriteLine($"MacroAddressee: {result.Extended.Pdf417.MacroPdf417Addressee}");
                        Console.WriteLine($"MacroSender: {result.Extended.Pdf417.MacroPdf417Sender}");
                        Console.WriteLine($"MacroTerminator: {result.Extended.Pdf417.MacroPdf417Terminator}");
                    }
                    else
                    {
                        Console.WriteLine("No Macro PDF417 metadata found for this barcode.");
                    }

                    Console.WriteLine(new string('-', 40));
                }
            }

            Console.WriteLine("Barcode processing completed.");
        }
    }
}
```

次のコマンドでプログラムを実行します。

```bash
dotnet run
```

コンソールにバーコードの種類、デコードされたテキスト、利用可能なすべての Macro PDF417 フィールドが表示されます。

## 結論

このチュートリアルでは Aspose.BarCode を使用して C# で **画像からバーコードを読み取る方法** を学びました。ガイドでは **C# barcode reader** の設定方法もカバーしました。

## 次に学ぶべきことは？

以下のチュートリアルは、本ガイドで示した手法を基にした密接に関連するトピックを扱っています。各リソースには、完全な動作コード例とステップバイステップの解説が含まれており、追加の API 機能を習得し、独自プロジェクトで代替実装アプローチを検討するのに役立ちます。

- [Read barcode from image C# – complete guide with Macro PDF417](/barcode/english/net/compact-pdf417-encoding/read-barcode-from-image-c-complete-guide-with-macro-pdf417/)
- [How to create macro PDF417 barcode in C# using Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/how-to-create-macro-pdf417-barcode-in-c-using-aspose-barcode/)
- [How to read PDF417 barcode c# – complete step‑by‑step guide](/barcode/english/net/compact-pdf417-encoding/how-to-read-pdf417-in-c-complete-step-by-step-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}