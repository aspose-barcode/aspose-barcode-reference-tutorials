---
category: general
date: 2026-09-07
description: バーコードジェネレーター C# チュートリアル：バーコードの PNG ファイルを生成する方法と、行と列をカスタマイズできる DataBar
  バーコードの作成方法を示します
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- barcode generator C#
- generate barcode PNG
- create DataBar barcode
language: ja
lastmod: 2026-09-07
og_description: バーコードジェネレーター C# チュートリアル：バーコードの PNG ファイル生成方法を学び、カスタム行列で DataBar バーコードを数分で作成できます
og_image_alt: Sample DataBar Expanded Stacked barcode saved as PNG using barcode generator
  C#
og_title: バーコードジェネレーター C# – DataBar バーコードと PNG 画像を作成
schemas:
- author: Aspose
  dateModified: '2026-09-07'
  description: barcode generator C# tutorial that shows you how to generate barcode
    PNG files and create DataBar barcodes with customizable rows and columns
  headline: How to use a barcode generator C# to create DataBar barcodes
  type: TechArticle
tags:
- barcode
- C#
- DataBar
title: C#のバーコードジェネレーターを使ってDataBarバーコードを作成する方法
url: /ja/python-java/general/how-to-use-a-barcode-generator-c-to-create-databar-barcodes/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# C# のバーコードジェネレータを使用して DataBar バーコードを作成する方法

高品質なバーコードを作成するための **barcode generator C#** が必要な場合、本ガイドでは **barcode PNG** ファイルの生成方法と、カスタム行・列で **DataBar バーコード** を作成する方法を示します。小売在庫システムやチケットプラットフォームを構築する場合でも、以下の手順で単一の自己完結型例として DataBar Expanded Stacked バーコードを生成できます。

このチュートリアルで学べること:

* `BarcodeGenerator` を DataBar Expanded Stacked シンボロジー用にインスタンス化する方法。  
* ISO / GS1 仕様に合わせて列と行の設定を調整する方法。  
* 出力を PNG 画像として保存し、ウェブページに埋め込んだりラベルに印刷したりできる方法。  

外部サービスは不要です—Aspose.BarCode for .NET ライブラリ（または同じ API に従う互換ライブラリ）だけで動作します。コードは .NET 6+ 上で実行でき、Visual Studio、Rider、または C# をサポートする任意の IDE で動作します。

## 前提条件

開始する前に、以下が揃っていることを確認してください:

* .NET 6 SDK 以降がインストールされていること。  
* `Aspose.BarCode` NuGet パッケージへの参照（または `BarcodeGenerator`、`EncodeTypes`、`BarCodeImageFormat` を提供する同等のライブラリ）。  
* C# の構文とプロジェクト構成に関する基本的な知識。  

コマンドラインでパッケージを追加できます:

```bash
dotnet add package Aspose.BarCode
```

## 手順 1: DataBar Expanded Stacked 用の C# バーコードジェネレータを初期化する

最初のステップは、**DataBar Expanded Stacked** シンボロジーを対象とした `BarcodeGenerator` インスタンスを作成することです。このオブジェクトは、エンコードするテキストを含むすべての描画パラメータを保持します。

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

// Step 1: Create a barcode generator for DataBar Expanded Stacked
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked,          // Symbology
    "Databar Expanded Stacked long");            // Data to encode
```

**重要な理由:** `EncodeTypes.DatabarExpandedStacked` 列挙値は、ライブラリに適用すべきバーコード標準を指示します。正しい列挙値を使用することで、生成された画像が GS1 DataBar 仕様に準拠していることが保証されます。

## 手順 2: 列数を設定する（デフォルトで行は使用されます）

DataBar Expanded Stacked は複数の列に分割できます。列数を調整すると視覚的な密度が変わり、限られたスペースに長いデータ文字列を収めやすくなります。

```csharp
// Step 2: Set the number of columns (default rows are used)
barcodeGenerator.Parameters.Barcode.DataBar.Columns = 4;
```

**プロのコツ:** デフォルトの列数は 1 です。4 に設定すると、4 つのスタックされた列が作成され、バーコードの高さを抑えつつ長い数値文字列に最適です。

## 手順 3: 列設定を適用したバーコード PNG を生成する

次に、バーコードを PNG 画像として保存します。PNG はスキャナーに必要な鮮明なエッジを保持し、ウェブと印刷の両方でうまく機能します。

```csharp
// Step 3: Save the barcode image with the column setting applied
barcodeGenerator.Save("YOUR_DIRECTORY/DatabarCols4.png", BarCodeImageFormat.Png);
```

`DatabarCols4.png` ファイルには、HTML に直接埋め込める **barcode PNG** が含まれています:

```html
<img src="DatabarCols4.png" alt="Sample DataBar Expanded Stacked barcode saved as PNG using barcode generator C#">
```

## 手順 4: 行設定用に別のジェネレータインスタンスを作成する

列ではなく行数を制御したい場合は、新しい `BarcodeGenerator` をインスタンス化してください。次元を変更した後に同じインスタンスを再利用すると予期しないレイアウトのアーティファクトが発生する可能性があるため、フレッシュなオブジェクトを使用するのが最も安全です。

```csharp
// Step 4: Create a new generator instance for the same barcode type
BarcodeGenerator rowBarcodeGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked,
    "Databar Expanded Stacked long");
