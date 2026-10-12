---
category: general
date: 2026-10-12
description: C#でAsposeバーコードのサンプルを作成し、完全なメタデータを持つMacroPdf417バーコードを生成し、BarCodeReaderを使用してそれを読み取る方法を学びましょう。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- aspose barcode example
- macroPdf417 barcode
- barcode metadata
- c# barcode generation
- BarCodeReader
language: ja
lastmod: 2026-10-12
og_description: C# の Aspose バーコード例で、埋め込みメタデータを持つ MacroPdf417 バーコードの生成方法と、BarCodeReader
  を使用した読み取り方法を示します。
og_image_alt: Screenshot of an Aspose barcode example displaying a MacroPdf417 barcode
  with metadata
og_title: C#でMacroPdf417を使用したAsposeバーコードの例を作成する
schemas:
- author: Aspose
  dateModified: '2026-10-12'
  description: Learn how to create an Aspose barcode example in C# that generates
    a MacroPdf417 barcode with full metadata and reads it back using BarCodeReader.
  headline: How to build an Aspose barcode example with MacroPdf417 in C#
  type: TechArticle
tags:
- Aspose.BarCode
- C#
- Barcode
title: C#でMacroPdf417を使用したAsposeバーコードのサンプルを作成する方法
url: /ja/net/compact-pdf417-encoding/how-to-build-an-aspose-barcode-example-with-macropdf417-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# C# で MacroPdf417 を使用した Aspose バーコード例の作成方法

MacroPdf417 バーコードを作成し、埋め込まれたメタデータを読み取る **aspose barcode example** が必要な場合、このガイドでは完全なワークフローを示します。ジェネレータの設定方法、ファイルレベルの情報の埋め込み、画像の保存、そして `BarCodeReader` で同じデータをデコードする手順が分かります。

このチュートリアルでは、Aspose.BarCode を使用した **C# barcode generation** に必要なすべての情報を網羅し、一般的な落とし穴や大きなファイル ID、カスタムタイムスタンプの扱い方に関するヒントも提供します。

## 必要なもの

開始する前に、以下を用意してください。

* .NET 6.0 SDK 以降（コードは .NET Core および .NET Framework でも動作します）
* Visual Studio 2022 または C# をサポートする任意の IDE
* 有効な Aspose.BarCode ライセンス（開発用には無料トライアルが利用可能）
* プロジェクトにインストールされた NuGet パッケージ `Aspose.BarCode`

これらの前提条件が揃っていれば、追加設定なしでサンプルを実行できます。

## 手順 1: Aspose バーコード例プロジェクトのセットアップ

新しいコンソール アプリケーションを作成し、Aspose.BarCode ライブラリを追加します。

```bash
dotnet new console -n AsposeMacroPdf417Demo
cd AsposeMacroPdf417Demo
dotnet add package Aspose.BarCode
```

`Aspose.BarCode` パッケージは `BarcodeGenerator`、`BarCodeReader`、および MacroPdf417 の取り扱いに必要なすべての型を提供します。

### この手順が重要な理由
NuGet パッケージを追加することで、後で使用する `EncodeTypes`、`DecodeType`、`BarCodeImageFormat` 列挙体が解決されます。パッケージが無いとコンパイラはこれらのシンボルを認識できず、ビルド時にエラーとなります。

## 手順 2: MacroPdf417 バーコードジェネレータの作成

**Program.cs** を開き、テンプレートコードを以下のブロックに置き換えます。このブロックは MacroPdf417 シンボロジー用に構成された `BarcodeGenerator` を作成し、基本的な外観パラメータを設定します。

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Enums;
using System;

