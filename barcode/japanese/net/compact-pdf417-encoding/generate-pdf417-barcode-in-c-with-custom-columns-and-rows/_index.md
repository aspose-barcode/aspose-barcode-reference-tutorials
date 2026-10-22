---
category: general
date: 2026-10-21
description: C#でpdf417バーコードを素早く生成する。カスタムレイアウト、列、行、PNG出力でpdf417バーコードを生成する方法を学びましょう。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate pdf417 barcode
- how to generate pdf417 barcode
- pdf417 barcode layout
- barcode generator C#
- save barcode as PNG
language: ja
lastmod: 2026-10-21
og_description: C#でPDF417バーコードを生成する。このチュートリアルでは、カスタム列や行、PNG出力でPDF417バーコードを生成する方法を学べます。
og_image_alt: Screenshot showing a generated PDF417 barcode saved as a PNG file
og_title: C#でPDF417バーコードを生成する – 完全ステップバイステップガイド
schemas:
- author: Aspose
  dateModified: '2026-10-21'
  description: Generate pdf417 barcode quickly in C#. Learn how to generate pdf417
    barcode with custom layout, columns, rows, and PNG output.
  headline: Generate pdf417 barcode in C# with custom columns and rows
  type: TechArticle
- description: Generate pdf417 barcode quickly in C#. Learn how to generate pdf417
    barcode with custom layout, columns, rows, and PNG output.
  name: Generate pdf417 barcode in C# with custom columns and rows
  steps:
  - name: Open the PNG file in any image viewer.
    text: Open the PNG file in any image viewer.
  - name: Use a free PDF417 scanner app (e.g., ZXing, PDF417 Decoder) to scan the
      image.
    text: Use a free PDF417 scanner app (e.g., ZXing, PDF417 Decoder) to scan the
      image.
  - name: Confirm that the decoded text matches the original input.
    text: Confirm that the decoded text matches the original input.
  type: HowTo
tags:
- barcode
- pdf417
- C#
- image generation
title: C#でカスタム列と行を使用してPDF417バーコードを生成する
url: /ja/net/compact-pdf417-encoding/generate-pdf417-barcode-in-c-with-custom-columns-and-rows/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# C#でpdf417バーコードを生成する – 完全プログラミングガイド

.NET アプリケーションで **pdf417 バーコードを生成** する必要がある場合、このガイドでは数行のコードで実装する方法を示します。列数と行数を設定し、結果を PNG 画像として保存する実用的な例を紹介します。同じ手法は任意のテキストのエンコードに利用できるため、請求書、チケット、ID カードなどに応用できます。

**pdf417 バーコード** の生成は、他のコードベースとは別個の作業のように感じられることがあります。このチュートリアルの最後までに、レイアウトパラメータが重要な理由、画像品質の制御方法、そして **pdf417 バーコードを確実に生成** するために必要なライブラリ呼び出しを理解できるようになります。

## 必要なもの

* .NET 6.0 SDK 以降がインストールされていること  
* C# 対応の IDE（Visual Studio、VS Code、Rider など）  
* **Aspose.BarCode for .NET** NuGet パッケージ（または互換性のあるバーコードライブラリ）  

以下のコマンドでライブラリを追加できます:

```bash
dotnet add package Aspose.BarCode
```

このライブラリは、本チュートリアル全体で使用する `BarcodeGenerator` クラスを提供します。

## 手順 1: バーコードジェネレータのインスタンスを作成

最初の行は **pdf417 バーコードを生成** できるオブジェクトを作成します。エンコードタイプ（`EncodeTypes.Pdf417`）とエンコードしたいテキストを指定する必要があります。

```csharp
using Aspose.BarCode.Generation;

BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Sample Text");
```

*このステップが重要な理由* – `BarcodeGenerator` はバーコードのすべての設定をカプセル化します。正しい `EncodeTypes` でインスタンス化することで、エンジンに QR や Code128 などではなく PDF417 シンボロジーを使用させます。

## 手順 2: PDF417 レイアウトを設定

PDF417 では列数と行数を制御でき、これがバーコードのサイズと密度に直接影響します。これらの値を調整することが、カスタムレイアウトで **pdf417 バーコードを生成する方法** の核心です。

```csharp
// Set the number of data columns (valid range: 2‑30)
generator.Parameters.Barcode.Pdf417.Columns = 4;

// Set the number of rows (up to 90 rows)
generator.Parameters.Barcode.Pdf417.Rows = 9;
```

*これらの値を変更する理由* – 列数を増やすとバーコードの高さが減少し、行数を増やすと幅が広がります。対象のスキャナーデバイスや印刷可能領域に合わせて値を選択してください。

> **プロのコツ:** 行数を省略すると、ライブラリはデータ長に基づいて最適な行数を自動的に計算します。UI レイアウトで固定画像サイズが必要な場合は、行数を明示的に設定すると便利です。

## 手順 3: 画像フォーマットを選択しファイルを保存

レイアウトを設定した後、バーコードを画像としてレンダリングできます。以下の例ではバーコードを PNG ファイルとして保存しますが、JPEG、BMP、TIFF も選択可能です。

```csharp
using Aspose.BarCode;
using System.IO;

// Define the output path – replace with your actual directory
string outputPath = Path.Combine("C:\\Barcodes", "CustomLayout.png");

// Save the barcode image as PNG
generator.Save(outputPath, BarCodeImageFormat.Png);
```

コードを実行すると、`CustomLayout.png` に指定した列/行設定に合わせた鮮明な **pdf417 バーコード** が保存されます。

### 期待される出力

