---
category: general
date: 2026-11-27
description: C#でバーコード画像を作成し、Aspose.BarCodeを使用してPNG形式で保存する – ステップバイステップガイド
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode image
- save image PNG format
- Aspose.BarCode C#
- Macro PDF417 barcode
- barcode generation .NET
language: ja
lastmod: 2026-11-27
og_description: Aspose.BarCode を使用して C# でバーコード画像を作成し、PNG 形式で保存します。このチュートリアルに従って、Macro
  PDF417 バーコードをステップバイステップで生成してください。
og_image_alt: Screenshot of a created barcode image saved as PNG
og_title: C#でバーコード画像を作成しPNG形式で保存する完全ガイド
schemas:
- author: Aspose
  dateModified: '2026-11-27'
  description: Create barcode image in C# and save image PNG format with Aspose.BarCode
    – step‑by‑step guide.
  headline: Create barcode image and save PNG format in C#
  type: TechArticle
tags:
- barcode
- C#
- Aspose
title: C#でバーコード画像を作成し、PNG形式で保存する
url: /ja/net/one-dimensional-barcode-types/create-barcode-image-and-save-png-format-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# C# でバーコード画像を作成し PNG 形式で保存する

.NET アプリケーションで **バーコード画像を作成** する必要がある場合、このガイドでは Aspose.BarCode を使用して Macro PDF417 バーコードを生成し、**PNG 形式で画像を保存**する方法を示します。完全な実行可能サンプルと各設定の説明が得られるので、コードを自分の要件に合わせて調整できます。

バーコードの生成は単一のメソッド呼び出しだけではなく、モジュールサイズ、マクロパラメータ、出力形式を構成する必要があります。このチュートリアルの最後までに、各プロパティがなぜ重要なのか、一般的なエッジケースの対処方法、PNG ファイルが正しく書き込まれたかの検証方法が理解できるようになります。

## 必要なもの

- .NET 6.0 以上（コードは .NET Framework 4.6+ でも動作します）
- Aspose.BarCode for .NET（NuGet で入手可能: `Install-Package Aspose.BarCode`）
- Visual Studio 2022 または Visual Studio Code などの IDE
- PNG ファイルを保存するフォルダーへの書き込み権限

## 手順 1: バーコードジェネレーターの初期化

最初のステップは、`EncodeTypes.MacroPdf417` シンボロジーとエンコードしたいテキストを指定して `BarcodeGenerator` インスタンスを作成することです。

```csharp
using Aspose.BarCode.Generation;

// Step 1: Initialize a Macro PDF417 barcode generator with the desired text
using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MacroPdf417, "Sample text"))
{
    // Subsequent steps go here
}
```

**これが重要な理由:**  
`EncodeTypes.MacroPdf417` はライブラリに PDF417 のマクロバリアントを使用させ、ファイルの分割や追加メタデータをサポートします。コンストラクタには、バーコードにエンコードされる人間が読めるテキストも渡されます。

## 手順 2: モジュールサイズ (X‑dimension) の定義

X‑dimension は単一のバーコードモジュール（最小の黒/白要素）の幅を制御します。画面表示用 PNG では `2` ピクセルが適しています。

```csharp
    // Step 2: Define the module size (X‑dimension) in pixels
    generator.Parameters.Barcode.XDimension.Pixels = 2;
```

**実用的なヒント:**  
バーコードを印刷する場合は、ピクセル値を増やす（例: `4` または `5`）ことで、低解像度プリンターでのぼやけを防げます。

## 手順 3: PDF417 マクロパラメータの設定

Macro PDF417 では、ソースファイルの識別やセグメント順序、整合性チェックを助けるいくつかのオプションフィールドが追加されます。以下は典型的なパラメータの全セットです。不要なものは省略できます。

```csharp
    // Step 3: Set PDF417 macro parameters
    generator.Parameters.Barcode.Pdf417.Columns = 5;                     // Number of columns per row
    generator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;    // Unique file identifier
    generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;      // Current segment number
    generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20; // Total number of segments
    generator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01"; // Logical file name
    generator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234;     // CCITT‑16 checksum
    generator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000;  // Approximate file size in bytes
    generator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2019, 11, 1);
    generator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
    generator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
    generator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;
```

**これらのフィールドが有用な理由:**

| パラメータ | 目的 |
|-----------|------|
| `Columns` | バーコードの幅を制御します。列数が少ないほどバーコードは高くなります。 |
| `MacroPdf417FileID` | すべてのセグメントを結びつける一意の識別子。 |
| `MacroPdf417SegmentID` | ファイル全体におけるこのセグメントの位置。 |
| `MacroPdf417SegmentsCount` | セグメントの総数。再構築に必要です。 |
| `MacroPdf417FileName` | スキャンアプリで表示可能な人間が読める名前。 |
| `MacroPdf417Checksum` | 受信側がデータの完全性を検証するのに役立ちます（CCITT‑16）。 |
| `MacroPdf417FileSize` | 元ファイルのサイズに関するオプションのヒント。 |
| `MacroPdf417TimeStamp` | 元ファイル作成時のタイムスタンプ。 |
| `MacroPdf417Addressee` / `MacroPdf417Sender` | ルーティングや所有権に関するメタデータ。 |
| `MacroPdf417Terminator` | これが最終セグメントか（`Set`）、中間セグメントか（`Unset`）を示します。 |

