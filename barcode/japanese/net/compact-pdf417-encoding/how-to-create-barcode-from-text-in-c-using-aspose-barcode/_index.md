---
category: general
date: 2026-10-28
description: C# と Aspose.BarCode を使用してテキストからバーコードを作成します。PDF417 バーコード画像の生成方法、列数の設定、X
  次元の調整、コンパクトモードの有効化を学びましょう。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode from text
- generate barcode c#
- generate pdf417 barcode
- pdf417 barcode image
language: ja
lastmod: 2026-10-28
og_description: Aspose.BarCode を使用して C# でテキストからバーコードを作成します。このチュートリアルでは、PDF417 バーコード画像の生成方法、サイズ、列、コンパクトモードのカスタマイズ方法を示します。
og_image_alt: Screenshot showing a compact PDF417 barcode created from text using
  C#
og_title: C#でテキストからバーコードを作成する – ステップバイステップガイド
schemas:
- author: Aspose
  dateModified: '2026-10-28'
  description: Create barcode from text in C# with Aspose.BarCode. Learn to generate
    PDF417 barcode image, set columns, adjust X‑dimension, and enable compact mode.
  headline: How to create barcode from text in C# using Aspose.BarCode
  type: TechArticle
tags:
- barcode
- C#
- PDF417
- image generation
title: Aspose.BarCode を使用して C# でテキストからバーコードを作成する方法
url: /ja/net/compact-pdf417-encoding/how-to-create-barcode-from-text-in-c-using-aspose-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# C# と Aspose.BarCode を使用してテキストからバーコードを作成する方法

.NET アプリケーションで **テキストからバーコードを作成** する必要がある場合、このガイドはすぐに実行できるソリューションを提供します。**PDF417 バーコード** 画像の生成方法、モジュール幅、列数の制御、そして IDE を離れずにコンパクトモードを有効にする方法が分かります。

このチュートリアルでは、ライブラリのインストールから最終的な PNG ファイルの保存まで、**C# でバーコードを生成** するために必要なすべてをカバーしています。最後まで読むと、レポート、チケット、在庫ラベルなどに高密度の PDF417 バーコードを埋め込むことができます。

## 前提条件

開始する前に、以下が揃っていることを確認してください。

* .NET 6.0 SDK 以降がインストールされていること  
* Visual Studio 2022（または .NET をサポートする任意のエディタ）  
* Aspose.BarCode for .NET の NuGet パッケージをダウンロードするためのインターネット接続  

これらがあれば、Windows、Linux、macOS のいずれでもサンプルをコンパイルして実行できます。

## 手順 1: Aspose.BarCode NuGet パッケージをインストールする

バーコード生成を支えるライブラリは **Aspose.BarCode for .NET** です。.NET CLI でインストールします。

```bash
dotnet add package Aspose.BarCode
```

このパッケージは `Aspose.BarCode` 名前空間を追加し、チュートリアル全体で使用される `BarcodeGenerator` クラスが含まれます。

## 手順 2: コンソールプロジェクトを作成しコードを追加する

