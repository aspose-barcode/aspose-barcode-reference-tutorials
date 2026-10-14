---
category: general
date: 2026-10-05
description: C#でPDF417バーコードを作成し、ステップバイステップのコードとベストプラクティスのヒントでバーコードPNGを生成する方法を学びましょう。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create PDF417 barcode
- generate barcode PNG
- how to generate PDF417
language: ja
lastmod: 2026-10-05
og_description: C#でPDF417バーコードを作成し、バーコードPNGを即座に生成します。実践的なソリューションのための完全なチュートリアルをご覧ください。
og_image_alt: Example of a compact PDF417 barcode created with C#
og_title: C#でPDF417バーコードを作成 – PNG生成の完全ガイド
schemas:
- author: Aspose
  dateModified: '2026-10-05'
  description: Learn how to create PDF417 barcode in C# and generate barcode PNG with
    step‑by‑step code and best‑practice tips.
  headline: How to create PDF417 barcode and save it as PNG in C#
  type: TechArticle
- description: Learn how to create PDF417 barcode in C# and generate barcode PNG with
    step‑by‑step code and best‑practice tips.
  name: How to create PDF417 barcode and save it as PNG in C#
  steps:
  - name: Expected output
    text: When you open `CompactPdf417.png`, you should see a vertical, high‑density
      barcode that encodes the string *Åspóse.Barcóde©*. Scanning the image with any
      PDF417 reader returns the original text.
  - name: Generating other image formats
    text: 'If you prefer JPEG or BMP, change the `BarCodeImageFormat` enum:'
  - name: Adjusting error correction
    text: 'For harsh environments (e.g., outdoor signage), increase the error‑correction
      level:'
  - name: Encoding binary data
    text: 'PDF417 can encode binary payloads. Pass a `byte[]` instead of a string:'
  - name: Handling very long strings
    text: 'When the data exceeds the default capacity, the generator automatically
      creates additional rows. You can limit the row count to avoid oversized images:'
  type: HowTo
tags:
- barcode
- PDF417
- C#
- image generation
title: C#でPDF417バーコードを作成し、PNGとして保存する方法
url: /ja/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-and-save-it-as-png-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# C# で PDF417 バーコードを作成し PNG として保存する方法

.NET アプリケーションで **PDF417 バーコードを作成** する必要がある場合、このガイドでは具体的な手順を示します。高品質な **バーコード PNG** ファイルを生成する使い勝手の良い C# スニペットが手に入り、出力に影響するすべての設定を理解できるようになります。

バーコードの生成は、チケットシステム、在庫管理、セキュアな文書エンコードなどで一般的な要件です。このチュートリアルの最後までに、完全な実行可能な例を用いて “**PDF417 の生成方法**” という質問に答えられるようになります。

## 前提条件

* .NET 6.0 SDK 以降がインストールされていること  
* Visual Studio 2022 や VS Code などの開発環境  
* **Aspose.BarCode for .NET** NuGet パッケージ（または PDF417 をサポートする互換ライブラリ）

以下のコマンドでパッケージを追加できます：

```bash
dotnet add package Aspose.BarCode
```

以下のコードは Aspose API を使用しています。これは PDF417 のパラメータを細かく制御でき、PNG エクスポートを標準でサポートしているためです。

## Step 1: プロジェクトのセットアップと名前空間のインポート

新しいコンソールプロジェクトを作成し、必要な名前空間をインポートします：

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;
```

`Aspose.BarCode.Generation` 名前空間には `BarcodeGenerator` クラスが含まれており、**PDF417 バーコード** 画像を作成するエントリーポイントとなります。

## Step 2: 目的のテキストで PDF417 バーコードを作成する

`EncodeTypes.Pdf417` 列挙体とエンコードしたいデータでジェネレータをインスタンス化します。この例では、Unicode の取り扱いを示すために特殊文字を含む文字列を使用しています：

```csharp
// Step 2: Create a PDF417 barcode generator with the desired text
var generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Åspóse.Barcóde©");
```

ジェネレータは現在、レンダリング前に設定できるバーコードオブジェクトを保持しています。

## Step 3: ビジュアルパラメータの設定

バーコードを微調整することで可読性が向上し、画像サイズが削減されます。最も頻繁に調整される設定は **X‑dimension**、**columns**、**compact mode** です。

```csharp
// Step 3: Set the X‑dimension (module width) in pixels
generator.Parameters.Barcode.XDimension.Pixels = 2;

