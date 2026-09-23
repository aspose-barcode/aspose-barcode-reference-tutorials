---
category: general
date: 2026-08-12
description: C# で BarCodeGenerator を使用してバーコード画像を作成します。DataBar の生成方法、バーコード画像のサイズ調整、複数のバーコードを効率的に作成する方法を学びましょう。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode image
- barcode generator c#
- create multiple barcodes
- how to generate databar
- barcode image size
language: ja
lastmod: 2026-08-12
og_description: BarCodeGenerator を使用して C# でバーコード画像を作成します。このチュートリアルでは、DataBar コードの生成方法、バーコード画像サイズの調整、複数のバーコードの作成方法をステップバイステップで示します。
og_image_alt: Screenshot of a generated DataBar barcode image saved as PNG
og_title: C#でバーコード画像を作成 – 完全なBarCodeGeneratorガイド
schemas:
- author: Aspose
  dateModified: '2026-08-12'
  description: Create barcode image in C# using BarCodeGenerator. Learn how to generate
    DataBar, control barcode image size, and create multiple barcodes efficiently.
  headline: Create barcode image in C# with BarCodeGenerator
  type: TechArticle
- description: Create barcode image in C# using BarCodeGenerator. Learn how to generate
    DataBar, control barcode image size, and create multiple barcodes efficiently.
  name: Create barcode image in C# with BarCodeGenerator
  steps:
  - name: Setting up a **barcode generator c#** instance for DataBar Omni‑directional
      encoding.
    text: Setting up a **barcode generator c#** instance for DataBar Omni‑directional
      encoding.
  - name: Adjusting **barcode image size** by changing X‑dimension and bar height.
    text: Adjusting **barcode image size** by changing X‑dimension and bar height.
  - name: Using a loop to **create multiple barcodes** with different heights.
    text: Using a loop to **create multiple barcodes** with different heights.
  - name: Saving the images as PNG files and verifying the output.
    text: Saving the images as PNG files and verifying the output.
  type: HowTo
tags:
- barcode
- csharp
- barcodegenerator
- databar
- image-processing
title: BarCodeGenerator を使用して C# でバーコード画像を作成する
url: /ja/python-java/general/create-barcode-image-in-c-with-barcodegenerator/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# C# と BarCodeGenerator を使用してバーコード画像を作成する

.NET アプリケーションで **バーコード画像を作成** する必要がある場合、このガイドでは `BarCodeGenerator` クラスを使って正確に行う方法を示します。小売 POS システムや在庫管理ツールを構築しているかどうかに関わらず、DataBar シンボルの生成、バーコード画像サイズの制御、そして一度の実行で複数のバーコードを生成する方法を学べます。

また、**barcode generator c#** API を使用して寸法を調整したり、出力形式を切り替えたり、無効なデータ文字列などのエッジケースを処理できることもわかります。チュートリアルの最後までに、繰り返しコードを書くことなく自信を持って **複数のバーコードを作成** できるようになります。

## 前提条件

- .NET 6.0 以降がインストールされていること  
- 開発環境 (Visual Studio、Rider、または VS Code)  
- Aspose.BarCode for .NET NuGet パッケージ（または `BarCodeGenerator` を提供する互換ライブラリ）  

パッケージは次のコマンドで追加できます:

```bash
dotnet add package Aspose.BarCode
```

## このチュートリアルでカバーする内容

1. DataBar Omni‑directional エンコーディング用の **barcode generator c#** インスタンスを設定する。  
2. X‑dimension とバー高さを変更して **barcode image size** を調整する。  
3. ループを使用して異なる高さの **multiple barcodes** を作成する。  
4. 画像を PNG ファイルとして保存し、出力を検証する。  

すべてのコードスニペットは完全で、新しいコンソールプロジェクトにコピー＆ペーストできる状態です。

![バーコード画像作成例](barcode-example.png){alt="バーコード画像作成例"}

## ステップ 1: ジェネレータの初期化 – バーコード画像の基本作成

最初のステップは、目的のシンボリズムで `BarCodeGenerator` をインスタンス化することです。DataBar Omni‑directional シンボルの場合は `EncodeTypes.DatabarOmniDirectional` を使用します。

```csharp
using System;
using Aspose.BarCode.Generation;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // Create a barcode generator for DataBar Omni‑directional.
            // The string "(01)12345678901231" follows the GS1 Application Identifier format.
            var generator = new BarCodeGenerator(EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");

            // The rest of the steps are performed below.
        }
    }
}
```

**重要性:** ジェネレータをインスタンス化することでエンコーディングルールとデータペイロードが定義されます。正しい `EncodeTypes` の値を省略すると、ライブラリはサポートされていないバーコードを生成するか、例外をスローします。

## ステップ 2: X‑dimension とバー高さの設定 – バーコード画像サイズの制御

バーコードの視覚的サイズは 2 つのパラメータで決まります。

| Parameter | 制御内容 | 標準範囲 |
|-----------|----------|----------|
| `x_dimension.pixels` | 最小モジュール（“ドット”）の幅 | 1 – 4 px |
| `bar_height.pixels`  | 縦バーの高さ | 30 – 150 px |

```csharp
// Set the module width to 2 px for a crisp, readable image.
generator.Parameters.Barcode.XDimension.Pixels = 2;

// Set an initial bar height of 30 px.
generator.Parameters.Barcode.BarHeight.Pixels = 30;
```

**プロのヒント:** 小さな X‑dimension は高解像度の画像を生成しますが、低品質のプリンターではスキャンが困難になる場合があります。対象のスキャン機器に合わせて値を調整してください。

## ステップ 3: 最初のバーコードを保存 – 30 px の高さでバーコード画像を作成

これで画像を生成し、ディスクに書き込むことができます。`Save` メソッドはファイルパスと画像フォーマットの列挙型を受け取ります。

