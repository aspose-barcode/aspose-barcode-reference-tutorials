---
category: general
date: 2026-11-14
description: C#でPDF417バーコードをすばやく作成する方法を学びましょう。このガイドでは、PDF417の生成方法と、正確な制御のためにPDF417設定をカスタマイズする方法も示しています。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create pdf417 barcode
- how to generate pdf417
- how to customize pdf417
language: ja
lastmod: 2026-11-14
og_description: ステップバイステップの手順でC#でPDF417バーコードを作成します。PDF417の生成方法と、正確な結果を得るためのPDF417パラメータのカスタマイズ方法を学びましょう。
og_image_alt: Screenshot showing a generated PDF417 barcode created with C# code
og_title: C#でPDF417バーコードを作成する – カスタムレイアウト付き完全ガイド
schemas:
- author: Aspose
  dateModified: '2026-11-14'
  description: Learn how to create PDF417 barcode in C# quickly. This guide also shows
    how to generate PDF417 and how to customize PDF417 settings for precise control.
  headline: How to create PDF417 barcode with custom layout in C#
  type: TechArticle
- description: Learn how to create PDF417 barcode in C# quickly. This guide also shows
    how to generate PDF417 and how to customize PDF417 settings for precise control.
  name: How to create PDF417 barcode with custom layout in C#
  steps:
  - name: '**Check dimensions:** Ensure columns/rows stay within the allowed range.'
    text: '**Check dimensions:** Ensure columns/rows stay within the allowed range.'
  - name: '**Adjust error level:** Increase `ErrorLevel` for damaged media.'
    text: '**Adjust error level:** Increase `ErrorLevel` for damaged media.'
  - name: '**Review image quality:** Save with a higher DPI (`generator.Save(outputPath,
      BarCodeImageFormat.Png, 300)`) if you plan to print.'
    text: '**Review image quality:** Save with a higher DPI (`generator.Save(outputPath,
      BarCodeImageFormat.Png, 300)`) if you plan to print.'
  type: HowTo
tags:
- barcode
- pdf417
- C#
title: C#でカスタムレイアウトのPDF417バーコードを作成する方法
url: /ja/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-with-custom-layout-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# C# でカスタムレイアウトの PDF417 バーコードを作成する方法

チケットシステム、在庫タグ、モバイルアプリのスキャン用に **pdf417 バーコードを作成** する必要がある場合、このチュートリアルで全工程を解説します。PDF417 を素早く生成する方法と、列や行などの設定をカスタマイズしてデザイン制約に合わせる方法が分かります。

バーコード生成には複雑なグラフィックライブラリは不要です—Aspose.BarCode for .NET（または互換 API）だけで済みます。このガイドの最後までに、PNG ファイルが作成でき、PDF やウェブページに埋め込んだり、アプリから直接印刷したりできるようになります。

## 前提条件

- .NET 6.0 以降（コードは .NET Framework 4.7+ でも動作します）
- Aspose.BarCode for .NET（NuGet パッケージ `Aspose.BarCode`）
- C# と Visual Studio（または任意の IDE）に関する基本的な知識

> **プロのヒント:** CI/CD パイプラインを使用している場合は、プロジェクトファイルに NuGet パッケージ参照を追加して、ビルドの再現性を保ちましょう。

## ステップ 1: バーコードライブラリをインストールする

ターミナルでプロジェクトフォルダーを開き、次のコマンドを実行します:

```bash
dotnet add package Aspose.BarCode
```

このパッケージには、本チュートリアル全体で使用する `BarcodeGenerator` クラスが含まれています。追加のネイティブ依存関係は不要です。

## ステップ 2: 基本的な PDF417 バーコードを作成する

最初の目標は、デフォルト設定で **pdf417 バーコードを作成** することです。以下のプログラムはジェネレーターを設定し、サンプル文字列をエンコードし、結果を PNG 画像として保存します。

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Pdf417Demo
{
    static void Main()
    {
        // Step 2.1: Initialise the generator for PDF417 with the desired text
        BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Sample text for PDF417");

        // Step 2.2: Save the barcode as PNG
        string outputPath = "Pdf417Default.png";
        generator.Save(outputPath, BarCodeImageFormat.Png);

        Console.WriteLine($"Barcode saved to {outputPath}");
    }
}
```

