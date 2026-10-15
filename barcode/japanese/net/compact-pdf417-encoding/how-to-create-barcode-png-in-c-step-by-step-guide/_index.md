---
category: general
date: 2026-10-15
description: C#でコンパクトなPDF417の例を使用してバーコードPNGを作成 – 列の設定方法、サイズの調整、画像の生成方法を学びましょう。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode png
- how to create barcode
- how to set columns
- c# barcode example
language: ja
lastmod: 2026-10-15
og_description: C#でコンパクトなPDF417の例を使用してバーコードPNGを作成します。このガイドでは、列の設定、サイズの調整、画像の保存方法を示します。
og_image_alt: Screenshot showing a generated barcode PNG created with C#
og_title: C#でバーコードPNGを作成する – 完全プログラミングチュートリアル
schemas:
- author: Aspose
  dateModified: '2026-10-15'
  description: Create barcode PNG in C# with a compact PDF417 example – learn how
    to set columns, adjust dimensions, and generate the image.
  headline: How to create barcode PNG in C# – step‑by‑step guide
  type: TechArticle
- description: Create barcode PNG in C# with a compact PDF417 example – learn how
    to set columns, adjust dimensions, and generate the image.
  name: How to create barcode PNG in C# – step‑by‑step guide
  steps:
  - name: Initialise the barcode generator with the desired text
    text: '```csharp using Aspose.BarCode.Generation;'
  - name: Set the module (X) dimension in pixels
    text: '```csharp // Set the width of the smallest bar (module) to 2 pixels generator.Parameters.Barcode.XDimension.Pixels
      = 2; ```'
  - name: Define the number of columns for the PDF417 barcode
    text: '```csharp // Specify that the barcode should use 3 columns generator.Parameters.Barcode.Pdf417.Columns
      = 3; ```'
  - name: Enable the compact layout by truncating the barcode
    text: '```csharp // Truncate removes unnecessary empty rows, making the barcode
      shorter generator.Parameters.Barcode.Pdf417.Truncate = true; ```'
  - name: Save the barcode image as PNG
    text: '```csharp // Choose the output folder and file name string outputPath =
      Path.Combine(Environment.CurrentDirectory, "CompactPdf417.png");'
  - name: Full, runnable example
    text: 'Putting everything together, here is a self‑contained program you can copy,
      paste, and run:'
  type: HowTo
tags:
- barcode
- C#
- PDF417
- image generation
title: C#でバーコードPNGを作成する方法 – ステップバイステップガイド
url: /ja/net/compact-pdf417-encoding/how-to-create-barcode-png-in-c-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# C# でバーコード PNG を作成する方法 – ステップバイステップガイド

C# のコードから **バーコード PNG** ファイルを作成する必要がある場合、このチュートリアルでは数行のコードで完結する完全なソリューションをご紹介します。列数の設定、モジュールサイズの調整、コンパクトな PDF417 バーコードを PNG 画像として保存する方法を、シンプルで読みやすい例を通じて学べます。

プログラムでバーコードを生成すれば、グラフィックエディタで手作業で作成する手間が省け、請求書やチケット、在庫ラベルに直接埋め込むことができます。以下のセクションでは **バーコードの作成方法** 全般、各設定が重要な理由、さまざまなユースケースへのコードの適用方法を網羅します。

## 前提条件

開始する前に、以下が揃っていることを確認してください。

* .NET 6.0 以降（コードは .NET Framework 4.7+ でも動作します）
* PDF417 をサポートするバーコードライブラリへの参照（例: **Aspose.BarCode for .NET** または **IronBarcode**）。本例では Aspose.BarCode を使用します。NuGet からインストールできます:

```bash
dotnet add package Aspose.BarCode
```

* C# の基本構文と Visual Studio（またはお好みの IDE）に慣れていること

> **プロのコツ:** 無料の代替としてオープンソースの **ZXing.Net** ライブラリも PDF417 をサポートしていますが、プロパティ名が若干異なります。ここで示す概念は同じです。

## C# でバーコード PNG を作成する方法（メインステップ）

ソリューションの核心は PDF417 エンコード用に設定された `BarcodeGenerator` オブジェクトです。以下のセクションでコードの各行を分解し、**列数の設定方法** を説明し、設定が最終 PNG のサイズに与える影響を示します。

