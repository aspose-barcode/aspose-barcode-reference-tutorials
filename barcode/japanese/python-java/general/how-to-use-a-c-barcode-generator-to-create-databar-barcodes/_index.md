---
category: general
date: 2026-10-02
description: C# のバーコードジェネレーターで列と行を設定し、DataBar バーコードを作成する方法を学びましょう。完全なコード付きのステップバイステップガイド。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- c# barcode generator
- how to set columns
- how to set rows
- create databar barcode
language: ja
lastmod: 2026-10-02
og_description: C# バーコードジェネレーターガイド – 列と行の設定方法を学び、DataBar バーコードを作成するための完全なコード例をご紹介します。
og_image_alt: Screenshot of a DataBar Expanded Stacked barcode generated with a C#
  barcode generator
og_title: C# バーコードジェネレーター：DataBar バーコードの列と行を設定
schemas:
- author: Aspose
  dateModified: '2026-10-02'
  description: Learn how to set columns and rows in a C# barcode generator to create
    DataBar barcodes. Step‑by‑step guide with complete code.
  headline: How to use a C# barcode generator to create DataBar barcodes with custom
    columns and rows
  type: TechArticle
tags:
- barcode
- c#
- databar
title: C# バーコードジェネレーターを使用して、カスタム列と行で DataBar バーコードを作成する方法
url: /ja/python-java/general/how-to-use-a-c-barcode-generator-to-create-databar-barcodes/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# C# バーコードジェネレーターを使用して、カスタム列と行で DataBar バーコードを作成する方法

正確な列と行の構成で DataBar バーコードを生成できる **c# barcode generator** が必要な場合、このチュートリアルでその方法を詳しく解説します。列と行の調整がなぜ重要かを理解し、4 列と 3 行の DataBar Expanded Stacked バーコードの両方を作成する、完全に実行可能なサンプルを入手できます。

以下のセクションで取り上げます：

* Aspose.BarCode for .NET ライブラリを使用するための前提条件。
* DataBar バーコードで列（`how to set columns`）と行（`how to set rows`）を設定する方法。
* コピーしてコンパイル、実行できる完全な C# コンソールプログラム。
* 期待される出力ファイルとトラブルシューティングのヒント。

このガイドの最後までに、レイアウト要件に合わせた **create databar barcode** 画像を作成できるようになります。

## 前提条件

開始する前に、以下を用意してください：

| 必要条件 | 理由 |
|-------------|--------|
| .NET 6.0 SDK 以降 | C# コードの実行環境を提供します。 |
| Visual Studio 2022（または .NET をサポートする任意の IDE） | プロジェクト作成やデバッグが容易になります。 |
| Aspose.BarCode for .NET NuGet パッケージ | サンプルで使用する `BarcodeGenerator` クラスを提供します。 |
| 出力 PNG ファイル用フォルダーへの書き込み権限 | ジェネレーターがバーコード画像をディスクに書き込みます。 |

以下のコマンドで Aspose.BarCode パッケージをインストールします：

```bash
dotnet add package Aspose.BarCode
```

## Step 1: 基本的な DataBar Expanded Stacked バーコードを作成する

最初のステップは、`EncodeTypes.DatabarExpandedStacked` フォーマットで **c# barcode generator** のインスタンスを作成することです。このフォーマットは、最大 74 桁の数字をエンコードできる二次元 DataBar バーコードです。

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

// ...

// Create a generator for a DataBar Expanded Stacked barcode
var generator = new BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked,
    "Databar Expanded Stacked long");
