---
category: general
date: 2026-09-23
description: C# バーコードジェネレータチュートリアルでは、Aspose.BarCode ライブラリを使用して、カスタムアスペクト比のバーコード画像を生成する方法を示しています。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- c# barcode generator
- how to generate barcode
- DataBar barcode C#
- barcode aspect ratio
- Aspose.BarCode C#
- barcode image export
language: ja
lastmod: 2026-09-23
og_description: C# バーコードジェネレーターガイドでは、Aspose.BarCode を使用してバーコード画像の生成、アスペクト比の調整、PNG
  ファイルへのエクスポート方法を解説します。
og_image_alt: Screenshot of a barcode created with a C# barcode generator
og_title: C# バーコードジェネレーターで高品質なバーコードを作成する
schemas:
- author: Aspose
  dateModified: '2026-09-23'
  description: c# barcode generator tutorial shows how to generate barcode images
    with custom aspect ratios using the Aspose.BarCode library.
  headline: How to use a C# barcode generator for DataBar codes
  type: TechArticle
- description: c# barcode generator tutorial shows how to generate barcode images
    with custom aspect ratios using the Aspose.BarCode library.
  name: How to use a C# barcode generator for DataBar codes
  steps:
  - name: Switching to another barcode type
    text: 'If you need a QR code, Code 128, or PDF417, replace the enum value in the
      constructor:'
  - name: Handling unsupported characters
    text: 'The `BarcodeGenerator` validates the input string against the selected
      symbology. Supplying an illegal character throws an `ArgumentException`. Wrap
      the creation in a try‑catch block to provide a friendly error message:'
  - name: Exporting to other image formats
    text: 'Aspose.BarCode supports BMP, JPEG, TIFF, and SVG. Change the second argument
      of `Save` accordingly:'
  - name: High‑resolution output for printing
    text: 'When printing on high‑DPI printers, increase the X‑dimension and optionally
      set the `Resolution` property:'
  type: HowTo
tags:
- barcode
- c#
- Aspose
title: C# バーコードジェネレーターを使って DataBar コードを生成する方法
url: /ja/python-java/general/how-to-use-a-c-barcode-generator-for-databar-codes/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# DataBarコード用C#バーコードジェネレータの使用方法

DataBarスタック型Omni‑Directionalシンボルを生成できる **c# barcode generator** が必要な場合、このガイドは完全に実行可能なソリューションを提供します。バーコード画像の生成方法、X‑ディメンションの制御方法、アスペクト比の変更方法をIDEから離れずに学べます。

バーコードの生成は在庫管理システム、出荷ラベル、POSアプリケーションなどで一般的な要件です。このチュートリアルの最後までに、任意のアスペクト比でPNGファイルを作成でき、他のバーコードタイプへコードを適用する方法も理解できるようになります。

## 前提条件

開始する前に、以下がインストールされていることを確認してください。

* .NET 6.0 SDK 以降  
* Visual Studio 2022（またはお好みのC#エディタ）  
* **Aspose.BarCode** への NuGet 参照 – `BarcodeGenerator` クラスを提供するライブラリ  

別途グラフィックライブラリは不要です。Aspose.BarCode が画像エンコードを内部で処理します。

## 手順 1: Aspose.BarCode NuGet パッケージをインストール

プロジェクトフォルダーでターミナルを開き、次のコマンドを実行します。

```bash
dotnet add package Aspose.BarCode
```

このコマンドはライブラリの最新安定版をプロジェクトファイルに追加し、`BarcodeGenerator` クラスを使用可能にします。

## 手順 2: 出力フォルダーを定義

生成された PNG ファイルを保存するフォルダーを選択します。絶対パスでも相対パスでも構いませんが、相対パスにするとプロジェクトがポータブルになります。

```csharp
// Define the output folder (relative to the project root)
string outputFolder = "GeneratedBarcodes/";
Directory.CreateDirectory(outputFolder); // Ensure the folder exists
```

