---
category: general
date: 2026-09-26
description: C#でプラネットバーコードをすばやく作成する方法を学びましょう。このガイドでは、塗りつぶしあり・なしのプラネットバーコード、X寸法設定、画像エクスポートについて説明します。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create planet barcode
- Planet barcode C#
- filled planet barcode
- empty planet barcode
- barcode generator parameters
language: ja
lastmod: 2026-09-26
og_description: C#でプラネットバーコードを作成し、完全なコード例を提供します。塗りつぶしのあるプラネットバーコードと空のプラネットバーコードの両方を生成し、バー幅を設定してPNGとして保存します。
og_image_alt: Screenshot showing generated filled and empty planet barcode PNG files
og_title: C#で惑星バーコード画像を作成する – ステップバイステップガイド
schemas:
- author: Aspose
  dateModified: '2026-09-26'
  description: Learn how to create planet barcode in C# quickly. This guide covers
    filled and empty Planet barcodes, X‑dimension settings, and image export.
  headline: How to create planet barcode images in C# with BarcodeGenerator
  type: TechArticle
tags:
- barcode
- C#
- Aspose.BarCode
title: C# と BarcodeGenerator で惑星バーコード画像を作成する方法
url: /ja/python-java/general/how-to-create-planet-barcode-images-in-c-with-barcodegenerat/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# C# と BarcodeGenerator を使用してプラネットバーコード画像を作成する方法

.NET アプリケーションで **planet barcode** 画像を作成する必要がある場合、このチュートリアルでは正確な手順を示します。塗りつぶしの Planet バーコードと空の Planet バーコードの両方の生成方法、バー幅の調整、結果を PNG ファイルとしてエクスポートする方法を、Aspose.BarCode for .NET ライブラリですべて学べます。

**Planet barcode C#** ソリューションの生成は、主要な **barcode generator parameters** を理解すれば簡単です。以下のセクションでは、完全な実行可能コードを順に解説し、各設定が重要な理由を説明し、一般的な落とし穴を指摘して最初から回避できるようにします。

## 前提条件

* .NET 6.0 SDK またはそれ以降がインストールされていること。
* Visual Studio 2022（またはお好みの C# IDE）。
* **Aspose.BarCode for .NET** NuGet パッケージ（`Aspose.BarCode`）がプロジェクトに追加されていること。

パッケージは NuGet パッケージ マネージャ コンソールから追加できます：

```bash
dotnet add package Aspose.BarCode
```

## 手順 1: BarcodeGenerator の設定

`BarcodeGenerator` クラスはすべてのバーコード作成タスクのエントリーポイントです。2 つの引数が必要です：バーコードタイプ（`EncodeTypes.Planet`）とエンコードするデータです。

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class PlanetBarcodeDemo
{
    static void Main()
    {
        // Create a generator for a filled Planet barcode
        BarcodeGenerator filledPlanet = new BarcodeGenerator(EncodeTypes.Planet, "123456");
```

*この重要性:* `EncodeTypes.Planet` でジェネレータをインスタンス化すると、ライブラリは **Planet barcode** シンボルを使用するよう指示します。これは一部の国の郵便サービスで一般的に使用されています。文字列 `"123456"` はバーコードに表示されるペイロードです。

## 手順 2: X‑dimension（バー幅）の設定

X‑dimension は各バーの実際の幅を制御します。画面表示用の典型的な値は 4 ピクセルですが、印刷要件に合わせて調整できます。

```csharp
        // Define the bar width (X dimension) in pixels
        filledPlanet.Parameters.Barcode.XDimension.Pixels = 4;
```

*この重要性:* `XDimension.Pixels` を設定することで、生成されたバーコードが薄すぎて（スキャン失敗）または太すぎて（スペースの無駄）になるのを防ぎます。同じ設定は空のバーコードでも再利用されます。

## 手順 3: 塗りつぶし Planet バーコードの保存

`Save` メソッドを使用してバーコードを PNG ファイルとしてエクスポートします。`BarCodeImageFormat.Png` 列挙体は、ライブラリに対してさらに処理可能なロスレス画像を生成するよう指示します。

```csharp
        // Save the filled barcode as a PNG image
        filledPlanet.Save("PostalPlanetFilledBars.png", BarCodeImageFormat.Png);
```

プログラムを実行すると、出力フォルダーに `PostalPlanetFilledBars.png` が作成されます。開いてバーが実線（塗りつぶし）であることを確認してください。

## 手順 4: 空の Planet バーコード用ジェネレータの作成

**empty planet barcode** は同じデータを表示しますが、バーが未塗り（白）です。これは、カラー背景にバーコードをオーバーレイするデザインに便利です。

```csharp
        // Create a generator for an empty Planet barcode (unfilled bars)
        BarcodeGenerator emptyPlanet = new BarcodeGenerator(EncodeTypes.Planet, "123456");
```

コンストラクタ呼び出しは塗りつぶしバージョンと同一です。違いは次に変更するパラメータにあります。

## 手順 5: 同じ X‑dimension の再利用

視覚的なサイズを一致させるため、空のバーコードにも同じバー幅を適用します。

```csharp
        // Use the same bar width as before
        emptyPlanet.Parameters.Barcode.XDimension.Pixels = 4;
```

**barcode generator parameters** を再利用することで、2 つの画像を並べたときに完全に揃うことが保証されます。

## 手順 6: 未塗りバーへの切り替え

`FilledBars` フラグは、バーが実線の黒（デフォルト）で描画されるか、透明な白で描画されるかを決定します。

```csharp
        // Configure the generator to produce empty (unfilled) bars
        emptyPlanet.Parameters.Barcode.FilledBars = false;
```

*この重要性:* `FilledBars = false` を設定すると描画モードが反転し、塗りつぶし Planet バーコードと空の Planet バーコードの主な違いになります。

## 手順 7: 空の Planet バーコードの保存

最後に、空のバージョンを PNG としてエクスポートします。

```csharp
        // Save the empty barcode as a PNG image
        emptyPlanet.Save("PostalPlanetEmptyBars.png", BarCodeImageFormat.Png);
    }
}
```

プログラムを実行すると、2 つのファイルが生成されます：

* `PostalPlanetFilledBars.png` – 実線の黒バー。
* `PostalPlanetEmptyBars.png` – 透明（未塗り）バー。

両方の画像は同じデータ（`123456`）を含み、同じ X‑dimension を共有するため、ほとんどの UI シナリオで相互に置き換え可能です。

## 完全な実行可能サンプル

すべてをまとめると、以下が新しいコンソール プロジェクトにコピー＆ペーストできる完全なソース ファイルです：

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class PlanetBarcodeDemo
{
    static void Main()
    {
        // ----------- Filled Planet barcode -----------
        BarcodeGenerator filledPlanet = new BarcodeGenerator(EncodeTypes.Planet, "123456");
        filledPlanet.Parameters.Barcode.XDimension.Pixels = 4;
        filledPlanet.Save("PostalPlanetFilledBars.png", BarCodeImageFormat.Png);

        // ----------- Empty Planet barcode ------------
        BarcodeGenerator emptyPlanet = new BarcodeGenerator(EncodeTypes.Planet, "123456");
        emptyPlanet.Parameters.Barcode.XDimension.Pixels = 4;
        emptyPlanet.Parameters.Barcode.FilledBars = false;
        emptyPlanet.Save("PostalPlanetEmptyBars.png", BarCodeImageFormat.Png);
    }
}
```

