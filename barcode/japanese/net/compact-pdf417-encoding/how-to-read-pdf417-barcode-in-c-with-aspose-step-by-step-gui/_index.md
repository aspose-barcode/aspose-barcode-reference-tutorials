---
category: general
date: 2026-10-24
description: Aspose.BarCode を使用して C# で PDF417 バーコードの読み取り方法を学びます。このチュートリアルでは、バーコード画像の読み取り、Macro
  PDF417 フィールドの抽出、一般的なシナリオの処理について説明します。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to read pdf417 barcode
- read barcode image c#
- read barcode with aspose
language: ja
lastmod: 2026-10-24
og_description: Aspose.BarCode を使用して C# で PDF417 バーコードを読み取る方法。画像をデコードし、Macro PDF417
  メタデータを取得し、一般的な落とし穴を回避するための完全なチュートリアルをご覧ください。
og_image_alt: Screenshot showing how to read PDF417 barcode results in a C# console
  application
og_title: Aspose を使用した C# で PDF417 バーコードを読み取る方法 – 完全ガイド
schemas:
- author: Aspose
  dateModified: '2026-10-24'
  description: Learn how to read PDF417 barcode in C# using Aspose.BarCode. This tutorial
    covers reading a barcode image, extracting Macro PDF417 fields, and handling common
    scenarios.
  headline: How to read PDF417 barcode in C# with Aspose – step‑by‑step guide
  type: TechArticle
- description: Learn how to read PDF417 barcode in C# using Aspose.BarCode. This tutorial
    covers reading a barcode image, extracting Macro PDF417 fields, and handling common
    scenarios.
  name: How to read PDF417 barcode in C# with Aspose – step‑by‑step guide
  steps:
  - name: Why use `DecodeType.MacroPdf417`?
    text: '* **Macro PDF417** stores additional fields (file ID, segment count, timestamps,
      etc.) that are not present in standard PDF417. * The `Extended` property of
      `BarCodeResult` is populated only when you request the macro type, saving you
      a separate parsing step.'
  - name: What each property means
    text: '| Property | Description | |----------|-------------| | **MacroPdf417FileID**
      | Unique identifier for the whole multi‑segment document. | | **MacroPdf417SegmentID**
      | Index of the current segment (starting at 0). | | **MacroPdf417SegmentsCount**
      | Total number of segments that belong to the file. | '
  - name: Missing macro fields
    text: 'Sometimes a PDF417 barcode is generated without the optional macro fields.
      Accessing a missing property returns `null` or `0`. Guard against this if you
      plan to store the values:'
  - name: Corrupted or low‑quality images
    text: 'If the image is blurry, you can improve detection by enabling the `BarCodeReader`
      quality options:'
  - name: Multiple barcode formats in one image
    text: 'If you suspect other barcode types might be present, use `DecodeType.AllSupported`
      and filter results:'
  type: HowTo
- questions:
  - answer: Yes. Change `DecodeType.MacroPdf417` to `DecodeType.Pdf417`. The `Extended`
      property will be empty, but `CodeText` and `CodeTypeName` remain available.
    question: Can I read a standard PDF417 (non‑macro) with the same code?
  - answer: Absolutely. Use the overload `new BarCodeReader(Stream, DecodeType)` and
      pass a `FileStream` or `MemoryStream`. This is useful when the image comes from
      a web API.
    question: Does Aspose.BarCode support reading from a stream instead of a file
      path?
  - answer: 'The `MacroPdf417Checksum` field contains the raw CRC‑16 value. You can
      recompute the checksum on the reconstructed file and compare it to ensure data
      integrity. ## Next steps and related topics * **Write PDF417 barcodes** – explore
      `BarCodeGenerator` to create macro barcodes for testing. * **Combine'
    question: How do I validate the checksum?
  type: FAQPage
tags:
- barcode
- Aspose.BarCode
- C#
title: Aspose を使用した C# で PDF417 バーコードを読み取る方法 – ステップバイステップガイド
url: /ja/net/compact-pdf417-encoding/how-to-read-pdf417-barcode-in-c-with-aspose-step-by-step-gui/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# C# と Aspose で PDF417 バーコードを読み取る方法 – ステップバイステップガイド