// Step 4: Define the number of columns for the PDF417 code
generator.Parameters.Barcode.Pdf417.Columns = 3;

// Step 5: Enable compact (truncated) mode to reduce the barcode size
generator.Parameters.Barcode.Pdf417.Truncate = true;
```

* **X‑dimension** は各モジュールの幅を制御します。`2` ピクセルの値は、コンパクトでありながら可読性のあるバーコードを生成します。  
* **Columns** はコードが使用するデータ列の数を決定します。列数が少ないほどバーコードは狭くなりますが、縦に長くなります。  
* **Truncate** は PDF417 仕様で定義された「コンパクト」モードを有効にし、不要なパディング行を削除します。

使用ケースで耐損傷性を高める必要がある場合は、`Rows` と `ErrorCorrectionLevel` を試すことができます。

## Step 4: バーコードを PNG 画像として保存する

最後に、バーコードを PNG ファイルとしてエクスポートします。PNG はシャープなエッジを保持し、透過もサポートするため、ウェブや印刷シナリオに最適です。

```csharp
// Step 6: Save the generated barcode as a PNG image
string outputPath = @"C:\Barcodes\CompactPdf417.png";
generator.Save(outputPath, BarCodeImageFormat.Png);
Console.WriteLine($"Barcode saved to {outputPath}");
```

プログラムを実行すると、指定ディレクトリに `CompactPdf417.png` が作成されます。画像は以下のようになります：

![C# で作成されたコンパクト PDF417 バーコード](compact-pdf417.png "C# で作成されたコンパクト PDF417 バーコードの例")

*上記の alt テキストには主要キーワードが含まれており、SEO とアクセシビリティの要件の両方を満たしています。*

## 完全な実行可能例

すべての要素を組み合わせた、コピーして貼り付けて実行できる自己完結型プログラムを以下に示します：

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        // 1. Initialize the generator with PDF417 type and sample data
        var generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Åspóse.Barcóde©");

        // 2. Configure size and compactness
        generator.Parameters.Barcode.XDimension.Pixels = 2;          // module width
        generator.Parameters.Barcode.Pdf417.Columns = 3;           // number of columns
        generator.Parameters.Barcode.Pdf417.Truncate = true;       // enable compact mode

        // 3. Optional: increase error correction for damaged prints
        // generator.Parameters.Barcode.Pdf417.ErrorCorrectionLevel = 5;

        // 4. Export to PNG
        string outputPath = @"C:\Barcodes\CompactPdf417.png";
        generator.Save(outputPath, BarCodeImageFormat.Png);

        Console.WriteLine($"Barcode saved to {outputPath}");
    }
}
```

### 期待される出力

`CompactPdf417.png` を開くと、文字列 *Åspóse.Barcóde©* をエンコードした縦向きの高密度バーコードが表示されます。任意の PDF417 リーダーで画像をスキャンすると、元のテキストが取得できます。

## なぜこれらの設定が重要なのか

* **X‑dimension** は物理的サイズとスキャン速度の両方に影響します。モジュールを小さくするとデータ密度が上がりますが、より高解像度のスキャナーが必要になる場合があります。  
* **Columns** はアスペクト比に影響します。モバイルレシートでは、列数を少なくすることで狭い紙にも収まるようにバーコードを細く保てます。  
* **Truncate** は行数を減らし、インクとスペースを節約します。PDF417 はすでにエラー訂正コードワードを含んでいるため、データの完全性を損なうことはありません。

