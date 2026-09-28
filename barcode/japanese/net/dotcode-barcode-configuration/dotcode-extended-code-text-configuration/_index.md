---
date: 2026-09-28
description: Aspose.BarCode for .NET を使用して 2Dマトリックスバーコードを作成する方法を学びます – 拡張コードテキストを使用した
  DotCode バーコード生成のステップバイステップガイドです。
keywords:
- create 2d matrix barcode
- how to generate dotcode
- dotcode extended codetext
lastmod: 2026-09-28
linktitle: DotCode 拡張コードテキスト構成
og_description: Aspose.BarCode for .NET を使用して 2Dマトリックスバーコードを作成する方法を学びます。このガイドでは、拡張コードテキストを使用した
  DotCode バーコードの生成手順をステップバイステップで示します。
og_image_alt: Guide showing how to create a 2d matrix DotCode barcode with extended
  codetext in .NET
og_title: Aspose.BarCode for .NET で 2Dマトリックスバーコードを作成する
schemas:
- author: Aspose
  dateModified: '2026-09-28'
  description: Learn how to create 2d matrix barcode with Aspose.BarCode for .NET
    – a step‑by‑step guide for generating DotCode barcodes with extended code text.
  headline: How to create 2d matrix barcode via Aspose.BarCode for .NET
  type: TechArticle
- questions:
  - answer: Yes. The PNG image produced by the generator can be embedded in iOS, Android,
      or any cross‑platform mobile application.
    question: Can I use the generated barcode in a mobile app?
  - answer: Use the `AddECICodetext` method with the appropriate `ECIEncodings` (e.g.,
      `ECIEncodings.Base64`) to embed binary payloads.
    question: What if I need to encode binary data instead of text?
  - answer: Adjust the `XDimension.Pixels` property; higher values increase module
      size, while lower values make the barcode more compact.
    question: How do I change the barcode size without affecting readability?
  - answer: Yes. Set `gen.Parameters.Barcode.Margin` to define the desired quiet zone
      in pixels.
    question: Is there a way to add a quiet zone around the barcode?
  - answer: The latest Aspose.BarCode releases are compatible with .NET 8; just reference
      the appropriate NuGet package version.
    question: Does the library support .NET 8?
  type: FAQPage
second_title: Aspose.BarCode .NET API
tags:
- dotcode
- Aspose.BarCode
- .NET barcode generation
- 2d matrix barcode
title: Aspose.BarCode for .NET を使用した 2Dマトリックスバーコードの作成方法
url: /ja/net/dotcode-barcode-configuration/dotcode-extended-code-text-configuration/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.BarCode for .NET を使用した 2D マトリックスバーコードの作成方法

## はじめに

バーコードの生成と管理の分野において、Aspose.BarCode for .NET は **50 以上の入力および出力フォーマット** をサポートし、ファイル全体をメモリに読み込むことなく数百ページにわたるドキュメントを処理できる汎用的なソリューションとして際立っています。製品トラッキング、在庫管理、またはデータリッチなアプリケーション向けにバーコードが必要な場合、拡張コードテキストを持つ **2d マトリックスバーコード**（例: DotCode）を作成することで、テキストとバイナリの両方のペイロードをコンパクトな正方形シンボルに埋め込むことができます。このチュートリアルでは、拡張コードテキストの構築手順をステップバイステップで解説し、最終画像のレンダリングまでを案内します。

## クイック回答
- **“create dotcode extended codetext” とは何ですか？** DotCode バーコードを構築し、FNC1、ECICodetext、プレーンテキスト、シンボル区切り文字を単一の拡張ペイロードに含めることを意味します。  
- **必要なライブラリはどれですか？** Aspose.BarCode for .NET。  
- **ライセンスは必要ですか？** 評価用には一時ライセンスで動作しますが、本番環境ではフルライセンスが必要です。  
- **サポートされている .NET バージョンは？** .NET Framework 4.5 以上、.NET Core 3.1 以上、.NET 5/6/7 以上。  
- **実装にどれくらい時間がかかりますか？** 基本的な例で約 10〜15 分です。

## DotCode 拡張コードテキストの作成方法

