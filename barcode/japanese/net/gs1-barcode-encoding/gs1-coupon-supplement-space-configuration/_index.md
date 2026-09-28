---
date: 2026-09-28
description: Aspose.BarCode for .NET を使用して、GS1 クーポンのバーコードカスタムスペースの作成方法を学び、バーコードの読み取り精度を向上させましょう。ステップバイステップのガイドに従ってください。
keywords:
- create barcode custom space
- GS1 coupon supplement
- Aspose.BarCode .NET
- increase barcode readability
lastmod: 2026-09-28
linktitle: GS1 クーポン補足スペース構成
og_description: Aspose.BarCode for .NET を使用して、GS1 クーポンのバーコードカスタムスペースの作成方法とバーコードの読み取り精度向上を学びます。ステップバイステップのコードとヒントが含まれています。
og_image_alt: Screenshot of a GS1 coupon barcode generated with custom supplement
  space using Aspose.BarCode for .NET
og_title: GS1 クーポン補足用バーコードカスタムスペースの作成 – Aspose.BarCode .NET
schemas:
- author: Aspose
  dateModified: '2026-09-28'
  description: Learn how to create barcode custom space for GS1 coupons with Aspose.BarCode
    for .NET and increase barcode readability. Follow our step‑by‑step guide.
  headline: How to create barcode custom space for GS1 coupon supplement
  type: TechArticle