class Program
{
    static void Main()
    {
        // Step 2.1: Initialize the generator with source text.
        using (BarcodeGenerator barcodeGenerator =
               new BarcodeGenerator(EncodeTypes.MacroPdf417, "Sample data"))
        {
            // Adjust the module size – 2 pixels per X‑dimension.
            barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;

            // Reduce the number of columns to keep the barcode compact.
            barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 5;

            // Step 2.2: Embed MacroPdf417 metadata.
            // ---------------------------------------------------------
            // The following properties are optional but illustrate
            // how a full‑featured barcode can carry file‑level data.
            // ---------------------------------------------------------
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234; // CCITT‑16
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000;
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp =
                new DateTime(2024, 9, 1);
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Terminator =
                Pdf417MacroTerminator.Set;

            // Step 2.3: Save the barcode image.
            const string outPath = "ExtPDF417Meta.png";
            barcodeGenerator.Save(outPath, BarCodeImageFormat.Png);
            Console.WriteLine($"Barcode saved to {outPath}");
        }
```

#### 主なプロパティの説明

| プロパティ | 用途 | 典型的な範囲 / 備考 |
|----------|---------|-----------------------|
| `MacroPdf417FileID` | ファイル全体の一意の識別子 | 2³¹‑1 以下である必要があります |
| `MacroPdf417SegmentID` | 現在のセグメントのインデックス | 0 から開始 |
| `MacroPdf417SegmentsCount` | ファイル内のセグメント総数 | SegmentID 以上である必要があります |
| `MacroPdf417FileName` | ファイルの人間が読める名前 | 最大 255 文字 |
| `MacroPdf417Checksum` | 元ファイルの CCITT‑16 チェックサム | 必要に応じて外部ツールで計算 |
| `MacroPdf417FileSize` | 元ファイルのバイト単位サイズ | 検証に役立ちます |
| `MacroPdf417TimeStamp` | ファイルが作成された日時 | 一貫性のために UTC を使用 |
| `MacroPdf417Addressee` / `MacroPdf417Sender` | オプションのルーティング情報 | 最大 255 文字の文字列 |
| `MacroPdf417Terminator` | 最終セグメントを示す | `Set` を最後のセグメントに使用 |

これらのフィールドは、後でリーダーが抽出できる **barcode metadata** を構成します。

## 手順 3: バーコードをデコードしメタデータを表示

画像を保存した後、同じプログラムが `BarCodeReader` でファイルを開きます。前の `using` ブロックの後、`Main` メソッド内に以下のコードを追加してください。

```csharp
        // Step 3: Open the saved image with a MacroPdf417 reader.
        using (BarCodeReader barcodeReader =
               new BarCodeReader("ExtPDF417Meta.png", DecodeType.MacroPdf417))
        {
            // Step 3.1: Iterate through all decoded results.
            foreach (BarCodeResult result in barcodeReader.ReadBarCodes())
            {
                // The Extended property holds the MacroPdf417 specific fields.
                var meta = result.Extended.Pdf417;
                Console.WriteLine($"FileID: {meta.MacroPdf417FileID}");
                Console.WriteLine($"SegmentID: {meta.MacroPdf417SegmentID}");
                Console.WriteLine($"SegmentsCount: {meta.MacroPdf417SegmentsCount}");
                Console.WriteLine($"FileName: {meta.MacroPdf417FileName}");
                Console.WriteLine($"Checksum: {meta.MacroPdf417Checksum}");
                Console.WriteLine($"FileSize: {meta.MacroPdf417FileSize}");
                Console.WriteLine($"Timestamp: {meta.MacroPdf417TimeStamp}");
                Console.WriteLine($"Addressee: {meta.MacroPdf417Addressee}");
                Console.WriteLine($"Sender: {meta.MacroPdf417Sender}");
                Console.WriteLine($"Terminator: {meta.MacroPdf417Terminator}");
            }
        }
    }
}
```

### 再読込みが重要な理由
`BarCodeReader` は埋め込んだメタデータが正しくエンコードされているかを検証します。プロパティが欠落している、または範囲外の場合、リーダーはそのフィールドに対して `null` を返し、エラーを優雅に処理できるようになります。

## 手順 4: 実行して出力を確認

プログラムを実行します。

```bash
dotnet run
```

コンソールに以下のような出力が表示されるはずです。

```
Barcode saved to ExtPDF417Meta.png
FileID: 12345678
SegmentID: 12
SegmentsCount: 20
FileName: file01
Checksum: 1234
FileSize: 400000
Timestamp: 9/1/2024 12:00:00 AM
Addressee: street
Sender: aspose
Terminator: Set
```

Step 2 で設定した値と一致すれば、**aspose barcode example** は期待通りに動作しています。

## エッジケースとベストプラクティスのヒント

| 状況 | 注意点 | 推奨される対処法 |
|-----------|-------------------|----------------------|
| **FileID が 32 ビット範囲を超える** | Aspose が `ArgumentOutOfRangeException` をスローします。 | ID を 2 147 483 647 以下に保つか、ファイルを複数の MacroPdf417 ブロックに分割してください。 |
| **ローカル時間のタイムスタンプ** | 別のタイムゾーンのリーダーが値を誤解する可能性があります。 | タイムスタンプは UTC (`DateTime.UtcNow`) で保存し、表示時に必要に応じて変換してください。 |
| **大きなファイルサイズ** | `MacroPdf417FileSize` は `int` で、2 GB 超えるとオーバーフローします。 | カスタムフィールドを使用するか、ファイルを小さなセグメントに分割してください。 |
| **セグメント欠落** | `SegmentID` が連続していないと再構築に失敗します。 | エンコード前にセグメント順序を検証するか、エラー訂正設定を使用してください。 |
| **サポートされていない画像形式** | BMP で保存するとサイズが大幅に増加する可能性があります。 | デフォルトは PNG が適切です。ロスィ圧縮を許容できる場合は JPEG も使用可能です。 |

**Pro tip:** バッチで多数のバーコードを生成する場合、単一の `BarcodeGenerator` インスタンスを再利用し、`EncodeTypes` とソーステキストだけを変更してください。これによりメモリ割り当てが削減され、処理速度が向上します。

## 次に探求できる関連トピック

* **他のマクロシンボル** – Aspose はエラー訂正レベル付きの MacroPdf417 もサポートしています。
* **PDF へのバーコード埋め込み** – `Aspose.PDF` とバーコードジェネレータを組み合わせて印刷可能なドキュメントを作成します。
* **ASP.NET Core との統合** – 生成したバーコードを Web API から直接提供します。
* **モバイルデバイスでのスキャン** – クロスプラットフォームのデコードには `Aspose.BarCode.Cloud` SDK を使用します。

これらのフォローアップ項目は **aspose barcode example** を自然に拡張し、**C# barcode generation** に関する専門知識を深めます。

## 結論

これで、MacroPdf417 バーコードを作成し、豊富な **barcode metadata** を埋め込み、画像を保存し、`BarCodeReader` でデータを読み戻す完全な **aspose barcode example** が完成しました。上記の手順に従えば、異なるファイル ID、タイムスタンプ、あるいは Aspose がサポートする他のバーコードタイプにもコードを簡単に適応できます。

追加のメタデータフィールドを試したり、画像形式を変更したり、ジェネレータを大規模アプリケーションに統合したりしてみてください。楽しいコーディングを！

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}