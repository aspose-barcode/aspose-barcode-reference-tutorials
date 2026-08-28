---
date: 2026-08-02
description: Aspose.BarCode for .NET プロジェクトで DataMatrix バーコードの作成方法、DataMatrix の生成、そして高密度バーコード生成の方法を学びます。
keywords:
- create datamatrix barcode
- high density barcode
- generate datamatrix barcode
- barcode generation asp.net
- temporary aspose license
lastmod: 2026-08-02
linktitle: DataMatrix ECC 200 設定
og_description: Aspose.BarCode for .NET を使用して DataMatrix バーコードを作成します。このチュートリアルでは、高密度バーコード生成、テンポラリ
  Aspose ライセンスの設定、ステップバイステップの C# コードを紹介します。
og_image_alt: Guide showing C# code to create a DataMatrix barcode using Aspose.BarCode
og_title: DataMatrix バーコードの作成 – Aspose.BarCode .NET ガイド
schemas:
- author: Aspose
  dateModified: '2026-08-02'
  description: Learn how to create DataMatrix barcode, generate datamatrix, and explore
    high density barcode generation with Aspose.BarCode for .NET projects.
  headline: How to create DataMatrix barcode (ECC 200) with Aspose.BarCode for .NET
  type: TechArticle
- description: Learn how to create DataMatrix barcode, generate datamatrix, and explore
    high density barcode generation with Aspose.BarCode for .NET projects.
  name: How to create DataMatrix barcode (ECC 200) with Aspose.BarCode for .NET
  steps:
  - name: Initialize the Barcode Generator
    text: '`BarcodeGenerator` is Aspose.BarCode''s core class that creates and renders
      barcodes. It accepts the symbology type and the text to encode. Replace `"Your
      Directory Path"` with the folder where you’d like the image saved.'
  - name: Set XDimension and ECC Type
    text: '`XDimension` defines the pixel size of each DataMatrix module, while `DataMatrixEcc`
      selects the error‑correction level. ECC 200 provides the highest correction
      capability for this symbology. Adjust the pixel value if you need larger or
      smaller modules; typical values are 4‑6 px for on‑screen displa'
  - name: Generate and Save the Barcode Image
    text: The `Save` method writes the barcode to a file. You can choose PNG, JPEG,
      or TIFF by passing the corresponding `BarCodeImageFormat` enum value. Switch
      `BarCodeImageFormat.Png` to `BarCodeImageFormat.Jpeg` or `BarCodeImageFormat.Tiff`
      if your workflow requires a different format.
  type: HowTo
- questions:
  - answer: Yes, the same API works in .NET Core, .NET 5, and .NET 6 projects.
    question: Can I use this code in a .NET Core console application?
  - answer: Replace `BarCodeImageFormat.Png` with `BarCodeImageFormat.Jpeg` in the
      `Save` call.
    question: How do I change the output format to JPEG?
  - answer: Yes – generate the image first, then add it to a PDF using Aspose.PDF
      or any PDF library.
    question: Is it possible to embed the barcode directly into a PDF?
  - answer: DataMatrix supports UTF‑8; simply pass the Unicode string to the generator
      as shown.
    question: What if I need to encode Unicode characters?
  - answer: Absolutely – place the generation code inside a loop and change the data/value
      for each iteration.
    question: Does the library support batch generation of multiple barcodes?
  type: FAQPage
second_title: Aspose.BarCode .NET API
tags:
- datamatrix barcode
- Aspose.BarCode
- .NET barcode generation
- C# barcode tutorial
title: Aspose.BarCode for .NET を使用して DataMatrix バーコード（ECC 200）を作成する方法
url: /ja/net/datamatrix-barcode-configuration/datamatrix-ecc-200-configuration/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.BarCode for .NET を使用して DataMatrix バーコード (ECC 200) を作成する方法

## はじめに

