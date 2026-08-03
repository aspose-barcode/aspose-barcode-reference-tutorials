---
category: general
date: 2026-08-03
description: Barcode generator C# チュートリアルでは、Aspose.BarCode を使用してバーコード画像を生成し、列と行を設定し、DataBar
  Expanded Stacked 用の PNG ファイルを保存する方法を示します。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- barcode generator c#
- generate barcode image
language: ja
lastmod: 2026-08-03
og_description: Barcode generator C# チュートリアルでは、Aspose.BarCode を使用してバーコード画像を生成し、DataBar
  Expanded Stacked の列と行を設定し、PNG ファイルとして保存する方法を解説します。
og_image_alt: Screenshot of a DataBar Expanded Stacked barcode generated with C#
og_title: バーコードジェネレーター C# – バーコード画像を生成するステップバイステップガイド
schemas:
- author: Aspose
  dateModified: '2026-08-03'
  description: Barcode generator C# tutorial shows how to generate barcode image with
    Aspose.BarCode, set columns and rows, and save PNG files for DataBar Expanded
    Stacked.
  headline: Barcode generator C# – generate barcode image
  type: TechArticle
tags:
- barcode
- C#
- Aspose.BarCode
title: バーコードジェネレーター C# – バーコード画像を生成
url: /ja/python-java/general/barcode-generator-c-generate-barcode-image/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Barcode generator C# – バーコード画像の生成

DataBar Expanded Stacked 用のバーコード画像を生成できる barcode generator C# が必要な場合、このガイドでは全工程を解説します。列と行の設定方法、PNG への保存方法、他のシンボロジーへのコード適用方法を学べます。

バーコード画像をプログラムで生成することで手作業を省き、請求書、出荷ラベル、在庫システム間での一貫性を確保できます。このチュートリアルはプロジェクトのセットアップから完全なソースコードまで、必要なすべてを網羅しているので、すぐにサンプルを実行できます。

## 前提条件

* .NET 6.0 以降がインストールされていること  
* Visual Studio 2022 などの IDE（C# をサポートするエディタならどれでも可）  
* **Aspose.BarCode for .NET** のライセンス（無料評価版でテスト可能）  
* C# 構文の基本的な知識  

上記のいずれかが不足している場合は、dotnet.microsoft.com から .NET SDK をインストールし、以下のコマンドで Aspose.BarCode NuGet パッケージを取得してください。

```bash
dotnet add package Aspose.BarCode
```

## ステップ 1: barcode generator C# プロジェクトの作成

新しいコンソール アプリケーションを作成し、必要な `using` ディレクティブを追加します。

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // The implementation starts in the next sections
        }
    }
}
```

`BarcodeGenerator` クラスは barcode generator C# API の中心です。シンボロジーの種類とエンコードするテキストを受け取ります。

## ステップ 2: DataBar Expanded Stacked バーコードを生成し、列数を設定する

最初の例では、4 列のバーコードを作成します。`Columns` プロパティを調整すると、DataBar Expanded Stacked シンボロジーの視覚的密度が変わります。

```csharp
// Step 2: Create a barcode generator for DataBar Expanded Stacked
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked, "Databar Expanded Stacked long");

// Set the number of columns to 4
barcodeGenerator.Parameters.Barcode.DataBar.Columns = 4;

// Save the barcode image as PNG
string colsPath = @"YOUR_DIRECTORY\DatabarCols4.png";
barcodeGenerator.Save(colsPath, BarCodeImageFormat.Png);

Console.WriteLine($"Barcode with 4 columns saved to {colsPath}");
```

**重要なポイント:** 列数は、コンパクトなスペースに格納できるデータ量に影響します。4 に設定すると、より幅広いバーコードになり、ほとんどのスキャナで読み取り可能です。

## ステップ 3: カスタム行数でバーコードを生成する

2 番目の例では、`Rows` プロパティを設定して垂直レイアウトを制御する方法を示します。横幅が限られている場合に、より高さのあるバーコードが必要なときは、3 行構成が有用です。

```csharp
// Step 3: Create a second barcode generator for the same type
BarcodeGenerator barcodeGeneratorRows = new BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked, "Databar Expanded Stacked long");

// Set the number of rows to 3
barcodeGeneratorRows.Parameters.Barcode.DataBar.Rows = 3;

// Save the barcode image as PNG
string rowsPath = @"YOUR_DIRECTORY\DatabarRows3.png";
barcodeGeneratorRows.Save(rowsPath, BarCodeImageFormat.Png);

