---
category: general
date: 2026-07-27
description: C#でPDF417バーコードを素早く読み取る方法。複数のバーコードの読み取り、画像のデコード、そしてMacro PDF417メタデータの取得を、完全なC#バーコード例で学びましょう。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to read pdf417
- read multiple barcodes
- c# barcode example
- read barcode image c#
language: ja
lastmod: 2026-07-27
og_description: このステップバイステップガイドでC#を使ってPDF417バーコードを読み取る方法。画像をデコードし、複数のバーコードを処理し、実行可能なサンプルでMacro
  PDF417メタデータを抽出します。
og_image_alt: Screenshot showing how to read PDF417 barcode using C# code
og_title: C#でPDF417を読み取る方法 – 完全なバーコード例
schemas:
- author: Aspose
  dateModified: '2026-07-27'
  description: How to read PDF417 barcode in C# quickly. Learn to read multiple barcodes,
    decode images, and get Macro PDF417 metadata in a full C# barcode example.
  headline: How to Read PDF417 in C# – Complete Barcode Example
  type: TechArticle
- description: How to read PDF417 barcode in C# quickly. Learn to read multiple barcodes,
    decode images, and get Macro PDF417 metadata in a full C# barcode example.
  name: How to Read PDF417 in C# – Complete Barcode Example
  steps:
  - name: Loads a barcode image from disk.
    text: Loads a barcode image from disk.
  - name: Decodes **PDF417** (including Macro PDF417) barcodes.
    text: Decodes **PDF417** (including Macro PDF417) barcodes.
  - name: Prints basic information such as code type and text.
    text: Prints basic information such as code type and text.
  - name: Outputs the full set of Macro PDF417 fields (file ID, segment ID, checksum,
      etc.).
    text: Outputs the full set of Macro PDF417 fields (file ID, segment ID, checksum,
      etc.).
  type: HowTo
tags:
- barcode
- C#
- PDF417
- image-processing
- Aspose
title: C#でPDF417を読み取る方法 – 完全なバーコード例
url: /ja/net/compact-pdf417-encoding/how-to-read-pdf417-in-c-complete-barcode-example/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# C#でPDF417を読み取る方法 – 完全なバーコード例

C#アプリケーションで**PDF417を読み取る方法**で、髪の毛を抜くほど悩んだことはありませんか？ あなただけではありません。物流スキャナーやチケットバリデーターを作成する場合でも、PDF417でエンコードされたIDからデータを取得したいだけの場合でも、最初はプロセスが少し神秘的に感じられることがあります。  

このチュートリアルでは、PDF417画像を読み取り、**read multiple barcodes** が存在する場合に処理し、必要になる可能性のあるすべての便利なMacro PDF417メタデータを抽出する**c# barcode example**をご紹介します。

## 作成するもの

このガイドの最後までに、以下の機能を持つ小さなコンソールプログラムが作成できます：

1. ディスクからバーコード画像をロードします。  
2. **PDF417**（Macro PDF417を含む）バーコードをデコードします。  
3. コードタイプやテキストなどの基本情報を出力します。  
4. Macro PDF417フィールド（file ID、segment ID、checksum など）の全セットを出力します。  

外部サービスは不要で、単一のNuGetパッケージと数行のC#だけで実現できます。

## 前提条件 – 開始前に必要なもの

- **.NET 6.0** 以降（コードは .NET Framework 4.6+ でも動作します）。  
- **Aspose.BarCode for .NET** の最新バージョン – NuGet でインストールします（`Install-Package Aspose.BarCode`）。  
- PDF417バーコードを含む画像ファイル（デモでは `ExtPDF417Meta.png` を使用）。  
- C# コンソールアプリの基本的な理解（「Hello World」を書いたことがあれば問題ありません）。

> **プロのコツ:** PDF417のサンプルが手元にない場合は、Aspose デモサイトで生成するか、PDF417タグを作成できるスマートフォンアプリを使用してください。

## 手順 1: プロジェクトの設定とライブラリのインストール

まず、新しいコンソールプロジェクトを作成します：

```bash
dotnet new console -n Pdf417ReaderDemo
cd Pdf417ReaderDemo
dotnet add package Aspose.BarCode
```