このガイドでは Aspose.BarCode for .NET を使用して **DataMatrix バーコード** (ECC 200) を作成します。 在庫トラッカー、POS システム、または文書ワークフローの自動化など、どのような用途でも、高密度バーコードは小さなスペースに大量のデータを保存できます。 すべての設定手順を順に説明し、各設定が重要な理由を解説し、すぐに実行できる C# スニペットを提供します。

## クイック回答
- **.NET で DataMatrix に最適なライブラリは何ですか？** Aspose.BarCode for .NET  
- **ECC 200 はどの ECC レベルを提供しますか？** 高密度エラー訂正により堅牢なスキャンが可能です。  
- **サンプルを実行するのにライセンスは必要ですか？** 評価用に一時ライセンスが使用できますが、本番環境ではフルライセンスが必要です。  
- **サポートされている .NET バージョンは何ですか？** .NET Framework 4.5 以上、.NET Core 3.1 以上、.NET 5/6 以上。  
- **PNG、JPEG、または TIFF を出力できますか？** はい – `Save` メソッドは複数の画像形式をサポートしています。

## DataMatrix ECC 200 とは何ですか？

DataMatrix ECC 200 は、高密度の二次元バーコードで、コンパクトな正方形または長方形のパターンに最大 2,335 文字の英数字または 1,556 バイトのバイナリデータを格納できます。 Reed‑Solomon エラー訂正を使用して失われたまたは損傷したモジュールを復元できるため、航空宇宙部品のマーキング、医薬品ラベリング、物流など、信頼性が重要な用途に最適です。

## なぜ Aspose のバーコード生成を使用するのか？

Aspose.BarCode は **30 以上のシンボル** をサポートし、ファイル全体をメモリにロードせずに最大 10,000 × 10,000 px の画像をレンダリングでき、Windows、Linux、macOS 間で決定的な出力を提供します。 API を使用するとすべてのレンダリングパラメータを制御でき、**barcode generation ASP.NET** シナリオで最も柔軟な選択肢となります。

## 前提条件

