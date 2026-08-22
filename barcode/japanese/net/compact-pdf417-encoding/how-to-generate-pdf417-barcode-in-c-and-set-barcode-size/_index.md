---
category: general
date: 2026-08-22
description: Aspose.BarCode を使用して C# で PDF417 バーコードを生成し、バーコードのサイズを設定し、列を調整し、コンパクトモードを有効にする方法を学びましょう。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate pdf417 barcode
- how to generate pdf417
- set barcode size
language: ja
lastmod: 2026-08-22
og_description: Aspose.BarCode を使用して C# で PDF417 バーコードを生成します。このガイドでは、バーコードのサイズ設定、列数の制御、そして小さい画像のためにコンパクトモードを有効にする方法を示します。
og_image_alt: Screenshot of a generated PDF417 barcode in C# showing compact mode
og_title: C#でPDF417バーコードを生成 – サイズ、列数、コンパクトモードを設定
schemas:
- author: Aspose
  dateModified: '2026-08-22'
  description: Learn how to generate PDF417 barcode in C# with Aspose.BarCode, set
    barcode size, adjust columns, and enable compact mode.
  headline: How to generate PDF417 barcode in C# and set barcode size
  type: TechArticle
tags:
- pdf417
- barcode
- csharp
title: C#でPDF417バーコードを生成し、バーコードのサイズを設定する方法
url: /ja/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-and-set-barcode-size/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# C# で PDF417 バーコードを生成し、バーコードサイズを設定する方法

If you need to **generate PDF417 barcode** in a .NET application, this guide walks you through the complete process. You’ll see exactly **how to generate PDF417** with Aspose.BarCode, adjust the **set barcode size**, and produce a compact PNG that can be embedded in reports or mobile apps.

.NET アプリケーションで **PDF417 バーコードを生成** する必要がある場合、このガイドではプロセス全体を順を追って説明します。Aspose.BarCode を使用して **PDF417 を生成** する方法、**バーコードサイズを設定** する方法、そしてレポートやモバイルアプリに埋め込めるコンパクトな PNG の作成方法が分かります。

Creating a barcode doesn’t require a separate graphics editor. By the end of this tutorial you will have a fully functional C# method that produces a PDF417 image with the exact dimensions you need, ready for downstream processing.

バーコードの作成には別途のグラフィックエディタは不要です。このチュートリアルの最後までに、必要な正確なサイズの PDF417 画像を生成する完全な C# メソッドが手に入り、以降の処理にすぐ使えるようになります。

## 学べること

* Aspose.BarCode ライブラリをインストールし、参照する。
* PDF417 バーコードジェネレータを作成し、エンコードするテキストを指定する。
* **バーコードサイズを設定** は X‑dimension と列数を構成して行う。
* コンパクト（トランケート）モードを有効にしてシンボルを縮小する。
* 結果を PNG ファイルとして保存する。
* 読み取り不能なコードやサイズが大きすぎる画像など、一般的な問題のトラブルシューティングを行う。

### 前提条件

* .NET 6.0 以降（API は .NET Framework 4.6+ でも動作します）。
* C# と Visual Studio（または任意の C# IDE）に関する基本的な知識。
* 有効な Aspose.BarCode ライセンス（無料評価版はテストに使用可能）。

> **プロのコツ:** ループで多数のバーコードを生成する場合、単一の `BarcodeGenerator` インスタンスを再利用し、`CodeText` プロパティだけを変更してください。これによりメモリ割り当てが削減されます。

## Aspose.BarCode で PDF417 バーコードを生成する

The first step is to instantiate the `BarcodeGenerator` for the PDF417 symbology. This object is the entry point for all barcode operations.

最初のステップは PDF417 シンボロジー用に `BarcodeGenerator` をインスタンス化することです。このオブジェクトがすべてのバーコード操作のエントリーポイントになります。

```csharp
using Aspose.BarCode.Generation;

// Step 1: Create a PDF417 barcode generator with the desired text
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.Pdf417,          // Symbology
    "Sample text for PDF417");   // Data to encode
```

