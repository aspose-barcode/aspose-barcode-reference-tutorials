---
date: 2026-08-17
description: Aspose.BarCode for .NET を使用してマクロ文字付き DataMatrix バーコードの作成方法を学び、アプリケーションで
  DataMatrix を活用する方法を探ります。
keywords:
- create datamatrix barcode
- datamatrix barcode error correction
- aspose barcode macro
- .net barcode generation
lastmod: 2026-08-17
linktitle: DataMatrix マクロ構成
og_description: Aspose.BarCode for .NET を使用してマクロ文字付き DataMatrix バーコードの作成方法を学びます。このガイドでは、ステップバイステップのコード、カスタマイズオプション、信頼性の高いバーコード生成のための検証ポイントを提供します。
og_image_alt: Guide showing creation of DataMatrix barcode with macro characters in
  .NET using Aspose.BarCode
og_title: Aspose.BarCode を使用してマクロ文字付き DataMatrix バーコードを作成
schemas:
- author: Aspose
  dateModified: '2026-08-17'
  description: Learn how to create DataMatrix barcode with macro characters using
    Aspose.BarCode for .NET and discover how to use DataMatrix in your applications.
  headline: How to create DataMatrix barcode with macro characters in .NET
  type: TechArticle
- description: Learn how to create DataMatrix barcode with macro characters using
    Aspose.BarCode for .NET and discover how to use DataMatrix in your applications.
  name: How to create DataMatrix barcode with macro characters in .NET
  steps:
  - name: setting up your project
    text: Create a new Console Application (or any .NET project) in Visual Studio.
      Add a reference to the Aspose.BarCode DLLs that you obtained from the download.
  - name: DataMatrix macro configuration
    text: The core of the tutorial – here we actually **create DataMatrix barcode**
      with a macro character. > **Pro tip:** Replace `"ASPOSE"` with any string you
      need to encode. The macro character (`Macro05`) tells scanners that this barcode
      is part of a macro sequence.
  - name: customize barcode parameters for error correction
    text: 'Before saving, you can tweak additional settings: - **XDimension** – controls
      the size of each module (pixel). - **Margin**, **ErrorCorrection**, and **EncodingMode**
      – all accessible via `gen.Parameters.Barcode.DataMatrix`.'
  - name: save the barcode
    text: The snippet above saves the image as `DataMatrixMacro.png` in the folder
      you specified. PNG is loss‑less, making it ideal for further processing.
  - name: recognize the barcode
    text: '`BarCodeReader` is Aspose.BarCode''s class for decoding barcodes from images.
      Using `BarCodeReader` we immediately read back the generated image to confirm
      that the macro character and data are correct. This round‑trip validation is
      especially handy during automated testing.'
  type: HowTo
