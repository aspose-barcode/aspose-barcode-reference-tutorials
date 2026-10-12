---
category: general
date: 2026-09-19
description: C#でバーコードを生成する方法（ステップバイステップガイド）。PDF417バーコードの設定をカスタマイズし、C#開発者がすぐに使用できるバーコード画像を作成する方法を学びましょう。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to generate barcode
- customize pdf417 barcode
- create barcode image c#
language: ja
lastmod: 2026-09-19
og_description: C#でバーコードを生成する方法（詳細な手順付き）。PDF417バーコードのパラメータをカスタマイズし、今日からC#プロジェクトで使用できるバーコード画像を作成します。
og_image_alt: Screenshot of a generated MicroPDF417 barcode image created with C#
  code
og_title: C#でバーコードを生成し、PDF417バーコードをカスタマイズする方法
schemas:
- author: Aspose
  dateModified: '2026-09-19'
  description: How to generate barcode in C# with a step‑by‑step guide. Learn to customize
    PDF417 barcode settings and create a barcode image C# developers can use instantly.
  headline: How to generate barcode and customize PDF417 barcode in C#
  type: TechArticle
- description: How to generate barcode in C# with a step‑by‑step guide. Learn to customize
    PDF417 barcode settings and create a barcode image C# developers can use instantly.
  name: How to generate barcode and customize PDF417 barcode in C#
  steps:
  - name: Check that the X‑dimension is not set below 1 pixel (some scanners cannot
      resolve sub‑pixel modules).
    text: Check that the X‑dimension is not set below 1 pixel (some scanners cannot
      resolve sub‑pixel modules).
  - name: Ensure the output file is not corrupted—re‑run the program and compare file
      sizes.
    text: Ensure the output file is not corrupted—re‑run the program and compare file
      sizes.
  - name: Increase `ErrorLevel` to improve tolerance.
    text: Increase `ErrorLevel` to improve tolerance.
  type: HowTo
tags:
- barcode
- C#
- pdf417
title: C#でバーコードを生成し、PDF417バーコードをカスタマイズする方法
url: /ja/net/compact-pdf417-encoding/how-to-generate-barcode-and-customize-pdf417-barcode-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# C# でバーコードを生成し、PDF417 バーコードをカスタマイズする方法

.NET アプリケーションで **バーコードの生成方法** が必要な場合、このチュートリアルでは、完全で実行可能なソリューションを示します。PDF417 バーコードのサイズをカスタマイズし、列数を選択し、最終的に **C# でバーコード画像を作成** してプロジェクトに直接埋め込む方法を学びます。

バーコードの生成には複雑なビルドパイプラインは不要です。このガイドの最後までに、必要なサイズと解像度に正確に合わせた MicroPDF417 バーコードを含む PNG ファイルが手に入ります。

## 前提条件

* .NET 6.0 SDK 以降（コードは .NET Framework 4.6+ でも動作します）
* Visual Studio 2022（またはお好みの C# エディタ）
* Aspose.BarCode for .NET NuGet パッケージ – 以下でインストール  
  `dotnet add package Aspose.BarCode`

追加の外部ツールは必要ありません。

## 手順 1: プロジェクトのセットアップと名前空間のインポート

新しいコンソールプロジェクトを作成し、Aspose.BarCode の参照を追加します。

```bash
dotnet new console -n BarcodeDemo
cd BarcodeDemo
dotnet add package Aspose.BarCode
```

`Program.cs` を開き、必要な `using` ディレクティブを追加します：

```csharp
using System;
using Aspose.BarCode.Generation;   // Provides BarcodeGenerator and EncodeTypes
using Aspose.BarCode;               // Contains BarCodeImageFormat enum
```

これらの名前空間は、**バーコードの生成方法** を可能にし、PDF417 固有のオプションを制御できるクラスを公開します。

## 手順 2: 任意のテキストで MicroPDF417 ジェネレータを初期化する

最初の行は、MicroPDF417 シンボロジー用に設定された `BarcodeGenerator` インスタンスを作成します。コンストラクタはエンコードタイプと、エンコードしたいデータ文字列を受け取ります。

```csharp
// Step 2: Create a MicroPDF417 barcode generator with the desired text
BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MicroPdf417, "Sample");
```

**重要なポイント:** MicroPDF417 はフル PDF417 標準のコンパクト版で、ラベルやモバイル画面など小さな領域に最適です。正しい `EncodeTypes` でジェネレータを初期化することで、ライブラリが適切なエンコードアルゴリズムを使用します。

## 手順 3: より細かい解像度のために X‑dimension（モジュール幅）をカスタマイズする

X‑dimension は単一のバーコードモジュール（最小の黒または白のバー）の幅を制御します。低いピクセル値に設定すると、より高解像度の画像が得られます。

```csharp
// Step 3: Set the X‑dimension (module width) in pixels for finer resolution
generator.Parameters.Barcode.XDimension.Pixels = 2;
```

**重要なポイント:** X‑dimension が大きいと、低解像度スキャナでも読み取りやすくなります。一方、値を小さくすると限られたスペースにより多くのデータを詰め込めます。スキャン環境に応じてこの値を調整してください。

## 手順 4: バーコードサイズを制御する列数を定義する

MicroPDF417 は 1‑4 列をサポートします。列数を増やすと短くて幅の広いバーコードになり、列数を減らすと高くて狭いバーコードになります。

```csharp
// Step 4: Define the number of columns (1‑4 are allowed) to control barcode size
generator.Parameters.Barcode.Pdf417.Columns = 4;
```

**重要なポイント:** 適切な列数を選択することで、手動でスケーリングせずに特定の UI 要素や印刷ラベルにバーコードを収められます。

## 手順 5: バーコードを PNG 画像として保存する