.NET アプリケーションで **PDF417 バーコードの読み取り方法** が必要な場合、本ガイドでは Aspose.BarCode ライブラリを使用して C# で PDF417 バーコードを読み取る手順を正確に示します。スキャンした文書、モバイルで取得した画像、またはバッチインポートされた画像を処理する際、以下のコードはバーコードをデコードし、必要になる可能性のあるすべての Macro PDF417 プロパティを抽出します。

C# でバーコード画像を読み取るのは、特に拡張メタデータが含まれる場合はハードルが高く感じられます。このチュートリアルでは、完全に実行可能なサンプルを提供し、各行を解説し、マクロセグメントが欠落している場合や画像が破損している場合といったエッジケースも網羅します。最後まで読めば、どの C# プロジェクトにも自信を持って PDF417 デコードを組み込めるようになります。

## 前提条件

開始する前に、以下が揃っていることを確認してください。

* .NET 6.0 SDK 以降がインストールされていること  
* Visual Studio 2022（または .NET をサポートする任意の IDE）  
* **Aspose.BarCode for .NET** のライセンスまたは無料評価版 – Aspose のウェブサイトから一時キーを取得できます  
* Macro PDF417 バーコードを含む画像ファイル（例: `ExtPDF417Meta.png`）

> **プロのコツ:** 試したいだけの場合は、Aspose が提供する 30 日間のトライアルを利用すると、バーコード読み取り機能がフルに使えます。

## 手順 1: Aspose.BarCode NuGet パッケージをインストールする

ターミナルでプロジェクトフォルダーを開き、次のコマンドを実行します。

```bash
dotnet add package Aspose.BarCode
```

このパッケージは `Aspose.BarCode.ReadRecognition` 名前空間を追加し、画像をデコードするために使用する `BarCodeReader` クラスが含まれます。

## 手順 2: PDF417 画像用の BarCodeReader を作成する

`BarCodeReader` コンストラクターは 2 つの引数を受け取ります: 画像ファイルへのパスと対象とする `DecodeType`。`DecodeType.MacroPdf417` を指定すると、Aspose は Macro PDF417 シンボルを検索し、拡張プロパティを自動的に設定します。

```csharp
using Aspose.BarCode.ReadRecognition;

// Replace with the actual path to your barcode image
string imagePath = @"C:\Barcodes\ExtPDF417Meta.png";

using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
{
    // The reader is now ready to scan the image
```

### なぜ `DecodeType.MacroPdf417` を使うのか？

* **Macro PDF417** は、標準 PDF417 にはない追加フィールド（ファイル ID、セグメント数、タイムスタンプなど）を格納します。  
* `BarCodeResult` の `Extended` プロパティは、マクロタイプを要求したときにのみ自動的に埋められ、別途パースする手間が省けます。

## 手順 3: 検出されたすべてのバーコードを列挙する

1 つの画像に複数の PDF417 シンボルが含まれることがあります（例: 文書が複数ページに分割されている場合）。`ReadBarCodes()` メソッドは `IEnumerable<BarCodeResult>` を返すので、`foreach` でループできます。

```csharp
    foreach (BarCodeResult result in reader.ReadBarCodes())
    {
        // Basic information
        Console.WriteLine($"CodeType: {result.CodeTypeName}");
        Console.WriteLine($"CodeText: {result.CodeText}");
```

画像にバーコードが含まれていない場合、ループは一度も実行されず、プログラムは静かに終了します。この挙動は、ファイルの一部にバーコードが存在しないバッチ処理に最適です。

## 手順 4: Macro PDF417 の拡張プロパティを出力する

`Extended.Pdf417` プロパティはマクロ固有のすべてのフィールドをまとめています。各フィールドは PDF417 仕様に直接対応しているため、データベースに保存したり、ログに記録したり、さらなる検証に利用できます。

