---
category: general
date: 2026-09-29
description: C#でAspose.BarCodeを使用してバーコードを保存する方法と、マクロメタデータ付きPDF417を生成する方法を学びましょう。ステップバイステップのガイドです。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to save barcode
- how to generate pdf417
- how to set pdf417
- generate barcode with aspose
language: ja
lastmod: 2026-09-29
og_description: C# で Aspose.BarCode を使用してバーコードを保存する方法は簡単です。このチュートリアルでは、マクロメタデータ付き
  PDF417 を生成し、必要なすべてのパラメータを設定する方法を示します。
og_image_alt: Screenshot showing how to save barcode as PNG with PDF417 macro metadata
og_title: Asposeでバーコードを保存する方法 – PDF417生成ガイド
schemas:
- author: Aspose
  dateModified: '2026-09-29'
  description: How to save barcode using Aspose.BarCode in C# and learn how to generate
    PDF417 with macro metadata. Follow step‑by‑step guide.
  headline: How to save barcode and generate PDF417 with Aspose in C#
  type: TechArticle
- description: How to save barcode using Aspose.BarCode in C# and learn how to generate
    PDF417 with macro metadata. Follow step‑by‑step guide.
  name: How to save barcode and generate PDF417 with Aspose in C#
  steps:
  - name: '**Creating the generator** – The `BarcodeGenerator` constructor takes the
      barcode type (`EncodeTypes.MacroPdf417`) and the data to encode. Macro PDF417
      is a special variant that carries file‑transfer information, which is why we
      later fill macro fields.'
    text: '**Creating the generator** – The `BarcodeGenerator` constructor takes the
      barcode type (`EncodeTypes.MacroPdf417`) and the data to encode. Macro PDF417
      is a special variant that carries file‑transfer information, which is why we
      later fill macro fields.'
  - name: '**Appearance settings** – `XDimension.Pixels` controls the narrow bar width;
      adjusting it changes the overall image size without affecting data integrity.
      `Pdf417.Columns` defines the layout of the barcode matrix.'
    text: '**Appearance settings** – `XDimension.Pixels` controls the narrow bar width;
      adjusting it changes the overall image size without affecting data integrity.
      `Pdf417.Columns` defines the layout of the barcode matrix.'
  - name: '**Macro metadata** – These properties (`MacroPdf417FileID`, `MacroPdf417SegmentID`,
      etc.) are essential when you need to split a large file into multiple barcode
      segments. Setting them correctly ensures that a scanner can reconstruct the
      original file.'
    text: '**Macro metadata** – These properties (`MacroPdf417FileID`, `MacroPdf417SegmentID`,
      etc.) are essential when you need to split a large file into multiple barcode
      segments. Setting them correctly ensures that a scanner can reconstruct the
      original file.'
  - name: '**Saving the image** – The `Save` method writes the generated barcode to
      disk. You can choose any supported format (`Png`, `Jpeg`, `Bmp`, etc.). This
      line demonstrates the exact **how to save barcode** operation requested.'
    text: '**Saving the image** – The `Save` method writes the generated barcode to
      disk. You can choose any supported format (`Png`, `Jpeg`, `Bmp`, etc.). This
      line demonstrates the exact **how to save barcode** operation requested.'
  type: HowTo
tags:
- barcode
- PDF417
- Aspose
- C#
title: Aspose を使用して C# でバーコードを保存し、PDF417 を生成する方法
url: /ja/net/compact-pdf417-encoding/how-to-save-barcode-and-generate-pdf417-with-aspose-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose を使用して C# でバーコードを保存し PDF417 を生成する方法

Aspose.BarCode を使用して C# でバーコードを保存することは、画像ファイルにデータを埋め込む必要がある場合の一般的な要件です。このガイドでは、マクロメタデータ付き PDF417 バーコードを生成し、結果を PNG 画像として保存する手順をすべて解説します。最後まで読むと、**PDF417 の生成方法**、**PDF417 のオプション設定方法**、そして最も重要な **バーコードの保存方法** をプログラムで実装できるようになります。

完全に実行可能なサンプルを示します。Aspose.BarCode NuGet パッケージの追加から、ファイル ID、セグメント数、チェックサムといったマクロフィールドの設定まで、すべての手順を網羅しています。外部ドキュメントは不要で、コードを新しいコンソールプロジェクトに貼り付けてすぐに実行できます。本チュートリアルは Visual Studio 2022（またはそれ以降）と .NET 6.0 がインストールされていることを前提としています。

## 前提条件

- .NET 6.0 SDK（または Aspose.BarCode 23.11+ がサポートする任意の .NET バージョン）
- Visual Studio 2022、VS Code、またはお好みの C# IDE
- **Aspose.BarCode for .NET** NuGet パッケージ  
  ```bash
  dotnet add package Aspose.BarCode
  ```
- C# の基本構文とコンソールアプリケーションに関する基礎知識

> **プロのヒント:** 商用ライセンスをまだお持ちでない場合は、Aspose の無料開発者評価ライセンスを使用してください。評価版はコードの変更なしで動作します。

## バーコードを保存する方法 – 完全サンプル

