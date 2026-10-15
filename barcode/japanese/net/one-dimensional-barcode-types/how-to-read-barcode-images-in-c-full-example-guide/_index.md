---
category: general
date: 2026-10-15
description: C#でBarCodeReaderを使用してバーコード画像を高速に読み取る方法。複数のバーコードの読み取りを学び、Macro‑PDF417に対応したC#バーコードリーダーのサンプルをご覧ください。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to read barcode
- read multiple barcodes
- c# barcode reader example
- Macro‑PDF417 decoding
- barcode metadata extraction
language: ja
lastmod: 2026-10-15
og_description: C#でBarCodeReaderを使用してバーコードを読み取る方法。このチュートリアルでは、複数のバーコードを処理し、Macro‑PDF417メタデータを抽出する完全なC#バーコードリーダーの例を示します。
og_image_alt: Screenshot showing how to read barcode with C# BarCodeReader
og_title: C#でバーコードを読み取る方法 – ステップバイステップの例
schemas:
- author: Aspose
  dateModified: '2026-10-15'
  description: How to read barcode images in C# quickly using BarCodeReader. Learn
    to read multiple barcodes and see a c# barcode reader example that works with
    Macro‑PDF417.
  headline: How to read barcode images in C# – full example guide
  type: TechArticle
- description: How to read barcode images in C# quickly using BarCodeReader. Learn
    to read multiple barcodes and see a c# barcode reader example that works with
    Macro‑PDF417.
  name: How to read barcode images in C# – full example guide
  steps:
  - name: Initialise the `BarCodeReader`
    text: '```csharp using Aspose.BarCode; using Aspose.BarCode.BarCodeRecognition;'
  - name: Read all barcodes present in the image
    text: '```csharp // Step 2: Read all barcodes in the image BarCodeResult[] results
      = reader.ReadBarCodes(); ```'
  - name: Display basic barcode details
    text: '```csharp foreach (BarCodeResult result in results) { Console.WriteLine($"CodeType:
      {result.CodeTypeName}"); Console.WriteLine($"CodeText: {result.CodeText}");
      ```'
  - name: Retrieve and show Macro‑PDF417 specific metadata
    text: '```csharp // Macro‑PDF417 extended data Console.WriteLine($"FileID: {result.Extended.Pdf417.MacroPdf417FileID}");
      Console.WriteLine($"Segment: {result.Extended.Pdf417.MacroPdf417SegmentID}");
      Console.WriteLine($"Count: {result.Extended.Pdf417.MacroPdf417SegmentsCount}");
      Console.WriteLine($"FileName'
  - name: Full runnable program
    text: Below is a self‑contained console application that puts all four steps together.
      Copy the code into a new `.cs` file, adjust the `imagePath`, and run `dotnet
      run`.
  type: HowTo
tags:
- barcode
- C#
- Aspose.BarCode
title: C#でバーコード画像を読み取る方法 – 完全サンプルガイド
url: /ja/net/one-dimensional-barcode-types/how-to-read-barcode-images-in-c-full-example-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# C# でバーコード画像を読み取る方法 – 完全例ガイド

.NET アプリケーションで画像から **バーコードを読み取る** 方法が必要な場合、このガイドはすぐに実行できるソリューションを提供します。Macro‑PDF417 シンボルに対応し、1 枚の画像から **複数のバーコードを読み取る** ことができる **c# バーコードリーダー例** を確認できます。

バーコードの読み取りは在庫管理システム、チケット検証、文書処理などで一般的な要件です。このチュートリアルを終えると、以下ができるようになります。

* 任意のサポート対象フォーマットに対して `BarCodeReader` を初期化する。  
* コードタイプやデコードされたテキストなどの基本情報を取得する。  
* Macro‑PDF417 固有のメタデータ（ファイル ID、セグメント、チェックサム等）を取得する。  
* 余分なコードを書かずに、画像内の複数バーコードを処理する。

## 前提条件

開始する前に、以下が揃っていることを確認してください。

* .NET 6.0 SDK 以降がインストール済み。  
* 開発環境（Visual Studio 2022、VS Code、または Rider）。  
* **Aspose.BarCode for .NET** NuGet パッケージ（`Aspose.BarCode`） – 本例で使用する `BarCodeReader` クラスを提供します。  
* Macro‑PDF417 バーコードを含む画像ファイル（例: `MacroPdf417.png`）。  

NuGet パッケージは次のコマンドでインストールできます。

```bash
dotnet add package Aspose.BarCode
```

## C# で BarCodeReader を使ってバーコードを読み取る方法

ソリューションの核は 4 つの簡潔なステップに分かれています。各ステップは `using` ブロックで囲み、アンマネージドリソースが速やかに解放されるようにします。

### 手順 1: `BarCodeReader` を初期化する

```csharp
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

// Path to the image that contains the Macro‑PDF417 barcode(s)
string imagePath = @"YOUR_DIRECTORY\MacroPdf417.png";

// Initialise the reader for the specific DecodeType
using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
{
    // The remaining steps are inside this block
}
```

**ポイント:**  
`BarCodeReader` はファイルパスと `DecodeType` を受け取ります。`DecodeType.MacroPdf417` を指定すると、ライブラリは Macro‑PDF417 シンボルだけを対象に検索し、検出速度が向上し誤検出が減少します。

### 手順 2: 画像内のすべてのバーコードを読み取る

```csharp
    // Step 2: Read all barcodes in the image
    BarCodeResult[] results = reader.ReadBarCodes();
```

**ポイント:**  
`ReadBarCodes()` メソッドは、1 つまたは複数の `BarCodeResult` オブジェクトを含む配列を返します。ここが **複数のバーコードを読み取る** 機能の肝で、個別にループを書く必要がありません。

### 手順 3: 基本的なバーコード情報を表示する

```csharp
    foreach (BarCodeResult result in results)
    {
        Console.WriteLine($"CodeType: {result.CodeTypeName}");
        Console.WriteLine($"CodeText: {result.CodeText}");
```

**ポイント:**  
`CodeTypeName` は検出されたシンボル種別（例: “MacroPDF417”）を示し、`CodeText` はデコードされたペイロードを保持します。この 2 つのフィールドは下流ロジックで最も頻繁に使用されます。

### 手順 4: Macro‑PDF417 固有のメタデータを取得・表示する

```csharp
        // Macro‑PDF417 extended data
        Console.WriteLine($"FileID:    {result.Extended.Pdf417.MacroPdf417FileID}");
        Console.WriteLine($"Segment:   {result.Extended.Pdf417.MacroPdf417SegmentID}");
        Console.WriteLine($"Count:     {result.Extended.Pdf417.MacroPdf417SegmentsCount}");
        Console.WriteLine($"FileName:  {result.Extended.Pdf417.MacroPdf417FileName}");
        Console.WriteLine($"Checksum:  {result.Extended.Pdf417.MacroPdf417Checksum}");
        Console.WriteLine($"FileSize:  {result.Extended.Pdf417.MacroPdf417FileSize}");
        Console.WriteLine($"Time:      {result.Extended.Pdf417.MacroPdf417TimeStamp}");
        Console.WriteLine($"Addressee: {result.Extended.Pdf417.MacroPdf417Addressee}");
        Console.WriteLine($"Sender:    {result.Extended.Pdf417.MacroPdf417Sender}");
        Console.WriteLine($"Terminator:{result.Extended.Pdf417.MacroPdf417Terminator}");
        Console.WriteLine(new string('-', 40));
    }
}
```

**ポイント:**  
Macro‑PDF417 は通常の PDF417 に文書レベルのメタデータを付加した形式です。`Extended.Pdf417` プロパティにアクセスすることで、元ファイルの再構築や整合性検証、適切な受取人へのデータ振り分けに必要な情報がすべて取得できます。

### 完全に実行可能なプログラム

以下は 4 つの手順をすべて組み合わせた、自己完結型のコンソールアプリケーションです。コードを新しい `.cs` ファイルに貼り付け、`imagePath` を調整して `dotnet run` を実行してください。

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // ------------------------------------------------------------
            // 1️⃣ Initialise the BarCodeReader for Macro‑PDF417 images
            // ------------------------------------------------------------
            string imagePath = @"YOUR_DIRECTORY\MacroPdf417.png";

            using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
            {
                // ------------------------------------------------------------
                // 2️⃣ Read all barcodes present in the image
                // ------------------------------------------------------------
                BarCodeResult[] results = reader.ReadBarCodes();

                if (results.Length == 0)
                {
                    Console.WriteLine("No barcodes were detected.");
                    return;
                }

                // ------------------------------------------------------------
                // 3️⃣ Iterate over each result – this is where we **read multiple barcodes**
                // ------------------------------------------------------------
                foreach (BarCodeResult result in results)
                {
                    Console.WriteLine($"CodeType: {result.CodeTypeName}");
                    Console.WriteLine($"CodeText: {result.CodeText}");

                    // ------------------------------------------------------------
                    // 4️⃣ Extract Macro‑PDF417 metadata (c# barcode reader example)
                    // ------------------------------------------------------------
                    Console.WriteLine($"FileID:    {result.Extended.Pdf417.MacroPdf417FileID}");
                    Console.WriteLine($"Segment:   {result.Extended.Pdf417.MacroPdf417SegmentID}");
                    Console.WriteLine($"Count:     {result.Extended.Pdf417.MacroPdf417SegmentsCount}");
                    Console.WriteLine($"FileName:  {result.Extended.Pdf417.MacroPdf417FileName}");
                    Console.WriteLine($"Checksum:  {result.Extended.Pdf417.MacroPdf417Checksum}");
                    Console.WriteLine($"FileSize:  {result.Extended.Pdf417.MacroPdf417FileSize}");
                    Console.WriteLine($"Time:      {result.Extended.Pdf417.MacroPdf417TimeStamp}");
                    Console.WriteLine($"Addressee: {result.Extended.Pdf417.MacroPdf417Addressee}");
                    Console.WriteLine($"Sender:    {result.Extended.Pdf417.MacroPdf417Sender}");
                    Console.WriteLine($"Terminator:{result.Extended.Pdf417.MacroPdf417Terminator}");
                    Console.WriteLine(new string('-', 40));
                }
            }
        }
    }
}
```

#### 期待されるコンソール出力

```
CodeType: MacroPDF417
CodeText: https://example.com/document
FileID:    12
Segment:   3
Count:     5
FileName:  report.pdf
Checksum:  0x1A2B3C4D
FileSize:  1048576
Time:      2024-08-15T14:23:00Z
Addressee: John Doe
Sender:    Acme Corp.
Terminator:END
----------------------------------------
```

画像に複数の Macro‑PDF417 シンボルが含まれている場合、プログラムは各バーコードごとに別々のブロックを出力し、**複数のバーコードを読み取る** 機能が余分なコードなしで動作することを示します。

## 一般的なエッジケースの対処法

| 状況 | 対策 | 理由 |
|-----------|------------|--------|
| **ファイルが見つからない** | `BarCodeReader` の生成を `try/catch (FileNotFoundException)` で囲み、フレンドリーなメッセージを表示する。 | アプリケーションのクラッシュを防ぎ、欠損したアセットについてユーザーに通知できる。 |
| **バーコードが検出されない** | `results.Length == 0` をチェック（完全プログラム参照）し、適切に処理する。 | 画像にサポート対象シンボルが含まれていない場合に明確なフィードバックを提供できる。 |
| **別のバーコード種別** | `DecodeType.MacroPdf417` を `DecodeType.AllSupportedTypes` もしくは他の列挙値に変更する。 | 同一コードベースで QR、Code128、DataMatrix などにも対応でき、**複数のバーコードを読み取る** 機能を維持できる。 |
| **大きな画像** | `reader.AutoSize = true` を設定するか、画像を縮小してからリーダーに渡す。 | パフォーマンスが向上し、CLR のメモリ負荷が軽減される。 |
| **スレッドセーフな使用** | スレッドごとに別々の `BarCodeReader` インスタンスを作成する。クラス自体はスレッドセーフではない。 | マルチスレッドのスキャナーや Web サービスで競合状態を回避できる。 |

## 本番コード向けのプロティップ

* **早期に破棄:** `using` 文によりネイティブリソース（画像バッファ等）が速やかに解放されます。長時間稼働するサービスでは、各画像の処理が終わったらすぐにリーダーを破棄してください。  
* **バッチ処理**  

## 次に学ぶべきことは？

以下のチュートリアルは、本ガイドで示した手法を基にした、密接に関連するトピックを取り上げています。各リソースには完全な動作コード例とステップバイステップの解説が含まれており、追加の API 機能を習得したり、独自プロジェクトで代替実装アプローチを探求したりするのに役立ちます。

- [Read barcode from image C# – complete guide with Macro PDF417](/barcode/english/net/compact-pdf417-encoding/read-barcode-from-image-c-complete-guide-with-macro-pdf417/)
- [How to create macro PDF417 barcode in C# using Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/how-to-create-macro-pdf417-barcode-in-c-using-aspose-barcode/)
- [How to Read PDF417 in C# – Complete Barcode Reader Example](/barcode/english/net/compact-pdf417-encoding/how-to-read-pdf417-in-c-complete-barcode-reader-example/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}