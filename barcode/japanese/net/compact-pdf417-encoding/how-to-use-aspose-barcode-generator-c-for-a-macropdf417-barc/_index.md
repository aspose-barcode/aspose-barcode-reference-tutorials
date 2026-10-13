---
category: general
date: 2026-10-05
description: Aspose Barcode Generator C# を使用すれば、マクロデータを追加して PDF417 バーコードを簡単に生成できます。マクロメタデータの追加方法と
  PDF417 画像の作成手順をステップバイステップで学びましょう。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- aspose barcode generator c#
- how to add macro
- how to generate pdf417
language: ja
lastmod: 2026-10-05
og_description: Aspose Barcode Generator C# は、マクロメタデータを追加し、数行のコードで PDF417 バーコードを生成する方法を示します。
og_image_alt: Screenshot of a MacroPdf417 barcode created with Aspose Barcode Generator
  C#
og_title: Aspose Barcode Generator C# – マクロを追加して PDF417 バーコードを生成
schemas:
- author: Aspose
  dateModified: '2026-10-05'
  description: Aspose Barcode Generator C# lets you add macro data and generate PDF417
    barcodes effortlessly. Learn step‑by‑step how to add macro metadata and create
    a PDF417 image.
  headline: How to use Aspose Barcode Generator C# for a MacroPdf417 barcode
  type: TechArticle
tags:
- barcode
- csharp
- aspose
title: MacroPdf417 バーコード用に Aspose Barcode Generator C# を使用する方法
url: /ja/net/compact-pdf417-encoding/how-to-use-aspose-barcode-generator-c-for-a-macropdf417-barc/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose Barcode Generator C# を使用して MacroPdf417 バーコードを作成する方法

C# で MacroPdf417 バーコードを作成する必要がある場合、**Aspose Barcode Generator C#** はバーコード画像と必要なマクロメタデータの両方を処理する簡潔な API を提供します。このチュートリアルでは、マクロ情報を追加し、数ステップで PDF417 バーコード画像を生成する方法を正確に示します。

視覚パラメータの設定方法、ファイル ID やタイムスタンプなどのマクロフィールドの埋め込み方法、そして PNG として保存する方法を学びます。外部ツールは不要で、Aspose.BarCode ライブラリと .NET 開発環境さえあれば完了です。

## 前提条件

開始する前に、以下がインストールされていることを確認してください。

* .NET 6.0 以降  
* Visual Studio 2022（または任意の C# IDE）  
* **Aspose.BarCode for .NET** のライセンス版または評価版  

このコードは Windows、Linux、macOS で動作します。ライブラリはプラットフォームに依存しません。

## 手順 1: Aspose.BarCode NuGet パッケージをインストール

Visual Studio でプロジェクトを開き、**Package Manager Console** で次のコマンドを実行します。

```powershell
Install-Package Aspose.BarCode
```

これにより `Aspose.BarCode` アセンブリとその依存関係がプロジェクトに追加されます。

## 手順 2: バーコードジェネレータのインスタンスを作成

最初の行で **MacroPdf417** シンボロジー用の `BarcodeGenerator` オブジェクトを作成し、エンコードしたいテキストを指定します。

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode.BarCodeImageFormat;

// Step 2: Initialise the generator with MacroPdf417 and the payload text
using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MacroPdf417, "Åspóse.Barcóde©"))
{
    // subsequent configuration goes here
}
```

*重要ポイント*: `EncodeTypes.MacroPdf417` を指定することで、ライブラリはマクロ関連フィールドの使用を前提に動作します。次の手順でこれらのフィールドを設定します。

## 手順 3: 視覚的外観を定義

各モジュール（最小の黒または白の正方形）のサイズや PDF417 行列の列数を制御できます。`XDimension` を調整すると画像全体の解像度が変わります。

```csharp
    // Step 3: Visual settings
    generator.Parameters.Barcode.XDimension.Pixels = 2;          // width of a single module
    generator.Parameters.Barcode.Pdf417.Columns = 5;           // number of columns in the symbol
```

`Columns` を増やすとバーコードの高さが低くなり、`XDimension` を大きくすると高 DPI 画面で画像がより鮮明になります。

## 手順 4: マクロメタデータを追加（マクロの追加方法）

MacroPdf417 では、ソースファイルとその分割情報を記述する複数の追加フィールドが必要です。以下のプロパティは PDF417 マクロ仕様に直接対応しています。

```csharp
    // Step 4: Macro fields – how to add macro data
    generator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;               // unique file identifier
    generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;                  // current segment number
    generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;              // total number of segments
    generator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";             // optional file name
    generator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234;                // CCITT‑16 placeholder
    generator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000;              // size in bytes
    generator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = 
        new DateTime(2019, 11, 1);                                                   // creation timestamp
    generator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";            // recipient identifier
    generator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";               // sender identifier
    generator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = 
        Pdf417MacroTerminator.Set;                                                   // marks the last segment
