---
category: general
date: 2026-08-19
description: C#でPDF417バーコードを素早く生成する。コンパクトモードとカスタム設定を使用して、Aspose.BarCodeでC#のPDF417バーコード生成方法を学びましょう。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate pdf417 barcode
- how to generate pdf417 barcode c#
- Aspose.BarCode PDF417
- compact PDF417 barcode
- barcode X‑dimension
language: ja
lastmod: 2026-08-19
og_description: Aspose.BarCode を使用して C# で PDF417 バーコードを生成します。このチュートリアルでは、コンパクトモードで
  PDF417 バーコードを C# で生成し、X 軸寸法を設定し、PNG として保存する方法を示します。
og_image_alt: Screenshot of a compact PDF417 barcode saved as PNG
og_title: C#でPDF417バーコードを生成する – ステップバイステップガイド
schemas:
- author: Aspose
  dateModified: '2026-08-19'
  description: Generate PDF417 barcode in C# quickly. Learn how to generate PDF417
    barcode C# using Aspose.BarCode with compact mode and custom settings.
  headline: Generate PDF417 barcode in C# – complete guide with compact layout
  type: TechArticle
- description: Generate PDF417 barcode in C# quickly. Learn how to generate PDF417
    barcode C# using Aspose.BarCode with compact mode and custom settings.
  name: Generate PDF417 barcode in C# – complete guide with compact layout
  steps:
  - name: Why each line matters
    text: '* **`EncodeTypes.Pdf417`** – selects the PDF417 symbology, which supports
      up to ~1.1 KB of data. * **`XDimension.Pixels = 2`** – sets the basic bar width.
      Smaller values make the barcode thinner; larger values improve readability on
      low‑resolution devices. * **`Pdf417.Columns = 3`** – limits the num'
  - name: 4️⃣ Generate a high‑density PDF417 for printing
    text: 'If you need a barcode that fits on a small label, increase the column count
      and lower the X‑dimension:'
  - name: 5️⃣ Change the output format to SVG for vector scaling
    text: '```csharp generator.Save("CompactPdf417.svg", BarCodeImageFormat.Svg);
      ```'
  - name: 6️⃣ Encode binary data (e.g., a byte array)
    text: 'If you need to embed binary payloads, convert them to a Base64 string first:'
  type: HowTo
tags:
- barcode
- C#
- Aspose
title: C#でPDF417バーコードを生成する – コンパクトレイアウトの完全ガイド
url: /ja/net/compact-pdf417-encoding/generate-pdf417-barcode-in-c-complete-guide-with-compact-lay/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# C# で PDF417 バーコードを生成する – 完全ガイド

.NET アプリケーションで **PDF417 バーコードを生成** する必要がある場合、このチュートリアルで手順をすべて解説します。コンパクトな PDF417 バーコードを作成し、X‑ディメンションをカスタマイズし、PNG 画像として保存する、実用的で本番環境向けのサンプルをご覧いただけます。

PDF417 バーコードの生成は、チケット情報、出荷明細、身分証明書など大量のデータを機械可読形式でエンコードする必要があるときに一般的です。Aspose.BarCode を使用すれば手順はシンプルで、コードは .NET 6+ または .NET Framework 4.7.2 以降で動作します。

このガイドで学べること:

* Aspose.BarCode NuGet パッケージをインストールする方法。
* 列数を少なくし、コンパクト（トランケート）モードで **PDF417 バーコードを生成** する自己完結型 C# プログラムの作成。
* 鮮明な描画のためにバー幅（X‑ディメンション）を調整する方法。
* バーコードを PNG ファイルとして保存する手順。
* バリエーション、エッジケース、ベストプラクティスのヒントを紹介。

## 前提条件

開始する前に、以下を確認してください:

* Visual Studio 2022（または任意の C# IDE）に .NET 6 SDK がインストールされていること。
* **Aspose.BarCode** NuGet パッケージをダウンロードできるインターネット接続。
* PNG ファイルを保存するフォルダーへの書き込み権限。

追加のライブラリは不要です。Aspose.BarCode が画像エンコードを内部で処理します。

## 手順 1: Aspose.BarCode パッケージを追加する

Visual Studio でプロジェクトを開き、ソリューションを右クリックして **Manage NuGet Packages** を選択します。`Aspose.BarCode` を検索し、最新の安定版をインストールします。

```bash
dotnet add package Aspose.BarCode
```

> **プロのコツ:** パッケージは常に最新に保ちましょう。新しいリリースにはパフォーマンス向上や最新 .NET ランタイムへの対応が含まれることが多いです。

## 手順 2: 最小限のコンソール アプリケーションを作成する

まだプロジェクトがない場合は、新しい C# コンソール プロジェクトを作成します:

```bash
dotnet new console -n Pdf417Demo
cd Pdf417Demo
```

`Program.cs` の内容を以下の完全なサンプルに置き換えてください。このプログラムは **C# で PDF417 バーコードを生成** する手順を最初から最後まで示しています。

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode.BarCodeImageFormat;

namespace Pdf417Demo
{
    class Program
    {
        static void Main(string[] args)
        {
            // -----------------------------------------------------------------
            // 1️⃣  Define the data you want to encode.
            // -----------------------------------------------------------------
            // The string can contain Unicode characters; Aspose.BarCode handles
            // encoding automatically. Here we use characters with diacritics to
            // prove Unicode support.
            string data = "Åspóse.Barcóde©";

            // -----------------------------------------------------------------
            // 2️⃣  Initialise the BarcodeGenerator for PDF417.
            // -----------------------------------------------------------------
            // EncodeTypes.Pdf417 tells the library which symbology to use.
            // The constructor also accepts the data to encode.
            BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, data);

            // -----------------------------------------------------------------
            // 3️⃣  Configure visual parameters.
            // -----------------------------------------------------------------
            // • XDimension controls the bar width in pixels. A value of 2 gives
            //   a clear, readable barcode on most screens.
            // • Columns define how many data columns the barcode will use.
            //   Fewer columns produce a more compact image but increase the
            //   number of rows.
            // • Truncate enables “compact mode”, which removes the trailing
            //   stop pattern and reduces the overall size.
            generator.Parameters.Barcode.XDimension.Pixels = 2;
            generator.Parameters.Barcode.Pdf417.Columns = 3;
            generator.Parameters.Barcode.Pdf417.Truncate = true; // compact mode

            // -----------------------------------------------------------------
            // 4️⃣  Choose the output format and save the image.
            // -----------------------------------------------------------------
            // BarCodeImageFormat.Png yields a lossless PNG file that works
            // well for web, print, and further image processing.
            string outputPath = "CompactPdf417.png";
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"PDF417 barcode saved to: {outputPath}");
        }
    }
}
```

