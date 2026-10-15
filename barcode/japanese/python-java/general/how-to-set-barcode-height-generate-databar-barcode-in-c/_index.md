---
category: general
date: 2026-10-12
description: Aspose.BarCode を使用して C# でバーコードの高さを設定し、DataBar バーコードを生成する方法。完全なコード付きのステップバイステップガイドをご覧ください。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to set barcode
- generate barcode c#
- how to create databar
- create databar barcode
- change barcode height
language: ja
lastmod: 2026-10-12
og_description: C#でバーコードの高さを設定し、Aspose.BarCodeを使用してDataBarバーコードを生成する方法。完全なコード、各ステップの重要性、そしてバーコードの高さを変更する方法を学びましょう。
og_image_alt: Screenshot showing how to set barcode height in a C# barcode generator
og_title: C#でバーコードの高さを設定し、DataBarバーコードを生成する方法
schemas:
- author: Aspose
  dateModified: '2026-10-12'
  description: How to set barcode height and generate a DataBar barcode in C# using
    Aspose.BarCode. Follow a step‑by‑step guide with complete code.
  headline: How to set barcode height, generate DataBar barcode in C#
  type: TechArticle
tags:
- barcode
- C#
- Aspose.BarCode
title: C#でバーコードの高さを設定し、DataBarバーコードを生成する方法
url: /ja/python-java/general/how-to-set-barcode-height-generate-databar-barcode-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# バーコードの高さを設定し、C#でDataBarバーコードを生成する方法

プログラムで **how to set barcode** の寸法を設定する必要がある場合、このガイドでは正確な手順を示します。DataBar Omni‑directional バーコードの生成方法、高さの調整方法、そして両方のバージョンを PNG ファイルとして保存する方法を学びます。

レシート、製品ラベル、モバイル画面などにバーコードを組み込む際、バーコードのバー高さを変更することは一般的な要件です。以下の例では、GS1 DataBar シンボルのすべてのバリエーションをサポートする Aspose.BarCode ライブラリを使用しています。

## 本チュートリアルで達成できること

* **how to set barcode** の高さを DataBar Omni‑directional バーコードに設定する  
* **generate barcode c#** コードで、異なる高さの画像を2つ作成する  
* **how to create databar** シンボルの理解と、バー高さが重要な理由  
* **change barcode height** ロジックを、ジェネレータを再作成せずに適用する  

外部ツールは必要なく、Aspose.BarCode の NuGet パッケージと .NET 6 以上のランタイムさえあれば完了します。

## 前提条件

* .NET 6 SDK またはそれ以降がインストールされていること  
* Visual Studio 2022（または任意の C# エディタ）  
* Aspose.BarCode for .NET – `dotnet add package Aspose.BarCode` でインストール  

> **Pro tip:** 商用キーがない場合は Aspose の無料トライアルライセンスを使用してください。API の動作は同じです。

## 手順 1: Aspose.BarCode パッケージのインストール

プロジェクトフォルダーでターミナルを開き、次のコマンドを実行します：

```bash
dotnet add package Aspose.BarCode
```

このパッケージは `Aspose.BarCode` 名前空間を追加し、**generate barcode c#** 画像の生成に使用する `BarcodeGenerator` クラスが含まれます。

## 手順 2: DataBar バーコードジェネレータの作成

**how to set barcode** パラメータの最初の具体的な操作は、目的のシンボルとデータ文字列で `BarcodeGenerator` をインスタンス化することです。

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

// Step 2: Initialize the generator for a DataBar Omni‑directional barcode
var barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarOmniDirectional, // symbology
    "(01)12345678901231");               // GS1 data payload
