---
category: general
date: 2026-07-27
description: 惑星バーコード画像をすばやく作成。C#で惑星バーコードを生成し、塗りつぶしバーと空白バーをカスタマイズする方法を学びましょう。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create planet barcode image
- how to generate planet barcode
- planet barcode C#
- barcode X‑dimension
- filled vs empty bars
language: ja
lastmod: 2026-07-27
og_description: 数秒で惑星バーコード画像を作成。ガイドに従って惑星バーコードの生成方法、X軸の調整、塗りつぶしバーと空白バーの切り替えを学びましょう。
og_image_alt: Screenshot showing a create planet barcode image with filled bars
og_title: 惑星バーコード画像を作成 – 完全C#チュートリアル
schemas:
- author: Aspose
  dateModified: '2026-07-27'
  description: create planet barcode image quickly. Learn how to generate planet barcode
    with C# and customize filled or empty bars.
  headline: create planet barcode image – Step‑by‑Step Guide
  type: TechArticle
- description: create planet barcode image quickly. Learn how to generate planet barcode
    with C# and customize filled or empty bars.
  name: create planet barcode image – Step‑by‑Step Guide
  steps:
  - name: Why the X‑dimension matters
    text: The X‑dimension controls how wide each tiny bar (or “module”) is. A value
      of **4 pixels** yields a barcode that’s clear on screen and prints nicely on
      standard label printers. If you need a denser image for a high‑resolution print,
      bump the value up to 6 or 8.
  - name: Expected output
    text: Open the resulting `PostalPlanetFilledBars.png` and you should see a classic
      Planet barcode—solid vertical bars with a quiet zone on each side. It looks
      just like the example you’d find on a postal envelope.
  - name: What “FilledBars = false” does
    text: Setting `FilledBars` to `false` tells the rendering engine to draw only
      the bar outlines. This is useful when you need a lighter‑weight image for on‑screen
      display or when a printing guideline explicitly requires the empty style.
  - name: Expected output
    text: The `PostalPlanetEmptyBars.png` file shows the same pattern as before, but
      each bar is a thin line instead of a solid block. It’s perfect for low‑contrast
      printing on colored paper.
  - name: When to use RM4SCC
    text: RM4SCC is the Dutch “Postcode” barcode. If you’re building a multi‑country
      logistics platform, having both Planet and RM4SCC generators at hand saves you
      a lot of boilerplate code.
  - name: What if I need a different image format?
    text: Just swap `BarCodeImageFormat.Png` for `Jpeg`, `Bmp`, or `Gif`. The library
      handles the conversion automatically.
  - name: How do I change the barcode height?
    text: Use `planetFilled.Parameters.Barcode.BarHeight = 50; // height in points`
      (or pixels, depending on the library version). Higher values give you a taller
      barcode, which can improve scan reliability on low‑resolution scanners.
  - name: Can I embed the barcode directly into a PDF?
    text: Absolutely. The `Save` method returns a `byte[]` if you call the overload
      that writes to a stream. Feed that stream into a PDF generation library (e.g.,
      iTextSharp) and you’ve got a fully‑automated mailing label.
  - name: What if the data string contains non‑numeric characters?
    text: 'Planet and RM4SCC expect **numeric only** payloads. Passing letters will
      throw an `ArgumentException`. Validate your input first:'
  - name: Does the X‑dimension affect scanning speed?
    text: A larger X‑dimension creates a more robust barcode, which generally improves
      scanning speed, especially on low‑quality scanners. However, it also increases
      the physical size of the label, so balance readability with space constraints.
  type: HowTo
tags:
- barcode
- C#
- imaging
title: 惑星バーコード画像の作成 – ステップバイステップガイド
url: /ja/python-java/general/create-planet-barcode-image-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Planet バーコード画像の作成 – 完全 C# チュートリアル

メールシステムや物流アプリで **planet バーコードを生成する方法** を考えたことはありませんか？ あなただけが頭を抱えているわけではありません。このチュートリアルでは、`BarcodeGenerator` クラスの基本から X‑dimension の調整、塗りつぶしバーから空白バーへの切り替えまで、 **planet バーコード画像** を作成するために必要なすべてを解説します。

さらに、関連するシンボルである RM4SCC も簡単に紹介します。これにより、他の郵便バーコードでも同様のパターンが使えることが分かります。最後まで読むと、PNG ファイルをそのままプロジェクトに組み込める 3 つの実行可能なコードスニペットが手に入ります。

## 必要な環境

- .NET 6.0 以上（.NET Framework 4.7+ でも動作します）  
- **Aspose.BarCode** への参照（または `BarcodeGenerator`、`EncodeTypes`、`BarCodeImageFormat` を提供する任意のライブラリ）  
- お好きな IDE（Visual Studio、Rider、VS Code など）  
- 画像を書き込めるフォルダー（サンプル中の `YOUR_DIRECTORY` を置き換えてください）

以上です。バーコードライブラリ以外に追加の NuGet パッケージは不要です。

---

## Step 1: プロジェクトとインポートの設定

