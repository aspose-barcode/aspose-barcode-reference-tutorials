---
category: general
date: 2026-07-15
description: C#でPDF417バーコードを読み取る方法と、画像から複数のバーコードを読み取る方法。詳細なコードとヒントでC#でバーコード画像の読み取りを学びましょう。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to read pdf417
- read multiple barcodes
- read barcode image c#
- Aspose.BarCode PDF417
- C# barcode decoding
language: ja
lastmod: 2026-07-15
og_description: C#でPDF417バーコードを素早く読み取る方法。このガイドでは、1つの画像から複数のバーコードを読み取り、各プロパティをデコードする手順を示します。
og_image_alt: Screenshot of C# console output displaying PDF417 barcode details
og_title: C#でPDF417を読み取る方法 – 完全なコードサンプルと解説
schemas:
- author: Aspose
  dateModified: '2026-07-15'
  description: How to read PDF417 barcode in C# and read multiple barcodes from an
    image. Learn to read barcode image C# with detailed code and tips.
  headline: How to Read PDF417 in C# – Complete Step‑by‑Step Guide
  type: TechArticle
- description: How to read PDF417 barcode in C# and read multiple barcodes from an
    image. Learn to read barcode image C# with detailed code and tips.
  name: How to Read PDF417 in C# – Complete Step‑by‑Step Guide
  steps:
  - name: Why This Code Works
    text: '* **`BarCodeReader`** is the core class that streams the image, detects
      barcodes, and returns a collection of `BarCodeResult` objects. * Passing **`DecodeType.MacroPdf417`**
      tells the library to treat Macro‑PDF417 specially; it still returns plain PDF417
      symbols, which satisfies the **read multiple '
  - name: What if the image has both Macro‑PDF417 and regular PDF417 symbols?
    text: The same `BarCodeReader` call will return both. You can differentiate them
      by checking `result.CodeType` (`MacroPdf417` vs `Pdf417`). The extended properties
      will be `null` for a plain PDF417, so the `if (macro != null)` guard prevents
      a `NullReferenceException`.
  - name: My barcode is rotated or skewed—will the reader still work?
    text: Aspose.BarCode includes built‑in rotation and distortion compensation. As
      long as the barcode is at least 30 % of the image width, the decoder will usually
      succeed. For extreme cases you can enable `reader.Options.AllowInvertedBarcodes
      = true;` before calling `ReadBarCodes()`.
  - name: How do I handle large batches of images?
    text: Wrap the reading logic in a `foreach (var file in Directory.GetFiles(folder,
      "*.png"))` loop. The `using` pattern ensures each image’s native resources are
      freed before the next iteration, keeping memory usage low.
  type: HowTo
tags:
- C#
- barcode
- PDF417
- Aspose
title: C#でPDF417を読み取る方法 – 完全ステップバイステップガイド
url: /ja/net/compact-pdf417-encoding/how-to-read-pdf417-in-c-complete-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# C#でPDF417を読む方法 – 完全ステップバイステップガイド

C#で画像から **PDF417の読み取り方法** を疑問に思ったことはありませんか？ あなただけではありません。多くの開発者は、スキャンしたドキュメントから拡張 Macro‑PDF417 フィールドを取得しようとすると壁にぶつかります。良いニュースは、数行のコードで PDF417 をデコードし、同じ画像内の複数のバーコードを読み取り、仕様が提供するすべての隠れたプロパティを取得できることです。

このチュートリアルでは、実際の例を通じて **PDF417の読み取り方法**、単一ファイルから **複数のバーコードを読む方法**、そして **read barcode image C#** コードがそのようになっている理由を解説します。最後まで読むと、ファイル ID、セグメント ID、チェックサム、タイムスタンプなど、必要な情報をすべて出力する実行可能なコンソールアプリが手に入ります。

## 前提条件

* .NET 6.0 SDK またはそれ以降 (コードは .NET Core および .NET Framework でも動作します)。  
* Visual Studio 2022 (またはお好みのエディタ)。  
* **Aspose.BarCode for .NET** NuGet パッケージ – これは実際に PDF417 を解析するライブラリです。  
* Macro‑PDF417 バーコードを含むサンプル画像 (例: `ExtPDF417Meta.png`)。  

追加の設定は不要です；ライブラリには必要なデコーダがすべて同梱されています。

## ステップ 1: Aspose.BarCode をインストール

ターミナルでプロジェクトフォルダーを開き、以下を実行します：

```bash
dotnet add package Aspose.BarCode
```

このコマンドは最新の安定版を取得します（2026年7月時点で 23.12）。Visual Studio のパッケージ マネージャ コンソールを使用したい場合は、次を使用してください：

```powershell
Install-Package Aspose.BarCode
```

> **プロのコツ:** 後で予期せぬ破壊的変更を防ぐために、`.csproj` でバージョン (`23.12.0`) を固定してください。