### 各行の重要ポイント

* **`EncodeTypes.Pdf417`** – PDF417 シンボルを選択します。最大約 1.1 KB のデータをエンコード可能です。
* **`XDimension.Pixels = 2`** – 基本的なバー幅を設定します。値が小さいほどバーコードは細くなり、値が大きいほど低解像度デバイスでの可読性が向上します。
* **`Pdf417.Columns = 3`** – 列数を制限し、行数を増やすことで、縦長で横幅が狭いバーコードになります。
* **`Pdf417.Truncate = true`** – コンパクトモードを有効にし、ストップパターンを除去して画像サイズを縮小します（データの完全性は保持）。
* **`Save(..., BarCodeImageFormat.Png)`** – PNG ファイルとして保存します。必要に応じて `Jpeg`、`Bmp`、`Svg` も選択可能です。

プログラムを実行します:

```bash
dotnet run
```

コンソールにファイルの場所が表示され、フォルダー内に `CompactPdf417.png` が生成されます。PNG を開くと、Unicode 文字列をエンコードしたクリアでコンパクトな PDF417 バーコードが確認できます。

## 手順 3: バーコードを検証する（任意だが推奨）

バーコードが正しく読み取れるか確認するには、スマートフォンの標準 PDF417 スキャナーアプリやデスクトップ向けデコーダーライブラリを使用してください。エンコードされたテキストは元の `data` 文字列と完全に一致するはずです（特殊文字も含む）。