1. **開発環境** – 適切な .NET フレームワークがインストールされた Visual Studio。  
2. **Aspose.BarCode for .NET** – ウェブサイトからダウンロードしてインストールします、[here](https://releases.aspose.com/barcode/net/)。  
3. **ライセンス** – テスト用の一時ライセンスを [here](https://purchase.aspose.com/temporary-license/) から取得します。  
4. **C# 基礎** – C# の構文とプロジェクト構成に慣れていること。

基本がカバーされたので、次は DataMatrix ECC 200 の設定に進みましょう。

## 名前空間のインポート

`Aspose.BarCode.Generation` 名前空間にはバーコード作成に必要なすべてのクラスが含まれています。ファイルの先頭でインポートしてください：

```csharp
using Aspose.BarCode.Generation;
```

## DataMatrix バーコード (ECC 200) の作成手順

DataMatrix ECC 200 バーコードを生成するには、エンコードしたいデータをロードし、`BarcodeGenerator` のいくつかの主要パラメータを設定し、`Save` を呼び出して画像ファイルを書き出すだけです。この 3 ステップのフローはエンコード、エラー訂正、出力形式の選択を処理し、最小限のコードで任意の .NET アプリケーションにバーコード作成を統合できます。

### 手順 1: Barcode Generator の初期化

`BarcodeGenerator` は Aspose.BarCode のコアクラスで、バーコードの作成とレンダリングを行います。シンボロジータイプとエンコードするテキストを受け取ります。

```csharp
string path = "Your Directory Path";
System.Console.WriteLine("DataMatrixEcc200:");

using (BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.DataMatrix, "Åspóse.Barcóde©"))
{
    // Your code goes here
}
```

`"Your Directory Path"` を画像を保存したいフォルダーに置き換えてください。

### 手順 2: XDimension と ECC タイプの設定

`XDimension` は各 DataMatrix モジュールのピクセルサイズを定義し、`DataMatrixEcc` はエラー訂正レベルを選択します。ECC 200 はこのシンボロジーに対して最高の訂正能力を提供します。

```csharp
gen.Parameters.Barcode.XDimension.Pixels = 4;
gen.Parameters.Barcode.DataMatrix.DataMatrixEcc = DataMatrixEccType.Ecc200;
```

モジュールを大きくまたは小さくしたい場合はピクセル値を調整してください。一般的な値は画面表示で 4‑6 px、印刷ラベルで 8‑10 px です。

### 手順 3: バーコード画像の生成と保存

`Save` メソッドはバーコードをファイルに書き出します。対応する `BarCodeImageFormat` 列挙値を渡すことで PNG、JPEG、または TIFF を選択できます。

```csharp
gen.Save($"{path}DataMatrixEcc200.png", BarCodeImageFormat.Png);
```

ワークフローで別の形式が必要な場合は、`BarCodeImageFormat.Png` を `BarCodeImageFormat.Jpeg` または `BarCodeImageFormat.Tiff` に変更してください。

## よくある問題とトラブルシューティング

| 症状 | 考えられる原因 | 対策 |
|---------|--------------|-----|
| バーコードがぼやけて表示される | XDimension が低すぎる | `XDimension.Pixels` を 6‑8 に増やす |
| モバイルでスキャンに失敗する | ECC レベルが間違っている | `DataMatrixEcc = DataMatrixEccType.Ecc200` を確認する |
| ファイルが作成されない | パス文字列が無効 | 絶対パスを使用するか、フォルダーが存在することを確認する |

## よくある質問

**Q: このコードを .NET Core コンソールアプリケーションで使用できますか？**  
A: はい、同じ API は .NET Core、.NET 5、.NET 6 プロジェクトで動作します。

**Q: 出力形式を JPEG に変更するにはどうすればよいですか？**  
A: `Save` 呼び出しで `BarCodeImageFormat.Png` を `BarCodeImageFormat.Jpeg` に置き換えてください。

**Q: バーコードを PDF に直接埋め込むことは可能ですか？**  
A: はい – まず画像を生成し、次に Aspose.PDF または任意の PDF ライブラリを使用して PDF に追加します。

**Q: Unicode 文字をエンコードする必要がある場合はどうすればよいですか？**  
A: DataMatrix は UTF‑8 をサポートしています。示されたように Unicode 文字列をジェネレータに渡すだけです。

**Q: ライブラリは複数のバーコードのバッチ生成をサポートしていますか？**  
A: もちろんです – 生成コードをループ内に配置し、各イテレーションでデータ/値を変更してください。

## 結論

Aspose.BarCode for .NET を使用して **DataMatrix バーコード** (ECC 200) を **作成**するために必要なすべてを網羅しました。前提条件と名前空間のインポートから X‑dimension の設定、ECC レベルの選択、好みの形式での画像保存まで。余白、背景色、回転などの多数の追加プロパティを試して、特定のユースケースに合わせて出力を微調整してください。

問題が発生した場合は、コミュニティが [Aspose.BarCode forum](https://forum.aspose.com/c/barcode/13) でサポートします。コーディングを楽しんでください！

---

**最終更新日:** 2026-08-02  
**テスト環境:** Aspose.BarCode 24.11 for .NET  
**作者:** Aspose  

{{< blocks/products/products-backtop-button >}}

## 関連チュートリアル

- [Aspose.BarCode for .NET を使用して DataMatrix ECC 000-140 バーコードを生成する方法](/barcode/net/datamatrix-barcode-configuration/datamatrix-ecc-000-140-configuration/)
- [Aspose.BarCode for .NET を使用して DataMatrix バーコードを読み取る方法](/barcode/net/datamatrix-barcode-reading/)
- [バーコード PNG の作成 – DataMatrix アスペクト比 – Aspose.BarCode](/barcode/net/datamatrix-barcode-configuration/datamatrix-aspect-ratio-customization/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}