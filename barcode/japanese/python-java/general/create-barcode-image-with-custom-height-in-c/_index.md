---
category: general
date: 2026-10-28
description: C#でバーコード画像を作成し、BarcodeGenerator APIを使用して高さを調整する方法を学びます。カスタムバーコードの高さとバーの高さを変更するステップバイステップガイド。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode image
- how to adjust height
- c# barcode generator
- custom barcode height
- change barcode height
language: ja
lastmod: 2026-10-28
og_description: C#でバーコード画像を作成し、すぐに高さの調整方法を確認できます。BarcodeGeneratorを使用してカスタムバーコードの高さを設定する完全な例をご覧ください。
og_image_alt: Screenshot showing a generated barcode image with a custom height
og_title: C#でカスタム高さのバーコード画像を作成する – 完全ガイド
schemas:
- author: Aspose
  dateModified: '2026-10-28'
  description: Create barcode image in C# and learn how to adjust height using the
    BarcodeGenerator API. Step‑by‑step guide for custom barcode height and changing
    bar height.
  headline: Create barcode image with custom height in C#
  type: TechArticle
tags:
- barcode
- C#
- image generation
- GS1‑Databar
title: C#でカスタム高さのバーコード画像を作成する
url: /ja/python-java/general/create-barcode-image-with-custom-height-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# C#でカスタム高さのバーコード画像を作成する

バーコード画像を**作成**し、そのサイズを制御する必要がある場合、このガイドではその手順を正確に示します。Aspose.BarCode .NET ライブラリを使用すると、GS1‑Databar Omni‑Directional バーコードを生成でき、**高さの調整方法**を示すことで、あらゆるレイアウト要件に対応できます。

完全な実行可能プログラムを順に確認し、**c# barcode generator** を実演し、設定した各プロパティを説明し、30ピクセルのバー高さと60ピクセルのバー高さの2つの異なる出力を示します。最後には、ライブラリがサポートする任意のバーコードタイプに対してプログラムで**バーコードの高さを変更**できるようになります。

## 前提条件

- .NET 6.0 SDK またはそれ以降（コードは .NET Framework 4.6+ でも動作します）
- Visual Studio 2022 または C# プロジェクトをビルドできる任意のエディタ
- Aspose.BarCode for .NET NuGet パッケージ (`Install-Package Aspose.BarCode`)
- C# 構文の基本的な知識

> **Pro tip:** CI パイプラインを使用している場合は、NuGet パッケージを `csproj` ファイルに追加して、ビルド時に自動的に復元されるようにします。

## 手順 1: プロジェクトの設定と名前空間のインポート

新しいコンソールプロジェクトを作成し、必要な `using` 文を追加します。これらの名前空間により、`BarcodeGenerator`、`EncodeTypes`、および画像フォーマットヘルパーにアクセスできます。

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace BarcodeHeightDemo
{
    class Program
    {
        static void Main()
        {
            // The rest of the tutorial code lives here.
        }
    }
}
```

> **Why this matters:** 正しい名前空間をインポートすることで、コンパイル時エラーを防ぎ、IntelliSense で API を検出しやすくなります。

## 手順 2: GS1‑Databar Omni‑Directional コード用の **c# barcode generator** を初期化する

コンストラクタは 2 つの引数を受け取ります：バーコードタイプ (`EncodeTypes.DatabarOmniDirectional`) とデータ文字列です。データ文字列は GS1 アプリケーション識別子形式に従う必要があり、例として `(01)12345678901231` があります。

```csharp
// Create a barcode generator for a GS1‑Databar Omni‑Directional code
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarOmniDirectional,
    "(01)12345678901231");
```

> **Explanation:** `BarcodeGenerator` オブジェクトはすべてのバーコード関連設定のエントリーポイントです。このインスタンスを取得すれば、サイズ、色、出力形式を調整できます。

## 手順 3: 共通の X‑dimension（最も細いバーのピクセル幅）を定義する

2 ピクセルの X‑dimension は、ほとんどの画面表示シナリオで良い出発点です。

```csharp
// Set a 2‑pixel X‑dimension (width of the smallest bar)
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

> **Why set X‑dimension?** バーコード全体の幅を制御します。一貫性を保つことで、バー高さを変更しても視覚的バランスが歪まないようにします。

## 手順 4: **Create barcode image** を 30 ピクセルのバー高さで作成する

ここでバー高さを設定し、最初の画像を保存し、次に高さを変更して2枚目を作成します。

```csharp
// Configure a 30‑pixel bar height
barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 30;

// Save the first image
string output30 = "DatabarBarHeight30Pixels.png";
barcodeGenerator.Save(output30, BarCodeImageFormat.Png);
Console.WriteLine($"Saved barcode with 30 px height to {output30}");
```

> **Result:** 各垂直バーが 30 ピクセルの PNG ファイルが生成されます。X‑dimension は 2 ピクセルのままで、全体の幅は変わりません。

## 手順 5: **How to adjust height** – バー高さを 60 ピクセルに変更する

**custom barcode height** を示すために、同じプロパティに新しい値を割り当てて再度保存するだけです。

