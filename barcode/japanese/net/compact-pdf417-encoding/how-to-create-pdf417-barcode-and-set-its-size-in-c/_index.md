---
category: general
date: 2026-09-22
description: C#でPDF417バーコードを作成し、バーコードサイズを設定し、ステップバイステップのコード例でバーコード画像ファイルを生成する方法を学びましょう。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create PDF417 barcode
- how to create PDF417
- set barcode size
- create barcode image c#
language: ja
lastmod: 2026-09-22
og_description: C#でPDF417バーコードを素早く作成します。このチュートリアルでは、バーコードのサイズ設定、コンパクトモードの有効化、そして任意の.NETプロジェクト向けにPNG画像を出力する方法を紹介します。
og_image_alt: Screenshot of a generated PDF417 barcode image created with C# code
og_title: C#でPDF417バーコードを作成する – ステップバイステップガイド
schemas:
- author: Aspose
  dateModified: '2026-09-22'
  description: Learn how to create PDF417 barcode in C#, set barcode size, and generate
    barcode image files with clear step‑by‑step code examples.
  headline: How to create PDF417 barcode and set its size in C#
  type: TechArticle
tags:
- PDF417
- C#
- Barcode
- Imaging
title: C#でPDF417バーコードを作成し、サイズを設定する方法
url: /ja/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-and-set-its-size-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# C# で PDF417 バーコードを作成しサイズを設定する方法

C# で **PDF417 バーコードを作成** したい場合、本ガイドではバーコードの生成方法、サイズの調整方法、画像ファイルとしての保存手順を解説します。チケットシステム、物流ラベル、セキュア認証情報など、さまざまな用途で PDF417 形式をマスターすれば、大量のデータをコンパクトなビジュアルでエンコードできます。

このチュートリアルで学べること：

* **Aspose.BarCode（または互換ライブラリ）** を使用した **PDF417 バーコードの作成**。  
* X‑dimension と列数を調整して **バーコードのサイズを設定**。  
* C# で **PNG、JPEG、BMP 形式** のバーコード画像を生成。  

例では Aspose.BarCode for .NET の無料コミュニティエディションを使用していますが、同様のプロパティを持つ他のライブラリでも同様の概念が適用できます。

## 前提条件

開始する前に以下を確認してください：

* .NET 6.0 SDK 以降がインストール済み。  
* C# 用 IDE（Visual Studio、Visual Studio Code、Rider など）。  
* `Aspose.BarCode` NuGet パッケージ（`dotnet add package Aspose.BarCode`）。  

追加設定は不要です。ライブラリは Windows、Linux、macOS で動作します。

## 手順 1: 基本的な PDF417 バーコードを作成しサイズを設定する

まず `BarcodeGenerator` を `EncodeTypes.Pdf417` 列挙体でインスタンス化し、エンコードしたいテキストを指定します。その後 **X‑dimension**（モジュール幅）と **列数** を調整して全体サイズを制御します。

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;

// Define the text that the barcode will represent.
string data = "Sample text for PDF417 barcode";

// Create a basic PDF417 barcode generator.
var basicPdf417 = new BarcodeGenerator(EncodeTypes.Pdf417, data);

// Set the module width to 2 pixels (controls bar thickness).
basicPdf417.Parameters.Barcode.XDimension.Pixels = 2;

// Set the column count; 3 columns yields a compact visual but still readable.
basicPdf417.Parameters.Barcode.Pdf417.Columns = 3;