```csharp
        // Macro PDF417 extended properties
        Console.WriteLine($"Pdf417MacroFileID: {result.Extended.Pdf417.MacroPdf417FileID}");
        Console.WriteLine($"Pdf417MacroSegmentID: {result.Extended.Pdf417.MacroPdf417SegmentID}");
        Console.WriteLine($"Pdf417MacroSegmentsCount: {result.Extended.Pdf417.MacroPdf417SegmentsCount}");
        Console.WriteLine($"Pdf417MacroFileName: {result.Extended.Pdf417.MacroPdf417FileName}");
        Console.WriteLine($"Pdf417MacroChecksum: {result.Extended.Pdf417.MacroPdf417Checksum}");
        Console.WriteLine($"Pdf417MacroFileSize: {result.Extended.Pdf417.MacroPdf417FileSize}");
        Console.WriteLine($"Pdf417MacroTimeStamp: {result.Extended.Pdf417.MacroPdf417TimeStamp}");
        Console.WriteLine($"Pdf417MacroAddressee: {result.Extended.Pdf417.MacroPdf417Addressee}");
        Console.WriteLine($"Pdf417MacroSender: {result.Extended.Pdf417.MacroPdf417Sender}");
        Console.WriteLine($"MacroPdf417Terminator: {result.Extended.Pdf417.MacroPdf417Terminator}");
    }
}
```

### 各プロパティの意味

| Property | Description |
|----------|-------------|
| **MacroPdf417FileID** | 複数セグメントからなる文書全体を一意に識別する ID |
| **MacroPdf417SegmentID** | 現在のセグメントのインデックス（0 から開始） |
| **MacroPdf417SegmentsCount** | ファイルに属するセグメントの総数 |
| **MacroPdf417FileName** | バーコードに埋め込まれた任意のファイル名 |
| **MacroPdf417Checksum** | マクロデータブロックの CRC‑16 チェックサム |
| **MacroPdf417FileSize** | 元ファイルのバイト単位サイズ |
| **MacroPdf417TimeStamp** | マクロバーコードが生成されたタイムスタンプ |
| **MacroPdf417Addressee** | 文書の受取人 |
| **MacroPdf417Sender** | 文書の送信元 |
| **MacroPdf417Terminator** | マクロシーケンスの終了を示すフラグ |

これらのフィールドは、低解像度メディア向けに印刷するために複数の PDF417 シンボルに分割された大きな PDF や画像を再構築する際に特に有用です。

## 手順 5: 一般的なエッジケースに対処する

### マクロフィールドが欠落している場合

PDF417 バーコードがオプションのマクロフィールドなしで生成されることがあります。欠落したプロパティにアクセスすると `null` または `0` が返ります。値を保存する場合は必ずチェックしてください。

```csharp
string fileName = result.Extended.Pdf417.MacroPdf417FileName ?? "Unnamed";
long fileSize = result.Extended.Pdf417.MacroPdf417FileSize;
```

### 画像が破損または低品質の場合

画像がぼやけている場合は、`BarCodeReader` の品質オプションを有効にすると検出率が向上します。

```csharp
reader.BarcodeSettings.ImageQuality = 90; // value between 0‑100
reader.BarcodeSettings.PureBarcode = false; // allow detection in noisy backgrounds
```

これらの設定は任意ですが、スキャン文書の成功率を大幅に高めることができます。

### 1 つの画像に複数のバーコード形式が混在している場合

他のバーコードタイプが存在する可能性がある場合は、`DecodeType.AllSupported` を使用し、結果をフィルタリングしてください。

```csharp
using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.AllSupported))
{
    foreach (BarCodeResult result in reader.ReadBarCodes())
    {
        if (result.CodeType == DecodeType.MacroPdf417)
        {
            // Process macro PDF417 as shown above
        }
    }
}
```

## 完全に実行可能なサンプル

以下のプログラムを新しいコンソールプロジェクト（`dotnet new console`）に貼り付けて実行してください。`imagePath` 変数を自分の Macro PDF417 画像のパスに置き換えます。

