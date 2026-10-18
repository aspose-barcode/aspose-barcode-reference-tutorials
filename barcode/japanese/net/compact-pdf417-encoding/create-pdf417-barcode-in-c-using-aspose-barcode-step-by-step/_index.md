---
category: general
date: 2026-10-18
description: Aspose.BarCode を使用して C# で PDF417 バーコードの作成方法を学びましょう。このチュートリアルでは、基本、コンパクト、マクロ、マイクロ
  PDF417 の生成をフルコード付きで解説します。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create pdf417 barcode
- how to create pdf417
language: ja
lastmod: 2026-10-18
og_description: C# と Aspose.BarCode で PDF417 バーコードを作成します。このガイドに従って、基本、コンパクト、マクロ、マイクロの
  PDF417 バーコードをステップバイステップで生成しましょう。
og_image_alt: Screenshot showing a generated PDF417 barcode saved as an image file
og_title: C#でPDF417バーコードを作成する – 完全なAspose.BarCodeチュートリアル
schemas:
- author: Aspose
  dateModified: '2026-10-18'
  description: Learn how to create PDF417 barcode in C# with Aspose.BarCode. This
    tutorial covers basic, compact, macro and micro PDF417 generation with full code.
  headline: Create PDF417 barcode in C# using Aspose.BarCode – step‑by‑step guide
  type: TechArticle
tags:
- barcode
- pdf417
- csharp
- aspose
title: Aspose.BarCode を使って C# で PDF417 バーコードを作成する – ステップバイステップガイド
url: /ja/net/compact-pdf417-encoding/create-pdf417-barcode-in-c-using-aspose-barcode-step-by-step/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# C#でAspose.BarCodeを使用してPDF417バーコードを作成する – ステップバイステップガイド

.NETアプリケーションで**PDF417バーコードを作成**する必要がある場合、このチュートリアルではプロセス全体を順を追って説明します。基本的なバーコードの生成、コンパクトモードの有効化、マクロメタデータの追加、マイクロバリアントの作成方法を、わかりやすい解説と実行可能なコードで示します。

PDF417バーコードの生成は、物流、チケット発行、文書管理などで一般的です。このガイドを終える頃には、外部ツールを使用せずに任意のC#プロジェクトにバーコード作成機能を組み込めるようになります。

## 前提条件

* .NET 6.0 以降（コードは .NET Framework 4.7+ でも動作します）
* Visual Studio 2022 または任意のC# IDE
* **Aspose.BarCode for .NET** NuGet パッケージ  
  ```bash
  dotnet add package Aspose.BarCode
  ```
* 生成された PNG ファイルを保存するフォルダーへの書き込み権限

追加の設定は不要です。ライブラリがすべての低レベルエンコードの詳細を処理します。

## 手順 1: 基本的な PDF417 バーコードを作成する

最初の手順では、カスタムサイズと列数を指定した標準的な PDF417 バーコードを作成します。

```csharp
using Aspose.BarCode.Generation;

// Initialize the generator for a standard PDF417 barcode
BarcodeGenerator basicGen = new BarcodeGenerator(EncodeTypes.Pdf417, "Åspóse.Barcóde©");

// Adjust the X‑dimension (module width) to 2 pixels for higher resolution
basicGen.Parameters.Barcode.XDimension.Pixels = 2;

// Set the number of columns – three columns keep the barcode compact yet readable
basicGen.Parameters.Barcode.Pdf417.Columns = 3;

// Save the barcode as a PNG image
basicGen.Save(@"YOUR_DIRECTORY\Pdf417Basic.png", BarCodeImageFormat.Png);
```

**これらの設定が重要な理由**

* `XDimension.Pixels` は各バーコード要素の物理サイズを制御します。値を 2 に設定すると、ほとんどの画面やプリンターで鮮明な画像が得られます。
* `Pdf417.Columns` はバーコードが持つデータ列の数を決定します。列数を減らすと幅が狭くなり、列数を増やすとデータ容量が増加します。