プログラムでディレクトリを作成すれば、フォルダーが存在しない場合の実行時エラーを防げます。

## 手順 3: サンプルデータで C# バーコードジェネレータをインスタンス化

`BarcodeGenerator` コンストラクタは 2 つの引数を受け取ります: バーコードタイプとデータ文字列。DataBarスタック型Omni‑Directionalシンボルの場合は `EncodeTypes.DatabarStackedOmniDirectional` を使用します。

```csharp
// Create a barcode generator for a DataBar stacked Omni‑Directional code
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarStackedOmniDirectional,
    "(01)12345678901231");
```

データ文字列は GS1 アプリケーション識別子形式に従います。`EncodeTypes` 列挙体には 150 種類以上のバーコード規格が含まれており、列挙体の値を変更すれば別のタイプに切り替えられます。

## 手順 4: バーコードの X‑ディメンション（ピクセルサイズ）を設定

X‑ディメンションは最細バーの幅を制御します。ピクセル値を 2 に設定すると、ほとんどの画面に適した鮮明で高解像度な画像が得られます。

```csharp
// Set the X‑dimension to 2 pixels
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

X‑ディメンションの調整は任意ですが、バーコードの視覚的密度を細かく制御できます。

## 手順 5: アスペクト比 15 のバーコードを生成し PNG として保存

`AspectRatio` プロパティは `DataBar` サブオブジェクトに属します。この値を変更すると、エンコードされたデータは保持したままバーコードが垂直方向に伸縮します。

```csharp
// Set aspect ratio to 15 and save the image
barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 15;
barcodeGenerator.Save($"{outputFolder}DatabarAspectRatio15.png", BarCodeImageFormat.Png);
```

`Save` メソッドは指定されたファイルパスにバーコードを書き出します。`BarCodeImageFormat.Png` 列挙体によりロスレス圧縮が保証されます。

![c# barcode generator output example](generated_barcode_example.png)

*画像: アスペクト比 15 で生成されたバーコード。*

## 手順 6: アスペクト比を 30 に変更し、2 枚目の画像を生成

同じ `BarcodeGenerator` インスタンスを再利用すれば、新しいオブジェクトを割り当てる必要がありません。`AspectRatio` を更新し、再度 `Save` を呼び出すだけです。

```csharp
// Update aspect ratio to 30 and save a second image
barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 30;
barcodeGenerator.Save($"{outputFolder}DatabarAspectRatio30.png", BarCodeImageFormat.Png);
```

これで、垂直スケーリングが異なる 2 つの PNG ファイルが作成されました。この手法は、同一データを異なるラベルサイズで表示したい場合に便利です。

## よくあるバリエーションとエッジケース

### 別のバーコードタイプへ切り替える

QR コード、Code 128、PDF417 などが必要な場合は、コンストラクタの列挙体値を置き換えます。

```csharp
BarcodeGenerator qrGenerator = new BarcodeGenerator(
    EncodeTypes.QR, "https://example.com");