- description: Learn how to create barcode custom space for GS1 coupons with Aspose.BarCode
    for .NET and increase barcode readability. Follow our step‑by‑step guide.
  name: How to create barcode custom space for GS1 coupon supplement
  steps:
  - name: '**Visual Studio** – The primary IDE for .NET development.'
    text: '**Visual Studio** – The primary IDE for .NET development.'
  - name: '**Aspose.BarCode for .NET** – Download the library from the [Aspose.BarCode
      for .NET documentation](https://reference.aspose.com/barcode/net/).'
    text: '**Aspose.BarCode for .NET** – Download the library from the [Aspose.BarCode
      for .NET documentation](https://reference.aspose.com/barcode/net/).'
  - name: '**.NET Framework or .NET 5+** – Familiarity with C# and the .NET runtime
      is required.'
    text: '**.NET Framework or .NET 5+** – Familiarity with C# and the .NET runtime
      is required.'
  - name: '**Create** a `BarcodeGenerator` instance for the `UpcaGs1DatabarCoupon`
      type.'
    text: '**Create** a `BarcodeGenerator` instance for the `UpcaGs1DatabarCoupon`
      type.'
  - name: '**Set** the X‑dimension to 2 pixels, which determines the narrowest bar
      width.'
    text: '**Set** the X‑dimension to 2 pixels, which determines the narrowest bar
      width.'
  - name: '**Adjust** the `SupplementSpace.Pixels` property to 30 px, generate an
      image, then repeat with 50 px.'
    text: '**Adjust** the `SupplementSpace.Pixels` property to 30 px, generate an
      image, then repeat with 50 px.'
  type: HowTo
- questions:
  - answer: It adds a mandatory blank margin around the supplemental data, improving
      scanner reliability and meeting retailer‑specified minimum widths.
    question: What is the purpose of the GS1 Coupon Supplement Space in barcodes?
  - answer: Yes, set `gen.Parameters.Barcode.Coupon.SupplementSpace.Pixels` to any
      integer value; the library instantly applies the change to the generated image.
    question: Can I customize the width of the GS1 Coupon Supplement Space with Aspose.BarCode
      for .NET?
  - answer: Refer to the [Aspose.BarCode for .NET documentation](https://reference.aspose.com/barcode/net/)
      and visit the [Aspose.BarCode forum](https://forum.aspose.com/c/barcode/13)
      for community assistance.
    question: Where can I find additional documentation and support for Aspose.BarCode
      for .NET?
  - answer: Absolutely. The API offers straightforward methods for quick tasks and
      advanced options for fine‑tuned barcode generation.
    question: Is Aspose.BarCode for .NET suitable for both beginners and experienced
      developers?
  - answer: Yes, request a trial license from the [Aspose temporary license website](https://purchase.aspose.com/temporary-license/).
    question: Can I obtain a temporary license for Aspose.BarCode for .NET to evaluate
      its features?
  type: FAQPage
second_title: Aspose.BarCode .NET API
tags:
- barcode configuration
- GS1 standards
- Aspose.BarCode
- .NET barcode generation
title: GS1 クーポン補足用のバーコードカスタムスペースの作成方法
url: /ja/net/gs1-barcode-encoding/gs1-coupon-supplement-space-configuration/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# GS1 クーポン補足スペース構成

このチュートリアルでは、Aspose.BarCode for .NET を使用して GS1 クーポン補足スペースの **バーコードカスタムスペース** を作成します。補足スペースの調整は、低解像度スキャナーで **バーコードの読み取り易さを向上** させる必要がある場合や、小売業者が指定する余白に準拠する際に不可欠です。このガイドの最後までに、補足スペースが重要な理由、プログラムでの設定方法、異なるピクセル値で画像を生成する方法が理解できるようになります。

## クイック回答

- **補足スペースは何を制御しますか？** クーポンデータとバーコードの残り部分との間の空白領域（ピクセル単位）を定義します。  
- **使用されるバーコードタイプは何ですか？** `EncodeTypes.UpcaGs1DatabarCoupon`.  
- **スペースサイズを変更できますか？** はい – `gen.Parameters.Barcode.Coupon.SupplementSpace.Pixels` を任意の整数値に設定してください。  
- **この機能にライセンスは必要ですか？** 評価用の一時ライセンスで動作しますが、本番環境ではフルライセンスが必要です。  
- **サポートされている出力形式は何ですか？** PNG、JPEG、BMP、GIF、TIFF など、`BarCodeImageFormat` を介して利用可能です。

## GS1 クーポン補足スペースとは？

GS1 クーポン補足スペースは、GS1‑Databar クーポンバーコードに表示される定義された空白領域です。小売システムはこのスペースを使用してスキャンの信頼性を向上させ、補足データの周囲に最低限の余白を要求する業界仕様に準拠します。

## なぜ補足スペースを設定するのか？

補足スペースは直接 **バーコードの読み取り易さを向上** させ、厳格な小売業者ガイドラインを満たすのに役立ちます。余分なピクセルを追加することで、低解像度スキャナーでの誤読の可能性を減らし、さまざまなラベルサイズでのスキャンの一貫性を確保し、印刷レイアウト内でバーコードのバランスを取る視覚的柔軟性を提供します。

## 前提条件

Aspose.BarCode for .NET を使用して GS1 クーポン補足スペースを設定する前に、以下が揃っていることを確認してください。

1. **Visual Studio** – .NET 開発の主要 IDE。  
2. **Aspose.BarCode for .NET** – ライブラリは [Aspose.BarCode for .NET documentation](https://reference.aspose.com/barcode/net/) からダウンロードしてください。  
3. **.NET Framework or .NET 5+** – C# と .NET ランタイムの知識が必要です。

環境が整ったので、実装に進みましょう。

## 名前空間のインポート

`Aspose.BarCode.Generation` 名前空間には `BarcodeGenerator` クラスと関連設定が含まれています。

```csharp
using Aspose.BarCode;
```

## 手順 1: パスの定義

生成された画像を保存するフォルダーを選択してください。パスは使用している OS に適したディレクトリ区切り文字で終わっている必要があります。

```csharp
string path = "Your Directory Path";
```

## 手順 2: GS1 クーポン補足スペース構成の生成

以下のスニペットはバーコードを作成し、X‑ディメンションを設定し、補足スペースを調整します。

```csharp
System.Console.WriteLine("Gs1CouponSupplementSpace:");

BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.UpcaGs1DatabarCoupon, "123456789012(8110)ASPOSE");
gen.Parameters.Barcode.XDimension.Pixels = 2;

// Set coupon supplement space to 30 pixels
gen.Parameters.Barcode.Coupon.SupplementSpace.Pixels = 30;
gen.Save($"{path}Gs1CouponSpace30Pixels.png", BarCodeImageFormat.Png);

// Set coupon supplement space to 50 pixels
gen.Parameters.Barcode.Coupon.SupplementSpace.Pixels = 50;
gen.Save($"{path}Gs1CouponSpace50Pixels.png", BarCodeImageFormat.Png);
```

この例では、次のことを行います：

1. **作成** `UpcaGs1DatabarCoupon` タイプの `BarcodeGenerator` インスタンスを作成します。  
2. **設定** X‑ディメンションを 2 ピクセルに設定します。これにより最も狭いバー幅が決まります。  
3. **調整** `SupplementSpace.Pixels` プロパティを 30 px に設定し、画像を生成し、次に 50 px で繰り返します。  

印刷ワークフローに合わせて、他のピクセル値でも自由に試してみてください。

## よくある問題とヒント

- **Invalid path** – `path` 変数が OS に適した末尾のバックスラッシュ (`\`) またはスラッシュ (`/`) で終わっていることを確認してください。  
- **Insufficient permissions** – Visual Studio を管理者として実行するか、アプリケーションに書き込み権限があるフォルダーを選択してください。  
- **Incorrect data format** – データ文字列は GS1 構文に従う必要があります（`(8110)` は補足識別子を示します）。

## なぜこれがビジネスに重要なのか

Aspose.BarCode は **60 種類以上のバーコードシンボル** をサポートし、メモリを使い切ることなく **10,000 × 10,000 ピクセル** までの画像をレンダリングできます。大規模な小売展開において、これは典型的なサーバーハードウェア上で画像あたり 1 秒未満の処理時間でバッチモードで高解像度の GS1 クーポンを生成できることを意味します。

## よくある質問

**Q: GS1 クーポン補足スペースの目的は何ですか？**  
A: 補足データの周囲に必須の空白余白を追加し、スキャナーの信頼性を向上させ、小売業者が指定する最小幅を満たします。

**Q: Aspose.BarCode for .NET で GS1 クーポン補足スペースの幅をカスタマイズできますか？**  
A: はい、`gen.Parameters.Barcode.Coupon.SupplementSpace.Pixels` を任意の整数値に設定すれば、ライブラリは生成された画像に即座に変更を適用します。

**Q: Aspose.BarCode for .NET の追加ドキュメントやサポートはどこで見つけられますか？**  
A: [Aspose.BarCode for .NET documentation](https://reference.aspose.com/barcode/net/) を参照し、コミュニティ支援のために [Aspose.BarCode forum](https://forum.aspose.com/c/barcode/13) を訪れてください。

**Q: Aspose.BarCode for .NET は初心者と経験豊富な開発者の両方に適していますか？**  
A: はい、間違いなく適しています。API は迅速なタスク向けのシンプルなメソッドと、細かく調整されたバーコード生成のための高度なオプションを提供します。

**Q: Aspose.BarCode for .NET の機能を評価するために一時ライセンスを取得できますか？**  
A: はい、[Aspose temporary license website](https://purchase.aspose.com/temporary-license/) からトライアルライセンスをリクエストしてください。

## 結論

上記の手順に従うことで、GS1 クーポン補足スペースの **バーコードカスタムスペースの作成** 方法が分かり、**バーコードの読み取り易さを向上** させ小売基準を満たす重要なテクニックを習得しました。コードを既存のスキャンソリューションに組み込み、さまざまなピクセル値で実験し、Aspose.BarCode for .NET が提供する他のバーコードタイプも探求してください。

---

**最終更新:** 2026-09-28  
**テスト済み:** Aspose.BarCode 24.12 for .NET  
**作者:** Aspose

## 関連チュートリアル

- [.NET API を使用した Aspose.BarCode Databar バーコードの生成 – 行と列の構成](/barcode/net/one-dimensional-barcode-types/one-dimensional-databar-row-column-configuration/)
- [Aspose.BarCode for .NET を使用した DataMatrix バーコードの生成方法 – ステップバイステップガイド](/barcode/net/datamatrix-barcode-configuration/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}