```csharp
// Change the bar height to 60 pixels
barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 60;

// Save the second image
string output60 = "DatabarBarHeight60Pixels.png";
barcodeGenerator.Save(output60, BarCodeImageFormat.Png);
Console.WriteLine($"Saved barcode with 60 px height to {output60}");
```

> **Key insight:** `BarHeight` プロパティは変更可能で、`BarcodeGenerator` インスタンスを再作成する必要はありません。これにより、ループやバッチ処理で複数サイズを安価に生成できます。

## 手順 6: 出力を確認する

コンソールプログラムを実行します（`dotnet run`）。実行後、プロジェクトの出力フォルダーに 2 つの PNG ファイルが生成されます：

- `DatabarBarHeight30Pixels.png` – 短いバー（30 px）
- `DatabarBarHeight60Pixels.png` – 長いバー（60 px）

両画像は同じエンコードデータを含みますが、視覚的な高さが異なるため、フォーム、製品ラベル、またはスペース制約が異なる UI コンポーネントにバーコードを組み込む際に便利です。

![カスタム高さのバーコード画像を作成](barcode-example.png){.align-center width="600" alt="カスタム高さのバーコード画像を作成"}

> **Tip:** 任意の画像ビューアで PNG ファイルを開きます。長いバーコードは短いものの垂直サイズが正確に2倍になり、横方向の間隔は同じままです。

## 手順 7: 一般的なバリエーションとエッジケース

| Situation | Recommended setting |
|-----------|---------------------|
| **高解像度ラベルプリンターで印刷** | X‑dimension を大きく（例: 4 px）し、`BarHeight` を比例的に増やす。 |
| **低 DPI スクリーンで表示** | `XDimension` を 1 px に保ち、可読性のため `BarHeight` を 20‑40 px の範囲に設定する。 |
| **QR コードや 2D バーコードの生成** | `BarHeight` プロパティは無視されます。代わりに `EncodeTypes.QR` を使用し、`ImageHeight` を調整してください。 |
| **多数の高さをバッチ生成** | 高さの配列をループし、ループ内で `Save` を呼び出す。各イテレーションでジェネレータを再作成する必要はありません。 |

### 無効な高さの取り扱い

`BarHeight` に正の値でないものを設定すると、ライブラリは `ArgumentOutOfRangeException` をスローします。シンプルなチェックでこれを防止しましょう：

```csharp
int desiredHeight = 0; // example invalid value
if (desiredHeight <= 0)
{
    throw new ArgumentException("Bar height must be greater than zero.");
}
barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = desiredHeight;
```

## 完全なソースコード（コピー用）

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace BarcodeHeightDemo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Create the barcode generator for GS1‑Databar Omni‑Directional
            BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
                EncodeTypes.DatabarOmniDirectional,
                "(01)12345678901231");

            // 2️⃣ Set a common 2‑pixel X‑dimension
            barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;

            // 3️⃣ First image – 30 pixel bar height
            barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 30;
            string path30 = "DatabarBarHeight30Pixels.png";
            barcodeGenerator.Save(path30, BarCodeImageFormat.Png);
            Console.WriteLine($"Saved barcode with 30 px height to {path30}");

            // 4️⃣ Second image – 60 pixel bar height
            barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 60;
            string path60 = "DatabarBarHeight60Pixels.png";
            barcodeGenerator.Save(path60, BarCodeImageFormat.Png);
            Console.WriteLine($"Saved barcode with 60 px height to {path60}");
        }
    }
}
```

> **Why this works:** 必要なすべての設定（`EncodeTypes`、`XDimension`、`BarHeight`）が各 `Save` 呼び出しの前に適用されています。同じ `BarcodeGenerator` インスタンスを再利用することで、メモリ効率が高く、読みやすくなります。

## 結論

これで C# で **create barcode image** ファイルを作成し、`BarcodeGenerator` API を使用して **barcode height** を正確に **change barcode height** できるようになりました。`BarHeight.Pixels` を調整することで、ジェネレータを再構築せずに **custom barcode height** を実現でき、動的ラベル作成、UI レンダリング、バッチ処理パイプラインに最適なソリューションとなります。

次に、**how to adjust width**、**adding human‑readable text**、または **exporting to SVG for scalable web use** などの関連トピックを探求してください。同じパターン（プロパティを設定し、`Save` を呼び出す）をこれらのシナリオでも適用でき、例を自信を持って拡張できます。

## 次に学ぶべきことは？

以下のチュートリアルは、本ガイドで示した手法を基にした密接に関連するトピックを取り上げています。各リソースには、完全な動作コード例とステップバイステップの解説が含まれ、追加の API 機能を習得し、プロジェクトで代替実装アプローチを検討するのに役立ちます。

- [C#でバーコードの高さを変更する方法 – 完全ガイド](/barcode/english/python-java/general/how-to-change-barcode-height-in-c-complete-guide/)
- [バーコードジェネレータ例 – カスタム高さで Planet と RM4SCC バーコードを作成](/barcode/english/python-java/general/barcode-generator-example-create-planet-and-rm4scc-barcodes/)
- [C#で rm4scc バーコードを作成し高さを制御する方法](/barcode/english/python-java/general/how-to-create-rm4scc-barcode-and-control-its-height-in-c/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}