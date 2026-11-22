---
category: general
date: 2026-11-20
description: Aspose.BarCode を使用して C# でマクロ PDF417 バーコードの作成方法を学びましょう。このガイドではメタデータ、パラメータ、画像の保存について説明します。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create macro PDF417 barcode
- macro PDF417 metadata
- Aspose.BarCode C#
- PDF417 macro parameters
- barcode generator example
language: ja
lastmod: 2026-11-20
og_description: Aspose.BarCode を使用して C# でマクロ PDF417 バーコードを作成します。この完全なチュートリアルに従ってメタデータを設定し、パラメータを構成し、PNG
  にエクスポートしてください。
og_image_alt: Screenshot of a generated macro PDF417 barcode image
og_title: C#でマクロPDF417バーコードを作成する – ステップバイステップガイド
schemas:
- author: Aspose
  dateModified: '2026-11-20'
  description: Learn how to create macro PDF417 barcode in C# using Aspose.BarCode.
    This guide covers metadata, parameters, and saving the image.
  headline: How to create macro PDF417 barcode with Aspose.BarCode in C#
  type: TechArticle
- description: Learn how to create macro PDF417 barcode in C# using Aspose.BarCode.
    This guide covers metadata, parameters, and saving the image.
  name: How to create macro PDF417 barcode with Aspose.BarCode in C#
  steps:
  - name: Expected output
    text: 'Running the program prints a confirmation line similar to:'
  - name: What if I need more than 20 segments?
    text: The `MacroPdf417SegmentsCount` property can be set up to `255`. Ensure the
      receiving system can handle the larger segment count, and consider splitting
      the data into a manageable number of symbols.
  - name: How does the checksum affect scanning?
    text: The CCITT‑16 checksum (`MacroPdf417Checksum`) provides an additional error‑checking
      layer. If a scanner detects a mismatch, it will reject the barcode. You can
      omit the checksum if your workflow does not require it.
  - name: Can I generate a PDF417 macro barcode without Aspose?
    text: Yes, other libraries (e.g., ZXing.Net, Dynamsoft) support PDF417, but macro‑specific
      fields are often missing. Aspose.BarCode offers the most complete implementation
      for macro metadata.
  - name: What image formats are supported for saving?
    text: The `Save` method accepts any format defined in `BarCodeImageFormat`, such
      as `Png`, `Jpeg`, `Gif`, `Bmp`, and `Tiff`. Choose a format that matches your
      downstream processing pipeline.
  type: HowTo
tags:
- barcode
- PDF417
- C#
- Aspose
title: C#でAspose.BarCodeを使用してマクロPDF417バーコードを作成する方法
url: /ja/net/compact-pdf417-encoding/how-to-create-macro-pdf417-barcode-with-aspose-barcode-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.BarCode を使用した C# でのマクロ PDF417 バーコードの作成方法

.NET アプリケーションで **マクロ PDF417 バーコードを作成** する必要がある場合、このチュートリアルでは正確な手順を示します。マクロ固有のメタデータの設定方法、ビジュアル設定の調整方法、そして結果を PNG ファイルとして保存する方法が分かります。

マクロ PDF417 バーコードの生成は、大量のデータセットを複数のシンボルに分割しながら、ファイル全体の識別子を保持したい場合に便利です。以下の例では、すべての PDF417 機能に対して流暢な API を提供する Aspose.BarCode ライブラリを使用します。

このガイドの最後までに、完全なマクロ情報を含むバーコード画像を生成する、すぐに実行できるコンソールプログラムが手に入ります。

## 前提条件

* .NET 6.0 SDK 以降がインストールされていること。
* Visual Studio 2022（または C# をサポートする任意の IDE）。
* **Aspose.BarCode for .NET** NuGet パッケージ（`Aspose.BarCode`）。

以下のコマンドでパッケージを追加できます。

```bash
dotnet add package Aspose.BarCode
```

## 手順 1: マクロ PDF417 用のバーコードジェネレータを初期化する

最初のステップは、`EncodeTypes.MacroPdf417` 列挙値を使用して `BarcodeGenerator` のインスタンスを作成することです。これにより、ライブラリはバーコードをマクロ PDF417 シンボルとして扱います。

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

