---
category: general
date: 2026-09-29
description: Aspose.BarCode を使用して C# で全方向型 Databar バーコードの作成方法を学びましょう。X 次元を調整し、アスペクト比を設定して
  PNG 画像として保存します。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create omnidirectional databar barcode
- DataBar stacked omnidirectional barcode
- set barcode aspect ratio
- Aspose.BarCode C#
- generate barcode image
language: ja
lastmod: 2026-09-29
og_description: Aspose.BarCode を使用して C# で全方向型 Databar バーコードを作成します。X ディメンションの設定、アスペクト比の調整、PNG
  ファイルへのエクスポート方法を学びましょう。
og_image_alt: Screenshot showing two PNG files of an omnidirectional Databar barcode
  with different aspect ratios
og_title: C#で全方向対応Databarバーコードを作成する – ステップバイステップガイド
schemas:
- author: Aspose
  dateModified: '2026-09-29'
  description: Learn how to create omnidirectional Databar barcode in C# with Aspose.BarCode.
    Adjust X‑dimension, set aspect ratio, and save PNG images.
  headline: How to create omnidirectional Databar barcode in C#
  type: TechArticle
- description: Learn how to create omnidirectional Databar barcode in C# with Aspose.BarCode.
    Adjust X‑dimension, set aspect ratio, and save PNG images.
  name: How to create omnidirectional Databar barcode in C#
  steps:
  - name: What if I need a different X‑dimension?
    text: You can assign any integer value to `XDimension.Pixels`. Values below `1`
      are ignored, and values above `10` may produce oversized modules that exceed
      printer margins. Test the visual output after each change.
  - name: How do I encode other AI‑generated data (e.g., UPC, EAN)?
    text: Replace the data string in the `BarcodeGenerator` constructor with the appropriate
      Application Identifier (AI). For a UPC‑A code, use `"012345678905"` without
      an AI prefix.
  - name: Can I export to formats other than PNG?
    text: Yes. The `Save` method accepts `BarCodeImageFormat.Jpeg`, `BarCodeImageFormat.Gif`,
      `BarCodeImageFormat.Tiff`, and `BarCodeImageFormat.Bmp`. Choose the format that
      matches your downstream workflow.
  type: HowTo
tags:
- barcode
- C#
- Aspose
title: C#で全方向性Databarバーコードを作成する方法
url: /ja/python-java/general/how-to-create-omnidirectional-databar-barcode-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# C# で全方向性 Databar バーコードを作成する方法

.NET アプリケーションで **全方向性 Databar バーコードを作成** する必要がある場合、このガイドでは正確な手順を示します。DataBar stacked omnidirectional バーコードの初期化方法、X‑dimension の設定、アスペクト比の変更、そして Aspose.BarCode を使用した PNG 画像の生成方法が分かります。

**DataBar stacked omnidirectional barcode** の生成は、小売スキャナ用に製品識別子をエンコードする必要がある場合に一般的です。このチュートリアルでは **set barcode aspect ratio** を設定し、モジュールサイズを制御し、IDE を離れずに結果をエクスポートする方法を学びます。

## 前提条件

- .NET 6.0 以降がインストールされていること
- Visual Studio 2022（または任意の C# 対応 IDE）
- **Aspose.BarCode for .NET** NuGet パッケージ（バージョン 23.12 以降）

NuGet パッケージ マネージャーからパッケージを追加できます：

```bash
dotnet add package Aspose.BarCode
```

## ステップ 1: 全方向性 Databar バーコードを初期化する

最初のステップは、**DataBar stacked omnidirectional** シンボルを対象とする `BarcodeGenerator` インスタンスを作成することです。コンストラクタはエンコードタイプとデータ文字列を受け取ります。

```csharp
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Initialise a DataBar stacked omnidirectional barcode with GTIN data
        var generator = new BarcodeGenerator(
            EncodeTypes.DatabarStackedOmniDirectional,
            "(01)12345678901231");
```

**Why this matters:** `EncodeTypes.DatabarStackedOmniDirectional` の値は、Aspose.BarCode に特定の全方向性 Databar フォーマットを描画させるもので、両方向のスキャンに必要です。

## ステップ 2: X‑dimension（モジュールサイズ）を定義する

X‑dimension は、1 つのバーコードモジュールの幅（ピクセル）を制御します。`2` ピクセルの値は、画面表示やほとんどのプリンターでうまく機能します。

```csharp
        // Set the basic size of the barcode modules (X‑dimension) in pixels
        generator.Parameters.Barcode.XDimension.Pixels = 2;
```

**Why this matters:** 一貫した X‑dimension により、バーコードが小売スキャナの最小サイズ要件を満たしつつ、画像ファイルサイズを適切に保つことができます。

## ステップ 3: 最初のアスペクト比を設定し、画像を保存する

**aspect ratio** は DataBar の高さと幅の比率を決定します。`15` のアスペクト比は、狭いラベルスペースに最適なコンパクトで縦長のバーコードを生成します。

