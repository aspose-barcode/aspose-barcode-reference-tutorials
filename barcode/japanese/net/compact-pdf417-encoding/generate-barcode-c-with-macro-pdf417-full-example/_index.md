---
category: general
date: 2026-08-19
description: Aspose.BarCode を使用して C# でバーコードを生成し、カスタムテキストを含む Macro PDF417 を作成し、画像ファイルとして保存する。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate barcode C#
- how to generate pdf417
- create barcode custom text
- generate barcode image file
language: ja
lastmod: 2026-08-19
og_description: Aspose.BarCode を使用して C# でバーコードを生成し、PDF417 の生成方法を学び、カスタムテキストを追加し、バーコード画像ファイルを保存します。
og_image_alt: Screenshot of a Macro PDF417 barcode generated with C#
og_title: バーコード生成 C# – マクロ PDF417 ガイド
schemas:
- author: Aspose
  dateModified: '2026-08-19'
  description: Generate barcode C# using Aspose.BarCode to create a Macro PDF417 with
    custom text and save as an image file.
  headline: Generate barcode C# with Macro PDF417 – full example
  type: TechArticle
- questions:
  - answer: Yes. Replace `BarCodeImageFormat.Png` with `Jpeg`, `Bmp`, or `Gif` as
      needed.
    question: Can I generate a different image format?
  - answer: Macro PDF417 is designed for segmentation. Adjust `MacroPdf417SegmentsCount`
      and `MacroPdf417SegmentID` for each part, then concatenate the scanned results.
    question: What if my data exceeds a single barcode?
  - answer: Aspose.BarCode fully supports Unicode. Ensure your source file is saved
      with UTF‑8 encoding to avoid character corruption.
    question: Is Unicode support guaranteed?
  - answer: A licensed version removes the evaluation watermark and provides full
      functionality. The trial works for testing and learning.
    question: Do I need a license for production?
  type: FAQPage
tags:
- barcode
- C#
- Aspose
title: Macro PDF417でバーコードを生成するC# – 完全例
url: /ja/net/compact-pdf417-encoding/generate-barcode-c-with-macro-pdf417-full-example/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Macro PDF417 でバーコード C# を生成 – 完全例

Macro PDF417 形式の **generate barcode C#** が必要な場合、このガイドではすぐに実行できるソリューションを示します。**how to generate pdf417** の方法、カスタムテキストの埋め込み、そして **generate barcode image file** を単一の自己完結型プログラムで行う方法が分かります。

このチュートリアルは、Aspose.BarCode ライブラリのインストールから Macro PDF417 メタデータの設定までを網羅しているため、コードをそのままプロジェクトにコピーしてすぐに結果を確認できます。

## 前提条件

開始する前に、以下が揃っていることを確認してください。

- .NET 6.0 SDK 以上（コードは .NET Framework 4.7+ でも動作します）
- Visual Studio 2022（または C# をサポートする任意の IDE）
- Aspose.BarCode for .NET のライセンス（評価用の無料トライアルで試せます）
- C# の基本的な構文に関する知識

> **Pro tip:** バージョン不一致を防ぐために CLI で NuGet パッケージをインストールしてください:  
> `dotnet add package Aspose.BarCode`

## Step 1: プロジェクトのセットアップとライブラリのインポート

新しいコンソール アプリケーションを作成し、必要な `using` ディレクティブを追加します。

```csharp
using Aspose.BarCode.Generation;
using System;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // The full barcode generation logic starts in the next step.
        }
    }
}
```

**このステップが重要な理由:**  
`Aspose.BarCode.Generation` 名前空間は `BarcodeGenerator` クラスを提供し、Macro PDF417 を含む任意のバーコードタイプの作成エントリーポイントとなります。`System` をインポートすることで、タイムスタンプ メタデータに使用する `DateTime` が利用可能になります。

## Step 2: カスタムテキスト付き Macro PDF417 ジェネレータの作成

プレースホルダー コメントをジェネレータ初期化コードに置き換えます。これにより **create barcode custom text** を実演し、正しいエンコーディング タイプも選択できます。

```csharp
// Step 2: Initialize a barcode generator for Macro PDF417 with custom text.
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.MacroPdf417,          // Choose Macro PDF417 as the symbology
    "Åspóse.Barcóde©");               // Custom text can contain Unicode characters
```

**説明:**  
- `EncodeTypes.MacroPdf417` は、ファイル分割やチェックサムなどのマクロ機能をサポートする PDF417 バーコードを生成するよう Aspose に指示します。  
- テキスト `"Åspóse.Barcóde©"` は、Unicode 文字が完全にサポートされていることを示し、国際化アプリケーションでよく必要とされます。

## Step 3: 外観と Macro PDF417 メタデータの設定

バーコードの寸法を微調整し、分割ファイル処理に必要なマクロ固有フィールドを設定します。

```csharp
// Appearance: set the narrow bar width to 2 pixels.
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;

// PDF417 specific settings
barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 5;                     // Number of columns per row
barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;    // Unique file identifier
barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;       // Current segment number
barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;  // Total number of segments
barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01"; // Logical file name
barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234;     // CCITT‑16 CRC checksum
barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000;   // Approximate file size in bytes
barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2019, 11, 1);
barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;
```

**これらの設定が重要な理由:**

