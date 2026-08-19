---
date: 2026-05-24
description: Aspose.BarCode for .NET を使用して Aztec バーコード (.NET) を作成する方法を学びます。Auto、FullRange、Compact、Rune
  シンボルモードをカバーし、ステップバイステップのガイダンスを提供します。
keywords:
- create aztec barcode .net
- aztec symbol mode
- aspose barcode .net
linktitle: Aztec シンボルモードの例
schemas:
- author: Aspose
  dateModified: '2026-05-24'
  description: Learn how to create aztec barcode .net using Aspose.BarCode for .NET,
    covering Auto, FullRange, Compact, and Rune symbol modes with step‑by‑step guidance.
  headline: Create Aztec Barcode .NET with Aspose.BarCode
  type: TechArticle
- questions:
  - answer: Aztec Symbol Mode determines how the library packs data into layers, affecting
      size, capacity, and readability.
    question: What is the purpose of Aztec Symbol Mode in barcode generation?
  - answer: Yes, simply assign a new string to the `CodeText` property before calling
      `Save`.
    question: Can I change the code text for Aztec barcodes in Aspose.BarCode for
      .NET?
  - answer: Yes, you can download a free trial version of Aspose.BarCode for .NET
      [here](https://releases.aspose.com/).
    question: Is there a free trial version of Aspose.BarCode for .NET available?
  - answer: You can refer to the complete documentation for Aspose.BarCode for .NET
      [here](https://reference.aspose.com/barcode/net/).
    question: Where can I find the full documentation for Aspose.BarCode for .NET?
  - answer: You can acquire a temporary license for Aspose.BarCode for .NET by visiting
      [this link](https://purchase.aspose.com/temporary-license/).
    question: How can I obtain a temporary license for Aspose.BarCode for .NET?
  type: FAQPage
second_title: Aspose.BarCode .NET API
title: Aspose.BarCode を使用した Aztec バーコードの作成（.NET）
url: /ja/net/aztec-barcode-encoding/aztec-symbol-mode-example/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.BarCode for .NET を使用した Aztec シンボルモードのマスター

If you're looking to **create aztec barcode .net** quickly and reliably, Aspose.BarCode for .NET gives you a full‑featured API that works on .NET Framework, .NET Core and .NET 5/6+. In this tutorial we’ll explore the four Aztec Symbol Modes—Auto, FullRange, Compact, and Rune—showing you exactly how to switch between them and save the result as an image. By the end you’ll be able to embed Aztec barcodes in any .NET application with just a few lines of code.

## クイック回答
- **.NET で Aztec バーコードを生成するライブラリは何ですか？** Aspose.BarCode for .NET.  
- **Aztec がサポートするシンボルモードは何種類ありますか？** 4 種類：Auto、FullRange、Compact、Rune.  
- **開発にライセンスは必要ですか？** 評価用の無料トライアルで動作しますが、本番環境では商用ライセンスが必要です。  
- **対応している .NET バージョンは？** .NET Framework 4.5+、.NET Core 3.1+、.NET 5+、および .NET 6+.  
- **PNG、JPEG、SVG などの形式で出力できますか？** はい、標準的な画像形式はすべてサポートされています。

## create aztec barcode .net とは？

`create aztec barcode .net` は、Aspose.BarCode API を使用して .NET 環境で Aztec 二次元バーコードを生成するプロセスを指します。API はエンコード、シンボルモードの選択、画像レンダリングを自動的に処理し、開発者はエラー訂正計算やピクセル操作といった低レベルの詳細に悩むことなく、高品質なバーコードを作成できます。

## なぜ Aztec バーコードに Aspose.BarCode を使用するのか？

Aspose.BarCode は **30 以上のバーコードシンボロジー** をサポートし、**10,000 × 10,000 px** までの画像をメモリに全体をロードせずにレンダリングできます。500 ページのドキュメントを **2 秒未満** で処理できるため、高スループットが求められるエンタープライズシナリオに最適です。

## 前提条件

Before we get started, make sure you have the following prerequisites in place:

- .NET 開発の実務知識。  
- マシンに Visual Studio がインストールされていること。  
- Aspose.BarCode for .NET のコピー。You can download it [here](https://releases.aspose.com/barcode/net/). You can also explore other Aspose products [here](https://releases.aspose.com/).

Now that you're all set, let's dive into the Aztec Symbol Mode examples.

## 名前空間のインポート

First, you'll need to import the necessary namespaces to work with Aspose.BarCode for .NET. Open your Visual Studio project and add the following using statements at the top of your code file:

```csharp
using Aspose.BarCode.Generation;
```

With the namespaces in place, you can now start using Aspose.BarCode for .NET.

## Aztec バーコード用の Barcode Generator の設定方法は？

The `BarcodeGenerator` class is the core component that creates barcode images based on the selected symbology and configuration options. It provides a simple API to specify the type of barcode, the data to encode, and various rendering parameters before saving the result to an image file.

```csharp
string path = "Your Directory Path";
System.Console.WriteLine("AztecSymbolModeExample:");

BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.Aztec, "Åspóse.Barcóde©");
```

In this step, we have set up the generator and provided the code text for encoding.

## Aztec Symbol Mode を Auto に設定する方法は？

The `AztecSymbolMode` enumeration defines the four possible symbol modes for Aztec barcodes, and the **Auto** option lets the library automatically choose the most compact size while preserving all data and error‑correction requirements. This mode is ideal for most scenarios where you want the smallest possible barcode without manual tuning.

```csharp
gen.Parameters.Barcode.Aztec.AztecSymbolMode = AztecSymbolMode.Auto;
gen.Save($"{path}AztecSymbolModeAuto.png", BarCodeImageFormat.Png);
```

This step ensures that the Aztec Symbol Mode is automatically determined, and the resulting barcode image is saved.

## FullRange シンボルモードを強制する方法は？

When you need the maximum data capacity, you can select the **FullRange** value of the `AztecSymbolMode` enumeration. This mode disables automatic size reduction, allowing the barcode to store the full range of characters and achieve the highest possible information density, which is useful for large data sets.

```csharp
gen.Parameters.Barcode.Aztec.AztecSymbolMode = AztecSymbolMode.FullRange;
gen.Save($"{path}AztecSymbolModeFullRange.png", BarCodeImageFormat.Png);
```

This will create a barcode with the FullRange Aztec Symbol Mode.

## Compact Aztec バーコードを生成する方法は？

The **Compact** value of the `AztecSymbolMode` enumeration produces a smaller barcode by reducing the number of layers used in the matrix. This results in a more space‑efficient image, making it suitable for applications with limited display area such as mobile screens or small labels.

```csharp
gen.Parameters.Barcode.Aztec.AztecSymbolMode = AztecSymbolMode.Compact;
gen.Save($"{path}AztecSymbolModeCompact.png", BarCodeImageFormat.Png);
```

This step configures the barcode to be generated with the Compact Aztec Symbol Mode.

## Rune Aztec バーコードを作成する方法は？

The **Rune** mode is a specialized variant of the Aztec symbology that encodes numeric data using a custom character set, offering a distinct visual style while retaining the same error‑correction strength as other modes. It is useful when you need a barcode that emphasizes numeric information.

```csharp
gen.CodeText = "123"; // Change the code text if needed
gen.Parameters.Barcode.Aztec.AztecSymbolMode = AztecSymbolMode.Rune;
gen.Save($"{path}AztecSymbolModeRune.png", BarCodeImageFormat.Png);
```

This step changes the code text to "123" and generates a barcode with the Rune Aztec Symbol Mode.

## よくある問題と解決策

- **Image not saving** – 出力フォルダーが存在し、アプリケーションに書き込み権限があることを確認してください。  
- **Unexpected symbol size** – コード内で `EncodeMode` を上書きしていないか確認してください。  
- **License exception** – 試用版は透かしが付加されます。有効なライセンスを適用して透かしを除去してください。

## よくある質問

**Q: バーコード生成における Aztec Symbol Mode の目的は何ですか？**  
A: Aztec Symbol Mode は、ライブラリがデータをレイヤーにどのように詰め込むかを決定し、サイズ、容量、可読性に影響を与えます。

**Q: Aspose.BarCode for .NET で Aztec バーコードのコードテキストを変更できますか？**  
A: はい、`Save` を呼び出す前に `CodeText` プロパティに新しい文字列を代入するだけです。

**Q: Aspose.BarCode for .NET の無料トライアル版は入手可能ですか？**  
A: はい、Aspose.BarCode for .NET の無料トライアル版は [here](https://releases.aspose.com/) からダウンロードできます。

**Q: Aspose.BarCode for .NET の完全なドキュメントはどこで確認できますか？**  
A: 完全なドキュメントは [here](https://reference.aspose.com/barcode/net/) で参照できます。

**Q: Aspose.BarCode for .NET の一時ライセンスはどこで取得できますか？**  
A: 一時ライセンスは [this link](https://purchase.aspose.com/temporary-license/) から取得できます。

## 結論

In this tutorial we explored how to **create aztec barcode .net** using Aspose.BarCode, covering the Auto, FullRange, Compact, and Rune symbol modes. You now have a solid foundation to embed versatile Aztec barcodes into any .NET application, whether it runs on a desktop, web server, or cloud service.

If you have any questions or need further assistance, don't hesitate to reach out to the Aspose.BarCode community on their [support forum](https://forum.aspose.com/c/barcode/13).

---

**最終更新日:** 2026-05-24  
**テスト環境:** Aspose.BarCode 24.11 for .NET  
**作者:** Aspose  

{{< blocks/products/products-backtop-button >}}

## 関連チュートリアル

- [Aspose.BarCode for .NET を使用した Aztec コードテキストエンコーディング](/barcode/net/aztec-barcode-encoding/aztec-code-text-encoding/)
- [barcode generator .net を使用した Aztec バイトエンコーディング](/barcode/net/aztec-barcode-encoding/aztec-bytes-encoding/)
- [エラー訂正付き Aztec バーコードの作成方法（.NET）](/barcode/net/aztec-barcode-encoding/aztec-error-level-example/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}