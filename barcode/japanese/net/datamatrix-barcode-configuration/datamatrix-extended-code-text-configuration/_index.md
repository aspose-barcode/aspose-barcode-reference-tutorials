---
date: 2026-09-23
description: Aspose.BarCode を使用して .NET で拡張コードテキスト付きの DataMatrix バーコードを生成する方法を学びます。在庫管理や物流アプリケーションに最適です。
keywords:
- how to use aspose
- create barcode for inventory
- barcode generation .net core
- generate barcode image c#
lastmod: 2026-09-23
linktitle: DataMatrix 拡張コードテキスト構成
og_description: Aspose.BarCode を使用して .NET で拡張コードテキスト付きの DataMatrix バーコードを生成する方法です。在庫管理や物流ソリューション向けの簡単なステップバイステップガイドをご覧ください。
og_image_alt: Screenshot of a DataMatrix barcode generated with Aspose.BarCode in
  a .NET console app
og_title: Aspose.BarCode を使用して .NET で DataMatrix コードテキストを作成する方法
schemas:
- author: Aspose
  dateModified: '2026-09-23'
  description: Learn how to use Aspose.BarCode to generate a DataMatrix barcode with
    extended code text in .NET, ideal for inventory and logistics applications.
  headline: How to use Aspose.BarCode to create DataMatrix code text in .NET
  type: TechArticle
- description: Learn how to use Aspose.BarCode to generate a DataMatrix barcode with
    extended code text in .NET, ideal for inventory and logistics applications.
  name: How to use Aspose.BarCode to create DataMatrix code text in .NET
  steps:
  - name: Define the output folder
    text: Specify where the generated barcode image will be saved. Replace the placeholder
      with a valid path on your machine.
  - name: Build the extended code text
    text: '`DataMatrixExtCodetextBuilder` is a helper class that assembles the extended
      code text according to the DataMatrix specification. It automatically inserts
      the required ECI (Extended Channel Interpretation) markers. This mix demonstrates
      how you can combine Unicode characters, C40 encoding, plain tex'
  - name: Generate the final codetext string
    text: After configuring all parts, retrieve the combined string that Aspose.BarCode
      will embed into the barcode.
  - name: Create the DataMatrix barcode
    text: '`BarcodeGenerator` is the core class that produces barcode images. Instantiate
      it with `EncodeTypes.DataMatrix` and the extended codetext, then set visual
      parameters such as X‑dimension, image format, and optional human‑readable text.
      The above code **creates barcode aspose .net** with the desired e'
  - name: Verify the barcode by reading it back
    text: '`BarCodeReader` validates that the generated symbol can be decoded correctly,
      which is essential for automated test pipelines and quality assurance. If everything
      is set up properly, the console will output the exact extended code text you
      built earlier.'
  type: HowTo
- questions:
  - answer: Aspose.BarCode for .NET
    question: What library is needed?
  - answer: DataMatrix with extended code text
    question: Which barcode type?
  - answer: Yes, the API is cross‑platform
    question: Can I use .NET Core / .NET 6?
  - answer: A free trial works for development; a license is required for production
    question: Do I need a license for testing?
  - answer: About 10‑15 minutes for a basic example
    question: How long does implementation take?
  type: FAQPage
second_title: Aspose.BarCode .NET API
tags:
- Aspose.BarCode
- DataMatrix
- .NET barcode
- C# barcode generation
- inventory labeling
title: Aspose.BarCode を使用して .NET で DataMatrix コードテキストを作成する方法
url: /ja/net/datamatrix-barcode-configuration/datamatrix-extended-code-text-configuration/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.BarCode を使用して .NET で DataMatrix コードテキストを作成する方法

最新の .NET アプリケーションにバーコードを統合することは、もはやニッチな作業ではなく、在庫管理、物流、モバイルスキャンソリューションのコア要件です。このガイドでは **Aspose.BarCode の使い方** を学び、拡張コードテキストを持つ DataMatrix バーコードを設定し、画像を生成し、プログラムで検証する方法を紹介します。このアプローチが在庫用バーコード作成に最適であり、.NET Core や .NET 6 プロジェクトにどのように適合するかを確認できます。

