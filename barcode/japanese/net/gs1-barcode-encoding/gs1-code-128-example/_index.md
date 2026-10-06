---
date: 2026-09-08
description: Aspose.BarCode for .NET を使用した C# で code 128 バーコードを作成し、GS1 バーコードを生成する方法を学びます。ステップバイステップのガイド、前提条件、コード不要のカスタマイズが含まれます。
keywords:
- create code 128 barcode
- generate gs1 barcode
- how to generate barcode
- create barcode from data
- step by step barcode
lastmod: 2026-09-08
linktitle: GS1 Code 128 の例
og_description: Aspose.BarCode for .NET を使用した C# で code 128 バーコードを作成し、GS1 バーコードを生成する方法を学びます。ステップバイステップのガイドに従って、バーコード画像を迅速に生成・保存できます。
og_image_alt: 'Developer guide: create code 128 barcode with Aspose.BarCode .NET'
og_title: Aspose.BarCode を使用して GS1 の code 128 バーコードを作成する方法
schemas:
- author: Aspose
  dateModified: '2026-09-08'
  description: Learn how to create code 128 barcode and generate GS1 barcodes in C#
    with Aspose.BarCode for .NET. Step‑by‑step guide, prerequisites, and code‑free
    customization.
  headline: How to create code 128 barcode with GS1 using Aspose.BarCode
  type: TechArticle
