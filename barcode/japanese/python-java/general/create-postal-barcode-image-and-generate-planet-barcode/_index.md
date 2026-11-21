---
category: general
date: 2026-11-20
description: C#で郵便バーコード画像を素早く作成。カスタマイズ可能なバーのスタイルで、PlanetバーコードとRM4SCCバーコードの生成方法を学びましょう。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create postal barcode image
- generate planet barcode
- postal barcode C#
- Aspose.BarCode example
- barcode image generation
language: ja
lastmod: 2026-11-20
og_description: Aspose.BarCode を使用して C# で郵便バーコード画像を作成します。このチュートリアルでは、プラネットバーコードの生成、バーのスタイルのカスタマイズ、RM4SCC
  画像の作成方法を示します。
og_image_alt: Create postal barcode image example showing filled and empty bars
og_title: C#で郵便バーコード画像を作成する – ステップバイステップガイド
schemas:
- author: Aspose
  dateModified: '2026-11-20'
  description: Create postal barcode image in C# quickly. Learn how to generate planet
    barcode and RM4SCC barcodes with customizable bar styles.
  headline: Create postal barcode image and generate planet barcode
  type: TechArticle
tags:
- barcode
- C#
- Aspose
title: 郵便バーコード画像を作成し、プラネットバーコードを生成する
url: /ja/python-java/general/create-postal-barcode-image-and-generate-planet-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 郵便バーコード画像を作成し、Planet バーコードを生成する

C# で Aspose.BarCode ライブラリを使用して郵便バーコード画像を作成します。メールアプリケーション向けに Planet バーコードまたは RM4SCC バーコードを生成する必要がある場合、このチュートリアルは完全な、すぐに実行できるソリューションを提供します。

郵便サービス向けのバーコード生成は、正確な寸法と塗りつぶしバーと空バーのスタイルを切り替えるオプションが必要になることが多いです。このガイドでは、出力フォルダーの設定、塗りつぶしバーと空バーの両方の Planet バーコードの作成、そして同じビジュアル設定で RM4SCC バーコードを生成する手順を説明します。最後まで実行すると、メールワークフローで直接使用できる 4 つの PNG ファイルが得られます。

## 前提条件

開始する前に、以下がインストールされていることを確認してください。

* .NET 6.0 以降がインストールされていること  
* Visual Studio 2022（またはお好みの C# IDE）  
* **Aspose.BarCode** NuGet パッケージ（`Install-Package Aspose.BarCode`）  

追加の設定は不要です。コードはデフォルトフォントと PNG エンコーダーのみを使用します。

## 郵便バーコード画像の作成 – 概要

このプロセスの中心は `BarcodeGenerator` クラスです。`EncodeTypes` の値を受け取り、バーコードのシンボロジーを決定します（例: `EncodeTypes.Planet` は Planet バーコード用）。ジェネレーターを設定したら、`Save` を呼び出して画像ファイルを書き出します。

![Create postal barcode image example](/images/postal_barcode_example.png)

*Alt text: 塗りつぶしバーと空バーを示す郵便バーコード画像作成例.*

## 手順 1: 出力フォルダーの設定

まず、PNG ファイルを保存するフォルダーを定義します。絶対パスでも相対パスでも同様に機能しますので、フォルダーが存在することを確認するか、コードに作成させてください。

```csharp
using System.IO;
using Aspose.BarCode.Generation;

// Define the output folder (change to your own path)
string outputFolder = Path.Combine(Directory.GetCurrentDirectory(), "Barcodes");

// Ensure the directory exists
Directory.CreateDirectory(outputFolder);
```

プログラムでフォルダーを作成すると、チュートリアルを新しいマシンで実行した際に `DirectoryNotFoundException` が発生するのを防げます。

## 手順 2: 塗りつぶしバーで Planet バーコードを生成

塗りつぶしバーの Planet バーコードはデフォルトのビジュアルスタイルです。以下のコードはバーコードを作成し、X‑dimension を 4 ピクセルに設定（郵便アプリケーションで一般的なサイズ）し、画像を保存します。

```csharp
// Step 2: Generate a Planet barcode with filled bars
BarcodeGenerator planetFilled = new BarcodeGenerator(EncodeTypes.Planet, "123456");

// Set the X‑dimension (module width) to 4 pixels
planetFilled.Parameters.Barcode.XDimension.Pixels = 4;

// Save as PNG
string planetFilledPath = Path.Combine(outputFolder, "PostalPlanetFilledBars.png");
planetFilled.Save(planetFilledPath, BarCodeImageFormat.Png);
```

**この動作の理由:**  
* `EncodeTypes.Planet` はジェネレーターに Planet シンボロジーを使用させます。これは多くの郵便サービスで必須です。  
* `XDimension.Pixels` は各バーの幅を制御します。4 px はファイルサイズが過大にならず、スキャンしやすいクリアな画像を実現します。  
* `Save` メソッドは `BarCodeImageFormat` 列挙体に基づいて PNG エンコーダーを自動的に選択します。