*重要な理由*: `EncodeTypes.Pdf417` はライブラリに PDF417 標準を使用させることを示し、大量のデータとエラー訂正をサポートします。コンストラクタはエンコードしたいデータも受け取るため、後で別途 `CodeText` を設定する必要がなくなります。

## バーコードサイズと列数の設定

PDF417 symbols consist of rows and columns of small rectangular modules. Controlling the module width (X‑dimension) and the number of columns lets you fine‑tune the overall dimensions.

PDF417 シンボルは小さな長方形モジュールの行と列で構成されています。モジュール幅（X‑dimension）と列数を制御することで、全体のサイズを細かく調整できます。

```csharp
// Step 2: Adjust the module size (X‑dimension) – 2 pixels per module
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;

// Step 3: Define the number of columns for the PDF417 code
barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 3;
```

*説明*:  
* **X‑dimension** (`Pixels`) は各モジュールの幅を決定します。小さい値はバーコードをコンパクトにし、大きい値は低解像度スキャナでの読み取りやすさを向上させます。  
* **Columns** は横方向のレイアウトを制御します。列数が少ないとバーコードが縦長になり、列数が多いと横長になります。これら二つの設定を組み合わせて、必要な **バーコードサイズを設定** してください。

## 小さなバーコードのためにコンパクトモードを有効にする

PDF417 includes a “compact” (or truncated) mode that removes unnecessary padding and reduces the overall footprint. This is especially useful when you have limited screen real estate.

PDF417 には不要な余白を削除し、全体の占有領域を減らす “コンパクト”（またはトランケート）モードがあります。画面スペースが限られている場合に特に有用です。

```csharp
// Step 4: Enable compact mode to truncate the barcode data
barcodeGenerator.Parameters.Barcode.Pdf417.Truncate = true;
```

*なぜトランケーションを有効にするのか？*  
`Truncate` が `true` の場合、ジェネレータはストップパターンと、ほとんどのスキャンシナリオで不要なエラー訂正コードワードを省略します。その結果、画像は約 15‑20 % 小さくなり、典型的な使用ケースでデータの完全性を損なうことはありません。

## バーコードを PNG 画像として保存する

After configuring size and mode, write the barcode to disk. PNG is lossless, ensuring that the module edges remain sharp.

サイズとモードを設定したら、バーコードをディスクに書き出します。PNG はロスレス形式で、モジュールのエッジが鮮明に保たれます。

```csharp
// Step 5: Save the generated barcode as a PNG image
barcodeGenerator.Save(
    "YOUR_DIRECTORY/CompactPdf417.png",
    BarCodeImageFormat.Png);
```

The file `CompactPdf417.png` will contain a crisp PDF417 symbol that matches the dimensions you set in the previous steps.

ファイル `CompactPdf417.png` には、前のステップで設定した寸法に一致する鮮明な PDF417 シンボルが含まれます。

### 期待される出力

Opening the saved PNG should display a vertical‑oriented PDF417 barcode consisting of three columns, each module 2 px wide, and a total size of roughly **120 × 240 px** (width × height). Scanning the image with any standard PDF417 reader returns the original text “Sample text for PDF417”.

保存した PNG を開くと、縦向きの PDF417 バーコードが表示されます。3 列で構成され、各モジュールは 2 px の幅、全体サイズはおおよそ **120 × 240 px**（幅 × 高さ）です。標準的な PDF417 リーダーで画像をスキャンすると、元のテキスト “Sample text for PDF417” が取得されます。

## よくある落とし穴と回避方法

| 症状 | 考えられる原因 | 対策 |
|---------|--------------|-----|
| バーコードが読み取れない | スキャナに対して X‑dimension が小さすぎる | `XDimension.Pixels` を 3 または 4 に増やす |
| 画像が UI に対して幅が広すぎる | 列数が多すぎる | `Pdf417.Columns` を減らすか、`Truncate` を有効にする |
| 例外 `ArgumentOutOfRangeException` | 列数が負またはゼロ | `Columns` が正の整数（最小 1）であることを確認する |
| PNG ファイルが空 | 出力パスが存在しない、または書き込み権限がない | ディレクトリが存在し、アプリに書き込み権限があるか確認する |