```

その他の設定手順（X‑ディメンション、保存）は同じです。

### 非対応文字の取り扱い

`BarcodeGenerator` は選択したシンボロジーに対して入力文字列を検証します。無効な文字を指定すると `ArgumentException` がスローされます。try‑catch ブロックで囲んで、ユーザーフレンドリーなエラーメッセージを提供しましょう。

```csharp
try
{
    var generator = new BarcodeGenerator(EncodeTypes.DatabarStackedOmniDirectional, data);
}
catch (ArgumentException ex)
{
    Console.WriteLine($"Invalid data for the selected barcode type: {ex.Message}");
}
```

### 他の画像形式へのエクスポート

Aspose.BarCode は BMP、JPEG、TIFF、SVG をサポートしています。`Save` の第2引数を適切に変更してください。

```csharp
barcodeGenerator.Save($"{outputFolder}Databar.svg", BarCodeImageFormat.Svg);
```

### 印刷用の高解像度出力

高 DPI プリンタで印刷する場合は、X‑ディメンションを上げ、必要に応じて `Resolution` プロパティも設定します。

```csharp
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 4;
barcodeGenerator.Parameters.ImageResolution.Dpi = 300;
```

これらの設定によりファイルサイズは大きくなりますが、物理メディア上でもエッジが鮮明に保たれます。

## 期待される出力

プログラムを実行すると、`GeneratedBarcodes/` フォルダー内に以下のファイルが作成されます。

* `DatabarAspectRatio15.png` – 標準高さの DataBar コード  
* `DatabarAspectRatio30.png` – 垂直に伸長されたバージョン  

両画像は同一の GS1 データをエンコードしており、任意のバーコードスキャナアプリで検証できます。

## 完全なソースコード

以下のコードを新しいコンソールプロジェクト（`dotnet new console`）に貼り付けて実行してください。プログラムはコンソールにステータスメッセージを表示し、PNG ファイルをディスクに書き出します。

```csharp
using System;
using System.IO;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Step 2: Define the output folder
        string outputFolder = "GeneratedBarcodes/";
        Directory.CreateDirectory(outputFolder);

        // Step 3: Create a C# barcode generator with sample data
        BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
            EncodeTypes.DatabarStackedOmniDirectional,
            "(01)12345678901231");

        // Step 4: Set common barcode properties (pixel size of X‑dimension)
        barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;

        // Step 5: Generate a barcode with aspect ratio 15 and save it as PNG
        barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 15;
        string file15 = Path.Combine(outputFolder, "DatabarAspectRatio15.png");
        barcodeGenerator.Save(file15, BarCodeImageFormat.Png);
        Console.WriteLine($"Saved barcode with aspect ratio 15 to {file15}");

        // Step 6: Change the aspect ratio to 30 and save the new image
        barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 30;
        string file30 = Path.Combine(outputFolder, "DatabarAspectRatio30.png");
        barcodeGenerator.Save(file30, BarCodeImageFormat.Png);
        Console.WriteLine($"Saved barcode with aspect ratio 30 to {file30}");
    }
}
```

プログラム実行時のコンソール出力例:

```
Saved barcode with aspect ratio 15 to GeneratedBarcodes/DatabarAspectRatio15.png
Saved barcode with aspect ratio 30 to GeneratedBarcodes/DatabarAspectRatio30.png
```

## 結論

これで **c# barcode generator** を使用し、DataBarスタック型Omni‑Directionalシンボルの生成、X‑ディメンションの調整、カスタムアスペクト比での PNG エクスポートができるようになりました。同じパターンは Aspose.BarCode がサポートする他のすべてのバーコードシンボロジーでも機能し、在庫管理、出荷、POS ソリューションへのバーコード作成の統合が容易になります。

さらに学びたい方は、以下に挑戦してみてください。

* QR コードや PDF417 シンボルの生成（モバイルアプリ向け `how to generate barcode`）  
* SVG へのエクスポートでスケーラブルなウェブグラフィックを作成  
* Aspose.PDF を使用して生成画像を PDF 請求書に直接埋め込む  

さまざまな `AspectRatio` 値、X‑ディメンションサイズ、出力形式を試し、正確な要件に合わせたバーコードを作成しましょう。

## 次に学ぶべきことは？

以下のチュートリアルは、本ガイドで示したテクニックを応用した関連トピックを扱っています。各リソースには、ステップバイステップの説明と完全な動作コード例が含まれており、API の追加機能を習得したり、独自プロジェクトで代替実装アプローチを探求したりするのに役立ちます。

- [How to generate Aztec barcode with custom aspect ratio using Aspose.BarCode for .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)
- [How to Adjust Barcode Size – Codablock F Aspect Ratio with Aspose.BarCode for .NET](/barcode/english/net/codablock-f-encoding/codablock-f-aspect-ratio-customization/)
- [How to Generate and Adjust Barcode Height for One-Dimensional Databar using Aspose.BarCode for .NET](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-barcode-height-adjustment/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}