これで必要な **c# barcode example** の依存関係が取得されます。`Program.cs` を開き、デフォルトのコードを以下のスケルトンに置き換えます：

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
            // We'll fill this in in the next steps.
        }
    }
}
```

## 手順 2: PDF417 用のバーコードリーダーを初期化

ソリューションの中心は `BarCodeReader` クラスです。スキャンするファイルと対象とするバーコードタイプを指定します――この場合は `DecodeType.Pdf417` またはマクロバリアントの `DecodeType.MacroPdf417` です。マクロタイプを使用することで拡張フィールドを確実に取得できます。

```csharp
// Step 2: Create the reader, targeting Macro PDF417 barcodes
string imagePath = "YOUR_DIRECTORY/ExtPDF417Meta.png";

using (BarCodeReader reader = new BarCodeReader(
           imagePath, DecodeType.MacroPdf417))
{
    // The rest of the logic lives inside this block.
}
```

なぜ `MacroPdf417` を使用するのか？ Macro PDF417 は、ファイルID、セグメント数、タイムスタンプなどの余分なメタデータを保持しており、多くの実務アプリケーションで利用されています――例えば、複数ページに分割された出荷明細書などです。

## 手順 3: 画像内のすべてのバーコードを読み取る

単一の画像に **read multiple barcodes** が含まれることがあります――たとえば PDF417 の横に QR コードがある場合などです。`ReadBarCodes()` メソッドは `IEnumerable<BarCodeResult>` を返すので、これを反復処理できます。

```csharp
// Step 3: Iterate through every barcode detected
foreach (BarCodeResult result in reader.ReadBarCodes())
{
    // Inside we’ll output both generic and macro‑specific data.
}
```

画像に PDF417 が1つだけ含まれている場合でも、ループは1回実行されます。これにより、将来的に同じスキャンから **read multiple barcodes** が必要になるシナリオにも柔軟に対応できます。

## 手順 4: 基本的なバーコード情報を表示

マクロフィールドに入る前に、バーコードタイプとデコードされたテキストを表示すると便利です。これにより、リーダーが実際に PDF417 を認識したか、他のシンボルと間違えていないかを確認できます。

```csharp
Console.WriteLine($"CodeType : {result.CodeTypeName}");
Console.WriteLine($"CodeText : {result.CodeText}");
```

`CodeTypeName` は *MacroPdf417*（マクロフラグが設定されていない場合は *Pdf417*）を返し、`CodeText` にはバーコードにエンコードされた生データが格納されます。

## 手順 5: Macro PDF417 メタデータを抽出

`Extended` プロパティを使うと、PDF417 固有の構造を詳細に取得できます。以下で出力する各フィールドは、PDF417 マクロ仕様に直接対応しています。

```csharp
// Step 5: Macro PDF417 metadata – all optional, but very handy
Console.WriteLine($"Pdf417MacroFileID          : {result.Extended.Pdf417.MacroPdf417FileID}");
Console.WriteLine($"Pdf417MacroSegmentID       : {result.Extended.Pdf417.MacroPdf417SegmentID}");
Console.WriteLine($"Pdf417MacroSegmentsCount   : {result.Extended.Pdf417.MacroPdf417SegmentsCount}");
Console.WriteLine($"Pdf417MacroFileName        : {result.Extended.Pdf417.MacroPdf417FileName}");
Console.WriteLine($"Pdf417MacroChecksum        : {result.Extended.Pdf417.MacroPdf417Checksum}");
Console.WriteLine($"Pdf417MacroFileSize        : {result.Extended.Pdf417.MacroPdf417FileSize}");
Console.WriteLine($"Pdf417MacroTimeStamp       : {result.Extended.Pdf417.MacroPdf417TimeStamp}");
Console.WriteLine($"Pdf417MacroAddressee       : {result.Extended.Pdf417.MacroPdf417Addressee}");
Console.WriteLine($"Pdf417MacroSender          : {result.Extended.Pdf417.MacroPdf417Sender}");
Console.WriteLine($"MacroPdf417Terminator      : {result.Extended.Pdf417.MacroPdf417Terminator}");
```

各行はマクロペイロードの異なる要素を取得します：

- **FileID** – ドキュメント全体の一意の識別子。  
- **SegmentID** – マルチセグメントファイルのどの部分か。  
- **SegmentsCount** – 期待されるセグメント総数。  
- **FileName**, **Checksum**, **FileSize** – 転送されたファイルの整合性を検証するのに役立ちます。  
- **TimeStamp**, **Addressee**, **Sender** – 多くの物流システムが埋め込むオプションフィールド。  

ソースバーコードにこれらのフィールドが存在しない場合、ライブラリは `null` または `0` を返しますので、必要に応じてハンドリングしてください。

## 手順 6: 完全なサンプルを実行

すべてを組み合わせた、実行可能な完全プログラムは以下の通りです：

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
            // Path to the image containing a Macro PDF417 barcode
            string imagePath = "YOUR_DIRECTORY/ExtPDF417Meta.png";

            // Initialize the reader for Macro PDF417 (covers both standard and macro)
            using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
            {
                // Loop through every barcode detected – handles read multiple barcodes gracefully
                foreach (BarCodeResult result in reader.ReadBarCodes())
                {
                    // Basic info
                    Console.WriteLine($"CodeType : {result.CodeTypeName}");
                    Console.WriteLine($"CodeText : {result.CodeText}");

                    // Macro PDF417 specific metadata
                    Console.WriteLine($"Pdf417MacroFileID          : {result.Extended.Pdf417.MacroPdf417FileID}");
                    Console.WriteLine($"Pdf417MacroSegmentID       : {result.Extended.Pdf417.MacroPdf417SegmentID}");
                    Console.WriteLine($"Pdf417MacroSegmentsCount   : {result.Extended.Pdf417.MacroPdf417SegmentsCount}");
                    Console.WriteLine($"Pdf417MacroFileName        : {result.Extended.Pdf417.MacroPdf417FileName}");
                    Console.WriteLine($"Pdf417MacroChecksum        : {result.Extended.Pdf417.MacroPdf417Checksum}");
                    Console.WriteLine($"Pdf417MacroFileSize        : {result.Extended.Pdf417.MacroPdf417FileSize}");
                    Console.WriteLine($"Pdf417MacroTimeStamp       : {result.Extended.Pdf417.MacroPdf417TimeStamp}");
                    Console.WriteLine($"Pdf417MacroAddressee       : {result.Extended.Pdf417.MacroPdf417Addressee}");
                    Console.WriteLine($"Pdf417MacroSender          : {result.Extended.Pdf417.MacroPdf417Sender}");
                    Console.WriteLine($"MacroPdf417Terminator      : {result.Extended.Pdf417.MacroPdf417Terminator}");
                    Console.WriteLine(new string('-', 40));
                }
            }

            Console.WriteLine("Decoding complete. Press any key to exit.");
            Console.ReadKey();
        }
    }
}
```

