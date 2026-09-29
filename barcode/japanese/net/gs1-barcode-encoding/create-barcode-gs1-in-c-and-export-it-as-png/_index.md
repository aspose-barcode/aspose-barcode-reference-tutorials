---
category: general
date: 2026-09-29
description: C#でGS1バーコードを作成し、BarcodeGeneratorを使用してバーコードのPNG画像を生成します。ステップバイステップのガイドに従って、バーコード画像を効率的にエクスポートしましょう。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode gs1
- generate barcode png
- barcode generator c#
- how to generate barcode
- export barcode image
language: ja
lastmod: 2026-09-29
og_description: C#でGS1バーコードを作成し、BarcodeGeneratorでバーコードPNGファイルを生成します。この完全なガイドに従って、バーコード画像をすばやくエクスポートしましょう。
og_image_alt: Generated GS1 MicroPDF417 barcode saved as a PNG file
og_title: C#でGS1バーコードを作成 – 数分でPNGとしてエクスポート
schemas:
- author: Aspose
  dateModified: '2026-09-29'
  description: Create barcode GS1 in C# and generate barcode PNG images using BarcodeGenerator.
    Follow a step‑by‑step guide to export barcode image efficiently.
  headline: Create barcode GS1 in C# and export it as PNG
  type: TechArticle
tags:
- barcode
- C#
- GS1
- PNG
- Aspose
title: C#でGS1バーコードを作成し、PNGとしてエクスポートする
url: /ja/net/gs1-barcode-encoding/create-barcode-gs1-in-c-and-export-it-as-png/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# C#でGS1バーコードを作成しPNGとしてエクスポートする

.NET アプリケーションで **GS1 バーコードを作成** したい場合、本ガイドではその手順を正確に示します。Aspose.BarCode の `BarcodeGenerator` クラスを使用して、バーコードの PNG 画像を生成し、ディスクにエクスポートする簡潔なソリューションをご覧いただけます。

GS1 バーコードの生成は、在庫管理、出荷、POS システムなどで一般的な要件です。このチュートリアルの最後までに、GS1 準拠の MicroPDF417 バーコードを作成し、高品質な PNG ファイルとして保存する小さな C# プログラムを書けるようになります。

## 前提条件

開始する前に、以下がインストールされていることを確認してください。

* **.NET 6**（またはそれ以降の .NET バージョン）
* **Visual Studio 2022** もしくは C# をサポートする任意の IDE
* **Aspose.BarCode for .NET** NuGet パッケージ（`Aspose.BarCode`） – 例で使用する `BarcodeGenerator` API を提供します
* C# の基本的な構文に慣れていること

> **プロのコツ:** 実験時は Aspose.BarCode の無料コミュニティエディションを使用してください。フルバージョンでは評価用の透かしが除去されます。

## Step 1 – BarcodeGenerator で GS1 バーコードを作成

まず、*MicroPDF417* フォーマット用に `BarcodeGenerator` をインスタンス化し、GS1 データ文字列を渡す必要があります。GS1 アプリケーション識別子（AI）は丸括弧で囲みます。例: GTIN‑14 用の `(01)`、シリアル番号用の `(21)`。

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;

// GS1 data: (01) – GTIN‑14, (21) – serial number
string gs1Data = "(01)12345678901234(21)ABC123";

// Initialise the generator for MicroPDF417 (GS1 compatible)
BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MicroPdf417, gs1Data);
```

**重要なポイント:**  
`EncodeTypes.MicroPdf417` は、文字列に有効な AI が含まれている場合、自動的に入力を GS1 データとして扱います。これにより、追加設定なしで GS1 仕様に準拠したバーコードが生成されます。

## Step 2 – 最適なサイズのためにバーコード寸法を設定

バーコードの視覚的サイズは **X‑dimension**（1 モジュールの幅）で制御されます。`XDimension.Pixels` を調整することで、可読性を保ちつつ最終画像サイズを微調整できます。

```csharp
// Set the module width to 2 pixels – a good balance for screen and print
generator.Parameters.Barcode.XDimension.Pixels = 2;
```

> **バーコード PNG の生成方法** – X‑dimension はエンコードされるデータには影響せず、生成される画像の物理的寸法のみを変更します。高解像度印刷用に大きなバーコードが必要な場合は、この値を `3` や `4` などに増やしてください。

## Step 3 – バーコード PNG を生成し画像をエクスポート

これでバーコードを描画し、PNG ファイルとして書き出すことができます。`Save` メソッドは保存先パスと画像フォーマットを受け取ります。

```csharp
// Define the output folder (ensure it exists)
string outputFolder = Path.Combine(Environment.CurrentDirectory, "output");
Directory.CreateDirectory(outputFolder);

// Export the barcode image as PNG
string pngPath = Path.Combine(outputFolder, "GS1MicroPdf417.png");
generator.Save(pngPath, BarCodeImageFormat.Png);

