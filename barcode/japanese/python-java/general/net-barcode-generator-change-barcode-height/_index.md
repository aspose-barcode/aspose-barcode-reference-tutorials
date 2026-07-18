---
category: general
date: 2026-07-18
description: .NETのバーコードジェネレータでバーコード画像を生成する方法と、GS1‑Databar Omni‑Directionalシンボルのバーコード高さを簡単に変更する方法を学びましょう。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- .net barcode generator
- how to generate barcode
- change barcode height
- GS1‑Databar Omni‑Directional
- barcode image export
language: ja
lastmod: 2026-07-18
og_description: .NET バーコードジェネレーターは、バーコード画像を迅速に作成できます。このガイドでは、バーコードの生成方法、バーの高さの調整、PNG
  ファイルの保存方法を示します。
og_image_alt: Screenshot of a .net barcode generator output showing different bar
  heights
og_title: .NET バーコードジェネレータでバーコードの高さを変更する
schemas:
- author: Aspose
  dateModified: '2026-07-18'
  description: Learn how to generate barcode images with a .net barcode generator
    and easily change barcode height for GS1‑Databar Omni‑Directional symbols.
  headline: .net barcode generator – change barcode height
  type: TechArticle
- description: Learn how to generate barcode images with a .net barcode generator
    and easily change barcode height for GS1‑Databar Omni‑Directional symbols.
  name: .net barcode generator – change barcode height
  steps:
  - name: Why each line matters
    text: '| Line | Reason | |------|--------| | `BarcodeGenerator generator = new
      BarcodeGenerator(...);` | Instantiates the **.net barcode generator** with the
      desired symbology and data payload. The `EncodeTypes.DatabarOmniDirectional`
      enum tells the library to use the GS1‑Databar Omni‑Directional format. |'
  - name: Adjusting the X‑dimension for larger prints
    text: '```csharp generator.Parameters.Barcode.XDimension.Pixels = 4; // Double
      the narrow bar width ``` Increasing the X‑dimension makes the whole barcode
      larger without altering the encoded data. This is handy when you print on large
      labels.'
  - name: Switching output formats
    text: '```csharp generator.Save($"{outFolder}/Databar.svg", BarCodeImageFormat.Svg);
      ``` SVG scales infinitely, which is perfect for web‑based scanners that need
      crisp vectors.'
  - name: Adding human‑readable text
    text: '```csharp generator.Parameters.Barcode.CodeTextVisible = true; generator.Parameters.Barcode.CodeTextAlignment
      = CodeLocation.Below; ``` Enabling `CodeTextVisible` appends the raw data under
      the barcode, useful for verification during testing.'
  type: HowTo
tags:
- barcode
- .net
- image export
title: .NET バーコードジェネレーター – バーコードの高さを変更
url: /ja/python-java/general/net-barcode-generator-change-barcode-height/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# .net バーコードジェネレーター – バーコードの高さを変更する

サードパーティ製ツールを何十個も使い分けることなく、**バーコードを生成する方法**を知りたくありませんか？ .NET の世界では、驚くほどシンプルな方法があり、その鍵となるのが **.net barcode generator** です。数行の C# だけで GS1‑Databar Omni‑Directional シンボルを作成し、バーの高さを調整し、結果を PNG ファイルとして出力できます。

在庫管理システムや出荷ラベルプリンター、あるいはスキャン可能なコードが必要なアプリを作成しているなら、このチュートリアルで数分で動作するバーコードを作成できます。完全なコードを順に解説し、各設定がなぜ重要かを説明し、**バーコードの高さを変更**する方法を仕様を壊さずに示します。

## 必要なもの

- .NET 6.0 以降（API は .NET Framework 4.7+ でも同様に動作します）
- バーコードライブラリへの参照（例: Aspose.BarCode for .NET – 多くの商用キットで同じクラスが使用されています）
- 開発環境（Visual Studio、Rider、または C# 拡張機能付き VS Code）
- 書き込み権限のあるフォルダー – チュートリアルは PNG ファイルをそこに保存します

以上です。バーコードライブラリ以外に追加の NuGet パッケージは必要ありません。

## .net barcode generator を使用してバーコードの高さを変更する

以下は **完全な実行可能コンソールプログラム** です。新しい C# プロジェクトに貼り付け、出力フォルダーを調整し、F5 キーで実行してください。

```csharp
using System;
using Aspose.BarCode.Generation;   // Namespace for the barcode generator
using Aspose.BarCode;               // For BarCodeImageFormat enum

