---
category: general
date: 2026-08-03
description: Aspose.BarCode を使用して Planet バーコードを作成し、X 次元を設定して PNG 画像として保存する方法を示す C#
  バーコードジェネレータチュートリアル。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- barcode generator c#
- create planet barcode
language: ja
lastmod: 2026-08-03
og_description: BarcodeジェネレーターC#チュートリアルでは、Planetバーコードの作成、X次元の調整、そしてAspose.BarCodeを使用したPNG形式での保存方法を順を追って解説します。
og_image_alt: Screenshot of generated Planet and RM4SCC barcodes in PNG format
og_title: C# バーコードジェネレーター – Planet バーコードをステップバイステップで作成
schemas:
- author: Aspose
  dateModified: '2026-08-03'
  description: Barcode generator C# tutorial showing how to create Planet barcode
    with Aspose.BarCode, set X‑dimension, and save as PNG images.
  headline: Barcode generator C# – create Planet barcode and RM4SCC example
  type: TechArticle
tags:
- barcode
- C#
- Aspose.BarCode
title: バーコードジェネレーター C# – Planet バーコードと RM4SCC の作成例
url: /ja/python-java/general/barcode-generator-c-create-planet-barcode-and-rm4scc-example/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Barcode generator C# – create Planet barcode and RM4SCC example

郵便向けシンボルを生成できる **barcode generator C#** が必要な方へ。本ガイドでは Aspose.BarCode を使用して **Planet barcode** 画像を作成する手順を示します。X‑dimension の設定方法、対応する RM4SCC バーコードの生成、両方を PNG ファイルとして保存する方法を数ステップで解説します。

このチュートリアルは .NET 6 以降でコードを実行するために必要なすべてを網羅し、各設定が重要な理由や、モジュール幅の誤設定・ディレクトリ権限不足といった一般的な落とし穴についても説明します。最後には Planet と RM4SCC の規格に準拠した、印刷可能なバーコード画像が 2 枚得られます。

## Prerequisites

開始する前に、以下を用意してください。

* .NET 6 SDK（または Aspose.BarCode がサポートする任意の .NET バージョン）
* Visual Studio 2022 もしくはお好みの C# IDE
* **Aspose.BarCode** への NuGet 参照（`Install-Package Aspose.BarCode`）
* PNG ファイルを保存するフォルダーへの書き込み権限

追加の外部サービスは不要です。ライブラリがローカルでエンコードをすべて処理します。

## Step 1: Initialise the barcode generator C# object

最初の作業は `BarcodeGenerator` のインスタンスを作成することです。コンストラクタにはバーコードシンボル（`EncodeTypes.Planet`）とエンコードするデータを渡します。

```csharp
using Aspose.BarCode.Generation;

// Step 1: Create a Planet barcode generator with the data to encode
BarcodeGenerator planetGenerator = new BarcodeGenerator(EncodeTypes.Planet, "123456");
```

*Why this step?*  
`BarcodeGenerator` は生成するすべてのバーコードのエントリーポイントです。`EncodeTypes.Planet` を選択することで、郵便サービスで広く使用されている ISO/IEC 24723 仕様に従ったバーコードが生成されます。

## Step 2: Set the X‑dimension (module width) for the Planet barcode

X‑dimension は単一モジュール（最小のバーまたはスペース）の幅を定義します。**4 ピクセル** の値は多くのラベルプリンターでうまく機能します。

```csharp
// Step 2: Define the X‑dimension (module width) in pixels
planetGenerator.Parameters.Barcode.XDimension.Pixels = 4;
```

*Why this matters*  
モジュールが狭すぎるとバーコードが読めなくなり、広すぎるとラベルサイズが不必要に大きくなります。`Pixels` を調整することで、使用するプリンターの解像度に合わせてバーコードを微調整できます。

## Step 3: Save the Planet barcode as a PNG image

Aspose.BarCode は選択したシンボルに基づきバーコードの高さを自動計算するため、ファイルパスとフォーマットだけを指定すれば完了です。

```csharp
// Step 3: Save the Planet barcode as a PNG image (height is calculated automatically)
planetGenerator.Save("YOUR_DIRECTORY/PostalPlanetBarHeightNone.png", BarCodeImageFormat.Png);
```

*Tip*  
`YOUR_DIRECTORY` を実際に存在する絶対パスまたは相対パスに置き換えてください。ディレクトリが存在しない場合、`Save` メソッドは `DirectoryNotFoundException` をスローします。

**Expected output** – 以下のイラストに似た PNG ファイルが生成されます（実際の画像はここでは表示されませんが、数値ペイロード `123456` を持つ典型的な Planet バーコードが出力されます）。

## Step 4: Initialise a second generator for the RM4SCC barcode

多くの郵便システムでは同一郵便物に Planet と RM4SCC の両シンボルが必要です。RM4SCC 用に新しい `BarcodeGenerator` インスタンスを作成します。

```csharp
// Step 4: Create an RM4SCC barcode generator with the same data
BarcodeGenerator rm4sccGenerator = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");
```

*Why a separate instance?*  
シンボルごとに固有のパラメータが存在します。同一インスタンスを再利用すると、X‑dimension などの設定が意図せず引き継がれ、2 番目のバーコードに最適でなくなる可能性があります。

## Step 5: Configure the X‑dimension for the RM4SCC barcode

RM4SCC でも X‑dimension 設定が有効です。視覚的な一貫性を保つため、同じピクセル幅を適用します。

```csharp
// Step 5: Set the X‑dimension for the RM4SCC barcode
rm4sccGenerator.Parameters.Barcode.XDimension.Pixels = 4;
```