コードを実行すると `Pdf417Basic.png` が生成されます。この画像は、右側にフルメタデータ列がある、典型的な PDF417 シンボルで、データ列は3列です。

## 手順 2: コンパクト（トランケート）モードを有効にする

コンパクトモードは右側のメタデータ列を削除し、バーコードを狭くします。スペースが限られているが、残りの行からデータを再構築できる場合に便利です。

```csharp
// Turn on truncated mode to omit the metadata column
basicGen.Parameters.Barcode.Pdf417.Truncate = true;

// Save the compact version
basicGen.Save(@"YOUR_DIRECTORY\CompactPdf417.png", BarCodeImageFormat.Png);
```

**なぜトランケートするのか？**  
`Truncate` が `true` の場合、ジェネレータはエラー訂正とファイルレベルのメタデータを格納するオプションの右側列を省略します。その結果、バーコードは列数が少なくなりますが、ほとんどの PDF417 リーダーでスキャン可能です。

## 手順 3: ファイルレベルメタデータ付き Macro PDF417 バーコードを作成する

Macro PDF417 は標準フォーマットにセグメント識別子を追加し、大きな文書を複数のバーコードに分割できるようにします。長い文字列や複数ページのファイルをエンコードするのに便利です。

```csharp
// Initialize a generator for Macro PDF417
BarcodeGenerator macroGen = new BarcodeGenerator(EncodeTypes.MacroPdf417, "sample text");

// Set column count for better readability
macroGen.Parameters.Barcode.Pdf417.Columns = 5;

// Assign macro-specific identifiers
macroGen.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;   // Unique file identifier
macroGen.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 1;      // Current segment number
macroGen.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 10; // Total segments

// Save the macro barcode
macroGen.Save(@"YOUR_DIRECTORY\MacroPdf417.png", BarCodeImageFormat.Png);
```

**マクロフィールドの説明**

| プロパティ | 目的 |
|----------|---------|
| `MacroPdf417FileID` | ファイル全体の一意の識別子。すべてのセグメントがこの値を共有します。 |
| `MacroPdf417SegmentID` | 現在のセグメントのインデックス（1 から開始）。 |
| `MacroPdf417SegmentsCount` | 完全なデータセットを構成するセグメントの総数。 |

Macro PDF417 を理解できるスキャナーは、すべてのセグメントを読み取り、これらの識別子を使用して元のデータを再構築できます。

## 手順 4: 短いデータ用の Micro PDF417 バーコードを作成する

Micro PDF417 は、最大 90 文字の小さなペイロード向けに設計されたコンパクト版です。列範囲を 1‑4 に制限することで、極小ラベルや表示領域が限られたデバイスに適したバーコードになります。

```csharp
// Initialize a generator for Micro PDF417
BarcodeGenerator microGen = new BarcodeGenerator(EncodeTypes.MicroPdf417, "small data");

// Set a fine X‑dimension for crisp rendering
microGen.Parameters.Barcode.XDimension.Pixels = 2;

// Choose a column count within the allowed range (1‑4)
microGen.Parameters.Barcode.Pdf417.Columns = 4;

// Save the micro barcode
microGen.Save(@"YOUR_DIRECTORY\MicroPdf417.png", BarCodeImageFormat.Png);
```

**Micro PDF417 を使用すべき場面**  
データペイロードが短く、可能な限り小さなバーコードが必要な場合にこのバリアントを使用します。在庫タグ、アクセスカード、または画面スペースが限られたあらゆるシーンに最適です。

## 完全な動作例

以下は、1 回の実行で 4 種類すべてのバーコードを生成する自己完結型コンソールアプリケーションです。コードを新しい C# プロジェクトにコピーし、`YOUR_DIRECTORY` を既存のフォルダー パスに置き換えて実行してください。

