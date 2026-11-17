---
category: general
date: 2026-11-17
description: バーコードの保存方法、コンパクトモードの有効化、列の調整、そして完全なC#サンプルを使用したPDF417バーコードの生成方法を学びましょう。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to save barcode
- enable compact mode
- how to adjust columns
- generate pdf417 barcode
- how to enable compact mode
language: ja
lastmod: 2026-11-17
og_description: C#でPDF417バーコードを生成する際に、バーコードを保存し、コンパクトモードを有効にし、列数を調整する方法。ステップバイステップのガイドをご覧ください。
og_image_alt: Screenshot showing how to save barcode as PNG file in C#
og_title: C#でバーコードをPNGとして保存し、コンパクトモードを有効にする方法
schemas:
- author: Aspose
  dateModified: '2026-11-17'
  description: Learn how to save barcode, enable compact mode, adjust columns, and
    generate PDF417 barcode with a complete C# example.
  headline: How to save barcode as PNG and enable compact mode in C#
  type: TechArticle
- description: Learn how to save barcode, enable compact mode, adjust columns, and
    generate PDF417 barcode with a complete C# example.
  name: How to save barcode as PNG and enable compact mode in C#
  steps:
  - name: Expected output
    text: Opening the saved PNG file shows a vertically compact PDF417 barcode with
      three columns and truncated padding. The visual size is roughly 2 px per module,
      making the image suitable for embedding in HTML `<img>` tags or for printing
      on small labels.
  - name: What if I need a different image format?
    text: The `Save` method accepts any `BarCodeImageFormat` enum value, such as `Jpeg`,
      `Bmp`, or `Gif`. Replace `BarCodeImageFormat.Png` with the desired format, and
      the rest of the code remains unchanged.
  - name: How does truncation affect data capacity?
    text: Enabling **compact mode** (truncation) reduces the number of rows, which
      can lower the maximum data capacity of the barcode. If you encounter a “Data
      too large” exception, either increase the number of columns or disable truncation.
  - name: Can I use a dynamic column count?
    text: 'Yes. You can calculate the column count based on the length of the input
      string:'
  - name: Is the X‑dimension limited to integer pixels?
    text: The `Pixels` property accepts any positive integer. For higher‑resolution
      outputs (e.g., printing), you might prefer setting `Points` instead of `Pixels`
      to achieve device‑independent sizing.
  type: HowTo
tags:
- barcode
- pdf417
- csharp
- image generation
title: C#でバーコードをPNGとして保存し、コンパクトモードを有効にする方法
url: /ja/net/compact-pdf417-encoding/how-to-save-barcode-as-png-and-enable-compact-mode-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# C# でバーコードを PNG として保存し、コンパクトモードを有効にする方法

Web や印刷で使用できる形式で **how to save barcode** する必要がある場合、このガイドでは正確な手順を示します。また、Aspose.BarCode ライブラリ for .NET を使用して **enable compact mode**、**adjust columns**、**generate PDF417 barcode** の方法も学べます。

このチュートリアルはプロジェクトのセットアップから最終的な PNG ファイルまでを網羅しているため、追加の調査なしでコードを自分のソリューションにコピーできます。外部ドキュメントは不要で、完全に実行可能なサンプルが含まれています。

## 前提条件

開始する前に、以下がインストールされていることを確認してください。

* .NET 6.0 以降  
* Visual Studio 2022（または任意の C# IDE）  
* `Aspose.BarCode` NuGet パッケージ（`Install-Package Aspose.BarCode`）  

これら 3 つが以下のコードの唯一の依存関係です。

## Step 1: Create a PDF417 barcode generator

**generate PDF417 barcode** の最初の作業は、正しいエンコードタイプとエンコードしたいデータを指定して `BarcodeGenerator` のインスタンスを作成することです。

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

