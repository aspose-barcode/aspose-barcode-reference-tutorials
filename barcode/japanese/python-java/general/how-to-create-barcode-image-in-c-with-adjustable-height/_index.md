---
category: general
date: 2026-09-07
description: C#でバーコード画像を作成し、高さ・幅・フォーマットを調整して、バーコードのPNGファイルを素早く生成する方法を学びましょう。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode image
- how to set barcode
- how to adjust barcode
- generate barcode png
- change barcode height
language: ja
lastmod: 2026-09-07
og_description: C#でバーコード画像を作成し、バーコードのサイズ設定、バーコードの高さ変更、任意のアプリケーション向けにバーコードPNGファイルを生成する方法を学びましょう。
og_image_alt: C# generated barcode image saved as PNG with custom height
og_title: C#でバーコード画像を作成する – ステップバイステップガイド
schemas:
- author: Aspose
  dateModified: '2026-09-07'
  description: Learn how to create barcode image in C# and adjust its height, width,
    and format to generate barcode PNG files quickly.
  headline: How to create barcode image in C# with adjustable height
  type: TechArticle
- description: Learn how to create barcode image in C# and adjust its height, width,
    and format to generate barcode PNG files quickly.
  name: How to create barcode image in C# with adjustable height
  steps:
  - name: 3.1 Adjust the narrow bar width (X‑dimension)
    text: The X‑dimension controls the thickness of the thinnest bar. A value of **2
      pixels** yields a finer appearance, useful when you need a compact label.
  - name: 3.2 Change barcode height for visual balance
    text: Bar height determines how tall the barcode appears. Below we show two common
      heights—30 pixels for a small label and 60 pixels for a larger visual. This
      demonstrates **how to adjust barcode** height programmatically.
  - name: 4.1 Save the first image (30 px height)
    text: '```csharp // Save a 30‑pixel‑high barcode as PNG generator.Save("DatabarBarHeight30Pixels.png",
      BarCodeImageFormat.Png); ```'
  - name: 4.2 Increase the height and save a second image
    text: '```csharp // Increase height to 60 pixels for a larger visual generator.Parameters.Barcode.BarHeight.Pixels
      = 60;'
  type: HowTo
tags:
- barcode
- C#
- image generation
title: C#で高さ調整可能なバーコード画像の作成方法
url: /ja/python-java/general/how-to-create-barcode-image-in-c-with-adjustable-height/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# C#で調整可能な高さのバーコード画像を作成する方法

POSシステムや在庫管理ツール用にC#でバーコード画像を作成する必要がある場合、このガイドでは完全なワークフローを示します。バーコードのパラメータ設定方法、バーコードの高さ変更方法、そして視覚要件を満たすバーコードPNGファイルの生成方法が分かります。

スキャニングハードウェアの統合、ラベル印刷、レポートダッシュボードの構築時に、バーコード画像の生成は一般的な作業です。このチュートリアルの最後までに、IDEを離れることなくバーコードのXディメンション、高さ、出力形式を調整できる再利用可能なコードスニペットが手に入ります。

## 前提条件

* .NET 6.0（またはそれ以降）がインストールされていること – コードは最新の.NET SDKでコンパイルできます。
* **Aspose.BarCode** ライブラリへの参照（NuGet `Aspose.BarCode` で入手可能）。
* C# コンソールアプリケーションの基本的な知識。

これらの要件により、例はWindows、Linux、macOS上でそのまま実行できます。

## 手順 1: プロジェクトのセットアップとライブラリのインポート

新しいコンソールプロジェクトを作成し、バーコードパッケージを追加します。

```bash
dotnet new console -n BarcodeDemo
cd BarcodeDemo
dotnet add package Aspose.BarCode
```

