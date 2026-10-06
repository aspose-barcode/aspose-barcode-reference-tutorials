---
category: general
date: 2026-09-16
description: BarcodeGenerator を使用して C# でバーコードの列を設定する方法と、DataBar Expanded Stacked バーコードの行を設定する方法を学びましょう。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- set barcode columns
- set barcode rows
- DataBar Expanded Stacked
- BarcodeGenerator C#
- barcode image format
- configure barcode dimensions
language: ja
lastmod: 2026-09-16
og_description: C#でバーコードの列を素早く設定。このガイドでは、BarcodeGeneratorを使って列、行、画像形式の設定方法を示します。
og_image_alt: DataBar Expanded Stacked barcode showing custom columns and rows
og_title: C#でバーコードの列と行を設定する – 完全なBarcodeGeneratorガイド
schemas:
- author: Aspose
  dateModified: '2026-09-16'
  description: Learn how to set barcode columns in C# using BarcodeGenerator and also
    set barcode rows for DataBar Expanded Stacked barcodes.
  headline: How to set barcode columns and rows with C# BarcodeGenerator
  type: TechArticle
tags:
- barcode
- C#
- Aspose.BarCode
title: C# BarcodeGeneratorでバーコードの列と行を設定する方法
url: /ja/python-java/general/how-to-set-barcode-columns-and-rows-with-c-barcodegenerator/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# C# BarcodeGenerator でバーコードの列と行を設定する方法

C# アプリケーションでバーコードの列を設定する必要がある場合、本チュートリアルでは必要な手順を正確に示します。DataBar Expanded Stacked バーコードの列と行の両方を設定し、結果を PNG 画像として保存する方法が分かります。

プログラムでバーコードを生成すれば、手作業でのデザイン作業を省け、レポートや請求書、製品ラベル全体で一貫性を確保できます。以下の例では、ライブラリのインストールから、カスタム列数の画像とカスタム行数の画像の 2 枚を作成するまでのフルワークフローをカバーしています。

## 前提条件

開始する前に、以下を確認してください：

* .NET 6.0 以降がインストールされていること。
* **Aspose.BarCode for .NET** NuGet パッケージへの参照。以下でインストールします：

```bash
dotnet add package Aspose.BarCode
```

* 生成された PNG ファイルを保存するフォルダーへの書き込み権限。

これらの要件により、コードは追加設定なしでコンパイルおよび実行できます。

## C# でバーコードの列を設定する方法

最初の重要なステップは、**DataBar Expanded Stacked** シンボロジー用の `BarcodeGenerator` インスタンスを作成し、目的の列数を割り当てることです。

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // 1️⃣ Initialize a DataBar Expanded Stacked barcode generator with the target text.
        var barcodeGenerator = new BarcodeGenerator(
            EncodeTypes.DatabarExpandedStacked,
            "Databar Expanded Stacked long");

        // 2️⃣ Configure the number of columns. The DataBar object exposes a Columns property.
        barcodeGenerator.Parameters.Barcode.DataBar.Columns = 4;

        // 3️⃣ Save the image using the PNG format.
        barcodeGenerator.Save(@"C:\Barcodes\DatabarCols4.png", BarCodeImageFormat.Png);
    }
}
```

**Why this works:**  
`EncodeTypes.DatabarExpandedStacked` はライブラリにどのシンボロジーを描画するかを指示します。`Parameters.Barcode.DataBar.Columns` を設定すると内部モジュールレイアウトが変更され、バーコードの視覚的幅に直接影響します。`Save` メソッドは指定された `BarCodeImageFormat` で画像をディスクに書き込みます。

### 期待される結果
任意の画像ビューアで `C:\Barcodes\DatabarCols4.png` を開いてください。デフォルトよりも幅が広く、4 列を使用した DataBar Expanded Stacked バーコードが表示されます。

## C# でバーコードの行を設定する方法

列ベースの画像を保存した後、行数を調整して高さを変えるバーコードが必要になることがあります。手順は列設定と同様ですが、`Rows` プロパティを使用します。

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // 4️⃣ Re‑initialize the generator for a fresh configuration.
        var barcodeGenerator = new BarcodeGenerator(
            EncodeTypes.DatabarExpandedStacked,
            "Databar Expanded Stacked long");

        // 5️⃣ Set the number of rows. This property controls the vertical module count.
        barcodeGenerator.Parameters.Barcode.DataBar.Rows = 3;

        // 6️⃣ Save the barcode image with the row configuration.
        barcodeGenerator.Save(@"C:\Barcodes\DatabarRows3.png", BarCodeImageFormat.Png);
    }
}
```