```csharp
        // Apply aspect ratio 15 and save the first PNG
        generator.Parameters.Barcode.DataBar.AspectRatio = 15;
        generator.Save("DatabarAspectRatio15.png", BarCodeImageFormat.Png);
```

**Why this matters:** アスペクト比を調整することで、可読性を損なうことなくさまざまなラベルレイアウトにバーコードを合わせることができます。保存された PNG は任意の画像ビューアで確認できます。

## ステップ 4: アスペクト比を変更し、2 番目の画像を生成する

場合によっては、ラベルに横方向の余裕があるため、より横長のバーコードが必要になることがあります。比率を `30` に変更すると、より平坦な外観になります。

```csharp
        // Change aspect ratio to 30 and save a second PNG
        generator.Parameters.Barcode.DataBar.AspectRatio = 30;
        generator.Save("DatabarAspectRatio30.png", BarCodeImageFormat.Png);
    }
}
```

**Why this matters:** **set barcode aspect ratio** プロパティを公開することで、単一のコードベースから複数のバーコードバリエーションを生成でき、ラベル自動生成パイプラインを簡素化できます。

## 期待される出力

プログラムを実行すると、アプリケーションの出力フォルダーに 2 つの PNG ファイルが生成されます：

| ファイル名                | アスペクト比 | ビジュアル説明 |
|--------------------------|--------------|--------------------|
| `DatabarAspectRatio15.png` | 15           | 縦長で狭いラベルに適したバーコード |
| `DatabarAspectRatio30.png` | 30           | 横幅が広く、より多くの横方向スペースを埋めるバーコード |

これらの画像はレポートに埋め込んだり、製品パッケージに印刷したり、さらなる処理のために Web サービスへ送信したりできます。

![全方向性 Databar バーコード作成例](databar-example.png "全方向性 Databar バーコード作成例")

*このスクリーンショットは、生成された 2 つの PNG ファイルが横に並んでいる様子を示しています。*

## よくある質問とエッジケース

### 異なる X‑dimension が必要な場合は？

`XDimension.Pixels` には任意の整数値を割り当てられます。`1` 未満の値は無視され、`10` を超える値はプリンタの余白を超える過大なモジュールを生成する可能性があります。変更のたびにビジュアル出力をテストしてください。

### 他の AI 生成データ（例: UPC、EAN）をエンコードするには？

`BarcodeGenerator` コンストラクタのデータ文字列を、適切な Application Identifier (AI) に置き換えてください。UPC‑A コードの場合は、AI プレフィックスなしで `"012345678905"` を使用します。

### PNG 以外の形式にエクスポートできますか？

はい。`Save` メソッドは `BarCodeImageFormat.Jpeg`、`BarCodeImageFormat.Gif`、`BarCodeImageFormat.Tiff`、`BarCodeImageFormat.Bmp` を受け付けます。下流のワークフローに合った形式を選択してください。

## プロのコツ: バッチ処理のためにジェネレータを再利用する

さまざまなアスペクト比で数十個のバーコードを生成する必要がある場合、`BarcodeGenerator` インスタンスを保持し、各 `Save` の前に `DataBar.AspectRatio` だけを変更します。これにより、画像ごとにジェネレータを再インスタンス化するオーバーヘッドが回避できます。

```csharp
var ratios = new[] { 10, 15, 20, 30 };
foreach (var ratio in ratios)
{
    generator.Parameters.Barcode.DataBar.AspectRatio = ratio;
    generator.Save($"DatabarAspectRatio{ratio}.png", BarCodeImageFormat.Png);
}
```

## 結論

これで、Aspose.BarCode を使用して C# で **全方向性 Databar バーコードを作成** する方法がわかりました。`BarcodeGenerator` を初期化し、X‑dimension を設定し、**set barcode aspect ratio** を調整して PNG ファイルを保存することで、さまざまなラベル要件を満たすバーコード画像を生成できます。  

次に、QR コード用の **generate barcode image**、**DataBar stacked omnidirectional barcode** の検証、または生成した PNG を Aspose.PDF を使用して PDF 請求書に統合するなど、関連トピックを探求してください。異なるアスペクト比やモジュールサイズを試して、特定の印刷ハードウェアに最適な構成を見つけてください。

---

## 次に学ぶべきことは？

以下のチュートリアルは、本ガイドで示した手法を基にした密接に関連するトピックを取り上げています。各リソースには、ステップバイステップの解説と完全な動作コード例が含まれており、追加の API 機能を習得し、プロジェクトで代替実装アプローチを検討するのに役立ちます。

- [C# のバーコードジェネレータを使用して DataBar Omni‑directional バーコードを作成する方法](/barcode/english/python-java/general/how-to-use-a-barcode-generator-c-to-create-databar-omni-dire/)
- [C# における databar stacked omnidirectional バーコード – 完全ガイド](/barcode/english/python-java/general/databar-stacked-omnidirectional-barcode-in-c-complete-guide/)
- [C# でバーコードを生成する方法 – DataBar Expanded でバーコード画像を作成する](/barcode/english/python-java/general/how-to-generate-barcode-in-c-create-barcode-image-c-with-dat/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}