---
category: general
date: 2026-08-03
description: C#でバーコードPNGを作成し、DataBar画像のアスペクト比の変更方法を学びましょう。このコードとヒントが含まれた完全な例に従ってください。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode PNG
- how to change aspect ratio
- Aspose.BarCode C#
- DataBar stacked omnidirectional
- barcode image format PNG
language: ja
lastmod: 2026-08-03
og_description: C#でバーコードPNGを作成し、DataBarバーコードのアスペクト比の変更方法を確認しましょう。このガイドでは、すぐに実行できるコードと実用的なヒントを提供します。
og_image_alt: Sample barcode PNG generated with aspect ratio 15
og_title: C#でバーコードPNGを作成 – アスペクト比制御付きの完全例
schemas:
- author: Aspose
  dateModified: '2026-08-03'
  description: Create barcode PNG in C# and learn how to change aspect ratio for DataBar
    images. Follow this complete example with code and tips.
  headline: Create barcode PNG in C# – step‑by‑step guide
  type: TechArticle
- description: Create barcode PNG in C# and learn how to change aspect ratio for DataBar
    images. Follow this complete example with code and tips.
  name: Create barcode PNG in C# – step‑by‑step guide
  steps:
  - name: How to change other visual properties?
    text: 'You can adjust foreground color, background color, or add human‑readable
      text through the `generator.Parameters.Barcode` object. For example:'
  - name: What if I need a different image format?
    text: Replace `BarCodeImageFormat.Png` with `Jpeg`, `Bmp`, or `Gif` as needed.
      PNG remains the best choice for lossless barcode images.
  - name: Does the aspect ratio affect scanning speed?
    text: Higher aspect ratios increase the barcode’s height, which can improve scan
      reliability on devices that struggle with short stacked symbols. However, extremely
      tall barcodes may not fit on small labels, so test with your target hardware.
  - name: Can I generate multiple barcodes in a loop?
    text: Yes. Create a new `BarcodeGenerator` instance for each data string or reuse
      the same instance while updating `CodeText` and `DataBar.AspectRatio`. This
      approach reduces object allocation overhead.
  type: HowTo
tags:
- barcode
- C#
- PNG
- Aspose
title: C#でバーコードPNGを作成する – ステップバイステップガイド
url: /ja/python-java/general/create-barcode-png-in-c-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# C# でバーコード PNG を作成 – ステップバイステップ ガイド

C# で **バーコード PNG を作成** したい場合は、このチュートリアルが手順をすべて示します。スタック型全方向 DataBar バーコードを生成し、PNG ファイルとして保存し、**アスペクト比の変更方法** を学んで、さまざまなスキャン環境に合わせられるようになります。

本ガイドでは、必要なパッケージ、完全に実行可能なプログラム、各設定が重要な理由の説明をすべて網羅しています。最後には、アスペクト比が 15 の PNG と 30 の PNG の 2 つのファイルが作成され、テストや本番環境で使用できる状態になります。

## 前提条件

開始する前に、以下を確認してください。

- .NET 6.0 SDK 以降がインストール済み
- Visual Studio 2022（または任意の C# IDE）
- **Aspose.BarCode** への NuGet 参照（`BarcodeGenerator` を提供するライブラリ）
- PNG ファイルを保存するディレクトリへの書き込み権限

以下のコマンドで Aspose.BarCode パッケージを追加できます。

```bash
dotnet add package Aspose.BarCode
```

## 手順 1: プロジェクトの作成と名前空間のインポート

新しいコンソール アプリケーションを作成し、バーコード生成とファイル I/O に必要な名前空間をインポートします。

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

