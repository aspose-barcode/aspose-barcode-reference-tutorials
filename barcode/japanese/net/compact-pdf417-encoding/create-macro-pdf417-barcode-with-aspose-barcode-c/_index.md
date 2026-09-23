---
category: general
date: 2026-09-22
description: C#でAspose.BarCodeを使用してマクロPDF417バーコードを作成します。Asposeでバーコードを生成し、メタデータを設定し、PNGとして保存する手順をステップバイステップで学びます。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create macro PDF417 barcode
- generate barcode with Aspose
- Aspose.BarCode PDF417
- C# barcode generation
- barcode metadata configuration
language: ja
lastmod: 2026-09-22
og_description: C# で Aspose.BarCode を使用してマクロ PDF417 バーコードを作成します。このガイドでは、Aspose を使ってバーコードを生成し、マクロメタデータを設定し、画像をエクスポートする方法を示します。
og_image_alt: Screenshot of a created macro PDF417 barcode using Aspose.BarCode in
  C#
og_title: Aspose.BarCode（C#）を使用したマクロ PDF417 バーコードの作成 – ステップバイステップガイド
schemas:
- author: Aspose
  dateModified: '2026-09-22'
  description: Create macro PDF417 barcode using Aspose.BarCode in C#. Learn step‑by‑step
    how to generate barcode with Aspose, configure metadata, and save as PNG.
  headline: Create macro PDF417 barcode with Aspose.BarCode (C#)
  type: TechArticle
tags:
- Aspose
- PDF417
- C#
- Barcode
title: Aspose.BarCode (C#) を使用してマクロ PDF417 バーコードを作成する
url: /ja/net/compact-pdf417-encoding/create-macro-pdf417-barcode-with-aspose-barcode-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.BarCode (C#) でマクロ PDF417 バーコードを作成する

.NET アプリケーションで **マクロ PDF417 バーコード** を作成する必要がある場合、このチュートリアルでは Aspose.BarCode を使用した手順を詳しく解説します。**Aspose でバーコードを生成**し、マクロ固有のフィールドをすべて設定し、結果を PNG 画像として保存する完全な実行可能サンプルをご覧いただけます。

バーコードは在庫管理、出荷、文書追跡などで頻繁に使用され、Macro PDF417 バリアントはバーコード自体にファイルレベルのメタデータを埋め込むことができます。このガイドを最後まで読むと、ISO/IEC 15438 標準に準拠したフル機能のマクロ PDF417 バーコードを生成できるようになります。

## 必要なもの

開始する前に以下を用意してください。

* .NET 6.0 SDK 以降（コードは .NET Core および .NET Framework でも動作します）
* Visual Studio 2022（または任意の C# IDE）
* Aspose.BarCode パッケージを取得できる NuGet 対応のインターネット接続
* C# の基本的な構文に関する知識

これらの前提条件があれば、追加設定なしでコードをコンパイルできます。

## 手順 1: Aspose.BarCode NuGet パッケージをインストール

Aspose.BarCode ライブラリは、本チュートリアル全体で使用する `BarcodeGenerator` クラスを提供します。

```bash
dotnet add package Aspose.BarCode
```

上記コマンドを実行すると、最新の安定版がプロジェクトファイル（`*.csproj`）に追加されます。このパッケージは PDF417、Macro PDF417、その他多数のシンボロジーをサポートしています。

## 手順 2: 新しいコンソールプロジェクトを作成（任意）

クリーンな環境から始めたい場合は、コンソール アプリを生成します。

```bash
dotnet new console -n MacroPdf417Demo
cd MacroPdf417Demo
```

生成された `Program.cs` がバーコード生成コードのホストになります。

## 手順 3: バーコードジェネレータを初期化

ジェネレータは `EncodeTypes.MacroPdf417` 列挙値とエンコードしたいテキストで作成します。Aspose.BarCode は Unicode 文字を自動的に処理するため、アクセント付き文字や記号もそのまま含められます。

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;
using System;

class Program
{
    static void Main()
    {
        // Step 3: Create a Macro PDF417 barcode generator with the desired text
        using (var barcodeGenerator = new BarcodeGenerator(EncodeTypes.MacroPdf417, "Åspóse.Barcóde©"))
        {
            // The rest of the configuration follows...
```

### なぜ重要か
`EncodeTypes.MacroPdf417` はライブラリにマクロ版 PDF417 を使用させ、ファイルレベルのメタデータ（ファイル ID、セグメント数など）を埋め込む機能を追加します。テキスト `"Åspóse.Barcóde©"` はジェネレータが UTF‑8 文字を正しくエンコードできることを示す例です。

## 手順 4: 基本的なバーコードサイズを設定

PDF417 では列数と X‑dimension（1 モジュールの幅）を制御できます。これらの値を調整すると、バーコードの実際のサイズとスキャン信頼性に影響します。

```csharp
            // Step 4: Set basic barcode dimensions
            barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;   // module width in pixels
            barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 5;    // number of columns
```

* **XDimension** – 値が小さいほど密度が高くなり、値が大きいほど低解像度スキャナでも読み取りやすくなります。  
* **Columns** – データ列数を制御します。一般的な範囲は 1〜30 です。

## 手順 5: Macro PDF417 メタデータを設定

Macro PDF417 には、バーコードが表すファイルに関する追加フィールドが含まれます。各フィールドは任意ですが、設定しておくとマクロ形式を理解するスキャナとの相互運用性が向上します。

```csharp
            // Step 5: Configure Macro PDF417 metadata
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234; // demo checksum
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000; // bytes
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2019, 11, 1);
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;
```

### 各フィールドの説明

| プロパティ | 用途 | 典型的な範囲 |
|----------|------|--------------|
| **MacroPdf417FileID** | 複数のバーコードに分割される論理ファイルの一意識別子 | 0‑2³²‑1 |
| **MacroPdf417SegmentID** | 現在のセグメントインデックス（0 から開始） | 0‑(SegmentsCount‑1) |
| **MacroPdf417SegmentsCount** | ファイル全体を構成するセグメント総数 | 1‑99 |
| **MacroPdf417FileName** | ファイルの人間可読名 | 最大 255 文字 |
| **MacroPdf417Checksum** | エラー検出用の任意チェックサム | 0‑65535 |
| **MacroPdf417FileSize** | 元ファイルのバイトサイズ | 0‑2³²‑1 |
| **MacroPdf417TimeStamp** | ファイル作成または更新のタイムスタンプ | 任意の `DateTime` |
| **MacroPdf417Addressee** | 宛先識別子（例: 部署や機械） | 任意文字列 |
| **MacroPdf417Sender** | 送信元識別子（例: 会社名） | 任意文字列 |
| **MacroPdf417Terminator** | このセグメントが最後かどうかを示す | `Set` または `Unset` |

**プロのコツ:** 大きなファイルを複数のバーコードに分割する場合、各セグメントの `SegmentID` が連番になるようにし、`SegmentsCount` をすべてのセグメントで同一に保ちます。スキャナはこれらの値を元に元ファイルを再構築します。

## 手順 6: バーコード画像を保存

Aspose.BarCode は PNG、JPEG、BMP、SVG など多数の出力形式をサポートします。PNG はロスレス品質で、テストやドキュメントに最適です。

```csharp
            // Step 6: Save the barcode image as PNG
            barcodeGenerator.Save("ExtPDF417Meta.png", BarCodeImageFormat.Png);
        }
    }
}
```

プログラムを実行すると、プロジェクトの出力ディレクトリ（`bin/Debug/net6.0/`）に `ExtPDF417Meta.png` という名前のファイルが作成されます。任意のビューアで画像を開き、バーコードが正しく描画されていることを確認してください。

## 手順 7: 生成されたバーコードを検証（任意）

PDF417 スキャナ アプリ（モバイルまたはデスクトップ）がある場合、保存した PNG をスキャンします。スキャナは以下を返すはずです。

* エンコードされたテキスト `"Åspóse.Barcóde©"`
* 設定したすべてのマクロフィールド（ファイル ID、セグメント ID など）

自動検証が必要な場合は、Aspose.BarCode の `BarCodeReader` クラスも利用できます。

```csharp
using Aspose.BarCode.BarCodeRecognition;

// ...

using (var reader = new BarCodeReader("ExtPDF417Meta.png", DecodeType.Pdf417))
{
    foreach (BarCodeResult result in reader.ReadBarCodes())
    {
        Console.WriteLine($"Text: {result.CodeText}");
        Console.WriteLine($"Macro File ID: {result.GetMacroPdf417FileID()}");
        // Access other macro properties similarly
    }
}
```

このスニペットは、プログラムでマクロメタデータを読み戻す方法を示しており、**Aspose でバーコードを生成**するフローがエンドツーエンドで機能することを確認できます。

## エッジケースとベストプラクティス

| シチュエーション | 推奨される対処 |
|----------------|----------------|
| **Unicode 文字** | ソース文字列が UTF‑8（.NET のデフォルト）であることを確認。Aspose.BarCode は Unicode を自動エンコードしますが、スキャナ側の文字セットも合わせて確認してください。 |
| **大容量ファイル** | Macro PDF417 は最大 99 セグメントまで分割可能です。ファイルが 400 KB を超える場合は `SegmentsCount` を増やし、連番の `SegmentID` を持つ複数のバーコードを生成します。 |
| **タイムスタンプの精度** | 汎用時刻として `DateTime.UtcNow` を使用。スキャナの中には UTC を前提とするものがあります。 |
| **チェックサム検証** | 受信側で整合性を確認したい場合は、正しいチェックサムを提供してください。 |
| **画像形式の選択** | 無限に拡大可能なベクタ画像が必要なときは `BarCodeImageFormat.Svg` を使用します。 |
| **パフォーマンス** | 多数のバーコードを生成する際は、`BarcodeGenerator` インスタンスを再利用し、イテレーションごとに `Parameters` だけを変更してください。 |

## 完全な実行可能サンプル

以下は、NuGet パッケージがインストールされている前提で、変更なしでコピー＆ペーストして実行できる完全プログラムです。

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;
using Aspose.BarCode.BarCodeRecognition;
using System;

class Program
{
    static void Main()
    {
        // Create a Macro PDF417 barcode generator with the desired text
        using (var barcodeGenerator = new BarcodeGenerator(EncodeTypes.MacroPdf417, "Åspóse.Barcóde©"))
        {
            // Set basic barcode dimensions
            barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
            barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 5;

            // Configure Macro PDF


## 次に学ぶべきことは？

以下のチュートリアルは、本ガイドで示した手法を応用した関連トピックをカバーしています。各リソースには、ステップバイステップの解説と完全なコード例が含まれており、API の追加機能を習得したり、独自プロジェクトで代替実装を検討したりするのに役立ちます。

- [Aspose barcode example: generate Macro PDF417 in C#](/barcode/english/net/compact-pdf417-encoding/aspose-barcode-example-generate-macro-pdf417-in-c/)
- [Create PDF417 Barcode Metadata in C# – Complete Step‑by‑Step Guide](/barcode/english/net/compact-pdf417-encoding/create-pdf417-barcode-metadata-in-c-complete-step-by-step-gu/)
- [How to Generate PDF417 Barcode Image in C# with Aspose](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-image-in-c-with-aspose/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}