## ステップ 2: コンソール アプリの雛形を作成

まだ作成していない場合は、新しいコンソール プロジェクトを作成します：

```bash
dotnet new console -n Pdf417ReaderDemo
cd Pdf417ReaderDemo
```

自動生成された `Program.cs` を以下のコードに置き換えてください。各ブロックは次のセクションで説明します。

## ステップ 3: 完全な “PDF417の読み取り方法” コードを書く

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

namespace Pdf417ReaderDemo
{
    class Program
    {
        static void Main(string[] args)
        {
            // -----------------------------------------------------------------
            // 1️⃣  Set the path to the image that contains one or more PDF417 codes
            // -----------------------------------------------------------------
            string imagePath = @"YOUR_DIRECTORY/ExtPDF417Meta.png";

            // -----------------------------------------------------------------
            // 2️⃣  Initialise the BarCodeReader for MacroPdf417 decoding
            // -----------------------------------------------------------------
            // The DecodeType flag tells Aspose to look specifically for Macro‑PDF417,
            // but it will also pick up plain PDF417 symbols that happen to be in the
            // same image – perfect for the “read multiple barcodes” scenario.
            using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
            {
                // -----------------------------------------------------------------
                // 3️⃣  Iterate over every barcode found in the image
                // -----------------------------------------------------------------
                foreach (BarCodeResult result in reader.ReadBarCodes())
                {
                    // -------------------------------------------------------------
                    // 4️⃣  Basic barcode information – works for any barcode type
                    // -------------------------------------------------------------
                    Console.WriteLine($"Code Type : {result.CodeTypeName}");
                    Console.WriteLine($"Code Text : {result.CodeText}");

                    // -------------------------------------------------------------
                    // 5️⃣  Macro‑PDF417 extended properties (the real reason you’re here)
                    // -------------------------------------------------------------
                    var macro = result.Extended?.Pdf417?.MacroPdf417;
                    if (macro != null)
                    {
                        Console.WriteLine($"File ID          : {macro.FileID}");
                        Console.WriteLine($"Segment ID       : {macro.SegmentID}");
                        Console.WriteLine($"Segments Count   : {macro.SegmentsCount}");
                        Console.WriteLine($"File Name        : {macro.FileName}");
                        Console.WriteLine($"Checksum         : {macro.Checksum}");
                        Console.WriteLine($"File Size        : {macro.FileSize}");
                        Console.WriteLine($"Time Stamp       : {macro.TimeStamp}");
                        Console.WriteLine($"Addressee        : {macro.Addressee}");
                        Console.WriteLine($"Sender           : {macro.Sender}");
                        Console.WriteLine($"Terminator       : {macro.Terminator}");
                    }
                    else
                    {
                        Console.WriteLine("No Macro‑PDF417 extended data found for this barcode.");
                    }

                    Console.WriteLine(new string('-', 40)); // visual separator
                }
            }

            // -----------------------------------------------------------------
            // 6️⃣  Keep the console window open when running from VS
            // -----------------------------------------------------------------
            Console.WriteLine("Done. Press any key to exit...");
            Console.ReadKey();
        }
    }
}
```

### このコードが機能する理由

* **`BarCodeReader`** は画像をストリームし、バーコードを検出し、`BarCodeResult` オブジェクトのコレクションを返すコアクラスです。  
* **`DecodeType.MacroPdf417`** を渡すと、ライブラリは Macro‑PDF417 を特別に扱いますが、依然としてプレーンな PDF417 シンボルを返すため、**read multiple barcodes** の要件を満たします。  
* **`Extended.Pdf417.MacroPdf417`** オブジェクトは ISO/IEC 15438 標準で定義されたすべてのオプションフィールドを保持しており、`FileID`、`SegmentID`、`Checksum` などが取得できます。  
* `using` ブロックはネイティブリソースの解放を保証し、長時間実行されるサービスでのメモリリークを防ぎます。

## ステップ 4: アプリケーションを実行し、出力を確認

ターミナルから実行します：

```bash
dotnet run
```

以下のような出力が表示されます：

```
Code Type : MacroPdf417
Code Text : 1234567890...
File ID          : 12
Segment ID       : 1
Segments Count   : 3
File Name        : invoice2024.pdf
Checksum         : 9A3F
File Size        : 245760
Time Stamp       : 2024-11-02T14:23:00Z
Addressee        : Acme Corp
Sender           : Logistics Dept
Terminator       : 1
----------------------------------------
Done. Press any key to exit...
```

画像に複数のバーコードが含まれている場合、ループは区切り線 (`----------------------------------------`) を出力し、次の結果に続きます—実際に **read multiple barcodes** がどのように見えるかを正確に示しています。

## よくある質問とエッジケース

### 画像に Macro‑PDF417 と通常の PDF417 シンボルの両方が含まれている場合は？

同じ `BarCodeReader` 呼び出しで両方が返されます。`result.CodeType` (`MacroPdf417` と `Pdf417`) を確認することで区別できます。プレーンな PDF417 の場合、拡張プロパティは `null` になるため、`if (macro != null)` ガードが `NullReferenceException` を防ぎます。

### バーコードが回転または歪んでいる場合、リーダーは動作しますか？

Aspose.BarCode には回転および歪み補正が組み込まれています。バーコードが画像幅の少なくとも 30 % であれば、デコーダは通常成功します。極端なケースでは、`ReadBarCodes()` を呼び出す前に `reader.Options.AllowInvertedBarcodes = true;` を有効にできます。

### 大量の画像バッチを処理するには？

読み取りロジックを `foreach (var file in Directory.GetFiles(folder, "*.png"))` ループでラップします。`using` パターンにより、次のイテレーションの前に各画像のネイティブリソースが解放され、メモリ使用量が低く抑えられます。

## 完全なソースリスト（コピー＆ペースト用）

以下は、すぐにコピー＆ペーストできるように 1 つのブロックにまとめたプログラム全体です。隠れた依存関係はなく、Aspose.BarCode NuGet パッケージだけです。

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

namespace Pdf417ReaderDemo
{
    class Program
    {
        static void Main(string[] args)
        {
            string imagePath = @"YOUR_DIRECTORY/ExtPDF417Meta.png";

            using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
            {
                foreach (BarCodeResult result in reader.ReadBarCodes())
                {
                    Console.WriteLine($"Code Type : {result.CodeTypeName}");
                    Console.WriteLine($"Code Text : {result.CodeText}");

                    var macro = result.Extended?.Pdf417?.MacroPdf417;
                    if (macro != null)
                    {
                        Console.WriteLine($"File ID          : {macro.FileID}");
                        Console.WriteLine($"Segment ID       : {macro.SegmentID}");
                        Console.WriteLine($"Segments Count   : {macro.SegmentsCount}");
                        Console.WriteLine($"File Name        : {macro.FileName}");
                        Console.WriteLine($"Checksum         : {macro.Checksum}");
                        Console.WriteLine($"File Size        : {macro.FileSize}");
                        Console.WriteLine($"Time Stamp       : {macro.TimeStamp}");
                        Console.WriteLine($"Addressee        : {macro.Addressee}");
                        Console.WriteLine($"Sender           : {macro.Sender}");
                        Console.WriteLine($"Terminator       : {macro.Terminator}");
                    }
                    else
                    {
                        Console.WriteLine("No Macro‑PDF417 extended data found for this barcode.");
                    }

                    Console.WriteLine(new string('-', 40));
                }
            }

            Console.WriteLine("Done. Press any key to exit...");
            Console.ReadKey();
        }
    }
}
```

