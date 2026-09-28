---
category: general
date: 2026-08-19
description: C#でバーコードのPNGファイルを生成し、高さを調整する方法を学びます。バーコード画像の生成方法とバーコードの高さを簡単に変更する手順を網羅しています。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- barcode png file
- how to generate barcode
- adjust barcode height
- change barcode height
language: ja
lastmod: 2026-08-19
og_description: C#でバーコードのPNGファイルを作成し、バーコード画像の生成方法、バーコードの高さの調整、最適なスキャンのための高さ変更を学びましょう。
og_image_alt: barcode PNG file showing Databar OmniDirectional barcode at two heights
og_title: C#でバーコードPNGファイルを作成する – ステップバイステップガイド
schemas:
- author: Aspose
  dateModified: '2026-08-19'
  description: Learn how to generate a barcode PNG file in C# and adjust its height,
    covering how to generate barcode images and change barcode height easily.
  headline: How to create a barcode PNG file with adjustable height in C#
  type: TechArticle
- questions:
  - answer: Yes. Replace `BarCodeImageFormat.Png` with `BarCodeImageFormat.Jpeg`,
      `BarCodeImageFormat.Bmp`, etc.
    question: Can I generate other image formats (JPEG, BMP)?
  - answer: Serve the generated PNG via an HTTP endpoint or convert it to a Base64
      string and place it in an `<img>` tag’s `src` attribute.
    question: How do I embed the PNG in a web page?
  - answer: 'Use `generator.Parameters.Image.BackgroundColor = Color.White;` (or any
      `System.Drawing.Color`). ## Conclusion You now know how to **generate a barcode
      PNG file** in C# and precisely **adjust barcode height** to meet scanning or
      design requirements. By changing the `BarHeight.Pixels` property you ca'
    question: Is there a way to set the background color?
  type: FAQPage
tags:
- barcode
- C#
- image generation
title: C#で高さを調整可能なバーコードPNGファイルの作成方法
url: /ja/python-java/general/how-to-create-a-barcode-png-file-with-adjustable-height-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# C#で高さ調整可能なバーコードPNGファイルを作成する方法

C#で **バーコードPNGファイル** を作成する必要がある場合、このガイドで手順を正確に示します。**バーコードの生成方法** と **バーコードの高さを調整する方法** を示す、完全に実行可能なサンプルをご覧いただけます。

バーコードPNGファイルの生成は、在庫管理システム、POS端末、機械可読データを印刷または表示する必要があるあらゆるアプリケーションで一般的な要件です。このチュートリアルの最後までに、バーコードの高さを変更し、複数のPNGファイルを保存し、高さがスキャンの信頼性に与える影響を理解できるようになります。

## 前提条件

* .NET 6.0 SDK 以降がインストールされていること  
* Visual Studio 2022（または .NET をサポートする任意の IDE）  
* **Aspose.BarCode for .NET** NuGet パッケージ（コードサンプルはこのライブラリを使用）

コマンドラインからパッケージを追加できます:

```bash
dotnet add package Aspose.BarCode
```

> **プロのコツ:** Aspose.BarCode の無料評価版は開発およびテストで使用できます。製品版では、ライセンスキーを取得してください。

## バーコードライブラリのインストール

最初のステップはプロジェクトにライブラリを参照することです。C# ファイルの先頭に以下の `using` ディレクティブを追加します。

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;
```

## バーコードPNGファイルの作成

ここでは **バーコードPNGファイル** を出力する `BarcodeGenerator` インスタンスを作成します。例では Databar OmniDirectional シンボロジーを使用していますが、`EncodeTypes.DatabarOmniDirectional` を任意のサポートされているタイプに置き換えることができます。

```csharp
// Step 1: Create a DataBar Omnidirectional generator with the desired data
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");
```

`"(01)12345678901231"` の文字列は 14 桁 GTIN の GS1 アプリケーション識別子形式に従っています。データはご自身の製品識別子に合わせて調整してください。

## X‑ディメンションの設定（任意）

X‑ディメンションは単一のバーコードモジュールの幅を定義します。ピクセル単位の値にすることで画像サイズを正確に制御できます。

```csharp
// Optional: Set the pixel size of the X‑dimension (module width)
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

`2` ピクセルの値はほとんどの画面表示でうまく機能します。印刷時により大きなバーコードが必要な場合は増やしてください。

## バーコードの高さを調整してバーコードPNGファイルを保存する

**BarHeight** プロパティはバーの垂直サイズを制御します。この値を変更することで、エンコードされたデータに影響を与えることなく **バーコードの高さを調整** できます。

```csharp
// Step 2: Generate a 30‑pixel‑high barcode and save it as PNG
barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 30;
barcodeGenerator.Save("DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);
```

`DatabarBarHeight30Pixels.png` ファイルは高さ 30 ピクセルの **バーコードPNGファイル** です。  

**バーコードの高さを変更** して2枚目の画像を作成するには、新しい値を代入して `Save` を再度呼び出すだけです:

```csharp
// Step 3: Change the height to 60 pixels and save the new image
barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 60;
barcodeGenerator.Save("DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);
```