- questions:
  - answer: Aspose.BarCode for .NET is a powerful library that allows .NET developers
      to generate and recognize barcodes in various formats, including DataMatrix,
      QR, and more.
    question: What is Aspose.BarCode for .NET?
  - answer: DataMatrix barcodes are compact, highly reliable, and can store large
      amounts of data, making them ideal for manufacturing, logistics, and healthcare.
    question: Why should I use DataMatrix barcodes?
  - answer: You can find the documentation at [the Aspose.BarCode for .NET documentation](https://reference.aspose.com/barcode/net/).
    question: Where can I find the documentation for Aspose.BarCode for .NET?
  - answer: Yes, you can download a free trial from [the free trial link](https://releases.aspose.com/).
    question: Is there a free trial available for Aspose.BarCode for .NET?
  - answer: If you have any questions or need support, you can visit the Aspose.BarCode
      for .NET forum at [the support forum](https://forum.aspose.com/c/barcode/13).
    question: Where can I get support for Aspose.BarCode for .NET?
  type: FAQPage
second_title: Aspose.BarCode .NET API
tags:
- datamatrix barcode
- aspose.barcode
- c# barcode generation
- macro barcode
- barcode error correction
title: .NET でマクロ文字を使用した DataMatrix バーコードの作成方法
url: /ja/net/datamatrix-barcode-configuration/datamatrix-macro-configuration/
weight: 18
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# マクロ文字を使用したDataMatrixバーコードの作成方法（.NET）

## はじめに

マクロ文字を含む**DataMatrixバーコード**を生成すると、余分な参照情報を小さな正方形シンボルに詰め込むことができます。このチュートリアルでは、Aspose.BarCode for .NET を使用してマクロ文字付きの**DataMatrixバーコード**を作成し、サイズやエラー訂正をカスタマイズし、結果を即座に検証する方法を学びます。最後には、製品ラベル、文書、医療機器などにマクロ対応バーコードを埋め込む準備が整います。

## 簡単な回答

- **主要なライブラリは何ですか？** Aspose.BarCode for .NET  
- **マクロ文字付きのDataMatrixバーコードを作成できますか？** Yes – set the `MacroCharacters` property.  
- **本番環境でライセンスが必要ですか？** A valid Aspose license is required for production use.  
- **サポートされている.NETバージョンはどれですか？** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **無料トライアルは利用可能ですか？** Absolutely – download it from the official Aspose site.

## 前提条件

マクロ設定に入る前に、以下が揃っていることを確認してください。

1. **Visual Studio** – 最近のエディションであればどれでも動作します。  
2. **Aspose.BarCode for .NET** – [the download link](https://releases.aspose.com/barcode/net/) からダウンロードしてください。  
3. **Basic .NET knowledge** – C# と .NET エコシステムに慣れていること。

## 名前空間のインポート

バーコードの生成と認識に必要な名前空間をインポートします。

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode.BarCodeRecognition;
```

## マクロ文字付きの「DataMatrixバーコード生成」とは何ですか？

`MacroCharacters` は、DataMatrixバーコードに追加データを参照するマクロシンボルを含めることを可能にします。Macro05 や Macro06 などのマクロ文字を使用すると、1つのバーコードがより大きなデータセットや関連するバーコードのシーケンスを指し示すことができ、物流、製造、文書追跡など、リンクされた情報をコンパクトにエンコードする必要がある場面で有用です。

## DataMatrixバーコード生成にAspose.BarCodeを使用する理由は何ですか？

Aspose.BarCode は、DataMatrix のサイズ、エラー訂正レベル、マクロ設定を正確に制御でき、30 以上のバーコードシンボルをサポートし、画像全体をメモリに読み込まずに最大 10 MB のファイルを処理します。クロスプラットフォームの .NET 実装は .NET Framework、.NET Core、.NET 5/6 で動作し、組み込みの認識機能があるため、バーコードを即座に検証できます。

## ステップバイステップガイド

### ステップ 1: プロジェクトの設定

Visual Studio で新しいコンソール アプリケーション（または任意の .NET プロジェクト）を作成します。ダウンロードで取得した Aspose.BarCode の DLL への参照を追加してください。

### ステップ 2: DataMatrix マクロ構成

チュートリアルの核心です – ここで実際にマクロ文字を使用して**DataMatrixバーコード**を**作成**します。

```csharp
string path = "Your Directory Path";
System.Console.WriteLine("DataMatrixMacro:");

using (BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.DataMatrix, "ASPOSE"))
{
    gen.Parameters.Barcode.XDimension.Pixels = 4;
    // Set the macro character to 05
    gen.Parameters.Barcode.DataMatrix.MacroCharacters = MacroCharacter.Macro05;
    gen.Save($"{path}DataMatrixMacro.png", BarCodeImageFormat.Png);

    // Try to recognize it
    using (BarCodeReader read = new BarCodeReader(gen.GenerateBarCodeImage(), DecodeType.DataMatrix))
    {
        foreach (BarCodeResult result in read.ReadBarCodes())
            Console.WriteLine("DataMatrixMacro:" + result.CodeText);
    }
}
```

> **Pro tip:** `"ASPOSE"` をエンコードしたい任意の文字列に置き換えてください。マクロ文字（`Macro05`）は、スキャナーにこのバーコードがマクロシーケンスの一部であることを伝えます。

### ステップ 3: エラー訂正用にバーコードパラメータをカスタマイズ

保存する前に、追加設定を調整できます。

- **XDimension** – 各モジュール（ピクセル）のサイズを制御します。  
- **Margin**, **ErrorCorrection**, and **EncodingMode** – すべて `gen.Parameters.Barcode.DataMatrix` からアクセス可能です。

### ステップ 4: バーコードを保存

上記のスニペットは、指定したフォルダーに画像を `DataMatrixMacro.png` として保存します。PNG はロスレス形式で、後続の処理に最適です。

### ステップ 5: バーコードを認識

`BarCodeReader` は、画像からバーコードをデコードするための Aspose.BarCode のクラスです。`BarCodeReader` を使用して、生成した画像をすぐに読み取り、マクロ文字とデータが正しいことを確認します。この往復検証は、特に自動テスト時に便利です。

## 実際のシナリオでDataMatrixを使用する方法

マクロ文字付きのDataMatrixバーコードは、製品ラベルへの適用、シリアル番号を中央データベースにリンク、デジタル記録への参照を埋め込んだ文書追跡、患者や機器データを小さなスキャン可能シンボルに保存する医療機器タグなどに利用できます。これらのユースケースは手動データ入力を削減し、トレーサビリティを向上させます。

## 一般的な問題と解決策

| 問題 | 原因 | 対策 |
|-------|--------|-----|
| バーコードが認識されない | `XDimension` が不正確、または画像解像度が低い | `XDimension.Pixels` を 4‑6 に増やし、PNG または TIFF で保存する |
| マクロ文字が無視される | リーダーがマクロモードをサポートしていない | DataMatrix マクロを明示的にサポートするスキャナー/リーダーを使用する（例: 新しい ZXing バージョン） |
| パスが見つからない | `path` 変数が無効 | ディレクトリが存在することを確認するか、`Environment.CurrentDirectory` と `Path.Combine` を使用する |

## よくある質問

**Q: Aspose.BarCode for .NET とは何ですか？**  
A: Aspose.BarCode for .NET は、.NET 開発者が DataMatrix、QR などさまざまな形式のバーコードを生成および認識できる強力なライブラリです。

**Q: なぜ DataMatrix バーコードを使用すべきですか？**  
A: DataMatrix バーコードはコンパクトで信頼性が高く、大量のデータを保存できるため、製造、物流、医療分野に最適です。

**Q: Aspose.BarCode for .NET のドキュメントはどこで見つけられますか？**  
A: ドキュメントは [the Aspose.BarCode for .NET documentation](https://reference.aspose.com/barcode/net/) にあります。

**Q: Aspose.BarCode for .NET の無料トライアルはありますか？**  
A: はい、[the free trial link](https://releases.aspose.com/) から無料トライアルをダウンロードできます。

**Q: Aspose.BarCode for .NET のサポートはどこで受けられますか？**  
A: ご質問やサポートが必要な場合は、[the support forum](https://forum.aspose.com/c/barcode/13) の Aspose.BarCode for .NET フォーラムをご利用ください。

---

**最終更新日:** 2026-08-17  
**テスト環境:** Aspose.BarCode 24.11 for .NET  
**作者:** Aspose

## 関連チュートリアル

- [バーコード作成 Aspose .NET - DataMatrix コードテキストの構成](/barcode/net/datamatrix-barcode-configuration/datamatrix-extended-code-text-configuration/)
- [Aspose.BarCode for .NET を使用した DataMatrix バーコード (ECC 200) の生成方法](/barcode/net/datamatrix-barcode-configuration/datamatrix-ecc-200-configuration/)
- [Aspose.BarCode for .NET を使用した DataMatrix Structured Append の構成](/barcode/net/datamatrix-barcode-reading/datamatrix-structured-append-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}