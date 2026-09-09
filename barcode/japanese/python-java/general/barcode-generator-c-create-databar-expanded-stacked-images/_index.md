---
category: general
date: 2026-07-24
description: バーコードジェネレーター C# チュートリアルでは、バーコード画像の生成、列と行の設定、そして数行のコードで Databar バーコードを作成する方法を示します。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- barcode generator c#
- generate barcode image
- how to set columns
- how to set rows
- create databar barcode
language: ja
lastmod: 2026-07-24
og_description: Barcode Generator C# チュートリアルでは、バーコード画像の生成、列と行の設定、そして明確なコード例を用いたDatabarバーコードの作成方法を順を追って解説します。
og_image_alt: Screenshot of a DataBar Expanded Stacked barcode generated with C#
og_title: バーコードジェネレーター C# – DataBar スタックバーコードを高速に作成
schemas:
- author: Aspose
  dateModified: '2026-07-24'
  description: Barcode Generator C# tutorial that shows how to generate barcode image,
    set columns, set rows, and create Databar barcode in just a few lines of code.
  headline: Barcode Generator C# – Create DataBar Expanded Stacked Images
  type: TechArticle
tags:
- barcode
- C#
- Aspose.BarCode
title: バーコードジェネレーター C# – DataBar Expanded Stacked 画像の作成
url: /ja/python-java/general/barcode-generator-c-create-databar-expanded-stacked-images/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Barcode Generator C# – DataBar Expanded Stacked 完全ガイド

数秒で鮮明でスキャン可能な画像を出力する **barcode generator c#** の使い方、気になったことはありませんか？空のプロジェクトを見つめ、列や行の配置が分からず、頭を悩ませながら *generate barcode image* ファイルを作成する方法が分からない…そんな方は正しい場所に来ました。このチュートリアルでは、 tiny console app をセットアップし、DataBar Expanded Stacked バーコードを生成し、レイアウトを調整し、結果を PNG として保存します—すべて **barcode generator c#** ライブラリを使用します。

必要なことすべてをカバーします：パッケージのインストール、列と行の設定（はい、*how to set columns* と *how to set rows* の答えもあります）、そして最終的に請求書やチケット、機械可読ラベルが必要なあらゆるものに埋め込める **create databar barcode** オブジェクトの作成方法。外部ドキュメントは不要です；コピー＆ペーストして実行すれば、フォルダーに PNG ファイルが 2 つ生成されます。

## 必要なもの

- .NET 6.0 SDK またはそれ以降（コードは .NET Core、.NET Framework、.NET 5+ でも動作します）
- 新しいコンソールプロジェクト (`dotnet new console`) – UI が好きな場合は Visual Studio でも構いません。
- Aspose.BarCode for .NET NuGet パッケージ（**barcode generator c#** の基盤となるライブラリ）。以下でインストールします：

```bash
dotnet add package Aspose.BarCode
```

以上です。パッケージが復元されれば、すぐに始められます。

## Barcode Generator C# – プロジェクトのセットアップ

