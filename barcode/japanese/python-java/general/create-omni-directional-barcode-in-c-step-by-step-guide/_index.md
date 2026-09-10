---
category: general
date: 2026-07-15
description: Aspose.BarCode を使用して C# で全方向バーコードを素早く作成 – バーの高さと X 軸寸法を調整可能な C# バーコード生成方法を学びましょう。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create omni-directional barcode
- how to generate barcode c#
- GS1 DataBar Omni-Directional
- barcode XDimension
- barcode BarHeight
language: ja
lastmod: 2026-07-15
og_description: Aspose.BarCode を使用して C# で全方向バーコードを作成します。XDimension と BarHeight を調整して完璧な結果を得る方法をマスターしましょう。
og_image_alt: Screenshot showing a create omni-directional barcode generated in C#
  with 60 px bar height
og_title: C#で全方向バーコードを作成 – 完全プログラミングウォークスルー
schemas:
- author: Aspose
  dateModified: '2026-07-15'
  description: create omni-directional barcode in C# quickly with Aspose.BarCode –
    learn how to generate barcode C# with adjustable bar height and X‑dimension.
  headline: create omni-directional barcode in C# – Step‑by‑Step Guide
  type: TechArticle
- description: create omni-directional barcode in C# quickly with Aspose.BarCode –
    learn how to generate barcode C# with adjustable bar height and X‑dimension.
  name: create omni-directional barcode in C# – Step‑by‑Step Guide
  steps:
  - name: Expected output
    text: '- `DatabarBarHeight30Pixels.png` – a 30 px tall omni‑directional barcode.
      - `DatabarBarHeight60Pixels.png` – the same data, but with a 60 px tall barcode.'
  - name: What if I need a different X‑dimension?
    text: Simply assign a new value before calling `Save`. For ultra‑high‑density
      printing you might go down to 1 px, but test with your scanner first—some devices
      struggle with sub‑2 px bars.
  - name: Can I add human‑readable text below the barcode?
    text: Yes. Set `barcodeGenerator.Parameters.Barcode.CodeText` to a string and
      optionally adjust `barcodeGenerator.Parameters.Barcode.CodeLocation` to `BarCodeTextLocation.Below`.
      This is handy for retail environments where the numeric GTIN must be visible.
  - name: Is PNG the best format for printing?
    text: PNG is lossless, which preserves the sharp edges needed for barcode scanners.
      If your downstream system expects a different format (TIFF, BMP), just change
      the `BarCodeImageFormat` enum.
  type: HowTo
tags:
- barcode
- C#
- Aspose
- GS1
- DataBar
title: C#で全方向バーコードを作成する – ステップバイステップガイド
url: /ja/python-java/general/create-omni-directional-barcode-in-c-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# C# で全方向バーコードを作成 – ステップバイステップガイド

GS1 DataBar Omni‑Directional シンボロジーに準拠した C# のバーコードを生成する方法を考えたことがありますか？ あなただけではありません。このチュートリアルでは、**全方向バーコード** をゼロから作成し、X‑ディメンションを調整し、バーの高さを操作します—すべて Aspose.BarCode ライブラリを使用します。

実際のシナリオを通して説明します。小型で高密度なバーコードが小売ラベルに必要で、視覚的なサイズを完全にコントロールしたいとします。最後には、30 px のバー高さと 60 px のバー高さの PNG ファイルがそれぞれ 1 つずつ作成され、任意の印刷ワークフローにすぐに組み込めます。

## 前提条件

- .NET 6（または最近の .NET ランタイム）をマシンにインストールしてください。  
- Visual Studio 2022 または VS Code—お好みの IDE で構いません。  
- 無料の Aspose.BarCode for .NET NuGet パッケージ（`Aspose.BarCode`）。

他に依存関係は必要ありません。NuGet を使ったことがない場合は、Package Manager Console を開いて次を実行してください：

```powershell
Install-Package Aspose.BarCode
```

## 全方向バーコードの作成 – 基本を理解する

**GS1 DataBar Omni‑Directional** シンボロジーは、どの向きでもスキャンできるよう設計されており、シェルフエッジラベルに最適です。`new BarcodeGenerator(EncodeTypes.DatabarOmniDirectional, data)` を呼び出すと、ライブラリがデータのエンコード、シンボロジー規則の適用、ラスタ画像の生成という重い処理を行います。

> **Pro tip:** 常に生データを適切な Application Identifier (AI) 形式でラップしてください。例: GTIN‑14 の場合は `"(01)12345678901231"`。これによりスキャナは数字が何を表すかを認識します。

## ステップ 1 – バーコードジェネレータの設定 (how to generate barcode c#)

まずジェネレータオブジェクトを作成します。これは Aspose を使った **how to generate barcode c#** の基礎です。

```csharp
using Aspose.BarCode.Generation;

// Step 1: Create a barcode generator for the GS1 DataBar Omni‑Directional symbology
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");
```

`EncodeTypes.DatabarOmniDirectional` 列挙値は使用するシンボロジーをエンジンに指示します。第 2 引数は、すでに GTIN AI でラップされた生データ文字列です。

## ステップ 2 – X‑ディメンションの調整 (barcode XDimension)

**barcode XDimension** は最小バーの幅を制御します。2 px の値は、ほとんどのラベルプリンタで可読性とコンパクトさのバランスが取れた設定です。