**Why this works:**  
ジェネレータを再初期化することで、以前の列設定が行設定に干渉しないようにします。`Parameters.Barcode.DataBar.Rows` を変更するとバーコードの高さが変わり、行数がデフォルトを超えると画像がより高くなります。

### 期待される結果
`C:\Barcode\DatabarRows3.png` を開くと、3 行構成を反映した高さのあるバーコードが表示されます。

## 完全なエンドツーエンド例

以下は、1 回の実行で両方の画像を作成する単一プログラムです。コードを 1 ファイルにまとめることで、アプリケーションを再起動せずに列設定と行設定を切り替える方法が示せます。

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Common text for both barcodes.
        const string barcodeText = "Databar Expanded Stacked long";

        // ---------- Column configuration ----------
        var colGenerator = new BarcodeGenerator(EncodeTypes.DatabarExpandedStacked, barcodeText);
        colGenerator.Parameters.Barcode.DataBar.Columns = 4;
        colGenerator.Save(@"C:\Barcodes\DatabarCols4.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved barcode with 4 columns to DatabarCols4.png");

        // ---------- Row configuration ----------
        var rowGenerator = new BarcodeGenerator(EncodeTypes.DatabarExpandedStacked, barcodeText);
        rowGenerator.Parameters.Barcode.DataBar.Rows = 3;
        rowGenerator.Save(@"C:\Barcodes\DatabarRows3.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved barcode with 3 rows to DatabarRows3.png");
    }
}
```

プログラムを実行すると、次の 2 つの PNG ファイルが生成されます：

* **DatabarCols4.png** – 4 列のバーコード。  
* **DatabarRows3.png** – 3 行のバーコード。

どちらのファイルも PNG 形式の **barcode image format** を使用しており、エッジが鮮明でロスレス圧縮をサポートするため、印刷やデジタル表示に最適です。

## よくある質問とヒント

| 質問 | 回答 |
|----------|--------|
| *PNG の代わりに JPEG を使用できますか？* | はい。`BarCodeImageFormat.Png` を `BarCodeImageFormat.Jpeg` に置き換えます。JPEG はサイズが小さくなりますが、圧縮アーティファクトが発生し、スキャナーの信頼性に影響する可能性があります。 |
| *列または行の最大数はどれくらいですか？* | ライブラリは DataBar 仕様に対して値を検証します。許容範囲外の値は `ArgumentException` をスローします。正確な上限は Aspose.BarCode のドキュメントをご確認ください。 |
| *`BarcodeGenerator` を破棄する必要がありますか？* | このクラスは `IDisposable` を実装しています。ループ内で多数のインスタンスを作成する場合は、`using` ブロックでラップしてアンマネージドリソースを速やかに解放してください。 |
| *列や行を変更せずにバーコードのサイズを変更するには？* | `barcodeGenerator.Parameters.Image.Width` と `Height` を使用して、モジュール配置はそのままに出力画像のサイズをスケールします。 |

**Pro tip:** 高解像度印刷用にバーコードを生成する際は、列や行の数を増やすのではなく、出力画像の寸法（`Width`/`Height`）を大きくしてください。この方法はシンボロジーで定義された標準モジュールサイズを維持しつつ、よりシャープな画像を得られます。

## 結論

これで **BarcodeGenerator** クラスを使用して C# でバーコードの列と行を設定する方法が分かりました。ガイドではジェネレータの初期化、列・行数の設定、PNG 形式での保存、画像形式の変更やリソース破棄といった一般的なバリエーションの取り扱いを説明しました。

次は **バーコードの色のカスタマイズ**、**人が読めるテキストの追加**、**PDF 文書へのバーコード埋め込み** などの関連トピックを探求してください。これらの拡張機能は本稿で示した設定パターンをベースにしており、任意の .NET アプリケーションでフル機能のバーコードソリューションを構築できます。

## 次に学ぶべきことは？

以下のチュートリアルは、本ガイドで示した手法を基にした、密接に関連するトピックをカバーしています。各リソースには、ステップバイステップの説明と完全な動作コード例が含まれており、追加の API 機能を習得したり、プロジェクトで代替実装アプローチを検討したりするのに役立ちます。

- [C# の Barcode Generator 例 – 列・行の設定と画像のエクスポート](/barcode/english/python-java/general/barcode-generator-example-in-c-set-columns-rows-export-image/)
- [databar expanded stacked バーコードガイド – C# での生成とサイズ設定](/barcode/english/python-java/general/databar-expanded-stacked-barcode-guide-how-to-generate-and-s/)
- [C# の Barcode Generator 例 – 幅と高さの設定](/barcode/english/python-java/general/barcode-generator-example-in-c-set-width-and-height/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}