| Setting | Purpose |
|---------|---------|
| `XDimension.Pixels` | 視覚的密度を制御します。2 px でクリアでスキャンしやすい画像になります。 |
| `Columns` | 行ごとのデータ列数を決定し、バーコードのサイズに影響します。 |
| `MacroPdf417FileID` | すべてのセグメントにわたって論理ファイルを一意に識別します。 |
| `MacroPdf417SegmentID` / `SegmentsCount` | 複数のバーコードから元のファイルを再構築できるようにします。 |
| `MacroPdf417FileName` | 後続処理のためにバーコード内に格納される人間可読のファイル名です。 |
| `MacroPdf417Checksum` | CCITT‑16 CRC アルゴリズムを使用したエラー検出を提供します。 |
| `MacroPdf417FileSize` | デコーダがファイル全体の受信完了を判断するのに役立ちます。 |
| `MacroPdf417TimeStamp` | バーコード生成時刻を記録し、監査トレイルに有用です。 |
| `MacroPdf417Addressee` / `MacroPdf417Sender` | ビジネス ワークフローで使用できるオプション フィールドです。 |
| `MacroPdf417Terminator` | このセグメントが最終セグメントであることを示します（`Set`）。 |

## Step 4: バーコードを画像ファイルとして保存

最後に、バーコードを PNG ファイルとして書き出し、他の場所で表示または埋め込めるようにします。

```csharp
// Step 4: Save the generated barcode image to a file.
string outputPath = @"C:\Barcodes\ExtPDF417Meta.png";   // Adjust the folder as needed
barcodeGenerator.Save(outputPath, BarCodeImageFormat.Png);

Console.WriteLine($"Barcode saved to {outputPath}");
```

**表示される内容:**  
`ExtPDF417Meta.png` という名前の PNG 画像が生成され、カスタムテキストと上記で設定したすべてのメタデータをエンコードした Macro PDF417 バーコードが含まれます。この画像は標準のビューアで開くことができ、PDF、レポート、Web ページなどに挿入可能です。

## 完全なソースコード（コピー＆ペースト可能）

```csharp
using Aspose.BarCode.Generation;
using System;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // Initialize generator with custom Unicode text.
            BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
                EncodeTypes.MacroPdf417,
                "Åspóse.Barcóde©");

            // Appearance settings.
            barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
            barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 5;

            // Macro PDF417 metadata.
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234;
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000;
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2019, 11, 1);
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;

            // Save the barcode image.
            string outputPath = @"C:\Barcodes\ExtPDF417Meta.png";
            barcodeGenerator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"Barcode saved to {outputPath}");
        }
    }
}
```

### 期待される出力

プログラム実行時に次が表示されます:

```
Barcode saved to C:\Barcodes\ExtPDF417Meta.png
```

`ExtPDF417Meta.png` を開くと、任意の PDF417 リーダーで正しくスキャンできるクリーンな Macro PDF417 バーコードが確認でき、カスタムテキスト `"Åspóse.Barcóde©"` と定義したマクロ メタデータが保持されています。

## よくある質問とエッジケース

- **別の画像形式で出力できますか？**  
  はい。`BarCodeImageFormat.Png` を `Jpeg`、`Bmp`、`Gif` など必要な形式に置き換えてください。

- **データが単一のバーコードに収まらない場合は？**  
  Macro PDF417 は分割用に設計されています。各部分の `MacroPdf417SegmentsCount` と `MacroPdf417SegmentID` を調整し、スキャン結果を結合してください。

- **Unicode のサポートは保証されていますか？**  
  Aspose.BarCode は Unicode を完全にサポートしています。文字化けを防ぐため、ソース ファイルは UTF‑8 エンコーディングで保存してください。

- **本番環境でライセンスは必要ですか？**  
  ライセンス版は評価用の透かしを除去し、すべての機能を利用可能にします。トライアルはテストと学習に使用できます。

## 結論

これで Macro PDF417 用の **generate barcode C#**、リッチなメタデータ付き **how to generate pdf417**、**create barcode custom text**、そして Aspose.BarCode を使用した **generate barcode image file** の方法が分かりました。プロジェクトのセットアップから最終 PNG 画像の保存まで、すべての必須ステップを実行可能なサンプルで示しています。

### 次のステップ

- `ErrorCorrectionLevel` や `CompactPdf417` など、他の PDF417 設定を試してシンボルを小さくしてみましょう。  
- Aspose.PDF を使用して生成したバーコードを PDF レポートに組み込みます。  
- バッチ生成を検討してください。ファイル コレクションをループし、分割された Macro PDF417 バーコードのシリーズを作成します。

コードを自分のワークフローに合わせて自由にカスタマイズし、バーコード生成を C# アプリケーションのシームレスな一部にしてください。コーディングを楽しんでください！

## 次に学ぶべきことは？

以下のチュートリアルは、本ガイドで示した手法を基にした密接に関連するトピックを取り上げています。各リソースには、完全な動作コード例とステップバイステップの解説が含まれており、追加の API 機能を習得したり、独自プロジェクトで代替実装アプローチを探求したりするのに役立ちます。

- [How to generate Aztec barcode with custom aspect ratio using Aspose.BarCode for .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)
- [Generate barcode image – Code 93 with Aspose.BarCode](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-code-93-configuration/)
- [How to Generate and Adjust Barcode Height for One-Dimensional Databar using Aspose.BarCode for .NET](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-barcode-height-adjustment/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}