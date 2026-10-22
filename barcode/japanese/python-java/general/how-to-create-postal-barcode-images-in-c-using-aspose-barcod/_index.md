---
category: general
date: 2026-10-21
description: Aspose.BarCode を使用して C# で郵便バーコード画像の作成方法を学びましょう – Planet と RM4SCC バーコードを生成し、バーの塗りつぶしを制御し、PNG
  ファイルとして保存します。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create postal barcode
- generate planet barcode
- how to generate barcode c#
language: ja
lastmod: 2026-10-21
og_description: Aspose.BarCode を使用して C# で郵便バーコード画像を作成します。このチュートリアルでは、Planet と RM4SCC
  バーコードの生成方法、塗りつぶしバーの切り替え、PNG ファイルへの保存方法を示します。
og_image_alt: Screenshot of a generated Planet postal barcode with filled bars
og_title: C#で郵便バーコード画像を作成する – ステップバイステップガイド
schemas:
- author: Aspose
  dateModified: '2026-10-21'
  description: Learn how to create postal barcode images in C# with Aspose.BarCode
    – generate Planet and RM4SCC barcodes, control filled bars, and save PNG files.
  headline: How to create postal barcode images in C# using Aspose.BarCode
  type: TechArticle
- description: Learn how to create postal barcode images in C# with Aspose.BarCode
    – generate Planet and RM4SCC barcodes, control filled bars, and save PNG files.
  name: How to create postal barcode images in C# using Aspose.BarCode
  steps:
  - name: 1. Prepare the output folder
    text: The barcode images need a writable directory. The code creates the folder
      if it does not exist, preventing a runtime `DirectoryNotFoundException`.
  - name: 2. Generate a Planet barcode with filled bars
    text: Planet barcodes are used by many postal services for domestic mail. The
      default `FilledBars` setting renders solid bars, which is the most common visual
      style.
  - name: 3. Generate a Planet barcode with empty bars
    text: Some postal specifications require **empty** (hollow) bars. You can toggle
      this behavior via the `FilledBars` property.
  - name: 4. Generate an RM4SCC barcode with filled bars
    text: RM4SCC (Royal Mail 4‑State Customer Code) is the UK postal barcode. Like
      Planet, the default appearance uses solid bars.
  - name: Full source code in one block
    text: Copy the following snippet into a new C# console project. It compiles with
      .NET 6.0 and produces three PNG files in the `Barcodes` subfolder.
  - name: Next steps
    text: '* **Generate other postal barcodes** – try `EncodeTypes.Postnet` or `EncodeTypes.USPSIntelligentMail`.
      * **Customize appearance** – experiment with `BarHeight`, `ForeColor`, and `BackColor`
      to match your branding. * **Integrate into a web service** – expose the generation
      logic via ASP.NET Core endp'
  type: HowTo
tags:
- barcode
- C#
- Aspose.BarCode
title: Aspose.BarCode を使用して C# で郵便バーコード画像を作成する方法
url: /ja/python-java/general/how-to-create-postal-barcode-images-in-c-using-aspose-barcod/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# C# と Aspose.BarCode を使用して郵便バーコード画像を作成する方法

.NET プロジェクトで **郵便バーコード** 画像を **作成** する必要がある場合、このガイドでは完全に実行可能なソリューションを示します。Planet と RM4SCC バーコードの生成方法、塗りつぶしバーと空白バーの切り替え、結果を PNG ファイルとして保存する方法を、数行の C# コードで確認できます。

信頼性の高い郵便バーコードの生成は、メール自動化、ラベル大量印刷、物流プラットフォームとの連携に不可欠です。このチュートリアルを終える頃には、任意の C# コンソールまたは Web アプリケーションにコピーできる再利用可能なコードスニペットが手に入ります。

## 前提条件

開始する前に、以下がインストールされていることを確認してください。

* .NET 6.0 SDK 以降  
* Visual Studio 2022（または .NET をサポートする任意の IDE）  
* 有効な **Aspose.BarCode** NuGet パッケージ (`Install-Package Aspose.BarCode`)  

これらのツールだけで、追加の依存関係なしにサンプルをコンパイル・実行できます。

## **郵便バーコード** 画像を **作成** するステップバイステップガイド

このプロセスは 4 つの論理的なステップで構成されます。

1. 出力フォルダーを準備する。  
2. 塗りつぶしバー（デフォルト外観）で Planet バーコードを生成する。  
3. 空白バーで Planet バーコードを生成する。  
4. 塗りつぶしバーで RM4SCC バーコードを生成する。

各ステップの説明は以下にあり、全ソースコードは説明の後にまとめて掲載しています。

