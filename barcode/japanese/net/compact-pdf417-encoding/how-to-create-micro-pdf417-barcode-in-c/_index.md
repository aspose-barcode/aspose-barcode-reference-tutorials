---
category: general
date: 2026-11-14
description: C# と Aspose.BarCode を使用してマイクロ PDF417 バーコードを作成する – ジェネレータ設定、X ディメンション、列、PNG
  エクスポートを網羅したステップバイステップガイド。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create micro pdf417 barcode
- micro pdf417 barcode generator
- set XDimension pixels
- define barcode columns
- save barcode as PNG
- Aspose.BarCode C# example
language: ja
lastmod: 2026-11-14
og_description: Aspose.BarCode を使用して C# でマイクロ PDF417 バーコードを作成します。ジェネレータの設定方法、XDimension
  の設定、列数の選択、PNG へのエクスポート方法を学びましょう。
og_image_alt: Screenshot of a generated micro PDF417 barcode saved as a PNG file
og_title: C#でマイクロPDF417バーコードを作成する – 完全プログラミングガイド
schemas:
- author: Aspose
  dateModified: '2026-11-14'
  description: Create micro PDF417 barcode in C# with Aspose.BarCode – step‑by‑step
    guide covering generator setup, X‑dimension, columns, and PNG export.
  headline: How to create micro PDF417 barcode in C#
  type: TechArticle
- description: Create micro PDF417 barcode in C# with Aspose.BarCode – step‑by‑step
    guide covering generator setup, X‑dimension, columns, and PNG export.
  name: How to create micro PDF417 barcode in C#
  steps:
  - name: Open the PNG in an image viewer.
    text: Open the PNG in an image viewer.
  - name: Use any smartphone barcode‑scanning app that supports PDF417 (most “QR‑code
      scanner” apps include it).
    text: Use any smartphone barcode‑scanning app that supports PDF417 (most “QR‑code
      scanner” apps include it).
  - name: Scan the image; the app should display the original text `"Åspóse.Barcóde©"`.
    text: Scan the image; the app should display the original text `"Åspóse.Barcóde©"`.
  type: HowTo
tags:
- barcode
- PDF417
- C#
- Aspose
- image generation
title: C#でマイクロPDF417バーコードを作成する方法
url: /ja/net/compact-pdf417-encoding/how-to-create-micro-pdf417-barcode-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# C# でマイクロ PDF417 バーコードを作成する方法  

マイクロ PDF417 バーコードを **すぐに作成** したい場合は、このガイドが完全な実行可能ソリューションを示します。バーコードジェネレータのインスタンス化、X‑ディメンションの設定、列数の選択、最終的に PNG 画像として保存する手順を、Aspose.BarCode for .NET ライブラリを使用して解説します。

マイクロ PDF417 バーコードの生成には複雑なビルドパイプラインは不要です。このチュートリアルの最後までに、レポートやラベル、モバイルアプリに埋め込める高品質なバーコード画像を生成する単一の C# ファイルが手に入ります。

## 前提条件  

開始する前に、以下が揃っていることを確認してください。

