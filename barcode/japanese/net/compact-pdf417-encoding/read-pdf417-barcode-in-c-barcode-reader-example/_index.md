---
category: general
date: 2026-08-03
description: C# の BarCodeReader を使用して画像から PDF417 バーコードを読み取る – 複数のバーコードの読み取り方法も示す、完全なバーコードリーダーのサンプルです。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- read PDF417 barcode
- barcode reader example
- read multiple barcodes
- read barcodes image
language: ja
lastmod: 2026-08-03
og_description: C# の BarCodeReader サンプルで PDF417 バーコードを素早く読み取ります。ステップバイステップのガイドに従って、マクロ
  PDF417 をデコードし、画像から複数のバーコードを読み取ります。
og_image_alt: Console output of a read PDF417 barcode example in C#
og_title: C#でPDF417バーコードを読み取る – 完全なバーコードリーダーの例
schemas:
- author: Aspose
  dateModified: '2026-08-03'
  description: Read PDF417 barcode from an image using C# BarCodeReader – a complete
    barcode reader example that also shows how to read multiple barcodes.
  headline: Read PDF417 barcode in C# – barcode reader example
  type: TechArticle
- description: Read PDF417 barcode from an image using C# BarCodeReader – a complete
    barcode reader example that also shows how to read multiple barcodes.
  name: Read PDF417 barcode in C# – barcode reader example
  steps:
  - name: '**Create a new console project**'
    text: '**Create a new console project**'
  - name: '**Add the barcode library**'
    text: '**Add the barcode library**'
  - name: '**Copy the barcode image**'
    text: '**Copy the barcode image**'
  type: HowTo
tags:
- barcode
- PDF417
- C#
- .NET
title: C#でPDF417バーコードを読み取る – バーコードリーダーの例
url: /ja/net/compact-pdf417-encoding/read-pdf417-barcode-in-c-barcode-reader-example/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# C# で PDF417 バーコードを読み取る – バーコードリーダーの例

画像から PDF417 バーコードデータを読み取る必要がある場合、このガイドでは **BarCodeReader** クラスを使用した方法を示します。マクロ PDF417 を扱い、1 つの画像内の複数のバーコードを読み取ることができるバーコードリーダーの例を学びます。

バーコードを扱う際は、さまざまな画像ソースや照明条件、時にはマクロ PDF417 のような複合データに対応する必要があります。本チュートリアルでは、PDF417 バーコードをデコードし、拡張フィールドを抽出し、同じ画像から複数のバーコードを処理する方法をすべて網羅しています。最後まで進めば、画像ファイルからバーコードを読み取り、コンソールに詳細情報を出力する実行可能なコンソールプログラムが完成します。

## 必要なもの

開始する前に、以下がインストールされていることを確認してください。

* .NET 6.0 SDK 以降  
* **Aspose.BarCode for .NET** の最新バージョン NuGet パッケージ（または `BarCodeReader` と `DecodeType.MacroPdf417` を提供する互換ライブラリ）  
* PDF417 またはマクロ PDF417 バーコードを含む画像ファイル（サンプルでは `ExtPDF417Meta.png` を使用）  
* Visual Studio 2022 などのコードエディタまたは IDE  

追加のサービスや外部 API は必要ありません。

## バーコード読み取りプロジェクトのセットアップ

1. **新しいコンソールプロジェクトを作成**  

   ```bash
   dotnet new console -n Pdf417ReaderDemo
   cd Pdf417ReaderDemo
   ```

2. **バーコードライブラリを追加**  

   ```bash
   dotnet add package Aspose.BarCode --version 23.12
   ```

3. **バーコード画像をコピー**  

   `ExtPDF417Meta.png`（または PDF417 バーコードを含む任意の画像）をプロジェクトフォルダーに配置します。  
   本チュートリアルではファイルが `YOUR_DIRECTORY/ExtPDF417Meta.png` にあるものとします。

これでプロジェクトはコンパイルおよび実行できるバーコードリーダーの例の準備が整いました。

## BarCodeReader で PDF417 バーコードを読む方法

解決策の核心は、`BarCodeReader` インスタンスを作成し、`DecodeType.MacroPdf417` を指定して、検出されたすべてのバーコードを反復処理する `using` ブロックです。以下のコードは、`Program.cs` に貼り付けて使用できる、完全かつ自己完結型のプログラムです。

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