*Pro tip*  
より高いバーコードが必要な場合（例：大きなラベル用）には `Height.Pixels` も設定できます。未設定のままにすると、ライブラリが自動で最適な高さを計算します。

## Step 6: Save the RM4SCC barcode as a PNG image

最後に RM4SCC バーコードをディスクに保存します。

```csharp
// Step 6: Save the RM4SCC barcode as a PNG image (height is calculated automatically)
rm4sccGenerator.Save("YOUR_DIRECTORY/PostalRM4SCCBarHeightNone.png", BarCodeImageFormat.Png);
```

これで 2 つの PNG ファイル、`PostalPlanetBarHeightNone.png` と `PostalRM4SCCBarHeightNone.png` が作成されました。これらは郵便ラベルに埋め込んだり、封筒に印刷したり、サードパーティの印刷サービスに送信したりできます。

## Optional: Adjusting height or using other image formats

ワークフローで特定のバーコード高さや別の画像形式（例：JPEG や BMP）が必要な場合は、`Save` 呼び出し前にパラメータを変更します。

```csharp
// Example: set a fixed height of 100 pixels and save as JPEG
planetGenerator.Parameters.Barcode.Height.Pixels = 100;
planetGenerator.Save("PostalPlanet.jpg", BarCodeImageFormat.Jpeg);
```

**Edge case** – カスタム高さを設定する際は、ISO 標準が要求する最小高さを満たすように注意してください。満たさないとバーコードの検証に失敗する可能性があります。

## Common pitfalls and how to avoid them

| Pitfall | Why it happens | Fix |
|---------|----------------|-----|
| `DirectoryNotFoundException` | 対象フォルダーが存在しない、または名前が間違っている。 | 事前にフォルダーを作成するか、`Path.Combine` と `Environment.CurrentDirectory` を使用してください。 |
| Barcode unreadable on low‑resolution printers | プリンターの DPI に対して X‑dimension が小さすぎる。 | 203 dpi プリンターの場合は `XDimension.Pixels` を 5 – 6 に増やす、またはサンプルラベルでテストしてください。 |
| Wrong symbology used | `EncodeTypes.Code128` を指定してしまい、`EncodeTypes.Planet` ではない。 | 必要な郵便規格に合致する `EncodeTypes` 列挙値を再確認してください。 |
| Null reference on `Parameters` | Aspose.BarCode の旧バージョンを使用しており API が異なる。 | 最新の NuGet パッケージ（v23.12 以降）にアップグレードしてください。 |

## Full runnable example

以下はそのままコピーして実行できる完全なプログラムです。`using` 文、エラーハンドリング、各行の説明コメントが含まれています。

```csharp
using System;
using System.IO;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Define the output directory (change as needed)
        string outputDir = Path.Combine(Environment.CurrentDirectory, "Barcodes");
        Directory.CreateDirectory(outputDir);

        // -------- Planet barcode ----------
        var planetGenerator = new BarcodeGenerator(EncodeTypes.Planet, "123456");
        planetGenerator.Parameters.Barcode.XDimension.Pixels = 4;
        string planetPath = Path.Combine(outputDir, "PostalPlanetBarHeightNone.png");
        planetGenerator.Save(planetPath, BarCodeImageFormat.Png);
        Console.WriteLine($"Planet barcode saved to: {planetPath}");

        // -------- RM4SCC barcode ----------
        var rm4sccGenerator = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");
        rm4sccGenerator.Parameters.Barcode.XDimension.Pixels = 4;
        string rm4sccPath = Path.Combine(outputDir, "PostalRM4SCCBarHeightNone.png");
        rm4sccGenerator.Save(rm4sccPath, BarCodeImageFormat.Png);
        Console.WriteLine($"RM4SCC barcode saved to: {rm4sccPath}");
    }
}
```

プログラムを実行すると、実行ファイルと同じディレクトリに `Barcodes` フォルダーが作成され、2 つの PNG ファイルが格納されます。任意の画像ビューアで開き、出力を確認してください。

## Conclusion

これで **barcode generator C#** ソリューションが完成し、**Planet barcode** 画像の作成、最適な印刷のための X‑dimension 調整、そして対応する RM4SCC バーコードの生成が数行のコードで実現できました。この手法は .NET 6+ で動作し、必要なのは Aspose.BarCode の NuGet パッケージだけです。`EncodeTypes` の値を変更すれば、Code128、QR、DataMatrix など他のシンボルにも簡単に拡張できます。

### What’s next?

* プリンターの DPI に合わせて `XDimension.Pixels` の値を試行錯誤してください。
* `BarCodeImageFormat` 列挙体を変更して、PDF や SVG など別形式でバーコードを生成してください。
* **SkiaSharp** などのグラフィックライブラリを使い、2 つの PNG を 1 枚のラベルに結合してください。
* チェックサム検証やカスタムフォントといった高度な機能は、Aspose.BarCode API 全体を探索してみましょう。

コードをバッチ処理向けに改造したり、オンデマンドでバーコード画像を返す ASP.NET Core Web サービスに組み込んだりしても構いません。Happy coding!

## What Should You Learn Next?

以下のチュートリアルは、本ガイドで示したテクニックを応用した関連トピックを扱っています。各リソースには完全な動作コード例とステップバイステップの解説が含まれており、API の追加機能習得や代替実装アプローチの探求に役立ちます。

- [Create Barcode PNG – DataMatrix Aspect Ratio – Aspose.BarCode](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-aspect-ratio-customization/)
- [How to Save PNG using DataMatrix C40 with Aspose.BarCode](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-c40/)
- [barcode generator tutorial c# – Customize Code 16K Barcode Aspect Ratios with Aspose.BarCode for .NET](/barcode/english/net/code-16k-encoding/code-16k-aspect-ratio-customization/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}