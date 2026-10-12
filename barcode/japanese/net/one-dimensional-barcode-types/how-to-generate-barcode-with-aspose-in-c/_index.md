---
category: general
date: 2026-09-19
description: C#でAsposeを使用してバーコードを生成する方法 – Asposeでバーコードを迅速かつ確実に作成するステップバイステップガイド
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to generate barcode
- create barcode with aspose
language: ja
lastmod: 2026-09-19
og_description: C#でAsposeを使用してバーコードを生成する方法。Asposeでバーコードを作成し、MacroPdf417を設定してPNGとして保存する手順をご覧ください。
og_image_alt: Screenshot showing a MacroPdf417 barcode generated with Aspose in C#
og_title: Asposeでバーコードを生成する方法 – 完全なC#ガイド
schemas:
- author: Aspose
  dateModified: '2026-09-19'
  description: How to generate barcode using Aspose in C# – a step‑by‑step guide to
    create barcode with Aspose quickly and reliably.
  headline: How to generate barcode with Aspose in C#
  type: TechArticle
- description: How to generate barcode using Aspose in C# – a step‑by‑step guide to
    create barcode with Aspose quickly and reliably.
  name: How to generate barcode with Aspose in C#
  steps:
  - name: What if I need a different image format?
    text: Aspose supports `BarCodeImageFormat.Jpeg`, `Bmp`, `Tiff`, `Svg`, and `Pdf`.
      Just replace `BarCodeImageFormat.Png` with the desired enum value.
  - name: How do I generate multiple segments automatically?
    text: You can place the code above inside a loop, incrementing `MacroPdf417SegmentID`
      on each iteration and updating the data string. Remember to keep `MacroPdf417SegmentsCount`
      constant across all segments.
  - name: What if the data exceeds the capacity of a single MacroPdf417 symbol?
    text: MacroPdf417 is designed for large payloads, but every barcode has a theoretical
      maximum (≈ 1.1 KB per segment). Split the source file into chunks that fit this
      limit, then encode each chunk as a separate segment.
  - name: Does the checksum need to be calculated manually?
    text: Aspose can generate the CCITT‑16 checksum automatically if you set `MacroPdf417Checksum`
      to `0`. In the example we supplied a hard‑coded value for illustration; in production
      code you’d typically let the library compute it.
  - name: How can I change the barcode’s foreground/background colors?
    text: 'Use the `BarColor` and `BackColor` properties:'
  type: HowTo
tags:
- barcode
- Aspose
- C#
- .NET
title: C#でAsposeを使用してバーコードを生成する方法
url: /ja/net/one-dimensional-barcode-types/how-to-generate-barcode-with-aspose-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose を使用した C# でのバーコード生成方法

Aspose.BarCode ライブラリを使用すれば、C# でバーコードを生成するのは簡単です。このチュートリアルでは、**Aspose でバーコードを作成**する方法をステップバイステップで示し、MacroPdf417 フォーマット、一般的な外観設定、そして結果を PNG 画像として保存する方法をカバーします。

以下を学びます：

* Aspose.BarCode for .NET のインストールと参照方法  
* ファイル ID、セグメント ID、チェックサムなど MacroPdf417 固有のプロパティの設定方法  
* X‑dimension や列数などの外観オプションの調整方法  
* バーコードを画像ファイルとしてエクスポートする方法  

Aspose の事前経験は不要です—C# と Visual Studio の基本的な理解があれば始められます。

## 前提条件

開始する前に、以下を確認してください：

| 要件 | 詳細 |
|------|------|
| .NET ランタイム | .NET 6.0 以降（コードは .NET Framework 4.7+ でも動作） |
| IDE | Visual Studio 2022、Rider、または C# をサポートするエディタ |
| Aspose.BarCode | NuGet パッケージ `Aspose.BarCode`（無料トライアルまたはライセンス版） |
| 基本的な C# の知識 | `using` 文とオブジェクト初期化に慣れていること |

NuGet パッケージ マネージャーから Aspose.BarCode をプロジェクトに追加できます：

```bash
dotnet add package Aspose.BarCode
```

## C# でバーコードを生成する全体的なワークフロー

このプロセスは 4 つの論理ステップで構成されます：