class Program
{
    static void Main()
    {
        // Path to the image that contains one or more PDF417 barcodes
        const string imagePath = "YOUR_DIRECTORY/ExtPDF417Meta.png";

        // Step 1: Create a BarCodeReader for a macro PDF417 image
        using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
        {
            // Step 2: Read all barcodes from the image
            foreach (BarCodeResult result in reader.ReadBarCodes())
            {
                // Step 3: Output basic barcode information
                Console.WriteLine($"CodeType: {result.CodeTypeName}");
                Console.WriteLine($"CodeText: {result.CodeText}");

                // Step 4: Output macro PDF417 specific fields
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
                Console.WriteLine(new string('-', 40));
            }

            // Pro tip: If no barcodes are found, ReadBarCodes() returns an empty collection.
            // You can check reader.HasBarcodes for a quick boolean test.
            if (!reader.HasBarcodes)
            {
                Console.WriteLine("No barcodes detected in the provided image.");
            }
        }
    }
}
```

**このコードが機能する理由**  

* `DecodeType.MacroPdf417` は、PDF417 のマクロ拡張（ファイル ID、セグメント数、タイムスタンプなどの追加メタデータ）を検索するようリーダーに指示します。  
* `using` 文は、アンマネージドリソース（ファイルハンドルやネイティブデコードバッファ）を速やかに解放することを保証します。  
* `foreach` ループは、画像に含まれる **すべて** のバーコードを自動的に処理し、*複数バーコードの読み取り* 要件を満たします。  

プログラムを実行 (`dotnet run`) すると、以下のような出力が表示されます。

```
CodeType: MacroPdf417
CodeText: https://example.com/document.pdf
Pdf417MacroFileID: 12345
Pdf417MacroSegmentID: 1
Pdf417MacroSegmentsCount: 3
Pdf417MacroFileName: document.pdf
Pdf417MacroChecksum: 0x1A2B
Pdf417MacroFileSize: 204800
Pdf417MacroTimeStamp: 2024-07-15T10:25:00Z
Pdf417MacroAddressee: John Doe
Pdf417MacroSender: Acme Corp
MacroPdf417Terminator: True
----------------------------------------
```

画像に複数の PDF417 バーコードが含まれている場合、ループは各バーコードごとに別々のブロックを出力し、**1 つの画像から複数バーコードを読む** 方法を示します。

## 画像から複数のバーコードを読む

同じ `BarCodeReader` インスタンスで、複数のバーコードタイプを同時にデコードできます。マクロ PDF417 のみから、任意の PDF417（あるいは QR、Code128 など）へ範囲を広げるには、`DecodeType` フラグを調整します。

```csharp
using (BarCodeReader reader = new BarCodeReader(imagePath,
       DecodeType.Pdf417 | DecodeType.MacroPdf417 | DecodeType.QR | DecodeType.Code128))
{
    // The rest of the code stays unchanged.
}
```

*`DecodeType`* はビットマスクなので、サポートされているフォーマットを任意の数だけ組み合わせられます。この柔軟性により、スニペットは **バーコードリーダーの例** として、製品ラベル、チケット、ID カードなど、さまざまなユースケースに対応できます。

## マクロ PDF417 フィールドを安全に取得する

マクロ PDF417 には豊富な拡張プロパティが含まれますが、すべてのバーコードがすべてのフィールドを持つわけではありません。存在しないプロパティにアクセスすると `NullReferenceException` がスローされる可能性があります。最も安全な方法は、各プロパティを出力する前に存在を確認することです。

```csharp
var macro = result.Extended?.Pdf417;
if (macro != null)
{
    Console.WriteLine($"Pdf417MacroFileID: {macro.MacroPdf417FileID ?? "N/A"}");
    // Repeat for other fields...
}
```

*このチェックが重要な理由*: 実運用では、マクロデータを含まない普通の PDF417 バーコードが届くことがあります。防御的チェックを入れることで、アプリケーションがクラッシュせずに動作し続けます。

## よくある落とし穴とベストプラクティス

| 問題 | 発生原因 | 推奨される対策 |
|------|----------|----------------|
| 画像パスが間違っている | `BarCodeReader` がデコード前にファイル未検出例外をスローする | `Path.Combine` を使用し、`File.Exists` でファイルの存在を検証する |
| 低解像度画像 | デコーダがバーコードのエッジを検出できず、検出件数が 0 になる | 信頼性のある結果を得るために最低 300 dpi の解像度を確保する |
| バーコードが 45° 超で回転している | 多くのライブラリは正立姿勢を前提としている | 必要に応じて `reader.RecognitionOptions.RotateImage = true` を有効にする |

## 次に学ぶべきことは？

以下のチュートリアルは、本ガイドで示したテクニックを基にした、密接に関連するトピックを取り上げています。各リソースには、ステップバイステップの解説と完全な動作コード例が含まれており、追加の API 機能を習得したり、独自プロジェクトで代替実装アプローチを探求したりするのに役立ちます。

- [How to Read DataMatrix Barcodes with Aspose.BarCode for .NET](/barcode/english/net/datamatrix-barcode-reading/)
- [Read DataMatrix barcode C# – Generate DataMatrix Mode (Auto)](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-auto/)
- [Read Barcode from Image – Mastering Barcode Region Extraction in Java with Aspose.BarCode](/barcode/english/java/advanced-settings-and-optimization/extracting-barcode-region-information/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}