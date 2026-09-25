---
category: general
date: 2026-08-22
description: C#でDataBar Stacked Omni‑Directionalジェネレータを使用してバーコードのサイズを変更する方法。PNG出力のX寸法とアスペクト比の設定方法を学びましょう。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to change barcode size
- DataBar Stacked Omni‑Directional barcode
- C# barcode generator
- barcode aspect ratio
- X‑dimension pixels
- BarCodeImageFormat PNG
language: ja
lastmod: 2026-08-22
og_description: C#でDataBar Stacked Omni‑Directionalジェネレーターを使用してバーコードのサイズを変更する方法。X軸寸法とアスペクト比を調整するステップバイステップのガイドに従ってください。
og_image_alt: Screenshot showing how to change barcode size in C#
og_title: C#でバーコードサイズを変更する方法 – 完全ガイド
schemas:
- author: Aspose
  dateModified: '2026-08-22'
  description: How to change barcode size in C# using the DataBar Stacked Omni‑Directional
    generator. Learn to set X‑dimension and aspect ratio for PNG output.
  headline: How to change barcode size in C# with DataBar Stacked
  type: TechArticle
- description: How to change barcode size in C# using the DataBar Stacked Omni‑Directional
    generator. Learn to set X‑dimension and aspect ratio for PNG output.
  name: How to change barcode size in C# with DataBar Stacked
  steps:
  - name: Create a DataBar Stacked Omni‑Directional barcode generator
    text: The generator object holds all barcode settings. By passing `EncodeTypes.DatabarStackedOmniDirectional`
      and sample data, you create a valid barcode ready for further customization.
  - name: Set the basic module size (X‑dimension) in pixels
    text: The X‑dimension defines the width of a single barcode module. Adjusting
      it changes the overall width and height proportionally.
  - name: Change the barcode aspect ratio to 15 and save the image
    text: The **barcode aspect ratio** controls the height‑to‑width relationship.
      An aspect ratio of 15 yields a relatively tall barcode.
  - name: Change the barcode aspect ratio to 30 and save the new image
    text: Increasing the aspect ratio to 30 makes the barcode even taller, illustrating
      the flexibility of size adjustments.
  - name: Verify the generated images
    text: Open the PNG files in any image viewer. You should see two barcodes with
      identical width (controlled by the X‑dimension) but different heights (controlled
      by the aspect ratio). If the images appear blurry, increase the X‑dimension
      pixels; if they are too tall, lower the aspect ratio.
  - name: What to explore next
    text: '* **Custom colors** – experiment with `barcodeGenerator.Parameters.Barcode.ForeColor`
      and `BackColor` to match brand guidelines. * **Different barcode types** – replace
      `EncodeTypes.DatabarStackedOmniDirectional` with `EncodeTypes.QR` or `EncodeTypes.Code128`
      to see how size parameters differ across'
  type: HowTo
tags:
- barcode
- C#
- Aspose.BarCode
title: C#でDataBar Stackedを使用してバーコードサイズを変更する方法
url: /ja/python-java/general/how-to-change-barcode-size-in-c-with-databar-stacked/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# C#でDataBar Stackedを使用してバーコードサイズを変更する方法

.NET アプリケーションで **バーコードサイズの変更方法** が必要な場合、本ガイドでは DataBar Stacked Omni‑Directional バーコードジェネレータを使用した正確な手順を示します。X ディメンション（ピクセル）を制御し、バーコードのアスペクト比を調整し、結果を PNG ファイルとして保存する方法が分かります。

印刷ラベルのスペースが限られている場合や、デジタルチャネル向けに高解像度画像が必要な場合など、バーコードサイズの変更は頻繁に求められます。このチュートリアルでは、ジェネレータの初期化からサイズが異なる 2 つの画像の生成まで、必要なすべてをカバーします。

## 前提条件

* .NET 6.0 SDK またはそれ以降がインストールされていること  
* **Aspose.BarCode for .NET** NuGet パッケージへの参照  
* C# の構文に関する基本的な知識  

追加の設定は不要です。コードは Windows、Linux、macOS 上で実行できます。

## C#でバーコードサイズを変更する方法 – ステップバイステップ