// Save the barcode as a PNG image.
string basicPath = Path.Combine("YOUR_DIRECTORY", "Pdf417Basic.png");
basicPdf417.Save(basicPath, BarCodeImageFormat.Png);
```

**これらの設定が重要な理由**

* `XDimension.Pixels` は最も細いバーの幅を決定します。値が小さいほどバーコードは密になり、値が大きいほど低解像度スキャナでの可読性が向上します。  
* `Pdf417.Columns` はバーコードのアスペクト比に影響します。列数が少ないとバーコードは縦長になり、列数が多いと横長になります。列数の調整は **エンコードデータを変更せずにサイズを設定** する主な手段です。

コードを実行すると、指定フォルダーに `Pdf417Basic.png` が生成されます。画像は以下のスクリーンショットと同様です：

<img src="images/pdf417-basic.png" alt="基本的な PDF417 バーコードのレイアウト例">

## 手順 2: 同じサイズでコンパクトな PDF417 バーコード（トランケートモード）を作成する

スペースが限られる場合、短いバーコードが必要になることがあります。PDF417 にはストップパターンを除去し全体の高さを削減する *トランケート*（コンパクト）モードがあります。`Truncate` プロパティでこの動作を切り替えます。

```csharp
// Reuse the same data string.
var compactPdf417 = new BarcodeGenerator(EncodeTypes.Pdf417, data);

// Keep the same module width and column count for a fair size comparison.
compactPdf417.Parameters.Barcode.XDimension.Pixels = 2;
compactPdf417.Parameters.Barcode.Pdf417.Columns = 3;

// Enable compact (truncate) mode – this removes the stop pattern.
compactPdf417.Parameters.Barcode.Pdf417.Truncate = true;

// Save the compact version.
string compactPath = Path.Combine("YOUR_DIRECTORY", "CompactPdf417.png");
compactPdf417.Save(compactPath, BarCodeImageFormat.Png);
```

**`Truncate = true` で何が変わるか？**

* バーコードの高さが約 15‑20 % 短くなり、ラベルやモバイル画面で有用です。  
* データは完全に復元可能で、ほとんどの最新スキャナはトランケートモードを自動的に認識します。

生成された `CompactPdf417.png` は基本バーコードの細身バージョンとして表示されます。

## 手順 3: Micro PDF417 バーコードを作成し、列数を調整して保存する

Micro PDF417 は非常に小さなスペース（例：ID カード）向けに設計された高密度バリアントです。列数は 1‑4 のみサポートされ、サイズ制御は同じ `XDimension` プロパティで行います。

```csharp
// Create a Micro PDF417 generator.
var microPdf417 = new BarcodeGenerator(EncodeTypes.MicroPdf417, data);

// Set module width – 2 pixels works well for most printers.
microPdf417.Parameters.Barcode.XDimension.Pixels = 2;

// Micro PDF417 allows only 1 to 4 columns; choose 4 for a more square shape.
microPdf417.Parameters.Barcode.Pdf417.Columns = 4;

