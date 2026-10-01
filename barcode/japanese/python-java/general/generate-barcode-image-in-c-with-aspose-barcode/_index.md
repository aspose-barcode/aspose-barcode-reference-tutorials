---
category: general
date: 2026-08-06
description: Aspose.BarCode を使用して C# でバーコード画像を生成します。Databar の生成方法、カスタムバーコードサイズの調整、バーコードの高さ変更をシンプルなコードで学びましょう。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate barcode image
- how to generate databar
- custom barcode size
- create databar barcode
- change barcode height
language: ja
lastmod: 2026-08-06
og_description: Aspose.BarCode を使用して C# でバーコード画像を生成します。このチュートリアルでは、Databar Omnidirectional
  バーコードの作成方法、サイズのカスタマイズ、そしてバーコードの高さを効率的に変更する方法を示します。
og_image_alt: Screenshot of a Databar barcode generated with custom height in C#
og_title: C#でバーコード画像を生成する – 完全なAspose.BarCodeガイド
schemas:
- author: Aspose
  dateModified: '2026-08-06'
  description: Generate barcode image in C# using Aspose.BarCode. Learn how to generate
    Databar, adjust custom barcode size, and change barcode height with simple code.
  headline: Generate barcode image in C# with Aspose.BarCode
  type: TechArticle
- questions:
  - answer: The evaluation version of Aspose.BarCode works without a license but adds
      a small watermark. For production use, apply a purchased license using `License
      license = new License(); license.SetLicense("Aspose.BarCode.lic");`.
    question: Can I generate a barcode without installing a license?
  - answer: Yes. Very small X‑dimensions can make the barcode unreadable on low‑resolution
      printers. A minimum of 1 px for screen rendering is recommended; for print,
      use at least 0.25 mm.
    question: Does changing the X‑dimension affect readability?
  - answer: 'Replace `BarCodeImageFormat.Png` with `BarCodeImageFormat.Jpeg`. You
      may also set `generator.Parameters.ImageQuality` to control compression. ##
      Conclusion You now know how to **generate barcode image** in C# using Aspose.BarCode,
      how to **create Databar barcode**, adjust a **custom barcode size**, '
    question: What if I need to generate a barcode in JPEG format?
  type: FAQPage
tags:
- barcode
- C#
- Aspose.BarCode
title: Aspose.BarCode を使用して C# でバーコード画像を生成する
url: /ja/python-java/general/generate-barcode-image-in-c-with-aspose-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# C# で Aspose.BarCode を使用してバーコード画像を生成する

プログラムで **バーコード画像を生成** する必要がある場合、本ガイドで具体的な手順を示します。小売在庫システムや物流トラッキングポータルを構築している場合でも、Databar Omnidirectional バーコードの作成、サイズ調整、PNG ファイルとして保存するまでの完全なワークフローが確認できます。

バーコード画像の生成は一般的な要件ですが、開発者はしばしば **Databar を正確なサイズで生成する方法** に悩みます。このチュートリアルでは、Databar バーコードを作成し、幅と高さをカスタマイズし、ジェネレータ全体を書き直すことなくバーコードの高さを変更する方法を学びます。

## 前提条件

開始する前に、以下が揃っていることを確認してください。

* .NET 6.0 SDK 以降（コードは .NET Core と .NET Framework でも動作します）
* Visual Studio 2022（または C# をサポートする任意の IDE）
* 有効な Aspose.BarCode for .NET ライセンス（評価版でもテストは可能です）
* C# 文法に関する基本的な知識

## ステップ 1: Aspose.BarCode のインストール

プロジェクトに Aspose.BarCode NuGet パッケージを追加します。

```bash
dotnet add package Aspose.BarCode
```

このパッケージには、本チュートリアル全体で使用する `BarcodeGenerator` クラスが含まれています。インストール後、プロジェクトを復元して依存関係を取得してください。

## ステップ 2: 基本的なバーコードジェネレータを作成

最初のコード行は、Databar Omnidirectional シンボルを生成する **バーコードジェネレータ** を作成します。`EncodeTypes.DatabarOmniDirectional` 列挙体は使用するシンボロジーを指定し、データ文字列は GS1 アプリケーション識別子構文に従います。

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        // Step 2: Initialize the generator for a Databar Omnidirectional barcode
        BarcodeGenerator generator = new BarcodeGenerator(
            EncodeTypes.DatabarOmniDirectional,
            "(01)12345678901231"); // GS1-14 data (example GTIN)
```

**重要ポイント:** `BarcodeGenerator` オブジェクトはすべてのバーコード操作のエントリーポイントです。`DatabarOmniDirectional` を選択することで、出力が小売スキャン用の GS1 標準に準拠することが保証されます。

## ステップ 3: カスタム X‑dimension（モジュール幅）を設定

X‑dimension は最細バーの幅を制御します。小さなピクセル値に設定するとコンパクトなバーコードになり、値を大きくすると全体幅が広がります。

```csharp
        // Step 3: Define a custom X‑dimension (module width) of 2 px
        generator.Parameters.Barcode.XDimension.Pixels = 2;
