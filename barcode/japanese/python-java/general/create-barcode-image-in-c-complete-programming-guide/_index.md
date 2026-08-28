---
category: general
date: 2026-08-09
description: C#でバーコード画像を作成するステップバイステップガイドです。バーコードの生成方法、バーコードの高さ（ピクセル）の調整、そして複数のバーコードを効率的に作成する方法を学びましょう。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode image
- how to generate barcode
- barcode generator c#
- create multiple barcodes
- barcode height pixels
language: ja
lastmod: 2026-08-09
og_description: C#でバーコード画像を素早く作成しましょう。このチュートリアルに従って、バーコードの生成方法、バーコードの高さ（ピクセル）の設定、そして複数のバーコードの作成方法を学びます。
og_image_alt: Screenshot of barcode images generated with C# code showing different
  heights
og_title: C#でバーコード画像を作成する – 開発者向け完全ガイド
schemas:
- author: Aspose
  dateModified: '2026-08-09'
  description: Create barcode image in C# with this step-by-step guide. Learn how
    to generate barcode, adjust barcode height pixels, and create multiple barcodes
    efficiently.
  headline: Create barcode image in C# – complete programming guide
  type: TechArticle
- description: Create barcode image in C# with this step-by-step guide. Learn how
    to generate barcode, adjust barcode height pixels, and create multiple barcodes
    efficiently.
  name: Create barcode image in C# – complete programming guide
  steps:
  - name: Define the output folder
    text: Choose a folder where the generated PNG files will be stored. Using an absolute
      path avoids permission surprises.
  - name: Instantiate the barcode generator
    text: For a DataBar Omnidirectional barcode, pass `EncodeTypes.DatabarOmniDirectional`
      and the GS1‑128 data string.
  - name: Set common barcode parameters
    text: The most common visual tweaks are the X‑dimension (module width) and the
      bar height. Both are expressed in pixels.
  - name: Save the first barcode image
    text: '```csharp // Step 4: Save the barcode image with a 30 px height string
      file30 = Path.Combine(outputFolder, "DatabarBarHeight30Pixels.png"); barcode.Save(file30,
      BarCodeImageFormat.Png); ```'
  - name: Adjust the barcode height pixels
    text: Changing the height does not require a new `BarcodeGenerator` instance—just
      modify the parameter.
  - name: Save the second barcode image
    text: '```csharp // Step 6: Save the barcode image with the new 60 px height string
      file60 = Path.Combine(outputFolder, "DatabarBarHeight60Pixels.png"); barcode.Save(file60,
      BarCodeImageFormat.Png); ```'
  - name: Expected output
    text: 'After running the full sample, the `Barcodes` folder contains:'
  type: HowTo
tags:
- barcode
- C#
- image generation
title: C#でバーコード画像を作成する – 完全プログラミングガイド
url: /ja/python-java/general/create-barcode-image-in-c-complete-programming-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# C# でバーコード画像を作成 – 完全プログラミングガイド

.NET アプリケーションで **バーコード画像を作成** する必要がある場合、このガイドでは Aspose.BarCode ライブラリを使用して **バーコードを生成する方法** を正確に示します。**バーコードの高さ（ピクセル）** の制御方法、画像の保存方法、コードを重複させずに **複数のバーコード** を作成する方法が分かります。

このチュートリアルでは、パッケージのインストールからサイズのカスタマイズまで、すべてを網羅しているので、すぐにプロジェクトに貼り付けて実行できるサンプルをコピー＆ペーストできます。

## 前提条件

* .NET 6.0 SDK 以降がインストールされていること  
* Visual Studio 2022（または任意の C# IDE）  
* NuGet パッケージ `Aspose.BarCode` – 以下でインストール  

```bash
dotnet add package Aspose.BarCode
```

追加の依存関係は必要ありません。

## BarcodeGenerator C# を使用してバーコード画像を生成する方法

バーコード画像を作成するためのコアクラスは `BarcodeGenerator` です。エンコードタイプ、データ文字列、すべてのレンダリングパラメータをカプセル化します。

### 手順 1: 出力フォルダーを定義する

生成された PNG ファイルを保存するフォルダーを選択します。絶対パスを使用することで、権限に関する予期せぬ問題を回避できます。

```csharp
// Step 1: Define the output folder
string outputFolder = Path.Combine(Environment.CurrentDirectory, "Barcodes");
Directory.CreateDirectory(outputFolder);
```

> **なぜ？** フォルダーをプログラムで作成することで、後続の `Save` 呼び出しが新しいマシンでも確実に成功することが保証されます。

### 手順 2: バーコードジェネレーターをインスタンス化する

DataBar Omnidirectional バーコードの場合、`EncodeTypes.DatabarOmniDirectional` と GS1‑128 データ文字列を渡します。

```csharp
// Step 2: Create a DataBar Omnidirectional barcode generator with the data to encode
var barcode = new BarcodeGenerator(
    EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");
```

> **注:** `BarcodeGenerator` オブジェクトは再利用可能です。保存間でパラメータを変更することで、同じデータから **複数のバーコード** を **作成** できます。

### 手順 3: 共通のバーコードパラメータを設定する

最も一般的なビジュアル調整は X‑dimension（モジュール幅）とバーの高さです。どちらもピクセル単位で指定します。

```csharp
// Step 3: Set common barcode parameters (X‑dimension and initial height)
barcode.Parameters.Barcode.XDimension.Pixels = 2;   // thin modules for sharper output
barcode.Parameters.Barcode.BarHeight.Pixels = 30;  // initial height – 30 px
```

> **なぜ X‑dimension を設定するのか？** X‑dimension を小さくすると解像度が上がり、画像を印刷したり高 DPI スクリーンに表示したりする際に重要です。

### 手順 4: 最初のバーコード画像を保存する

```csharp
// Step 4: Save the barcode image with a 30 px height
string file30 = Path.Combine(outputFolder, "DatabarBarHeight30Pixels.png");
barcode.Save(file30, BarCodeImageFormat.Png);
```

ファイル `DatabarBarHeight30Pixels.png` には、30 ピクセルの高さの DataBar Omnidirectional バーコードが含まれています。

### 手順 5: バーコードの高さ（ピクセル）を調整する

高さを変更する際に新しい `BarcodeGenerator` インスタンスは不要です。パラメータを変更するだけです。

```csharp
// Step 5: Change the bar height to 60 px for the same barcode
barcode.Parameters.Barcode.BarHeight.Pixels = 60;
```

### 手順 6: 2 番目のバーコード画像を保存する

```csharp
// Step 6: Save the barcode image with the new 60 px height
string file60 = Path.Combine(outputFolder, "DatabarBarHeight60Pixels.png");
barcode.Save(file60, BarCodeImageFormat.Png);
```

これで、異なる **バーコード高さ（ピクセル）** を持つ 2 つの PNG ファイルができました。**バーコード画像** のバリエーションを作成するのがいかに簡単かが示されています。

## バーコード高さ（ピクセル）を動的に設定する

UI 要素や印刷ラベルに合わせた高さのバーコードが多数必要になることがよくあります。以下のヘルパーメソッドは高さの変更を抽象化します。

```csharp
/// <summary>
/// Saves a barcode image with a custom height.
/// </summary>
/// <param name="generator">Configured BarcodeGenerator instance.</param>
/// <param name="heightPx">Desired bar height in pixels.</param>
/// <param name="fileName">Target file name (including path).</param>
void SaveBarcodeWithHeight(BarcodeGenerator generator, int heightPx, string fileName)
{
    generator.Parameters.Barcode.BarHeight.Pixels = heightPx;
    generator.Save(fileName, BarCodeImageFormat.Png);
}
```

これで、`SaveBarcodeWithHeight(barcode, 45, "BarHeight45.png");` を呼び出すだけで、45 ピクセルの高さの **バーコード画像** をワンラインで **作成** できます。

## ループで複数のバーコードを作成する

製品識別子のコレクションがある場合、`foreach` ループで繰り返しコードを削減できます。この例は、GTIN の配列から **複数のバーコード** を **作成** する方法を示しています。

```csharp
string[] gtins = { "01234567890123", "09876543210987", "12345098765432" };
int[] heights = { 30, 45, 60 }; // different heights for visual variety

for (int i = 0; i < gtins.Length; i++)
{
    // Encode each GTIN as a DataBar Omnidirectional barcode
    var gen = new BarcodeGenerator(EncodeTypes.DatabarOmniDirectional,
                                   $"(01){gtins[i]}");

    // Reuse the X‑dimension setting for consistency
    gen.Parameters.Barcode.XDimension.Pixels = 2;

    // Choose a height from the heights array (or calculate dynamically)
    int height = heights[i % heights.Length];
    string filePath = Path.Combine(outputFolder,
        $"Databar_{gtins[i]}_Height{height}px.png");

    SaveBarcodeWithHeight(gen, height, filePath);
}
```

このループは 3 つの PNG ファイルを生成し、それぞれ異なる **バーコード高さ（ピクセル）** の値を持ちます。`SaveBarcodeWithHeight` ヘルパーが高さ変更をカプセル化しているため、メインループはデータに集中したシンプルな構造のままです。

### 期待される出力

サンプル全体を実行すると、`Barcodes` フォルダーには以下が含まれます：

```
DatabarBarHeight30Pixels.png
DatabarBarHeight60Pixels.png
Databar_01234567890123_Height30px.png
Databar_09876543210987_Height45px.png
Databar_12345098765432_Height60px.png
```

任意の PNG を開くと、標準的なモバイルアプリでスキャン可能な鮮明な DataBar Omnidirectional バーコードが表示されます。

## よくある落とし穴とプロのコツ

| Issue | Why it happens | How to avoid it |
|-------|----------------|-----------------|
| **EncodeTypes の誤り** | DataBar に 1D タイプを使用すると、読めない画像が生成されます。 | `EncodeTypes.DatabarOmniDirectional`（または他の DataBar バリアント）を GS1‑128 ペイロードに必ず使用してください。 |
| **X‑dimension が不足** | 非常に低い X‑dimension は、低解像度モニターで細いバーが消えてしまう可能性があります。 | `XDimension.Pixels` を画面表示では ≥ 2、印刷では 3‑4 に保ちます。 |
| **ファイルパスエラー** | 相対パスは予期しないディレクトリに解決されることがあります。 | `Path.Combine` と `Environment.CurrentDirectory` を使用して絶対パスを構築します。 |
| **画像の上書き** | ループ内で同じファイル名を再利用すると、以前の結果が上書きされます。 | ファイル名にユニークな識別子（例: GTIN やタイムスタンプ）を含めます。 |
| **NuGet パッケージが欠如** | コードはコンパイルされますが、実行時に `FileNotFoundException` がスローされます。 | `Aspose.BarCode` がインストールされ、プロジェクトが参照していることを確認してください。 |

## 完全な動作例

以下はコンソールアプリケーションにコピーできる完全なプログラムです。すべての手順、ヘルパーメソッド、エラーハンドリングが含まれています。

```csharp
using System;
using System.IO;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Prepare output folder
        string outputFolder = Path.Combine(Environment.CurrentDirectory, "Barcodes");
        Directory.CreateDirectory(outputFolder);

        // ---------- Single barcode with two heights ----------
        var barcode = new BarcodeGenerator(
            EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");

        barcode.Parameters.Barcode.XDimension.Pixels = 2;
        barcode.Parameters.Barcode.BarHeight.Pixels = 30;
        barcode.Save(Path.Combine(outputFolder, "DatabarBarHeight30Pixels.png"),
                     BarCodeImageFormat.Png);

        barcode.Parameters.Barcode.BarHeight.Pixels = 60;
        barcode.Save(Path.Combine(outputFolder, "DatabarBarHeight60Pixels.png"),
                     BarCodeImageFormat.Png);

        // ---------- Helper for dynamic heights ----------
        void SaveBarcodeWithHeight(BarcodeGenerator gen, int heightPx, string fileName)
        {
            gen.Parameters.Barcode.BarHeight.Pixels = heightPx;
            gen.Save(fileName, BarCodeImageFormat.Png);
        }

        // ---------- Multiple barcodes ----------
        string[] gtins = { "01234567890123", "09876543210987", "12345098765432" };
        int[] heights = { 30, 45, 60 };

        for (int i = 0; i < gtins.Length; i++)
        {
            var gen = new BarcodeGenerator(EncodeTypes.DatabarOmniDirectional,
                                           $"(01){gtins[i]}");
            gen.Parameters.Barcode.XDimension.Pixels = 2;

            int height = heights[i % heights.Length];
            string filePath = Path.Combine(outputFolder,
                $"Databar_{gtins[i]}_Height{height}px.png");

            SaveBarcodeWithHeight(gen, height, filePath);
        }

        Console.WriteLine($"Barcode images created in: {outputFolder}");
    }
}
```

このプログラムを実行すると

## 次に学ぶべきことは？

以下のチュートリアルは、本ガイドで示した手法を基にした密接に関連するトピックを扱っています。各リソースには、ステップバイステップの解説と完全な動作コード例が含まれており、追加の API 機能を習得し、独自プロジェクトで代替実装アプローチを検討するのに役立ちます。

- [バーコードのカスタム高さ作成 – 1 次元バーコード](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-barcode-height-adjustment/)
- [C# でバーコード画像作成 – GS1 DataMatrix の例](/barcode/english/net/gs1-barcode-encoding/gs1-datamatrix-example/)
- [DotCode バーコード画像作成 – 行と列（Aspose.BarCode）](/barcode/english/net/dotcode-barcode-configuration/dotcode-rows-columns-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}