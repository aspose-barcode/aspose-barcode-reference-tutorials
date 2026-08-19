---
category: general
date: 2026-08-19
description: C# と Aspose.BarCode を使用してデータバー PNG ファイルを作成します。データバー画像の生成方法、データバー パラメータの設定方法、PNG
  出力の保存方法を学びます。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create databar png
- how to generate databar
- configure databar parameters
language: ja
lastmod: 2026-08-19
og_description: Aspose.BarCode を使用して C# でデータバーの PNG ファイルを作成します。このチュートリアルでは、データバー画像の生成方法、X
  ディメンションやアスペクト比などのデータバー パラメータの設定方法、印刷やウェブで使用できる高品質 PNG ファイルの保存方法を順を追って解説します。
og_image_alt: create databar PNG example
og_title: C#でデータバーPNG画像を作成する – ステップバイステップガイド
schemas:
- author: Aspose
  dateModified: '2026-08-19'
  description: Create databar PNG files in C# with Aspose.BarCode. Learn how to generate
    databar images, configure databar parameters, and save PNG output.
  headline: How to create databar PNG images with C# and Aspose.BarCode
  type: TechArticle
tags:
- barcode
- databar
- C#
- PNG
- Aspose.BarCode
title: C# と Aspose.BarCode を使用してデータバー PNG 画像を作成する方法
url: /ja/python-java/general/how-to-create-databar-png-images-with-c-and-aspose-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# C# と Aspose.BarCode を使用して databar PNG 画像を作成する方法

.NET アプリケーションで **databar PNG** ファイルを作成する必要がある場合、本ガイドで具体的な手順を示します。スタック型全方向 DataBar コードを生成し、主要パラメータを設定し、異なるアスペクト比の PNG ファイルを 2 つ保存する、完全に実行可能なサンプルをご覧いただけます。

DataBar 画像の生成は単にメソッドを呼び出すだけではありません。印刷やスキャンの仕様を満たすために、X‑dimension（モジュール幅）やアスペクト比など **databar パラメータを設定** する必要があります。このチュートリアルの最後までに、実際のシナリオで信頼性のある **databar グラフィックを生成する方法** が理解できるようになります。

## 前提条件

- .NET 6.0 以降（コードは .NET Framework 4.7+ でも動作します）
- Visual Studio 2022 または任意の C# 対応 IDE
- **Aspose.BarCode for .NET** の有効なライセンス（無料評価版でもテストは可能）
- C# の基本的な構文に慣れていること

> **プロのコツ:** まだライセンスをお持ちでない場合は、Aspose ポータルから一時的な評価キーをリクエストできます。API の動作は同じで、変わるのは透かしだけです。

## Step 1: Install the Aspose.BarCode NuGet package

Visual Studio でプロジェクトを開き、ソリューションを右クリックして **Manage NuGet Packages** を選択します。`Aspose.BarCode` を検索し、最新の安定版をインストールします。

```bash
dotnet add package Aspose.BarCode
```

このコマンドにより `Aspose.BarCode` アセンブリがプロジェクトに追加され、`BarcodeGenerator` クラスが利用可能になります。

## Step 2: Initialize the barcode generator for a stacked omnidirectional DataBar

`BarcodeGenerator` コンストラクタは 2 つの引数を受け取ります：バーコードの種類と生データ文字列です。スタック型全方向 DataBar を使用する場合は `EncodeTypes.DatabarStackedOmniDirectional` を指定します。

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

