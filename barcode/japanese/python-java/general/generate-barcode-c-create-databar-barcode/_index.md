---
category: general
date: 2026-07-21
description: Aspose.BarCode を使用して C# でバーコードを素早く生成しましょう。DataBar バーコードの作成方法、バーコードサイズのカスタマイズ、そして数ステップでバーコード画像をエクスポートする方法を学べます。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate barcode c#
- create databar barcode
- customize barcode size
- change barcode dimensions
- export barcode image
language: ja
lastmod: 2026-07-21
og_description: Aspose.BarCode を使用して C# でバーコードを生成します。DataBar バーコードを作成し、サイズをカスタマイズして、画像をすぐにエクスポートします。
og_image_alt: Screenshot of a DataBar Expanded Stacked barcode saved as PNG
og_title: C#でバーコード生成 – カスタムサイズのDataBarバーコードを作成
schemas:
- author: Aspose
  dateModified: '2026-07-21'
  description: Generate barcode C# quickly with Aspose.BarCode. Learn to create DataBar
    barcode, customize barcode size, and export barcode image in just a few steps.
  headline: Generate barcode C# – Create DataBar barcode
  type: TechArticle
- questions:
  - answer: Replace `BarCodeImageFormat.Png` with `Jpeg`, `Bmp`, `Gif`, or `Svg`.
      The API handles the conversion automatically.
    question: What if I need a different image format?
  - answer: Technically you can set both, but Aspose will prioritize the last property
      you modify. It's safer to set *one* dimension and let the library compute the
      other for a valid DataBar.
    question: Can I change both rows and columns simultaneously?
  - answer: 'Use `barcodeGen.Parameters.Barcode.ForegroundColor` and `BackgroundColor`.
      Example:'
    question: How do I apply a foreground/background color?
  - answer: DataBar Expanded Stacked supports up to 74 numeric characters (or 30 alphanumeric).
      Exceeding that throws an exception.
    question: Is there a size limit for the encoded data?
  type: FAQPage
tags:
- barcode
- csharp
- databar
- image-export
- aspnet
title: C#でバーコード生成 – DataBarバーコードの作成
url: /ja/python-java/general/generate-barcode-c-create-databar-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# バーコード生成 C# – DataBar バーコードの作成

膨大なドキュメントを読むことなく **generate barcode C#** を実行したいですか？ここが正しい場所です。このガイドでは、**DataBar barcode** の作成、サイズの調整、そして最終的に **exporting the barcode image** を行う手順を、数行の C# で説明します。

小さな棚タグに収まるコンパクトな商品ラベルが必要だと想像してください。DataBar Expanded Stacked シンボルがそれを実現し、Aspose.BarCode を使えば列や行の数を正確に制御できます。準備はいいですか？さっそく始めましょう。

## 達成できること

- **Create a DataBar barcode**（“expanded stacked” バリアント）をゼロから作成する。  
- **Customize barcode size** を列または行を直接設定してカスタマイズする。  
- **Change barcode dimensions** を再生成せずにリアルタイムで変更する。  
- **Export barcode image** を PNG（または Aspose がサポートする任意の形式）にエクスポートする。  

## 前提条件

- .NET 6.0 以降（コードは .NET Framework 4.7+ でも動作します）。  
- 有効な Aspose.BarCode for .NET ライセンス（またはトライアルモードで実行可能）。  
- お好みの IDE—Visual Studio、Rider、または VS Code が使用できます。  

まだ NuGet パッケージをインストールしていない場合は、次を実行してください：

```bash
dotnet add package Aspose.BarCode
```

それだけです—他の依存関係はありません。

## ステップ 1: バーコードジェネレータの設定（**generate barcode C#** の方法）

まず、**DataBar Expanded Stacked** シンボルを指す `BarcodeGenerator` インスタンスが必要です。このオブジェクトが後で画像を生成するエンジンです。

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

// Initialize the generator with the desired symbology and data
BarcodeGenerator barcodeGen = new BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked,   // Symbology
    "Databar Expanded Stacked long");    // Human‑readable text (optional)
