---
category: general
date: 2026-10-02
description: C#でスタック型データバーコードをすばやく作成します。XDimensionの設定、アスペクト比の調整、そしてバーコードジェネレータでPNG画像をエクスポートする方法を学びましょう。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create stacked databars barcode
- C# barcode generator
- DataBar stacked omnidirectional
- barcode aspect ratio
- XDimension pixel size
- BarCodeImageFormat PNG
language: ja
lastmod: 2026-10-02
og_description: C#でスタックされたデータバーのバーコードを作成し、完全なコード例を提供します。XDimensionを調整し、アスペクト比を変更し、数行でPNGファイルを保存できます。
og_image_alt: Screenshot showing a create stacked databars barcode example generated
  with C#
og_title: C#でスタックされたデータバーのバーコードを作成 – クイックチュートリアル
schemas:
- author: Aspose
  dateModified: '2026-10-02'
  description: Create stacked databars barcode in C# quickly. Learn to set XDimension,
    adjust aspect ratio, and export PNG images with a barcode generator.
  headline: Create stacked databars barcode in C# – step‑by‑step guide
  type: TechArticle
tags:
- barcode
- C#
- DataBar
- Aspose
- image generation
title: C#でスタックされたデータバーのバーコードを作成する – ステップバイステップガイド
url: /ja/python-java/general/create-stacked-databars-barcode-in-c-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# C# でスタック型データバーコードを作成する – ステップバイステップガイド

.NET プロジェクトで **スタック型データバーコード** を作成する必要がある場合、このチュートリアルで具体的な手順を示します。X‑dimension の設定、アスペクト比の切り替え、結果を PNG ファイルとして保存する方法を、すべて Aspose.BarCode ライブラリを使って学びます。

スタック型 DataBar バーコードの生成には、複雑なグラフィック パイプラインは必要ありません。このガイドの最後までに、異なるアスペクト比を示す 2 つのすぐに使用できる PNG 画像が手に入り、スキャンの信頼性にこれらのパラメータがなぜ重要かが理解できるようになります。

## 必要なもの

- .NET 6.0 以降（コードは .NET Framework 4.6+ でも動作します）
- Visual Studio 2022 または任意の C# IDE
- **Aspose.BarCode for .NET** NuGet パッケージ  
  ```bash
  dotnet add package Aspose.BarCode
  ```
- PNG ファイルを保存するフォルダーへの書き込み権限

## 手順 1: プロジェクトのセットアップと名前空間のインポート

新しいコンソール アプリケーションを作成する（または既存プロジェクトにコードを追加する）し、必要な名前空間をインポートします。

```csharp
using System;
using Aspose.BarCode.Generation;   // BarcodeGenerator lives here
using Aspose.BarCode;               // BarCodeImageFormat enum
```

> **なぜ重要か:** `Aspose.BarCode.Generation` は `BarcodeGenerator` クラスを提供し、`Aspose.BarCode` には画像保存に使用される `BarCodeImageFormat` 列挙型が含まれています。

## 手順 2: スタック型全方向 DataBar 用ジェネレータの初期化

`EncodeTypes.DatabarStackedOmniDirectional` の値はスタック型 DataBar シンボルを選択します。データ文字列は GS1 アプリケーション識別子 (AI) 形式に従う必要があります；ここではダミーの GTIN‑14 値を使用しています。

```csharp
// Initialise a generator for a stacked omnidirectional DataBar barcode
var barcodeGen = new BarcodeGenerator(
    EncodeTypes.DatabarStackedOmniDirectional,
    "(01)12345678901231");
```

> **なぜ重要か:** 選択したエンコードタイプはライブラリに *スタック* バーコードを描画させます。これは、垂直方向のスペースが限られた高密度ラベルにとって重要です。

## 手順 3: モジュール（X‑dimension）サイズをピクセル単位で定義

X‑dimension は最小バー（“モジュール”）の幅を制御します。2 ピクセルの値はほとんどの画面解像度出力でうまく機能します。

```csharp
// Set the X‑dimension to 2 pixels (module width)
barcodeGen.Parameters.Barcode.XDimension.Pixels = 2;
```

> **なぜ重要か:** スキャナーはモジュール幅を測定の基本単位として解釈します。値が小さすぎると印刷がぼやけ、逆に大きすぎるとスペースが無駄になります。

## 手順 4: アスペクト比 15 で最初の画像を保存

`AspectRatio` プロパティは各スタック セグメントの高さと幅の関係に影響します。アスペクト比 15 は小売アプリケーションで一般的なデフォルトです。

```csharp
// Apply aspect ratio 15 and save the first PNG
barcodeGen.Parameters.Barcode.DataBar.AspectRatio = 15;
barcodeGen.Save("DatabarAspectRatio15.png", BarCodeImageFormat.Png);
```

> **なぜ重要か:** アスペクト比が低いとバーコードが平坦になり、特定のラベル素材上でスキャンしやすくなる場合があります。PNG 形式はテスト用にロスレス品質を保持します。

## 手順 5: アスペクト比を 30 に変更し、2 番目の画像を保存

アスペクト比を上げると各スタック セグメントが高くなり、低コントラストの背景でのスキャン信頼性が向上することがあります。

```csharp
// Apply aspect ratio 30 and save the second PNG
barcodeGen.Parameters.Barcode.DataBar.AspectRatio = 30;
barcodeGen.Save("DatabarAspectRatio30.png", BarCodeImageFormat.Png);
```