Console.WriteLine($"Barcode image saved to: {pngPath}");
```

**内部で何が起きているか:**  
`BarcodeGenerator.Save` はバーコードをビットマップにラスタライズし、先ほど設定した X‑dimension を適用した上で PNG ファイルとしてエンコードします。生成されたファイルはウェブページに直接埋め込んだり、ラベルに印刷したり、PDF に組み込んだりできます。

## 完全なソースコード例

以下はコピー＆ペーストして実行できる、自己完結型のコンソール アプリケーションです。**バーコード PNG を生成**し、**バーコード画像をエクスポート**する方法を示すとともに、基本的なエラーハンドリングも含んでいます。

```csharp
using System;
using System.IO;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace Gs1BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            try
            {
                // 1️⃣ Initialise the barcode generator for GS1 MicroPDF417
                string gs1Data = "(01)12345678901234(21)ABC123";
                BarcodeGenerator generator = new BarcodeGenerator(
                    EncodeTypes.MicroPdf417, gs1Data);

                // 2️⃣ Adjust X‑dimension to control the visual size
                generator.Parameters.Barcode.XDimension.Pixels = 2;

                // 3️⃣ Prepare output folder
                string outputFolder = Path.Combine(
                    Environment.CurrentDirectory, "output");
                Directory.CreateDirectory(outputFolder);

                // 4️⃣ Save the barcode as PNG (export barcode image)
                string pngPath = Path.Combine(outputFolder, "GS1MicroPdf417.png");
                generator.Save(pngPath, BarCodeImageFormat.Png);

                Console.WriteLine($"✅ Barcode created and saved as PNG:");
                Console.WriteLine(pngPath);
            }
            catch (Exception ex)
            {
                Console.Error.WriteLine($"Error: {ex.Message}");
            }
        }
    }
}
```

### 期待される出力

プログラムを実行すると、次のような出力が表示されます。

```
✅ Barcode created and saved as PNG:
C:\Path\To\Your\App\output\GS1MicroPdf417.png
```

PNG ファイルを開くと、GTIN‑14 `12345678901234` とシリアル番号 `ABC123` をエンコードした **GS1 MicroPDF417** バーコードがはっきりと表示されます。GS1 対応スキャナで読み取れば、元のデータ文字列が返ります。

## よくある落とし穴とベストプラクティス

| 問題 | 発生理由 | 回避方法 |
|------|----------|----------|
| **AI の書式が正しくない** | 丸括弧が抜けている、または順序が間違っているとバーコードが GS1 にならない | 常に各 AI を丸括弧で囲む（例: `(01)`） |
| **X‑dimension が小さすぎる** | 低解像度デバイスでバーコードが読めなくなる | ほとんどのプリンタで `XDimension.Pixels` を 2 以上に保ち、高 DPI 出力時はさらに増やす |
| **出力フォルダが存在しない** | `Save` が `DirectoryNotFoundException` をスローする | `Save` を呼び出す前に `Directory.CreateDirectory` でフォルダを作成 |
| **間違った EncodeType を使用** | 例: `Code128` は GS1 データを自動でサポートしない | `EncodeTypes.MicroPdf417` など、GS1 対応のタイプを選択 |
| **NuGet 参照が不足** | `The type or namespace name 'Aspose' could not be found` などのコンパイルエラー | NuGet で `Aspose.BarCode` パッケージをインストール |

## サンプルの拡張例

* **別の画像形式** – `BarCodeImageFormat.Png` を `Jpeg`、`Gif`、`Bmp` に置き換えると別形式で保存可能です。
* **高解像度出力** – 保存前に `generator.Parameters.ImageResolution.DpiX` と `DpiY` を設定します。
* **PDF への埋め込み** – `Aspose.Pdf` を使用して PNG を PDF 請求書やラベルに配置できます。

## 結論

これで、Aspose.BarCode の `BarcodeGenerator` を使って C# で **GS1 バーコードを作成**し、**バーコード PNG を生成**、**画像をファイルシステムにエクスポート**する方法が分かりました。本ガイドは、GS1 データでジェネレータを初期化し、X‑dimension を調整し、最終 PNG を保存するまでの全手順を網羅し、一般的なエラーへの対処法と拡張アイデアも提供しています。

他の GS1 アプリケーション識別子や別のシンボル種別、あるいは高解像度画像に挑戦してみてください。これらの基本をマスターすれば、在庫管理、出荷、リテール向けの準拠バーコード生成は .NET ツールボックスの定番機能となります。

## 次に学ぶべきこと

以下のチュートリアルは、本ガイドで示した手法を基にした関連トピックを扱っています。各リソースには完全な動作コード例とステップバイステップの解説が含まれており、API の追加機能習得や代替実装アプローチの探求に役立ちます。

- [Create GS1 Barcode Images in C# – How to Generate Barcode C# Quickly](/barcode/english/net/gs1-barcode-encoding/create-gs1-barcode-images-in-c-how-to-generate-barcode-c-qui/)
- [Create barcode PNG in C# – step‑by‑step guide](/barcode/english/python-java/general/create-barcode-png-in-c-step-by-step-guide/)
- [Create barcode image in C# – complete programming guide](/barcode/english/python-java/general/create-barcode-image-in-c-complete-programming-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}