---
category: general
date: 2026-08-09
description: BarCodeReader を使用して C# で PDF417 を読み取る方法。バーコード PNG ファイルの読み取り、複数のバーコードの処理、拡張メタデータの抽出を学びます。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to read pdf417
- c# barcode reader
- read multiple barcodes
- read barcode png
- read barcode extended
language: ja
lastmod: 2026-08-09
og_description: C# と Aspose.BarCode を使用して PDF417 を読み取る方法。このチュートリアルでは、バーコード PNG ファイルの読み取り、1
  つの画像内の複数バーコードの処理、そして拡張 PDF417 メタデータの取得方法を示します。
og_image_alt: Screenshot of C# BarCodeReader console output displaying PDF417 metadata
og_title: C#でPDF417を読み取る方法 – バーコードリーダーのチュートリアル
schemas:
- author: Aspose
  dateModified: '2026-08-09'
  description: How to read PDF417 in C# using the BarCodeReader. Learn to read barcode
    PNG files, handle multiple barcodes, and extract extended metadata.
  headline: How to read PDF417 in C# – complete barcode reader guide
  type: TechArticle
- description: How to read PDF417 in C# using the BarCodeReader. Learn to read barcode
    PNG files, handle multiple barcodes, and extract extended metadata.
  name: How to read PDF417 in C# – complete barcode reader guide
  steps:
  - name: Verify the file exists before creating the reader.
    text: Verify the file exists before creating the reader.
  - name: Use `Image.FromFile` only when you need to pre‑process (rotate, crop). The
      `BarCodeReader` can open the file directly, which avoids extra memory allocation.
    text: Use `Image.FromFile` only when you need to pre‑process (rotate, crop). The
      `BarCodeReader` can open the file directly, which avoids extra memory allocation.
  - name: If the PNG contains transparency, the reader still works because the barcode
      is rendered on opaque pixels.
    text: If the PNG contains transparency, the reader still works because the barcode
      is rendered on opaque pixels.
  type: HowTo
tags:
- barcode
- C#
- PDF417
title: C#でPDF417を読み取る方法 – 完全なバーコードリーダーガイド
url: /ja/net/compact-pdf417-encoding/how-to-read-pdf417-in-c-complete-barcode-reader-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# C# で PDF417 を読み取る方法 – 完全なバーコードリーダーガイド

.NET アプリケーションで **PDF417 の読み取り方法** が必要な場合、このガイドはすぐに実行できるソリューションを提供します。バーコード PNG の読み取り方法、同じ画像内の複数のバーコードの処理方法、そして多くのスキャナーが隠す拡張 PDF417 フィールドの取得方法を紹介します。

PDF417 バーコードの読み取りは物流、チケット発行、文書管理で一般的です。このチュートリアルの最後までに、Macro PDF417 画像をデコードし、すべての結果を表示し、拡張情報（ファイル ID、セグメント数、タイムスタンプなど）を独自のビジネスロジックで利用できるようになります。

## 前提条件

- .NET 6.0 以降（コードは .NET Framework 4.7+ でも動作します）
- Visual Studio 2022 または任意の C# IDE
- **Aspose.BarCode for .NET**（無料トライアルまたはライセンス済み NuGet パッケージ）
- Macro PDF417 バーコードを含む PNG 画像（サンプルファイルは `ExtPDF417Meta.png`）

> **プロのコツ:** NuGet コンソールでライブラリをインストールします:  
> `dotnet add package Aspose.BarCode`

## C# の BarCodeReader で PDF417 を読み取る方法

ソリューションの核心は `BarCodeReader` クラスです。画像パスと、エンジンにどのシンボルを探すか指示する `DecodeType` 列挙型を受け取ります。

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.ReadEngine;

