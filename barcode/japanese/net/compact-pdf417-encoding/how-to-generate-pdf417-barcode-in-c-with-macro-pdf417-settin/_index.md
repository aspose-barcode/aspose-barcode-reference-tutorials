---
category: general
date: 2026-10-15
description: C#でMacro‑PDF417パラメータを使用してPDF417バーコードを生成し、バーコードのサイズを設定し、PNGとして保存する方法を学びます。完全なコード例が含まれています。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to generate pdf417 barcode
- C# PDF417 barcode
- Macro PDF417 parameters
- set barcode dimensions
- barcode image format
- barcode checksum
language: ja
lastmod: 2026-10-15
og_description: C#で完全なMacro‑PDF417設定、サイズ制御、PNG出力を使用してPDF417バーコードを生成する方法。完全なサンプルをご覧ください。
og_image_alt: Screenshot of a generated PDF417 barcode image created with C# code
og_title: C#でPDF417バーコードを生成する方法 – ステップバイステップガイド
schemas:
- author: Aspose
  dateModified: '2026-10-15'
  description: Learn how to generate PDF417 barcode in C# using Macro‑PDF417 parameters,
    set barcode dimensions, and save as PNG. Complete code example included.
  headline: How to generate PDF417 barcode in C# with Macro‑PDF417 settings
  type: TechArticle
tags:
- barcode
- PDF417
- C#
- Aspose.Barcode
title: C#でMacro‑PDF417設定を使用してPDF417バーコードを生成する方法
url: /ja/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-with-macro-pdf417-settin/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# C# で Macro‑PDF417 設定を使用して PDF417 バーコードを生成する方法

ドキュメントワークフローで **PDF417 バーコードの生成方法** が必要な場合、本ガイドでは正確な手順を示します。Macro‑PDF417 パラメータの設定方法、バーコードのサイズ指定、結果を PNG 画像としてエクスポートする方法を、単一の実行可能な C# プログラムで解説します。

PDF417 バーコードの生成は、複数のライブラリや複雑な後処理を必要としません。Aspose.Barcode for .NET を使用すれば、モジュール幅からチェックサムまでバーコードのあらゆる要素を制御でき、高品質な画像を印刷やスキャン用に作成できます。

## 前提条件

開始する前に、以下がインストールされていることを確認してください。

* .NET 6.0（またはそれ以降）SDK  
* Visual Studio 2022 またはお好みの C# IDE  
* Aspose.Barcode for .NET NuGet パッケージ（`Install-Package Aspose.Barcode`）  

これらの前提条件により、追加設定なしでコードがコンパイルできます。

## 手順 1: Macro‑PDF417 バーコード用のジェネレータを作成する

最初の操作では、`EncodeTypes.MacroPdf417` 形式を対象とした `BarcodeGenerator` インスタンスを作成します。コンストラクタにはエンコードしたいデータを渡します。ここでは文字列 `"Sample text"` を使用します。

```csharp
using Aspose.Barcode;
using Aspose.Barcode.Generation;

// Step 1: Initialize the generator with Macro‑PDF417 and data to encode
using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MacroPdf417, "Sample text"))
{
    // Subsequent steps configure the barcode
```

ジェネレータを作成すると内部の `Parameters` オブジェクトが初期化され、**C# PDF417 バーコード** の各種プロパティを調整できるようになります。

## 手順 2: 基本的なバーコード外観を設定 – バーコードのサイズを指定する

バーコードの視覚的サイズを制御することで、スキャンの信頼性が向上します。`XDimension.Pixels` プロパティはモジュール（ドット）の幅を、`Pdf417.Columns` はバーコードが持つ列数を決定します。

```csharp
    // Step 2: Define module width and column count
    generator.Parameters.Barcode.XDimension.Pixels = 2;   // module width in pixels
    generator.Parameters.Barcode.Pdf417.Columns = 5;    // number of columns
```

これらのサイズを設定することで、バーコードが一般的なラベルサイズに収まり、スキャナの仕様を満たすようになります。

## 手順 3: Macro‑PDF417 のファイル識別情報を提供する

Macro‑PDF417 は標準の PDF417 にファイルレベルのメタデータを追加します。ユニークなファイル ID、セグメント ID、総セグメント数、そして人間が読めるファイル名を割り当てる必要があります。

```csharp
    // Step 3: Assign macro file identification
    generator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
    generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 1;
    generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 10;
    generator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "myFile.pdf";
```

これらの **Macro PDF417 パラメータ** により、下流システムは複数のバーコードセグメントから元のファイルを再構築できます。

## 手順 4: 追加のマクロメタデータを付加 – バーコードチェックサムを含める

識別情報に加えて、Macro‑PDF417 はチェックサム、ファイルサイズ、タイムスタンプ、受取人、送信者、終了フラグなどを格納できます。チェックサムを提供することで、デコード時のデータ整合性チェックが向上します。

```csharp
    // Step 4: Populate extra macro metadata
    generator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 0x1A2B;               // CCITT‑16 checksum
    generator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 850_000;             // file size in bytes
    generator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = DateTime.UtcNow;   // UTC timestamp
    generator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "Acme Corp";
    generator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "John Doe";
    generator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;
```

**バーコードチェックサム** やその他のメタデータを含めることで、バーコードは自己記述的になり、ドキュメント自動処理パイプラインでの価値が高まります。