以下のコードは **Macro PDF417** バーコードを作成し、すべてのマクロフィールドを埋め込み、画像を `ExtPDF417Meta.png` として保存します。必要な `using` ディレクティブもすべて含まれているので、`Program.cs` に直接貼り付けて使用できます。

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Step 1: Create a barcode generator for Macro PDF417 with sample data
        using (BarcodeGenerator generator = new BarcodeGenerator(
            EncodeTypes.MacroPdf417,          // EncodeTypes enum selects the barcode type
            "Åspóse.Barcóde©"))               // Sample data – Unicode characters are supported
        {
            // Step 2: Define basic barcode appearance
            generator.Parameters.Barcode.XDimension.Pixels = 2;   // narrow bar width (2 px)
            generator.Parameters.Barcode.Pdf417.Columns = 5;    // number of columns per row

            // Step 3: Configure Macro PDF417 metadata
            generator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
            generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;
            generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;
            generator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";
            generator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234; // CCITT‑16 example
            generator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000;
            generator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2019, 11, 1);
            generator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
            generator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
            generator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;

            // Step 4: Save the generated barcode as a PNG image
            // This is the core of **how to save barcode** with Aspose.
            generator.Save("ExtPDF417Meta.png", BarCodeImageFormat.Png);
        }

        Console.WriteLine("Barcode saved as ExtPDF417Meta.png");
    }
}
```

### 各ステップの重要ポイント

1. **ジェネレータの作成** – `BarcodeGenerator` コンストラクタはバーコードタイプ（`EncodeTypes.MacroPdf417`）とエンコードするデータを受け取ります。Macro PDF417 はファイル転送情報を保持できる特殊なバリアントであるため、後でマクロフィールドを設定します。
2. **外観設定** – `XDimension.Pixels` は狭いバー幅を制御し、画像全体のサイズを変更しますがデータの整合性には影響しません。`Pdf417.Columns` はバーコードマトリックスのレイアウトを決定します。
3. **マクロメタデータ** – これらのプロパティ（`MacroPdf417FileID`、`MacroPdf417SegmentID` など）は、大きなファイルを複数のバーコードセグメントに分割する際に必須です。正しく設定することで、スキャナが元のファイルを再構築できます。
4. **画像の保存** – `Save` メソッドは生成したバーコードをディスクに書き出します。任意のサポート形式（`Png`、`Jpeg`、`Bmp` など）を選択可能です。この行が **バーコードの保存方法** を示す具体例です。

> **よくある質問:** *別の画像形式が必要な場合は？*  
> `BarCodeImageFormat.Png` を `BarCodeImageFormat.Jpeg`（または他のサポート列挙値）に変更し、ファイル拡張子も同様に調整してください。

## マクロメタデータ付き PDF417 の生成方法

通常の PDF417（マクロデータなし）が必要な場合は、マクロセクションを省略し、基本ジェネレータだけを使用してください。

```csharp
using (BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.Pdf417, "Sample data"))
{
    gen.Parameters.Barcode.XDimension.Pixels = 3;
    gen.Save("SimplePdf417.png", BarCodeImageFormat.Png);
}
```

上記コードは **PDF417 の生成方法** を簡潔に示しています。`EncodeTypes.Pdf417` 列挙体がマクロなしバージョンを選択している点に注目してください。

## PDF417 の設定 – 高度なオプション

Aspose.BarCode では PDF417 固有のパラメータが多数公開されています。代表的なものを以下に示します。

| プロパティ | 説明 | 典型的な値 |
|----------|------|------------|
| `Pdf417.Columns` | 行あたりの列数 | 1‑30（デフォルト 3） |
| `Pdf417.Rows` | 行数（0 の場合は自動計算） | 0‑90 |
| `Pdf417.ErrorLevel` | 誤り訂正レベル（0‑8） | バランスの取れたサイズ/耐久性のために 2‑4 |
| `Pdf417.RowsPerStrip` | 大きなバーコード用のストリップあたりの行数 | 0（自動） |
| `Pdf417.Pdf417MacroFileID` | マクロ使用時のファイル識別子 | 任意の 32 ビット整数 |

これらの値はメイン例の **ステップ 2** と同様のパターンで設定し、`Save` を呼び出す前に調整してください。

## 期待される出力

プログラムを実行すると、実行ファイルの作業ディレクトリに `ExtPDF417Meta.png` が作成されます。画像には高解像度の PDF417 バーコードが含まれ、すべてのマクロフィールドが埋め込まれています。PDF417 対応スキャナ（またはモバイルアプリ）で画像をスキャンすると、元のデータ文字列 `"Åspóse.Barcóde©"` とともにマクロメタデータ（ファイル ID、セグメント ID など）が返されます。

![PNG として保存されたバーコード – バーコード保存例](ExtPDF417Meta.png "マクロ PDF417 メタデータ付き PNG としてバーコードを保存する方法")

*画像の代替テキスト:* **how to save barcode as PNG with PDF417 macro metadata**（主要キーワードに一致）

## 結論

本チュートリアルでは、Aspose.BarCode を使用した **バーコードの保存方法**、**PDF417 の生成方法**、**PDF417 のパラメータ設定方法**、そして **Aspose でバーコードを生成する方法** を、通常版とマクロ対応版の両方で学びました。

## 次に学ぶべきこと

以下のチュートリアルは、本ガイドで示したテクニックを応用した関連トピックを扱っています。各リソースには完全なコード例とステップバイステップの解説が含まれており、API の追加機能を習得したり、独自プロジェクトで代替実装を検討したりするのに役立ちます。

- [How to Generate PDF417 Barcode with Aspose – Complete Guide](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-with-aspose-complete-guide/)
- [How to Generate PDF417 Barcode Image in C# with Aspose](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-image-in-c-with-aspose/)
- [How to generate barcode in C# with Aspose.BarCode and add metadata](/barcode/english/net/compact-pdf417-encoding/how-to-generate-barcode-in-c-with-aspose-barcode-and-add-met/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}