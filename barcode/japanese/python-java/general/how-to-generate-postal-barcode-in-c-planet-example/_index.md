---
category: general
date: 2026-10-28
description: C#でPlanet形式を使用して郵便バーコードを生成します。このPlanetバーコードの例では、バーコードの幅を設定し、塗りつぶされたバーと空白のバーの両方を保存する方法を示しています。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate postal barcode
- set barcode width
- planet barcode example
language: ja
lastmod: 2026-10-28
og_description: C#で郵便バーコードを生成し、完全なPlanetバーコードの例を示します。バーコードの幅の設定方法、塗りつぶしバーの作成、空バー画像の作成を学びましょう。
og_image_alt: Screenshot of a generated Planet postal barcode saved as PNG
og_title: C#で郵便バーコードを生成する – ステップバイステップガイド
schemas:
- author: Aspose
  dateModified: '2026-10-28'
  description: Generate postal barcode in C# using the Planet format. This planet
    barcode example shows how to set barcode width and save both filled and empty
    bars.
  headline: How to generate postal barcode in C# – planet example
  type: TechArticle
- description: Generate postal barcode in C# using the Planet format. This planet
    barcode example shows how to set barcode width and save both filled and empty
    bars.
  name: How to generate postal barcode in C# – planet example
  steps:
  - name: Build the project (`dotnet build`).
    text: Build the project (`dotnet build`).
  - name: Run the executable (`dotnet run`).
    text: Run the executable (`dotnet run`).
  - name: Locate `PostalPlanetFilledBars.png` and `PostalPlanetEmptyBars.png` in the
      `bin/Debug/net6.0` folder.
    text: Locate `PostalPlanetFilledBars.png` and `PostalPlanetEmptyBars.png` in the
      `bin/Debug/net6.0` folder.
  - name: Open each image; you should see a series of vertical bars representing the
      numeric string
    text: Open each image; you should see a series of vertical bars representing the
      numeric string
  type: HowTo
tags:
- barcode
- C#
- Aspose.BarCode
title: C#で郵便バーコードを生成する方法 – planet の例
url: /ja/python-java/general/how-to-generate-postal-barcode-in-c-planet-example/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# C# で郵便バーコード（Planet）を生成する方法

C# で郵便バーコードを生成する必要がある場合、このガイドが完全なソリューションを示します。数値文字列をエンコードし、バーコードの幅を設定でき、塗りつぶしバーと空白バーの両方の画像を保存する実用的な Planet バーコード例をご覧いただけます。

郵便バーコードの作成は複雑なビルドパイプラインを必要としません。このチュートリアルの最後までに、任意の .NET アプリケーションにバーコード生成を組み込み、X‑dimension をカスタマイズし、バーを塗りつぶすか空白にするかを選択できるようになります。

## 前提条件

開始する前に、以下がインストールされていることを確認してください。

* .NET 6.0 SDK 以降  
* C# 開発環境（Visual Studio、VS Code、または Rider）  
* **Aspose.BarCode for .NET** NuGet パッケージ（バージョン 23.10 以上）  

次のコマンドでパッケージを追加できます。

```bash
dotnet add package Aspose.BarCode
```

以下のコードスニペットは、ファイルの先頭に `using Aspose.BarCode.Generation;` を追加したことを前提としています。

## Planet シンボロジーで郵便バーコードを生成する

最初のステップは、Planet シンボロジーを使用する `BarcodeGenerator` インスタンスを作成することです。Planet は複数の国の郵便サービスで使用されている郵便バーコード形式です。

```csharp
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Create a Planet barcode generator with the data to encode
        BarcodeGenerator barcodeGenerator = new BarcodeGenerator(EncodeTypes.Planet, "123456");

        // Additional configuration will be applied here (see next steps)

        // Save the filled‑bars image
        barcodeGenerator.Save("PostalPlanetFilledBars.png", BarCodeImageFormat.Png);

        // Switch to empty bars and save the second image
        barcodeGenerator.Parameters.Barcode.FilledBars = false;
        barcodeGenerator.Save("PostalPlanetEmptyBars.png", BarCodeImageFormat.Png);
    }
}
```

**重要ポイント:**  
`EncodeTypes.Planet` はライブラリに Planet バーコード標準を使用させ、数値データをバーとスペースの列にエンコードします。コンストラクタにはエンコードしたいデータ文字列（この例では `"123456"`）を渡します。

プログラムを実行すると、実行ファイルの作業ディレクトリに 2 つの PNG ファイルが生成されます。

* **PostalPlanetFilledBars.png** – バーが黒い実線の長方形として描画されます。  
* **PostalPlanetEmptyBars.png** – バーが黒い輪郭だけの白い長方形として描画され、暗い背景への印刷に適しています。

## ピクセル単位でバーコード幅（X‑dimension）を設定する

バーコードの視覚的サイズは X‑dimension で制御され、1 本のバーの幅を定義します。この値を調整することで、意図した印刷解像度で正しくスキャンできるようになります。

```csharp
// Define the width of each bar (X‑dimension) in pixels
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 4;
```

**設定すべき理由:**  
X‑dimension を大きくすると低解像度スキャナでもスキャンしやすくなり、逆に小さくすると高密度印刷向けに画像サイズが縮小されます。デフォルト幅は 2 ピクセルで、4 ピクセルがデスクトッププリンタ向けの一般的な妥協点です。

さまざまな値で試すことができます。

| ピクセル | 主な使用例 |
|----------|------------|
| 2        | 高密度ラベル |
| 4        | 標準的なオフィス印刷 |
| 6‑8      | 大判サイネージ |