**なぜこれが機能するのか:**  
`EncodeTypes.Pdf417` がライブラリに PDF417 シンボルを使用するよう指示します。コンストラクターは自動的にデフォルトの列/行値で `Barcode` オブジェクトを作成し、ほとんどのユースケースでスキャン可能な状態を保証します。

プログラムを実行します (`dotnet run`)。プロジェクトフォルダーに `Pdf417Default.png` が生成されます。画像を開くと、スキャン可能な標準的な PDF417 バーコードが表示されます。

![Create PDF417 barcode example](https://example.com/images/pdf417-default.png){:alt="デフォルトレイアウトを示す PDF417 バーコード作成例"}

## ステップ 3: カスタム寸法で PDF417 を生成する方法

固定サイズのラベルや UI コンポーネントで特定のバーコード領域が必要になることがあります。そのような場合、カスタム列と行で **pdf417 を生成する方法** が重要になります。

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Pdf417CustomDemo
{
    static void Main()
    {
        // Initialise generator with the same text
        BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Custom layout text");

        // ---- Customization begins here ----
        // Set the number of columns (2‑30). Fewer columns make the barcode taller.
        generator.Parameters.Barcode.Pdf417.Columns = 4;

        // Set the number of rows (1‑90). More rows make the barcode wider.
        generator.Parameters.Barcode.Pdf417.Rows = 9;
        // ------------------------------------

        // Save the customized barcode
        string outputPath = "Pdf417CustomLayout.png";
        generator.Save(outputPath, BarCodeImageFormat.Png);

        Console.WriteLine($"Custom barcode saved to {outputPath}");
    }
}
```

**これが必要になる理由:**  
- **幅が制限されている場合:** 列を減らし行を増やすと、横長で高さが短いバーコードになり、狭いラベルに最適です。  
- **高さが制限されている場合:** 列を増やし行を減らすと、縦長で幅が狭いバーコードになり、垂直スペースがあるときに有用です。

`Columns` と `Rows` は、ドキュメントで定義された範囲内の値（列は 2‑30、行は 1‑90）のみ受け付けます。範囲外の値を指定すると `ArgumentOutOfRangeException` がスローされるため、UI でこれらの設定を公開する場合は必ずユーザー入力を検証してください。

## ステップ 4: PDF417 をさらにカスタマイズする方法

列と行以外にも、PDF417 シンボルは多くのオプションパラメータを提供します:

| プロパティ | 用途 | 典型的な値 |
|----------|------|------------|
| `ErrorLevel` | エラー訂正機能を制御 | 0‑8（数値が大きいほど堅牢） |
| `MacroPdf417` | 複数セグメントデータ用のマクロ PDF417 を有効化 | `true`/`false` |
| `CompactPdf417` | エラー訂正を減らす代わりに、よりコンパクトなバーコードを生成 | `true`/`false` |
| `SecurityLevel` | セキュリティチェックディジットを追加 | 0‑2 |

以下は、ノイズが多い環境向けにエラーレベルを最大 (8) に設定した簡単な例です:

```csharp
generator.Parameters.Barcode.Pdf417.ErrorLevel = 8;
generator.Parameters.Barcode.Pdf417.CompactPdf417 = true;
```

**重要な理由:**  
高いエラー訂正は、バーコードの一部が損傷していてもスキャナがデータを復元できるようにします。ただし、バーコードのサイズも大きくなるため、レイアウト制約とバランスを取る必要があります。

## ステップ 5: バーコードが機能するか検証する

PNG を生成したら、任意のバーコードスキャナアプリ（ほとんどのスマートフォンに無料の PDF417 リーダーがあります）でテストしてください。スキャナが元のテキスト（`Custom layout text`）を返せば、バーコードは有効です。

スキャンに問題がある場合:

1. **寸法を確認:** 列/行が許容範囲内にあることを確認してください。  
2. **エラーレベルを調整:** 損傷した媒体には `ErrorLevel` を上げてください。  
3. **画像品質を確認:** 印刷する場合は、より高い DPI（例: `generator.Save(outputPath, BarCodeImageFormat.Png, 300)`）で保存してください。

## 再利用可能なヘルパーの完全なソースコード

以下は、任意の .NET プロジェクトに組み込めるコンパクトで再利用可能なクラスです。単一メソッドで **pdf417 の生成方法** と **pdf417 のカスタマイズ方法** をカプセル化しています。

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

public static class Pdf417Helper
{
    /// <summary>
    /// Creates a PDF417 barcode image with optional layout parameters.
    /// </summary>
    /// <param name="text">The data to encode.</param>
    /// <param name="outputPath">Full file path for the PNG output.</param>
    /// <param name="columns">Number of columns (2‑30). Pass null to use default.</param>
    /// <param name="rows">Number of rows (1‑90). Pass null to use default.</param>
    /// <param name="errorLevel">Error correction level (0‑8). Null = default.</param>
    public static void CreatePdf417(string text, string outputPath,
                                    int? columns = null,
                                    int? rows = null,
                                    int? errorLevel = null)
    {
        var generator = new BarcodeGenerator(EncodeTypes.Pdf417, text);

        // Apply optional customizations
        if (columns.HasValue) generator.Parameters.Barcode.Pdf417.Columns = columns.Value;
        if (rows.HasValue)    generator.Parameters.Barcode.Pdf417.Rows    = rows.Value;
        if (errorLevel.HasValue) generator.Parameters.Barcode.Pdf417.ErrorLevel = errorLevel.Value;

        // Save as high‑resolution PNG (300 DPI) for printing scenarios
        generator.Save(outputPath, BarCodeImageFormat.Png, 300);
    }
}
```

このヘルパーは次のように呼び出せます:

```csharp
Pdf417Helper.CreatePdf417(
    text: "Order #12345",
    outputPath: "OrderBarcode.png",
    columns: 5,
    rows: 12,
    errorLevel: 6);
```

このメソッドは繰り返しのボイラープレートを抽象化し、ビジネスロジックに集中できるようにします。

## よくある落とし穴と回避策

- **範囲外の値:** `columns` と `rows` を代入する前に必ず検証してください。  
- **画像形式が不正:** 一部の旧式スキャナは BMP または JPEG のみ対応です。必要に応じて `BarCodeImageFormat.Bmp` を使用してください。  
- **印刷時の DPI が低い:** デフォルト DPI は 96 です。高品質印刷の場合は、`Save` 呼び出し時に明示的に高い DPI（例: 300）を設定してください。  
- **フォントサポートが欠如:** PDF417 はバイナリデータをエンコードするため、通常フォントを指定する必要はありません。ただし、画像にテキストを重ねる場合は、対象マシンにフォントがインストールされていることを確認してください。

## 結論

これで、開始から完了まで **pdf417 バーコードを作成** する方法、カスタム列/行設定で **pdf417 を生成** する方法、エラー訂正やコンパクト化のために **pdf417 をカスタマイズ** する方法がわかりました。再利用可能なヘルパーパターンに従うことで、オンデマンドでバーコードを生成し、任意のレイアウト制約に適応させ、実稼働環境での信頼性の高いスキャンを保証できます。

**次のステップ**

- 同じ `BarcodeGenerator` クラスを使用して、QR や Code128 など他のシンボルも調査してください。  
- PNG 出力を PDF 生成ライブラリ（例: iText7）と組み合わせ、請求書にバーコードを埋め込んでください。  
- `MacroPdf417` を試して、物流や輸送アプリケーションで有用なマルチセグメントデータ伝送を実装してください。

コーディングを楽しんで、バーコードが常に最初の試みでスキャンできるように！

## 次に学ぶべきことは？

以下のチュートリアルは、本ガイドで示した手法に基づく密接に関連したトピックを扱っています。各リソースには、ステップバイステップの解説付きの完全なコード例が含まれており、追加の API 機能を習得し、独自プロジェクトで代替実装アプローチを探求するのに役立ちます。

- [How to generate PDF417 barcode in C# – step‑by‑step guide](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-step-by-step-guide/)
- [How to generate barcode and customize PDF417 barcode in C#](/barcode/english/net/compact-pdf417-encoding/how-to-generate-barcode-and-customize-pdf417-barcode-in-c/)
- [How to create PDF417 barcode and export PNG in C#](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-and-export-png-in-c/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}