### 1. 出力フォルダーを準備する

バーコード画像を保存するための書き込み可能ディレクトリが必要です。コードはフォルダーが存在しない場合に作成し、実行時の `DirectoryNotFoundException` を防ぎます。

```csharp
using System;
using System.IO;
using Aspose.BarCode.Generation;

class PostalBarcodeDemo
{
    static void Main()
    {
        // Define the output folder (adjust the path to your environment)
        string outputFolder = Path.Combine(Environment.CurrentDirectory, "Barcodes");

        // Ensure the folder exists
        Directory.CreateDirectory(outputFolder);
```

*重要性*: ディレクトリが存在しないと、バーコードが生成される前にプログラムが停止します。`Directory.CreateDirectory` は、フォルダーが既にある場合は何もしないため安全です。

### 2. 塗りつぶしバーで Planet バーコードを生成する

Planet バーコードは多くの郵便サービスで国内郵便に使用されます。デフォルトの `FilledBars` 設定は実線バーを描画し、最も一般的なビジュアルスタイルです。

```csharp
        // Step 2: Generate a Planet barcode with filled bars (default)
        BarcodeGenerator planetFilled = new BarcodeGenerator(EncodeTypes.Planet, "123456");
        // XDimension controls the width of a single bar; 4 pixels works well for screen display
        planetFilled.Parameters.Barcode.XDimension.Pixels = 4;
        planetFilled.Save(Path.Combine(outputFolder, "PostalPlanetFilledBars.png"),
                          BarCodeImageFormat.Png);
```

*解説*:  
* `EncodeTypes.Planet` は Aspose.BarCode に Planet 標準を使用させます。  
* データ文字列 `"123456"` は有効な Planet ペイロード（数字 6 桁）です。  
* `XDimension.Pixels = 4` はバー幅を 4 px に設定し、可読性とファイルサイズのバランスを取ります。  
* `Save` は画像を PNG 形式で書き出します。PNG はロスレス形式で、後続処理に適しています。

### 3. 空白バーで Planet バーコードを生成する

一部の郵便仕様では **空白**（中空）バーが求められます。`FilledBars` プロパティを切り替えるだけで実現できます。

```csharp
        // Step 3: Generate a Planet barcode with empty bars
        BarcodeGenerator planetEmpty = new BarcodeGenerator(EncodeTypes.Planet, "123456");
        planetEmpty.Parameters.Barcode.XDimension.Pixels = 4;
        // Setting FilledBars to false creates hollow bars
        planetEmpty.Parameters.Barcode.FilledBars = false;
        planetEmpty.Save(Path.Combine(outputFolder, "PostalPlanetEmptyBars.png"),
                         BarCodeImageFormat.Png);
```

*ヒント*: 塗りつぶしバーと空白バーを切り替える際は、`XDimension` の値を変えずに保つことで、画像間のサイズ一貫性が保たれます。

### 4. 塗りつぶしバーで RM4SCC バーコードを生成する

RM4SCC（Royal Mail 4‑State Customer Code）は英国の郵便バーコードです。Planet と同様に、デフォルト外観は実線バーです。

```csharp
        // Step 4: Generate an RM4SCC barcode with filled bars (default)
        BarcodeGenerator rm4sccFilled = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");
        rm4sccFilled.Parameters.Barcode.XDimension.Pixels = 4;
        rm4sccFilled.Save(Path.Combine(outputFolder, "PostalRM4SCCFilledBars.png"),
                          BarCodeImageFormat.Png);
    }
}
```

*RM4SCC が選ばれる理由*: RM4SCC 形式は 6 桁の数字文字列にチェックサムを付加してエンコードするため、英国の郵便サービスに最適です。

### 1 つのブロックにまとめた完全なソースコード

以下のスニペットを新しい C# コンソールプロジェクトに貼り付けてください。 .NET 6.0 でコンパイルでき、`Barcodes` サブフォルダーに 3 つの PNG ファイルが生成されます。

