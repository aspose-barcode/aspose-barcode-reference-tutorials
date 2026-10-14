---
category: general
date: 2026-10-08
description: C# バーコードジェネレーターの例で、バーの高さを30 pxから60 pxに数行のコードだけで調整し、バーコード画像のサイズ変更方法を学びましょう。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to resize barcode
- barcode generator example c#
language: ja
lastmod: 2026-10-08
og_description: C# のバーコードジェネレータ例でバーコードを素早くリサイズする方法。バーの高さを調整し、PNG ファイルとして保存し、一般的な落とし穴を回避します。
og_image_alt: Screenshot showing a resized barcode generated with C# code
og_title: C#でバーコードのサイズを変更する方法 – ステップバイステップのジェネレータ例
schemas:
- author: Aspose
  dateModified: '2026-10-08'
  description: Learn how to resize barcode images with a C# barcode generator example,
    adjusting bar height from 30 px to 60 px in just a few lines of code.
  headline: How to resize barcode using a barcode generator example in C#
  type: TechArticle
- description: Learn how to resize barcode images with a C# barcode generator example,
    adjusting bar height from 30 px to 60 px in just a few lines of code.
  name: How to resize barcode using a barcode generator example in C#
  steps:
  - name: Open each PNG in an image viewer and verify the pixel dimensions (e.g.,
      150 × 30 px vs. 150 × 60 px).
    text: Open each PNG in an image viewer and verify the pixel dimensions (e.g.,
      150 × 30 px vs. 150 × 60 px).
  - name: Print the images at 100 % scale.
    text: Print the images at 100 % scale.
  - name: Scan with a handheld barcode scanner or a mobile app. The decoded data should
      be
    text: Scan with a handheld barcode scanner or a mobile app. The decoded data should
      be
  type: HowTo
tags:
- barcode
- C#
- image processing
title: C# のバーコードジェネレータ例を使用してバーコードのサイズを変更する方法
url: /ja/python-java/general/how-to-resize-barcode-using-a-barcode-generator-example-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# C# のバーコードジェネレータ例でバーコードのサイズを変更する方法

.NET プロジェクトで **バーコードのサイズ変更** が必要な場合、本ガイドでは完全な解決策を示します。**C# のバーコードジェネレータ例** を使って、バーの高さを 30 px から 60 px に変更し、各バージョンを PNG ファイルとして保存する手順を簡潔に解説します。

バーコードのサイズ変更は、同じデータをレシート、ラベル、商品ページなどで異なる視覚スケールで表示する必要があるときに頻繁に求められます。外部エディタでラスタ画像を編集する代わりに、プログラム上でバーコードの寸法を調整すれば、データの完全性を保ったまま対応できます。

このチュートリアルで学べること：

* DataBar Omni‑Directional バーコードジェネレータのセットアップ方法  
* X‑dimension とバー高さパラメータの変更方法  
* 高さが異なる 2 つの画像の保存方法  
* バー高さを変更するときの仕組みと注意すべきエッジケースの理解  

> **Prerequisite** – .NET 開発環境（Visual Studio 2022 以降）と、`BarcodeGenerator`、`EncodeTypes`、`BarCodeImageFormat` を提供するバーコードライブラリがインストールされていること。コードは 2026 年 10 月時点の最新バージョンで動作します。

## C# のバーコードジェネレータ例に必要な前提条件

開始する前に、以下を確認してください。

| 項目 | 理由 |
|------|------|
| .NET 6.0 SDK 以上 | サンプルで使用するランタイムと言語機能を提供します。 |
| バーコードライブラリ（例: Aspose.BarCode、Dynamsoft、または `BarcodeGenerator` を公開している任意のライブラリ） | `EncodeTypes.DatabarOmniDirectional` 列挙体と画像エクスポートメソッドを提供します。 |
| 書き込み可能なフォルダー（例: `C:\Temp\Barcodes\`） | サンプルは PNG ファイルをこの場所に保存します。 |
| 基本的な C# の知識 | クラス、プロパティ、文字列補間に慣れていることを前提としています。 |

まだインストールしていない場合は、NuGet でライブラリを導入してください。

```bash
dotnet add package Aspose.BarCode
```

実際に使用しているパッケージ名に置き換えてください。以下に示す API は多くのバーコード SDK で共通です。

## バーコードのサイズ変更 – 手順 1: ジェネレータを作成

まず、目的のシンボロジーとデータペイロードを指定して `BarcodeGenerator` のインスタンスを生成します。この例では **DataBar Omni‑Directional** バーコードを生成し、GTIN‑14 の値をエンコードします。

```csharp
using Aspose.BarCode.Generation;

