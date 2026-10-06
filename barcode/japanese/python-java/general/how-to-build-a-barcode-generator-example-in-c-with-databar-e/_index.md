---
category: general
date: 2026-09-19
description: C# のバーコードジェネレータ例 – Aspose.BarCode を使用して、列レイアウトと行レイアウトでバーコードを生成する方法を示す。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- barcode generator example
- generate barcode c#
language: ja
lastmod: 2026-09-19
og_description: バーコードジェネレーターのサンプルは、Aspose.BarCode を使用して列と行のレイアウトで C# のバーコードを生成する方法を示しています。
og_image_alt: C# barcode generator example output showing a DataBar Expanded Stacked
  barcode with 4 columns
og_title: バーコードジェネレータ例 – C#でDataBar Expanded Stackedバーコードを作成
schemas:
- author: Aspose
  dateModified: '2026-09-19'
  description: barcode generator example in C# showing how to generate barcode C#
    using Aspose.BarCode for column and row layouts
  headline: How to build a barcode generator example in C# with DataBar Expanded Stacked
  type: TechArticle
tags:
- barcode
- C#
- Aspose.BarCode
title: C#でDataBar Expanded Stackedを使用したバーコードジェネレータのサンプルを作成する方法
url: /ja/python-java/general/how-to-build-a-barcode-generator-example-in-c-with-databar-e/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# バーコードジェネレータ例 – C#でDataBar Expanded Stackedバーコードを作成

.NETプロジェクトで動作する**barcode generator example**が必要な場合、このガイドではAspose.BarCodeライブラリを使用してC#でバーコードを生成する方法を正確に示します。列ベースのレイアウトと行ベースのレイアウトの両方に対してDataBar Expanded Stackedバーコードを設定する方法が分かり、PNG画像を生成する実行可能なコードが得られます。

このチュートリアルは、NuGetパッケージのインストールから最終画像の保存までを網羅しているため、コードを自分のソリューションにコピーするだけで追加の調査は不要です。

## 学べること

* C#プロジェクトにAspose.BarCodeをインストールし、参照する方法。  
* 長いデータ文字列をエンコードする**barcode generator example**の作成方法。  
* 同じバーコードタイプで4列レイアウトと3行レイアウトを設定する方法。  
* 生成した画像をPNGファイルとして保存する方法。  

この記事の最後まで読むと、`ExpandedStackedCols4.png`（4列）と`ExpandedStackedRows3.png`（3行）の2つのPNGファイルがすぐに使用できるようになります。

## 前提条件

* .NET 6.0 SDK 以降（コードは .NET Framework 4.7.2 でも動作します）。  
* Visual Studio 2022、VS Code、またはお好みのC# IDE。  
* **Aspose.BarCode** NuGetパッケージをダウンロードできるインターネット接続。  

追加の外部サービスは必要ありません。

## 手順 1: Aspose.BarCode NuGet パッケージをインストール

プロジェクトフォルダーでターミナルを開き、次のコマンドを実行します。

```bash
dotnet add package Aspose.BarCode
```

このコマンドは Aspose.BarCode の最新安定版をプロジェクトファイルに追加します。パッケージが復元されたら、C# ソースファイルでその名前空間を参照できるようになります。

## 手順 2: 必要な using ディレクティブを追加

新しい C# コンソール アプリケーションを作成するか、既存プロジェクトにコードを追加し、ファイルの先頭に以下の `using` 文を入れます。

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;
```

これらのディレクティブにより、**barcode generator example**で使用する `BarcodeGenerator` クラスと `EncodeTypes` 列挙体にアクセスできます。

## 手順 3: 4列レイアウトのバーコードジェネレータ例を作成

例の最初の部分では、4列配置の DataBar Expanded Stacked バーコードを構築します。以下のコードは元のスニペットと同じ手順を踏みつつ、各行の目的を説明するコメントを追加しています。

```csharp
// Step 3.1: Initialise the generator with the desired barcode type and data
BarcodeGenerator generator = new BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked,   // DataBar Expanded Stacked type
    "Long data string");                  // The data you want to encode

// Step 3.2: Configure the barcode to use a 4‑column layout
generator.Parameters.Barcode.DataBar.Columns = 4;

// Step 3.3: Save the image as a PNG file
generator.Save("ExpandedStackedCols4.png", BarCodeImageFormat.Png);
```

**動作のポイント**

* `EncodeTypes.DatabarExpandedStacked` は Aspose.BarCode に DataBar Expanded Stacked シンボルの生成を指示し、小売向けアプリケーションに適しています。  
* `DataBar.Columns` を `4` に設定すると、シンボルが4つの垂直セクションに分割され、狭いラベルでも可読性が向上します。  
* `Save` はバーコードをディスクに書き込み、`BarCodeImageFormat.Png` 引数によりロスレスな画像品質が保証されます。

このブロックを実行すると、アプリケーションの作業ディレクトリに `ExpandedStackedCols4.png` が作成されます。ファイルには高解像度のバーコードが含まれ、標準的な DataBar リーダーで読み取れます。

## 手順 4: 別レイアウト用にジェネレータを再初期化

行ベースのレイアウトを示すために、新しい `BarcodeGenerator` インスタンスが必要です。再初期化することで、前の列設定が新しい構成に影響しないことが保証されます。

```csharp
// Step 4.1: Create a new generator with the same data string
generator = new BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked,
    "Long data string");