1. **`BarcodeGenerator` インスタンスを作成**し、目的のエンコードタイプ（MacroPdf417）とエンコードしたいテキストを指定します。  
2. **X‑dimension や列数などの共通外観オプションを設定**します。  
3. **MacroPdf417 固有のプロパティ**（ファイル ID、セグメント ID、タイムスタンプなど）を構成します。  
4. **バーコードを任意のファイル形式（この例では PNG）に保存**します。

各ステップは以下で詳しく説明します。

## ステップ 1: MacroPdf417 用のバーコードジェネレータを作成

`BarcodeGenerator` クラスはすべてのバーコード作成タスクのエントリーポイントです。インスタンス化する際に 2 つの引数を渡します：

* `EncodeTypes.MacroPdf417` – Aspose に MacroPdf417 シンボロジーを使用させます。  
* データ文字列 – バーコード内にエンコードされるテキスト。

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;
using System;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // Step 1 – instantiate the generator with MacroPdf417 and sample data
            using (BarcodeGenerator generator = new BarcodeGenerator(
                       EncodeTypes.MacroPdf417, "Sample"))
            {
                // Subsequent steps go here
            }
        }
    }
}
```

> **なぜ重要か:** MacroPdf417 は大量のデータを保持できる二次元バーコードで、ファイル分割などのマクロ機能をサポートします。大きなファイルを分割して送信する際に便利です。

## ステップ 2: 共通のバーコード外観オプションを設定

MacroPdf417 には多くの専門的設定がありますが、視覚的密度やレイアウトは依然として制御したいです。最も一般的なパラメータは次のとおりです：

* **X‑dimension** – 最小モジュール（ピクセル）の幅。値が小さいほど画像は密になります。  
* **Columns** – 行ごとのデータ列数。数が大きいほどバーコードの高さが低くなります。

```csharp
// Step 2 – adjust appearance
generator.Parameters.Barcode.XDimension.Pixels = 2;   // 2‑pixel modules
generator.Parameters.Barcode.Pdf417.Columns = 5;    // 5 columns per row
```

> **ヒント:** ほとんどの画面表示シナリオでは `XDimension` を 2〜4 ピクセルに保ちます。低解像度プリンターでは大きめの値が可読性を向上させますが、画像サイズは大きくなります。

## ステップ 3: MacroPdf417 固有のプロパティを構成

MacroPdf417 は、巨大なファイルを複数のバーコードセグメントに分割できるメタデータフィールドのセットを提供します。以下のプロパティが一般的に必要です：

| プロパティ | 目的 |
|-----------|------|
| `MacroPdf417FileID` | ファイル全体の一意の識別子（最大8桁）。 |
| `MacroPdf417SegmentID` | 現在のセグメントのインデックス（0 から開始）。 |
| `MacroPdf417SegmentsCount` | ファイル内のセグメント総数。 |
| `MacroPdf417FileName` | 元ファイルの人間が読める名前。 |
| `MacroPdf417Checksum` | エラー検出用のオプション CCITT‑16 チェックサム。 |
| `MacroPdf417FileSize` | 元ファイルのバイト単位サイズ。 |
| `MacroPdf417TimeStamp` | ファイルが生成された時刻のタイムスタンプ。 |
| `MacroPdf417Addressee` / `MacroPdf417Sender` | 送信者/受信者を識別するためのオプション文字列。 |
| `MacroPdf417Terminator` | バーコードが最後のセグメントか（`Set`）中間か（`Unset`）を決定する。 |

```csharp
// Step 3 – set macro‑specific data
generator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;
generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;
generator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";
generator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234; // CCITT‑16 example
generator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000; // in bytes
generator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2019, 11, 1);
generator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
generator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
generator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;
```

> **これらのフィールドが有用な理由:**  
> *低帯域チャネルで大容量文書を送信する必要がある場合、文書を複数の MacroPdf417 バーコードに分割できます。受信側は各セグメントのメタデータを読み取り、元のファイルを再構築します。*

## ステップ 4: 生成したバーコードを画像として保存

Aspose は PNG、JPEG、BMP、TIFF、SVG、PDF など多数の出力形式をサポートします。PNG はロスレス形式で、Web や UI 表示に最適です。

```csharp
// Step 4 – export the barcode
string outputPath = @"C:\Barcodes\MacroPdf417.png";
generator.Save(outputPath, BarCodeImageFormat.Png);
Console.WriteLine($"Barcode saved to {outputPath}");
```

プログラムを実行すると、以下のイラストに似た PNG ファイルが生成されます。

![MacroPdf417 barcode generated with Aspose in C#](placeholder-image.png){.img-fluid alt="Aspose を使用した C# でのバーコード生成方法"}

> **期待される出力:** 300 × 150 ピクセルの PNG で、テキスト “Sample” と提供したマクロメタデータをエンコードした MacroPdf417 バーコードが表示されます。

## 完全な実行可能サンプル

すべてをまとめた完全なプログラムは以下の通りです。コピーして貼り付け、実行できます：

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;
using System;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // Create the generator for MacroPdf417
            using (BarcodeGenerator generator = new BarcodeGenerator(
                       EncodeTypes.MacroPdf417, "Sample"))
            {
                // Appearance settings
                generator.Parameters.Barcode.XDimension.Pixels = 2;
                generator.Parameters.Barcode.Pdf417.Columns = 5;

                // MacroPdf417 specific data
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
                generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;
                generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";
                generator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234;
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000;
                generator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2019, 11, 1);
                generator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
                generator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
                generator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;

                // Save as PNG
                string outputPath = @"C:\Barcodes\MacroPdf417.png";
                generator.Save(outputPath, BarCodeImageFormat.Png);
                Console.WriteLine($"Barcode saved to {outputPath}");
            }
        }
    }
}
```