## まとめ – カバーした内容

* **How to read PDF417** を Aspose.BarCode と C# で使用する方法。  
* 単一画像から **read multiple barcodes** を行う正確な手順。  
* **read barcode image C#** の方法とすべての Macro‑PDF417 フィールドの抽出方法。  
* 回転、バッチ処理、拡張データが欠落している場合の対処法に関するヒント。

## 次のステップと関連トピック

* **Encode PDF417** – `BarCodeBuilder` を使用して独自の Macro‑PDF417 バーコードを生成します。  
* **Read other 2‑D symbologies** – 同じ `BarCodeReader` クラスを使用して QR、DataMatrix、Aztec を読み取ります。  
* **Integrate with ASP.NET Core** – アップロードされた画像を受け取り、デコードされたフィールドを含む JSON を返す Web エンドポイントを公開します。  

自由に実験してください：画像パスを変更したり、同じフォルダーにプレーンな PDF417 を置いたり、`DecodeType` フラグを調整してライブラリの挙動を確認したりできます。試せば試すほど、**read barcode image C#** シナリオに慣れるでしょう。

デコードできない厄介な画像がありますか？下にコメントを残すか、サンプルプロジェクトの GitHub リポジトリで issue を作成してください。ハッピーコーディング！

## 次に学ぶべきことは？

以下のチュートリアルは、本ガイドで示した手法を基にした密接に関連するトピックをカバーしています。各リソースには、ステップバイステップの解説付きの完全な動作コード例が含まれており、追加の API 機能を習得し、独自プロジェクトで代替実装アプローチを検討するのに役立ちます。

- [Aspose.BarCode for .NET で DataMatrix バーコードを読む方法](/barcode/english/net/datamatrix-barcode-reading/)
- [Aspose.BarCode で Compact PDF417 バーコードを作成する方法](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [DataMatrix バーコード C# の読み取り – 自動モードで生成](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-auto/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}