まずは、コードをすぐに実行できる小さなコンソール アプリを作成しましょう。

```csharp
using System;
using Aspose.BarCode.Generation;   // Core barcode generator
using Aspose.BarCode;               // For BarCodeImageFormat enum

namespace PlanetBarcodeDemo
{
    class Program
    {
        static void Main(string[] args)
        {
            // We'll call helper methods here (see later)
            GeneratePlanetFilledBars();
            GeneratePlanetEmptyBars();
            GenerateRM4SCCFilledBars();
        }
```

> **プロのコツ:** `Main` メソッドはシンプルに保ち、各シナリオは個別のメソッドに委譲しましょう。コードが読みやすくなるだけでなく、元のスニペットにある 3 つの例と同様の構造になります。

---

## Step 2: **planet バーコード画像** をデフォルトの塗りつぶしバーで作成

Planet シンボルは多くの郵便サービスで追跡番号に使用されています。通常の実線バーで **planet バーコード画像** を作成するには、次の 3 行だけです。

```csharp
        static void GeneratePlanetFilledBars()
        {
            // 1️⃣ Create a generator for the Planet symbology with data "123456"
            BarcodeGenerator planetFilled = new BarcodeGenerator(EncodeTypes.Planet, "123456");

            // 2️⃣ Set the X‑dimension (module width) to 4 pixels for better visibility
            planetFilled.Parameters.Barcode.XDimension.Pixels = 4;

            // 3️⃣ Save the barcode as a PNG image
            planetFilled.Save("YOUR_DIRECTORY/PostalPlanetFilledBars.png", BarCodeImageFormat.Png);
        }
```

### X‑dimension が重要な理由
X‑dimension は各小さなバー（「モジュール」）の幅を決定します。**4 ピクセル** の値は、画面上でもはっきりと表示され、標準的なラベルプリンターでも綺麗に印刷できます。高解像度印刷用に密度を上げたい場合は、6 や 8 に変更してください。

### 期待される出力
生成された `PostalPlanetFilledBars.png` を開くと、クラシックな Planet バーコードが表示されます。左右にクワイエットゾーンを持つ実線の垂直バーが特徴で、郵便封筒に印刷されている例と同じ見た目です。

---

## Step 3: **planet バーコード画像** を空白バーで作成

郵便仕様によっては、バーが塗りつぶしではなく輪郭だけの *空白バー* スタイルが求められることがあります。このモードへの切り替えはプロパティ一つで完了します。

```csharp
        static void GeneratePlanetEmptyBars()
        {
            // 1️⃣ Create the generator (same data as before)
            BarcodeGenerator planetEmpty = new BarcodeGenerator(EncodeTypes.Planet, "123456");

            // 2️⃣ Keep the X‑dimension consistent
            planetEmpty.Parameters.Barcode.XDimension.Pixels = 4;

            // 3️⃣ Disable filled bars → we get an empty‑bar representation
            planetEmpty.Parameters.Barcode.FilledBars = false;

            // 4️⃣ Save the PNG
            planetEmpty.Save("YOUR_DIRECTORY/PostalPlanetEmptyBars.png", BarCodeImageFormat.Png);
        }
```

### `FilledBars = false` が行うこと
`FilledBars` を `false` に設定すると、描画エンジンはバーの輪郭だけを描きます。画面表示用に軽量な画像が必要なときや、印刷ガイドラインで空白スタイルが指定されている場合に便利です。

### 期待される出力
`PostalPlanetEmptyBars.png` は先ほどと同じパターンですが、各バーが実線ではなく細い線で描かれています。カラー紙への低コントラスト印刷に最適です。

---

## Step 4: RM4SCC バーコードを生成（ボーナス）

メインは Planet シンボルですが、同じ API を使って他の郵便コード向けにも **planet バーコード画像** と同様の結果を得られます。ここではオランダの「Postcode」バーコードである RM4SCC の生成方法を示します。

```csharp
        static void GenerateRM4SCCFilledBars()
        {
            // 1️⃣ Create a generator for the RM4SCC symbology
            BarcodeGenerator rm4sccFilled = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");

            // 2️⃣ Align X‑dimension with the other examples
            rm4sccFilled.Parameters.Barcode.XDimension.Pixels = 4;

            // 3️⃣ Save the image
            rm4sccFilled.Save("YOUR_DIRECTORY/PostalRM4SCCFilledBars.png", BarCodeImageFormat.Png);
        }
    }
}
```

### RM4SCC を使うタイミング
RM4SCC はオランダの郵便バーコードです。多国展開の物流プラットフォームを構築する場合、Planet と RM4SCC の両方のジェネレータを用意しておくと、ボイラープレートコードを大幅に削減できます。

---

## よくある質問とエッジケース

### 画像形式を変えたいときは？
`BarCodeImageFormat.Png` を `Jpeg`、`Bmp`、`Gif` に置き換えるだけです。ライブラリが自動で変換してくれます。