これらのパラメータを理解すれば、ラベルプリンター、ウェブページ、モバイルアプリなど、対象メディアの制約に合わせてバーコードを最適化できます。

## 一般的なバリエーションとエッジケース

### 他の画像フォーマットの生成

JPEG や BMP を使用したい場合は、`BarCodeImageFormat` 列挙体を変更します：

```csharp
generator.Save(@"C:\Barcodes\Pdf417.jpg", BarCodeImageFormat.Jpeg);
```

JPEG は画像を圧縮しますが、サイズが小さい場合にスキャンに影響するアーティファクトが発生することがあります。

### エラー訂正の調整

過酷な環境（例：屋外サイン）では、エラー訂正レベルを上げます：

```csharp
generator.Parameters.Barcode.Pdf417.ErrorCorrectionLevel = 8; // max is 8
```

レベルが高くなるほど冗長性が増し、バーコードは大きくなりますが、耐久性が向上します。

### バイナリデータのエンコード

PDF417 はバイナリペイロードをエンコードできます。文字列の代わりに `byte[]` を渡します：

```csharp
byte[] binaryData = new byte[] { 0x01, 0xFF, 0xA5 };
generator = new BarcodeGenerator(EncodeTypes.Pdf417, binaryData);
```

ライブラリは自動的にバイナリモードに切り替わります。

### 非常に長い文字列の処理

データがデフォルト容量を超えると、ジェネレータは自動的に追加行を作成します。画像が大きくなりすぎないように行数を制限できます：

```csharp
generator.Parameters.Barcode.Pdf417.Rows = 30; // max rows
```

それでも内容が収まらない場合は、複数のバーコードに分割することを検討してください。

## プロのコツ

* 同じ設定で多数のバーコードを作成する必要がある場合は、**ジェネレータをキャッシュ** してください。オブジェクトを再利用することで内部リソースの再割り当てを防げます。  
* 印刷用に特定の DPI が必要な場合は、`ImageOptions` の **`Resolution`** を設定します：

  ```csharp
  generator.Parameters.ImageResolution = 300; // DPI
  ```

* ユーザーに配布する前に、`BarCodeReader` を使用してプログラム上で出力を検証し、生成された PNG がデコード可能であることを確認します。

## 結論

これで C# で **PDF417 バーコードを作成**し、サイズ、列数、コンパクトモードを完全に制御した **バーコード PNG** ファイルを生成する方法が分かりました。完全な例は標準的なアプローチを示し、各設定が重要な理由を説明し、エラー訂正、代替フォーマット、バイナリデータなどのバリエーションもカバーしています。上記のコツを活用して、チケットシステム、物流ラベルジェネレータ、セキュア文書エンコーダなど、特定のワークフローに合わせてソリューションを適応させてください。

---

**次のステップ**

* 同じ `BarcodeGenerator` クラスを使用して、他の 2D シンボル（DataMatrix、QR など）を調査する。  
* バーコード作成を ASP.NET Core API に統合し、オンデマンドで PNG を提供する。  
* バーコード画像を PDF 生成ライブラリと組み合わせ、レポートに直接埋め込む。

コーディングを楽しんでください！

## 次に学ぶべきことは？

以下のチュートリアルは、本ガイドで示した手法を基にした密接に関連するトピックを取り上げています。各リソースには、ステップバイステップの解説と完全な動作コード例が含まれており、追加の API 機能を習得し、独自プロジェクトで代替実装アプローチを探求するのに役立ちます。

- [C# で pdf417 バーコードを作成する方法 – ステップバイステップガイド](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-in-c-step-by-step-guide/)
- [C# でマイクロ pdf417 バーコードを生成する方法 – ステップバイステップガイド](/barcode/english/net/compact-pdf417-encoding/how-to-generate-micro-pdf417-barcode-in-c-step-by-step-guide/)
- [C# でコンパクトモード付き PDF417 バーコードを作成する方法](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-in-c-with-compact-mode/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}