```csharp
// Step 2: Define common barcode parameters (2 px X‑dimension)
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

より細かくまたは粗くしたい場合は、数値を変更するだけです。X‑ディメンションは基本単位であり、他のすべてのバー幅はこの値の倍数となります。

## ステップ 3 – 30 px のバー高さで最初の画像を作成 (barcode BarHeight)

次に **barcode BarHeight** を 30 px に設定し、画像を保存します。これにより、標準ラベルにきれいに収まるほどの控えめなサイズのバーコードが生成されます。

```csharp
// Step 3: Set a 30 px bar height and save the first image
barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 30;
barcodeGenerator.Save("YOUR_DIRECTORY/DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);
```

`Save` メソッドは PNG ファイルをディスクに書き出します。JPEG 出力が必要な場合は `BarCodeImageFormat.Jpeg` に変更してください。

## ステップ 4 – 大きなラベル用にバー高さを 60 px に増やす (barcode BarHeight)

場合によっては、スキャナから離れたシェルフラベルなど、より大きなバーコードが必要になることがあります。高さを倍にしてみましょう。

```csharp
// Step 4: Increase the bar height to 60 px for a larger barcode
barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 60;
```

ジェネレータを再作成する必要は **ありません**；パラメータを調整して同じオブジェクトを再利用するだけです。これによりメモリ使用量が抑えられ、コードがすっきりします。

## ステップ 5 – 2 番目の画像を保存 (how to generate barcode c#)

最後に 2 番目の PNG を保存します。これでバー高さが異なるだけの 2 つのファイルが手に入ります。

```csharp
// Step 5: Save the second image with the updated height
barcodeGenerator.Save("YOUR_DIRECTORY/DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);
```

### 期待される出力

- `DatabarBarHeight30Pixels.png` – 高さ 30 px の全方向バーコード。  
- `DatabarBarHeight60Pixels.png` – 同じデータですが、バー高さが 60 px のバーコードです。

任意の画像ビューアでファイルを開くと、GS1 DataBar Omni‑Directional 仕様に準拠した、鮮明でスキャン可能なバーが確認できます。

## よくある質問とエッジケース

### 別の X‑ディメンションが必要な場合は？

`Save` を呼び出す前に新しい値を代入するだけです。超高密度印刷の場合は 1 px まで下げられますが、まずスキャナでテストしてください—一部のデバイスは 2 px 未満のバーに苦戦します。

### バーコードの下に人が読めるテキストを追加できますか？

はい。`barcodeGenerator.Parameters.Barcode.CodeText` に文字列を設定し、必要に応じて `barcodeGenerator.Parameters.Barcode.CodeLocation` を `BarCodeTextLocation.Below` に変更します。小売環境で数値 GTIN を表示したいときに便利です。

```csharp
barcodeGenerator.Parameters.Barcode.CodeText = "(01)12345678901231";
barcodeGenerator.Parameters.Barcode.CodeLocation = BarCodeTextLocation.Below;
```

### 印刷に PNG が最適ですか？

PNG はロスレス形式で、バーコードスキャナに必要なシャープなエッジを保持します。下流システムが別の形式（TIFF、BMP）を要求する場合は、`BarCodeImageFormat` 列挙体を変更するだけです。

## 完全な動作例 (create omni-directional barcode)

以下は完成した、すぐに実行できるプログラムです。新しいコンソールプロジェクトに貼り付けて **F5** を押してください。

```csharp
using System;
using Aspose.BarCode.Generation;

namespace OmniDirectionalDemo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Create generator for GS1 DataBar Omni‑Directional
            BarcodeGenerator generator = new BarcodeGenerator(
                EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");

            // 2️⃣ Set X‑dimension (2 px)
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // 3️⃣ First image – 30 px height
            generator.Parameters.Barcode.BarHeight.Pixels = 30;
            generator.Save("DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);

            // 4️⃣ Second image – 60 px height
            generator.Parameters.Barcode.BarHeight.Pixels = 60;
            generator.Save("DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);

            Console.WriteLine("Two omni‑directional barcodes created successfully.");
        }
    }
}
```

プログラムを実行し、出力フォルダを確認すると、説明通りの 2 つの PNG ファイルが生成されているはずです。

## まとめ

**how to generate barcode C#** のコードを示し、Aspose.BarCode を使用して **create omni-directional barcode** を作成する方法を解説しました。**barcode XDimension** と **barcode BarHeight** を調整することで、スキャン信頼性を損なうことなく視覚的サイズを細かく制御できます。

## 次にやること

- `Color` や `Margin` など、他の **GS1 DataBar Omni-Directional** 設定を試してみてください。  
- `Graphics` を使用して、単一のキャンバス上に複数のバーコードを組み合わせ、複雑なラベルデザインを作成します。  
- ジェネレータを Web API に統合し、e‑コマースプラットフォームが必要に応じてバーコードを生成できるようにします。

何か工夫があればコメントで共有してください。会話を続けましょう。Happy coding!

## 次に学ぶべきことは？

以下のチュートリアルは、本ガイドで示したテクニックを基にした密接に関連するトピックをカバーしています。各リソースには、ステップバイステップの解説と完全な動作コード例が含まれており、追加の API 機能を習得したり、独自プロジェクトで代替実装アプローチを探求したりするのに役立ちます。

- [バーコード生成方法 – Code 39 設定（Aspose.BarCode）](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-code-39-configuration/)
- [Aspose.BarCode for .NET を使用した ITF-14 のバーコードクワイエットゾーン作成方法](/barcode/english/net/itf-14-barcode-customization/itf-14-barcode-quiet-zone-configuration/)
- [Aspose.BarCode for .NET を使用した Code 16K のバーコードクワイエットゾーン作成方法](/barcode/english/net/code-16k-encoding/code-16k-quiet-zone-settings/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}