最後に、生成したバーコードをディスクに書き込みます。PNG はロスレス品質を保つため、鮮明なスキャンに重要です。

```csharp
// Step 5: Save the generated barcode as a PNG image
string outputPath = @"C:\Barcodes\MicroPdf417.png";
generator.Save(outputPath, BarCodeImageFormat.Png);
Console.WriteLine($"Barcode saved to {outputPath}");
```

対象ディレクトリが存在しない場合、`Save` メソッドは `ArgumentException` をスローします。簡単なチェックでこれを防げます：

```csharp
if (!System.IO.Directory.Exists(@"C:\Barcodes"))
{
    System.IO.Directory.CreateDirectory(@"C:\Barcodes");
}
```

### 完全なソースコード

各パーツを組み合わせた、完全で実行可能なプログラムは以下の通りです：

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Create a MicroPDF417 barcode generator with the desired text
            BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MicroPdf417, "Sample");

            // 2️⃣ Set the X‑dimension (module width) in pixels for finer resolution
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // 3️⃣ Define the number of columns (1‑4 are allowed) to control barcode size
            generator.Parameters.Barcode.Pdf417.Columns = 4;

            // Ensure the output folder exists
            string folder = @"C:\Barcodes";
            if (!System.IO.Directory.Exists(folder))
                System.IO.Directory.CreateDirectory(folder);

            // 4️⃣ Save the generated barcode as a PNG image
            string outputPath = System.IO.Path.Combine(folder, "MicroPdf417.png");
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"Barcode saved to {outputPath}");
        }
    }
}
```

このプログラムを実行すると、**MicroPdf417.png** という名前のファイルが生成され、以下のスクリーンショット（省略）と同様の外観になります。バーコードはテキスト *Sample* をエンコードし、設定した X‑dimension と列数を反映します。

## その他の PDF417 オプションのカスタマイズ

このガイドはサイズに影響する **PDF417 バーコードのカスタマイズ** パラメータに焦点を当てていますが、Aspose.BarCode には他にも多数の設定があります。

| Property | Purpose | Typical values |
|----------|---------|----------------|
| `generator.Parameters.Barcode.Pdf417.Rows` | 行数（高さ）を制御 | 3‑30 |
| `generator.Parameters.Barcode.Pdf417.ErrorLevel` | 誤り訂正レベルを設定（数値が大きいほど耐性が向上） | 0‑8 |
| `generator.Parameters.Barcode.Pdf417.Truncated` | 終端パターンなしの短縮バーコードを生成 | `true`/`false` |
| `generator.Parameters.Barcode.Pdf417.CompactionMode` | 数字、テキスト、バイトのいずれかの圧縮モードを選択 | `CompactionModes.Numeric` など |

**プロのコツ:** 固定幅に収めるバーコードが必要な場合、まず `Columns` を増やし、`XDimension` を減らします。スキャナがシンボルの欠落を報告したら、`ErrorLevel` を上げて冗長性を高めましょう。

## エッジケースの処理

* **MicroPDF417 のテキストが長すぎる:** Micro バリアントは最大 1 KB のデータをサポートします。文字列がこの上限を超える場合、`EncodeTypes.MicroPdf417` を `EncodeTypes.Pdf417` に変更してフル `Pdf417` シンボロジーに切り替えてください。
* **サポートされていない画像形式:** `BarCodeImageFormat` は `Jpeg`、`Bmp`、`Gif` もサポートしています。下流の処理パイプラインに合った形式を選択してください。
* **クロスプラットフォームのパス:** Linux や macOS を対象にする場合は、ハードコーディングされたバックスラッシュの代わりに `Path.Combine` を使用してください。

## バーコードの検証

任意の標準的なバーコードスキャナアプリ（モバイルまたはデスクトップ）で生成画像を検証できます。スキャナは元のテキスト **Sample** を返すはずです。失敗した場合は、以下を確認してください。

1. X‑dimension が 1 ピクセル未満に設定されていないか確認してください（サブピクセルモジュールを解像できないスキャナがあります）。
2. 出力ファイルが破損していないか確認し、プログラムを再実行してファイルサイズを比較してください。
3. `ErrorLevel` を上げて耐性を向上させます。

## 結論

これで、Aspose.BarCode を使用して C# で **バーコードの生成方法**、**PDF417 バーコードのサイズと列数のカスタマイズ方法**、そして **C# でバーコード画像を作成** してプロジェクトに直接埋め込む方法が分かりました。完全なサンプルは、プロジェクトのセットアップから最終的な PNG 出力までの実践的なワークフローを示しています。

次に、`EncodeTypes` 列挙値を変更して QR、Code128、DataMatrix など他のシンボロジーを試してみてください。`Resolution` や `Margin` といった追加パラメータを調整すれば、あらゆるバーコードを特定のアプリケーションに合わせて微調整できます。

コーディングを楽しんで、バーコードで次の自動化プロジェクトを強化しましょう！

## 次に学ぶべきことは？

以下のチュートリアルは、本ガイドで示した手法を基にした密接に関連するトピックを取り上げています。各リソースには、ステップバイステップの解説と完全な動作コード例が含まれており、追加の API 機能を習得し、独自プロジェクトで代替実装アプローチを探求するのに役立ちます。

- [C# で Aspose を使用して PDF417 バーコード画像を生成する方法](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-image-in-c-with-aspose/)
- [Aspose で PDF417 バーコードを作成する方法 – 完全ステップバイステップガイド](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-with-aspose-complete-step-by-st/)
- [C# でバーコードを保存する方法 – PDF417 バーコードの生成](/barcode/english/net/compact-pdf417-encoding/how-to-save-barcode-in-c-generate-pdf417-barcodes/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}