> **プロのコツ:** `Save()` を呼び出す前に `barcodeGenerator.ValidateParameters()` を使用して、設定エラーを早期に検出してください。

## 完全な実行可能サンプル

Below is a self‑contained console program that incorporates all the steps above. Copy it into a new C# project, restore the Aspose.BarCode NuGet package, and run it to see the result.

以下は上記すべての手順を組み込んだ単体のコンソールプログラムです。新しい C# プロジェクトにコピーし、Aspose.BarCode の NuGet パッケージを復元して実行すると結果が確認できます。

```csharp
using System;
using Aspose.BarCode.Generation;

namespace Pdf417Demo
{
    class Program
    {
        static void Main()
        {
            // Create the generator with the data to encode
            var generator = new BarcodeGenerator(
                EncodeTypes.Pdf417,
                "Sample text for PDF417");

            // Set module width (X‑dimension) – 2 px per module
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // Choose a small number of columns to keep the barcode compact
            generator.Parameters.Barcode.Pdf417.Columns = 3;

            // Enable truncation for a smaller image
            generator.Parameters.Barcode.Pdf417.Truncate = true;

            // Optional: validate parameters before saving
            generator.ValidateParameters();

            // Save as PNG
            const string outputPath = "CompactPdf417.png";
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"PDF417 barcode saved to {outputPath}");
        }
    }
}
```

**プログラムを実行**すると、実行ファイルの作業ディレクトリに `CompactPdf417.png` が生成されます。モバイルアプリ（例: “Barcode Scanner”）で画像をスキャンし、エンコードされたテキストが元の文字列と一致することを確認してください。

## 次のステップと関連トピック

* **エラー訂正レベルを上げる** – ノイズの多いスキャン環境向けに `Pdf417.ErrorLevel` を調整します。  
* **向きの変更** – 横向きレイアウトが必要な場合は `Pdf417.Rotate` を `RotationAngle.Rotate90` に設定します。  
* **PDF にバーコードを埋め込む** – Aspose.PDF と Aspose.BarCode を組み合わせて、画像を直接ドキュメントに配置します。  
* **他の 2 次元バーコードを生成** – 同じ `BarcodeGenerator` クラスは DataMatrix、QR、Aztec コードもサポートしています。目的のシンボロジーに合わせて `EncodeTypes.Pdf417` を置き換えるだけです。

By mastering **generate PDF417 barcode** techniques, you can automate ticketing, inventory labeling, and secure data transmission across a wide range of .NET applications.

**PDF417 バーコード生成** の技術を習得すれば、チケット発行、在庫ラベリング、データの安全な送信などを幅広い .NET アプリケーションで自動化できます。

## 結論

You now know how to **generate PDF417 barcode** in C#, precisely **set barcode size**, configure columns, enable compact mode, and save the result as a PNG. Apply these settings to fit any UI constraint or scanning requirement, and extend the approach to other barcode formats as needed. Happy coding!

これで C# で **PDF417 バーコードを生成** し、正確に **バーコードサイズを設定**、列数を構成し、コンパクトモードを有効にして PNG として保存する方法が分かりました。これらの設定を使用して UI の制約やスキャン要件に合わせ、必要に応じて他のバーコード形式にも応用してください。コーディングを楽しんでください！

## 次に学ぶべきことは？

The following tutorials cover closely related topics that build on the techniques demonstrated in this guide. Each resource includes complete working code examples with step-by-step explanations to help you master additional API features and explore alternative implementation approaches in your own projects.

以下のチュートリアルは本ガイドで示した手法を基にした、密接に関連するトピックを扱っています。各リソースには完全な動作コード例とステップバイステップの解説が含まれ、追加の API 機能を習得し、プロジェクトで代替実装アプローチを検討するのに役立ちます。

- [PDF417 バーコードの生成 – コンパクト PDF417 エンコーディング](/barcode/english/net/compact-pdf417-encoding/)
- [バーコードの作成 – Aspose.BarCode を使用したコンパクト PDF417](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [Aspose.BarCode for .NET を使用した DataMatrix バーコード生成 – ステップバイステップガイド](/barcode/english/net/datamatrix-barcode-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}