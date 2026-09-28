---
category: general
date: 2026-08-12
description: 正確なピクセルサイズでバーコードを生成する方法を示すバーコードジェネレータの例です。モジュール幅やバーの高さの設定方法を学び、Planetバーコードを作成しましょう。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- barcode generator example
- how to generate barcode
- barcode pixel size
- generate planet barcode
- barcode height setting
language: ja
lastmod: 2026-08-12
og_description: バーコードジェネレータの例では、正確なピクセル寸法でバーコードを生成する方法を示しています。このガイドに従って、Planet および
  RM4SCC コードのモジュール幅とバーの高さを制御してください。
og_image_alt: Screenshot of a barcode generator example showing a Planet barcode with
  custom pixel size
og_title: バーコードジェネレーターの例 – C#でピクセルサイズをカスタマイズ
schemas:
- author: Aspose
  dateModified: '2026-08-12'
  description: barcode generator example that shows how to generate barcode with precise
    pixel size. Learn to set module width, bar height and create Planet barcodes.
  headline: barcode generator example – step‑by‑step guide for custom pixel sizes
  type: TechArticle
- description: barcode generator example that shows how to generate barcode with precise
    pixel size. Learn to set module width, bar height and create Planet barcodes.
  name: barcode generator example – step‑by‑step guide for custom pixel sizes
  steps:
  - name: Install the Aspose.BarCode package
    text: 'Open a terminal in your project folder and run:'
  - name: Add the necessary `using` directives
    text: '```csharp using Aspose.BarCode.Generation; using Aspose.BarCode.BarCodeImageFormat;
      ```'
  - name: – generate a Planet barcode with automatically calculated height
    text: '```csharp // Step 1: Generate a Planet barcode with automatically calculated
      height BarcodeGenerator planetAuto = new BarcodeGenerator(EncodeTypes.Planet,
      "123456");'
  - name: – generate a Planet barcode with an explicit 100‑pixel height
    text: '```csharp // Step 2: Generate a Planet barcode with an explicit 100‑pixel
      height BarcodeGenerator planetFixed = new BarcodeGenerator(EncodeTypes.Planet,
      "123456");'
  - name: – generate an RM4SCC barcode with the same explicit height
    text: '```csharp // Step 3: Generate an RM4SCC barcode with the same explicit
      height BarcodeGenerator rm4sccFixed = new BarcodeGenerator(EncodeTypes.RM4SCC,
      "123456");'
  - name: What is **barcode pixel size**?
    text: '*Pixel size* refers to the physical number of screen or printer pixels
      that represent a single module (`XDimension`). A larger pixel size yields a
      bigger barcode, which can be easier for low‑resolution scanners but consumes
      more label real‑estate.'
  - name: How does `BarHeight` affect readability?
    text: The `BarHeight` property controls the vertical length of the bars. Standards
      for most 1‑D barcodes (including Planet and RM4SCC) recommend a minimum height
      of 10 mm when printed at 300 dpi, which translates to roughly 118 pixels. Setting
      a height below that can cause read errors, especially on mobil
  - name: When should you let the library calculate height automatically?
    text: If you’re generating barcodes for on‑screen display only, the automatic
      calculation keeps the aspect ratio consistent and reduces the amount of manual
      tweaking needed. For printed labels that must meet strict ISO specifications,
      you should **explicitly set the bar height**.
  - name: Pro tip on performance
    text: When generating thousands of barcodes in a batch job, reuse a single `BarcodeGenerator`
      instance and only change the `CodeText` and size parameters between saves. This
      avoids repeated allocation of internal rendering objects and can cut execution
      time by up to 30 %.
  type: HowTo
tags:
- barcode
- C#
- Aspose.BarCode
title: バーコード生成例 – カスタムピクセルサイズのステップバイステップガイド
url: /ja/python-java/general/barcode-generator-example-step-by-step-guide-for-custom-pixe/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# バーコードジェネレータ例 – カスタムピクセルサイズのステップバイステップガイド

すべてのピクセルを制御できる **barcode generator example** が必要な場合、このガイドではその手順を正確に示します。モジュール幅の設定、固定バー高さの定義、そして Planet と RM4SCC のバーコードを予測可能なサイズで生成する方法を学びます。

ほとんどの開発者は、画面やプリンターごとに同じに見える「how to generate barcode」画像の作成に苦労しています。以下のコードスニペットは、Aspose.BarCode for .NET ライブラリのピクセルレベルのパラメータを公開することで、この問題を解決し、推測なしで一貫した出力を実現します。

## What you’ll learn

* 必要な NuGet パッケージのインストール方法。
* 高さを自動計算した Planet バーコードの生成方法。
* 明示的に 100 ピクセルの高さを指定した Planet バーコードの生成方法。
* 同じ明示的な高さで RM4SCC バーコードを生成する方法。
* **barcode pixel size** がスキャン信頼性に与える影響。
* Planet バーコード画像を生成する際の一般的な問題のトラブルシューティングのヒント。