```

コンストラクターは 2 つの引数を受け取ります：

* `EncodeTypes.DatabarExpandedStacked` – 使用するシンボロジーをライブラリに指示します。
* `"Databar Expanded Stacked long"` – エンコードされるテキストです。

## Step 2: 列の設定方法

列は DataBar バーコードの横方向の密度に影響します。列数を増やすとバーコードが横に広がり、低解像度プリンターでのスキャン信頼性が向上することがあります。

```csharp
// Set the number of columns to 4
generator.Parameters.Barcode.DataBar.Columns = 4;
```

**なぜ 4 列なのか？**  
4 列は多くの小売アプリケーションでサイズと可読性のバランスが取れた設定です。1 から 8 の範囲で値を試すことができ、ライブラリが自動的にモジュール幅を調整します。

## Step 3: 列設定済みバーコードを保存する

```csharp
// Save the image that uses the column setting
generator.Save(@"C:\Barcodes\DatabarCols4.png", BarCodeImageFormat.Png);
```

画像は PNG ファイルとして保存され、バーコードスキャナーに必要な鮮明なエッジが保持されます。

## Step 4: 行設定用に別のジェネレーターを作成する

行設定も同様の手順ですが、縦方向の密度に影響します。列設定と行設定が混在しないように、新しいジェネレーターインスタンスを作成します。

```csharp
var generatorRows = new BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked,
    "Databar Expanded Stacked long");
```

## Step 5: 行の設定方法

```csharp
// Set the number of rows to 3
generatorRows.Parameters.Barcode.DataBar.Rows = 3;
```

**行を増やすのはいつか？**  
行を増やすとバーコードが縦に長くなり、横方向の印刷スペースが限られていて縦に余裕がある場合（例：縦長の製品ラベル）に有用です。

## Step 6: 行設定済みバーコードを保存する

```csharp
// Save the image that uses the row setting
generatorRows.Save(@"C:\Barcodes\DatabarRows3.png", BarCodeImageFormat.Png);
```

両方の PNG ファイル（`DatabarCols4.png` と `DatabarRows3.png`）は `C:\Barcodes` フォルダーに作成されます。

## 完全な実行可能サンプル

以下は、上記のすべての手順を組み込んだ自己完結型コンソールアプリケーションです。コードを新しい .NET コンソールプロジェクトに貼り付けて実行してください。

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace DatabarDemo
{
    class Program
    {
        static void Main()
        {
            // Output directory – change to a folder that exists on your machine
            const string outputDir = @"C:\Barcodes";

            // -------------------------------------------------
            // 1️⃣ Create a barcode generator for column testing
            // -------------------------------------------------
            var colGenerator = new BarcodeGenerator(
                EncodeTypes.DatabarExpandedStacked,
                "Databar Expanded Stacked long");

            // Set the number of columns (how to set columns)
            colGenerator.Parameters.Barcode.DataBar.Columns = 4;

            // Save the column‑based barcode
            string colPath = System.IO.Path.Combine(outputDir, "DatabarCols4.png");
            colGenerator.Save(colPath, BarCodeImageFormat.Png);
            Console.WriteLine($"Column barcode saved to: {colPath}");

            // -------------------------------------------------
            // 2️⃣ Create a barcode generator for row testing
            // -------------------------------------------------
            var rowGenerator = new BarcodeGenerator(
                EncodeTypes.DatabarExpandedStacked,
                "Databar Expanded Stacked long");

            // Set the number of rows (how to set rows)
            rowGenerator.Parameters.Barcode.DataBar.Rows = 3;

            // Save the row‑based barcode
            string rowPath = System.IO.Path.Combine(outputDir, "DatabarRows3.png");
            rowGenerator.Save(rowPath, BarCodeImageFormat.Png);
            Console.WriteLine($"Row barcode saved to: {rowPath}");

            // -------------------------------------------------
            // 3️⃣ Confirmation message
            // -------------------------------------------------
            Console.WriteLine("Both DataBar barcodes have been generated successfully.");
        }
    }
}
```

### コードの概要

| セクション | 目的 |
|---------|---------|
| **Namespace imports** | `Aspose.BarCode` と `Aspose.BarCode.Generation` をインポートします。 |
| **Output directory** | フォルダー パスを一元管理し、フォルダーを移動した場合でも 1 行だけ変更すれば済むようにします。 |
| **Column generator** | `c# barcode generator` で **列の設定方法** を示します。 |
| **Row generator** | `c# barcode generator` で **行の設定方法** を示します。 |
| **Save calls** | PNG ファイルをディスクに書き込み、スキャンやレポートへの組み込みがすぐにできるようにします。 |
| **Console output** | 開発中に便利な即時フィードバックを提供します。 |