プロジェクトを読み込み、ディレクトリを設定し、拡張コードテキストを構築して画像を生成します—コードは 12 行未満です。以下の直接的な回答が全体の流れを要約しています。

`EncodeTypes.DotCode` を指定して `BarcodeGenerator` をロードし、`DotCodeExtendedCodetextBuilder` を使用して拡張コードテキストを構築（FNC1、ECICodetext、プレーンテキスト、FNC3 区切り文字を追加）し、`Save` を呼び出して PNG ファイルを書き出します。この手順で、単一の呼び出しで完全に準拠した 2d マトリックスバーコードが作成されます。

## DotCode 拡張コードテキストとは？

**dotcode 拡張コードテキスト** は、FNC1 識別子、ECICodetext、プレーンテキスト、FNC3 区切り文字など複数のデータセグメントを 1 つのペイロードに結合した複合文字列で、DotCode がデコードできる形式です。これにより、単一の 2d マトリックスバーコード内で多言語テキスト、バイナリブロブ、構造化データをエンコードでき、サプライチェーン、医療、IoT シナリオに最適です。

## このタスクに Aspose.BarCode を使用する理由

Aspose.BarCode は、一般的なサーバー ハードウェア上で **1 秒あたり最大 500 ページ** を処理し、DotCode を含む **30 種類以上のバーコードシンボロジー** をサポートします。`GetExtendedCodetext` API は制御文字の正しい配置を保証し、手動での文字列結合エラーを排除し、ISO/IEC 24724 への準拠を確保します。さらに、組み込みのエラー訂正と自動クワイエットゾーン処理を提供し、手動調整の必要性を減らします。

## 前提条件