### 期待される出力

有効な `ExtPDF417Meta.png` に対してプログラムを実行すると、以下のような出力が得られるはずです：

```
CodeType : MacroPdf417
CodeText : https://example.com/track?order=12345
Pdf417MacroFileID          : 101
Pdf417MacroSegmentID       : 1
Pdf417MacroSegmentsCount   : 3
Pdf417MacroFileName        : order_manifest.pdf
Pdf417MacroChecksum        : 0x1A2B3C4D
Pdf417MacroFileSize        : 45296
Pdf417MacroTimeStamp       : 2024-03-15T10:27:00Z
Pdf417MacroAddressee       : LogisticsDept
Pdf417MacroSender          : WarehouseA
MacroPdf417Terminator      : true
----------------------------------------
Decoding complete. Press any key to exit.
```

画像に複数のバーコードが含まれている場合、

## 次に学ぶべきことは？

以下のチュートリアルは、本ガイドで示した手法を基にした、密接に関連するトピックをカバーしています。各リソースには、ステップバイステップの解説と完全なコード例が含まれており、追加の API 機能を習得したり、独自プロジェクトで代替実装アプローチを検討したりするのに役立ちます。

- [PDF417バーコードの生成方法 – コンパクトPDF417エンコーディング](/barcode/english/net/compact-pdf417-encoding/)
- [バーコードの作成方法 – Aspose.BarCode を使用したコンパクトPDF417](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [Aspose.BarCode for .NET で DataMatrix バーコードを読む方法](/barcode/english/net/datamatrix-barcode-reading/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}