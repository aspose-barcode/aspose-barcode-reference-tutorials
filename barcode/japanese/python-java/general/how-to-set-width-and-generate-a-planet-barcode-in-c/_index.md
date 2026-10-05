---
category: general
date: 2026-09-16
description: Aspose.BarCode を使用して Planet バーコードを生成する際に、幅の設定方法、空白バーの作成方法、バーの塗りつぶし方法を学びましょう。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to set width
- how to make empty
- how to fill bars
- generate planet barcode
language: ja
lastmod: 2026-09-16
og_description: Aspose.BarCodeでPlanetバーコードを生成する際に、幅を設定し、空白バーを作成し、バーを塗りつぶす方法 – 完全ステップバイステップガイド.
og_image_alt: Screenshot showing how to set width for a Planet barcode in C#
og_title: C#で幅を設定し、Planetバーコードを生成する方法
schemas:
- author: Aspose
  dateModified: '2026-09-16'
  description: Learn how to set width, how to make empty bars, and how to fill bars
    when you generate Planet barcode using Aspose.BarCode.
  headline: How to set width and generate a Planet barcode in C#
  type: TechArticle
tags:
- barcode
- C#
- Aspose.BarCode
title: C#で幅を設定し、Planetバーコードを生成する方法
url: /ja/python-java/general/how-to-set-width-and-generate-a-planet-barcode-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# C# で幅を設定し Planet バーコードを生成する方法

Planet バーコードの **幅の設定方法** が必要な場合、このガイドでは完全な手順を示します。また、**空のバーの作成方法**、**バーの塗りつぶし方法**、そして Aspose.BarCode for .NET を使用した **Planet バーコードの生成方法** も確認できます。

郵便ラベルアプリケーションや郵便サービスとの統合を構築する際、郵便形式の Planet バーコードを生成することは一般的です。このチュートリアルの最後までに、同じデータ文字列を使用して塗りつぶしバー画像と空バー画像の両方を作成できる、すぐに実行可能なコンソールプログラムが手に入ります。

## 前提条件

- .NET 6.0 SDK 以降（コードは .NET Framework 4.7+ でも動作します）
- Visual Studio 2022 または任意の C# 対応 IDE
- Aspose.BarCode for .NET NuGet パッケージ（`Aspose.BarCode`）  
  インストールは以下の通り：

```bash
dotnet add package Aspose.BarCode
```

追加の設定は不要です。ライブラリが内部で画像エンコードを処理します。

## 手順 1: コンソールプロジェクトを作成しライブラリを追加する

ターミナルを開き、次のコマンドを実行します：

```bash
dotnet new console -n PlanetBarcodeDemo
cd PlanetBarcodeDemo
dotnet add package Aspose.BarCode
```

これにより `Program.cs` ファイルが作成され、そこにバーコードロジックを記述します。

## 手順 2: コードを書く – 幅を設定し Planet バーコードを生成する方法