- **Aspose.BarCode for .NET** – [Aspose.BarCode for .NET ドキュメント](https://reference.aspose.com/barcode/net/) からダウンロードしてください。  
- .NET 開発環境（推奨: Visual Studio 2022 以降）。  
- オプション: 評価用の一時ライセンス ファイル。

## 名前空間のインポート

`using Aspose.BarCode.Generation;`  
`using Aspose.BarCode.ComplexBarcodes;`  

これらの名前空間は、サンプルで必要となる `BarcodeGenerator` クラスと `DotCodeExtendedCodetextBuilder` ヘルパーを公開します。

```csharp
using Aspose.BarCode.Generation;
```

前提条件が整ったので、DotCode 拡張コードテキストの生成プロセスをステップバイステップで解説しましょう。

## 手順 1: ディレクトリ パスの定義

生成された PNG を保存する場所を指定します。アプリケーションが書き込み可能な絶対パスまたは相対パスを使用してください。

```csharp
string path = "Your Directory Path";
```

`"Your Directory Path"` を実際のパスに置き換えてください。

## 手順 2: DotCode 拡張コードテキストの作成

`DotCodeExtendedCodetextBuilder` クラスは、さまざまなセグメントを単一の拡張コードテキスト文字列に組み立てます。

DotCode 拡張コードテキストを作成するには、以下のサブステップに従ってください：

### 2.1 fnc1 フォーマット識別子の追加

FNC1 フォーマット識別子は新しいデータフィールドの開始を示します。GS1 準拠の DotCode シンボルには必須です。

```csharp
DotCodeExtCodetextBuilder textBuilder = new DotCodeExtCodetextBuilder();
textBuilder.AddFNC1FormatIdentifier();
```

### 2.2 ecicodetext の追加

ECICodetext は特殊文字と国際テキストをエンコードします。この例では、UTF‑8 を使用して `"犬Right狗"` をエンコードします。

```csharp
textBuilder.AddECICodetext(ECIEncodings.UTF8, "犬Right狗");
```

### 2.3 プレーンコードテキストの追加

DotCode 拡張コードテキストにプレーンテキストを追加することもできます。ここでは `"Plain text"` を追加します。

```csharp
textBuilder.AddPlainCodetext("Plain text");
```

### 2.4 fnc3 シンボル区切り文字の追加

FNC3 シンボル区切り文字はコードの異なるセクションを分割し、スキャナの可読性を向上させます。

```csharp
textBuilder.AddFNC3SymbolSeparator();
```

### 2.5 fnc3 リーダー初期化の追加

このステップでは、スキャナに続くデータの解釈方法を指示する FNC3 リーダー初期化情報を追加します。

```csharp
textBuilder.AddFNC3ReaderInitialization();
```

### 2.6 コードテキストの生成

`textBuilder` オブジェクトの `GetExtendedCodetext` メソッドを呼び出して、DotCode 拡張コードテキストを生成します。

```csharp
string codetext = textBuilder.GetExtendedCodetext();
```

## 手順 3: DotCode 画像の生成

拡張コードテキストからバーコード画像をレンダリングします。

#### 3.1 バーコードジェネレータの初期化

`BarcodeGenerator` クラスは、任意のバーコードを作成するための Aspose.BarCode のコアオブジェクトです。目的のシンボロジー（`EncodeTypes.DotCode`）と先ほど構築した拡張コードテキストでインスタンス化します。

```csharp
using (BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.DotCode, codetext))
{
    // Set the X-dimension for the barcode (adjust as needed).
    gen.Parameters.Barcode.XDimension.Pixels = 10;

    // Set the DotCode encoding mode to ExtendedCodetext.
    gen.Parameters.Barcode.DotCode.DotCodeEncodeMode = DotCodeEncodeMode.ExtendedCodetext;

    // Save the generated barcode image.
    gen.Save($"{path}DotCodeExtendedCodetext.png", BarCodeImageFormat.Png);
}
```

最後に `Save` を呼び出して PNG ファイルをディスクに書き込みます。この画像はレポート、モバイルアプリ、または印刷ラベルに埋め込む準備が整っています。

## よくある問題と解決策

- **エンコーディングが正しくない** – 多言語テキストを追加する際は `ECIEncodings.UTF8` を使用してください。そうしないと文字化けが発生する可能性があります。  
- **ファイルアクセスエラー** – アプリケーションが対象ディレクトリに書き込み権限を持っていることを確認してください。  
- **クワイエットゾーンが欠如** – スキャナがシンボル周囲に余白を必要とする場合は、`gen.Parameters.Barcode.Margin` を設定してください。

## よくある質問

**Q: 生成したバーコードをモバイルアプリで使用できますか？**  
A: はい。ジェネレータが生成した PNG 画像は iOS、Android、または任意のクロスプラットフォームモバイルアプリに埋め込むことができます。

**Q: テキストではなくバイナリデータをエンコードしたい場合は？**  
A: `AddECICodetext` メソッドを適切な `ECIEncodings`（例: `ECIEncodings.Base64`）と共に使用して、バイナリペイロードを埋め込みます。

**Q: バーコードのサイズを可読性に影響を与えずに変更するには？**  
A: `XDimension.Pixels` プロパティを調整します。値を大きくするとモジュールサイズが増え、値を小さくするとバーコードがコンパクトになります。

**Q: バーコードの周囲にクワイエットゾーンを追加する方法はありますか？**  
A: はい。`gen.Parameters.Barcode.Margin` を設定して、ピクセル単位で希望のクワイエットゾーンを定義します。

**Q: ライブラリは .NET 8 をサポートしていますか？**  
A: 最新の Aspose.BarCode リリースは .NET 8 と互換性があります。適切な NuGet パッケージ バージョンを参照してください。

さらにガイダンスが必要な場合や質問がある場合は、遠慮なく [Aspose.BarCode for .NET ドキュメント](https://reference.aspose.com/barcode/net/) をご覧いただくか、[Aspose.BarCode サポートフォーラム](https://forum.aspose.com/c/barcode/13) でコミュニティと交流してください。

---

**最終更新日:** 2026-09-28  
**テスト環境:** Aspose.BarCode 24.12 for .NET  
**作者:** Aspose

## 関連チュートリアル

- [Aspose.BarCode を使用した DotCode バーコードの作成（自動モード） .NET](/barcode/net/dotcode-barcode-configuration/dotcode-encoding-mode-auto/)
- [Aspose.BarCode for .NET を使用した DataMatrix バーコード生成方法 – ステップバイステップ ガイド](/barcode/net/datamatrix-barcode-configuration/)
- [Aspose.BarCode for .NET で Aztec バーコードを作成する方法](/barcode/net/aztec-barcode-encoding/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}