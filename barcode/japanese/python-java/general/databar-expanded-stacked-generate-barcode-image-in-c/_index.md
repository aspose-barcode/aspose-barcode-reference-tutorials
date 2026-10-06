---
category: general
date: 2026-08-15
description: Databar拡張スタック型バーコードのC#での生成。バーコード画像の生成方法や、DataBarレイアウトの列と行の設定方法を学びましょう。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- databar expanded stacked
- generate barcode image
- how to generate barcode
- how to set columns
- how to set rows
language: ja
lastmod: 2026-08-15
og_description: C# で Databar 拡張スタックバーコードを生成します。ステップバイステップのガイドに従い、バーコード画像を作成し、列と行を効率的に設定しましょう。
og_image_alt: Screenshot of a databar expanded stacked barcode generated with C#
og_title: Databar 拡張スタック – C#でバーコード画像を生成
schemas:
- author: Aspose
  dateModified: '2026-08-15'
  description: Databar expanded stacked barcode generation in C#. Learn how to generate
    barcode image, set columns and rows for DataBar layouts.
  headline: 'Databar expanded stacked: generate barcode image in C#'
  type: TechArticle
- description: Databar expanded stacked barcode generation in C#. Learn how to generate
    barcode image, set columns and rows for DataBar layouts.
  name: 'Databar expanded stacked: generate barcode image in C#'
  steps:
  - name: 1. Install the Aspose.BarCode library
    text: 'The code uses the **Aspose.BarCode for .NET** library, which provides the
      `BarcodeGenerator` class. Install the NuGet package with the following command:'
  - name: 2. Create a barcode generator for **databar expanded stacked**
    text: The generator is the entry point for all barcode operations. You must specify
      the symbology (`EncodeTypes.DatabarExpandedStacked`) and the text to encode.
  - name: 3. How to set columns for DataBar
    text: The `Columns` property controls how many vertical modules appear in the
      stacked barcode. Valid values are 2, 3, or 4. Setting columns influences the
      barcode’s width and the amount of data it can store.
  - name: 4. Save the 4‑column barcode image
    text: Saving the image produces a file that you can embed in reports, invoices,
      or mobile apps. The `Save` method accepts a file path and an image format.
  - name: 5. How to set rows for DataBar
    text: Rows add a second dimension to the stacked layout, allowing more data to
      be encoded without widening the barcode. The `Rows` property defaults to 1;
      you can increase it up to 3 for the expanded stacked variant.
  - name: 6. Save the 3‑row barcode image
    text: '```csharp // Step 5: Save the 3‑row barcode image barcode.Save("YOUR_DIRECTORY/DatabarRows3.png",
      BarCodeImageFormat.Png); ```'
  - name: 7. Complete C# example to generate barcode image
    text: 'Putting all steps together yields a self‑contained program you can copy
      into a console application:'
  type: HowTo
tags:
- barcode
- C#
- Aspose.BarCode
title: 'Databar expanded stacked: C#でバーコード画像を生成'
url: /ja/python-java/general/databar-expanded-stacked-generate-barcode-image-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Databar expanded stacked: C# でバーコード画像を生成する方法

C# で **databar expanded stacked** バーコード画像を生成する必要がある場合、このガイドでは **バーコードを生成** する手順をカスタム列・行レイアウトで正確に示します。列の設定方法、行の設定方法、IDE を離れずに画像を保存する方法が分かります。

このチュートリアルで扱う内容:

* **databar expanded stacked** シンボロジー用のバーコードジェネレータを作成する方法。  
* 4 列レイアウトと 3 行レイアウトの構成方法。  
* 各構成を PNG ファイルとして保存する手順。  
* 無効な列数などのエッジケースに対処するためのヒント。

外部ドキュメントは不要です。完全に実行可能なサンプルが同梱されています。

![Databar expanded stacked barcode example](YOUR_DIRECTORY/DatabarCols4.png){: .center alt="C#で生成されたdatabar expanded stackedバーコード" }

## Databar expanded stacked バーコード生成手順

### 1. Aspose.BarCode ライブラリをインストールする

コードは **Aspose.BarCode for .NET** ライブラリを使用します。このライブラリは `BarcodeGenerator` クラスを提供します。以下のコマンドで NuGet パッケージをインストールしてください。

```bash
dotnet add package Aspose.BarCode
```

パッケージがインストールされたら、ファイルの先頭に必要な名前空間を追加します。

```csharp
using Aspose.BarCode.Generation;
```

### 2. **databar expanded stacked** 用のバーコードジェネレータを作成する

ジェネレータはすべてのバーコード操作のエントリーポイントです。シンボロジー (`EncodeTypes.DatabarExpandedStacked`) とエンコードするテキストを指定する必要があります。

```csharp
// Step 1: Create a barcode generator for Databar Expanded Stacked
BarcodeGenerator barcode = new BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked,
    "Databar Expanded Stacked long");