まず、必要な名前空間をインポートし、メインルーチンをすっきりさせるヘルパーメソッドを作成しましょう。

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        // Folder where PNG files will be saved
        string outputFolder = Environment.CurrentDirectory;

        // Build the first barcode with custom columns
        GenerateDatabarWithColumns(outputFolder, columns: 4);

        // Build the second barcode with custom rows
        GenerateDatabarWithRows(outputFolder, rows: 3);
    }

    // -----------------------------------------------------------------
    // Helper: creates a DataBar Expanded Stacked barcode and sets columns
    // -----------------------------------------------------------------
    static void GenerateDatabarWithColumns(string folder, int columns)
    {
        // Step 1: Create a DataBar Expanded Stacked barcode generator with the desired text
        var barcodeGenerator = new BarcodeGenerator(
            EncodeTypes.DatabarExpandedStacked, "Databar Expanded Stacked long");

        // Step 2: Configure the barcode to use the supplied number of columns
        // This answers the “how to set columns” question.
        barcodeGenerator.Parameters.Barcode.DataBar.Columns = columns;

        // Step 3: Save the barcode image as PNG – this is the “generate barcode image” part.
        string filePath = System.IO.Path.Combine(folder, $"DatabarCols{columns}.png");
        barcodeGenerator.Save(filePath, BarCodeImageFormat.Png);

        Console.WriteLine($"✅ Created barcode with {columns} columns: {filePath}");
    }

    // -----------------------------------------------------------------
    // Helper: creates a DataBar Expanded Stacked barcode and sets rows
    // -----------------------------------------------------------------
    static void GenerateDatabarWithRows(string folder, int rows)
    {
        // Step 4: Create another generator for the same barcode type and text
        var barcodeGenerator = new BarcodeGenerator(
            EncodeTypes.DatabarExpandedStacked, "Databar Expanded Stacked long");

        // Step 5: Configure the barcode to use the supplied number of rows
        // This answers the “how to set rows” query.
        barcodeGenerator.Parameters.Barcode.DataBar.Rows = rows;

        // Step 6: Save the second barcode image as PNG
        string filePath = System.IO.Path.Combine(folder, $"DatabarRows{rows}.png");
        barcodeGenerator.Save(filePath, BarCodeImageFormat.Png);

        Console.WriteLine($"✅ Created barcode with {rows} rows: {filePath}");
    }
}
```

### この構造が有効な理由

- **Separation of concerns** – 各ヘルパーは単一の設定（列または行）に集中します。これによりコードが読みやすく、再利用しやすくなります。
- **Explicit parameters** – `columns` または `rows` を引数として渡すので、メソッド本体を編集せずに任意の値で呼び出せます。
- **Immediate feedback** – `Console.WriteLine` がファイルの保存先を正確に表示するため、ターミナルからプログラムを実行したときに便利です。

## DataBar Expanded Stacked の列（Columns）設定方法

`DataBar.Columns` プロパティは、バーコードが持つ垂直スライス（列）の数を決定する設定です。デフォルトは `4` ですが、エンコードするデータ量やスキャナの要件に応じて `2` や `6` が必要になる場合があります。以下は列設定ロジックだけを抜き出した簡単なコードスニペットです：

```csharp
var generator = new BarcodeGenerator(EncodeTypes.DatabarExpandedStacked, "Sample Text");
generator.Parameters.Barcode.DataBar.Columns = 5;   // ← change this number as needed
generator.Save("databar_columns5.png", BarCodeImageFormat.Png);
```

**Pro tip:** 列数を増やすと、バーコード全体の幅が比例して広がります。画像を PDF やウェブページに埋め込む場合は、コンテナが余分な幅を収容できるか確認してください。さもなければスキャナが誤読する可能性があります。

## DataBar Expanded Stacked の行（Rows）設定方法

行も同様に機能しますが、バーコードの高さに影響します。デフォルトの行数は `3` です。ラベルの垂直スペースが限られている場合は `2` に減らすことができます。逆に、行数を増やすと低解像度プリンターでも可読性が向上します。

```csharp
var generator = new BarcodeGenerator(EncodeTypes.DatabarExpandedStacked, "Sample Text");
generator.Parameters.Barcode.DataBar.Rows = 2;   // ← adjust rows here
generator.Save("databar_rows2.png", BarCodeImageFormat.Png);
```

**Watch out:** エンコードされたデータに必要な最小行数未満に設定すると、実行時に例外が発生します。ライブラリは明確なメッセージとともに `ArgumentException` をスローするので、設定が無効な場合はすぐに分かります。

## バーコード画像の生成 – PNG で保存

上記のヘルパーはどちらも `Save` 呼び出しで終わります。`BarCodeImageFormat.Png` 列挙体は Aspose.BarCode にロスレスの PNG ファイルを出力させます。これはエッジが鮮明に保たれるため、ほとんどのスキャンシナリオに最適です。別の形式（ウェブ用の JPEG、レガシーシステム用の BMP）を使用したい場合は、列挙体の値を入れ替えるだけで、他のコードは変更不要です。

```csharp
generator.Save("mybarcode.jpeg", BarCodeImageFormat.Jpeg);
```

生成された PNG は以下のようになります（画像は想像してください；下の alt テキストが説明しています）：

> **生成された画像の代替テキスト:** *4 列（左）と 3 行（右）の DataBar Expanded Stacked バーコードで、透明背景に高コントラストの黒で描画されています。*

## DataBar バーコードの作成 – 完全動作例

すべてをまとめると、`Program.cs` に直接貼り付けられるコンパクトなバージョンがこちらです。列と行の設定の両方を示し、保存後にファイルが存在するかの簡易チェックも行います。

```csharp
using System;
using System.IO;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Demo
{
    static void Main()
    {
        string outDir = Directory.GetCurrentDirectory();

        // ---------- Create barcode with custom columns ----------
        var colGen = new BarcodeGenerator(EncodeTypes.DatabarExpandedStacked,
                                          "Databar Expanded Stacked long");
        colGen.Parameters.Barcode.DataBar.Columns = 4;   // how to set columns
        string colPath = Path.Combine(outDir, "DatabarCols4.png");
        colGen.Save(colPath, BarCodeImageFormat.Png);
        Console.WriteLine($"Saved column barcode → {colPath}");

        // ---------- Create barcode with custom rows ----------
        var rowGen = new BarcodeGenerator(EncodeTypes.DatabarExpandedStacked,
                                          "Databar Expanded Stacked long");
        rowGen.Parameters.Barcode.DataBar.Rows = 3;      // how to set rows
        string rowPath = Path.Combine(outDir, "DatabarRows3.png");
        rowGen.Save(rowPath, BarCodeImageFormat.Png);
        Console.WriteLine($"Saved row barcode → {rowPath}");

        // ---------- Verify files exist ----------
        Console.WriteLine(File.Exists(colPath)
            ? "✅ Column image generated successfully."
            : "❌ Column image missing.");
        Console.WriteLine(File.Exists(rowPath)
            ? "✅ Row image generated successfully."
            : "❌ Row image missing.");
    }
}
```

### 期待される出力

プログラムを実行すると（`dotnet run`）、以下のようなコンソール出力が表示されます：

```
Saved column barcode → C:\MyProject\DatabarCols4.png
Saved row barcode → C:\MyProject\DatabarRows3.png
✅ Column image generated successfully.
✅ Row image generated successfully.
```

任意の画像ビューアで 2 つの PNG を開くと、左側のファイルは 4 つの垂直モジュール（列）を持ち、右側のファイルは 3 モジュールの高さ（行）であることが分かります。どちらも標準的な DataBar リーダーで問題なくスキャンできます。

## よくある落とし穴と回避方法

| Symptom | Likely Cause | Fix |
|---------|--------------|-----|
| `ArgumentException: Columns value is out of range` | 列が 0 または 8 超（ライブラリは 8 で上限）に設定されている。 | **1** から **8** の間の値にしてください。 |
| Barcode appears blurry in PDF | PNG がデフォルト DPI（96）で保存され、その後拡大縮小された。 | `generator.Parameters.ImageResolution = 300;` を保存前に設定してください。 |
| Scanner fails on rows‑only configuration | 行は変更したが、列がデフォルトのままでデータ長に合っていない。 | 行と列の両方を同時に調整するか、手動設定を省略してライブラリに自動サイズさせてください。 |

## 次のステップ

これで **generate barcode image**、**set columns**、**set rows**、そして **barcode generator c#** を使った **create databar barcode** の方法が分かったので、以下が可能です：

- `Aspose.PDF` または `iTextSharp` を使用して PNG を PDF に埋め込む。
- より小さなフットプリントが必要な場合は `EncodeTypes.DatabarLimited` に切り替える。
- 色を試す（`generator.Parameters.Barcode.ForeColor = Color.Blue`）。
- 同じプロジェクトに QR コードや他のシンボルを追加—Aspose.BarCode は 150 種類以上をサポートしています。

問題が発生したら、下にコメントを残すか、公式の Aspose.BarCode ドキュメントを確認してください（API リファレンスは網羅的で、数十の実装サンプルが含まれています）。コーディングを楽しんで、スキャナが決して読み逃さないことを願っています！

## 次に学ぶべきことは？

以下のチュートリアルは、本ガイドで示した手法を基にした密接に関連するトピックを扱っています。各リソースには、ステップバイステップの解説と完全な動作コード例が含まれ、追加の API 機能を習得し、独自プロジェクトで代替実装アプローチを探求するのに役立ちます。

- [Create DotCode barcode image – rows & columns (Aspose.BarCode)](/barcode/english/net/dotcode-barcode-configuration/dotcode-rows-columns-configuration/)
- [Create barcode image c# – Configure Codablock F Rows & Columns](/barcode/english/net/codablock-f-encoding/codablock-f-row-column-configuration/)
- [Generate barcode image – GS1 Coupon UPC-A Databar](/barcode/english/net/gs1-barcode-encoding/gs1-coupon-upc-a-databar-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}