### バーコードの高さはどう変更する？
`planetFilled.Parameters.Barcode.BarHeight = 50; // height in points`（またはピクセル、ライブラリのバージョンによる）と設定します。高さを上げるとバーコードが長くなり、低解像度スキャナでの読み取り信頼性が向上します。

### バーコードを直接 PDF に埋め込めますか？
もちろんです。`Save` メソッドのストリームオーバーロードを使用すれば `byte[]` が取得できます。そのバイト配列を iTextSharp などの PDF 生成ライブラリに渡せば、完全に自動化されたラベルが作れます。

### データ文字列に数字以外が含まれていたら？
Planet と RM4SCC は **数字のみ** のペイロードを想定しています。文字が含まれると `ArgumentException` がスローされます。事前に入力を検証してください。

```csharp
if (!Regex.IsMatch(data, @"^\d+$"))
    throw new ArgumentException("Planet barcode data must be numeric.");
```

### X‑dimension がスキャン速度に影響しますか？
X‑dimension を大きくするとバーが太くなり、ローパフォーマンスのスキャナでも読み取りが速くなる傾向があります。ただし、ラベルの物理サイズも大きくなるため、可読性とスペースのバランスを取る必要があります。

---

## 完全動作サンプル（3 つのメソッドすべて）

以下は新しいコンソール プロジェクトに貼り付けてそのまま実行できる完全プログラムです。`YOUR_DIRECTORY` を、アプリが書き込み可能な絶対パスまたは相対パスに置き換えてください。

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

namespace PlanetBarcodeDemo
{
    class Program
    {
        static void Main(string[] args)
        {
            GeneratePlanetFilledBars();
            GeneratePlanetEmptyBars();
            GenerateRM4SCCFilledBars();

            Console.WriteLine("All barcode images have been saved.");
        }

        static void GeneratePlanetFilledBars()
        {
            BarcodeGenerator planetFilled = new BarcodeGenerator(EncodeTypes.Planet, "123456");
            planetFilled.Parameters.Barcode.XDimension.Pixels = 4;
            planetFilled.Save("YOUR_DIRECTORY/PostalPlanetFilledBars.png", BarCodeImageFormat.Png);
        }

        static void GeneratePlanetEmptyBars()
        {
            BarcodeGenerator planetEmpty = new BarcodeGenerator(EncodeTypes.Planet, "123456");
            planetEmpty.Parameters.Barcode.XDimension.Pixels = 4;
            planetEmpty.Parameters.Barcode.FilledBars = false;
            planetEmpty.Save("YOUR_DIRECTORY/PostalPlanetEmptyBars.png", BarCodeImageFormat.Png);
        }

        static void GenerateRM4SCCFilledBars()
        {
            BarcodeGenerator rm4sccFilled = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");
            rm4sccFilled.Parameters.Barcode.XDimension.Pixels = 4;
            rm4sccFilled.Save("YOUR_DIRECTORY/PostalRM4SCCFilledBars.png", BarCodeImageFormat.Png);
        }
    }
}
```

プログラムを実行し、3 つの PNG ファイルを開くと、前述の画像がそのまま出力されていることが確認できます。追加設定は不要です。

---

## まとめと次のステップ

ここまでで、**planet バーコード画像** をゼロから生成し、実線と空白スタイルを切り替える方法、さらに RM4SCC への応用まで学びました。重要ポイントは以下の通りです。

1. 正しい `EncodeTypes` とデータで `BarcodeGenerator` をインスタンス化する。  
2. `XDimension.Pixels` でバー幅を調整する。  
3. 空白バーは `FilledBars = false` で実現する。  
4. 好みの画像形式で `Save` する。

これで **planet バーコード画像** を作成できたので、次のような応用を検討してみてください。

- **バッチ生成**: CSV の追跡番号をループして PNG を一括出力。  
- **動的サイズ設定**: Web API の設定項目として X‑dimension とバー高さを公開。  
- **ラベルプリンターとの統合**: PNG バイト列を ZPL 対応プリンターに直接送信し、リアルタイムでラベルを作成。

ぜひ実験してみてください。データ文字列を変えたり、異なる寸法を試したり、同じラベルに QR コードを組み合わせても構いません。バーコードライブラリは柔軟に対応できます。

疑問や難しいシナリオがあれば、下のコメント欄で教えてください。一緒に解決策を考えましょう。ハッピーコーディング！

## 次に学ぶべきこと

以下のチュートリアルは、本ガイドで示したテクニックを応用した関連トピックを扱っています。各リソースには、ステップバイステップの解説と完全動作コード例が含まれているので、API の追加機能をマスターしたり、別の実装アプローチを自分のプロジェクトに取り入れたりするのに役立ちます。

- [Create DotCode barcode image – rows & columns (Aspose.BarCode)](/barcode/english/net/dotcode-barcode-configuration/dotcode-rows-columns-configuration/)
- [Create barcode image C# – GS1 DataMatrix Example](/barcode/english/net/gs1-barcode-encoding/gs1-datamatrix-example/)
- [Create barcode image c# – Configure Codablock F Rows & Columns](/barcode/english/net/codablock-f-encoding/codablock-f-row-column-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}