```

*これらのフィールドが必要な理由*:  
* `MacroPdf417FileID` はすべてのセグメントを結び付け、スキャナが元の文書を再構築できるようにします。  
* `MacroPdf417SegmentID` と `MacroPdf417SegmentsCount` はデコーダに順序と総セグメント数を知らせます。  
* `MacroPdf417FileSize` と `MacroPdf417Checksum` は整合性チェックを提供し、大容量データ転送時に有用です。

## 手順 5: バーコード画像を保存（PDF417 の生成方法）

最後にバーコードをディスクに書き出します。`Save` メソッドはファイルパスと画像フォーマットを受け取ります。PNG は圧縮アーティファクトなしで鮮明なエッジを保持します。

```csharp
    // Step 5: Save the generated barcode – how to generate pdf417 image
    generator.Save("ExtPDF417Meta.png", BarCodeImageFormat.Png);
}
```

プログラム実行後、出力フォルダーに **ExtPDF417Meta.png** が作成されます。画像を開くと、印刷や PDF 埋め込みに適したクリーンな MacroPdf417 バーコードが確認できます。

### 期待される出力

| ファイル名            | フォーマット | サイズ（目安） |
|----------------------|--------------|----------------|
| ExtPDF417Meta.png    | PNG          | 300 × 150 px（`XDimension` により変動） |

PDF417 対応リーダー（例: ZXing、Aspose.BarCode for .NET）で画像をスキャンすると、元のテキスト **“Åspóse.Barcóde©”** とすべてのマクロフィールドが取得できます。

## よくある落とし穴と回避策

| 問題 | 発生理由 | 対策 |
|------|----------|------|
| **`EncodeTypes` が不正** | `EncodeTypes.Pdf417` を使用するとマクロフィールドが無効になる | 常に `EncodeTypes.MacroPdf417` でジェネレータをインスタンス化 |
| **マクロフィールドが欠如** | 必要なマクロフィールドが省かれると一部スキャナがバーコードを無視する | 少なくとも `FileID`、`SegmentID`、`SegmentsCount`、`Terminator` を設定 |
| **`XDimension` が小さすぎる** | 1 ピクセル未満の値は低解像度ディスプレイで読めないバーコードになる | 多くの画面・印刷シナリオでは `XDimension` を 2 ピクセル以上に保つ |
| **ファイルパスエラー** | 存在しない相対パスを指定すると例外がスローされる | `Path.Combine(Environment.CurrentDirectory, "ExtPDF417Meta.png")` もしくは絶対パスを使用 |

## 完全なソースコード

以下は新しいコンソールプロジェクトにコピーできる、完全に実行可能なサンプルです。

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode.BarCodeImageFormat;

namespace MacroPdf417Demo
{
    class Program
    {
        static void Main()
        {
            // Initialise the generator with MacroPdf417 and the payload text
            using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MacroPdf417, "Åspóse.Barcóde©"))
            {
                // Visual appearance
                generator.Parameters.Barcode.XDimension.Pixels = 2;          // module width
                generator.Parameters.Barcode.Pdf417.Columns = 5;           // number of columns

                // Macro fields – how to add macro
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
                generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;
                generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";
                generator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234;
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000;
                generator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2019, 11, 1);
                generator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
                generator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
                generator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;

                // Save the barcode – how to generate pdf417
                generator.Save("ExtPDF417Meta.png", BarCodeImageFormat.Png);
            }

            Console.WriteLine("MacroPdf417 barcode generated successfully.");
        }
    }
}
```

プログラムを実行（`dotnet run`）すると、コンソールに成功メッセージが表示され、PNG ファイルがプロジェクトの出力フォルダーに生成されます。

## 次のステップ

* **大容量データのエンコード** – `Columns` を増やすか、`Pdf417.Rows`（via `Pdf417.Rows`）を調整して文字数を増やす  
* **PDF への埋め込み** – Aspose.PDF を使用して生成した PNG を文書に配置  
* **スキャン検証** – `Aspose.BarCode.Reader` を利用してバーコードをデコードし、プログラム上でマクロフィールドを確認  

これらのトピックを探求することで、**リッチなマクロ情報を持つ PDF417 バーコード** の生成方法を深く理解でき、バッチ文書処理や安全なデータ交換といった実務シナリオに備えることができます。

---

*Happy coding! If you found this guide useful, consider sharing it with teammates or starring the Aspose.BarCode repository on GitHub.*

## 次に学ぶべきこと

以下のチュートリアルは、本ガイドで示した手法を基にした関連トピックを扱っています。各リソースには完全な動作コード例とステップバイステップの解説が含まれており、API の追加機能を習得したり、独自プロジェクトで代替実装アプローチを試したりするのに役立ちます。

- [How to create macro PDF417 barcode in C# using Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/how-to-create-macro-pdf417-barcode-in-c-using-aspose-barcode/)
- [How to generate PDF417 barcode in C# with Barcode Generator](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-with-barcode-generator/)
- [Aspose barcode example: generate Macro PDF417 in C#](/barcode/english/net/compact-pdf417-encoding/aspose-barcode-example-generate-macro-pdf417-in-c/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}