次に *Program.cs* を開き、必要な `using` ディレクティブを追加します。

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode.Encoding;
using Aspose.BarCode;
```

これらのインポートにより、**バーコード画像の作成** に必要な `BarcodeGenerator`、`EncodeTypes`、および画像形式列挙型にアクセスできます。

## 手順 2: 目的のシンボロジーでジェネレータを初期化する

最初のコード行は、エンコードするバーコードタイプを認識する `BarcodeGenerator` を作成します。この例では DataBar Omni‑Directional シンボロジーを使用していますが、`EncodeTypes.DatabarOmniDirectional` を Aspose.BarCode がサポートする他のタイプに置き換えることができます。

```csharp
// Initialize a generator for a DataBar Omni‑Directional barcode
var generator = new BarcodeGenerator(
    EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");
```

文字列 `"(01)12345678901231"` は多くの小売業者が要求する GS1 アプリケーション識別子形式に従っています。ジェネレータの初期化は、以降のすべての **バーコード設定方法** の土台となります。

## 手順 3: バーコード寸法の設定 – X ディメンションと高さ

### 3.1 ナローバー幅（X ディメンション）の調整

X ディメンションは最も細いバーの太さを制御します。**2 ピクセル** の値は、コンパクトなラベルが必要なときに有用な、より細かい外観を実現します。

```csharp
// Set the narrow bar width to 2 pixels
generator.Parameters.Barcode.XDimension.Pixels = 2;
```

### 3.2 視覚的バランスのためのバーコード高さの変更

バーの高さはバーコードの縦長さを決定します。以下では、30 ピクセル（小さなラベル用）と 60 ピクセル（大きな表示用）の2つの一般的な高さを示します。これは、プログラムで **バーコードの高さを調整する方法** を実演しています。

```csharp
// Height 30 pixels – suitable for compact labels
generator.Parameters.Barcode.BarHeight.Pixels = 30;
```

## 手順 4: 異なる高さのバーコードPNGファイルを生成する

### 4.1 最初の画像を保存（30 ピクセルの高さ）

```csharp
// Save a 30‑pixel‑high barcode as PNG
generator.Save("DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);
```

### 4.2 高さを増やして2枚目の画像を保存

```csharp
// Increase height to 60 pixels for a larger visual
generator.Parameters.Barcode.BarHeight.Pixels = 60;

// Save a 60‑pixel‑high barcode as PNG
generator.Save("DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);
```

これら2つの `Save` 呼び出しは、同じジェネレータインスタンスを再利用しながら、異なる寸法の **バーコードPNGの生成** を示しています。画像形式は明示的に PNG に設定されており、ロスレス品質を保つため、印刷や画面表示に最適です。

## 手順 5: 完全な実行可能サンプル

すべてをまとめると、任意の C# コンソールプロジェクトにコピーできる単一の `Main` メソッドが得られます。

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode.Encoding;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        // 1️⃣ Create a DataBar Omni‑Directional barcode generator
        var generator = new BarcodeGenerator(
            EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");

        // 2️⃣ Set the narrow bar width (X‑dimension) to 2 pixels
        generator.Parameters.Barcode.XDimension.Pixels = 2;

        // 3️⃣ Create a 30‑pixel‑high barcode and save it as PNG
        generator.Parameters.Barcode.BarHeight.Pixels = 30;
        generator.Save("DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved 30‑pixel barcode as DatabarBarHeight30Pixels.png");

        // 4️⃣ Change barcode height to 60 pixels and save again
        generator.Parameters.Barcode.BarHeight.Pixels = 60;
        generator.Save("DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved 60‑pixel barcode as DatabarBarHeight60Pixels.png");
    }
}
```

このプログラムを実行すると、プロジェクトの出力フォルダーに2つの PNG ファイルが生成されます。

* `DatabarBarHeight30Pixels.png` – コンパクトな 30 ピクセルのバーコード。
* `DatabarBarHeight60Pixels.png` – 大きめの 60 ピクセルのバーコード。

両方のファイルは **バーコード画像の作成** を含んでおり、HTML に埋め込んだり、ラベルに印刷したり、スキャン用にモバイルアプリへ送信したりできます。

## よくある質問とエッジケースの対処

| Question | Answer |
|----------|--------|
| **異なる画像形式が必要な場合は？** | `BarCodeImageFormat.Png` を `BarCodeImageFormat.Jpeg`、`Bmp`、または `Gif` に置き換えます。ライブラリが自動的に変換を処理します。 |
| **前景色/背景色を変更できますか？** | はい。`Save` を呼び出す前に `generator.Parameters.Barcode.ForeColor` と `BackColor` を使用して `System.Drawing.Color` の値を設定します。 |
| **ディスクにファイルを保存せずにバーコードを生成するには？** | `generator.GenerateBarCodeImage()` を呼び出して `System.Drawing.Image` オブジェクトを取得し、直接レスポンスやデータベースにストリームします。 |
| **データ文字列がシンボロジーの上限を超える場合は？** | ジェネレータは `ArgumentException` をスローします。入力長を検証するか、シンボロジーの仕様に従って切り詰めてください。 |
| **複数のバーコードをバッチ処理する方法はありますか？** | `foreach` ループで `generator.CodeText` と `BarHeight` を各アイテムごとに更新し、ユニークなファイル名で `Save` を呼び出すように手順をラップします。 |

これらのシナリオに対処することで、チュートリアルの **バーコード調整方法** ロジックは実務プロジェクトでも堅牢になります。

## 安定したバーコード生成のプロティップ

* 同じタイプのバーコードを多数作成する場合は **ジェネレータをキャッシュ** してください。オブジェクトを再利用することで割り当てオーバーヘッドが削減されます。
* 印刷用に高解像度 PNG が必要な場合は **`Resolution`**（`generator.Parameters.ImageResolution.Dpi`）を設定します。
* `CodeText` に割り当てる前に **GS1 データを検証** し、エンコードエラーによるスキャン失敗を防ぎます。
* 高さや X ディメンションを変更した後は **実際のスキャナーでテスト** してください。レガシーデバイスには最小サイズ要件がある場合があります。

## 結論

これで C# で **バーコード画像を作成する方法**、**バーコードの寸法を設定する方法**、**バーコードの高さを調整する方法**、そして **バーコードPNGを生成する方法** が分かりました。`XDimension` と `BarHeight` を調整すれば、基になるデータを変更せずにコンパクトなバーコードや大きなバーコードを作成できます。

次に、ユーザー入力に応じて **バーコードの高さを動的に変更** する方法や、Aspose.PDF を使用して PDF レポートにバーコードを埋め込む方法、`EncodeTypes.QR` を使った QR コード生成への切り替えなど、関連トピックを探求してください。さまざまなシンボロジーや出力形式を試すことで、C# におけるバーコード作成を完全にマスターできます。

## 次に学ぶべきことは？

以下のチュートリアルは、本ガイドで示した手法を基にした密接に関連するトピックを取り上げています。各リソースには、ステップバイステップの解説と完全な動作コード例が含まれており、追加の API 機能を習得し、プロジェクトでの代替実装アプローチを探求するのに役立ちます。

- [C#でGS1バーコード画像を作成 – バーコードC#を素早く生成する方法](/barcode/english/net/gs1-barcode-encoding/create-gs1-barcode-images-in-c-how-to-generate-barcode-c-qui/)
- [.NET 用 Aspose.BarCode で一次元Databarのバーコード高さを生成・調整する方法](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-barcode-height-adjustment/)
- [C#でバーコード画像を生成 – MicroPdf417 ガイド](/barcode/english/net/compact-pdf417-encoding/how-to-generate-barcode-image-in-c-micropdf417-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}