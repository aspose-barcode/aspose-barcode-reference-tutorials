---
category: general
date: 2026-10-05
description: C#でバーコードPNGを作成し、スタック型DataBar全方向バーコードのアスペクト比を15に設定する方法を学びます。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode png
- how to set aspect ratio
- set aspect ratio 15
language: ja
lastmod: 2026-10-05
og_description: C#でバーコードPNGを作成し、数ステップでスタックされたDataBar全方向バーコードのアスペクト比15の設定方法を学びましょう。
og_image_alt: Screenshot showing a generated barcode PNG with aspect ratio 15
og_title: C#でバーコードPNGを作成 – アスペクト比15の設定チュートリアル
schemas:
- author: Aspose
  dateModified: '2026-10-05'
  description: Create barcode PNG in C# and learn how to set aspect ratio 15 for stacked
    DataBar omnidirectional barcodes.
  headline: How to create barcode PNG with a custom aspect ratio in C#
  type: TechArticle
tags:
- barcode generation
- C#
- Aspose.BarCode
title: C#でカスタムアスペクト比のバーコードPNGを作成する方法
url: /ja/python-java/general/how-to-create-barcode-png-with-a-custom-aspect-ratio-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# C# でカスタムアスペクト比のバーコード PNG を作成する方法

C# で **バーコード PNG を作成** したい場合、このガイドではスタック型 DataBar オムニディレクショナルバーコードのアスペクト比を 15 に設定する方法を示します。各 API 呼び出しを順に解説し、アスペクト比が重要な理由を説明し、任意の .NET プロジェクトにそのまま組み込める完全な実行可能サンプルを提供します。

バーコード画像の生成は、在庫管理システム、出荷ラベル、店舗の POS アプリケーションなどで一般的な要件です。このチュートリアルを終える頃には、取引先が求める正確なビジュアル仕様を満たす PNG ファイルが手に入ります。外部ツールや手動での画像編集は不要です—コードだけで完結します。

## 前提条件

開始する前に、以下が揃っていることを確認してください。

* .NET 6.0 以降（例では .NET 6 を使用していますが、.NET 5+ でも動作します）
* Visual Studio 2022（または .NET をサポートする任意の IDE）
* **Aspose.BarCode for .NET** NuGet パッケージ  
  ```bash
  dotnet add package Aspose.BarCode
  ```
* PNG ファイルを保存したいフォルダーへの書き込み権限

これらの要件は最小限です。同じコードは .NET Core、.NET Framework、またはコンソール アプリケーションでも動作します。

## Aspose.BarCode でバーコード PNG を作成する

最初のステップは、正しいバーコードタイプで `BarcodeGenerator` クラスのインスタンスを作成することです。この例では `EncodeTypes.DatabarStackedOmniDirectional` を使用します。これは任意の方向から読み取れるスタック型 DataBar を生成します。

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

// Step 1: Initialize the generator with sample data
BarcodeGenerator generator = new BarcodeGenerator(
    EncodeTypes.DatabarStackedOmniDirectional,
    "(01)12345678901231");
```

*なぜ重要か:* コンストラクタは **バーコードシンボロジー** と **データ文字列** の 2 つの引数を受け取ります。DataBar 形式は GS1 アプリケーション識別子を期待するため、サンプル データは `(01)` で始まります。

## スタック型 DataBar のアスペクト比を設定する方法

DataBar の視覚的な幅は **アスペクト比** プロパティで制御されます。比率が高いほどバーが太くなり、低解像度プリンターでもスキャン信頼性が向上します。

```csharp
// Step 2: Define the module width (X‑dimension) in pixels
generator.Parameters.Barcode.XDimension.Pixels = 2;
```

`XDimension` は単一モジュール（最小のバーまたはスペース）のサイズを定義します。これを 2 px に保つことで、ほとんどのラベルプリンターに適した高密度で鮮明な画像が得られます。

## アスペクト比 15 を設定 – コード解説

ここで **アスペクト比 15 を設定** する要件を適用します。これが本チュートリアルの核心であり、必要な正確な API 呼び出しを示します。

```csharp
// Step 3: Set the DataBar aspect ratio to 15 for a wider appearance
generator.Parameters.Barcode.DataBar.AspectRatio = 15;
```

*なぜ 15 か？* スタック型 DataBar のデフォルトアスペクト比は 12 です。これを 15 に上げると各バーの幅が 25 % 拡大され、物流プロバイダーが求める「より広いバーコード」で高速スキャンが可能になることが多いです。

## バーコードを PNG として保存する

ジェネレータの設定が完了したら、最後に画像をディスクに書き出します。`Save` メソッドはファイルパスと画像形式列挙体を受け取ります。

```csharp
// Step 4: Save the generated barcode as a PNG image
string outputPath = @"C:\Barcodes\DatabarAspectRatio15.png";
generator.Save(outputPath, BarCodeImageFormat.Png);
```

PNG 形式はロスレス品質を保持し、どのディスプレイやプリンターでもバーコードが設計通りに表示されます。

## 完全なサンプルと期待される出力

以下はコンソール アプリの `Main` メソッドに貼り付けられるフル プログラムです。上記の手順すべてを含み、簡単な検証メッセージも出力します。

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        // Initialize the generator with stacked DataBar (omnidirectional) and sample GS1 data
        BarcodeGenerator generator = new BarcodeGenerator(
            EncodeTypes.DatabarStackedOmniDirectional,
            "(01)12345678901231");

        // Define the X‑dimension (module width) in pixels
        generator.Parameters.Barcode.XDimension.Pixels = 2;

        // Set the DataBar aspect ratio to 15 – this is the key to a wider barcode
        generator.Parameters.Barcode.DataBar.AspectRatio = 15;

        // Choose a folder you have write access to
        string outputPath = @"C:\Barcodes\DatabarAspectRatio15.png";

        // Save the barcode as a PNG file
        generator.Save(outputPath, BarCodeImageFormat.Png);

        Console.WriteLine($"Barcode PNG created at: {outputPath}");
    }
}
```