```csharp
using System;
using Aspose.BarCode.ReadRecognition;

class Program
{
    static void Main()
    {
        // Path to the barcode image
        string imagePath = @"C:\Barcodes\ExtPDF417Meta.png";

        // Initialize the reader for Macro PDF417
        using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
        {
            // Optional: improve detection on low‑quality scans
            reader.BarcodeSettings.ImageQuality = 90;
            reader.BarcodeSettings.PureBarcode = false;

            // Iterate through every barcode found in the image
            foreach (BarCodeResult result in reader.ReadBarCodes())
            {
                Console.WriteLine($"CodeType: {result.CodeTypeName}");
                Console.WriteLine($"CodeText: {result.CodeText}");

                // Output extended Macro PDF417 fields
                Console.WriteLine($"Pdf417MacroFileID: {result.Extended.Pdf417.MacroPdf417FileID}");
                Console.WriteLine($"Pdf417MacroSegmentID: {result.Extended.Pdf417.MacroPdf417SegmentID}");
                Console.WriteLine($"Pdf417MacroSegmentsCount: {result.Extended.Pdf417.MacroPdf417SegmentsCount}");
                Console.WriteLine($"Pdf417MacroFileName: {result.Extended.Pdf417.MacroPdf417FileName ?? \"N/A\"}");
                Console.WriteLine($"Pdf417MacroChecksum: {result.Extended.Pdf417.MacroPdf417Checksum}");
                Console.WriteLine($"Pdf417MacroFileSize: {result.Extended.Pdf417.MacroPdf417FileSize}");
                Console.WriteLine($"Pdf417MacroTimeStamp: {result.Extended.Pdf417.MacroPdf417TimeStamp}");
                Console.WriteLine($"Pdf417MacroAddressee: {result.Extended.Pdf417.MacroPdf417Addressee ?? \"N/A\"}");
                Console.WriteLine($"Pdf417MacroSender: {result.Extended.Pdf417.MacroPdf417Sender ?? \"N/A\"}");
                Console.WriteLine($"MacroPdf417Terminator: {result.Extended.Pdf417.MacroPdf417Terminator}");
                Console.WriteLine(new string('-', 40));
            }
        }
    }
}
```

**期待される出力**（画像に応じて値は変わります）:

```
CodeType: MacroPdf417
CodeText: 1234567890ABCDEFGHIJ
Pdf417MacroFileID: 42
Pdf417MacroSegmentID: 0
Pdf417MacroSegmentsCount: 3
Pdf417MacroFileName: Invoice_2026_10.pdf
Pdf417MacroChecksum: 32768
Pdf417MacroFileSize: 245760
Pdf417MacroTimeStamp: 2026-10-24T14:32:10Z
Pdf417MacroAddressee: AccountingDept
Pdf417MacroSender: SalesTeam
MacroPdf417Terminator: True
----------------------------------------
```

画像に Macro PDF417 シンボルが含まれていない場合、プログラムは何も出力せずに静かに終了します。多数のファイルを処理するバッチジョブに最適です。

## よくある質問

**Q: 同じコードで標準 PDF417（マクロなし）も読み取れますか？**  
A: はい。`DecodeType.MacroPdf417` を `DecodeType.Pdf417` に変更してください。`Extended` プロパティは空になりますが、`CodeText` と `CodeTypeName` は引き続き利用可能です。

**Q: Aspose.BarCode はファイルパスではなくストリームから読み取ることができますか？**  
A: もちろんです。`new BarCodeReader(Stream, DecodeType)` のオーバーロードを使用し、`FileStream` または `MemoryStream` を渡します。画像が Web API から取得される場合に便利です。

**Q: チェックサムはどのように検証しますか？**  
A: `MacroPdf417Checksum` フィールドには生の CRC‑16 値が格納されています。再構築したファイルでチェックサムを再計算し、値を比較することでデータ整合性を確認できます。

## 次のステップと関連トピック

* **PDF417 バーコードの生成** – `BarCodeGenerator` を使ってテスト用のマクロバーコードを作成します。  
* **複数セグメントの結合** – すべてのセグメントを読み取った後、`MacroPdf417SegmentID` で並び替え、`CodeText` を連結して元のペイロードを復元します。  
* **パフォーマンスチューニング** – 高スループットシナリオでは、複数画像に対して単一の `BarCodeReader` インスタンスを再利用します。

## 次に学ぶべきことは？

以下のチュートリアルは、本ガイドで示した手法を基にした、密接に関連するトピックをカバーしています。各リソースには、ステップバイステップの解説と完全なコード例が含まれており、API の追加機能を習得したり、独自プロジェクトで代替実装アプローチを探求したりするのに役立ちます。

- [How to Read PDF417 in C# – Complete Barcode Example](/barcode/english/net/compact-pdf417-encoding/how-to-read-pdf417-in-c-complete-barcode-example/)
- [How to create macro PDF417 barcode in C# using Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/how-to-create-macro-pdf417-barcode-in-c-using-aspose-barcode/)
- [Read barcode from image C# – complete guide with Macro PDF417](/barcode/english/net/compact-pdf417-encoding/read-barcode-from-image-c-complete-guide-with-macro-pdf417/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}