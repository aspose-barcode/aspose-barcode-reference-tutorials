---
date: 2026-06-14
description: .NET で Aspose.BarCode を使用し、DataMatrix の読み取りと Structured Append バーコードの生成方法を学びます。高速で信頼性の高いバーコードライブラリです。
keywords:
- how to read datamatrix
- DataMatrix structured append
- Aspose.BarCode .NET
linktitle: DataMatrix Structured Append の設定
schemas:
- author: Aspose
  dateModified: '2026-06-14'
  description: Learn how to read datamatrix and generate structured append barcodes
    in .NET using Aspose.BarCode, the fast and reliable barcode library.
  headline: How to Read DataMatrix Append with Aspose.BarCode for .NET
  type: TechArticle
- description: Learn how to read datamatrix and generate structured append barcodes
    in .NET using Aspose.BarCode, the fast and reliable barcode library.
  name: How to Read DataMatrix Append with Aspose.BarCode for .NET
  steps:
  - name: Aspose.BarCode for .NET Library – download it from [here](https://releases.aspose.com/barcode/net/).
    text: Aspose.BarCode for .NET Library – download it from [here](https://releases.aspose.com/barcode/net/).
  - name: You can also browse other Aspose products [here](https://releases.aspose.com/).
    text: You can also browse other Aspose products [here](https://releases.aspose.com/).
  - name: A .NET development environment such as Visual Studio 2022 or Visual Studio
      Code with the C# extension.
    text: A .NET development environment such as Visual Studio 2022 or Visual Studio
      Code with the C# extension.
  type: HowTo
- questions:
  - answer: Aspose.BarCode for .NET.
    question: What library handles DataMatrix structured append?
  - answer: Up to 16 DataMatrix symbols.
    question: How many symbols can a single structured append sequence contain?
  - answer: A free trial works for development and testing.
    question: Do I need a license for development?
  - answer: .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.
    question: Which .NET versions are supported?
  - answer: Yes, you can decode from a byte array or stream.
    question: Can I read the barcode without an image file?
  type: FAQPage
second_title: Aspose.BarCode .NET API
title: Aspose.BarCode for .NET を使用した DataMatrix Append の読み取り方法
url: /ja/net/datamatrix-barcode-reading/datamatrix-structured-append-configuration/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.BarCode for .NET を使用した DataMatrix 構造化付加構成

.NET アプリケーションで構造化付加を使用して **how to read datamatrix** を探している開発者の方には、Aspose.BarCode for .NET が最適なソリューションです。このステップバイステップガイドでは、複数のシンボルに分割された DataMatrix バーコードの生成とデコードの方法を解説します。チュートリアルの最後までに、Aspose.BarCode for .NET を使って DataMatrix 構造化付加バーコードの作成、設定、読み取りが自在にできるようになります。

## クイック回答
- **DataMatrix 構造化付加を処理するライブラリは何ですか？** Aspose.BarCode for .NET.
- **単一の構造化付加シーケンスに含められるシンボル数は最大何個ですか？** 最大 16 個の DataMatrix シンボル。
- **開発にライセンスは必要ですか？** 無料トライアルで開発およびテストが可能です。
- **サポートされている .NET バージョンはどれですか？** .NET Framework 4.5 以上、.NET Core 3.1 以上、.NET 5/6/7。
- **画像ファイルなしでバーコードを読み取れますか？** はい、バイト配列またはストリームからデコードできます。

## how to read datamatrix とは？
**how to read datamatrix** は、DataMatrix シンボルをデコードし、必要に応じて構造化付加シーケンスの各部分を結合して元のデータペイロードを取得するプロセスを指します。Aspose.BarCode はこのワークフローを組み込みでサポートし、シンボルの順序付けとデータの連結を自動的に処理します。

## DataMatrix 構造化付加に Aspose.BarCode を使用する理由
Aspose.BarCode は **30 以上のバーコードシンボロジー** をサポートし、典型的なサーバーハードウェア上で **200 ms 未満** に **10,000 × 10,000 px** までの画像をデコードできます。また、**ゼロ依存性デプロイ** を提供しており、追加のネイティブ DLL は不要で、Windows、Linux、macOS の .NET ランタイムでも動作します。

## 前提条件

1. Aspose.BarCode for .NET ライブラリ – [here](https://releases.aspose.com/barcode/net/) からダウンロードしてください。
2. 他の Aspose 製品は [here](https://releases.aspose.com/) でも閲覧できます。
3. Visual Studio 2022 や C# 拡張機能付き Visual Studio Code などの .NET 開発環境。

それでは、DataMatrix 構造化付加バーコードの作成と読み取りを始めましょう。

## 名前空間のインポート

最初のステップは、バーコード API を公開する名前空間をインポートすることです。

`BarCodeWriter` クラスはバーコード作成のエントリーポイントで、`BarCodeReader` はデコードを担当します。

```csharp
using Aspose.BarCode.BarCodeRecognition;
using Aspose.BarCode.Generation;
using System;
using System.Drawing;
```

必要な名前空間をインポートしたので、構造化付加バーコードを生成しましょう。

## DataMatrix 構造化付加バーコードの読み取り方法

生成した画像（またはストリーム）を `BarCodeReader` にロードし、`ReadStructuredAppend` オプションを有効にして `ReadBarcode` を呼び出します。リーダーは自動的に結合されたデータを返し、`StructuredAppendFileId`、`StructuredAppendTotalCount`、`StructuredAppendSegmentId` などのシーケンス情報を公開します。結合結果は単一の文字列として返され、カスタム処理のためにリーダーの `StructuredAppendSegmentId` プロパティから個々のセグメント識別子も取得できます。

```csharp
    using (BarCodeReader reader = new BarCodeReader(bitmap, DecodeType.DataMatrix))
    {
        reader.ReadBarCodes();

        Console.WriteLine("Barcode ID: {0}", reader.FoundBarCodes[0].Extended.DataMatrix.StructuredAppendBarcodeId);
        Console.WriteLine("Barcodes count: {0}", reader.FoundBarCodes[0].Extended.DataMatrix.StructuredAppendBarcodesCount);
        Console.WriteLine("File ID: {0}", reader.FoundBarCodes[0].Extended.DataMatrix.StructuredAppendFileId);
    }
}
```

このステップでは、リーダーを使用してバーコード ID、総カウント、ファイル ID を抽出し、構造化付加設定が正しく解釈されたことを確認します。

## 手順 1: DataMatrix 構造化付加構成の設定

DataMatrix 構造化付加バーコードを作成するには、構成を設定する必要があります。ディレクトリパス、バーコード ID、バーコード数、ファイル ID を定義します。

```csharp
string path = "Your Directory Path";

using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.DataMatrix, "Aspose"))
{
    generator.Parameters.Barcode.XDimension.Pixels = 4;

    // Set DataMatrix structured append mode
    generator.Parameters.Barcode.DataMatrix.StructuredAppendBarcodeId = 3;
    generator.Parameters.Barcode.DataMatrix.StructuredAppendBarcodesCount = 5;
    generator.Parameters.Barcode.DataMatrix.StructuredAppendFileId = 150;

    // Generate the barcode image
    Bitmap bitmap = generator.GenerateBarCodeImage();
```

このステップでは、目的のパラメータで DataMatrix バーコードを設定しました。

## よくある問題と解決策

- **セグメント順序が正しくない:** `StructuredAppendSegmentId` の値が 0 から順番に連続していることを確認してください。そうでないとリーダーはデータを正しく再構成できません。
- **総カウントが一致しない:** `StructuredAppendTotalCount` はすべてのシンボルで同一である必要があります。不一致があるとリーダーはシーケンスを不完全とみなします。
- **画像品質:** 低解像度の画像はデコード失敗の原因となります。バーコードをビットマップにレンダリングする際は少なくとも **300 dpi** を目指してください。

## よくある質問

### Q1: DataMatrix 構造化付加とは何か、なぜ使用されるのか？

A1: DataMatrix 構造化付加は、大量のデータを複数の小さなバーコードに分割できる機能です。単一のバーコードのスペースが限られている場合やデータを効率的に整理したい場合に特に有用です。物流、医療、製造業で一般的に使用されています。

### Q2: Aspose.BarCode for .NET をオープンソースプロジェクトで使用できますか？

A2: はい、Aspose.BarCode for .NET はオープンソースプロジェクトで使用できる無料トライアル版を提供しています。トライアル版は [here](https://releases.aspose.com/) から入手できます。

### Q3: Aspose.BarCode for .NET のコミュニティサポートはありますか？

A3: はい、Aspose.BarCode フォーラム [here](https://forum.aspose.com/c/barcode/13) でコミュニティサポートを受けたり、他のユーザーと交流できます。

### Q4: Aspose.BarCode for .NET の一時ライセンスはどのように取得できますか？

A4: 評価やテスト用の一時ライセンスが必要な場合は、[here](https://purchase.aspose.com/temporary-license/) から取得できます。

### Q5: Aspose.BarCode for .NET は他のバーコードタイプもサポートしていますか？

A5: はい、Aspose.BarCode for .NET は QR コード、Code 128、EAN‑13 など多数のバーコードタイプをサポートしています。サポートされているバーコードタイプの全リストは、完全なドキュメントを [here](https://reference.aspose.com/barcode/net/) で確認できます。

---

**最終更新日:** 2026-06-14  
**テスト環境:** Aspose.BarCode 24.11 for .NET  
**作者:** Aspose

## 関連チュートリアル

- [Aspose.BarCode for .NET を使用した DataMatrix リーダープログラミング](/barcode/net/datamatrix-barcode-reading/datamatrix-reader-programming/)
- [Aspose.BarCode for .NET で DataMatrix バーコードを生成](/barcode/net/datamatrix-barcode-reading/datamatrix-versions/)
- [Aspose.BarCode for .NET で DataMatrix マクロ構成をマスター](/barcode/net/datamatrix-barcode-configuration/datamatrix-macro-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< blocks/products/products-backtop-button >}}
{{< /blocks/products/pf/main-wrap-class >}}