---
category: general
date: 2026-09-19
description: C# 画像出力用に、バーコードの高さを変更し、DataBar Omni‑Directional を作成し、バーコードの寸法を調整する方法を示すバーコードジェネレータの例。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- barcode generator example
- how to change height
- how to create databar
- adjust barcode dimensions
- create barcode image c#
language: ja
lastmod: 2026-09-19
og_description: C# の PNG 画像用に、バーコードの高さを変更し、DataBar Omni‑Directional を作成し、バーコードの寸法を調整する方法を教えるバーコードジェネレータの例
og_image_alt: Screenshot of a DataBar Omni‑Directional barcode generated in C#
og_title: C#でのバーコードジェネレーター例 – ステップバイステップガイド
schemas:
- author: Aspose
  dateModified: '2026-09-19'
  description: barcode generator example showing how to change height, create DataBar
    Omni‑Directional, and adjust barcode dimensions for C# image output
  headline: How to build a barcode generator example in C#
  type: TechArticle
tags:
- barcode
- C#
- Aspose.BarCode
title: C#でバーコードジェネレータの例を作る方法
url: /ja/python-java/general/how-to-build-a-barcode-generator-example-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# C# のバーコードジェネレータ例 – 完全プログラミングガイド

.NET プロジェクト向けの **バーコードジェネレータ例** が必要な場合、本ガイドでは DataBar Omni‑Directional バーコードを C# で作成・設定・保存する方法をステップバイステップで解説します。高さの変更、バーコード寸法の調整、高品質 PNG 画像の出力を、単一の実行可能コンソールアプリケーションで実現できます。

以下の手順では、必要な SDK のインストールから X‑dimension とバー高さの微調整までを網羅しています。チュートリアルの最後まで進めば、請求書、在庫管理、スキャンワークフローに組み込める、すぐに使えるバーコードジェネレータが完成します。

## 前提条件

開始する前に、以下が揃っていることを確認してください。

* .NET 6.0 SDK 以降がインストール済み  
* Visual Studio 2022（または .NET をサポートする任意の IDE）  
* **Aspose.BarCode for .NET** の有効ライセンス（無料トライアルでもテスト可能）  

別のライブラリを使用する場合でも、寸法調整や画像保存の概念は同じです。該当する API 呼び出しを置き換えてください。

## 手順 1: プロジェクトを作成し Aspose.BarCode パッケージを追加

新しいコンソールプロジェクトを作成し、バーコードライブラリを参照します。

```bash
dotnet new console -n BarcodeDemo
cd BarcodeDemo
dotnet add package Aspose.BarCode
```

`dotnet add package` コマンドは、DataBar Omni‑Directional シンボルをフルサポートする Aspose.BarCode の最新安定版を取得します。

## 手順 2: 完全なバーコードジェネレータ例を記述