これで 30 px と 60 px の2つの PNG ファイルが作成され、**バーコードの高さを動的に調整** する方法が示されました。

### バーコードの高さが重要な理由

* **可読性:** スキャナは信頼できる検出のために最低限の高さを期待します。特に低解像度カメラでは、バーコードが短すぎると検出されないことがあります。
* **美観:** バーコードの高さを周囲のデザイン要素に合わせることで、よりすっきりした UI が実現します。
* **印刷制約:** ラベルプリンタの中には高さが固定されたスロットがあるものがあります。バーコードの高さを調整することでフィットさせられます。

**ベストプラクティス:** 高さは X‑ディメンションの倍数に保ちます（例: X‑ディメンションが 2 px の場合は 30 px）。これにより比例が保たれ、歪みを防げます。

## 完全なサンプル

以下は、コンソールアプリケーションに貼り付けてすぐに実行できる、完全な自己完結型プログラムです。

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        // 1️⃣ Create the generator with Databar OmniDirectional data
        BarcodeGenerator generator = new BarcodeGenerator(
            EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");

        // 2️⃣ Set a reasonable X‑dimension (module width)
        generator.Parameters.Barcode.XDimension.Pixels = 2;

        // 3️⃣ First height: 30 pixels → save as PNG
        generator.Parameters.Barcode.BarHeight.Pixels = 30;
        generator.Save("DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved 30‑pixel barcode as DatabarBarHeight30Pixels.png");

        // 4️⃣ Second height: 60 pixels → save as PNG
        generator.Parameters.Barcode.BarHeight.Pixels = 60;
        generator.Save("DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved 60‑pixel barcode as DatabarBarHeight60Pixels.png");
    }
}
```

**期待される出力**

プログラムを実行すると、実行ファイルの作業ディレクトリに2つのファイルが作成されます:

* `DatabarBarHeight30Pixels.png` – 高さ30ピクセルのバーコードPNGファイル  
* `DatabarBarHeight60Pixels.png` – 高さ60ピクセルのバーコードPNGファイル  

任意の画像ビューアでどちらかの PNG を開くと、スキャン可能なクリアな Databar OmniDirectional バーコードが表示されます。

## エッジケースとトラブルシューティング

| Situation | What to check | Recommended fix |
|-----------|---------------|-----------------|
| バーコードがぼやけて表示される | 選択した高さに対して X‑ディメンションが低すぎる | `XDimension.Pixels` を増やす（例: 2 から 3 へ） |
| 低高さのバーコードでスキャナが失敗する | 高さがスキャナの最小要件を下回っている | `BarHeight.Pixels` を最低でも30 pxに設定する（またはスキャナの仕様に従う） |
| PNG ファイルが空または破損している | 出力パスが無効、または書き込み権限がない | 絶対パスを使用するか、アプリに書き込み権限があることを確認する |
| 別のシンボロジーが必要 | 現在の `EncodeTypes` が適切でない | `EncodeTypes.DatabarOmniDirectional` を別の列挙値に置き換える（例: `EncodeTypes.Code128`） |

## よくある質問

**Q: 他の画像形式（JPEG、BMP）で生成できますか？**  
A: はい。`BarCodeImageFormat.Png` を `BarCodeImageFormat.Jpeg`、`BarCodeImageFormat.Bmp` などに置き換えてください。

**Q: PNG をウェブページに埋め込むにはどうすればよいですか？**  
A: 生成した PNG を HTTP エンドポイントで配信するか、Base64 文字列に変換して `<img>` タグの `src` 属性に設定します。

**Q: 背景色を設定する方法はありますか？**  
A: `generator.Parameters.Image.BackgroundColor = Color.White;`（または任意の `System.Drawing.Color`）を使用します。

## 結論

これで C# で **バーコードPNGファイルを生成** し、スキャンやデザイン要件に合わせて **バーコードの高さを正確に調整** する方法が分かりました。`BarHeight.Pixels` プロパティを変更することで、**バーコードの高さを動的に変更** でき、単一のコードベースから複数の PNG アセットを生成できます。

次に、前景色、余白、ヒューマンリーダブルテキストの追加など、他のカスタマイズオプションを検討してください。また、さまざまなシンボロジー（`EncodeTypes.Code128`、`EncodeTypes.QR`）を試すことで、エンコードできるデータの範囲を広げることができます。

コーディングを楽しんで、バーコードが常に最初のスキャンで読み取られますように！

## 次に学ぶべきことは？

以下のチュートリアルは、本ガイドで示した手法を基にした密接に関連するトピックを扱っています。各リソースには、ステップバイステップの解説と完全な動作コード例が含まれており、追加の API 機能を習得し、プロジェクトで代替実装アプローチを検討するのに役立ちます。

- [Aspose.BarCode for .NET を使用した 1 次元 Databar のバーコード高さの生成と調整方法](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-barcode-height-adjustment/)
- [バーコード生成 - 1 次元バーコードタイプ](/barcode/english/net/one-dimensional-barcode-types/)
- [Aspose.BarCode for .NET を使用したカスタムアスペクト比の Aztec バーコード生成方法](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}