namespace DatabarPngDemo
{
    class Program
    {
        static void Main(string[] args)
        {
            // Step 2: Initialize the generator with the desired DataBar type
            BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
                EncodeTypes.DatabarStackedOmniDirectional,
                "(01)12345678901231"); // GS1 Application Identifier for a 14‑digit GTIN
```

**重要ポイント:** `EncodeTypes.DatabarStackedOmniDirectional` 定数は、任意の向きから読み取れるバーコードを生成するようライブラリに指示します。これは小売棚ラベルに最適です。

## Step 3: Configure the X‑dimension (module width) in pixels

X‑dimension は最小バー要素のサイズを制御します。ピクセル単位で設定することで、最終画像サイズを正確にコントロールできます。

```csharp
            // Step 3: Define the X‑dimension (module width) in pixels
            barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

**2 ピクセル** の値は、ほとんどのラベルプリンターで可読性とコンパクトさのバランスが取れた設定です。必要に応じてモジュールを大きくしたり小さくしたりしてください。

## Step 4: Set the first aspect ratio and save the PNG

アスペクト比はスタック型 DataBar の高さに影響します。アスペクト比 **15** は比較的短いバーコードを生成し、**30** はより高くなります。

```csharp
            // Step 4: Set an aspect ratio of 15 and save the image
            barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 15;
            barcodeGenerator.Save("DatabarAspectRatio15.png", BarCodeImageFormat.Png);
```

`Save` メソッドは生成したバーコードを PNG ファイルとして書き出します。PNG はロスレス形式なので、バーコードスキャナが必要とする鮮明なエッジが保持されます。

## Step 5: Change the aspect ratio and save a second PNG

同じ `BarcodeGenerator` インスタンスを再利用し、アスペクト比を変更するだけでバリエーションを作成できます。

```csharp
            // Step 5: Change the aspect ratio to 30 and save a new image
            barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 30;
            barcodeGenerator.Save("DatabarAspectRatio30.png", BarCodeImageFormat.Png);
        }
    }
}
```

これで 2 つの PNG ファイル、`DatabarAspectRatio15.png` と `DatabarAspectRatio30.png` が作成され、それぞれ異なる視覚密度を持ちます。

## Step 6: Verify the output

生成された PNG ファイルを任意の画像ビューアで開きます。クリーンで高コントラストな DataBar バーコードが表示されるはずです。スマートフォンのバーコードスキャナで画像を読み取ると、両方のアスペクト比が元の GTIN 値 `12345678901231` に正しくデコードされることが確認できます。

![create databar PNG example](databar_example.png)

*上の画像は 2 つの PNG ファイルを横に並べたものです。左側がアスペクト比 15、右側がアスペクト比 30 を使用しています。*

## Common variations and edge cases

| シナリオ | 変更点 | 理由 |
|----------|----------------|--------|
| **異なるデータ** | `(01)12345678901231` の文字列を任意の有効な GS1 アプリケーション識別子とデータに置き換える | 製品 ID、シリアル番号などをエンコードできるようにするため |
| **高解像度** | `XDimension.Pixels` を 3 または 4 に増やす | 大きなサイズで印刷したり、遠距離からスキャンする場合に必要 |
| **他の DataBar タイプ** | `EncodeTypes.DatabarStacked` または `EncodeTypes.DatabarExpanded` を使用する | ラベルレイアウトに最適なタイプを選択できる |
| **透明背景** | `BarCodeImageFormat.Png` と共に `barcodeGenerator.Save(..., BarCodeImageFormat.Png, new ImageOptions { BackgroundColor = Color.Transparent })` を渡す | カラフルなラベル上にバーコードを重ねる際に便利 |

> **注意点:** X‑dimension を 1 ピクセル未満に設定すると、画像がぼやけたように見えるバーコードが生成される可能性があります。

## What Should You Learn Next?

以下のチュートリアルは、本ガイドで示した手法を基にした、密接に関連するトピックをカバーしています。各リソースには、ステップバイステップの解説と完全な動作コード例が含まれており、追加の API 機能を習得したり、プロジェクトで代替実装アプローチを検討したりするのに役立ちます。

- [How to Generate and Adjust Barcode Height for One-Dimensional Databar using Aspose.BarCode for .NET](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-barcode-height-adjustment/)
- [Create One-Dimensional Databar GS1 Encoding with Aspose.BarCode](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-gs1-encoding/)
- [Generate Aspose.BarCode Databar barcode using .NET API – Row & Column Configuration](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-row-column-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}