```

## 手順 5: 行数を設定する（デフォルトで列は使用されます）

行はバーコードモジュールの垂直スタックに影響します。行数を増やすとバーコードが高くなり、特定のラベルサイズで必要になることがあります。

```csharp
// Step 5: Set the number of rows (default columns are used)
rowBarcodeGenerator.Parameters.Barcode.DataBar.Rows = 3;
```

**行と列の違い:** 列はバーコードを横方向に分割し、行は縦方向に伸ばします。ラベルレイアウトに最適な向きを選択してください。

## 手順 6: 行設定を適用したバーコード PNG を生成する

最後に、行調整されたバーコードを PNG ファイルとして保存します。

```csharp
// Step 6: Save the barcode image with the row setting applied
rowBarcodeGenerator.Save("YOUR_DIRECTORY/DatabarRows3.png", BarCodeImageFormat.Png);
```

これで 2 つの異なる PNG ファイルが作成されました:

* `DatabarCols4.png` – 4 列、1 行。  
* `DatabarRows3.png` – 1 列、3 行。

両方の画像は、アプリケーション、レポート、または印刷ラベルで即座に使用できる状態です。

## カスタム寸法で C# のバーコード PNG ファイルを生成する方法

上記のパターンは、任意の DataBar バリエーションやライブラリがサポートする他のシンボロジーでも再利用できます。以下はユーティリティクラスにコピー＆ペーストできるコンパクトなテンプレートです：

```csharp
public static void GenerateDatabar(string data, int columns = 1, int rows = 1, string outputPath = "output.png")
{
    BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.DatabarExpandedStacked, data);
    generator.Parameters.Barcode.DataBar.Columns = columns;
    generator.Parameters.Barcode.DataBar.Rows = rows;
    generator.Save(outputPath, BarCodeImageFormat.Png);
}
```

このようにメソッドを呼び出します:

```csharp
GenerateDatabar("1234567890123", columns: 4, outputPath: "DatabarCols4.png");
GenerateDatabar("1234567890123", rows: 3, outputPath: "DatabarRows3.png");
```

**考慮すべきエッジケース**

* **データ長** – DataBar Expanded Stacked は最大 74 桁の数値文字をエンコードできます。この上限を超えると例外がスローされます。ジェネレータを呼び出す前に入力長を検証してください。  
* **無効な寸法** – このシンボロジーでは列は 1‑4、行は 1‑3 に制限されています。範囲外の値を指定すると無視されるかエラーが発生します。  
* **画像 DPI** – 印刷用に高解像度が必要な場合は、保存前に `generator.Parameters.ImageResolution` を設定してください。

## 期待される出力

`DatabarCols4.png` または `DatabarRows3.png` を開くと、はっきりとした高コントラストの DataBar バーコードが表示されます。GS1 互換スキャナーで画像をスキャンすると、元のテキスト "Databar Expanded Stacked long" が返されます。

![barcode generator C# を使用して PNG として保存されたサンプル DataBar Expanded Stacked バーコード](image.png)

*Alt text: barcode generator C# を使用して PNG として保存されたサンプル DataBar Expanded Stacked バーコード*

## 結論

このチュートリアルでは、**barcode generator C#** を使用して **DataBar バーコード** を作成し、カスタムの行・列設定で **barcode PNG** ファイルを生成する方法を示しました。6 つの手順（ジェネレータの初期化、列または行の設定、PNG として保存）に従うことで、在庫システム、チケット発行、または信頼性の高いバーコード描画が必要なあらゆるシナリオに適した、実装可能な画像を取得できます。

次に、以下を検討できます:

* PNG にカラーや背景画像を追加する（ほとんどのスキャナーと互換性あり）。  
* `BarcodeGenerator` API を使用して、QR、Code 128、PDF417 などの他のシンボロジーを利用する。  
* 生成した PNG を ASP.NET Core MVC ビューや Blazor コンポーネントに直接埋め込む。

さまざまなデータ文字列、寸法、画像フォーマット（例：JPEG、BMP）で自由に試してみてください。同じパターンが適用できるため、**barcode generator C#** はあらゆる .NET 開発者のツールボックスで多用途なツールとなります。コーディングを楽しんでください！

## 次に学ぶべきことは？

以下のチュートリアルは、本ガイドで示した手法を基にした密接に関連するトピックをカバーしています。各リソースには、ステップバイステップの解説付きの完全な動作コード例が含まれており、追加の API 機能を習得し、プロジェクトで代替実装アプローチを探求するのに役立ちます。

- [C# でバーコードを生成 – DataBar バーコードを作成](/barcode/english/python-java/general/generate-barcode-c-create-databar-barcode/)
- [バーコードジェネレータ例 – C# で DataBar 画像を構築](/barcode/english/python-java/general/barcode-generator-example-build-databar-image-in-c/)
- [C# のバーコードジェネレータ例 – 列・行を設定して画像をエクスポート](/barcode/english/python-java/general/barcode-generator-example-in-c-set-columns-rows-export-image/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}