```csharp
using System;
using System.IO;
using Aspose.BarCode.Generation;

class PostalBarcodeDemo
{
    static void Main()
    {
        // -------------------------------------------------
        // 1. Prepare the output folder
        // -------------------------------------------------
        string outputFolder = Path.Combine(Environment.CurrentDirectory, "Barcodes");
        Directory.CreateDirectory(outputFolder);

        // -------------------------------------------------
        // 2. Planet barcode – filled bars (default)
        // -------------------------------------------------
        BarcodeGenerator planetFilled = new BarcodeGenerator(EncodeTypes.Planet, "123456");
        planetFilled.Parameters.Barcode.XDimension.Pixels = 4;
        planetFilled.Save(Path.Combine(outputFolder, "PostalPlanetFilledBars.png"),
                          BarCodeImageFormat.Png);

        // -------------------------------------------------
        // 3. Planet barcode – empty bars
        // -------------------------------------------------
        BarcodeGenerator planetEmpty = new BarcodeGenerator(EncodeTypes.Planet, "123456");
        planetEmpty.Parameters.Barcode.XDimension.Pixels = 4;
        planetEmpty.Parameters.Barcode.FilledBars = false;
        planetEmpty.Save(Path.Combine(outputFolder, "PostalPlanetEmptyBars.png"),
                         BarCodeImageFormat.Png);

        // -------------------------------------------------
        // 4. RM4SCC barcode – filled bars (default)
        // -------------------------------------------------
        BarcodeGenerator rm4sccFilled = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");
        rm4sccFilled.Parameters.Barcode.XDimension.Pixels = 4;
        rm4sccFilled.Save(Path.Combine(outputFolder, "PostalRM4SCCFilledBars.png"),
                          BarCodeImageFormat.Png);

        Console.WriteLine("All barcode images have been saved to: " + outputFolder);
    }
}
```

#### 期待される出力

プログラム実行時に確認メッセージが表示され、次の 3 ファイルが作成されます。

* `PostalPlanetFilledBars.png` – 実線 Planet バーコード  
* `PostalPlanetEmptyBars.png` – 中空 Planet バーコード  
* `PostalRM4SCCFilledBars.png` – 実線 RM4SCC バーコード  

各画像はバー幅 4 px で、画面プレビューや印刷用 PDF 埋め込みに適しています。

## よくある質問とエッジケースの対処

| 質問 | 回答 |
|----------|--------|
| **データ文字列が無効な場合はどうなりますか？** | Aspose.BarCode は `ArgumentException` をスローします。生成前に入力長（Planet = 6 桁数字、RM4SCC = 6 桁数字）を検証してください。 |
| **画像形式を変更できますか？** | はい。`BarCodeImageFormat.Png` を `Jpeg`、`Gif`、`Bmp`、`Tiff` などに置き換えれば対応できます。 |
| **バーの高さはどう調整しますか？** | `planetFilled.Parameters.Barcode.BarHeight` を使用します（デフォルトは 50 px）。 |
| **Web API でこのコードを使用しても安全ですか？** | 問題ありません。ジェネレータは読み取り専用操作に対してスレッドセーフですが、リクエストごとに新しい `BarcodeGenerator` をインスタンス化して共有状態を避けてください。 |
| **他の郵便規格はどうですか？** | Aspose.BarCode は `EncodeTypes.Postnet`、`EncodeTypes.USPSIntelligentMail` などもサポートしています。手順は同じで、`EncodeTypes` の値を変更するだけです。 |

## 結論

C# と Aspose.BarCode を使って **郵便バーコード** 画像を作成する方法を習得しました。Planet と RM4SCC の両形式、塗りつぶしバーと空白バーの切り替え方法を網羅し、すぐに実行可能なサンプルコードを提供しました。この例を任意の .NET プロジェクトに組み込めば、即座に視覚的な出力が得られます。

### 次のステップ

* **他の郵便バーコードを生成** – `EncodeTypes.Postnet` や `EncodeTypes.USPSIntelligentMail` に挑戦してください。  
* **外観をカスタマイズ** – `BarHeight`、`ForeColor`、`BackColor` を調整してブランドに合わせましょう。  
* **Web サービスに統合** – ASP.NET Core エンドポイントで生成ロジックを公開し、オンデマンドでバーコードを作成できるようにします。  

これらのテクニックをマスターすれば、**planet barcode** 画像の生成や “**how to generate barcode C#**” といった質問に自信を持って答えられるようになります。デスクトップの郵便ツールでもクラウドベースの配送 API でも、安心して活用してください。Happy coding!

## 次に学ぶべきこと

以下のチュートリアルは、本ガイドで示した手法を基にした関連トピックを扱っています。各リソースには完全な動作コード例とステップバイステップの解説が含まれており、API の追加機能を習得したり、別の実装アプローチを自分のプロジェクトで試したりするのに役立ちます。

- [How to create planet barcode with filled and empty bars](/barcode/english/python-java/general/how-to-create-planet-barcode-with-filled-and-empty-bars/)
- [How to create RM4SCC barcode and generate planet barcode in C#](/barcode/english/python-java/general/how-to-create-rm4scc-barcode-and-generate-planet-barcode-in/)
- [Generate Postal Barcode in C# – Complete Guide with Planet Barcode](/barcode/english/python-java/general/generate-postal-barcode-in-c-complete-guide-with-planet-barc/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}