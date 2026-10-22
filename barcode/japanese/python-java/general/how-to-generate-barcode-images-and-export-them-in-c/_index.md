---
category: general
date: 2026-10-21
description: Aspose.BarCode を使用して C# でバーコード画像を生成し、バーコードファイルを PNG としてエクスポートする方法を学び、迅速で信頼性の高い結果を得ましょう。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to generate barcode
- how to export barcode
language: ja
lastmod: 2026-10-21
og_description: C#でバーコード画像を生成し、バーコードファイルをPNGとしてエクスポートする方法。Aspose.BarCodeを使用してPlanetおよびRM4SCCバーコードを作成する完全なチュートリアルをご覧ください。
og_image_alt: Screenshot showing how to generate barcode images with C# code
og_title: C#でバーコード画像を生成しエクスポートする方法 – ステップバイステップガイド
schemas:
- author: Aspose
  dateModified: '2026-10-21'
  description: Learn how to generate barcode images in C# and how to export barcode
    files as PNG using Aspose.BarCode for fast, reliable results.
  headline: How to generate barcode images and export them in C#
  type: TechArticle
tags:
- barcode generation
- C#
- Aspose.BarCode
title: C#でバーコード画像を生成し、エクスポートする方法
url: /ja/python-java/general/how-to-generate-barcode-images-and-export-them-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# C# でバーコード画像を生成しエクスポートする方法

.NET アプリケーションで **バーコードを生成する方法** の画像が必要な場合、本ガイドでは Planet と RM4SCC バーコードの作成手順と、**バーコードをエクスポートする方法** を PNG ファイルとして保存する手順を正確に示します。すぐに実行できるコードサンプル、各設定の説明、一般的な落とし穴に対するヒントが得られます。

このチュートリアルでは以下を取り上げます:

* Aspose.BarCode NuGet パッケージの追加
* モジュール幅とオプションのバー高さの設定
* 生成したバーコードをディスクに保存
* 出力ファイルの検証

> **前提条件** – .NET 6+ SDK、Visual Studio 2022（または任意の IDE）、および Aspose.BarCode パッケージをダウンロードするためのインターネット接続。

## 本記事で達成できること

この記事の最後までに、次のことができるようになります:

* 自動バー高さで **Planet** バーコードを生成する。
* 自動バー高さで **RM4SCC** バーコードを生成する。
* デフォルトの高さを上書きし、100 ピクセルの高さのバーコードを作成する。
* 任意のフォルダーに各バーコードを PNG ファイルとしてエクスポートする。

## 手順 1: Aspose.BarCode のインストール

プロジェクトフォルダーでターミナルを開き、次のコマンドを実行します:

```bash
dotnet add package Aspose.BarCode
```

このパッケージは、以下のコードで使用する `BarcodeGenerator` クラスと `EncodeTypes` 列挙体を提供します。

## 手順 2: 出力フォルダーの設定

PNG ファイルを保存するフォルダーを作成します。フォルダーは絶対パスでも、プロジェクトルートからの相対パスでも構いません。

```csharp
// Define the folder where barcode images will be saved
string outputFolder = Path.Combine(Environment.CurrentDirectory, "Barcodes");

// Ensure the directory exists
Directory.CreateDirectory(outputFolder);
```

> **ヒント:** `Path.Combine` を使用すると、ハードコードされたパス区切り文字を回避でき、Windows、macOS、Linux で動作します。

## 手順 3: 自動バー高さでバーコードを生成する

バー高さを指定しない場合、Aspose.BarCode はエンコードされたデータに合わせたサイズを自動的に選択します。以下のコードは、4 ピクセルのモジュール幅を使用して Planet と RM4SCC の 2 つのバーコードを作成します。

```csharp
using Aspose.BarCode.Generation;

// Planet barcode, automatic height
var planetAuto = new BarcodeGenerator(EncodeTypes.Planet, "123456");
planetAuto.Parameters.Barcode.XDimension.Pixels = 4; // Set module width
planetAuto.Save(Path.Combine(outputFolder, "PlanetAutoHeight.png"),
                BarCodeImageFormat.Png);

// RM4SCC barcode, automatic height
var rm4sccAuto = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");
rm4sccAuto.Parameters.Barcode.XDimension.Pixels = 4; // Set module width
rm4sccAuto.Save(Path.Combine(outputFolder, "RM4SCCAutoHeight.png"),
                BarCodeImageFormat.Png);
```

**この動作の理由:**  
* `EncodeTypes.Planet` と `EncodeTypes.RM4SCC` は、ジェネレーターに使用するシンボロジーを指示します。  
* `XDimension.Pixels` は単一バーコードモジュールの幅を定義します。4 px の値はクリアでスキャン可能な画像を生成します。  
* `BarHeight` が設定されていないため、ライブラリは最適な高さを自動的に計算します。

## 手順 4: 固定 100 ピクセルのバー高さでバーコードを生成する

デザインで特定のバー高さが必要な場合、 自動計算を上書きできます:

```csharp
// Planet barcode, fixed 100‑pixel height
var planetFixed = new BarcodeGenerator(EncodeTypes.Planet, "123456");
planetFixed.Parameters.Barcode.XDimension.Pixels = 4;      // Module width
planetFixed.Parameters.Barcode.BarHeight.Pixels = 100;   // Fixed height
planetFixed.Save(Path.Combine(outputFolder, "PlanetHeight100.png"),
                 BarCodeImageFormat.Png);

// RM4SCC barcode, fixed 100‑pixel height
var rm4sccFixed = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");
rm4sccFixed.Parameters.Barcode.XDimension.Pixels = 4;      // Module width
rm4sccFixed.Parameters.Barcode.BarHeight.Pixels = 100;   // Fixed height
rm4sccFixed.Save(Path.Combine(outputFolder, "RM4SCCHeight100.png"),
                 BarCodeImageFormat.Png);
```

**固定高さが必要になる理由:**  
出荷ラベルの設計仕様では、バーコードスキャナーとの互換性を確保するために正確なバー寸法が求められることがよくあります。`BarHeight.Pixels` を設定すると、生成されるすべての画像で一貫性が保証されます。

## 手順 5: エクスポートされたファイルを確認する

プログラム実行後、`Barcodes` フォルダーには次の 4 つの PNG ファイルが格納されます:

* `PlanetAutoHeight.png`
* `RM4SCCAutoHeight.png`
* `PlanetHeight100.png`
* `RM4SCCHeight100.png`

任意のファイルを画像ビューアで開くか、PDF に埋め込んで正しく表示されることを確認してください。スキャナーがバーコードを読み取れない場合は、`XDimension.Pixels` の値を増やすか、入力文字列の長さを再確認してください。

```bash
# Example verification command (Linux/macOS)
file Barcodes/*.png
```

以下のような出力が表示されます:

```
Barcodes/PlanetAutoHeight.png: PNG image data, 180 x 100, 8-bit/color RGBA, non-interlaced
```

## よくある質問とエッジケース

| Question | Answer |
|----------|--------|
| **Can I export to formats other than PNG?** | Yes. Replace `BarCodeImageFormat.Png` with `Jpeg`, `Bmp`, `Gif`, or `Tiff`. |
| **What if my data contains characters not allowed by the symbology?** | The generator throws `ArgumentException`. Validate the input or switch to a symbology that supports the character set. |
| **How do I change the foreground/background colors?** | Set `Parameters.Barcode.ForeColor` and `Parameters.Barcode.BackColor` before calling `Save`. |
| **Is there a way to generate barcodes in memory instead of saving to disk?** | Call `GenerateBarCodeImage()` to obtain a `System.Drawing.Image` object, then manipulate or stream it as needed. |

## プロのヒント: バッチ処理

多数のバーコード（例: メーリングリスト用）を作成する必要がある場合、生成ロジックを `foreach` ループでラップします:

```csharp
var values = new[] { "001122", "334455", "667788" };
int index = 0;

foreach (var value in values)
{
    var generator = new BarcodeGenerator(EncodeTypes.Planet, value);
    generator.Parameters.Barcode.XDimension.Pixels = 4;
    generator.Save(Path.Combine(outputFolder, $"Planet_{index++}.png"),
                   BarCodeImageFormat.Png);
}
```

このパターンはコードを簡潔に保ちつつ、数千件のバーコードにもスケールします。

## 結論

これで **バーコードを生成する方法** の画像を C# で作成し、Aspose.BarCode を使用して PNG として **バーコードをエクスポートする方法** が分かりました。完全なサンプルは Planet と RM4SCC シンボロジーの自動生成と固定高さ生成の両方を示しており、あらゆるバーコード関連プロジェクトの確固たる基盤となります。

**次のステップ**

* Code128、QR、DataMatrix など、他のシンボロジーを調査する。  
* カラーカスタマイズ（`ForeColor`、`BackColor`）を試す。  
* 生成した PNG を PDF 請求書や出荷ラベルに統合するために PDF ライブラリを使用する。  

コーディングを楽しんで、バーコードがスムーズに読み取れるようにしましょう！

## 次に学ぶべきことは？

以下のチュートリアルは、本ガイドで示した手法を基にした密接に関連するトピックをカバーしています。各リソースには、ステップバイステップの解説と完全な動作コード例が含まれており、追加の API 機能を習得し、独自プロジェクトで代替実装アプローチを探求するのに役立ちます。

- [Aspose.BarCode for .NET を使用した DataMatrix バーコードの生成方法 – ステップバイステップガイド](/barcode/english/net/datamatrix-barcode-configuration/)
- [C# で GS1 バーコード画像を作成する – バーコード C# を迅速に生成する方法](/barcode/english/net/gs1-barcode-encoding/create-gs1-barcode-images-in-c-how-to-generate-barcode-c-qui/)
- [C# で Aspose.BarCode を使用してバーコード画像を生成する方法](/barcode/english/python-java/general/how-to-generate-barcode-image-with-aspose-barcode-in-c/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}