## 期待される出力

プログラムを実行すると、2 つの PNG ファイルが生成されます：

* **DatabarCols4.png** – 4 列を反映した横に広いバーコード。
* **DatabarRows3.png** – 3 行を反映した縦に長いバーコード。

両画像にはテキスト *“Databar Expanded Stacked long”* が DataBar Expanded Stacked シンボロジーでエンコードされています。任意の画像ビューアで開くか、バーコードスキャナーにかざして可読性を確認できます。

## よくある落とし穴と回避策

| 問題 | 理由 | 対策 |
|-------|--------|-----|
| **File‑access exception** | 出力フォルダーが存在しない、または書き込み権限がない。 | フォルダーを手動で作成するか、管理者権限でプログラムを実行してください。 |
| **Incorrect column/row values** | ライブラリは列に 1‑8、行に 1‑4 のみ受け付けます。 | 代入前に値を検証してください。例：`if (value < 1 || value > 8) throw new ArgumentOutOfRangeException();` |
| **Barcode not scanning** | 生成された画像がスキャナーの解像度に対して小さすぎる。 | `generator.Parameters.Image.Height` や `...Width` を使用して `ImageHeight` または `ImageWidth` を増やしてください。 |
| **Text truncation** | エンコード文字列が選択した DataBar バリアントの最大長を超えている。 | 短い文字列にするか、容量が必要な場合は `EncodeTypes.DatabarExpanded` に切り替えてください。 |

## プロのコツ

* **ジェネレーターをキャッシュ** – 同じ列/行設定で多数のバーコードを作成する場合、同一の `BarcodeGenerator` インスタンスを再利用し、`CodeText` プロパティだけを変更します。  
* **バッチ処理** – 製品識別子のコレクションをループし、ループ内で `generator.CodeText` を設定し、各イテレーションでユニークなファイル名で `Save` を呼び出します。  
* **パフォーマンス** – 高ボリュームシナリオでは、アンチエイリアシングを無効化（`generator.Parameters.Image.AntiAlias = false`）して画像生成を高速化し、スキャン品質に影響を与えません。  

## 次のステップ

**列の設定方法** と **行の設定方法** を `c# barcode generator` で習得したので、以下も試してみてください：

* バーコード下部に **人が読めるテキスト** を追加する（`generator.Parameters.Barcode.CodeTextLocation`）。  
* **色の変更**（`generator.Parameters.Image.ForegroundColor` と `BackgroundColor`）。  
* `DatabarLimited` や `DatabarExpanded` など、他の DataBar バリアントを生成する。  
* Aspose.PDF を使用して PDF レポートにバーコードを埋め込む。  

これらのトピックは本ガイドで学んだ基礎の上に構築され、よりリッチで本番環境向けのバーコードソリューション作成に役立ちます。

---

*Happy coding! If you run into any issues, feel free to leave a comment or check the Aspose.BarCode documentation for deeper API details.*

## 次に学ぶべきことは？

以下のチュートリアルは、本ガイドで示した手法を基にした密接に関連するトピックをカバーしています。各リソースには、完全な動作コード例とステップバイステップの解説が含まれており、追加の API 機能をマスターしたり、独自プロジェクトで代替実装アプローチを探求したりするのに役立ちます。

- [How to set barcode columns and rows with C# BarcodeGenerator](/barcode/english/python-java/general/how-to-set-barcode-columns-and-rows-with-c-barcodegenerator/)
- [Barcode Generator Example in C# – Set Columns, Rows & Export Image](/barcode/english/python-java/general/barcode-generator-example-in-c-set-columns-rows-export-image/)
- [How to use a barcode generator C# to create DataBar barcodes](/barcode/english/python-java/general/how-to-use-a-barcode-generator-c-to-create-databar-barcodes/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}