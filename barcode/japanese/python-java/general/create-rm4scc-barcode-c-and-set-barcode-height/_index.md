---
category: general
date: 2026-08-25
description: ステップバイステップのコードでC#でRM4SCCバーコードを作成し、正確なサイズ調整のためにバーコードの高さを設定する方法を学びましょう。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create rm4scc barcode c#
- how to set barcode height
language: ja
lastmod: 2026-08-25
og_description: Aspose.BarCode を使用して C# で RM4SCC バーコードを作成し、.NET アプリケーションで正確に制御できるようにバーコードの高さの設定方法を学びましょう。
og_image_alt: Screenshot of an RM4SCC barcode generated with C#
og_title: RM4SCCバーコードをC#で作成 – バーコード高さ設定ガイド
schemas:
- author: Aspose
  dateModified: '2026-08-25'
  description: Create RM4SCC barcode C# with step‑by‑step code and learn how to set
    barcode height for precise sizing.
  headline: Create RM4SCC barcode C# and set barcode height
  type: TechArticle
tags:
- barcode
- C#
- RM4SCC
- Aspose.BarCode
title: RM4SCCバーコードをC#で作成し、バーコードの高さを設定する
url: /ja/python-java/general/create-rm4scc-barcode-c-and-set-barcode-height/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# RM4SCC バーコード C# の作成とバーコード高さの設定

Aspose.BarCode ライブラリを使用して RM4SCC バーコード C# をすばやく作成します。このチュートリアルでは **バーコードの高さの設定方法** と、レイアウトに正確に合わせるための他の視覚プロパティのカスタマイズ方法を示します。

完全な、すぐに実行できるコンソールプログラムが表示され、3 つの PNG ファイルが生成されます：

* デフォルト高さの Planet バーコード（比較用）  
* 手動で高さ 100 px に設定した RM4SCC バーコード  
* 空白（未塗りつぶし）バーを持つ Planet バーコード  

この例は、Visual Studio 2022（または任意の .NET 6+ IDE）と有効な Aspose.BarCode for .NET のライセンスまたは評価版があることを前提としています。

## 前提条件

| 要件 | 理由 |
|-------------|--------|
| .NET 6 SDK (or later) | コンソールアプリのランタイムを提供します |
| Aspose.BarCode for .NET NuGet package | `BarcodeGenerator`、`EncodeTypes`、画像エクスポート API を提供します |
| Basic C# knowledge | コードの流れを理解するために必要です |

NuGet パッケージは次のコマンドでインストールします:

```bash
dotnet add package Aspose.BarCode
```

> **プロのコツ:** ライセンスなしでコードを実行すると、生成された画像に小さな Aspose の透かしが入ります。

## ステップ 1: プロジェクト構造の設定

新しいコンソールプロジェクトを作成し、必要な `using` ディレクティブを追加します:

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;
using Aspose.BarCode.BarCodeImageFormat; // optional, you can use the enum directly
```

`using` ステートメントにより、バーコードジェネレータクラスと PNG フォーマット列挙体にアクセスできるようになります。

## ステップ 2: 出力フォルダーの定義

PNG ファイルを保存するフォルダーを選択します。`Save` を呼び出す前に、そのフォルダーが存在している必要があります。

```csharp
// Step 1: Define the output folder
string outputFolder = "GeneratedBarcodes/";

// Ensure the directory exists
System.IO.Directory.CreateDirectory(outputFolder);
```

ディレクトリをプログラムで作成することで、初回実行時に *FileNotFoundException* が発生するのを防げます。

## ステップ 3: デフォルト高さの Planet バーコードを生成（ベースライン）

Planet バーコードは本ガイドの主題ではありませんが、手動でサイズを指定した RM4SCC バーコードと比較するための視覚的ベースラインとして役立ちます。

```csharp
// Step 2: Generate a Planet barcode with the default (auto) height
BarcodeGenerator planetAuto = new BarcodeGenerator(EncodeTypes.Planet, "123456");
planetAuto.Parameters.Barcode.XDimension.Pixels = 4; // controls bar width
planetAuto.Save($"{outputFolder}PostalPlanetBarHeightNone.png", BarCodeImageFormat.Png);
```

*なぜ重要か:*  
`XDimension` は単一バーの幅を決定します。`BarHeight` を変更しながらこれを一定に保つことで、高さの効果だけを確認できます。

## ステップ 4: **Create RM4SCC barcode C#** – 手動で高さを設定

ここでは、主要タスクである **create RM4SCC barcode C#** を実行し、高さを明示的に制御します。

```csharp
// Step 3: Generate an RM4SCC barcode with a manual height of 100 px
BarcodeGenerator rm4sccManual = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");
rm4sccManual.Parameters.Barcode.XDimension.Pixels = 4;           // same bar width as Planet example
rm4sccManual.Parameters.Barcode.BarHeight.Pixels = 100;          // <-- how to set barcode height
rm4sccManual.Save($"{outputFolder}PostalRM4SCCBarHeight100Pixels.png", BarCodeImageFormat.Png);
```

### バーコードの高さの設定方法

`BarHeight` プロパティは `Parameters.Barcode` の下にあります。`Unit` に応じて **ピクセル**、**ポイント**、または **ミリメートル** で表した `float` 値を受け取ります（`Pixels`、`Points`、`Millimeters`）。この例では出力形式が PNG なので `Pixels` を使用しています。

ミリメートル単位で高さを指定したい場合は、まずユニットを切り替えます:

```csharp
rm4sccManual.Parameters.Barcode.BarHeight.Unit = BarHeightUnit.Millimeters;
rm4sccManual.Parameters.Barcode.BarHeight.Value = 25; // 25 mm tall
```

## ステップ 5: 空白（未塗りつぶし）バーを持つ Planet バーコードを生成

このステップでは、別の便利なプロパティ `FilledBars` を示します。`false` に設定すると「空洞」バーコードが生成され、デザイン上の用途に便利です。

```csharp
// Step 4: Generate a Planet barcode with empty (unfilled) bars
BarcodeGenerator planetEmptyBars = new BarcodeGenerator(EncodeTypes.Planet, "123456");
planetEmptyBars.Parameters.Barcode.XDimension.Pixels = 4;
planetEmptyBars.Parameters.Barcode.FilledBars = false; // makes bars transparent
planetEmptyBars.Save($"{outputFolder}PostalPlanetEmptyBars.png", BarCodeImageFormat.Png);
```

## 完全な実行可能プログラム

`Program.cs` に以下のコードをコピーしてください。プロジェクトをビルドして実行すると、`GeneratedBarcodes` フォルダーに 3 つの PNG ファイルが生成されます。



## 次に学ぶべきことは？

以下のチュートリアルは、本ガイドで示した手法を基にした、密接に関連するトピックを取り上げています。各リソースには、完全な動作コード例とステップバイステップの解説が含まれており、追加の API 機能を習得し、独自プロジェクトでの代替実装方法を検討するのに役立ちます。

- [Java で code128 バーコードを作成し、バーの高さを設定する方法](/barcode/english/java/barcode-configuration/setting-bars-height/)
- [Aspose.BarCode を使用して .NET で Code 16K のクワイエットゾーンを作成する方法](/barcode/english/net/code-16k-encoding/code-16k-quiet-zone-settings/)
- [.NET 用 Aspose.BarCode で Aztec バーコードを作成する方法](/barcode/english/net/aztec-barcode-encoding/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}