**期待される出力**

プログラムを実行すると `DatabarAspectRatio15.png` という名前のファイルが作成され、クリアで幅の広いスタック型 DataBar バーコードが格納されます。PNG を開くと、GS1 DataBar 仕様に準拠しつつ横方向に伸びたバーコードが確認できるはずです。

![Barcode PNG with aspect ratio 15](barcode-aspect15.png)

*画像の代替テキスト:* **アスペクト比 15 のスタック型 DataBar を示すバーコード PNG を作成**

### ヒントとよくある落とし穴

| 状況 | 推奨事項 |
|-----------|----------------|
| **画像がぼやけて見える** | `XDimension.Pixels` を 3 px 以上に増やす。ただし、全体の画像サイズは 500 px 未満に抑えてファイルが大きくなりすぎないように。 |
| **スキャナーがコードを読めない** | データ文字列が GS1 形式（`(01)` プレフィックス）に従っているか確認。また、プリンター解像度が最低 300 dpi であることを確認。 |
| **別のファイル形式が必要** | `BarCodeImageFormat.Png` を `Jpeg`、`Bmp`、`Gif` のいずれかに置き換える。API は主要なラスタ形式すべてをサポート。 |
| **Web アプリケーションで実行** | `generator.Save(Stream, BarCodeImageFormat.Png)` を使用して、ファイルシステムに書き込まず HTTP 応答に直接書き出す。 |

### サンプルの拡張例

* **1 つの画像に複数バーコード**: 追加の `BarcodeGenerator` インスタンスを作成し、`Graphics` を使って単一の `Bitmap` に描画。 |
* **ヒューマンリーダブルテキストの追加**: `generator.Parameters.Caption.Visible = true` に設定し、`generator.Parameters.Caption.Font` でフォントをカスタマイズ。 |
* **動的アスペクト比**: 設定ファイルやデータベースから比率値を取得し、実行時に幅を変化させるバーコードを生成。 |

## 結論

本チュートリアルでは、C# で **バーコード PNG を作成** し、スタック型 DataBar オムニディレクショナルバーコードのアスペクト比を正確に **15 に設定** する方法を学びました。完全な実行可能コードはすべての必須 API 呼び出しを示し、各設定がなぜ重要かを解説し、実務での展開に役立つ実践的なヒントも提供しています。

次は、**他のバーコードタイプ（例: QR Code や Code 128）** のアスペクト比設定方法や、オンデマンドでバーコード画像を返す ASP .NET Core サービスへの統合を検討してみてください。コーディングを楽しんでください！

## 次に学ぶべきこと

以下のチュートリアルは、本ガイドで示した手法を応用した関連トピックを扱っています。各リソースには完全な動作コード例とステップバイステップの解説が含まれており、API の追加機能習得や代替実装アプローチの探求に役立ちます。

- [How to create databar PNG images with C# and Aspose.Barcode](/barcode/english/python-java/general/how-to-create-databar-png-images-with-c-and-aspose-barcode/)
- [How to create databar stacked barcode in C# with Aspose.Barcode](/barcode/english/python-java/general/how-to-create-databar-stacked-barcode-in-c-with-aspose-barco/)
- [Customize databar stacked omnidirectional Aspect Ratio in .NET](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-aspect-ratio-customization/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}