```

*重要ポイント:* `EncodeTypes` 列挙体は、ライブラリにどのバーコード形式を生成させるかを指示します。**databar expanded stacked** を使用すると、スタックレイアウト用の GS1 DataBar 仕様に従った画像が生成されます。

### 3. DataBar の列数を設定する方法

`Columns` プロパティは、スタックされたバーコードに表示される垂直モジュールの数を制御します。有効な値は 2、3、4 のいずれかです。列数を設定すると、バーコードの幅と格納できるデータ量が変わります。

```csharp
// Step 2: Configure a 4‑column layout
barcode.Parameters.Barcode.DataBar.Columns = 4;
```

**ヒント:** 許容範囲外の値を設定しようとすると、ライブラリは `ArgumentException` をスローします。ユーザーに列選択を提供する場合は、必ず入力を検証してください。

### 4. 4 列バーコード画像を保存する

画像を保存すると、レポートや請求書、モバイルアプリに埋め込めるファイルが生成されます。`Save` メソッドはファイルパスと画像形式を受け取ります。

```csharp
// Step 3: Save the 4‑column barcode image
barcode.Save("YOUR_DIRECTORY/DatabarCols4.png", BarCodeImageFormat.Png);
```

ファイルが書き込まれたら、任意の画像ビューアで開き、**databar expanded stacked** パターンが正しく表示されていることを確認できます。

### 5. DataBar の行数を設定する方法

行を追加すると、スタックレイアウトに第 2 の次元が加わり、幅を広げずにデータ容量を増やせます。`Rows` プロパティの既定値は 1 で、拡張スタックバリアントでは最大 3 まで増やせます。

```csharp
// Step 4: Switch to a 3‑row layout (columns remain unchanged)
barcode.Parameters.Barcode.DataBar.Rows = 3;
```

**行が重要な理由:** 行数を増やすと全体の幅が抑えられ、狭いラベルやモバイル画面での使用に適します。

### 6. 3 行バーコード画像を保存する

```csharp
// Step 5: Save the 3‑row barcode image
barcode.Save("YOUR_DIRECTORY/DatabarRows3.png", BarCodeImageFormat.Png);
```

これで、4 列レイアウトと 3 行レイアウトの 2 つの PNG ファイルが作成され、どちらも **databar expanded stacked** シンボロジーを使用しています。

### 7. バーコード画像を生成する完全な C# サンプル

すべての手順を組み合わせると、コンソール アプリケーションに貼り付けてそのまま実行できる自己完結型プログラムが完成します。

```csharp
using System;
using Aspose.BarCode.Generation;

namespace DatabarExpandedStackedDemo
{
    class Program
    {
        static void Main()
        {
            // Create the generator for Databar Expanded Stacked
            BarcodeGenerator barcode = new BarcodeGenerator(
                EncodeTypes.DatabarExpandedStacked,
                "Databar Expanded Stacked long");

            // Configure a 4‑column layout and save
            barcode.Parameters.Barcode.DataBar.Columns = 4;
            barcode.Save("YOUR_DIRECTORY/DatabarCols4.png", BarCodeImageFormat.Png);
            Console.WriteLine("4‑column barcode saved.");

            // Change to a 3‑row layout (columns stay at 4) and save
            barcode.Parameters.Barcode.DataBar.Rows = 3;
            barcode.Save("YOUR_DIRECTORY/DatabarRows3.png", BarCodeImageFormat.Png);
            Console.WriteLine("3‑row barcode saved.");
        }
    }
}
```

**期待される出力**

プログラムを実行すると次のように表示されます。

```
4‑column barcode saved.
3‑row barcode saved.
```

そして `YOUR_DIRECTORY` に 2 つの PNG ファイルが作成されます。ファイルを開いて、各画像に有効な **databar expanded stacked** バーコードが表示されていることを確認してください。

## よくある落とし穴と実践的なヒント

* **ディレクトリの存在** – `Save` は不足しているフォルダーを自動作成しません。`YOUR_DIRECTORY` が存在することを確認するか、保存前に `Directory.CreateDirectory` を使用してください。  
* **列の上限** – 2、3、4 以外の値は例外を発生させます。ユーザー入力エラーを防ぐために簡単な範囲チェックを実装しましょう:

  ```csharp
  int columns = 4;
  if (columns < 2 || columns > 4) throw new ArgumentOutOfRangeException(nameof(columns));
  barcode.Parameters.Barcode.DataBar.Columns = columns;
  ```

* **行の上限** – 拡張スタックバリアントは最大 3 行までサポートします。`Rows` に 0 または 3 を超える値を設定すると例外がスローされます。  
* **画像形式** – `BarCodeImageFormat.Png` はロスレス品質を提供し、印刷に最適です。ファイルサイズが最重要の場合のみ `Jpeg` を使用してください。

## 次のステップ

カスタム列・行構成で **バーコードを生成** する方法が分かったので、以下のことが可能になります:

* Web API にジェネレータを組み込み、オンデマンドでバーコード画像を配信する。  
* 請求書に埋め込むため、PDF 生成ライブラリと組み合わせて使用する。  
* 同じ `Parameters.Barcode.DataBar` オブジェクトを使い、他の DataBar バリアント（`DatabarExpanded`、`DatabarLimited`）を試す。

バーの色変更やヒューマンリーダブルテキストの追加、QR コードのオーバーレイなど、さらに高度なカスタマイズについては Aspose.BarCode の `BarcodeGenerator` プロパティに関するドキュメントをご参照ください。

---

このガイドに従うことで **databar expanded stacked** のワークフローを習得し、**列の設定方法**、**行の設定方法** をマスターし、実稼働に使える 2 つの異なるバーコード画像を作成できました。コーディングを楽しんでください！


## 次に学ぶべきことは？

以下のチュートリアルは、本ガイドで示したテクニックを基にした関連トピックを扱っています。各リソースには完全な動作コード例とステップバイステップの解説が含まれており、追加の API 機能を習得したり、プロジェクトで代替実装アプローチを探求したりするのに役立ちます。

- [Generate barcode image – GS1 Coupon UPC-A Databar](/barcode/english/net/gs1-barcode-encoding/gs1-coupon-upc-a-databar-configuration/)
- [Create DotCode barcode image – rows & columns (Aspose.BarCode)](/barcode/english/net/dotcode-barcode-configuration/dotcode-rows-columns-configuration/)
- [How to Generate Barcode - One-Dimensional Barcode Types](/barcode/english/net/one-dimensional-barcode-types/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}