## 手順 3: 空バーで Planet バーコードを生成

一部の郵便仕様では、暗い背景に空（白）バーを使用することが好まれます。`FilledBars` を `false` に設定することで実現できます。

```csharp
// Step 3: Generate a Planet barcode with empty bars
BarcodeGenerator planetEmpty = new BarcodeGenerator(EncodeTypes.Planet, "123456");

// Keep the same X‑dimension for consistency
planetEmpty.Parameters.Barcode.XDimension.Pixels = 4;

// Disable filled bars – the bars become transparent (empty)
planetEmpty.Parameters.Barcode.FilledBars = false;

// Save the result
string planetEmptyPath = Path.Combine(outputFolder, "PostalPlanetEmptyBars.png");
planetEmpty.Save(planetEmptyPath, BarCodeImageFormat.Png);
```

**Tip:** `FilledBars` が `false` の場合、ジェネレーターはバーを背景色（デフォルトは白）で塗り、スペースを前景色（黒）で描画します。別の配色が必要な場合は、`Parameters.Barcode.ForeColor` と `BackColor` を調整してください。

## 手順 4: 塗りつぶしバーで RM4SCC バーコードを生成

RM4SCC はイギリスで使用される別の郵便シンボロジーです。作成手順は Planet の例と同様で、`EncodeTypes` の値だけが変わります。

```csharp
// Step 4: Generate an RM4SCC barcode with filled bars
BarcodeGenerator rm4sccFilled = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");

// Reuse the same X‑dimension for a uniform look
rm4sccFilled.Parameters.Barcode.XDimension.Pixels = 4;

// Save the PNG file
string rm4sccPath = Path.Combine(outputFolder, "PostalRM4SCCFilledBars.png");
rm4sccFilled.Save(rm4sccPath, BarCodeImageFormat.Png);
```

**What to expect:** 生成された PNG は、UK の郵便ガイドラインに準拠したコンパクトな RM4SCC バーコードを表示します。X‑dimension が同一のため、画像サイズは Planet バーコードとほぼ同じになります。

## 手順 5: 生成された画像を確認

プログラムを実行した後、`Barcodes` フォルダー内の 4 つのファイルを開きます。以下が表示されるはずです。

* `PostalPlanetFilledBars.png` – 明るい背景に暗いバー  
* `PostalPlanetEmptyBars.png` – 暗い背景に明るいバー（逆）  
* `PostalRM4SCCFilledBars.png` – 標準的な RM4SCC パターン  

画像が歪んでいる場合は、次の点を確認してください。

* **X‑dimension** – 2 px 未満はぼやけの原因になり、10 px 超はラベルサイズの制限を超える可能性があります。  
* **Data string** – `"123456"` の値は選択したシンボロジーの長さ要件を満たす必要があります（Planet は 6 桁、RM4SCC も 6 桁が必要）。  
* **Folder permissions** – アプリケーションが出力ディレクトリに書き込み権限を持っていることを確認してください。

## 一般的なバリエーションとエッジケース

| シナリオ | 調整 |
|----------|------|
| **Different barcode data** | `"123456"` を任意の有効な数値文字列に置き換えます。Planet は長さが正確に 6 桁である必要があり、RM4SCC も 6 桁が必要です。 |
| **Custom colors** | `planetFilled.Parameters.Barcode.ForeColor = System.Drawing.Color.DarkBlue;` と `BackColor = System.Drawing.Color.LightYellow;` を設定します。 |
| **Higher resolution** | 大きな印刷用に `XDimension.Pixels` を 6 または 8 に増やします。 |
| **Other image formats** | `Save` 呼び出しで `BarCodeImageFormat.Jpeg` または `BarCodeImageFormat.Bmp` を使用します。 |
| **Batch generation** | 文字列コレクションをループし、同じジェネレーター ロジックをループ内で呼び出し、`outputFolder` パスを再利用します。 |

## 完全な実行可能サンプル

以下のコードを新しい C# コンソール プロジェクトにコピーしてください。 .NET 6.0 でコンパイルでき、4 つのバーコード画像が自動的に生成されます。



## 次に学ぶべきことは？

以下のチュートリアルは、本ガイドで示した手法を基にした密接に関連するトピックをカバーしています。各リソースには、ステップバイステップの解説と完全な動作コード例が含まれており、追加の API 機能を習得し、独自プロジェクトで代替実装アプローチを探求するのに役立ちます。

- [C# でカスタム高さの郵便バーコード画像を作成する方法](/barcode/english/python-java/general/how-to-create-postal-barcode-image-with-custom-heights-in-c/)
- [C# で RM4SCC バーコードを作成し、Planet バーコードを生成する方法](/barcode/english/python-java/general/how-to-create-rm4scc-barcode-and-generate-planet-barcode-in/)
- [C# で郵便バーコード画像を作成する – ステップバイステップガイド](/barcode/english/python-java/general/create-postal-barcode-image-in-c-step-by-step-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}