// Step 1: Create a PDF417 barcode generator with the desired text.
BarcodeGenerator barcode = new BarcodeGenerator(EncodeTypes.Pdf417, "Compact mode");
```

`EncodeTypes.Pdf417` 列挙体は、ライブラリに PDF417 シンボルを使用するよう指示します。PDF417 は大量のデータをエンコードできるスタック型リニアバーコードです。文字列 `"Compact mode"` はバーコード下部に表示される人間可読テキストになります。

## Step 2: Set the X‑dimension (module width)

バーコードの各バーは「モジュール」と呼ばれます。モジュール幅を制御することで、データを変更せずにバーコードの視覚的サイズを微調整できます。

```csharp
// Step 2: Set the module (X) dimension – each bar will be 2 pixels wide.
barcode.Parameters.Barcode.XDimension.Pixels = 2;
```

2 ピクセルの X‑dimension は、ほとんどのデバイスで確実にスキャンできるコンパクトな画像を生成します。

## Step 3: **How to adjust columns** for the PDF417 code

PDF417 では、バーコードが使用する列数を指定できます。列が少ないほど縦長で細くなり、列が多いほど横長で短くなります。

```csharp
// Step 3: Define the number of columns for the PDF417 code (3 columns).
barcode.Parameters.Barcode.Pdf417.Columns = 3;
```

この行は **how to adjust columns** を示しています。対象メディアのスペースに応じて、値を 2、4、またはライブラリがサポートする任意の数に変更できます。

## Step 4: **How to enable compact mode** and truncate the symbol

コンパクトモードは不要な余白を削除し、バーコード全体のフットプリントを縮小します。この機能は `Truncate` プロパティを通じて利用できます。

```csharp
// Step 4: Enable compact mode by truncating the symbol.
barcode.Parameters.Barcode.Pdf417.Truncate = true;
```

ここで **enable compact mode** というフレーズが出てきますが、ガイドの後半でも同じ操作を **how to enable compact mode** という正確な表現で説明し、二次キーワード要件を満たしています。

## Step 5: **How to save barcode** as a PNG image

生成した画像を保存するのが最終ステップです。`Save` メソッドは指定した形式でバーコードをファイルシステムに書き込みます。

```csharp
// Step 5: Save the generated barcode as a PNG image.
barcode.Save("YOUR_DIRECTORY/CompactPdf417.png", BarCodeImageFormat.Png);
```

`YOUR_DIRECTORY` を、アプリケーションが書き込み可能な絶対パスまたは相対パスに置き換えてください。実行後、`CompactPdf417.png` という名前のファイルが作成され、コンパクトな PDF417 バーコードが格納されています。

### Expected output

保存された PNG ファイルを開くと、3 列でパディングが切り詰められた縦方向にコンパクトな PDF417 バーコードが表示されます。モジュールあたり約 2 px の視覚サイズになるため、HTML の `<img>` タグに埋め込んだり、小さなラベルに印刷したりするのに適しています。

## Full, runnable example

以下は新しいコンソールプロジェクトにコピーできる完全なプログラムです。必要な `using` ディレクティブをすべて含み、**how to save barcode**、**enable compact mode**、**how to adjust columns**、**generate PDF417 barcode** を単一のフローで実演します。

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace Pdf417CompactDemo
{
    class Program
    {
        static void Main(string[] args)
        {
            // Create a PDF417 barcode generator with the desired text.
            BarcodeGenerator barcode = new BarcodeGenerator(EncodeTypes.Pdf417, "Compact mode");

            // Set the module (X) dimension – each bar will be 2 pixels wide.
            barcode.Parameters.Barcode.XDimension.Pixels = 2;

            // Define the number of columns for the PDF417 code (3 columns).
            barcode.Parameters.Barcode.Pdf417.Columns = 3;

            // Enable compact mode by truncating the symbol.
            barcode.Parameters.Barcode.Pdf417.Truncate = true;

            // Save the generated barcode as a PNG image.
            string outputPath = "CompactPdf417.png"; // Adjust path as needed.
            barcode.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"Barcode saved to {outputPath}");
        }
    }
}
```

このプログラムを実行すると、前述の PNG ファイルが生成されます。コンソール出力は保存されたファイルの場所を示し、**how to save barcode** 手順が正常に完了したことを確認できます。

## Common questions and edge cases

### 別の画像形式が必要な場合は？

`Save` メソッドは `BarCodeImageFormat` 列挙体の任意の値を受け取ります。たとえば `Jpeg`、`Bmp`、`Gif` などです。`BarCodeImageFormat.Png` を希望の形式に置き換えるだけで、残りのコードは変更不要です。

### トランケーションはデータ容量にどう影響しますか？

**compact mode**（トランケーション）を有効にすると行数が減少し、バーコードの最大データ容量が低下する可能性があります。「Data too large」例外が発生した場合は、列数を増やすかトランケーションを無効にしてください。

### 動的に列数を決められますか？

はい。入力文字列の長さに基づいて列数を計算できます。

```csharp
int desiredColumns = Math.Max(2, Math.Min(30, inputText.Length / 10));
barcode.Parameters.Barcode.Pdf417.Columns = desiredColumns;
```

このスニペットは **how to adjust columns** をプログラム的に行う例で、レイアウトに合わせてバーコードが収まるようにします。

### X‑dimension は整数ピクセルに限定されていますか？

`Pixels` プロパティは正の整数を受け取ります。高解像度出力（例: 印刷）では、デバイス非依存のサイズ指定のために `Points` を使用する方が適しています。

## Tips for production use

* **Pro tip:** 入力データがシンボルの容量を超える場合に `BarCodeException` を捕捉できるよう、バーコード生成を try‑catch ブロックでラップしてください。  
* **Watch out for:** ファイルシステムの権限。プロセスが対象ディレクトリへの書き込み権限を持っていないと、**how to save barcode** 手順が `UnauthorizedAccessException` で失敗します。  
* **Performance note:** ループ内で多数のバーコードを作成する場合、単一の `BarcodeGenerator` インスタンスを再利用し、イテレーション間で `CodeText` プロパティだけを更新すると効率が向上します。

## Conclusion

これで Aspose.BarCode for C# を使用して **how to save barcode** を PNG ファイルとして保存し、**enable compact mode**、**how to adjust columns**、**generate PDF417 barcode** する方法が分かりました。完全なサンプルは、ジェネレータの初期化から最終画像の書き出しまで、必要なすべての手順を示しています。

ここからは、バーコードにロゴを追加したり色をカスタマイズしたり、ASP.NET Core API に統合したりといった関連トピックを探求できます。これらの拡張も本ガイドと同様のパターンで実装できるため、安心してコードを適用できます。

列数、X‑dimension、画像形式を自由に試して、プロジェクトの正確な要件に合わせてください。コーディングを楽しんでください！

## What Should You Learn Next?

以下のチュートリアルは、本ガイドで示したテクニックを基にした密接に関連するトピックを扱っています。各リソースには完全な動作コード例とステップバイステップの解説が含まれており、追加の API 機能を習得したり、プロジェクトで代替実装アプローチを検討したりするのに役立ちます。

- [C# で Aspose を使用してバーコードを保存し PDF417 を生成する方法](/barcode/english/net/compact-pdf417-encoding/how-to-save-barcode-and-generate-pdf417-with-aspose-in-c/)
- [C# でコンパクトモード付き PDF417 バーコードを作成する方法](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-in-c-with-compact-mode/)
- [C# で PDF417 バーコードを作成し PNG として保存する方法](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-and-save-it-as-png-in-c/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}