- description: Learn how to create code 128 barcode and generate GS1 barcodes in C#
    with Aspose.BarCode for .NET. Step‑by‑step guide, prerequisites, and code‑free
    customization.
  name: How to create code 128 barcode with GS1 using Aspose.BarCode
  steps:
  - name: set your directory path
    text: Define the folder where the generated image will be stored. Keeping the
      path configurable makes the code reusable across environments. Replace `"Your
      Directory Path"` with an absolute or relative path that your application can
      write to, such as `@"C:\Barcodes"` or `Path.Combine(Environment.CurrentDi
  - name: create a GS1 Code 128 barcode
    text: Create the barcode generator, specify the symbology, and provide GS1‑formatted
      data. The data string must include Application Identifiers wrapped in parentheses.
      The example uses the GTIN `(01)12345678901231`, a serial number `(21)ASPOSE`,
      and an additional custom AI `(30)9876`. Aspose.BarCode autom
  - name: customize barcode parameters
    text: Adjust visual parameters such as `XDimension` (the width of the narrow bar)
      to control the barcode’s density. You can also modify height, colors, and margins.
      Setting `XDimension = 2` yields a barcode that is easily scannable by most handheld
      readers while keeping the image size modest.
  - name: save the barcode image
    text: Persist the generated barcode to disk. You may choose PNG for lossless quality,
      JPEG for smaller files, or TIFF for printing workflows. The `Save` method writes
      the image file in the format indicated by the file extension. Replace `GS1Code128Example.png`
      with any valid filename and extension that ma
  - name: verify the barcode (optional)
    text: After saving, you can load the image back into your application or use a
      barcode scanner to confirm that the encoded data matches the original string.
      This step is useful during development and automated testing.
  type: HowTo
- questions:
  - answer: Yes, Aspose.BarCode works with .NET Core and .NET 5/6, so you can expose
      a lightweight REST endpoint that returns barcode images on demand.
    question: Can I generate barcodes in a web API without installing the full .NET
      Framework?
  - answer: Absolutely. Loop through a collection of data strings, instantiate a `BarcodeGenerator`
      for each, and call `Save` inside the loop. The library is thread‑safe for parallel
      processing.
    question: Does the library support batch generation of multiple barcodes?
  - answer: Use Aspose.PDF to create a PDF document, then call `PdfPage.AddImage`
      with the barcode image stream. This avoids writing intermediate files to disk.
    question: Is there a way to embed the barcode directly into a PDF?
  - answer: Set `BarcodeGenerator.Options.Barcode.XDimension` to at least 0.33 mm
      and enable `BarHeight` according to the label size. Aspose.BarCode validates
      the AI format and throws an exception for invalid data.
    question: How can I ensure the barcode meets ISO/GS1 quality standards?
  - answer: Aspose offers perpetual, subscription, and cloud‑based licensing models.
      A trial license works for evaluation, but a paid license removes the evaluation
      watermark and unlocks all features.
    question: What licensing options are available for production use?
  type: FAQPage
second_title: Aspose.BarCode .NET API
tags:
- create code 128 barcode
- Aspose.BarCode
- .NET barcode generation
title: Aspose.BarCode を使用して GS1 の code 128 バーコードを作成する方法
url: /ja/net/gs1-barcode-encoding/gs1-code-128-example/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.BarCode を使用して GS1 のコード 128 バーコードを作成する方法

このチュートリアルでは、.NET 用 Aspose.BarCode ライブラリを使用して **コード 128 バーコードを作成** し、GS1 標準に準拠させる方法を学びます。在庫管理、出荷、POS など、さまざまな用途にバーコードが必要な場合でも、開発環境の設定から最終画像の保存までの手順をすべて解説するので、数分で信頼性の高いバーコードの生成を開始できます。

## クイック回答
- **バーコードを生成するための主要クラスは何ですか？** `BarcodeGenerator` はバーコード画像を作成および構成します。  
- **GS1 Code 128 が使用するシンボロジーはどれですか？** `EncodeTypes.Code128` タイプを使用し、GS1 固有のデータフォーマットを適用します。  
- **開発にライセンスは必要ですか？** 無料トライアルで評価は可能ですが、製品版には商用ライセンスが必要です。  
- **画像形式を変更できますか？** はい、ファイル拡張子を変更することで PNG、JPEG、BMP、TIFF のいずれかで保存できます。  
- **サポートされている .NET バージョンは何ですか？** .NET Framework 4.5 以上、.NET Core 3.1 以上、.NET 5 以上、.NET 6 以上です。

## コード 128 バーコードの作成とは？
`コード 128 バーコードの作成` とは、Code 128 シンボロジーを使用して英数字データをエンコードする一次元バーコードを生成することを指します。Code 128 はフル ASCII セットをサポートし、GS1 アプリケーション識別子（AI）を埋め込めるため、物流分野で広く採用されています。製品識別子、シリアル番号、カスタムデータなどを格納でき、さまざまなビジネスシナリオに適しています。

## GS1 Code 128 に Aspose.BarCode を使用する理由
Aspose.BarCode は **30 以上のバーコードシンボロジー** をサポートし、**10,000 × 10,000 px** までの画像を品質低下なしでレンダリングできるため、高解像度ラベル印刷に最適です。ライブラリは GS1 データ構造を自動的に検証し、製造ラインでの不正なバーコードリスクを低減します。さらに、サイズ、色、レイアウトの豊富なカスタマイズオプションにより、厳格な業界基準にも対応できます。

## 前提条件
開始する前に、以下を用意してください。

1. **.NET 開発環境** – Visual Studio 2022、Rider、または .NET 6+ をサポートする任意の IDE。  
2. **Aspose.BarCode for .NET** – **Aspose.BarCode for .NET ダウンロードページ**（[https://releases.aspose.com/barcode/net/](https://releases.aspose.com/barcode/net/)）からダウンロードし、NuGet パッケージ `Aspose.BarCode` をプロジェクトに追加します。  
3. **基本的な C# 知識** – コンソールまたは Windows アプリケーションの作成に慣れていることが望ましいです。  
4. **GS1 Code 128 の理解** – 任意ですが役立ちます。GS1 は `(01)`（GTIN）や `(21)`（シリアル番号）などのアプリケーション識別子（AI）を使用します。

## コード 128 バーコードの作成手順

ライブラリを読み込み、バーコードタイプを設定し、GS1 データを指定し、サイズをカスタマイズして、最後に画像を保存します。「コード 128 バーコードを作成する方法？」への直接的な答えは、**`BarcodeGenerator` を `EncodeTypes.Code128` と GS1 形式データでインスタンス化し、必要に応じて `XDimension` を調整し、目的のファイル名と形式で `Save` を呼び出す** ことです。以下のセクションで各手順を詳しく説明します。

### 手順 1: ディレクトリパスの設定
生成された画像を保存するフォルダーを定義します。パスを設定可能にしておくことで、環境間でコードを再利用しやすくなります。

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;
```

`"Your Directory Path"` を、アプリケーションが書き込み可能な絶対パスまたは相対パスに置き換えてください。例: `@"C:\Barcodes"` または `Path.Combine(Environment.CurrentDirectory, "Output")`。

### 手順 2: GS1 Code 128 バーコードの作成
バーコードジェネレータを作成し、シンボロジーを指定し、GS1 形式のデータを提供します。データ文字列は括弧で囲まれたアプリケーション識別子を含める必要があります。

```csharp
string path = "Your Directory Path";
```

この例では GTIN `(01)12345678901231`、シリアル番号 `(21)ASPOSE`、カスタム AI `(30)9876` を使用しています。Aspose.BarCode は GS1 準拠のために必要な FNC1 文字を自動的に挿入します。

### 手順 3: バーコードパラメータのカスタマイズ
`XDimension`（狭いバーの幅）などの視覚パラメータを調整して、バーコードの密度を制御します。高さ、色、余白も変更可能です。