新しいコンソールプロジェクトを作成し、生成された `Program.cs` を以下のコードに置き換えます。このプログラムは **テキストからバーコードを作成** し、**PDF417 バーコード画像** として保存する方法を示します。

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace Pdf417Demo
{
    class Program
    {
        static void Main()
        {
            // Step 2.1: Define the text to encode.
            // Unicode characters such as Å, ó, and © are supported out of the box.
            string data = "Åspóse.Barcóde©";

            // Step 2.2: Initialize the PDF417 generator with the desired text.
            // EncodeTypes.Pdf417 tells the generator which symbology to use.
            BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, data);

            // Step 2.3: Set the X‑dimension (module width) to 2 pixels for a denser barcode.
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // Step 2.4: Define the number of columns in the PDF417 symbol.
            // Fewer columns produce a taller barcode; three columns keep it compact.
            generator.Parameters.Barcode.Pdf417.Columns = 3;

            // Step 2.5: Enable compact mode by truncating the right‑hand column.
            // Truncate reduces the overall width while preserving data integrity.
            generator.Parameters.Barcode.Pdf417.Truncate = true;

            // Step 2.6: Choose the output folder and file name.
            string outputPath = "CompactPdf417.png";

            // Step 2.7: Save the barcode as a PNG image.
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"PDF417 barcode image saved to {outputPath}");
        }
    }
}
```

### 各行の重要性

* **`EncodeTypes.Pdf417`** は PDF417 シンボルを選択します。これは大量のデータを二次元形式でエンコードするのに最適です。  
* **`XDimension.Pixels = 2`** はモジュール幅を縮小し、バーコードをより密にし、限られたスペースに適します。  
* **`Pdf417.Columns = 3`** は垂直データ列の数を制御します。列数が少ないほど、バーコードは高くなりますが幅が狭くなります。  
* **`Pdf417.Truncate = true`** はコンパクトモードを有効にし、右側の未使用列を削除します。これが通常の PDF417 を **コンパクト PDF417 バーコード画像** に変える重要な設定です。  

## 手順 3: プロジェクトをビルドして実行する

プロジェクトディレクトリで以下のコマンドを実行します。

```bash
dotnet build
dotnet run
```

プログラムが終了すると、ファイルの場所を示すコンソールメッセージが表示されます。任意の画像ビューアで `CompactPdf417.png` を開き、結果を確認してください。

**期待される出力** – 高コントラストの PNG で、文字列 `Åspóse.Barcóde©` をエンコードしたコンパクト PDF417 バーコードが表示されます。標準的なバーコードリーダーで画像をスキャンすると元のテキストが返され、**generate pdf417 barcode** が成功したことが確認できます。

## 手順 4: 異なるシナリオ向けにバーコードをカスタマイズする

例では固定の列数と X‑dimension を使用していますが、他の要件に合わせてジェネレータを調整できます。

| シナリオ | 調整 |
|----------|------------|
| データ量が大きい | `Pdf417.Columns` を増やすか、`Pdf417.Rows` を手動で設定する |
| スキャン信頼性を高める | `XDimension.Pixels` を 3 または 4 に上げる |
| 画像フォーマットを変更する | `BarCodeImageFormat.Png` を `Jpeg` または `Bmp` に置き換える |
| 透過背景 | `generator.Parameters.Barcode.BackgroundColor = System.Drawing.Color.Transparent` を設定する |

これらのオプションにより、モバイルアプリ、デスクトップレポート、Web サービスに適した **C# でバーコードを生成** ソリューションを作成できます。

## 手順 5: エッジケースの処理とベストプラクティス

* **Unicode 対応** – ジェネレータは Unicode 文字を自動的にエンコードしますが、ファイルから読み込む場合はソース文字列が UTF‑8 エンコードされていることを確認してください。  
* **大量テキスト** – PDF417 は最大 1,850 文字の英数字をエンコードできます。この上限を超えると、ライブラリは例外をスローします。データを複数のバーコードに分割するか、容量の大きいシンボルに切り替えてください。  
* **エラーハンドリング** – 生成コードを `try/catch` ブロックで囲み、`BarCodeException` を捕捉して分かりやすいエラーメッセージを提供します。  
* **パフォーマンス** – ループで多数のバーコードを生成する場合、単一の `BarcodeGenerator` インスタンスを再利用し、イテレーション間で `CodeText` のみを更新すると効果的です。  

```csharp
try
{
    generator.CodeText = nextText;
    generator.Save($"barcode_{i}.png", BarCodeImageFormat.Png);
}
catch (BarCodeException ex)
{
    Console.Error.WriteLine($"Failed to generate barcode: {ex.Message}");
}
```

## 完全なソースリスト

以下は `Program.cs` にコピーできる、完全で自己完結型のプログラムです。追加のファイルは不要です。

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace Pdf417Demo
{
    class Program
    {
        static void Main()
        {
            string data = "Åspóse.Barcóde©";

            BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, data);
            generator.Parameters.Barcode.XDimension.Pixels = 2;
            generator.Parameters.Barcode.Pdf417.Columns = 3;
            generator.Parameters.Barcode.Pdf417.Truncate = true;

            string outputPath = "CompactPdf417.png";
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"PDF417 barcode image saved to {outputPath}");
        }
    }
}
```

このプログラムを実行すると、下図に示す **pdf417 バーコード画像** が作成されます。

![C# を使用してテキストから作成されたコンパクト PDF417 バーコード](/images/compact-pdf417.png){.img-fluid alt="テキストから作成されたコンパクト PDF417 バーコード画像の例"}

*画像の説明: この PNG ファイルは、文字列 “Åspóse.Barcóde©” をエンコードしたコンパクト PDF417 バーコードを表示しています。*  

## 結論

これで C# で **テキストからバーコードを作成** し、カスタム寸法とコンパクトモードを備えた **PDF417 バーコード画像** を生成する方法が分かりました。この例は、**C# でバーコードを生成** するための基本手順、Unicode データの取り扱い、そしてさまざまな展開シナリオに合わせたビジュアルパラメータの調整を示しています。

次に、**C# で QR コードを生成**、**PDF ドキュメントにバーコードを追加**、または **ASP.NET Core API にバーコードを埋め込む** といった関連トピックを探求してください。これらはすべて、本稿で取り上げた `BarcodeGenerator` の基本に基づいています。

コーディングを楽しんで、.NET ソリューションにバーコードを統合してください！

## 次に学ぶべきことは？

以下のチュートリアルは、本ガイドで示した手法に基づく密接に関連したトピックをカバーしています。各リソースには、ステップバイステップの解説と完全な動作コード例が含まれており、追加の API 機能を習得し、独自プロジェクトで代替実装アプローチを検討するのに役立ちます。

- [C# で PDF417 バーコードを生成 – PDF417 バーコード C# を作成](/barcode/english/net/compact-pdf417-encoding/generate-pdf417-barcode-in-c-create-pdf417-barcode-c/)
- [C# で Aspose.BarCode を使用して PDF417 バーコードを生成する方法](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-with-aspose-barcode-in-c/)
- [C# で PDF417 バーコード画像を作成する方法 – 完全ガイド](/barcode/english/net/compact-pdf417-encoding/generate-pdf417-barcode-in-c-complete-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}