`dotnet run`（または Visual Studio で **F5**）でプログラムを実行してください。実行後、PNG ファイルが存在し、エラーなく開けることを確認してください。

## よくある質問とエッジケースの対処

### 別の画像形式が必要な場合は？
Aspose は `BarCodeImageFormat.Jpeg`、`Bmp`、`Tiff`、`Svg`、`Pdf` をサポートしています。`BarCodeImageFormat.Png` を目的の列挙値に置き換えるだけです。

### 複数のセグメントを自動的に生成するには？
上記コードをループ内に配置し、各イテレーションで `MacroPdf417SegmentID` をインクリメントし、データ文字列も更新します。`MacroPdf417SegmentsCount` はすべてのセグメントで一定に保つことを忘れないでください。

### データが単一の MacroPdf417 シンボルの容量を超える場合は？
MacroPdf417 は大容量ペイロード向けに設計されていますが、シンボルごとの理論上の最大は約 1.1 KB です。この制限に収まるようにソースファイルをチャンクに分割し、各チャンクを別々のセグメントとしてエンコードしてください。

### チェックサムは手動で計算する必要がありますか？
`MacroPdf417Checksum` に `0` を設定すると、Aspose が CCITT‑16 チェックサムを自動生成します。例では説明のためにハードコードした値を使用しましたが、実運用ではライブラリに計算させるのが一般的です。

### バーコードの前景色/背景色を変更するには？
`BarColor` と `BackColor` プロパティを使用します：

```csharp
generator.Parameters.Barcode.BarColor = System.Drawing.Color.DarkBlue;
generator.Parameters.Barcode.BackColor = System.Drawing.Color.White;
```

## 結論

これで Aspose.BarCode を使用して C# で **バーコードを生成**する方法、特に MacroPdf417 シンボロジー向けに **Aspose でバーコードを作成**する手順が分かりました。インストール、外観設定、マクロ固有フィールドの構成について学びました。

## 次に学ぶべきことは？

以下のチュートリアルは、本ガイドで示したテクニックを基に、関連するトピックを深く掘り下げたものです。各リソースには完全なコード例とステップバイステップの解説が含まれており、追加の API 機能を習得したり、独自プロジェクトで代替実装アプローチを検討したりするのに役立ちます。

- [Aspose.BarCode for .NET を使用した DataMatrix バーコードの生成方法 – ステップバイステップガイド](/barcode/english/net/datamatrix-barcode-configuration/)
- [Aspose を使用した C# での PDF417 バーコード画像の生成方法](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-image-in-c-with-aspose/)
- [Aspose.BarCode for .NET を使用したカスタムアスペクト比の Aztec バーコード生成方法](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}