`CustomLayout.png` を開くと、4 列 9 行の長方形バーコードが表示されます。任意の PDF417 リーダーで画像をスキャンすると、元のテキスト **“Sample Text”** が取得されます。

![Generated PDF417 barcode example](generated-pdf417.png){: .center-image alt="PNG ファイルとして保存された生成された pdf417 バーコード"}

## 手順 4: 完全な実行可能サンプル

以下は、すべての要素を組み合わせた単体のコンソールアプリケーションです。コードを新しい `.csproj` プロジェクトにコピーして実行してください。追加のファイルは不要です。

```csharp
using System;
using System.IO;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace Pdf417Demo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Create the generator with the desired text
            BarcodeGenerator generator = new BarcodeGenerator(
                EncodeTypes.Pdf417,
                "Sample Text for PDF417 barcode");

            // 2️⃣ Configure layout – custom columns and rows
            generator.Parameters.Barcode.Pdf417.Columns = 4; // 2‑30
            generator.Parameters.Barcode.Pdf417.Rows = 9;    // up to 90

            // Optional: increase image resolution for sharper output
            generator.Parameters.ImageResolution = 300; // DPI

            // 3️⃣ Define the output location
            string folder = Path.Combine(Environment.CurrentDirectory, "output");
            Directory.CreateDirectory(folder);
            string filePath = Path.Combine(folder, "CustomLayout.png");

            // 4️⃣ Save as PNG
            generator.Save(filePath, BarCodeImageFormat.Png);

            Console.WriteLine($"PDF417 barcode generated at: {filePath}");
        }
    }
}
```

プログラムを実行すると確認メッセージが出力され、`output` サブフォルダーに PNG ファイルが作成されます。この画像はレポートに埋め込んだり、ラベルに印刷したり、モバイルデバイスへ送信してスキャンに利用できます。

## 一般的なバリエーションとエッジケース

| シナリオ | 変更点 | 重要な理由 |
|----------|----------------|----------------|
| **長い文字列をエンコード** | `Rows` を増やすか、`Rows` の代入を省略してライブラリに自動計算させます | PDF417 は最大 1,850 文字まで保持可能です。行数が不足すると切り捨てが発生します |
| **高い視覚品質** | `generator.Parameters.ImageResolution` を 600 DPI に設定します | 高解像度プリンターでの印刷に有用です |
| **異なる画像フォーマット** | `BarCodeImageFormat.Png` を `Jpeg` または `Tiff` に置き換えます | JPEG はファイルサイズを削減し、TIFF はアーカイブ用にロスレスデータを保持します |
| **静かな領域（クワイエットゾーン）を追加** | `generator.Parameters.Barcode.XDimension = 2;`（または `Margins` を調整） | クワイエットゾーンはノイズの多い環境でスキャナーの信頼性を向上させます |
| **ユーザー入力からの動的テキスト** | ハードコードされた文字列を `Console.ReadLine()` に置き換えます | ユーザーデータに基づく実行時生成が可能になります |

### Web API で pdf417 バーコードを生成する方法

ASP.NET Core エンドポイントでバーコード生成機能を提供する必要がある場合、画像をバイト配列として返します:

```csharp
[HttpGet("api/barcode/pdf417")]
public IActionResult GetPdf417([FromQuery] string data)
{
    var generator = new BarcodeGenerator(EncodeTypes.Pdf417, data);
    generator.Parameters.Barcode.Pdf417.Columns = 5;
    generator.Parameters.Barcode.Pdf417.Rows = 10;

    using var ms = new MemoryStream();
    generator.Save(ms, BarCodeImageFormat.Png);
    return File(ms.ToArray(), "image/png");
}
```

このスニペットは、ディスクに書き込まずに **pdf417 バーコードをオンザフライで生成** する方法を示しており、マイクロサービスやモバイルバックエンドに最適です。

## 生成されたバーコードのテスト

バーコードが正しく作成されたことを確認するには:

1. 任意の画像ビューアで PNG ファイルを開く。  
2. 無料の PDF417 スキャナーアプリ（例: ZXing、PDF417 Decoder）で画像をスキャンする。  
3. デコードされたテキストが元の入力と一致することを確認する。

スキャナーがエラーを報告した場合、列/行の値を再確認し、画像解像度がデバイスに対して十分に高いか確認してください。

## 結論

これで、C# で列、行、出力フォーマットを完全に制御しながら **pdf417 バーコードを生成** する方法がわかりました。完全なサンプルは `BarcodeGenerator` の作成から PNG ファイルの保存までの全工程を示しているため、任意の .NET プロジェクトにバーコード作成機能を組み込むことができます。

次に、**pdf417 バーコードレイアウト** の最適化や PDF レポートへの埋め込み、モバイルデバイスでのバーコードデコードなどの関連トピックを探求してください。誤り訂正レベルの調整や画像解像度の変更を試すことで、特定のユースケースに合わせてソリューションを微調整できます。コーディングを楽しんでください！

## 次に学ぶべきことは？

以下のチュートリアルは、本ガイドで示した手法を基にした密接に関連するトピックを扱っています。各リソースには、ステップバイステップの解説付きの完全な動作コード例が含まれており、追加の API 機能を習得し、独自プロジェクトで代替実装アプローチを検討するのに役立ちます。

- [C#でPDF417バーコードを生成する方法 – ステップバイステップガイド](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-step-by-step-guide/)
- [C#でバーコードを保存する方法 – PDF417バーコードの生成](/barcode/english/net/compact-pdf417-encoding/how-to-save-barcode-in-c-generate-pdf417-barcodes/)
- [PDF417バーコードの生成方法 – 完全プログラミングガイド](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-complete-programming-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}