* .NET 6.0 SDK 以降（コードは .NET Framework 4.7+ でも動作します）。  
* Visual Studio 2022、VS Code、または Rider などの開発環境。  
* Aspose.BarCode for .NET のライセンス（または無料評価キー）。[Aspose のウェブサイト](https://purchase.aspose.com/barcode/net) から取得できます。  

> **プロのコツ:** 評価版を使用している場合、生成された PNG には小さな “Evaluation” ウォーターマークが入ります。ライセンス版では自動的に除去されます。

## 手順 1: プロジェクトのセットアップ  

新しいコンソールプロジェクトを作成し、Aspose.BarCode NuGet パッケージを追加します。

```bash
dotnet new console -n MicroPdf417Demo
cd MicroPdf417Demo
dotnet add package Aspose.BarCode --version 24.9.0
```

`dotnet add package` コマンドは **Aspose.BarCode C# example** の依存関係を取得するため、DLL を手動で管理する必要はありません。

## 手順 2: 完全なコードを書く  

自動生成された `Program.cs` を以下のコードに置き換えます。マイクロ pdf417 バーコードを最初から最後まで作成する方法を示しています。

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace MicroPdf417Demo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Create a MicroPDF417 barcode generator with the desired text.
            // The text can contain Unicode characters; here we use a sample string.
            var generator = new BarcodeGenerator(EncodeTypes.MicroPdf417, "Åspóse.Barcóde©");

            // 2️⃣ Set the X‑dimension (module width) in pixels.
            // This determines the width of the smallest element (a bar or a space).
            generator.Parameters.Barcode.XDimension.Pixels = 2; // secondary keyword: set XDimension pixels

            // 3️⃣ Define the number of columns (allowed values: 1‑4 for MicroPDF417).
            // More columns mean a wider barcode but fewer rows, which can improve readability.
            generator.Parameters.Barcode.Pdf417.Columns = 4; // secondary keyword: define barcode columns

            // 4️⃣ Choose the output format and save the barcode as a PNG image.
            // PNG preserves the sharp edges of the barcode, which is ideal for scanning.
            string outputPath = "MicroPdf417.png";
            generator.Save(outputPath, BarCodeImageFormat.Png); // secondary keyword: save barcode as PNG

            Console.WriteLine($"Micro PDF417 barcode saved to {outputPath}");
        }
    }
}
```

### 各行の重要ポイント  

* **BarcodeGenerator コンストラクタ** – エンコードしたいテキストで **マイクロ pdf417 バーコードジェネレータ** をインスタンス化します。  
* **XDimension.Pixels** – モジュール幅を制御します。`2` ピクセルに設定すると、ほとんどのスキャナに適した密度の高い高解像度バーコードが得られます。  
* **Pdf417.Columns** – MicroPDF417 は 1‑4 列のみサポートします。`4` を選択するとバーコードの高さが減少し、垂直スペースが限られている場合に有用です。  
* **Save メソッド** – バーコードを PNG ファイルに書き出します。PNG はロスレス形式なので、生成したパターンが正確にスキャナに読み取られます。

## 手順 3: ビルドと実行  

プログラムをコンパイルして実行します。

```bash
dotnet run
```

コンソールに次のような出力が表示されます。

```
Micro PDF417 barcode saved to MicroPdf417.png
```

プロジェクトフォルダーに **MicroPdf417.png** という名前のファイルが作成されます。任意の画像ビューアで開くと、文字列 `"Åspóse.Barcóde©"` をエンコードした鮮明なマイクロ PDF417 バーコードが表示されます。

![生成されたマイクロ PDF417 バーコード画像例](MicroPdf417.png "生成されたマイクロ PDF417 バーコード例"){.center-image width=400 alt="生成されたマイクロ PDF417 バーコード画像例"}

*上の画像は手順 2 のコード実行結果です。*

## 手順 4: よくあるバリエーションとエッジケース  

| 状況 | コードの適応方法 |
|-----------|----------------------|
| **データ長が異なる場合** | MicroPDF417 は最大 1 200 文字までエンコードできます。`BarcodeGenerator` の第 2 引数を変更するだけです。 |
| **解像度を上げたい場合** | `XDimension.Pixels` を `3` または `4` に増やします。モジュールが大きくなると低解像度スキャナでの読み取り性が向上しますが、画像サイズも大きくなります。 |
| **カスタムカラー** | ジェネレータ作成後に `generator.Parameters.Barcode.BarcodeColor = Color.Blue;` と `generator.Parameters.Barcode.BackgroundColor = Color.White;` を設定します。 |
| **他の形式で保存** | `BarCodeImageFormat.Png` を `Jpeg`、`Bmp`、`Gif` などに置き換えて、下流の要件に合わせます。 |
| **PDF に埋め込む** | `generator.Save("barcode.pdf", BarCodeImageFormat.Pdf);` とし、Aspose.PDF を使って他の文書と結合します。 |

> **注意点:** `XDimension.Pixels` を `1` 未満に設定すると `ArgumentOutOfRangeException` がスローされます。必ず `1` 以上に保ってください。

## 手順 5: バーコードの検証  

バーコードが正しくスキャンできるか確認する手順:

1. PNG を画像ビューアで開く。  
2. PDF417 をサポートするスマートフォンのバーコードスキャンアプリ（多くの「QR コードスキャナ」アプリに含まれます）を使用する。  
3. 画像をスキャンし、アプリが元のテキスト `"Åspóse.Barcóde©"` を表示することを確認する。

スキャンに失敗した場合は、**X‑ディメンション** と **列数** の設定を再確認してください。モジュール幅が小さすぎる、またはサポート外の列数を指定するとパターンが読めなくなることがあります。

## 結論  

Aspose.BarCode を使用して C# で **マイクロ pdf417 バーコードを作成** する方法が分かりました。このチュートリアルで学んだこと:

* **マイクロ pdf417 バーコードジェネレータ** のインスタンス化。  
* **XDimension ピクセル** を設定してモジュール幅を制御。  
* **バーコード列数** を定義して形状を調整。  
* **PNG で保存** してロスレス画像を出力。  

ここからは、カラーカスタマイズ、PDF への埋め込み、ASP.NET Core Web API でのオンデマンド生成など、追加機能を自由に探求してください。コーディングを楽しんでください！


## 次に学ぶべきことは？


以下のチュートリアルは、本ガイドで示した手法を基にした、密接に関連するトピックを扱っています。各リソースには完全な動作コード例とステップバイステップの解説が含まれており、API の追加機能を習得したり、独自プロジェクトで代替実装アプローチを探求したりするのに役立ちます。

- [Create barcode PNG in C# – full guide to GS1 Micro PDF417](/barcode/english/net/gs1-barcode-encoding/create-barcode-png-in-c-full-guide-to-gs1-micro-pdf417/)
- [How to create macro PDF417 barcode in C# using Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/how-to-create-macro-pdf417-barcode-in-c-using-aspose-barcode/)
- [Create PDF417 barcode in C# using Aspose.BarCode – step‑by‑step guide](/barcode/english/net/compact-pdf417-encoding/create-pdf417-barcode-in-c-using-aspose-barcode-step-by-step/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}