**Program.cs** を開き、内容を以下のコードに置き換えます。このブロックには **バーコードジェネレータ例** の全コードが含まれており、欠落はありません。

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
            // 1️⃣ Create a barcode generator for a DataBar Omni‑Directional symbol
            // The GTIN‑14 value "(01)12345678901231" is encoded as a numeric string.
            BarcodeGenerator generator = new BarcodeGenerator(
                EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");

            // 2️⃣ Adjust barcode dimensions
            // Set the X‑dimension (module width) to 2 pixels – this controls the thin bar width.
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // 3️⃣ How to change height
            // Set the bar height to 30 pixels. Height influences readability on larger scanners.
            generator.Parameters.Barcode.BarHeight.Pixels = 30;

            // 4️⃣ Optional: fine‑tune additional properties (quiet zone, color, etc.)
            generator.Parameters.Barcode.QrCodeErrorLevel = QRErrorLevel.LevelM; // example property
            generator.Parameters.ImageOptions.ForeColor = System.Drawing.Color.Black;
            generator.Parameters.ImageOptions.BackColor = System.Drawing.Color.White;

            // 5️⃣ Create barcode image C#
            // Save the generated barcode as a PNG file in the output folder.
            string outputPath = "DatabarOmniDirectional.png";
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"Barcode saved to {outputPath}");
        }
    }
}
```

### 各行の重要ポイント

* **Create a barcode generator** – `BarcodeGenerator` コンストラクタはエンコードタイプ（`EncodeTypes.DatabarOmniDirectional`）と埋め込むデータを結び付けます。これが **how to create databar** の核心です。  
* **Adjust barcode dimensions** – `XDimension.Pixels` プロパティは最細バーの幅を定義します。この値を変更すると全体サイズとスキャン信頼性に影響します。  
* **How to change height** – `BarHeight.Pixels` プロパティが垂直サイズを制御します。高さを上げるとハンドヘルドスキャナでの可読性が向上し、下げると小さなラベルでのスペース節約が可能です。  
* **Optional tweaks** – 前景・背景色やエラ―訂正レベルの設定は任意ですが、**adjust barcode dimensions** の概念を拡張する例として示しています。  
* **Create barcode image C#** – `Save` メソッドでバーコードをディスクに書き出します。`BarCodeImageFormat.Png` を使用すればロスレス圧縮となり、ほとんどの用途に最適です。

## 手順 3: ビルドして例を実行

プログラムをコンパイルし、実行します。

```bash
dotnet run
```

コンソールに次のように表示されます。

```
Barcode saved to DatabarOmniDirectional.png
```

プロジェクトフォルダーに **DatabarOmniDirectional.png** というファイルが生成されます。画像を開くと、スキャン可能な鮮明な DataBar Omni‑Directional バーコードが確認できます。

## 後から高さを変更する方法

高さを可変にしたい場合は、以下のように高さ設定をメソッド化します。

```csharp
static void SetBarHeight(BarcodeGenerator gen, int heightPixels)
{
    gen.Parameters.Barcode.BarHeight.Pixels = heightPixels;
}
```

`Save` の前に `SetBarHeight(generator, 45);` を呼び出してください。この手法により、ユーザー入力や設定ファイルに基づいて **how to change height** を動的に制御できます。

## 異なるデータで DataBar Omni‑Directional バーコードを作成する方法

DataBar Omni‑Directional は GTIN‑14、GTIN‑13 などの数値識別子をサポートします。別の値をエンコードしたい場合は、コンストラクタ内の文字列を差し替えるだけです。

```csharp
new BarcodeGenerator(EncodeTypes.DatabarOmniDirectional, "(01)98765432109876");
```

データは数値で正しい形式に整えてください。形式が不正だと `BarcodeException` がスローされます。

## 印刷シナリオ別のバーコード寸法調整

プリンターやラベルサイズに応じて X‑dimension と高さを変える必要があります。以下の表を参考にしてください。

| シナリオ                     | X‑Dimension (pixels) | Bar Height (pixels) |
|------------------------------|----------------------|---------------------|
| 小ラベル (25 mm × 15 mm)     | 1                    | 20                  |
| 中ラベル (50 mm × 30 mm)     | 2                    | 30                  |
| 大ラベル (100 mm × 50 mm)    | 3                    | 45                  |

`generator.Parameters.Barcode.XDimension.Pixels` と `BarHeight.Pixels` に上記の値を設定して適用します。

## プロのヒント: 生成したバーコードを検証する

ラベルを出荷する前に、プログラムで可読性を確認できます。

```csharp
using Aspose.BarCode.BarCodeRecognition;

// ...