### 手順 1: 目的のテキストでバーコードジェネレータを初期化

```csharp
using Aspose.BarCode.Generation;

// The text you want to encode in the barcode
string barcodeText = "Compact example";

// Create a generator for PDF417 barcodes
using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, barcodeText))
{
    // Subsequent configuration goes here
}
```

*重要性*: `EncodeTypes.Pdf417` 列挙体は、ライブラリに 2 次元スタック型バーコードを生成させます。コンストラクタはエンコードしたいデータも受け取るため、別途 `SetData` を呼び出す必要がありません。

### 手順 2: ピクセル単位でモジュール（X）サイズを設定

```csharp
// Set the width of the smallest bar (module) to 2 pixels
generator.Parameters.Barcode.XDimension.Pixels = 2;
```

**X 次元** はバーコードの視覚的密度を制御します。値が小さいほど画像がタイトになり、モバイル画面や印刷スペースが限られた環境でコンパクトな PNG が必要なときに有用です。

### 手順 3: PDF417 バーコードの列数を定義

```csharp
// Specify that the barcode should use 3 columns
generator.Parameters.Barcode.Pdf417.Columns = 3;
```

この行は **列数の設定方法** を示しています。PDF417 は自動で最適な列数を選択できますが、明示的に設定すれば幅が予測可能になり、固定サイズのレイアウトに PNG を埋め込む際に便利です。

### 手順 4: バーコードをトランケートしてコンパクトレイアウトを有効化

```csharp
// Truncate removes unnecessary empty rows, making the barcode shorter
generator.Parameters.Barcode.Pdf417.Truncate = true;
```

`Truncate` を true にすると、データが含まれない末尾の行が除去され、画像の全体高さが削減されますが情報は失われません。

### 手順 5: バーコード画像を PNG として保存

```csharp
// Choose the output folder and file name
string outputPath = Path.Combine(Environment.CurrentDirectory, "CompactPdf417.png");

// Save the generated barcode as a PNG file
generator.Save(outputPath, BarCodeImageFormat.Png);
```

`Save` メソッドは指定した形式でバーコードをディスクに書き出します。PNG はロスレス形式で、エッジ検出が正確に必要なスキャンアプリケーションに最適です。

### 完全な実行可能サンプル

すべてをまとめた自己完結型プログラムは以下の通りです。コピーして貼り付け、実行できます。

```csharp
using System;
using System.IO;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // 1️⃣ Initialise the generator with the data to encode
        string barcodeText = "Compact example";

        using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, barcodeText))
        {
            // 2️⃣ Set module width to 2 pixels for a tighter image
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // 3️⃣ Explicitly set the number of columns (how to set columns)
            generator.Parameters.Barcode.Pdf417.Columns = 3;

            // 4️⃣ Enable compact layout by truncating empty rows
            generator.Parameters.Barcode.Pdf417.Truncate = true;

            // 5️⃣ Define the output path and save as PNG (create barcode PNG)
            string outputPath = Path.Combine(Directory.GetCurrentDirectory(), "CompactPdf417.png");
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"Barcode PNG saved to: {outputPath}");
        }
    }
}
```

**期待される出力** – プログラム実行後、実行フォルダーに `CompactPdf417.png` が生成されます。この画像は 3 列の PDF417 バーコードを含み、標準的な 2 × 2 cm ラベルに収まるほどコンパクトでありながら、完全にスキャン可能です。

![バーコード PNG 作成例](placeholder.png){alt="C# を使用したバーコード PNG の作成"}

## データサイズ別の列数設定方法（サブキーワード）

列数は幅と可読性の両方に影響します。

| 列数 | おおよその幅 (px) | 主なユースケース |
|------|-------------------|------------------|
| 1‑2  | 細長く高い        | 小さなタグ、RFID ライク印刷 |
| 3‑5  | バランスが取れた   | 汎用ラベル |
| 6‑9  | 幅広く短い        | 大判ポスターやパッケージ |

データ文字列が長くなると、ライブラリは列数の上限内で高さを保つために自動で行数を増やします。ただし、列数を低すぎる値に固定するとバーコードが過度に高くなり、レシートプリンターに収まらなくなる可能性があります。出力媒体の物理的制約に合わせて列数を調整してください。