```csharp
// Save the 30 px high barcode as a PNG file.
string outputFolder = @"C:\Barcodes";
generator.Save($"{outputFolder}\\Databar30.png", BarCodeImageFormat.Png);
Console.WriteLine("Saved Databar30.png (30 px height)");
```

**期待結果:** `C:\Barcodes` に `Databar30.png` という PNG ファイルが作成されます。ファイルを開くと、はっきりとした高コントラストのパターンを持つ DataBar Omni‑directional シンボルが表示されます。

## ステップ 4: 高さを変更して追加画像を生成 – 複数のバーコードを作成

異なる寸法で **複数のバーコード** を作成するには、`BarHeight` プロパティを変更し、再度 `Save` を呼び出すだけです。これによりジェネレータの再インスタンス化を回避でき、メモリと CPU 時間を節約できます。

```csharp
// Increase the bar height to 60 px for a larger barcode.
generator.Parameters.Barcode.BarHeight.Pixels = 60;
generator.Save($"{outputFolder}\\Databar60.png", BarCodeImageFormat.Png);
Console.WriteLine("Saved Databar60.png (60 px height)");

// You can repeat the process for any height you need.
int[] heights = { 90, 120 };
foreach (int h in heights)
{
    generator.Parameters.Barcode.BarHeight.Pixels = h;
    generator.Save($"{outputFolder}\\Databar{h}.png", BarCodeImageFormat.Png);
    Console.WriteLine($"Saved Databar{h}.png ({h} px height)");
}
```

**動作理由:** `BarCodeGenerator` オブジェクトはすべての設定状態を保持しています。単一のプロパティを変更するだけで次の `Save` 呼び出し時のレンダリングエンジンが更新され、効率的に **複数のバーコード** を作成できます。

## ステップ 5: 上級編 – カスタムデータで DataBar を生成する方法

上記の例は静的な GS1 ペイロードを使用しています。実際のシナリオでは可変の製品識別子を埋め込む必要があることが多いです。ライブラリは DataBar 仕様に合致する任意の文字列を受け入れます。

```csharp
string[] gtins = { "01234567890123", "98765432109876", "12345678901234" };
foreach (var gtin in gtins)
{
    // GS1 Application Identifier (01) + GTIN
    generator.CodeText = $"(01){gtin}";
    generator.Parameters.Barcode.BarHeight.Pixels = 50; // uniform height
    generator.Save($"{outputFolder}\\Databar_{gtin}.png", BarCodeImageFormat.Png);
    Console.WriteLine($"Saved barcode for GTIN {gtin}");
}
```

**重要ポイント:** `generator.CodeText` を設定すると、オブジェクトを再作成せずにエンコードされたデータが更新されます。大量のデータセットを扱う際に推奨される **how to generate databar** パターンです。

## ステップ 6: 検証とトラブルシューティング – 正しいバーコード画像サイズの確保

画像を生成した後、プログラム上で寸法が期待通りであることを確認したくなることがあります。`System.Drawing` の `Image` クラスを使用すると、ファイルを読み取りサイズを取得できます。

```csharp
using System.Drawing;

// Verify image dimensions
string[] files = { "Databar30.png", "Databar60.png", "Databar90.png" };
foreach (var file in files)
{
    using var img = Image.FromFile($"{outputFolder}\\{file}");
    Console.WriteLine($"{file}: {img.Width}px × {img.Height}px");
}
```

設定した高さが反映されていない場合は、以下を確認してください：

- **X‑dimension**: 非常に小さい値はレンダラが高さを丸める原因になることがあります。  
- **Image format**: JPEG などの一部フォーマットは保存時に圧縮を行い、ピクセル寸法が変わることがあります。PNG は正確な寸法を保持します。

## ステップ 7: バーコード画像サイズとパフォーマンスに関するベストプラクティス

| 推奨事項 | 理由 |
|----------|------|
| ほとんどのスキャナで `x_dimension.pixels` を 2 – 3 px の範囲に保つ。 | 可読性とファイルサイズのバランスを取ります。 |
| 印刷する場合はロスレス出力の PNG を使用する。 | 正確な寸法と鮮明なエッジを保証します。 |
| 多数のバーコードを生成する際は単一の `BarCodeGenerator` インスタンスを再利用する。 | オブジェクト割り当てのオーバーヘッドを削減します。 |
| `CodeText` に割り当てる前に、入力文字列を GS1 標準に対して検証する。 | 実行時例外や無効なスキャンを防止します。 |
| 生成した画像は専用フォルダに明確な命名規則で保存する（例: `Databar_{GTIN}.png`）。 | 下流処理や監査トレイルを簡素化します。 |

## 完全な動作例

以下は、初期化から検証までのすべてのステップを組み込んだ完全なプログラムです。コードを新しいコンソールプロジェクトにコピーして実行してください。



## 次に学ぶべきことは？

以下のチュートリアルは、本ガイドで示した手法を基にした密接に関連するトピックを取り上げています。各リソースには、完全な動作コード例とステップバイステップの解説が含まれており、追加の API 機能を習得し、独自プロジェクトで代替実装アプローチを検討するのに役立ちます。

- [バーコード画像の生成 – GS1 クーポン UPC-A Databar](/barcode/english/net/gs1-barcode-encoding/gs1-coupon-upc-a-databar-configuration/)
- [DotCode バーコード画像の作成 – 行と列 (Aspose.BarCode)](/barcode/english/net/dotcode-barcode-configuration/dotcode-rows-columns-configuration/)
- [Aspose.BarCode for .NET を使用した ITF-14 のバーコードクワイエットゾーンの作成方法](/barcode/english/net/itf-14-barcode-customization/itf-14-barcode-quiet-zone-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}