デコードに問題がある場合は以下を試してください:

* `XDimension` を 3 または 4 ピクセルに増やす。
* 列数を減らす（例: `Columns = 2`）。
* `Truncate` を無効にする（`Truncate = false`）ことでストップパターンを追加。

これらの調整はサイズと可読性のトレードオフで、低解像度のプリンターやスキャナーに有効です。

## 手順 4: 一般的なバリエーションを探る

### 4️⃣ 印刷用の高密度 PDF417 を生成する

小さなラベルに収める必要がある場合は、列数を増やし X‑ディメンションを下げます:

```csharp
generator.Parameters.Barcode.XDimension.Pixels = 1;
generator.Parameters.Barcode.Pdf417.Columns = 6;
generator.Parameters.Barcode.Pdf417.Truncate = false; // keep full pattern
```

### 5️⃣ ベクトル拡大のために出力形式を SVG に変更する

```csharp
generator.Save("CompactPdf417.svg", BarCodeImageFormat.Svg);
```

SVG 出力は品質を失うことなく拡大できるため、レスポンシブなウェブページに最適です。

### 6️⃣ バイナリ データをエンコードする（例: バイト配列）

バイナリ ペイロードを埋め込む場合は、まず Base64 文字列に変換します:

```csharp
byte[] payload = new byte[] { 0x01, 0xFF, 0xA5 };
string base64 = Convert.ToBase64String(payload);
generator = new BarcodeGenerator(EncodeTypes.Pdf417, base64);
```

これでバーコードはバイナリ情報を保持し、デコーダー側で Base64 デコードを行う必要があります。

## よくある質問

| 質問 | 回答 |
|----------|--------|
| **Aspose を使わずに PDF417 を生成できますか？** | はい、ZXing.Net や Dynamsoft など他のライブラリもありますが、Aspose.BarCode は列数やトランケーションなどのレイアウト制御が豊富で、Unicode の取り扱いも優れています。 |
| **最大データ長はどれくらいですか？** | PDF417 は最大 1,108 バイト（約 1 KB）のバイナリ データをエンコードできます。これを超える場合は、複数のバーコードに分割することを検討してください。 |
| **コンパクトモードは規格に準拠していますか？** | トランケートされた PDF417 は ISO/IEC 15438 仕様の一部で、広くサポートされていますが、対象のスキャナーが明示的に対応しているか確認してください。 |
| **背景色を変更するには？** | 保存前に `generator.Parameters.Barcode.BackColor = System.Drawing.Color.White;` と `generator.Parameters.Barcode.ForeColor = System.Drawing.Color.Black;` を設定します。 |

## 結論

Aspose.BarCode を使用して **C# で PDF417 バーコードを生成** し、X‑ディメンションの微調整、コンパクトモードの有効化、PNG 画像へのエクスポート方法を習得しました。完全に実行可能なサンプルは任意の .NET プロジェクトにコピーでき、示したバリエーションを活用すれば、印刷、ウェブ、バイナリ ペイロード向けにバーコードを柔軟に適応できます。

次に検討できるステップ:

* バーコード生成を ASP.NET Core API に統合し、リクエストに応じて画像を返す。
* 同じラベル上に PDF417 と QR コードを組み合わせ、デュアルフォーマットスキャンを実現する。
* Aspose.BarCode の `Reader` クラスを使って生成画像をプログラム上でデコードし、データを自動検証する。

コーディングを楽しみながら、**PDF417 バーコード生成** ソリューションがもたらす柔軟性を活用してください！

## 次に学ぶべきことは？

以下のチュートリアルは、本ガイドで示したテクニックを基に、さらに関連するトピックを深く掘り下げたものです。各リソースには、ステップバイステップの解説と完全なコード例が含まれています。

- [バーコードの作成方法 – Aspose.BarCode を使用したコンパクト PDF417](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [Aspose.BarCode を使用した補足スペース カスタマイズ付きバーコード画像の生成方法](/barcode/english/net/supplemental-barcode-data/supplemental-barcode-space-customization/)
- [.NET 用 Aspose.BarCode でカスタムアスペクト比の Aztec バーコードを生成する方法](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}