BarCodeReader reader = new BarCodeReader(outputPath, DecodeType.DatabarOmniDirectional);
if (reader.Read())
{
    Console.WriteLine("Validation succeeded: " + reader.GetCodeText());
}
else
{
    Console.WriteLine("Validation failed – barcode may be unreadable.");
}
```

このスニペットは **adjust barcode dimensions** の簡易サニティチェックを示しており、スキャン要件を満たしているかを検証します。

## よくある落とし穴と回避策

| 落とし穴                              | 発生理由                                   | 対策                                                                 |
|--------------------------------------|--------------------------------------------|----------------------------------------------------------------------|
| DataBar に数値以外のデータを使用      | DataBar は数値 GTIN 形式を期待する         | `(01)XXXXXXXXXXXXX` パターンに合致する文字列を使用すること。          |
| X‑dimension を 0 または負に設定       | ライブラリが `ArgumentOutOfRangeException` をスロー | 最低 1 ピクセルを使用し、対象プリンターで事前テストすること。          |
| 読み取り専用フォルダーに保存           | `Save` 時に `UnauthorizedAccessException` が発生 | 書き込み可能なディレクトリを選択するか、適切な権限でアプリを実行する。 |
| `BarCodeReader` を破棄し忘れる        | 長時間稼働サービスでメモリリークが発生       | `using` ブロックでラッパーするか、手動で `Dispose()` を呼び出す。      |

早期にこれらを対処すればデバッグ時間を削減でき、運用の安定性が向上します。

## 完全なソースコードまとめ

以下は **バーコードジェネレータ例** を最初から最後まで実装した、コピーしてすぐに使える完全プログラムです。

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;
using Aspose.BarCode.BarCodeRecognition;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // Create generator – how to create databar
            BarcodeGenerator generator = new BarcodeGenerator(
                EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");

            // Adjust barcode dimensions
            generator.Parameters.Barcode.XDimension.Pixels = 2;   // thin bar width
            generator.Parameters.Barcode.BarHeight.Pixels = 30; // how to change height

            // Optional visual tweaks
            generator.Parameters.ImageOptions.ForeColor = System.Drawing.Color.Black;
            generator.Parameters.ImageOptions.BackColor = System.Drawing.Color.White;

            // Save image – create barcode image c#
            string filePath = "DatabarOmniDirectional.png";
            generator.Save(filePath, BarCodeImageFormat.Png);
            Console.WriteLine($"Barcode saved to {filePath}");

            // Validate barcode (optional)
            using (BarCodeReader reader = new BarCodeReader(filePath, DecodeType.DatabarOmniDirectional))
            {
                if (reader.Read())
                    Console.WriteLine($"Validation succeeded: {reader.GetCodeText()}");
                else
                    Console.WriteLine("Validation failed – barcode may be unreadable.");
            }
        }
    }
}
```

このプログラムを実行すると、次のような PNG ファイルが生成されます（イラスト例）:

![C# で生成された DataBar Omni‑Directional バーコード](https://example.com/og-image.png "C# で生成された DataBar Omni‑Directional バーコード")

*画像の代替テキスト*: **C# で生成された DataBar Omni‑Directional バーコード**（`og_image_alt` と一致）。

## 結論

これで **バーコードジェネレータ例** が完成し、バーコードの高さ変更、DataBar Omni‑Directional シンボルの作成、そして最適なスキャンを実現するための **adjust barcode dimensions** が実装できました。完全な C# コードは PNG 画像を保存し、検証も行い、バルク生成や Web サービスへの統合にも拡張可能です。

次は、**Aspose.BarCode を使った QR コード作成**、**複数バーコード値のバッチ処理**、または **PDF 文書へのバーコード埋め込み** など、同じ基礎を活かしたトピックを探求してください。

Happy coding, and may your barcodes always be scannable!

## 次に学ぶべきこと

以下のチュートリアルは、本ガイドで示したテクニックを応用した関連トピックを扱っています。各リソースには、ステップバイステップの解説と完全動作コード例が含まれており、API の追加機能習得や代替実装アプローチの探求に役立ちます。

- [Barcode Generator Example – Build DataBar Image in C#](/barcode/english/python-java/general/barcode-generator-example-build-databar-image-in-c/)
- [How to Generate and Adjust Barcode Height for One-Dimensional Databar using Aspose.BarCode for .NET](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-barcode-height-adjustment/)
- [Barcode generator example in C# – set width and height](/barcode/english/python-java/general/barcode-generator-example-in-c-set-width-and-height/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}