```csharp
BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.GS1Code128, "(01)12345678901231(21)ASPOSE(30)9876");
```

`XDimension = 2` に設定すると、ほとんどのハンドヘルドリーダーで容易にスキャンでき、画像サイズも抑えられます。

### 手順 4: バーコード画像の保存
生成したバーコードをディスクに永続化します。PNG はロスレス品質、JPEG はファイルサイズ削減、TIFF は印刷ワークフロー向けに適しています。`Save` メソッドは拡張子から画像形式を自動判別します。

```csharp
gen.Parameters.Barcode.XDimension.Pixels = 2;
```

`GS1Code128Example.png` を、目的の出力形式に合わせた任意の有効なファイル名と拡張子に置き換えてください。

### 手順 5: バーコードの検証（オプション）
保存後、アプリケーションに画像を再読み込みするか、バーコードスキャナで読み取って、エンコードされたデータが元の文字列と一致することを確認できます。このステップは開発時や自動テストで有用です。

```csharp
gen.Save($"{path}GS1Code128Example.png", BarCodeImageFormat.Png);
```

## よくある問題とトラブルシューティングのヒント
- **FNC1 が検出されない** – データ文字列が開括弧で始まり、有効な GS1 AI を含んでいることを確認してください。ライブラリは認識されたパターンに対してのみ自動的に FNC1 を挿入します。  
- **画像が保存されない** – 対象ディレクトリが存在し、アプリケーションに書き込み権限があるか確認してください。`Directory.CreateDirectory(path)` を使用して必要に応じて作成できます。  
- **バーコードが密すぎる** – `XDimension` を減らすか、画像の高さを増やして、リーダーが狭いバーを読み取りやすくします。  
- **サポートされていない文字** – Code 128 はフル ASCII セットのみエンコード可能です。範囲外の Unicode 文字は使用しないでください。

## よくある質問

**Q: フル .NET Framework をインストールせずに Web API でバーコードを生成できますか？**  
**A:** はい、Aspose.BarCode は .NET Core および .NET 5/6 と互換性があるため、軽量な REST エンドポイントからオンデマンドでバーコード画像を返すことができます。

**Q: 複数のバーコードを一括生成することは可能ですか？**  
**A:** もちろんです。データ文字列のコレクションをループし、各項目ごとに `BarcodeGenerator` をインスタンス化して `Save` を呼び出します。ライブラリは並列処理に対してスレッドセーフです。

**Q: バーコードを直接 PDF に埋め込む方法はありますか？**  
**A:** Aspose.PDF を使用して PDF ドキュメントを作成し、`PdfPage.AddImage` にバーコード画像ストリームを渡します。これにより中間ファイルをディスクに書き出す必要がなくなります。

**Q: バーコードが ISO/GS1 の品質基準を満たすことを保証するには？**  
**A:** `BarcodeGenerator.Options.Barcode.XDimension` を最低 0.33 mm に設定し、ラベルサイズに応じて `BarHeight` を有効にします。Aspose.BarCode は AI フォーマットを検証し、無効なデータがある場合は例外をスローします。

**Q: 本番環境で利用できるライセンス形態は？**  
**A:** 永続ライセンス、サブスクリプション、クラウドベースのライセンスモデルがあります。トライアルライセンスは評価用に利用できますが、評価ウォーターマークが除去され、すべての機能が解放されるのは有料ライセンスです。

## 追加リソース

- **Documentation** – 完全な API リファレンスは [https://reference.aspose.com/barcode/net/](https://reference.aspose.com/barcode/net/) で確認できます。  
- **Download** – 最新のライブラリリリースは [https://releases.aspose.com/barcode/net/](https://releases.aspose.com/barcode/net/) から取得できます。  
- **Free trial** – 30 日間のトライアルは [https://releases.aspose.com/](https://releases.aspose.com/) で開始できます。  
- **Purchase** – 商用ライセンスの購入は [https://purchase.aspose.com/buy](https://purchase.aspose.com/buy) から行えます。  
- **Support** – トラブルシューティングの支援はコミュニティフォーラム [https://forum.aspose.com/c/barcode/13](https://forum.aspose.com/c/barcode/13) に参加してください。

---

**最終更新日:** 2026-09-08  
**テスト環境:** Aspose.BarCode 24.11 for .NET  
**作者:** Aspose

## 関連チュートリアル

- [ITF-14 バーコードの作成方法 .NET – 包括的な Aspose.BarCode チュートリアル](/barcode/net/)
- [Aspose.BarCode .NET API を使用した 1 次元 Databar 2D バーコードの生成](/barcode/net/one-dimensional-barcode-types/one-dimensional-databar-2d-component-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}