.NET 6 以降、基本的な C# 開発環境、そして NuGet パッケージを取得できるインターネット接続があれば始められます。

---

## barcode generator example – set up the development environment

コードを書く前に、Aspose.BarCode ライブラリがプロジェクトで利用可能であることを確認してください。

### Install the Aspose.BarCode package

プロジェクトフォルダーでターミナルを開き、次のコマンドを実行します:

```bash
dotnet add package Aspose.BarCode
```

このコマンドは **Aspose.BarCode** の最新安定版を `csproj` に追加します。復元が完了したら、`BarcodeGenerator` クラスの使用を開始できます。

> **Pro tip:** .NET 6 または .NET 7 をターゲットにすると、最新のパフォーマンス改善とデフォルトの UTF‑8 ハンドリングの恩恵を受けられます。

### Add the necessary `using` directives

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode.BarCodeImageFormat;
```

これらの名前空間は、チュートリアル後半で使用する `BarcodeGenerator` クラスと `BarCodeImageFormat` 列挙体を公開します。

---

## How to generate barcode with custom pixel size

以下の 3 つのステップで、完全な **barcode generator example** を示します。各ステップは前のものに基づいているため、コード全体をコンソールアプリにコピー＆ペーストしてそのまま実行できます。

### Step 1 – generate a Planet barcode with automatically calculated height

```csharp
// Step 1: Generate a Planet barcode with automatically calculated height
BarcodeGenerator planetAuto = new BarcodeGenerator(EncodeTypes.Planet, "123456");

// Set module width (x‑dimension) to 4 pixels
planetAuto.Parameters.Barcode.XDimension.Pixels = 4;

// Save the image as PNG
planetAuto.Save("PlanetAuto.png", BarCodeImageFormat.Png);
```

**Why this works:**  
`XDimension` プロパティは単一のバーコードモジュール（最小の黒または白要素）の幅を定義します。`BarHeight` を省略すると、ライブラリは Planet コードの標準アスペクト比を保つ高さを自動計算します。

**Expected output:** `PlanetAuto.png` という名前の PNG ファイルが生成され、クリーンな Planet バーコードが含まれます。その高さは 4 ピクセルモジュール幅に合わせて自動調整され、通常は 6 文字のペイロードで約 60 ピクセルになります。

### Step 2 – generate a Planet barcode with an explicit 100‑pixel height

```csharp
// Step 2: Generate a Planet barcode with an explicit 100‑pixel height
BarcodeGenerator planetFixed = new BarcodeGenerator(EncodeTypes.Planet, "123456");

// Keep the same module width
planetFixed.Parameters.Barcode.XDimension.Pixels = 4;

// Force the bar height to 100 pixels
planetFixed.Parameters.Barcode.BarHeight.Pixels = 100;

// Save the image
planetFixed.Save("PlanetHeight100.png", BarCodeImageFormat.Png);
```

**Why you might need this:**  
スキャン機器が信頼できる検出のために最小バー高さを要求することがあります。`BarHeight.Pixels` を設定することで、エンコードデータの長さに関係なく、生成されるすべての画像がその要件を満たすことが保証されます。

**Expected output:** `PlanetHeight100.png` は前と同じデータを示しますが、バーの高さが正確に 100 ピクセルになり、視覚的なサイズを完全にコントロールできます。

### Step 3 – generate an RM4SCC barcode with the same explicit height

```csharp
// Step 3: Generate an RM4SCC barcode with the same explicit height
BarcodeGenerator rm4sccFixed = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");

// Use the same module width for consistency
rm4sccFixed.Parameters.Barcode.XDimension.Pixels = 4;

// Apply the 100‑pixel bar height
rm4sccFixed.Parameters.Barcode.BarHeight.Pixels = 100;