## 他フォーマットでバーコード画像を作成する方法（サブキーワード）

PNG がウェブやモバイルで最も一般的ですが、JPEG、BMP、SVG などの形式が必要になるケースもあります。

```csharp
// Save as JPEG with 90 % quality
generator.Save("CompactPdf417.jpg", BarCodeImageFormat.Jpeg, 90);

// Save as SVG (vector, infinite scaling)
generator.Save("CompactPdf417.svg", BarCodeImageFormat.Svg);
```

フォーマット選択は下流の利用者に依存します。

* **PNG** – ロスレス、スキャナに最適
* **JPEG** – ファイルサイズが小さく、軽度の圧縮アーティファクトが許容できる場合に有用
* **SVG** – 高解像度印刷や UI のスケーリングに最適

## C# バーコード例：エラー処理とエッジケースへの対応

堅牢な **C# バーコード例** は実行時の問題を予測しておく必要があります。

```csharp
try
{
    // All configuration steps as shown earlier
    generator.Save(outputPath, BarCodeImageFormat.Png);
}
catch (ArgumentException ex)
{
    Console.Error.WriteLine($"Invalid barcode parameter: {ex.Message}");
}
catch (IOException ex)
{
    Console.Error.WriteLine($"Failed to write file: {ex.Message}");
}
```

*`try/catch` でラップする理由*：テキストに無効な文字が含まれる、サポート外のサイズ指定、書き込み権限の問題などで例外がスローされます。これらを適切に処理すれば、バッチ処理中にアプリがクラッシュするのを防げます。

## 拡張例：ロゴや背景を追加する

実務ではロゴのオーバーレイやカラー背景が求められることがあります。Aspose.BarCode API ではバーコードとビットマップを組み合わせられます。

```csharp
// Load a logo image
using (Bitmap logo = (Bitmap)Image.FromFile("logo.png"))
{
    generator.Parameters.Barcode.ImageFormat = BarCodeImageFormat.Png;
    generator.Parameters.Barcode.Pdf417.EnablePdf417CodewordCount = true; // optional

    // Merge the logo with the barcode (centered)
    generator.Save("BarcodeWithLogo.png", BarCodeImageFormat.Png, logo);
}
```

この手法により **バーコード PNG の作成** ワークフローを保ちつつ、最終画像にブランド要素を加えることができます。

## まとめ

本ガイドでは、コンパクトな PDF417 設定を用いて C# で **バーコード PNG** を作成する方法を実演しました。学んだことは以下の通りです。

* `BarcodeGenerator` の初期化に必要な正確なコード
* **列数の設定方法** と列数がサイズ・可読性に与える影響
* X 次元の調整とトランケーションで PNG をタイトにする方法
* PNG、JPEG、SVG での保存手順
* 本番環境向け **C# バーコード例** のエラーハンドリングパターン
* ロゴオーバーレイや背景カスタマイズといったオプション拡張

これで、請求書ジェネレータ、チケットシステム、在庫管理ツールなどに組み込める実行可能なスニペットが手に入りました。列数、モジュールサイズ、バーコード種別（例: QR、Code128）を変えて、画像がどのように変化するか試してみてください。

## 次のステップ

* 他のエンコードタイプ（`EncodeTypes.QR`、`EncodeTypes.Code128`）を調査し、ユースケースを拡大する
* バーコード生成と PDF 作成ライブラリ（例: **iTextSharp**）を組み合わせ、PNG を文書に直接埋め込む
* 動的サイズ計算：入力文字列の長さとラベル寸法に基づき最適な列数を算出する

コーディングを楽しみながら、C# で鮮明なバーコード PNG をプログラム的に生成するシンプルさを体感してください！

## 次に学ぶべきこと

以下のチュートリアルは、本ガイドで示した技術を踏まえてさらに深く学べる関連トピックです。各リソースには完全な動作コード例とステップバイステップの解説が含まれており、API の追加機能や代替実装アプローチを自分のプロジェクトで試すのに役立ちます。

- [How to create PDF417 barcode and save it as PNG in C#](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-and-save-it-as-png-in-c/)
- [How to create PDF417 barcode and set its size in C#](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-and-set-its-size-in-c/)
- [How to create PDF417 barcode in C# with compact mode](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-in-c-with-compact-mode/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}