## 手順 5: 生成したバーコードを PNG 画像として保存 – バーコード画像形式を選択する

最終ステップでは、バーコードをファイルに書き出します。`Save` メソッドはファイルパスと `BarCodeImageFormat` 列挙体を受け取ります。PNG はロスレス圧縮を提供し、鮮明なエッジを保つためスキャンに適しています。

```csharp
    // Step 5: Export the barcode to PNG
    generator.Save("C:/Barcodes/MacroPdf417.png", BarCodeImageFormat.Png);
}
```

実行後、`MacroPdf417.png` ファイルには、PDF417 バーコードが鮮明に描画され、PDF に埋め込んだりラベルに印刷したり、画面に表示したりできる状態で保存されます。

## 期待される出力

`C:/Barcodes/MacroPdf417.png` を開くと、エンコードされたテキスト “Sample text” を含む長方形のバーコードが表示されます。バーコードには設定したマクロメタデータが含まれており、Macro‑PDF417 に対応した任意の PDF417 スキャナで確認できます。画像サイズはモジュール幅（2 px）と列数（5）に基づき、コンパクトながら読み取りやすいバーコードとなります。

## よくあるバリエーションとエッジケース

| 状況 | 調整方法 |
|-----------|------------|
| **データ長が異なる** | `"Sample text"` を任意の UTF‑8 文字列に置き換えてください。ジェネレータは自動的にバーコードサイズを調整します。 |
| **解像度を上げたい** | `XDimension.Pixels` を 3 または 4 に増やすと、モジュールが大きくなり低解像度プリンタ向きになります。 |
| **セグメント数が増える** | `MacroPdf417SegmentsCount` を生成するバーコードパーツの総数に合わせて変更してください。 |
| **別の画像形式を使用したい** | 下流システムが JPEG や BMP を好む場合は、`BarCodeImageFormat.Jpeg` または `BarCodeImageFormat.Bmp` を使用します。 |
| **エラー訂正レベルをカスタマイズ** | `generator.Parameters.Barcode.Pdf417.ErrorLevel`（範囲 0‑8）を変更して、データ密度とエラー耐性のバランスを調整します。 |

**プロのコツ:** 本番環境に導入する前に、必ず実機スキャナで生成されたバーコードを検証してください。スキャナによってはモジュール幅や列数にファームウェア固有の制限があります。

## 完全なソースコード

```csharp
using System;
using Aspose.Barcode;
using Aspose.Barcode.Generation;

namespace Pdf417MacroDemo
{
    class Program
    {
        static void Main()
        {
            // Initialize the generator for Macro‑PDF417 with sample data
            using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MacroPdf417, "Sample text"))
            {
                // Set visual dimensions
                generator.Parameters.Barcode.XDimension.Pixels = 2;          // module width
                generator.Parameters.Barcode.Pdf417.Columns = 5;           // column count

                // Provide macro file identification
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
                generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 1;
                generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 10;
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "myFile.pdf";

                // Add macro metadata
                generator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 0x1A2B;               // CCITT‑16 checksum
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 850_000;             // file size in bytes
                generator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = DateTime.UtcNow;   // timestamp
                generator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "Acme Corp";
                generator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "John Doe";
                generator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;

                // Export as PNG
                generator.Save("C:/Barcodes/MacroPdf417.png", BarCodeImageFormat.Png);
            }

            Console.WriteLine("PDF417 barcode generated successfully.");
        }
    }
}
```

このプログラムを実行すると、`C:/Barcodes` フォルダに `MacroPdf417.png` が作成されます。コンソールには生成成功のメッセージが表示されます。

## 結論

これで **C# で PDF417 バーコードを生成する方法** と、Macro‑PDF417 のフルコントロール、**バーコードサイズの設定**、**バーコードチェックサム** などのマクロメタデータの埋め込み、そして選択した **バーコード画像形式** でのエクスポート手順が理解できました。完全なサンプルは任意の .NET プロジェクトにコピーでき、データペイロードを変更したり、より大規模なドキュメント自動化パイプラインに統合したりできます。

### 次のステップ

* **C# PDF417 バーコード** のエラー訂正レベルを調査し、スキャン信頼性を向上させる。  
* 複数の Macro‑PDF417 セグメントを組み合わせて、PDF や画像などの大容量ファイルをエンコードする。  
* **バーコード画像形式** を SVG に切り替えて、Web アプリケーションでスケーラブルなベクターグラフィックを利用する。  

パラメータを自由に試し、結果をコメントやコミュニティフォーラムで共有してください。コーディングを楽しんでください！

## 次に学ぶべきこと

以下のチュートリアルは、本ガイドで示した手法を基にした関連トピックをカバーしています。各リソースには、ステップバイステップの解説と完全な動作コード例が含まれており、追加の API 機能を習得したり、代替実装アプローチを探求したりするのに役立ちます。

- [Generate barcode C# with Macro PDF417 – full example](/barcode/english/net/compact-pdf417-encoding/generate-barcode-c-with-macro-pdf417-full-example/)
- [How to Generate PDF417 Barcode – Complete Programming Guide](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-complete-programming-guide/)
- [How to generate PDF417 barcode in C# with custom dimensions](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-with-custom-dimensions/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}