// Step 1: Create a DataBar Omni‑Directional barcode generator with the desired data
BarcodeGenerator generator = new BarcodeGenerator(
    EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");
```

**ポイント:** `EncodeTypes.DatabarOmniDirectional` 列挙体は、使用するバーコード規格をライブラリに指示します。データ文字列は GS1 アプリケーション識別子 `(01)` に続く 14 桁の GTIN で、国際的な取引標準に準拠しています。

## バーコードのサイズ変更 – 手順 2: モジュール幅と初期バー高さを定義

バーコードの視覚サイズは以下の 2 つのパラメータで決まります。

* **X‑dimension** – 最小バー（モジュール）の幅。ピクセルまたはミリメートルで指定します。  
* **Bar height** – バーの垂直長さ。

保存前にこれらの値を設定すれば、生成される画像が期待通りの寸法になります。

```csharp
// Step 2: Define the X‑dimension (module width) and set the bar height to 30 px
generator.Parameters.Barcode.XDimension.Pixels = 2;   // 2 px per module
generator.Parameters.Barcode.BarHeight.Pixels = 30; // 30 px tall bars
```

**解説:** X‑dimension を 2 px に設定すると、コンパクトながら信頼性の高いスキャンが可能なバーコードになります。30 px の高さは小さなラベルでよく使われるデフォルトです。必要に応じて、密度の高いパターンや間隔の広いパターンを作るために、X‑dimension を高さとは独立に調整できます。

## バーコードのサイズ変更 – 手順 3: 最初の画像（30 px 高さ）を保存

バーコードを PNG ファイルとしてエクスポートします。`Save` メソッドはファイルパスと画像フォーマット列挙体を受け取ります。

```csharp
// Step 3: Save the barcode image with a 30 px height
string outputPath = @"C:\Temp\Barcodes\";
generator.Save($"{outputPath}DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);
```

**結果:** `DatabarBarHeight30Pixels.png` には高さ 30 px のバーコードが保存されます。任意の画像ビューアで開き、寸法を確認してください。

## バーコードのサイズ変更 – 手順 4: バー高さを 60 px に変更

大きめのバージョンを作成するには、`BarHeight` プロパティを変更するだけです。ジェネレータは同じデータと X‑dimension を再利用するため、パターンは変わらず、視覚的なサイズだけが変わります。

```csharp
// Step 4: Change the bar height to 60 px for a larger barcode
generator.Parameters.Barcode.BarHeight.Pixels = 60;
```

**なぜ機能するか:** バーコード描画エンジンは各バーのジオメトリをリアルタイムで計算します。次の `Save` 呼び出しの前に高さプロパティを更新すると、新しい寸法で再ラスタライズされます。

## バーコードのサイズ変更 – 手順 5: 2 番目の画像（60 px 高さ）を保存

```csharp
// Step 5: Save the barcode image with a 60 px height
generator.Save($"{outputPath}DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);
```

これで、30 px と 60 px の 2 つの PNG ファイルが用意できました。ラベルサイズに応じて使い分けてください。

## バーコードジェネレータ例 C# の完全ソースコード

以下は実行可能な完全プログラムです。新しいコンソールプロジェクトに貼り付けてすぐにテストできます。

```csharp
using System;
using Aspose.BarCode.Generation;

namespace BarcodeResizeDemo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Create the generator with DataBar Omni‑Directional symbology
            BarcodeGenerator generator = new BarcodeGenerator(
                EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");

            // 2️⃣ Set X‑dimension and initial bar height (30 px)
            generator.Parameters.Barcode.XDimension.Pixels = 2;
            generator.Parameters.Barcode.BarHeight.Pixels = 30;

            // 3️⃣ Define output folder (ensure it exists)
            string outputPath = @"C:\Temp\Barcodes\";
            System.IO.Directory.CreateDirectory(outputPath);

            // 4️⃣ Save the 30 px version
            generator.Save($"{outputPath}DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);
            Console.WriteLine("Saved 30 px barcode.");

            // 5️⃣ Increase bar height to 60 px
            generator.Parameters.Barcode.BarHeight.Pixels = 60;

            // 6️⃣ Save the 60 px version
            generator.Save($"{outputPath}DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);
            Console.WriteLine("Saved 60 px barcode.");
        }
    }
}
```

**コンソールへの期待出力:**

```
Saved 30 px barcode.
Saved 60 px barcode.
```

実行後、2 つの PNG ファイルを開いて視覚的な違いを確認してください。どちらも同じ GTIN‑14 をエンコードしており、高さが異なってもスキャン結果は同一です。

## バー高さを変更してもスキャンに支障がない理由

バーコードリーダーは光と暗のモジュールパターンを読み取ります。**X‑dimension** がスキャナの許容範囲（通常 0.5 mm〜2 mm）内に収まっていれば、バー高さを変えても可読性に影響しません。ライブラリは自動的にモジュールをスケーリングし、必要なクワイエットゾーンやアラインメントパターンを保持します。

## よくある落とし穴と回避策

| 落とし穴 | 対処方法 |
|---------|----------|
| **出力フォルダーが存在しない** | `Directory.CreateDirectory(outputPath)` を `Save` 前に呼び出す。 |
| **X‑dimension が不適切でスキャンがぼやける** | 多くのプリンタで 1 px〜4 px の範囲に収め、実機スキャナでテストする。 |
| **非常に大きなバーコードをラスタ形式で出力** | ピクセル化を防ぐために `BarCodeImageFormat.Svg` に切り替える。 |
| **2 回目の保存前に `BarHeight` をリセットし忘れる** | `Save` を再度呼び出す **前に** 新しい高さを必ず代入する。 |

## プロのコツ: ループで複数サイズを生成

30 px、45 px、60 px など、複数の高さが必要な場合は `foreach` ループで重複コードを削減できます。

```csharp
int[] heights = { 30, 45, 60 };
foreach (int h in heights)
{
    generator.Parameters.Barcode.BarHeight.Pixels = h;
    generator.Save($"{outputPath}DatabarBarHeight{h}Pixels.png", BarCodeImageFormat.Png);
    Console.WriteLine($"Saved {h} px barcode.");
}
```

このパターンは商品カタログのバッチ処理に最適です。

## エッジケース: 画像形式と DPI 設定の違い

* **SVG 出力** – `BarCodeImageFormat.Svg` を使用すれば、品質劣化なしで任意のサイズに拡大可能です。  
* **高 DPI PNG** – `generator.Parameters.Image.DpiX` と `DpiY` を 300 または 600 に設定すれば印刷向け画像が作れます。バー高さはピクセル単位で測定されるため、比例して増やす必要があります。  
* **非標準シンボロジー** – QR コードなど一部のタイプは `BarHeight` ではなく別の `Size` プロパティを持ちます。該当ライブラリのドキュメントを参照してください。

## リサイズしたバーコードのテスト手順

1. 各 PNG を画像ビューアで開き、ピクセル寸法（例: 150 × 30 px と 150 × 60 px）を確認する。  
2. 100 % スケールで印刷する。  
3. ハンドヘルドスキャナまたはモバイルアプリでスキャンし、デコードされたデータが一致することを確認する。

## 次に学ぶべきことは？

以下のチュートリアルは、本ガイドで示したテクニックを応用した関連トピックを扱っています。各リソースには完全なコード例とステップバイステップの解説が含まれており、API の追加機能習得や別実装アプローチの探求に役立ちます。

- [C# のバーコードジェネレータ例 – 幅と高さの設定](/barcode/english/python-java/general/barcode-generator-example-in-c-set-width-and-height/)
- [Aspose.BarCode を使った C# のバーコードサイズ変更 – 手順別ガイド](/barcode/english/python-java/general/how-to-resize-barcode-in-c-with-aspose-barcode-step-by-step/)
- [Barcode Generator C# でバーコード画像を保存する方法 – 手順別ガイド](/barcode/english/python-java/general/how-to-save-barcode-images-with-barcode-generator-c-step-by/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}