// Save the image
rm4sccFixed.Save("RM4SCCHeight100.png", BarCodeImageFormat.Png);
```

**Why this matters:**  
`EncodeTypes.RM4SCC` は物流で使用されるスタック型リニアバーコードです。そのバー高さを Planet バーコードと揃えることで、同じラベル上に両方のシンボルが出現した場合のバッチ処理が簡素化されます。

**Expected output:** `RM4SCCHeight100.png` は完璧にサイズ調整された RM4SCC バーコードを表示し、Planet コードに設定した 100 ピクセルの高さと一致します。

> **Result verification:** 各 PNG を画像ビューアで開き、黒いバーが幅 4 ピクセル、指定した場合は高さ 100 ピクセルであることを確認してください。また、バーコードスキャナーアプリにファイルを渡して「123456」とデコードされるかテストできます。

---

## Understanding barcode pixel size and bar height

### What is **barcode pixel size**?

*Pixel size* は、単一モジュール（`XDimension`）を表す画面またはプリンターピクセルの実数を指します。ピクセルサイズが大きいほどバーコードは大きくなり、低解像度スキャナーには読み取りやすくなりますが、ラベルの使用面積も増えます。

### How does `BarHeight` affect readability?

`BarHeight` プロパティはバーの垂直長さを制御します。Planet や RM4SCC などのほとんどの 1‑D バーコードの標準では、300 dpi で印刷した場合の最小高さは 10 mm とされ、これはおおよそ 118 ピクセルに相当します。この高さ未満に設定すると、特にモバイルカメラでの読み取りエラーが発生しやすくなります。

### When should you let the library calculate height automatically?

画面表示のみを目的としたバーコードを生成する場合、ライブラリの自動計算はアスペクト比を保ち、手動調整の手間を減らします。ISO 仕様など厳格な印刷ラベルが必要な場合は、**バー高さを明示的に設定** すべきです。

---

## Common pitfalls and best practices when you generate Planet barcode

| 落とし穴 | 発生原因 | 対策 |
|---------|----------|------|
| バーが細すぎるまたは太すぎる | 高解像度ディスプレイで `XDimension` がデフォルト (1 ピクセル) のまま | `XDimension.Pixels` を少なくとも 3‑4 に設定 |
| スキャナーがコードを読み取れない | `BarHeight` がスキャナーの焦点距離に対して小さすぎる | ほとんどのモバイルスキャナー向けに `BarHeight.Pixels` ≥ 100 を使用 |
| スケーリング後に画像がぼやける | JPEG で保存すると圧縮アーティファクトが発生 | ロスレス出力の PNG (`BarCodeImageFormat.Png`) で保存 |
| 予期しないバーコードタイプ | `EncodeTypes` 列挙体の値が間違っている | Planet シンボルには `EncodeTypes.Planet` を使用しているか再確認 |

### Pro tip on performance

数千件のバーコードをバッチ処理で生成する場合、`BarcodeGenerator` インスタンスを 1 つだけ再利用し、`CodeText` とサイズパラメータだけを変更して保存します。これにより内部レンダリングオブジェクトの再割り当てが回避され、実行時間が最大 30 % 短縮されることがあります。

---

## Full working example – put everything together

新しいコンソールプロジェクトを作成します (`dotnet new console -n BarcodeDemo`)。次に `Program.cs` の内容を以下に置き換えてください:

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode.BarCodeImageFormat;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // Directory where PNG files will be saved
            string outputDir = Environment.CurrentDirectory;

            // ---------- Planet barcode – automatic height ----------
            var planetAuto = new BarcodeGenerator(EncodeTypes.Planet, "123456");
            planetAuto.Parameters.Barcode.XDimension.Pixels = 4;
            planetAuto.Save($"{outputDir}/PlanetAuto.png", BarCodeImageFormat.Png);
            Console.WriteLine("PlanetAuto.png generated.");

            // ---------- Planet barcode – fixed 100‑pixel height ----------
            var planetFixed = new BarcodeGenerator(EncodeTypes.Planet, "123456");
            planetFixed.Parameters.Barcode.XDimension.Pixels = 4;
            planetFixed.Parameters.Barcode.BarHeight.Pixels = 100;
            planetFixed.Save($"{outputDir}/PlanetHeight100.png", BarCodeImageFormat.Png);
            Console.WriteLine("PlanetHeight100.png generated.");

            // ---------- RM4SCC barcode – same fixed height ----------
            var rm4sccFixed = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");
            rm4sccFixed.Parameters.Barcode.XDimension.Pixels = 4;
            rm4sccFixed.Parameters.Barcode.BarHeight.Pixels = 100;
            rm4sccFixed.Save($"{outputDir}/RM4SCCHeight100.png", BarCodeImageFormat.Png);
            Console.WriteLine("RM4SCCHeight100.png generated.");

            Console.WriteLine("All barcodes created successfully.");
        }
    }
}
```

`dotnet run` でプログラムを実行します。実行後、プロジェクトフォルダーに 3 つの PNG ファイルが作成され、それぞれが異なる **barcode generator example** シナリオを示します。

---

## Next steps and related topics

* **How to generate barcode in other formats** – `EncodeTypes.Code128`、`EncodeTypes.QR`、`EncodeTypes.DataMatrix` など 2‑D 用のフォーマットを調査してください。
* **Embedding barcodes in PDFs** – Aspose.BarCode と Aspose.PDF を組み合わせて、請求書テンプレートに直接バーコードを配置できます。
* **Dynamic barcode size based on user input** – ユーザー入力に基づいてサイズを計算する方法

## What Should You Learn Next?

以下のチュートリアルは、本ガイドで示したテクニックに基づく関連トピックをカバーしています。各リソースには、完全な動作コード例とステップバイステップの解説が含まれており、追加の API 機能を習得し、独自プロジェクトで代替実装アプローチを探求するのに役立ちます。

- [How to generate barcode java: Create an Exact Barcode Image](/barcode/english/java/barcode-basics/creating-image-exact-barcode/)
- [How to Generate Barcode in Java Create and Set Size for Whole Picture](/barcode/english/java/barcode-basics/creating-setting-size-whole-picture-barcode/)
- [How to create code128 barcode Java and set bar height](/barcode/english/java/barcode-configuration/setting-bars-height/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}