```csharp
using System;
using Aspose.BarCode.Generation;

namespace Pdf417Demo
{
    class Program
    {
        static void Main()
        {
            // Adjust this path to a writable folder on your machine
            string outputPath = @"C:\Barcodes";

            // ---------- Basic PDF417 ----------
            var basicGen = new BarcodeGenerator(EncodeTypes.Pdf417, "Åspóse.Barcóde©");
            basicGen.Parameters.Barcode.XDimension.Pixels = 2;
            basicGen.Parameters.Barcode.Pdf417.Columns = 3;
            basicGen.Save($"{outputPath}\\Pdf417Basic.png", BarCodeImageFormat.Png);

            // ---------- Compact PDF417 ----------
            basicGen.Parameters.Barcode.Pdf417.Truncate = true;
            basicGen.Save($"{outputPath}\\CompactPdf417.png", BarCodeImageFormat.Png);

            // ---------- Macro PDF417 ----------
            var macroGen = new BarcodeGenerator(EncodeTypes.MacroPdf417, "sample text");
            macroGen.Parameters.Barcode.Pdf417.Columns = 5;
            macroGen.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
            macroGen.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 1;
            macroGen.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 10;
            macroGen.Save($"{outputPath}\\MacroPdf417.png", BarCodeImageFormat.Png);

            // ---------- Micro PDF417 ----------
            var microGen = new BarcodeGenerator(EncodeTypes.MicroPdf417, "small data");
            microGen.Parameters.Barcode.XDimension.Pixels = 2;
            microGen.Parameters.Barcode.Pdf417.Columns = 4; // valid range: 1‑4
            microGen.Save($"{outputPath}\\MicroPdf417.png", BarCodeImageFormat.Png);

            Console.WriteLine("All PDF417 barcodes have been generated successfully.");
        }
    }
}
```

**期待される出力**

プログラムを実行すると、指定したフォルダーに 4 つの PNG ファイルが作成されます：

* `Pdf417Basic.png` – 3 列の標準バーコード
* `CompactPdf417.png` – 同じデータだが右側列がトランケートされたもの
* `MacroPdf417.png` – セグメントメタデータを含むマクロバーコード
* `MicroPdf417.png` – 短い文字列用のコンパクトなマイクロバーコード

画像ビューアで任意の画像を開くと、はっきりとした PDF417 パターンが確認できます。モバイルバーコードリーダー（例: ZXing、Scandit）でスキャンすると、元のテキスト文字列が返されます。

## よくある質問とヒント

* **バーコードがぼやけて見える場合は？**  
  `XDimension.Pixels` を 3 または 4 に増やします。モジュールサイズが大きくなると、画像解像度が上がりますが、ファイルサイズも大きくなります。

* **SVG を出力できますか（PNG の代わりに）？**  
  はい。`Save` 呼び出しで `BarCodeImageFormat.Png` を `BarCodeImageFormat.Svg` に置き換えます。

* **エラー訂正レベルを手動で設定する必要がありますか？**  
  Aspose.BarCode が自動的に最適なレベルを選択します。特定の用途では `Pdf417.ErrorCorrectionLevel` を調整できます。

* **バーコードを PDF 文書に埋め込むには？**  
  `Aspose.Pdf` を使用して、生成した PNG または SVG を PDF ページ上の画像要素として追加します。

* **ライブラリはスレッドセーフですか？**  
  各 `BarcodeGenerator` インスタンスは独立しているため、共有状態なしで複数スレッド上でジェネレータを作成できます。

## 結論

これで、Aspose.BarCode を使用して C# で **PDF417 バーコードを作成**する方法（基本、コンパクト、マクロ、マイクロの各バリアント）を理解できました。

## 次に学ぶべきことは？

以下のチュートリアルは、本ガイドで示した手法を基にした密接に関連するトピックを取り上げています。各リソースには、ステップバイステップの解説と完全な動作コード例が含まれており、追加の API 機能を習得し、プロジェクトで代替実装アプローチを検討するのに役立ちます。

- [How to create pdf417 barcode in C# – step‑by‑step guide](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-in-c-step-by-step-guide/)
- [How to create PDF417 barcode in C# with compact mode](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-in-c-with-compact-mode/)
- [How to create macro PDF417 barcode in C# using Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/how-to-create-macro-pdf417-barcode-in-c-using-aspose-barcode/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}