// Save the micro barcode.
string microPath = Path.Combine("YOUR_DIRECTORY", "MicroPdf417.png");
microPdf417.Save(microPath, BarCodeImageFormat.Png);
```

**Micro PDF417 の重要ポイント**

* `EncodeTypes.MicroPdf417` 列挙体で自動的にマイクロバリアントが選択されます。  
* シンボルが密なので、可読性を保つために 300 dpi 以上のプリンタが必要になることがあります。  
* 列数の調整が唯一のサイズ調整手段で、`XDimension` も引き続き有効です。

## 出力フォーマット別にバーコードサイズを設定する方法

上記例は PNG を使用していますが、同じ `Save` メソッドで JPEG、BMP、TIFF も扱えます。特定の画像サイズ（例：300 × 150 px）が必要な場合は、`XDimension` と `ResolutionX`/`ResolutionY` を組み合わせます。

```csharp
basicPdf417.Parameters.ImageResolution = 300; // DPI
basicPdf417.Parameters.Barcode.XDimension.Pixels = 3; // larger modules for higher DPI
basicPdf417.Save("Pdf417HighRes.jpg", BarCodeImageFormat.Jpeg);
```

`ImageResolution` を上げつつ `XDimension` をスケーリングすれば、高解像度印刷時の視覚品質が保たれます。

## よくある落とし穴とプロのコツ

| 問題 | 発生理由 | 対策 |
|------|----------|------|
| 画面上でバーコードがぼやけて見える | 小さな `XDimension` と低 DPI の組み合わせ | `ImageResolution` と/または `XDimension.Pixels` を増やす |
| スキャナがトランケートモードを読めない | 古いスキャナのファームウェアが未対応 | レガシーハードウェア向けにフル（非トランケート）モードを使用 |
| Micro PDF417 が読めない | 300 dpi 未満で印刷、またはコントラスト不足 | 300 dpi 以上のマット紙に印刷し、前景を濃くする |
| 出力ファイルが破損している | 書き込み先フォルダーへの権限がない | `YOUR_DIRECTORY` が存在し書き込み可能か確認 |

**プロのコツ**：後続処理（例：PDF への埋め込み）でロスレス品質が必要な場合は、常に PNG でバーコードを生成してください。PNG はピクセル値を正確に保持しますが、JPEG は圧縮アーティファクトが入り、可読性に影響することがあります。

## 完全な実行可能サンプル

以下は 3 種類のバーコードを一度に生成するコンソールアプリの全コードです。新しい .NET コンソールプロジェクトにコピーして実行してください。

```csharp
using System;
using System.IO;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // The text to encode – change this to whatever data you need.
        const string data = "Sample text for PDF417 barcode";

        // Directory where images will be saved.
        string outputDir = Path.Combine(Environment.CurrentDirectory, "Barcodes");
        Directory.CreateDirectory(outputDir);

        // ---------- Basic PDF417 ----------
        var basicPdf417 = new BarcodeGenerator(EncodeTypes.Pdf417, data);
        basicPdf417.Parameters.Barcode.XDimension.Pixels = 2;
        basicPdf417.Parameters.Barcode.Pdf417.Columns = 3;
        string basicPath = Path.Combine(outputDir, "Pdf417Basic.png");
        basicPdf417.Save(basicPath, BarCodeImageFormat.Png);
        Console.WriteLine($"Basic PDF417 saved to {basicPath}");

        // ---------- Compact (Truncate) PDF417 ----------
        var compactPdf417 = new BarcodeGenerator(EncodeTypes.Pdf417, data);
        compactPdf417.Parameters.Barcode.XDimension.Pixels = 2;
        compactPdf417.Parameters.Barcode.Pdf417.Columns = 3;
        compactPdf417.Parameters.Barcode.Pdf417.Truncate = true;
        string compactPath = Path.Combine(outputDir, "CompactPdf417.png");
        compactPdf417.Save(compactPath, BarCodeImageFormat.Png);
        Console.WriteLine($"Compact PDF417 saved to {compactPath}");

        // ---------- Micro PDF417 ----------
        var microPdf417 = new BarcodeGenerator(EncodeTypes.MicroPdf417, data);
        microPdf417.Parameters.Barcode.XDimension.Pixels = 2;
        microPdf417.Parameters.Barcode.Pdf417.Columns = 4; // 1‑4 allowed
        string microPath = Path.Combine(outputDir, "MicroPdf417.png");
        microPdf417.Save(microPath, BarCodeImageFormat.Png);
        Console.WriteLine($"Micro PDF417 saved to {microPath}");
    }
}
```

**期待される出力**

プログラム実行後、`Barcodes` フォルダー内に 3 つの PNG ファイルが作成されます：

* `Pdf417Basic.png` – 3 列の標準 PDF417 バーコード。  
* `CompactPdf417.png` – 同じデータをトランケート（コンパクト）モードで、やや短くなります。  
* `MicroPdf417.png` – 4 列の高密度 Micro PDF417 バリアント。

任意の画像ビューアで開くと、特徴的なスタック構造が確認できます。

## 次に学ぶべきことは？

以下のチュートリアルは、本ガイドで示したテクニックを応用した関連トピックを扱っています。各リソースには完全なコード例とステップバイステップの解説が含まれており、API の追加機能習得や代替実装アプローチの探求に役立ちます。

- [How to Create Barcode – Compact PDF417 with Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [How to Set Error Level in PDF417 Barcode – Complete Guide](/barcode/english/net/compact-pdf417-encoding/how-to-set-error-level-in-pdf417-barcode-complete-guide/)
- [Create PDF417 Barcode Metadata in C# – Complete Step‑by‑Step Guide](/barcode/english/net/compact-pdf417-encoding/create-pdf417-barcode-metadata-in-c-complete-step-by-step-gu/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}