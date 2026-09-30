---
category: general
date: 2026-08-22
description: Aspose.BarCode を使用して、バーコードを素早く生成し、PNG 形式でエクスポートする際にバーコードのサイズを変更する方法。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to generate barcode
- change barcode size
- export barcode image
language: ja
lastmod: 2026-08-22
og_description: C#でバーコードを生成し、PNGとしてエクスポートする前にバーコードサイズを簡単に変更する方法。完全ガイドをご覧ください。
og_image_alt: Screenshot showing how to generate barcode with Aspose.BarCode in C#
og_title: C#でカスタムサイズのバーコード画像を生成する方法
schemas:
- author: Aspose
  dateModified: '2026-08-22'
  description: How to generate barcode quickly and learn how to change barcode size
    while exporting the barcode image as PNG using Aspose.BarCode.
  headline: How to generate barcode images with custom size in C#
  type: TechArticle
tags:
- barcode
- C#
- Aspose.BarCode
title: C#でカスタムサイズのバーコード画像を生成する方法
url: /ja/python-java/general/how-to-generate-barcode-images-with-custom-size-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# C#でカスタムサイズのバーコード画像を生成する方法

郵便自動化、在庫管理、イベントチケットなどのために **how to generate barcode** が必要な場合、このガイドでは C# で完全に実行可能なソリューションを示します。また、**how to change barcode size** と **export barcode image** を PNG 形式で IDE を離れずに行う方法も学べます。

Aspose.BarCode ライブラリを使用します。このライブラリは OneCode シンボロジーをサポートし、ピクセル単位でサイズを制御でき、単一のメソッド呼び出しで画像エクスポートを処理します。チュートリアルの最後までに、異なる桁数の OneCode バーコードを表す 4 つの PNG ファイルが作成されます。

## 前提条件

- .NET 6.0 以降（コードは .NET Framework 4.6+ でも動作します）
- Visual Studio 2022（またはお好みの C# エディタ）
- **Aspose.BarCode** の NuGet 参照 (`Install-Package Aspose.BarCode`)
- C# 構文の基本的な知識

> **Pro tip:** ライブラリを評価中の場合、Aspose はすべてのバーコード機能を含む 30 日間の無料トライアルを提供しています。

## 手順 1: 最小限のコンソールプロジェクトを設定する

新しいコンソール アプリケーションを作成し、Aspose.BarCode パッケージを追加します：

```bash
dotnet new console -n BarcodeDemo
cd BarcodeDemo
dotnet add package Aspose.BarCode
```

生成された `Program.cs` にバーコード生成ロジック全体が含まれます。

## 手順 2: How to generate barcode – 再利用可能なメソッドを作成する

以下は、データ文字列、目的のファイル名、オプションのサイズパラメータを受け取る自己完結型メソッドです。このメソッドは **how to generate barcode** のコアパターンを示しています。

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // Example calls for different digit lengths
            GenerateOneCode("12345678901234567890", "PostalOneCodeBarcode20Digits.png");
            GenerateOneCode("1234567890123456789012345", "PostalOneCodeBarcode25Digits.png");
            GenerateOneCode("12345678901234567890123456789", "PostalOneCodeBarcode29Digits.png");
            GenerateOneCode("1234567890123456789012345678901", "PostalOneCodeBarcode31Digits.png");
        }

        /// <summary>
        /// Generates a OneCode barcode, applies size settings, and saves as PNG.
        /// </summary>
        /// <param name="data">Numeric string to encode (OneCode supports 20‑31 digits).</param>
        /// <param name="fileName">Target PNG file name.</param>
        /// <param name="xDimension">Width of a single module in pixels (default 4).</param>
        /// <param name="barHeight">Height of the barcode in pixels (default 50).</param>
        static void GenerateOneCode(string data, string fileName,
                                    int xDimension = 4, int barHeight = 50)
        {
            // 1️⃣ Initialize the generator for OneCode symbology
            var generator = new BarcodeGenerator(EncodeTypes.OneCode, data);

            // 2️⃣ **Change barcode size** – adjust module width and total height
            generator.Parameters.Barcode.XDimension.Pixels = xDimension; // module width
            generator.Parameters.Barcode.BarHeight.Pixels = barHeight;   // overall height

            // 3️⃣ **Export barcode image** as PNG; you can also choose JPEG, BMP, etc.
            generator.Save(fileName, BarCodeImageFormat.Png);
            Console.WriteLine($"Saved {fileName}");
        }
    }
}
```

### このメソッドが重要な理由

- **Encapsulation:** すべてのサイズ関連設定が一箇所に集約されているため、異なる寸法でメソッドを呼び出すのが簡単です。
- **Reusability:** 同じメソッドを任意の OneCode 文字列長で再利用でき、OneCode が 20‑31 桁のみ受け付ける点で重要です。
- **Clarity:** 絵文字でラベル付けされたコメントが、初期化、サイズ変更、エクスポートという 3 つの論理フェーズを読者に案内します。

## 手順 3: 異なる要件に合わせてバーコードサイズを変更する

スキャナがより高いバーコードを期待したり、印刷レイアウトがより狭いモジュールを要求したりすることがあります。`XDimension.Pixels` プロパティは単一のバーコードモジュールの幅を制御し、`BarHeight.Pixels` は全体の高さを設定します。

```csharp
// Example: generate a larger barcode (8‑pixel modules, 80‑pixel height)
GenerateOneCode(
    data: "12345678901234567890",
    fileName: "LargeOneCode.png",
    xDimension: 8,
    barHeight: 80);