**ヒント:** X‑dimension を変更したら、必ず対象スキャナで生成されたバーコードをテストしてください。

## Planet バーコード例 – 塗りつぶしバーと空白バー

Planet バーコードは、実線（塗りつぶし）バーまたは輪郭（空白）バーのいずれかで描画できます。`FilledBars` プロパティでこの動作を切り替えます。

```csharp
// Save the barcode with the default filled bars
barcodeGenerator.Save("PostalPlanetFilledBars.png", BarCodeImageFormat.Png);

// Configure the generator to produce empty (unfilled) bars
barcodeGenerator.Parameters.Barcode.FilledBars = false;

// Save the barcode with empty bars
barcodeGenerator.Save("PostalPlanetEmptyBars.png", BarCodeImageFormat.Png);
```

**空白バーを選ぶ理由:**  
空白バーは暗色の包装材上でコントラストが向上します。各バーの白い内部が暗い背景に対して目立つためです。塗りつぶしバーはデフォルトで、明るい媒体に適しています。

**期待される出力:**  

*両画像は同じエンコードデータ（`123456`）を表示します。* 視覚的な違いはバーのスタイルだけです。以下はテキストでの説明です。

* **塗りつぶしバー画像:** 白背景に黒い実線の縦バー。  
* **空白バー画像:** 同じパターンの黒い輪郭で、内部は白。

PNG ファイルは任意の画像ビューアで開き、パターンが Planet 仕様に合致していることを確認できます。

## 追加のバーコードプロパティをカスタマイズする（任意）

上記の基本手順でほとんどのシナリオはカバーできますが、他の設定を微調整したい場合があります。

| プロパティ | 説明 | 一般的な値 |
|------------|------|------------|
| `Barcode.Color` | バーの前景色 | `System.Drawing.Color.Black` |
| `Barcode.BackgroundColor` | 背景の塗りつぶし色 | `System.Drawing.Color.White` |
| `Barcode.CodeText` | バーコード下に表示される人が読めるテキスト | エンコードデータと同じかカスタムラベル |
| `Barcode.ImageFormat` | 出力形式（PNG、JPEG、BMP など） | `BarCodeImageFormat.Png` |

前景色をカスタムカラーに設定する例:

```csharp
barcodeGenerator.Parameters.Barcode.Color = System.Drawing.Color.DarkBlue;
```

これらのオプション調整により、企業ブランディングに合わせたり、特定の印刷要件を満たしたりできます。

## よくある落とし穴と回避策

| 問題 | 原因 | 対策 |
|------|------|------|
| バーコードが読めない | X‑dimension がプリンタの DPI に対して小さすぎる | `XDimension.Pixels` を 4 以上に増やす |
| 画像ファイルが破損している | 書き込み権限が対象フォルダにない | 絶対パスを使用するか、ディレクトリが存在することを確認 |
| シンボロジーが間違っている | `EncodeTypes.Code128` を渡している | `EncodeTypes.Planet` が使用されているか確認 |

**プロのコツ:** 本番環境にデプロイする前に、必ずテスト用バーコードを生成し、対象ハードウェアでスキャンして確認してください。

## 完全な実行可能サンプル

以下は、これまで説明したすべての手順を組み込んだ自己完結型コンソールアプリケーションです。新しい .NET コンソールプロジェクトにコードを貼り付け、実行すると出力フォルダに 2 つの PNG ファイルが生成されます。

```csharp
using System;
using Aspose.BarCode.Generation;

namespace PostalBarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Create a Planet barcode generator with the data to encode
            BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Planet, "123456");

            // 2️⃣ Set the width of each bar (X‑dimension) to 4 pixels
            generator.Parameters.Barcode.XDimension.Pixels = 4;

            // 3️⃣ Save the barcode with the default filled bars
            generator.Save("PostalPlanetFilledBars.png", BarCodeImageFormat.Png);
            Console.WriteLine("Saved filled‑bars barcode as PostalPlanetFilledBars.png");

            // 4️⃣ Configure the generator to produce empty (unfilled) bars
            generator.Parameters.Barcode.FilledBars = false;

            // 5️⃣ Save the barcode with empty bars
            generator.Save("PostalPlanetEmptyBars.png", BarCodeImageFormat.Png);
            Console.WriteLine("Saved empty‑bars barcode as PostalPlanetEmptyBars.png");
        }
    }
}
```

**検証手順:**  

1. プロジェクトをビルドする（`dotnet build`）。  
2. 実行ファイルを起動する（`dotnet run`）。  
3. `bin/Debug/net6.0` フォルダ内に `PostalPlanetFilledBars.png` と `PostalPlanetEmptyBars.png` が作成されていることを確認。  
4. 各画像を開くと、数値文字列を表す縦バーの列が表示されます。

## 次に学ぶべきことは？

以下のチュートリアルは、本ガイドで示した手法を基にした関連トピックを扱っています。各リソースには、ステップバイステップの解説と完全なコード例が含まれており、追加の API 機能を習得したり、代替実装アプローチを自分のプロジェクトで試したりするのに役立ちます。

- [塗りつぶしバーと空白バーの Planet バーコードの作成方法](/barcode/english/python-java/general/how-to-create-planet-barcode-with-filled-and-empty-bars/)
- [C# で幅を設定し Planet バーコードを生成する方法](/barcode/english/python-java/general/how-to-set-width-and-generate-a-planet-barcode-in-c/)
- [C# で郵便バーコードを作成 – 完全ジェネレータ例](/barcode/english/python-java/general/create-postal-barcode-in-c-full-generator-example/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}