namespace BarcodePngDemo
{
    class Program
    {
        static void Main()
        {
            // All subsequent steps are inside Main
```

**ポイント:** `Aspose.BarCode.Generation` をインポートすると `BarcodeGenerator` が利用可能になります。コードを `Main` 内に収めることで、サンプルが自己完結し、実行が容易になります。

## 手順 2: スタック型全方向 DataBar 用のバーコードジェネレータを作成

`EncodeTypes.DatabarStackedOmniDirectional` タイプとサンプルの GS1‑128 データ文字列で `BarcodeGenerator` をインスタンス化します。

```csharp
            // Step 2: Create a barcode generator for a stacked omnidirectional DataBar
            BarcodeGenerator generator = new BarcodeGenerator(
                EncodeTypes.DatabarStackedOmniDirectional,
                "(01)12345678901231");
```

**ポイント:** 選択したエンコードタイプは高密度の DataBar を生成し、最新のスキャナで読み取れます。データ文字列は GS1 アプリケーション識別子 (01) 形式で、製品識別子として一般的です。

## 手順 3: X‑ディメンション（モジュール幅）をピクセル単位で設定

モジュール幅を設定して、バーコード全体のサイズを制御します（可読性には影響しません）。

```csharp
            // Step 3: Define the X‑dimension (module width) in pixels
            generator.Parameters.Barcode.XDimension.Pixels = 2;
```

**ポイント:** X‑ディメンションを 2 ピクセルにすると、スキャナに対して小さすぎず、ラベル領域に対して大きすぎないサイズになります。

## 手順 4: アスペクト比 15 で最初の PNG を保存

DataBar のアスペクト比を調整し、画像を PNG ファイルとして保存します。

```csharp
            // Step 4: Set the DataBar aspect ratio to 15 and save the image
            generator.Parameters.Barcode.DataBar.AspectRatio = 15;
            string outputPath15 = @"YOUR_DIRECTORY\DatabarAspectRatio15.png";
            generator.Save(outputPath15, BarCodeImageFormat.Png);
            Console.WriteLine($"Barcode saved to {outputPath15} (aspect ratio 15).");
```

**ポイント:** アスペクト比はスタック型 DataBar の高さと幅の比率を決めます。比率 15 は可読性とラベル高さのバランスが取れた一般的なデフォルトです。

## 手順 5: アスペクト比を 30 に変更し、2 番目の PNG を保存

同じジェネレータ インスタンスのアスペクト比を大きくし、2 番目の画像を保存します。

```csharp
            // Step 5: Change the aspect ratio to 30 and save another image
            generator.Parameters.Barcode.DataBar.AspectRatio = 30;
            string outputPath30 = @"YOUR_DIRECTORY\DatabarAspectRatio30.png";
            generator.Save(outputPath30, BarCodeImageFormat.Png);
            Console.WriteLine($"Barcode saved to {outputPath30} (aspect ratio 30).");
        }
    }
}
```

**ポイント:** アスペクト比を上げるとバーコードが縦に伸び、低解像度デバイスや狭い媒体に印刷した場合のスキャン信頼性が向上します。

## 期待される出力

プログラムを実行すると、以下の 2 つの PNG ファイルが作成されます。

| ファイル名                           | アスペクト比 | おおよそのサイズ（ピクセル） |
|--------------------------------------|--------------|------------------------------|
| `DatabarAspectRatio15.png`           | 15           | 200 × 300（幅 × 高さ）       |
| `DatabarAspectRatio30.png`           | 30           | 200 × 600（幅 × 高さ）       |

どちらの画像も、GS1 識別子 `(01)12345678901231` をエンコードした、はっきりと読み取れる DataBar バーコードを含んでいます。

## よくある質問とエッジケース

### 他の視覚プロパティはどう変更する？

`generator.Parameters.Barcode` オブジェクトを使って前景色、背景色、ヒューマンリーダブルテキストなどを調整できます。例:

```csharp
generator.Parameters.Barcode.ForeColor = System.Drawing.Color.Black;
generator.Parameters.Barcode.BackColor = System.Drawing.Color.White;
generator.Parameters.Barcode.CodeTextParameters.ShowCodeText = true;
```

### 別の画像形式が必要な場合は？

`BarCodeImageFormat.Png` を `Jpeg`、`Bmp`、`Gif` などに置き換えてください。PNG はロスレスなバーコード画像として最適です。

### アスペクト比はスキャン速度に影響しますか？

アスペクト比が高いほどバーコードの高さが増し、短いスタックシンボルが苦手なデバイスでのスキャン信頼性が向上します。ただし、極端に高いバーコードは小さなラベルに収まらない可能性があるため、対象ハードウェアでテストしてください。

### ループで複数のバーコードを生成できますか？

可能です。各データ文字列ごとに新しい `BarcodeGenerator` を作成するか、同じインスタンスを再利用しつつ `CodeText` と `DataBar.AspectRatio` を更新します。これによりオブジェクト割り当てのオーバーヘッドが削減されます。

## プロのコツ

- **ジェネレータを再利用**: `CodeText` や `AspectRatio` だけを変更すれば、オブジェクトの再生成を避けられ、バッチ処理が高速化します。
- **出力を検証**: ハンドヘルドスキャナやモバイルアプリで生成した PNG が正しく読み取れるか確認してから本番環境に展開しましょう。
- **ファイル名にアスペクト比を含める**: テスト時にバリエーションを管理しやすくするため、例に示したようにファイル名に比率を入れます。

## 結論

これで C# で **バーコード PNG を作成** し、スタック型全方向 DataBar シンボルの **アスペクト比の変更方法** を正確に理解できました。完全なサンプルは、初期化、X‑ディメンション設定、アスペクト比操作、画像保存をすべて単一の実行可能プログラムで示しています。

ここからは、他のバーコードタイプを試したり、色をカスタマイズしたり、ジェネレータをレポートや在庫管理システムに組み込んだりして、さらに活用の幅を広げてください。コーディングを楽しんでください！


## 次に学ぶべきことは？

以下のチュートリアルは、本ガイドで示した手法を基にした、密接に関連するトピックをカバーしています。各リソースには、ステップバイステップの解説と完全なコード例が含まれており、API の追加機能を習得したり、代替実装アプローチを自プロジェクトで試したりするのに役立ちます。

- [Create Barcode PNG – DataMatrix Aspect Ratio – Aspose.BarCode](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-aspect-ratio-customization/)
- [How to generate Aztec barcode with custom aspect ratio using Aspose.BarCode for .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)
- [How to Customize Barcode - Codablock F Aspect Ratio with Aspose.BarCode for .NET](/barcode/english/net/codablock-f-encoding/codablock-f-aspect-ratio-customization/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}