namespace BarcodeHeightDemo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Create a barcode generator for a GS1‑Databar Omni‑Directional symbol.
            // The string "(01)12345678901231" follows the GS1 Application Identifier syntax.
            BarcodeGenerator generator = new BarcodeGenerator(
                EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");

            // 2️⃣ Define common visual parameters.
            // X‑dimension controls the width of the narrowest bar; 2 pixels works well for screen display.
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // 3️⃣ Set the initial bar height to 30 pixels.
            generator.Parameters.Barcode.BarHeight.Pixels = 30;

            // 4️⃣ Save the first image – a compact barcode.
            string outFolder = @"YOUR_DIRECTORY"; // ← replace with a real path
            generator.Save($"{outFolder}/DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);

            // 5️⃣ Increase the bar height to 60 pixels for a larger, more readable code.
            generator.Parameters.Barcode.BarHeight.Pixels = 60;

            // 6️⃣ Save the second image – a taller barcode.
            generator.Save($"{outFolder}/DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);

            Console.WriteLine("Two barcode images have been generated successfully.");
        }
    }
}
```

### 各行が重要な理由

| 行 | 理由 |
|------|--------|
| `BarcodeGenerator generator = new BarcodeGenerator(...);` | 目的のシンボルとデータペイロードで **.net barcode generator** のインスタンスを作成します。`EncodeTypes.DatabarOmniDirectional` 列挙体は、ライブラリに GS1‑Databar Omni‑Directional 形式を使用するよう指示します。 |
| `XDimension.Pixels = 2;` | X‑dimension は最も細いバーの幅を表します。*2 ピクセル* に設定すると、ほとんどのモニターで鮮明な画像が得られ、ファイルサイズも小さく抑えられます。 |
| `BarHeight.Pixels = 30;` | これは **バーコードの高さを変更** するステップで、各バーの高さを決定します。30 ピクセルの高さは小さなラベルに適したデフォルトです。 |
| `generator.Save(...);` | バーコードを PNG ファイルとして保存します。PNG はロスレス形式なので、スキャナーは生成した正確なパターンを読み取れます。 |
| `BarHeight.Pixels = 60;` | ここで再び **バーコードの高さを変更** します—今回は 60 ピクセルです。`Save` を2回目に呼び出すと、ライブラリは新しい寸法でシンボルを自動的に再描画します。 |
| `Console.WriteLine(...);` | 例外が発生せずに処理が完了したことをすぐにフィードバックします。 |

> **プロのコツ:** 印刷用に高解像度の出力が必要な場合は、`BarCodeImageFormat.Png` を `BarCodeImageFormat.Tiff` に切り替え、`Resolution` プロパティを上げてください（例: `generator.Parameters.ImageResolution = 300;`）。バーの高さは引き続き尊重され、より細かい DPI で描画されます。

## 異なる設定でバーコード画像を生成する方法

上記のスニペットは基本をカバーしていますが、実際のシナリオでは追加の調整が必要になることが多いです：

### 大きな印刷向けに X‑dimension を調整する
```csharp
generator.Parameters.Barcode.XDimension.Pixels = 4; // Double the narrow bar width
```
X‑dimension を増やすと、エンコードされたデータは変わらずにバーコード全体が大きくなります。大きなラベルに印刷する際に便利です。

### 出力フォーマットの切り替え
```csharp
generator.Save($"{outFolder}/Databar.svg", BarCodeImageFormat.Svg);
```
SVG は無限にスケールできるため、鮮明なベクタが必要なウェブベースのスキャナーに最適です。

### 人が読めるテキストの追加
```csharp
generator.Parameters.Barcode.CodeTextVisible = true;
generator.Parameters.Barcode.CodeTextAlignment = CodeLocation.Below;
```
`CodeTextVisible` を有効にすると、バーコードの下に生データが付加され、テスト時の検証に役立ちます。

## **バーコードの高さを変更**する際の一般的な落とし穴

1. **高さが小さすぎる** – 一部のスキャナーは最小バー高さ（物理単位でしばしば 10 mm）を要求します。`BarHeight.Pixels` を低すぎる値に設定すると、実際のスキャナーで画像が読めなくなる可能性があります。必ず対象ハードウェアでテストしてください。
2. **X‑dimension と高さの不一致** – 非常に大きなバー高さに対し X‑dimension が極小だと、バーが伸びすぎて見た目が不自然になり、デコードエラーを引き起こすことがあります。仕様で別途指示がない限り、概ね 3:1〜5:1 のバランスを目指してください。
3. **パラメータのリセット忘れ** – ジェネレーターは保存間で状態を保持します。ある画像で `BarHeight` を変更した後、同じインスタンスを別のバーコードに再利用すると、前の高さが残ります。プロパティをリセットするか、バーコードごとに新しい `BarcodeGenerator` をインスタンス化してください。

## NuGet インストールを含むフルエンドツーエンド例

ゼロから始める場合は、以下の手順でプロジェクトを実行できるようにしてください：

```bash
dotnet new console -n BarcodeHeightDemo
cd BarcodeHeightDemo
dotnet add package Aspose.BarCode
```

自動生成された `Program.cs` を先ほどのコードブロックに置き換え、**`YOUR_DIRECTORY` を `Path.Combine(Environment.CurrentDirectory, "output")` のように置き換えることを忘れずに**。その後：

```bash
dotnet run
```

`output` フォルダーに 2 つの PNG ファイルが作成されているはずです：

- `DatabarBarHeight30Pixels.png` – コンパクトな 30 ピクセルのバーコード。
- `DatabarBarHeight60Pixels.png` – より高い 60 ピクセルのバーコード。

両画像は見た目は似ていますが、2 番目はバーが目立って長くなるため、低解像度スキャナーでも読み取りやすくなります。

![Barcode height example](/images/barcode-height.png){alt=".net barcode generator の出力（異なるバー高さを表示）"}

## まとめと次のステップ

**.net barcode generator** を使用して **バーコードを生成** する方法、**バーコードの高さを変更** プロパティの微調整、そして PNG 形式で結果を保存する方法をカバーしました。主なポイントは次のとおりです：

- 正しい `EncodeTypes` でジェネレーターをインスタンス化する。
- `XDimension` と `BarHeight` で視覚的サイズを制御する。
- 各変更後に `Save` を呼び出して新しい画像を保存する。
- 解像度やフォーマットを調整する、

## 次に学ぶべきことは？

以下のチュートリアルは、本ガイドで示した手法を基にした密接に関連するトピックを扱っています。各リソースには、ステップバイステップの解説と完全な動作コード例が含まれており、追加の API 機能を習得し、独自プロジェクトで代替実装アプローチを検討するのに役立ちます。

- [How to generate Aztec barcode with custom aspect ratio using Aspose.BarCode for .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)
- [How to create dotcode extended codetext with Aspose.BarCode for .NET](/barcode/english/net/dotcode-barcode-configuration/dotcode-extended-code-text-configuration/)
- [How to Generate DataMatrix Barcodes (ECC 200) with Aspose.BarCode for .NET](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-ecc-200-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}