Console.WriteLine($"Barcode with 3 rows saved to {rowsPath}");
```

**重要なポイント:** 行数を調整することで、狭い列にバーコードを収めつつ可読性を保てます。barcode generator C# は、仕様に合わせてモジュールサイズを自動的に再計算します。

## ステップ 4: 完全な実行可能サンプル

以下は、前述の手順を組み合わせた単体で動作するプログラムです。コードを `Program.cs` に貼り付け、`YOUR_DIRECTORY` を既存のフォルダ パスに置き換えてアプリケーションを実行してください。

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // ---------- Generate barcode with 4 columns ----------
            BarcodeGenerator colsGenerator = new BarcodeGenerator(
                EncodeTypes.DatabarExpandedStacked, "Databar Expanded Stacked long");

            colsGenerator.Parameters.Barcode.DataBar.Columns = 4;

            string colsFile = @"YOUR_DIRECTORY\DatabarCols4.png";
            colsGenerator.Save(colsFile, BarCodeImageFormat.Png);
            Console.WriteLine($"Generated barcode image with columns saved to {colsFile}");

            // ---------- Generate barcode with 3 rows ----------
            BarcodeGenerator rowsGenerator = new BarcodeGenerator(
                EncodeTypes.DatabarExpandedStacked, "Databar Expanded Stacked long");

            rowsGenerator.Parameters.Barcode.DataBar.Rows = 3;

            string rowsFile = @"YOUR_DIRECTORY\DatabarRows3.png";
            rowsGenerator.Save(rowsFile, BarCodeImageFormat.Png);
            Console.WriteLine($"Generated barcode image with rows saved to {rowsFile}");
        }
    }
}
```

### 期待される出力

プログラムを実行すると、対象ディレクトリに 2 つの PNG ファイルが生成されます。

* **DatabarCols4.png** – 4 列の DataBar Expanded Stacked バーコード  
* **DatabarRows3.png** – 同じデータを 3 行でエンコードしたもの  

任意の画像ビューアで画像を開くと、印刷や PDF への埋め込みに適した、鮮明でスキャン可能なバーコードが表示されます。

## カスタムサイズでバーコード画像を生成する方法

特定の画像サイズが必要な場合は、`Save` を呼び出す前に `ImageHeight` と `ImageWidth` プロパティを調整します。

```csharp
colsGenerator.Parameters.ImageHeight = 150; // pixels
colsGenerator.Parameters.ImageWidth = 300;  // pixels
colsGenerator.Save(colsFile, BarCodeImageFormat.Png);
```

サイズを変更してもエンコードされたデータには影響せず、視覚的な表示だけが拡大・縮小されます。この手法は、固定レイアウトの UI コンポーネントにバーコードを組み込む際に便利です。

## よくある落とし穴とプロのコツ

* **パス区切り文字:** Windows でのエスケープ文字問題を回避するため、逐語的文字列 (`@"C:\Path\file.png"`) または `Path.Combine` を使用してください。  
* **ライセンスの適用:** 有効なライセンスがない場合、生成された画像に透かしが入ります。アプリケーション開始時にライセンスを適用してください:

  ```csharp
  Aspose.BarCode.License license = new Aspose.BarCode.License();
  license.SetLicense("Aspose.BarCode.lic");
  ```

* **エンコード制限:** DataBar Expanded Stacked は最大 74 桁の数字をサポートします。この上限を超えると例外がスローされます。ジェネレータを作成する前に入力長を検証してください。  
* **パフォーマンス:** 複数回保存する際に同一の `BarcodeGenerator` インスタンスを再利用するとメモリ割り当てが削減されます。エンコードするテキストが同じ場合のみ、保存間で `Rows` や `Columns` プロパティを変更してください。

## 次のステップ

barcode generator C# でバーコード画像を生成できるようになったので、以下を検討してみてください。

* **異なるシンボロジー** – `EncodeTypes.QR`、`EncodeTypes.Code128`、`EncodeTypes.Pdf417` を試す。  
* **カラーカスタマイズ** – `Parameters.Barcode.ForeColor` と `BackColor` を設定してブランドに合わせる。  
* **PDF への埋め込み** – 生成した PNG を Aspose.PDF と組み合わせて印刷可能な文書を作成する。  

これらの拡張により、在庫管理、物流、リテール向けのフル機能バーコードソリューションを構築できます。

---

## 次に学ぶべきことは？

以下のチュートリアルは、本ガイドで示した手法を応用した関連トピックを扱っています。各リソースには、完全な動作コード例とステップバイステップの解説が含まれており、追加の API 機能を習得し、独自プロジェクトで代替実装アプローチを検討するのに役立ちます。

- [バーコード画像の生成 – GS1 クーポン UPC-A Databar](/barcode/english/net/gs1-barcode-encoding/gs1-coupon-upc-a-databar-configuration/)
- [DotCode バーコード画像の作成 – 行と列 (Aspose.BarCode)](/barcode/english/net/dotcode-barcode-configuration/dotcode-rows-columns-configuration/)
- [Aspose.BarCode for .NET で DataMatrix バーコード (ECC 200) を生成する方法](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-ecc-200-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}