using (BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
           EncodeTypes.MacroPdf417, "Åspóse.Barcóde©"))
{
    // The generator is now ready for further configuration.
```

*この点が重要な理由*: `MacroPdf417` を選択すると、`Pdf417` パラメータオブジェクト上のすべてのマクロ関連プロパティが有効になります。

## 手順 2: 基本的なビジュアル外観を設定する

読み取りやすいバーコードは、適切なモジュールサイズと列数から始まります。`XDimension.Pixels` プロパティは単一モジュールの幅を制御し、`Pdf417.Columns` は各行が持つデータ列の数を定義します。

```csharp
    // Set module width to 2 pixels.
    barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;

    // Use 5 columns per row – a compact layout for this example.
    barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 5;
```

これらの値を調整することで、スキャナーの信頼性と画像サイズの両方に影響を与えます。

## 手順 3: マクロファイル識別情報を定義する

マクロ PDF417 では、ファイル識別子、セグメント識別子、および総セグメント数が必要です。この 3 つのフィールドにより、スキャナーは元のデータセットを再構築できます。

```csharp
    // Unique file identifier for the whole macro file.
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;

    // Identifier of the current segment (starting at 0 or 1 based on your protocol).
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;

    // Total number of segments that compose the complete file.
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;

    // Optional human‑readable file name.
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";
```

これらの **macro PDF417 parameters** はマクロ機能の核心です。これがなければ、スキャナーはシンボルを結び付けることができません。

## 手順 4: 任意のマクロメタデータを追加する

必須の識別子に加えて、マクロ形式はチェックサム、ファイルサイズ、タイムスタンプ、受取人、送信者、終了フラグなどの追加フィールドをサポートします。これらのデータを提供することで、エラー検出が向上し、下流システムへのコンテキストが提供されます。

```csharp
    // CCITT‑16 checksum example.
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234;

    // Approximate file size in bytes (helps the receiver allocate buffers).
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000;

    // Timestamp of when the macro file was generated.
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2019, 11, 1);

    // Optional address fields.
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";

    // Terminator indicates that this is the final segment.
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;
```

*プロのコツ*: ワークフローで特定のフィールドが不要な場合は、デフォルト値のままにしておくことができます。ライブラリは対応するデータ要素をバーコードから省略します。

## 手順 5: バーコード画像を保存する

すべてのパラメータを設定したら、`Save` を呼び出してバーコードをエクスポートします。例では、PNG ファイルをユーザー指定のディレクトリに保存します。

```csharp
    // Replace with a valid folder on your machine.
    string outputPath = "YOUR_DIRECTORY/ExtPDF417Meta.png";

    // Save as PNG – other formats (Jpeg, Gif, etc.) are also supported.
    barcodeGenerator.Save(outputPath, BarCodeImageFormat.Png);
}
```

プログラムが終了すると、`ExtPDF417Meta.png` に、テキスト `"Åspóse.Barcóde©"` とすべてのマクロメタデータをエンコードしたマクロ PDF417 バーコードが含まれます。

## 完全なソースコード

以下は完全な単体プログラムです。新しいコンソールプロジェクトにコピーし、Aspose.BarCode NuGet パッケージをインストールした後に実行してください。

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace MacroPdf417Demo
{
    class Program
    {
        static void Main()
        {
            // Step 1: Create a macro PDF417 barcode generator.
            using (BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
                       EncodeTypes.MacroPdf417, "Åspóse.Barcóde©"))
            {
                // Step 2: Visual appearance.
                barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
                barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 5;

                // Step 3: Core macro identifiers.
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";

                // Step 4: Optional macro metadata.
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2019, 11, 1);
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;

                // Step 5: Export the image.
                string outputPath = "YOUR_DIRECTORY/ExtPDF417Meta.png";
                barcodeGenerator.Save(outputPath, BarCodeImageFormat.Png);
                Console.WriteLine($"Macro PDF417 barcode saved to {outputPath}");
            }
        }
    }
}
```

### 期待される出力

プログラムを実行すると、以下のような確認行が出力されます。

```
Macro PDF417 barcode saved to YOUR_DIRECTORY/ExtPDF417Meta.png
```

PNG ファイルを開くと、密度が高くコントラストの強いバーコードが表示されます。PDF417 対応スキャナーでスキャンすると、元のテキストに加えてすべてのマクロフィールドが取得されます。

## よくある質問とエッジケース

### 20 セグメント以上が必要な場合は？

`MacroPdf417SegmentsCount` プロパティは最大 `255` まで設定可能です。受信システムがより多くのセグメント数に対応できることを確認し、データを管理しやすいシンボル数に分割することを検討してください。

### チェックサムはスキャンにどのように影響しますか？

CCITT‑16 チェックサム（`MacroPdf417Checksum`）は追加のエラーチェック層を提供します。スキャナーが不一致を検出した場合、バーコードは拒否されます。ワークフローで不要な場合は、チェックサムを省略できます。

### Aspose を使用せずに PDF417 マクロバーコードを生成できますか？

はい、他のライブラリ（例: ZXing.Net、Dynamsoft）でも PDF417 をサポートしていますが、マクロ固有のフィールドが欠けていることが多いです。Aspose.BarCode はマクロメタデータに関して最も完全な実装を提供します。

### 保存に対応している画像フォーマットは？

`Save` メソッドは `BarCodeImageFormat` で定義された任意のフォーマット（`Png`、`Jpeg`、`Gif`、`Bmp`、`Tiff` など）を受け付けます。下流の処理パイプラインに合ったフォーマットを選択してください。

## 結論

これで、Aspose.BarCode を使用して C# で **マクロ PDF417 バーコードを作成** する方法が分かりました。このチュートリアルでは、ジェネレータの初期化、ビジュアル設定、マクロファイル識別子、オプションのメタデータ、画像のエクスポートについて解説しました。この基礎を活かして、在庫システムや文書追跡、セグメント化されたデータ送信が必要なあらゆるシナリオでマクロ PDF を組み込むことができます。

次のステップとして、より高解像度のためにさまざまな `XDimension` 値を試したり、エラー訂正レベルの調整を加えたり、PNG ストリームを直接返す Web API にバーコードを統合したりできます。関連トピックとして、**barcode generator example**、**PDF417 macro parameters**、**macro PDF417 metadata** の取り扱いに関するチュートリアルをご覧ください。

コーディングを楽しんでください！

## 次に学ぶべきことは？

以下のチュートリアルは、本ガイドで示した手法を基にした密接に関連するトピックを取り上げています。各リソースには、ステップバイステップの解説と完全な動作コード例が含まれており、追加の API 機能を習得し、独自プロジェクトで代替実装アプローチを検討するのに役立ちます。

- [C# で Macro PDF417 オプションを使用した PDF417 バーコード画像の作成方法](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-image-in-c-with-macro-pdf417-op/)
- [C# で画像からバーコードを読み取る – Macro PDF417 を使用した完全ガイド](/barcode/english/net/compact-pdf417-encoding/read-barcode-from-image-c-complete-guide-with-macro-pdf417/)
- [Aspose を使用した PDF417 バーコードの作成方法 – 完全ステップバイステップガイド](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-with-aspose-complete-step-by-st/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}