## クイック回答
- **必要なライブラリは何ですか？** Aspose.BarCode for .NET  
- **どのバーコードタイプですか？** 拡張コードテキスト付き DataMatrix  
- **.NET Core / .NET 6 を使用できますか？** はい、API はクロスプラットフォームです  
- **テストにライセンスは必要ですか？** 開発には無料トライアルで動作しますが、本番環境ではライセンスが必要です  
- **実装にどれくらい時間がかかりますか？** 基本的な例で約 10‑15 分です  

## Aspose.BarCode for .NET とは？
Aspose.BarCode for .NET は商用ライブラリで、開発者が DataMatrix、QR、Code 128 など 30 種類以上のバーコードシンボルを生成および認識でき、外部依存なしで最大 10,000 × 10,000 ピクセルの画像を作成できます。 .NET Framework 4.5 以降、.NET Core 3.1 以降、.NET 5/6/7 をサポートしています。

## なぜ DataMatrix の拡張コードテキストを使用するのか？
DataMatrix の拡張コードテキストを使用すると、単一シンボル内に UTF‑8、C40、Text、X12 など複数のエンコーディング方式を埋め込むことができ、最大 **3116 コードワード**（約 155 KB のデータ）をコンパクトな正方形に収められます。この機能は、マルチリンガルな製品ラベリング、医療機器のトラッキング、アルファベットと数字の ID とバイナリペイロードを組み合わせる必要があるスマートパッケージングに最適です。

## 前提条件

開始する前に、以下が揃っていることを確認してください：