```

**サイズ変更時の重要ポイント:**

- **Minimum X‑dimension:** 技術的には 1 ピクセルが許容されますが、ほとんどのスキャナは信頼できる読み取りのために少なくとも 2 ピクセルを必要とします。
- **Maximum height:** 明確な上限はありませんが、非常に高いバーコードは標準ラベルの印刷可能領域を超える可能性があります。
- **Aspect ratio:** 歪みを防ぐため、高さとモジュール幅の比率をバランスさせてください（≈12‑15 × モジュール幅）。

## 手順 4: 他の形式でバーコード画像をエクスポートする（オプション）

`Save` メソッドは複数の `BarCodeImageFormat` 値を受け取ります: `Png`, `Jpeg`, `Bmp`, `Gif`, `Tiff`。ロスレスのベクタ形式が必要な場合は、代わりに `Svg` にエクスポートできます。

```csharp
// Export to SVG for infinite scaling
generator.Save("OneCode.svg", BarCodeImageFormat.Svg);
```

PNG でエクスポートするのが最も一般的な選択です。鮮明なエッジを保ち、ウェブブラウザや印刷パイプラインで広くサポートされています。

## 期待される出力

プログラムを実行すると、プロジェクトフォルダに 4 つの PNG ファイルが作成されます：

- `PostalOneCodeBarcode20Digits.png` – 20 桁の OneCode バーコード
- `PostalOneCodeBarcode25Digits.png` – 25 桁の OneCode バーコード
- `PostalOneCodeBarcode29Digits.png` – 29 桁の OneCode バーコード
- `PostalOneCodeBarcode31Digits.png` – 31 桁の OneCode バーコード

各画像は以下のプレースホルダーに似た外観になります（実際のグラフィックは提供した数値データに依存します）。

![How to generate barcode example](https://example.com/placeholder.png "How to generate barcode example")

*画像の alt テキストにはアクセシビリティと SEO のために主要キーワードが含まれています。*

## よくある質問とエッジケース

| Question | Answer |
|----------|--------|
| **データ文字列が 20 桁未満の場合はどうすればよいですか？** | OneCode は最低 20 桁が必要です。文字列を先頭にゼロでパディングするか、別のシンボロジー（例: Code128）を使用してください。 |
| **マルチスレッド環境でバーコードを生成できますか？** | はい。`BarcodeGenerator` はスレッドセーフではないため、スレッドごとに別々のジェネレータをインスタンス化してください。 |
| **背景色はどう設定しますか？** | `generator.Parameters.Barcode.BackgroundColor = System.Drawing.Color.White;` を `Save` 呼び出しの前に使用します。 |
| **画像を HTML ページに直接埋め込む方法はありますか？** | 画像を `MemoryStream` に保存し、Base64 に変換して `<img src="data:image/png;base64,..." />` で埋め込みます。 |

## 結論

これで、Aspose.BarCode を使用して C# で **how to generate barcode** 画像を生成し、X‑dimension とバー高さを調整して **change barcode size** する方法、そして PNG（または他の）形式で **export barcode image** ファイルをエクスポートする方法が分かりました。再利用可能な `GenerateOneCode` メソッドを使えば、20 桁から 31 桁までの任意の OneCode バーコードをワンライナーで作成できます。

ここからは次のことを試せます：

- 他のシンボロジー（`EncodeTypes.Code128`, `EncodeTypes.QR`）を実験する。
- ジェネレータを Web API に統合し、要求に応じてバーコード画像を返す。
- PNG 出力を PDF ライブラリと組み合わせて、出荷ラベルにバーコードを埋め込む。

コーディングを楽しんでください。また、コメントでご自身のバリエーションを自由に共有してください！

## 次に学ぶべきことは？

以下のチュートリアルは、本ガイドで示した手法を基にした密接に関連するトピックをカバーしています。各リソースには、ステップバイステップの解説と完全な動作コード例が含まれており、追加の API 機能を習得し、プロジェクトで代替実装アプローチを検討するのに役立ちます。

- [Aspose.BarCode for .NET を使用した DataMatrix バーコードの生成方法 – ステップバイステップガイド](/barcode/english/net/datamatrix-barcode-configuration/)
- [Aspose.BarCode for .NET を使用したカスタムアスペクト比の Aztec バーコード生成方法](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)
- [Aspose.BarCode for .NET を使用した One-Dimensional Databar のバーコード高さの生成と調整方法](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-barcode-height-adjustment/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}