```

*Why this matters*: `EncodeTypes.DatabarExpandedStacked` 列挙体は、狭いスペースに最適なスタック版を Aspose に指示します。渡すテキストはエンコードされた値となり、アプリケーションが必要とする任意の数値文字列に置き換え可能です。

## ステップ 2: **Customize barcode size** – 列を設定する

DataBar バーコードは、**columns** または **rows** のいずれかの数を指定することで視覚的密度を調整できます。まずは列から始めましょう。行数はバーコードが有効になるよう自動計算されます。

```csharp
// Set the number of columns; rows are computed automatically
barcodeGen.Parameters.Barcode.DataBar.Columns = 4;
```

*Pro tip*: 列はバーコードの幅に影響します。列が多いほど幅が広くなり、低解像度プリンターでのスキャン信頼性が向上することがあります。

## ステップ 3: **Export barcode image** を列設定で実行する

画像をディスクに書き込みます。PNG、JPEG、BMP、または SVG も選択可能です。ここでは、鮮明でロスレスな出力の PNG を使用します。

```csharp
// Save the barcode image using the current column configuration
barcodeGen.Save(@"C:\Barcodes\DatabarCols4.png", BarCodeImageFormat.Png);
```

> **Expected result** – `DatabarCols4.png` を開くと、4 列の整然としたスタックされた DataBar が表示されます。縦棒が密に積み重なったように見え、小さなラベルに最適です。

## ステップ 4: **Change barcode dimensions** – 代わりに行を設定する

場合によっては、幅よりも高さが必要になることがあります。行制御に切り替えると、Aspose が自動的に列数を再計算します。

```csharp
// Switch to row control – columns will be derived automatically
barcodeGen.Parameters.Barcode.DataBar.Rows = 3;
```

*Why switch?* 行はバーコードの高さに影響します。行が多いほどシンボルが高くなり、縦方向のスペースはあるが幅が限られている場合に便利です。

## ステップ 5: 行設定で **Export barcode image** を実行する

2 番目のバリエーションを保存します。ファイル名が変更を反映していることに注意してください。比較のために両方の画像を保持しても構いません。

```csharp
// Save the barcode image using the new row configuration
barcodeGen.Save(@"C:\Barcodes\DatabarRows3.png", BarCodeImageFormat.Png);
```

> **Result** – `DatabarRows3.png` は同じデータの高さが増したバージョンを表示し、依然として完全にスキャン可能です。

## 完全な動作例

すべてをまとめると、以下はすぐにコピー＆ペーストして実行できる自己完結型コンソールアプリです：

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        // 1️⃣ Initialize generator for DataBar Expanded Stacked
        BarcodeGenerator barcodeGen = new BarcodeGenerator(
            EncodeTypes.DatabarExpandedStacked,
            "Databar Expanded Stacked long");

        // 2️⃣ Customize size – set columns (width)
        barcodeGen.Parameters.Barcode.DataBar.Columns = 4;

        // 3️⃣ Export image with column setting
        string colPath = @"C:\Barcodes\DatabarCols4.png";
        barcodeGen.Save(colPath, BarCodeImageFormat.Png);
        Console.WriteLine($"Saved column‑based barcode to {colPath}");

        // 4️⃣ Change dimensions – set rows (height)
        barcodeGen.Parameters.Barcode.DataBar.Rows = 3;

        // 5️⃣ Export image with row setting
        string rowPath = @"C:\Barcodes\DatabarRows3.png";
        barcodeGen.Save(rowPath, BarCodeImageFormat.Png);
        Console.WriteLine($"Saved row‑based barcode to {rowPath}");
    }
}
```

プログラムを実行し、2 つの PNG ファイルを開いてください。これで **generated barcode C#**、**customized barcode size**、**changed barcode dimensions**、そして **exported the barcode image** をすべて 1 分未満で完了しました。

## よくある質問とエッジケース

- **What if I need a different image format?**  
  `BarCodeImageFormat.Png` を `Jpeg`、`Bmp`、`Gif`、または `Svg` に置き換えます。API が自動的に変換を処理します。

- **Can I change both rows and columns simultaneously?**  
  技術的には両方設定可能ですが、Aspose は最後に設定したプロパティを優先します。有効な DataBar を得るためには、*一方* の次元だけを設定し、もう一方はライブラリに計算させる方が安全です。

- **How do I apply a foreground/background color?**  
  `barcodeGen.Parameters.Barcode.ForegroundColor` と `BackgroundColor` を使用します。例：  
  ```csharp
  barcodeGen.Parameters.Barcode.ForegroundColor = Color.DarkBlue;
  barcodeGen.Parameters.Barcode.BackgroundColor = Color.White;
  ```

- **Is there a size limit for the encoded data?**  
  DataBar Expanded Stacked は最大 74 桁の数字（または 30 文字の英数字）をサポートします。これを超えると例外がスローされます。

## 次のステップ

これで **create databar barcode** の基本を習得したので、次のことを検討してください：

- **text annotations** をバーコード下に追加する (`barcodeGen.Parameters.CaptionAbove.Text`)。  
- Aspose.PDF を使用して PNG を PDF に直接埋め込む。  
- 製品 ID の CSV をループして大量にバーコードを生成する。  

これらのトピックはすべて同じ `BarcodeGenerator` オブジェクトを基にしているため、ゼロから始める必要はありません。

---

**Bottom line**: これで **generate barcode C#**、**customize barcode size**、**change barcode dimensions**、そして **export barcode image** を Aspose.BarCode で行う方法が分かりました。列/行の値を試したり、画像形式を変更したりして、在庫管理や POS システムにコードを統合してください。ハッピーコーディング！

## 次に学ぶべきことは？

以下のチュートリアルは、本ガイドで示した手法を基にした密接に関連するトピックをカバーしています。各リソースには、ステップバイステップの解説と完全な動作コード例が含まれ、追加の API 機能を習得し、プロジェクトで代替実装アプローチを探求するのに役立ちます。

- [バーコード画像の生成 – GS1 クーポン UPC-A Databar](/barcode/english/net/gs1-barcode-encoding/gs1-coupon-upc-a-databar-configuration/)
- [Aspose.BarCode for .NET を使用したカスタムアスペクト比の Aztec バーコード生成方法](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)
- [DataMatrix バーコード生成 – Aspose.BarCode のプロガイド](/barcode/english/net/datamatrix-barcode-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}