**期待される出力**

プログラムを実行すると、実行ファイルの作業ディレクトリに 2 つの PNG ファイルが作成されます。任意の画像ビューアで開いてください：

* **Filled version** – 暗く実線のバーで、標準スキャナで容易に読み取れます。
* **Empty version** – 黒い背景に白い隙間としてバーが表示され、オーバーレイ効果に便利です。

## よくある落とし穴とプロのコツ

| 問題 | 発生原因 | 対策 |
|-------|----------------|---------------|
| バーが細すぎる | X‑dimension がデフォルト（1 ピクセル）のまま | `XDimension.Pixels` を画面表示用に 3‑5 ピクセルに設定し、高解像度印刷の場合はさらに増やしてください。 |
| 空のバーコードが完全に黒く表示される | `FilledBars` が `false` に設定されていない | `emptyPlanet.Parameters.Barcode.FilledBars = false;` が X‑dimension 設定 **後**に実行されていることを確認してください。 |
| PNG ファイルが見つからない | 出力パスが間違っている、またはディレクトリが存在しない | フルパス（`@"C:\Barcodes\PostalPlanetFilledBars.png"`）を指定するか、事前に `Directory.CreateDirectory` でディレクトリを作成してください。 |
| バーコードがスキャンできない | データ文字列に Planet シンボロジーで使用できない文字が含まれている | Planet バーコードは数値ペイロードのみ受け付けるため、`int.TryParse` で入力を検証してください。 |

**Pro tip:** バーコードを PDF に埋め込む必要がある場合、生成した PNG を Aspose.PDF の `PdfDocument` にロードするか、ディスクに書き込まずに画像ストリームとして直接バーコードを追加できます。

## 次のステップ

これで **planet barcode** 画像を作成できるようになったので、以下の関連トピックを検討してください：

* **Planet barcode C#** – 色のカスタマイズ、ヒューマンリーダブルテキストの追加、または PDF への埋め込み。
* **Barcode generator parameters** – 誤り訂正レベル、クワイエットゾーン、回転の調整。
* **Batch generation** – 郵便番号のリストをループして PNG の zip ファイルを生成。
* **Alternative formats** – Web 向けに SVG や JPEG へエクスポート。

さまざまな `XDimension` の値と `FilledBars` フラグを試して、スキャン信頼性とビジュアルスタイルへの影響を確認してください。準備ができたら、生成コードを Web API やデスクトップ アプリケーションに統合し、郵便バーコードの自動生成をリアルタイムで実装しましょう。

---

## 次に学ぶべきことは？

以下のチュートリアルは、本ガイドで示した手法を基にした密接に関連するトピックを扱っています。各リソースには、ステップバイステップの解説付きの完全な動作コード例が含まれており、追加の API 機能を習得し、独自プロジェクトで代替実装アプローチを検討するのに役立ちます。

- [Create Planet Barcode in C# – Full Step‑by‑Step Guide](/barcode/english/python-java/general/create-planet-barcode-in-c-full-step-by-step-guide/)
- [Barcode generator C# – create Planet barcode and RM4SCC example](/barcode/english/python-java/general/barcode-generator-c-create-planet-barcode-and-rm4scc-example/)
- [Generate Postal Barcode in C# – Complete Guide with Planet Barcode](/barcode/english/python-java/general/generate-postal-barcode-in-c-complete-guide-with-planet-barc/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}