```

*Why this matters:* `EncodeTypes.DatabarOmniDirectional` はコンパクトで全方向からスキャン可能な DataBar を生成し、小さなラベルに最適です。

## 手順 3: 共通のバーコードパラメータを設定（初期バー高さを含む）

ここで、最初の画像を保存する前に **how to set barcode** の X‑dimension とバー高さを設定します。

```csharp
// Step 3: Configure X‑dimension (module width) and initial bar height
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;    // 2‑pixel modules
barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 30;   // 30‑pixel height
```

X‑dimension は各バーの全体幅を制御します。2 ピクセルの設定は、ほとんどの画面で読みやすく鮮明な画像を生成します。後の **change barcode height** 手順では同じジェネレータを再利用するため、時間とメモリを節約できます。

## 手順 4: 最初のバーコード画像を保存（30 ピクセルの高さ）

```csharp
// Step 4: Save the 30‑pixel barcode image
barcodeGenerator.Save("DatabarHeight30.png", BarCodeImageFormat.Png);
```

ファイル `DatabarHeight30.png` には、30 ピクセルのバー高さを持つ DataBar バーコードが保存されています。

## 手順 5: バー高さだけを 60 ピクセルに変更

**change barcode height** を示すために、`BarHeight` プロパティだけを変更します。他の設定はすべてそのままで、単一のジェネレータから複数サイズを生成する最も効率的な方法です。

```csharp
// Step 5: Update the bar height to 60 pixels
barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 60;
```

## 手順 6: 2 番目のバーコード画像を保存（60 ピクセルの高さ）

```csharp
// Step 6: Save the 60‑pixel barcode image
barcodeGenerator.Save("DatabarHeight60.png", BarCodeImageFormat.Png);
```

これで、バー高さは異なるものの、データと X‑dimension が同一の PNG ファイルが2つ作成されました。

## 完全な実行可能サンプル

以下は、`dotnet new console` で作成した新しいコンソールアプリケーションにコピー＆ペーストしてすぐに実行できる完全なプログラムです。

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        // Initialize the generator for a DataBar Omni‑directional barcode
        var barcodeGenerator = new BarcodeGenerator(
            EncodeTypes.DatabarOmniDirectional,
            "(01)12345678901231");

        // Set X‑dimension and initial bar height (30 pixels)
        barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
        barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 30;

        // Save the first image (30‑pixel height)
        barcodeGenerator.Save("DatabarHeight30.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved DatabarHeight30.png");

        // Change only the bar height to 60 pixels
        barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 60;

        // Save the second image (60‑pixel height)
        barcodeGenerator.Save("DatabarHeight60.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved DatabarHeight60.png");
    }
}
```

### 期待される出力

プログラムを実行すると、実行ファイルの作業ディレクトリに2つのファイルが生成されます：

* `DatabarHeight30.png` – 30 ピクセルのバー高さを持つ DataBar バーコード。  
* `DatabarHeight60.png` – 同じバーコードですが、各バーが2倍の高さです。

どちらの画像も任意の画像ビューアで開くことができ、PDF、HTML ページ、または印刷ラベルに直接埋め込むことができます。

## バー高さ調整が重要な理由

* **Scanning reliability:** 低解像度の媒体で非常に短いバーがあるとスキャナーが読み取りにくくなることがあります。高さを上げることで検出率が向上します。  
* **Design constraints:** モバイルアプリではコンパクトなバーコード（30 px）が必要な場合があり、印刷レシートではより大きなもの（60 px）が求められることがあります。  
* **Regulatory compliance:** 特定の業界では GS1 DataBar シンボルに対して最小バー高さが規定されています。  

同じ `BarcodeGenerator` インスタンスを再利用することで、データ文字列の再解析というオーバーヘッドを回避でき、高スループット環境で特に有益です。

## 一般的なバリエーションとエッジケース

| Situation | Recommended tweak |
|-----------|-------------------|
| 異なる X‑dimension が必要な場合 | 最初の `Save` の前に `XDimension.Pixels` を変更します。 |
| 別のシンボル（例: DataBar Stacked）を使用したい場合 | `BarcodeGenerator` を作成する際に `EncodeTypes.DatabarStacked` を使用します。 |
| バーコードを PDF に埋め込む必要がある場合 | `barcodeGenerator.Save(stream, BarCodeImageFormat.Png)` を使用し、ストリームを PDF ライブラリに追加します。 |
| .NET Framework 4.6 上で実行する場合 | 同じコードが動作します。適切な Aspose.BarCode アセンブリを参照してください。 |

## 信頼性の高いバーコード生成のためのプロティップス

* **Cache the generator** 同じデータでサイズだけ異なる多数のバーコードを生成する場合に使用します。  
* **

## 次に学ぶべきことは？

以下のチュートリアルは、本ガイドで示した手法を基にした密接に関連するトピックを取り上げています。各リソースには、ステップバイステップの解説と完全な動作コード例が含まれており、追加の API 機能を習得し、プロジェクトで代替実装アプローチを検討するのに役立ちます。

- [Aspose.BarCode for .NET を使用した 1 次元 Databar のバーコード高さの生成と調整方法](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-barcode-height-adjustment/)
- [C# と Aspose.BarCode で Databar PNG 画像を作成する方法](/barcode/english/python-java/general/how-to-create-databar-png-images-with-c-and-aspose-barcode/)
- [C# でバーコードをカスタムサイズで生成し画像として保存する方法](/barcode/english/python-java/general/how-to-generate-barcode-set-custom-size-and-save-image-in-c/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}