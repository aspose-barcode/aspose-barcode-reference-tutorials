---
category: general
date: 2026-07-18
description: Aspose.BarCode for .NET を使用してテキスト付きバーコードを生成します。PDF417 バーコードの生成方法、マクロオプションの設定、PNG
  画像へのエクスポート方法を学びましょう。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate barcode with text
- how to generate pdf417
language: ja
lastmod: 2026-07-18
og_description: C#でテキスト付きバーコードを素早く生成します。このステップバイステップのチュートリアルでは、PDF417バーコードの生成方法、マクロ設定の構成、PNGとしての保存方法を示します。
og_image_alt: Screenshot of a generated barcode with text using Aspose.BarCode
og_title: テキスト付きバーコードを生成 – マスター PDF417 マクロ作成
schemas:
- author: Aspose
  dateModified: '2026-07-18'
  description: Generate barcode with text using Aspose.BarCode for .NET. Learn how
    to generate PDF417 barcodes, set macro options, and export PNG images.
  headline: Generate barcode with text – Full PDF417 Macro Guide
  type: TechArticle
tags:
- barcode generation
- PDF417
- Aspose.BarCode
title: テキスト付きバーコード生成 – 完全PDF417マクロガイド
url: /ja/net/compact-pdf417-encoding/generate-barcode-with-text-full-pdf417-macro-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# テキスト付きバーコード生成 – 完全な PDF417 マクロガイド

PDF417 バーコードを生成し、カスタムテキストも埋め込む方法を考えたことはありますか？このチュートリアルでは、Aspose.BarCode for .NET を使用して **テキスト付きバーコードを生成** する方法を正確に示し、Macro PDF417 シンボルに必要なすべての設定を順に解説します。余計な説明は省き、すぐにプロジェクトに組み込める完全な実行可能サンプルをご紹介します。

We’ll cover:

* 必要な NuGet パッケージと using ディレクティブ。
* Unicode 文字を含むバーコードジェネレータの作成方法。
* モジュールサイズ、列数、マクロ固有の ID の設定。
* 結果を PNG ファイルとして保存し、出力を検証する方法。

By the end you’ll have a ready‑to‑use PNG image of a Macro PDF417 barcode that you can embed in invoices, tickets, or any document that needs a machine‑readable segment.

---

## 前提条件

本題に入る前に、以下が揃っていることを確認してください。

| 要件 | 理由 |
|------|------|
| **.NET 6.0** 以上 | Aspose.BarCode は .NET Standard 2.0+ をサポートしているため、.NET 6 は最新のランタイムを提供します。 |
| **Visual Studio 2022**（または任意の C# IDE） | 編集とデバッグが容易になるためです。 |
| **Aspose.BarCode for .NET** NuGet パッケージ | 実際にバーコードを生成するライブラリです。`dotnet add package Aspose.BarCode` でインストールします。 |
| 出力フォルダーへの **書き込み権限** | `Save` メソッドは PNG ファイルを書き込む必要があります。 |

これらのいずれかが馴染みがない場合は、まず取得しておいてください。そうしないとコードが明らかな例外をスローします。

---

## ステップ 1 – ライブラリのインストールとインポート

First, add the NuGet package to your project:

```bash
dotnet add package Aspose.BarCode
```

Then, bring the necessary namespaces into scope:

```csharp
using Aspose.BarCode.Generation;   // Core generation classes
using Aspose.BarCode;               // General utilities (optional)
```

> **プロのコツ:** Visual Studio を使用している場合は、プロジェクトを右クリック → *Manage NuGet Packages* → *Aspose.BarCode* を検索し、最新の安定版をインストールしてください。

---

## ステップ 2 – カスタムテキストでバーコードジェネレータを作成

The *primary* task is to **generate barcode with text** that contains special characters like “Å” and “©”. The constructor takes the encode type and the raw data string:

```csharp
// Step 2: Initialise a Macro PDF417 generator with Unicode text
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.MacroPdf417,            // Macro PDF417 type
    "Åspóse.Barcóde©");                 // Text to encode (Unicode supported)
```

重要なポイント: `EncodeTypes.MacroPdf417` は Aspose にマクロバージョンを使用することを指示し、大きなメッセージを複数のシンボルに分割できるようにします。テキスト文字列は任意の UTF‑8 シーケンスで構いません。Aspose が内部で変換を行います。

---

## ステップ 3 – 基本的な外観の調整（モジュールサイズ）

A barcode’s “module” is the smallest black‑or‑white square. Setting its pixel size controls overall image dimensions without changing data density:

```csharp
// Step 3: Set module (X‑dimension) size to 2 pixels
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

印刷用に画像を大きくしたい場合は、この値を 4 や 6 に上げてください。ただし、モジュールが大きくなると最終的な PNG のサイズも増加することを覚えておきましょう。

---

## ステップ 4 – Macro PDF417 固有のオプション設定

Macro PDF417 adds two identifiers that let a scanner stitch together multiple symbols. You’ll typically set:

| プロパティ | 機能 |
|------------|------|
| `Columns` | シンボルあたりのデータ列数（幅に影響）。 |
| `MacroPdf417FileID` | マクロ全体の一意な ID（≤ 2³¹‑1 が必要）。 |
| `MacroPdf417SegmentID` | 現在のセグメントのインデックス（0‑254）。 |

Here’s the code:

```csharp
// Step 4: Define macro‑specific settings
barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 4;                     // Narrower barcode
barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;   // Consistent across all segments
barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;      // This is segment #12
```

**エッジケースの注意:** `MacroPdf417FileID` は同一論理ファイル内のすべてのセグメントで同じである必要があります。複数のセグメントを生成する場合は同じ ID を再利用しないと、結合できない無関係なシンボルができてしまいます。

---

## ステップ 5 – バーコードを PNG 画像として保存

Now that everything’s configured, write the image to disk:

```csharp
// Step 5: Export the barcode to PNG
string outputPath = @"C:\Barcodes\MacroPdf417Main.png";
barcodeGenerator.Save(outputPath, BarCodeImageFormat.Png);
```

The `Save` method automatically creates the PNG, handling DPI and color depth for you. After execution, open the file to see something like this:

![テキスト付きバーコード生成例](/images/barcode-example.png){.center alt="テキスト付きバーコード生成例"}

バーコードが表示されない場合は、フォルダーが存在するか、アプリケーションに書き込み権限があるかを再確認してください。

---

## 完全な実行可能サンプル

Copy the whole snippet below into a new console app (`dotnet new console`) and run it. It will produce the PNG in the `C:\Barcodes` folder (create the folder first).

```csharp
using System;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // 1️⃣ Initialise generator with Unicode text
        BarcodeGenerator generator = new BarcodeGenerator(
            EncodeTypes.MacroPdf417,
            "Åspóse.Barcóde©");

        // 2️⃣ Set module size (pixel density)
        generator.Parameters.Barcode.XDimension.Pixels = 2;

        // 3️⃣ Macro‑PDF417 specific settings
        generator.Parameters.Barcode.Pdf417.Columns = 4;
        generator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
        generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;

        // 4️⃣ Export to PNG
        string path = @"C:\Barcodes\MacroPdf417Main.png";
        generator.Save(path, BarCodeImageFormat.Png);

        Console.WriteLine($"Barcode saved to {path}");
    }
}
```

**Expected output** (console):

```
Barcode saved to C:\Barcodes\MacroPdf417Main.png
```

そして PNG には、テキスト “Åspóse.Barcóde©” を含むコンパクトな Macro PDF417 シンボルが表示されます。

---

## よくある質問と落とし穴

| 質問 | 回答 |
|------|------|
| *別の画像形式を使用できますか？* | もちろんです。`BarCodeImageFormat.Png` を `Jpeg`、`Bmp`、または `Gif` に置き換えるだけです。PNG はロスレスなのでデフォルトとして使用しています。 |
| *複数のセグメントが必要な場合は？* | `BarcodeGenerator` をセグメントごとに新規作成し、`MacroPdf417FileID` を同一に保ち、`MacroPdf417SegmentID` を 0‑254 の範囲でインクリメントします。 |
| *テキストに絵文字が含まれています—動作しますか？* | Aspose.BarCode は UTF‑8 をサポートしているため、ほとんどの絵文字は使用可能です。ただし、対象のスキャナーがデコードできるか確認してください。多くの産業用スキャナーは英数字データのみ対応しています。 |
| *ラベルに対してバーコードが幅広すぎます。* | `Columns` を減らすか、モジュールサイズを大きくしてください。列数を減らすとシンボルが狭くなりますが、より高 DPI のプリンターが必要になる場合があります。 |
| *ライセンスは必要ですか？* | 評価用の無料ライセンスでもテストは可能ですが、透かしが付加されます。製品版ではライセンスを購入して透かしを除去し、すべての機能を利用してください。 |

---

## 次のステップ

Now that you know **how to generate PDF417** barcodes with custom text, you might want to:

* **Decode**: Aspose.BarCode の `BarCodeReader` を使用してモバイルアプリでバーコードをデコードする。  
* **Combine**: �数のマクロセグメントを単一の PDF ドキュメントに結合し、バッチ印刷する。  
* **Explore other symbologies** (QR, DataMatrix): 同様のパラメータパターンで他のシンボル（QR、DataMatrix）を試す。  
* **Adjust error correction level**: `Pdf417.ErrorCorrectionLevel` を使用して過酷な環境向けに誤り訂正レベルを調整する。  

These topics build on the same core concepts you just learned, so you’ll find the transition smooth.

---

## 結論

We’ve walked through a complete, end‑to‑end solution that lets you **generate barcode with text** and, specifically, **how to generate PDF417** macro symbols using Aspose.BarCode for .NET. By setting the X‑dimension, column count, and macro IDs, you gain full control over size, layout, and multi‑segment handling. The resulting PNG can be printed, embedded in PDFs, or sent to a scanner without any further conversion.

Give it a try, tweak the parameters, and let the barcode work for your business case. If you hit a snag, the Aspose documentation and community forums are excellent follow‑up resources. Happy coding!

## 次に学ぶべきことは？

The following tutorials cover closely related topics that build on the techniques demonstrated in this guide. Each resource includes complete working code examples with step‑by‑step explanations to help you master additional API features and explore alternative implementation approaches in your own projects.

- [PDF417 バーコードの生成方法 – コンパクト PDF417 エンコーディング](/barcode/english/net/compact-pdf417-encoding/)
- [Aspose.BarCode for .NET を使用した DataMatrix バーコードの生成](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-macro-configuration/)
- [バーコードの生成方法 – 1 次元バーコードタイプ](/barcode/english/net/one-dimensional-barcode-types/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}