class Pdf417Demo
{
    static void Main()
    {
        // Step 1: Create a BarCodeReader for a Macro PDF417 image
        using (BarCodeReader reader = new BarCodeReader(
            "YOUR_DIRECTORY/ExtPDF417Meta.png",
            DecodeType.MacroPdf417))
        {
            // Step 2: Read all barcodes from the image
            foreach (BarCodeResult result in reader.ReadBarCodes())
            {
                // Step 3: Output basic barcode information
                Console.WriteLine($"CodeType: {result.CodeTypeName}");
                Console.WriteLine($"CodeText: {result.CodeText}");

                // Step 4: Display Macro PDF417 extended metadata
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
        }
    }
}
```

### なぜこれが機能するのか

- **`DecodeType.MacroPdf417`** はリーダーに Macro PDF417 バリアントを探すよう指示し、ステップ 4 で確認できる拡張フィールドを格納します。
- `using` ブロックはリーダーを自動的に破棄し、ファイルハンドルを解放します。
- `ReadBarCodes()` は要求されたタイプに一致する **すべて** のバーコードを返すため、画像に 1 つだけ含まれていても *複数バーコードの読み取り* 要件を満たします。

プログラムを実行すると、以下のような出力が表示されます:

```
CodeType: MacroPdf417
CodeText: 1234567890
Pdf417MacroFileID: 1
Pdf417MacroSegmentID: 0
Pdf417MacroSegmentsCount: 3
Pdf417MacroFileName: invoice_2023.pdf
Pdf417MacroChecksum: 0x1A2B
Pdf417MacroFileSize: 254321
Pdf417MacroTimeStamp: 2023-03-15T10:45:00Z
Pdf417MacroAddressee: ACME Corp.
Pdf417MacroSender: Warehouse 7
MacroPdf417Terminator: True
----------------------------------------
```

## C# バーコードリーダーで複数のバーコードを読み取る

画像に複数の Macro PDF417 シンボルが含まれている場合（例: チケットのバッチがスキャンされたページ）、同じ `foreach` ループがそれぞれを処理します。追加コードは不要で、リーダーが内部で結果を集約します。

```csharp
// Example: processing a batch image
using (BarCodeReader batchReader = new BarCodeReader(
    "batch.png", DecodeType.MacroPdf417))
{
    int index = 0;
    foreach (BarCodeResult item in batchReader.ReadBarCodes())
    {
        Console.WriteLine($"--- Barcode #{++index} ---");
        Console.WriteLine($"Text: {item.CodeText}");
        // extended fields are accessed the same way
    }
}
```

### よくある落とし穴

- **画像形式:** リーダーは PNG、JPEG、BMP、TIFF をサポートします。デコードできない形式を使用すると空のコレクションが返ります。これがチュートリアルで *バーコード PNG の読み取り* を強調する理由です。
- **解像度:** 低解像度画像（< 300 dpi）はセグメントの取りこぼしを引き起こす可能性があります。可能な限り高解像度のスキャンを使用するか、画像を拡大してください。
- **Macro フラグ:** `DecodeType.MacroPdf417` を忘れるとエンジンは通常の PDF417 のみを対象とし、拡張データが破棄されます。*拡張バーコードフィールドの読み取り* が必要な場合は必ず Macro タイプを指定してください。

## バーコード PNG ファイルの読み取り – ベストプラクティス

PNG はロスレスなピクセルデータを保持するため、取り扱いが簡単です。以下は簡易チェックリストです:

1. リーダーを作成する前にファイルが存在することを確認します。  
   ```csharp
   if (!File.Exists(path))
       throw new FileNotFoundException($"File not found: {path}");
   ```
2. `Image.FromFile` は前処理（回転、トリミング）が必要なときだけ使用します。`BarCodeReader` はファイルを直接開くことができ、余分なメモリ割り当てを回避できます。
3. PNG に透過が含まれていても、バーコードは不透明ピクセル上に描画されているためリーダーは正常に動作します。

## 拡張 PDF417 メタデータへのアクセス

`Extended.Pdf417` オブジェクトは PDF417 仕様で定義されたすべてのオプションフィールドを公開します。これらのフィールドをドメインモデルにマッピングしたり、データベースに保存したり、検証に利用したりできます。

```csharp
public class Pdf417Metadata
{
    public int FileID { get; set; }
    public int SegmentID { get; set; }
    public int SegmentsCount { get; set; }
    public string FileName { get; set; }
    public string Checksum { get; set; }
    public long FileSize { get; set; }
    public DateTime TimeStamp { get; set; }
    public string Addressee { get; set; }
    public string Sender { get; set; }
    public bool Terminator { get; set; }
}
```

モデルにデータを設定します:



## 次に学ぶべきことは？

以下のチュートリアルは、本ガイドで示した手法を基にした密接に関連するトピックをカバーしています。各リソースには完全な動作コード例とステップバイステップの解説が含まれており、追加の API 機能を習得し、独自プロジェクトで代替実装アプローチを検討するのに役立ちます。

- [Aspose.BarCode for .NET を使用した DataMatrix バーコードの読み取り方法](/barcode/english/net/datamatrix-barcode-reading/)
- [Aspose.BarCode でコンパクト PDF417 バーコードを作成する方法](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [DataMatrix バーコードを C# で読み取る – DataMatrix モード（自動）を生成](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-auto/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}