1. **Aspose.BarCode for .NET** – 公式サイトの **[Aspose.BarCode .NET ダウンロードページ](https://releases.aspose.com/barcode/net/)** からダウンロードしてください。  
2. **.NET 開発環境** – Visual Studio、Rider、または .NET SDK がインストールされた VS Code。  
3. **基本的な C# の知識** – クラス、名前空間、`using` ディレクティブに慣れている必要があります。  

## 名前空間のインポート

C# ファイルの先頭に必要な名前空間を追加し、コンパイラがバーコードクラスの場所を認識できるようにします。

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode.BarCodeRecognition;
```

これらの名前空間により、バーコードの生成機能と認識機能の両方にアクセスできます。

## DataMatrix の拡張コードテキストを設定する方法

ビルダーをロードし、目的のセグメントを追加し、Aspose.BarCode に ECI マーカーを自動的に処理させます。この直接的な説明では、正確な手順を示します：`DataMatrixExtCodetextBuilder` を作成し、Unicode、C40、プレーンテキスト、Text モードのセグメントを追加し、最後にジェネレーター用の結合文字列を取得します。

### 手順 1: 出力フォルダーの定義

生成されたバーコード画像の保存先を指定します。プレースホルダーをマシン上の有効なパスに置き換えてください。

```csharp
string path = "Your Directory Path";
```

### 手順 2: 拡張コードテキストの構築

`DataMatrixExtCodetextBuilder` は、DataMatrix 仕様に従って拡張コードテキストを組み立てるヘルパークラスです。必要な ECI（拡張チャネル解釈）マーカーを自動的に挿入します。

```csharp
DataMatrixExtCodetextBuilder codetextBuilder = new DataMatrixExtCodetextBuilder();
codetextBuilder.AddECICodetext(ECIEncodings.UTF8, "犬Right狗");
codetextBuilder.AddECICodetextWithEncodeMode(ECIEncodings.UTF8, DataMatrixEncodeMode.C40, "ABCDE");
codetextBuilder.AddPlainCodetext("test");
codetextBuilder.AddCodetextWithEncodeMode(DataMatrixEncodeMode.Text, "abcde");
```

この例は、Unicode 文字、C40 エンコーディング、プレーンテキスト、Text モードを単一の DataMatrix シンボルに組み合わせる方法を示しています。

### 手順 3: 最終的なコードテキスト文字列の生成

すべてのパーツを設定した後、Aspose.BarCode がバーコードに埋め込む結合文字列を取得します。

```csharp
string codetext = codetextBuilder.GetExtendedCodetext();
```

### 手順 4: DataMatrix バーコードの作成

`BarcodeGenerator` はバーコード画像を生成するコアクラスです。`EncodeTypes.DataMatrix` と拡張コードテキストでインスタンス化し、X‑dimension、画像フォーマット、オプションのヒューマンリーダブルテキストなどの視覚パラメータを設定します。

```csharp
using (var generator = new BarcodeGenerator(EncodeTypes.DataMatrix, codetext))
{
    generator.Parameters.Barcode.XDimension.Pixels = 4;
    generator.Parameters.Barcode.CodeTextParameters.TwoDDisplayText = "Extended Codetext";
    generator.Parameters.Barcode.DataMatrix.DataMatrixEncodeMode = DataMatrixEncodeMode.ExtendedCodetext;

    generator.Save($"{path}DataMatrixExtendedCodetext.png", BarCodeImageFormat.Png);
}
```

上記のコードは、目的の拡張コードテキストを使用して **barcode aspose .net** を作成し、PNG ファイルとして保存します。

### 手順 5: バーコードを読み取りで検証する

`BarCodeReader` は、生成されたシンボルが正しくデコードできることを検証し、これは自動テストパイプラインや品質保証に不可欠です。

```csharp
using (var reader = new BarCodeReader(generator.GenerateBarCodeImage(), DecodeType.DataMatrix))
{
    foreach (BarCodeResult result in reader.ReadBarCodes())
        Console.WriteLine("DataMatrixExtendedCodetext:" + result.CodeText);
}
```

すべてが正しく設定されていれば、コンソールに先ほど構築した正確な拡張コードテキストが出力されます。

## よくある落とし穴とトラブルシューティング

| 問題 | 原因 | 対策 |
|-------|--------|-----|
| バーコードが読めない | X‑dimension が低すぎる | `XDimension.Pixels` を増やす（例: 4 → 6） |
| 文字化け | ECI エンコーディングが間違っている | `ECIEncodings.UTF8` が文字セットと一致していることを確認 |
| ファイルが保存されない | パスが無効 | 絶対パスを使用するか、フォルダーが存在することを確認 |
| ライセンス例外 | トライアル期限切れ | 一時ライセンスまたはフルライセンスを適用する（FAQ 参照） |

## よくある質問

### Q1: Aspose.BarCode for .NET とは？
A1: Aspose.BarCode for .NET は、開発者が DataMatrix、QR、Code128 など多種多様なバーコードシンボルを生成および認識できる強力なライブラリです。

### Q2: Aspose.BarCode for .NET のドキュメントはどこで見つけられますか？
A2: 完全な API リファレンスは **[Aspose.BarCode .NET API reference](https://reference.aspose.com/barcode/net/)** で確認できます。

### Q3: Aspose.BarCode for .NET の無料トライアルはありますか？
A3: はい、無料トライアル版は **[Aspose.BarCode free trial download](https://releases.aspose.com/)** からダウンロードできます。

### Q4: テスト用の一時ライセンスはどう取得しますか？
A4: 評価目的の一時ライセンスは **[Aspose temporary license request page](https://purchase.aspose.com/temporary-license/)** でリクエストできます。

### Q5: Aspose.BarCode for .NET のサポートや質問はどこで受けられますか？
A5: 公式の Aspose.BarCode フォーラムが最適なサポート先です: **[Aspose.BarCode forum](https://forum.aspose.com/c/barcode/13)**。

---

**最終更新日:** 2026-09-23  
**テスト環境:** Aspose.BarCode 24.11 for .NET  
**著者:** Aspose

## 関連チュートリアル

- [Aspose.BarCode for .NET を使用して DataMatrix バーコードを生成する方法 – ステップバイステップガイド](/barcode/net/datamatrix-barcode-configuration/)
- [Aspose.BarCode for .NET (C#) で ASCII モードの DataMatrix バーコードを生成する](/barcode/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-ascii/)
- [Aspose.BarCode for .NET を使用してテキストエンコーディング付き Aztec バーコードを生成する](/barcode/net/aztec-barcode-encoding/aztec-code-text-encoding/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}