`Program.cs` を開き、内容を以下の完全なサンプルに置き換えます：

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Data to encode – the same value is used for both images
        const string data = "123456";

        // -----------------------------------------------------------------
        // Part A: Filled‑bars version (default style)
        // -----------------------------------------------------------------
        // Step 2.1: Create a Planet barcode generator
        var filledGenerator = new BarcodeGenerator(EncodeTypes.Planet, data);

        // Step 2.2: How to set width – define the width of a single bar in pixels
        // The XDimension controls bar width; 4 pixels yields a clear, printable image
        filledGenerator.Parameters.Barcode.XDimension.Pixels = 4;

        // Step 2.3: Save the filled‑bars image (default is FilledBars = true)
        string filledPath = "PostalPlanetFilledBars.png";
        filledGenerator.Save(filledPath, BarCodeImageFormat.Png);
        Console.WriteLine($"Filled‑bars barcode saved to {filledPath}");

        // -----------------------------------------------------------------
        // Part B: Empty‑bars version (unfilled style)
        // -----------------------------------------------------------------
        // Step 3.1: Re‑instantiate the generator for the same data
        var emptyGenerator = new BarcodeGenerator(EncodeTypes.Planet, data);

        // Step 3.2: How to set width again – required after re‑instantiation
        emptyGenerator.Parameters.Barcode.XDimension.Pixels = 4;

        // Step 3.3: How to make empty – disable the filled‑bars flag
        emptyGenerator.Parameters.Barcode.FilledBars = false;

        // Step 3.4: Save the empty‑bars image
        string emptyPath = "PostalPlanetEmptyBars.png";
        emptyGenerator.Save(emptyPath, BarCodeImageFormat.Png);
        Console.WriteLine($"Empty‑bars barcode saved to {emptyPath}");

        // -----------------------------------------------------------------
        // Verification output
        // -----------------------------------------------------------------
        Console.WriteLine("Both barcodes generated successfully.");
    }
}
```

### 各ステップが重要な理由

- **幅の設定方法**: `XDimension.Pixels` プロパティは各バーの実際のサイズに直接影響します。2〜6 ピクセルの値を選択すると、画面上の可読性と印刷品質のバランスが取れます。
- **空のバーの作成方法**: `FilledBars = false` を設定すると、バーの輪郭だけが描画されます。このスタイルは「暗い背景に明るい」印刷や、紙の質感を透過させたい場合に便利です。
- **バーの塗りつぶし方法**: デフォルトの `FilledBars = true` は実線の黒バーを生成し、ほとんどの郵便スキャナーの標準です。
- **Planet バーコードの生成**: `EncodeTypes.Planet` を使用すると、米国郵便公社（USPS）が要求する Planet バーコード用の特定エンコーディングが選択されます。

## 手順 3: プログラムをビルドして実行する

プロジェクトフォルダーで次を実行します：

```bash
dotnet run
```

コンソールに以下のような出力が表示されます：

```
Filled‑bars barcode saved to PostalPlanetFilledBars.png
Empty‑bars barcode saved to PostalPlanetEmptyBars.png
Both barcodes generated successfully.
```

プロジェクトディレクトリに 2 つの PNG ファイルが生成されます：

- `PostalPlanetFilledBars.png` – 実線の黒バー（デフォルトスタイル）
- `PostalPlanetEmptyBars.png` – 輪郭だけのバー（空スタイル）

任意の画像ビューアで開き、バー幅が 4 ピクセル設定と一致していること、空バージョンが未塗りつぶしのバーであることを確認してください。

## よくある質問とエッジケース

| Question | Answer |
|----------|--------|
| *別の画像形式を使用できますか？* | はい。必要に応じて `BarCodeImageFormat.Png` を `Jpeg`、`Bmp`、または `Gif` に置き換えてください。 |
| *ラベルに対してバーコードが幅広すぎる場合はどうすればよいですか？* | `XDimension.Pixels` を減らす（例: `2` に）か、ラベルプリンターのモジュール幅を広げてください。 |
| *`Height` を手動で設定する必要がありますか？* | ライブラリはエンコーディングに基づいて高さを自動計算します。必要に応じて `Parameters.Barcode.BarHeight` で上書きできます。 |
| *空バーのスタイルはすべてのプリンターでサポートされていますか？* | ほとんどの最新のサーマルプリンターは塗りつぶしスタイルと空スタイルの両方に対応していますが、レガシーデバイスを使用する場合はテスト印刷で確認してください。 |
| *バーコードの下に人が読めるキャプションを追加するには？* | `Parameters.Caption` を使用してキャプションを有効化およびスタイル設定し、`CaptionAbove` を `false` に設定すると下部に配置されます。 |

## プロのコツ

- **同じジェネレーターを再利用**するのは、すべてのパラメータが同一の場合のみです。保存後に `FilledBars` を変更しても既存の画像には影響しないため、（示したように）再インスタンス化することでクリーンな状態が保証されます。
- **バッチ生成**: ループでコードを囲み、各イテレーションで `data` を変更して大量郵送用の Planet バーコードのシリーズを作成します。
- **パフォーマンス**: 数千件のバーコードを生成する場合、単一の `BarcodeGenerator` インスタンスを作成し、必要に応じて `XDimension` と `FilledBars` を調整してオブジェクトを再利用することでメモリ割り当てを削減します。

## 結論

これで **幅の設定方法**、**空バーの作成方法**、**バーの塗りつぶし方法**、そして Aspose.BarCode を使用した C# での **Planet バーコードの生成手順** が分かりました。完全な実行可能サンプルは、塗りつぶしバーと空バーの PNG ファイルの両方を生成し、任意の郵便ラベルワークフローに統合できる状態です。

次に、**同じラベルに QR コードを追加する方法**、**バーコードの色をカスタマイズする方法**、または **バーコードを PDF 文書に埋め込む方法** といった関連トピックを探求してください。これらはすべて本ガイドで扱った基本に基づいています。コーディングを楽しんでください！

## 次に学ぶべきことは？

以下のチュートリアルは、本ガイドで示した手法を基にした密接に関連するトピックを取り上げています。各リソースには、ステップバイステップの解説と完全な動作コード例が含まれており、追加の API 機能を習得し、プロジェクトでの代替実装方法を検討するのに役立ちます。

- [C# で Planet バーコード画像を作成 – 郵便バーコードの生成方法](/barcode/english/python-java/general/create-planet-barcode-image-in-c-how-to-generate-postal-barc/)
- [Java で空バー付き Code128 バーコードを作成する方法](/barcode/english/java/image-manipulation/generating-barcode-empty-bars/)
- [Java で Aspose.BarCode を使用してバーコード画像を生成する方法](/barcode/english/java/barcode-rendering-techniques/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}