以下のセクションでは、プロセスを個別の再利用可能な手順に分解しています。各手順は、コードが **なぜ** 必要なのかを説明し、**何を** 行うかだけでなく **なぜ** なのかを示します。

### 手順 1: DataBar Stacked Omni‑Directional バーコードジェネレータを作成する

ジェネレータオブジェクトはすべてのバーコード設定を保持します。`EncodeTypes.DatabarStackedOmniDirectional` とサンプルデータを渡すことで、さらにカスタマイズできる有効なバーコードを作成します。

```csharp
// Step 1: Create a DataBar Stacked Omni‑Directional barcode generator with sample data
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarStackedOmniDirectional, "(01)12345678901231");
```

*この点が重要な理由* – **C# barcode generator** クラスはエンコードアルゴリズムをカプセル化します。有効なジェネレータから開始することで、以降のサイズ変更が正しいバーコードタイプに適用されることが保証されます。

### 手順 2: 基本モジュールサイズ（X‑dimension）をピクセルで設定する

X‑dimension は単一バーコードモジュールの幅を定義します。これを調整すると、全体の幅と高さが比例して変化します。

```csharp
// Step 2: Define the basic module size (X‑dimension) in pixels
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

*この点が重要な理由* – 大きな X‑dimension は大きなバーコードを生成し、低解像度プリンタに適しています。逆に小さな値は、コンパクトなラベル向けの小さなバーコードを作成します。

### 手順 3: バーコードのアスペクト比を 15 に変更し、画像を保存する

**barcode aspect ratio** は高さと幅の関係を制御します。アスペクト比を 15 に設定すると、比較的高いバーコードが得られます。

```csharp
// Step 3: Set the DataBar aspect ratio to 15 and save the image
barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 15;
barcodeGenerator.Save("YOUR_DIRECTORY/DatabarAspectRatio15.png", BarCodeImageFormat.Png);
```

*この点が重要な理由* – スキャナーデバイスには最適なアスペクト比の要件があります。アスペクト比を 15 に設定することで、幅は X‑dimension で決まり、高さだけを変更して **バーコードサイズの変更方法** を実演できます。

#### 期待される出力

`DatabarAspectRatio15.png` ファイルは、デフォルトよりも縦長の DataBar Stacked Omni‑Directional バーコードを示します。バーコードの幅は 2 ピクセルの X‑dimension を反映し、高さは 15 の比率に従います。

### 手順 4: バーコードのアスペクト比を 30 に変更し、新しい画像を保存する

アスペクト比を 30 に上げると、さらに縦長になり、サイズ調整の柔軟性が示されます。

```csharp
// Step 4: Change the DataBar aspect ratio to 30 and save the new image
barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 30;
barcodeGenerator.Save("YOUR_DIRECTORY/DatabarAspectRatio30.png", BarCodeImageFormat.Png);
```

*この点が重要な理由* – **barcode aspect ratio** の値を入れ替えるだけで、ジェネレータを再作成せずに **バーコードサイズの変更方法** を即座に確認できます。バッチ処理での時間短縮につながります。

#### 期待される出力

`DatabarAspectRatio30.png` は前の画像よりも明らかに縦長で、アスペクト比がバーコードの高さに直接影響することが確認できます。

### 手順 5: 生成された画像を検証する

任意の画像ビューアで PNG ファイルを開きます。幅は X‑dimension で統一されているが、高さはアスペクト比で異なる 2 つのバーコードが表示されるはずです。画像がぼやけている場合は X‑dimension のピクセル数を増やし、過度に高い場合はアスペクト比を下げて調整してください。

```csharp
// Optional verification code – load images and print dimensions
using (var img15 = Image.Load("YOUR_DIRECTORY/DatabarAspectRatio15.png"))
using (var img30 = Image.Load("YOUR_DIRECTORY/DatabarAspectRatio30.png"))
{
    Console.WriteLine($"15‑ratio size: {img15.Width}×{img15.Height}");
    Console.WriteLine($"30‑ratio size: {img30.Width}×{img30.Height}");
}
```

*この点が重要な理由* – プログラムによる検証により、サイズ変更が正しく適用されたことを確実に確認でき、CI パイプラインなど自動化された環境で重要です。

## 一般的なバリエーションとエッジケース

| Situation | Adjustment | Reason |
|-----------|------------|--------|
| **非常に小さいラベル** | Set `XDimension.Pixels = 1` and `AspectRatio = 10` | 読みやすさを保ちつつ全体のフットプリントを削減します |
| **高解像度印刷** | Set `XDimension.Pixels = 4` and `AspectRatio = 20` | 鮮明な出力のためにピクセル密度を高めます |
| **異なる画像形式** | Replace `BarCodeImageFormat.Png` with `BarCodeImageFormat.Jpeg` | PNG のサポートが制限されている場合に有用です |
| **動的データ** | Pass a variable string to the `BarcodeGenerator` constructor | 各製品のバーコードを自動的に生成します |

多数のバーコードをサイズ違いで生成する必要がある場合は、手順をメソッドにまとめます。

```csharp
void GenerateDatabar(string data, int xDim, int aspectRatio, string filePath)
{
    var generator = new BarcodeGenerator(EncodeTypes.DatabarStackedOmniDirectional, data);
    generator.Parameters.Barcode.XDimension.Pixels = xDim;
    generator.Parameters.Barcode.DataBar.AspectRatio = aspectRatio;
    generator.Save(filePath, BarCodeImageFormat.Png);
}
```

`GenerateDatabar("(01)98765432109876", 3, 25, "output.png")` を呼び出すと、1 行のコードでカスタムサイズのバーコードが生成されます。

## 信頼性の高いサイズ変更のためのプロのコツ

* **アスペクト比を設定する前に必ず X‑dimension を設定してください。** アスペクト比を先に変更すると、X‑dimension が非理想的なデフォルト値になる場合に予期しないスケーリングが発生することがあります。  
* **一貫した出力フォルダーを使用してください。** デモでは `"YOUR_DIRECTORY"` をハードコーディングしても構いませんが、本番環境では `Path.Combine(Environment.CurrentDirectory, "Barcodes")` の使用を推奨します。  
* **生成された画像サイズを検証してください。** X‑dimension の微小な変更は画面上では目立たないことがあります。ピクセル寸法を確認することで、変更が確実に反映されたことを保証できます。  

## 結論

これで **バーコードサイズの変更方法** を C# と DataBar Stacked Omni‑Directional バーコードジェネレータを使ってマスターしました。**X‑dimension ピクセル** と **barcode aspect ratio** を調整することで、ラベルサイズや解像度要件に合わせた PNG 画像を簡単に作成できます。上記の完全な実行可能サンプルは、ジェネレータ作成からサイズ検証までの全ワークフローを示しています。

### 次に探求すべきこと

* **カスタムカラー** – `barcodeGenerator.Parameters.Barcode.ForeColor` と `BackColor` を試して、ブランドガイドラインに合わせた配色にします。  
* **異なるバーコードタイプ** – `EncodeTypes.DatabarStackedOmniDirectional` を `EncodeTypes.QR` や `EncodeTypes.Code128` に置き換えて、シンボロジーごとのサイズパラメータの違いを確認します。  
* **バッチ処理** – `GenerateDatabar` メソッドと CSV インポートを組み合わせ、数千件のバーコードを自動生成します。

コードスニペットはプロジェクトのアーキテクチャに合わせて自由に調整し、バーコードサイズの調整でスキャン信頼性とビジュアルデザインを向上させてください。Happy coding!

## 次に学ぶべきことは？

以下のチュートリアルは、本ガイドで示したテクニックを基にした、密接に関連するトピックをカバーしています。各リソースには、ステップバイステップの解説と完全な動作コード例が含まれており、追加の API 機能を習得し、独自プロジェクトで代替実装アプローチを探求するのに役立ちます。

- [バーコードサイズの調整方法 – Codablock F アスペクト比（Aspose.BarCode for .NET）](/barcode/english/net/codablock-f-encoding/codablock-f-aspect-ratio-customization/)
- [Aspose.BarCode for .NET を使用したカスタムアスペクト比の Aztec バーコード生成方法](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)
- [Aspose.BarCode for .NET を使用した一次元 Databar のバーコード高さの生成と調整方法](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-barcode-height-adjustment/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}