> **なぜ重要か:** 小売業者や物流パートナーによっては特定のバーコード寸法が求められることがあります。両バージョンを用意することで、スキャン性能をすぐに比較できます。

## 完全な実行可能サンプル

`Program.cs` にコピー＆ペーストできる完全なプログラムです。Aspose.BarCode NuGet パッケージをインストールすれば、変更なしでコンパイル・実行できます。

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

namespace StackedDataBarDemo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Initialise the generator for stacked omnidirectional DataBar
            var barcodeGen = new BarcodeGenerator(
                EncodeTypes.DatabarStackedOmniDirectional,
                "(01)12345678901231");

            // 2️⃣ Define the module (X‑dimension) size in pixels
            barcodeGen.Parameters.Barcode.XDimension.Pixels = 2;

            // 3️⃣ Save first image with aspect ratio 15
            barcodeGen.Parameters.Barcode.DataBar.AspectRatio = 15;
            barcodeGen.Save("DatabarAspectRatio15.png", BarCodeImageFormat.Png);
            Console.WriteLine("Saved DatabarAspectRatio15.png");

            // 4️⃣ Save second image with aspect ratio 30
            barcodeGen.Parameters.Barcode.DataBar.AspectRatio = 30;
            barcodeGen.Save("DatabarAspectRatio30.png", BarCodeImageFormat.Png);
            Console.WriteLine("Saved DatabarAspectRatio30.png");
        }
    }
}
```

### 期待される出力

プログラムを実行すると、実行フォルダーに 2 つのファイルが作成されます：

| ファイル名                     | アスペクト比 | 視覚的説明 |
|-------------------------------|--------------|--------------------|
| `DatabarAspectRatio15.png`    | 15           | 短く、平坦なスタック型バーコード |
| `DatabarAspectRatio30.png`    | 30           | 高く、より細長いスタック型バーコード |

任意の画像ビューアで PNG ファイルを開き、バーコードが正しく描画されていることを確認できます。

![スタック型データバーコード作成例](placeholder-image.png){alt="スタック型データバーコード作成例"}

## よくある質問とエッジケース

| 質問 | 回答 |
|----------|--------|
| **異なる X‑dimension を使用できますか？** | はい。典型的な値は 1 から 4 ピクセルの範囲です。値が大きくなるとバーコードのサイズは大きくなりますが、低解像度プリンターでの読み取り易さが向上する場合があります。 |
| **別のシンボルが必要な場合はどうすればよいですか？** | `EncodeTypes.DatabarStackedOmniDirectional` を別の `EncodeTypes` の値に置き換えます。例えば `DatabarStacked`（非全方向）や `DatabarLimited` などです。 |
| **出力形式はどう変更しますか？** | `Save` 呼び出しで `BarCodeImageFormat.Jpeg`、`Gif`、または `Bmp` を使用します。 |
| **GTIN‑14 形式は必須ですか？** | DataBar シンボルは、適切な AI（例: GTIN‑14 の場合は `(01)`）でプレフィックスされた数値文字列を期待します。使用ケースに合わせてデータを調整してください。 |
| **DPI 設定はどうですか？** | ジェネレータは `Resolution` プロパティを尊重します。高解像度印刷の場合は、`barcodeGen.Parameters.ImageResolution.DpiX` と `DpiY` を適切に設定してください。 |

## プロのコツ

- **バッチ生成:** 保存ロジックをループで囲み、GTIN のリストを渡すことで、数千のバーコードを自動的に生成します。
- **バリデーション:** 保存前に `barcodeGen.Validate()` を使用して、データ不正を早期に検出します。
- **パフォーマンス:** 同じ `BarcodeGenerator` インスタンスを再利用（パラメータだけ変更）する方が、画像ごとに新しいオブジェクトを作成するより高速です。

## 次のステップ

カスタムアスペクト比で **スタック型データバーコード** を作成できるようになったので、以下を検討してください：

- バーコードの下に人が読めるテキストを追加する（`barcodeGen.Parameters.Barcode.CodeText`）。
- 印刷用ラベルシート用に **PDF** へエクスポートする（`BarCodeImageFormat.Pdf`）。
- ジェネレータを Web API に統合し、オンデマンドでバーコードを提供する。
- 他の **二次キーワード**（例: *C# barcode generator*、*barcode aspect ratio*）を試して、特定ハードウェア向けに実装を微調整する。

コーディングを楽しんで、Aspose.BarCode が C# バーコードプロジェクトにもたらす柔軟性を活用してください！

## 次に学ぶべきことは？

以下のチュートリアルは、本ガイドで示した手法を基にした密接に関連するトピックをカバーしています。各リソースには、ステップバイステップの解説付きの完全なコード例が含まれており、追加の API 機能を習得し、独自プロジェクトで代替実装アプローチを検討するのに役立ちます。

- [C# でデータバー スタック型バーコードを作成する – ステップバイステップガイド](/barcode/english/python-java/general/create-databar-stacked-barcode-in-c-step-by-step-guide/)
- [C# でデータバー スタック型全方向バーコード – 完全ガイド](/barcode/english/python-java/general/databar-stacked-omnidirectional-barcode-in-c-complete-guide/)
- [C# と Aspose.BarCode でデータバー PNG 画像を作成する方法](/barcode/english/python-java/general/how-to-create-databar-png-images-with-c-and-aspose-barcode/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}