**エッジケース:** 単一セグメントのバーコードを生成する場合は、`MacroPdf417SegmentsCount` を `1` に、`MacroPdf417Terminator` を `Unset` に設定します。ライブラリは適用できないセグメント関連フィールドを自動的に省略します。

## 手順 4: 生成したバーコードを PNG 画像として保存

最後に、ファイルパスと `BarCodeImageFormat.Png` 列挙値を指定して `Save` を呼び出します。このメソッドは画像をロスレス PNG 形式でディスクに書き込みます。

```csharp
    // Step 4: Save the generated barcode as a PNG image
    string outputPath = Path.Combine(Environment.CurrentDirectory, "ExtPDF417Meta.png");
    generator.Save(outputPath, BarCodeImageFormat.Png);
}
```

**なぜ PNG なのか？**  
PNG は正確なピクセル値を保持するため、鮮明なコントラストが必要なバーコードスキャナーにとって重要です。JPEG 圧縮はパターンを壊すアーティファクトを生む可能性があります。

### 出力の検証

プログラム実行後、実行フォルダーに `ExtPDF417Meta.png` という名前のファイルが作成されているはずです。任意の画像ビューアで開くと、密な長方形のバーコードが表示されます。PDF417 マクロをサポートするモバイルバーコードリーダーでスキャンすれば、埋め込まれたメタデータ（ファイル ID、セグメント番号など）が表示されます。

## よくある落とし穴と回避方法

| 症状 | 考えられる原因 | 対策 |
|------|----------------|------|
| バーコードがぼやけて見える | 選択した DPI に対して X‑dimension が低すぎる | `XDimension.Pixels` を増やすか、`generator.Parameters.ImageResolution` で高 DPI でレンダリングする。 |
| スキャナーが「checksum error」を報告 | `MacroPdf417Checksum` の値が不正確 | プロパティを省略して Aspose に自動計算させるか、CCITT‑16 アルゴリズムに合わせた値を設定する。 |
| PNG ファイルが空または作成されない | 出力パスが無効、または書き込み権限がない | `Path.Combine` を使用し、書き込み可能な既知のフォルダー（例: `Environment.GetFolderPath(Environment.SpecialFolder.Desktop)`）を指定する。 |
| マクロフィールドが無視される | `EncodeTypes` が通常の `Pdf417` に設定されている | コンストラクタで `EncodeTypes.MacroPdf417` が使用されていることを確認する。 |

## 完全な実行可能サンプル

以下はコンソールアプリケーションにコピーできる完全なプログラムです。.NET 6.0 でコンパイルでき、上記の PNG ファイルを生成します。

```csharp
using System;
using System.IO;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Initialize a Macro PDF417 barcode generator with the desired text
        using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MacroPdf417, "Sample text"))
        {
            // Define the module size (X-dimension) in pixels
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // Set PDF417 macro parameters
            generator.Parameters.Barcode.Pdf417.Columns = 5;
            generator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
            generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;
            generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;
            generator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";
            generator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234; // CCITT‑16 checksum
            generator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000;
            generator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2019, 11, 1);
            generator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
            generator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
            generator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;

            // Save the generated barcode as a PNG image
            string outputPath = Path.Combine(Environment.CurrentDirectory, "ExtPDF417Meta.png");
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"Barcode image saved to: {outputPath}");
        }
    }
}
```

**期待される出力（コンソール）：**

```
Barcode image saved to: C:\YourProject\bin\Debug\net6.0\ExtPDF417Meta.png
```

`ExtPDF417Meta.png` を開くと、スキャン可能な Macro PDF417 バーコードがはっきりと表示されます。

## 次のステップ

- **画像形式を変更** – 別のファイルタイプが必要な場合は `BarCodeImageFormat.Png` を `Jpeg` や `Bmp` に置き換えます。JPEG は圧縮アーティファクトを導入するため、スキャンの信頼性に影響する可能性があります。
- **解像度を調整** – 使用

## 次に学ぶべきことは？

以下のチュートリアルは、本ガイドで示した手法を基にした関連トピックを扱っています。各リソースには、ステップバイステップの説明と完全なコード例が含まれており、追加の API 機能を習得したり、独自プロジェクトで代替実装アプローチを探求したりするのに役立ちます。

- [C# で Aspose.Barcode を使用してバーコード画像を作成する方法](/barcode/english/python-java/general/how-to-create-barcode-image-with-aspose-barcode-in-c/)
- [Macro PDF417 オプション付き PDF417 バーコード画像を C# で作成する方法](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-image-in-c-with-macro-pdf417-op/)
- [C# と Aspose.BarCode を使用して画像からバーコードを読み取る – ステップバイステップガイド](/barcode/english/net/one-dimensional-barcode-types/how-to-read-barcodes-from-image-using-c-step-by-step-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}