```

## 手順 5: 3行レイアウトを設定

DataBar API は行配置もサポートしています。`Rows` プロパティに値を設定すると、シンボルが何行の水平スライスになるかが決まります。

```csharp
// Step 5.1: Apply a 3‑row layout
generator.Parameters.Barcode.DataBar.Rows = 3;

// Step 5.2: Save the row‑oriented barcode
generator.Save("ExpandedStackedRows3.png", BarCodeImageFormat.Png);
```

**列より行を選ぶ理由**

ラベルの高さが限られていて幅に余裕がある場合に行レイアウトが有効です。3行レイアウトはバーコードを垂直方向に圧縮しつつ、必要なデータ量を保持します。

## 完全なソース ファイル

以下は単体でコンパイル・実行できる `Program.cs` の全体です。列と行の例の両方が含まれているため、1回の実行で2つの PNG ファイルが生成されます。

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

namespace BarcodeGeneratorExample
{
    class Program
    {
        static void Main(string[] args)
        {
            // Data to encode – replace with your own value if needed
            const string data = "Long data string";

            // ---------- Column layout (4 columns) ----------
            var columnGenerator = new BarcodeGenerator(
                EncodeTypes.DatabarExpandedStacked,
                data);

            // Set 4‑column layout
            columnGenerator.Parameters.Barcode.DataBar.Columns = 4;

            // Save the column image
            columnGenerator.Save("ExpandedStackedCols4.png", BarCodeImageFormat.Png);
            Console.WriteLine("Saved ExpandedStackedCols4.png (4‑column layout)");

            // ---------- Row layout (3 rows) ----------
            var rowGenerator = new BarcodeGenerator(
                EncodeTypes.DatabarExpandedStacked,
                data);

            // Set 3‑row layout
            rowGenerator.Parameters.Barcode.DataBar.Rows = 3;

            // Save the row image
            rowGenerator.Save("ExpandedStackedRows3.png", BarCodeImageFormat.Png);
            Console.WriteLine("Saved ExpandedStackedRows3.png (3‑row layout)");
        }
    }
}
```

### 期待される出力

プログラム実行後、ファイル作成を確認する2つのコンソール メッセージが表示されます。

```
Saved ExpandedStackedCols4.png (4‑column layout)
Saved ExpandedStackedRows3.png (3‑row layout)
```

両方の PNG ファイルは、文字列 `"Long data string"` をエンコードした DataBar Expanded Stacked バーコードを表示します。標準的なバーコードスキャナーでどちらの画像をスキャンしても元データが取得できます。

## よくある質問とエッジケース

| Question | Answer |
|----------|--------|
| **Can I change the image format?** | Yes. Replace `BarCodeImageFormat.Png` with `Jpeg`, `Bmp`, or `Tiff` depending on your requirements. |
| **What if the data string is shorter?** | The DataBar format automatically adjusts the symbol size; you do not need to modify the layout settings. |
| **How do I set the barcode size (width/height)?** | Use `generator.Parameters.Image.Width` and `generator.Parameters.Image.Height` before calling `Save`. |
| **Is it possible to add a human‑readable caption?** | Set `generator.Parameters.Barcode.CodeText` and enable `generator.Parameters.Barcode.CodeLocation = CodeLocation.Above`. |
| **What .NET versions are supported?** | Aspose.BarCode supports .NET Standard 2.0, .NET 5/6, and .NET Framework 4.6.1+. |

これらのバリエーションに対応することで、**barcode generator example**は本番環境でも十分に活用できる堅牢なものになります。

## プロのコツ

* **レイアウトが同じ場合にのみジェネレータオブジェクトを再利用**してください。手順 4‑5 のようにレイアウトごとに新しいインスタンスを作成すると、プロパティの不意の引き継ぎを防げます。  
* 必要に応じて `generator.Validate()` で生成されたバーコードを検証し、ISO/GS1 標準への準拠を確認してください。  
* **バッチ処理**: 列と行のロジックをレイアウト構成のリストを走査するループでラップすれば、バリエーションが多数ある場合のコード重複を削減できます。

## 結論

この**barcode generator example**は、4列と3行の DataBar Expanded Stacked バーコードを生成する **generate barcode C#** コードを示しています。これで完全に実行可能なプログラム、主要プロパティ（`Columns`、`Rows`）の理解、そしてソリューション拡張の実践的なヒントが手に入りました。

次は、**バーコードの色カスタマイズ**、**PDF ドキュメントへの埋め込み**、または **Aspose.BarCode での QR コード生成** といった関連トピックを探求してください。これらはすべて本ガイドで扱った API の原則に基づいています。

さまざまなデータ文字列、画像形式、レイアウトの組み合わせで実験し、コーディングを楽しんでください！

## 次に学ぶべきこと

以下のチュートリアルは、本ガイドで示した手法を基にした、密接に関連するトピックをカバーしています。各リソースには、ステップバイステップの解説と完全なコード例が含まれており、API の追加機能を習得したり、代替実装アプローチを自分のプロジェクトで試したりするのに役立ちます。

- [Barcode Generator Example in C# – Set Columns, Rows & Export Image](/barcode/english/python-java/general/barcode-generator-example-in-c-set-columns-rows-export-image/)
- [Generate Aspose.BarCode Databar barcode using .NET API – Row & Column Configuration](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-row-column-configuration/)
- [Barcode generator example in C# – set width and height](/barcode/english/python-java/general/barcode-generator-example-in-c-set-width-and-height/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}