```

**解説:** 2 ピクセルの X‑dimension は高解像度画面で一般的に使用される選択肢です。視覚的密度をよりタイトまたはルーズにしたい場合は、この値を調整してください。

## ステップ 4: 特定の高さで最初のバーコード画像を生成

バーコードの高さは X‑dimension とは独立しています。ここではバーの高さを **30 px** に設定し、PNG として保存します。

```csharp
        // Step 4: Set bar height to 30 px and save the image
        generator.Parameters.Barcode.BarHeight.Pixels = 30;
        generator.Save("DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);
```

**結果:** `DatabarBarHeight30Pixels.png` というファイルが生成され、30 px の高さの Databar バーコードが確認できます。これは小さなラベル向けに **カスタムバーコードサイズ** を実現する例です。

## ステップ 5: より大きなバージョン用にバーコード高さを変更

同じバーコードを大きなラベルに表示する必要がある場合、プロパティの高さだけを変更し、同じジェネレータインスタンスを再利用すれば完了です。

```csharp
        // Step 5: Increase the bar height to 60 px for a larger barcode
        generator.Parameters.Barcode.BarHeight.Pixels = 60;
        generator.Save("DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);
    }
}
```

**再利用できる理由:** `BarHeight.Pixels` を変更すると、内部レイアウトが更新されオブジェクトの再生成が不要になるため、メモリ節約とデータ文字列の保持が実現します。これは **バーコード高さを動的に変更** する推奨手法です。

## ステップ 6: 出力を確認

任意の画像ビューアで 2 つの PNG ファイルを開きます。同一の GTIN をエンコードしつつ、垂直サイズが異なる Databar Omnidirectional バーコードが表示されます。

* `DatabarBarHeight30Pixels.png` – 30 px の高さ、コンパクトなレシート向け
* `DatabarBarHeight60Pixels.png` – 60 px の高さ、棚エッジラベル向け

両画像は同じ X‑dimension を保持しているため、バーとスペースの比率は一定で、全体の高さだけがスケールしています。

## 一般的なバリエーションとエッジケース

| 状況 | 対処方法 |
|-----------|------------------|
| **異なるバーコードシンボロジー** | `EncodeTypes.DatabarOmniDirectional` を別の列挙値（例: `EncodeTypes.Code128`）に置き換えます。残りのコードは変更不要です。 |
| **ピクセル以外の単位** | 印刷用に実寸を指定したい場合は、`generator.Parameters.Barcode.XDimension.Millimeters` や `BarHeight.Millimeters` を使用します。 |
| **透明背景** | `Save` 呼び出し前に `generator.Parameters.ImageBackgroundColor = Color.Transparent;` を設定します。 |
| **高解像度出力** | `XDimension.Pixels` と `BarHeight.Pixels` を比例的に増やすか、ロスレス品質のために `BarCodeImageFormat.Tiff` で保存します。 |
| **1 画像に複数バーコード** | 個別の `BarcodeGenerator` インスタンスを作成し、各々を `Bitmap` に描画した後、`Graphics.DrawImage` で合成します。 |

**プロのコツ:** 本番環境に導入する前に、実際のスキャナで必ず生成バーコードをテストしてください。薄いバーは照明やセンサー品質により読み取りが変わることがあります。

## 参考用フルソースコード

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // Initialize the generator for a Databar Omnidirectional barcode
            BarcodeGenerator generator = new BarcodeGenerator(
                EncodeTypes.DatabarOmniDirectional,
                "(01)12345678901231"); // Example GTIN

            // Custom X‑dimension (module width) – 2 px
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // First image: 30 px height
            generator.Parameters.Barcode.BarHeight.Pixels = 30;
            generator.Save("DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);

            // Second image: 60 px height (larger barcode)
            generator.Parameters.Barcode.BarHeight.Pixels = 60;
            generator.Save("DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);

            Console.WriteLine("Barcode images generated successfully.");
        }
    }
}
```

コードを新しいコンソールプロジェクトに貼り付け、実行すると出力フォルダに 2 つの PNG ファイルが生成されます。

## よくある質問

**Q: ライセンスをインストールせずにバーコードを生成できますか？**  
A: 評価版 Aspose.BarCode はライセンスなしで動作しますが、画像に小さな透かしが入ります。本番利用の場合は `License license = new License(); license.SetLicense("Aspose.BarCode.lic");` のように購入したライセンスを適用してください。

**Q: X‑dimension を変更すると可読性に影響しますか？**  
A: はい。非常に小さい X‑dimension は低解像度プリンタでの読み取りが困難になることがあります。画面表示の場合は最小 1 px、印刷の場合は少なくとも 0.25 mm を推奨します。

**Q: JPEG 形式でバーコードを生成したい場合は？**  
A: `BarCodeImageFormat.Png` を `BarCodeImageFormat.Jpeg` に置き換えます。また、`generator.Parameters.ImageQuality` で圧縮率を調整できます。

## 結論

これで C# と Aspose.BarCode を使用して **バーコード画像を生成** する方法、**Databar バーコードの作成**、**カスタムバーコードサイズの調整**、そして **オンデマンドでバーコード高さを変更** する手順が習得できました。完全なサンプルは最も一般的なワークフローを示しており、表にあるバリエーションは実務でのエッジケースに対応できるようにしています。

次は **PDF 文書へのバーコード埋め込み**、**複数バーコードのバッチ生成**、**モバイル決済向け QR コードの活用** などの関連トピックを探求してください。これらのシナリオは本ガイドで学んだ原則に基づいているため、自信を持って応用できます。

Happy coding, and may your barcodes scan flawlessly!

## 次に学ぶべきこと

以下のチュートリアルは、本ガイドで示したテクニックを基にした、密接に関連するトピックを扱っています。各リソースには、ステップバイステップの解説と完全なコード例が含まれており、API の追加機能をマスターし、プロジェクトで代替実装アプローチを探求するのに役立ちます。

- [Generate barcode image – GS1 Coupon UPC-A Databar](/barcode/english/net/gs1-barcode-encoding/gs1-coupon-upc-a-databar-configuration/)
- [How to generate Aztec barcode with custom aspect ratio using Aspose.BarCode for .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)
- [How to Generate Barcode – Code 39 Configuration with Aspose.BarCode](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-code-39-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}