---
category: general
date: 2026-11-23
description: C#でBarCodeReaderを使用して画像からバーコードを読み取る方法を学び、Macro PDF417のデコードも含めた完全なコード例と分かりやすい解説を提供します。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to use barcodereader
- read barcodes from image c#
language: ja
lastmod: 2026-11-23
og_description: C# の BarCodeReader を使用して画像からバーコードを読み取る方法。ステップバイステップのガイドに従い、Macro PDF417
  やその他のフォーマットをすぐに実行できるコードでデコードしましょう。
og_image_alt: Screenshot of BarCodeReader console output showing decoded Macro PDF417
  data
og_title: C#でBarCodeReaderを使う方法 – 画像からバーコードを素早く読み取る
schemas:
- author: Aspose
  dateModified: '2026-11-23'
  description: Learn how to use BarCodeReader in C# to read barcodes from an image,
    including Macro PDF417 decoding, with a complete code example and clear explanations.
  headline: How to use BarCodeReader in C# to read barcodes from images
  type: TechArticle
- description: Learn how to use BarCodeReader in C# to read barcodes from an image,
    including Macro PDF417 decoding, with a complete code example and clear explanations.
  name: How to use BarCodeReader in C# to read barcodes from images
  steps:
  - name: 1. Decoding multiple barcode formats
    text: 'If you need to detect more than one format, pass a combined `DecodeType`
      flag:'
  - name: 2. Managing large images
    text: 'Large images can cause high memory usage. Downscale the image before passing
      it to the reader:'
  - name: 3. Error handling
    text: 'Wrap the reading logic in a try‑catch block to surface decoding failures:'
  type: HowTo
tags:
- barcode
- C#
- image-processing
title: C#でBarCodeReaderを使用して画像からバーコードを読み取る方法
url: /ja/net/compact-pdf417-encoding/how-to-use-barcodereader-in-c-to-read-barcodes-from-images/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# C# で BarCodeReader を使用して画像からバーコードを読み取る方法

BarCodeReader の **BarCodeReader の使い方** が必要な場合、このガイドでは迅速なバーコードスキャンの方法を正確に示します。POS システムを構築する場合や文書取り込みを自動化する場合でも、数行のコードだけで C# プロジェクトの画像からバーコードを読み取る方法が学べます。

このチュートリアルでは、Macro PDF417 バーコードをデコードし、拡張プロパティを抽出し、コンソールに有用な情報を出力する完全な実行可能サンプルを紹介します。外部ドキュメントは不要です – 必要なものはすべてここにあります。

## 前提条件

開始する前に、以下がインストールされていることを確認してください。

* .NET 6.0（またはそれ以降） – コードは最新の LTS バージョンを対象としています。
* `BarCodeReader` を提供する **Aspose.BarCode**（または互換性のある）NuGet パッケージへの参照。
* Macro PDF417 バーコードを含む画像ファイル（例では `ExtPDF417Meta.png` を使用）。

> **プロのコツ:** Visual Studio を使用している場合は、`dotnet add package Aspose.BarCode` または NuGet パッケージ マネージャー UI からパッケージを追加してください。

## 手順 1: BarCodeReader インスタンスの作成

バーコード ライブラリを使用する際に最初に行うことは、ソース画像を指し示し、API に検索対象のバーコードタイプを伝えるリーダーをインスタンス化することです。

```csharp
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

// Step 1: Initialise BarCodeReader for a Macro PDF417 image
using (BarCodeReader barcodeReader = new BarCodeReader(
           "YOUR_DIRECTORY/ExtPDF417Meta.png",
           DecodeType.MacroPdf417))
{
    // The using block guarantees proper disposal of native resources.
```

*このステップが重要な理由:*  
`BarCodeReader` は画像を開き、ネイティブ メモリを割り当て、指定された `DecodeType` 用のデコード アルゴリズムを準備します。`MacroPdf417` に限定することで CPU の負荷を減らし、検出精度を向上させます。

## 手順 2: 画像内で検出されたすべてのバーコードを読み取る

1 枚の画像には複数のバーコードが含まれることがあります。特にマクロ エンコード データを扱う場合は顕著です。`ReadBarCodes` メソッドは `BarCodeResult` オブジェクトの列挙可能オブジェクトを返し、検出された各コードを表します。

```csharp
    // Step 2: Iterate over every barcode found
    foreach (BarCodeResult barcodeResult in barcodeReader.ReadBarCodes())
    {
```

*このステップが重要な理由:*  
コレクションを反復処理することで、バッチ処理シナリオや文書に複数のコードが埋め込まれている場合に、すべてのインスタンスを確実に取得できます。

## 手順 3: 拡張 Macro PDF417 プロパティにアクセスする

Macro PDF417 はファイル識別子、セグメント番号、総セグメント数などの追加メタデータを保持します。これらの値は `BarCodeResult` の `Extended.Pdf417` プロパティを通じて取得できます。

```csharp
        // Step 3: Pull extended Macro PDF417 information
        var macroInfo = barcodeResult.Extended.Pdf417;
```

*このステップが重要な理由:*  
拡張フィールドを利用することで、マルチセグメント文書を再構築したり、すべてのパーツが同一ソースに属していることを検証したりできます。このステップを省略すると、生テキストのみが得られ、重要なコンテキストが失われます。

## 手順 4: 最も有用な情報を出力する

最後にデータをコンソール（または任意のロガー）に書き出し、読み取り操作を検証します。サンプルはコードタイプ、デコードされたテキスト、いくつかのマクロ フィールドを出力します。

```csharp
        // Step 4: Display key details
        Console.WriteLine($"Code Type: {barcodeResult.CodeTypeName}");
        Console.WriteLine($"Code Text: {barcodeResult.CodeText}");
        Console.WriteLine($"Macro PDF417 File ID: {macroInfo.MacroPdf417FileID}");
        // Additional macro fields are available:
        // macroInfo.MacroPdf417SegmentID
        // macroInfo.MacroPdf417SegmentsCount
    }
}
```

**期待されるコンソール出力**

```
Code Type: MacroPdf417
Code Text: 1234567890
Macro PDF417 File ID: 42
```

> **注意:** 画像に Macro PDF417 バーコードが含まれていない場合、`ReadBarCodes()` は空のコレクションを返し、ループ本体は実行されません。実運用コードでは必ず空結果をチェックしてください。

## C# で画像からバーコードを読み取る – 一般的なシナリオの対処法

### 1. 複数のバーコード形式をデコードする

複数の形式を検出したい場合は、結合した `DecodeType` フラグを渡します。

```csharp
using (BarCodeReader reader = new BarCodeReader(
           "sample.png",
           DecodeType.Pdf417 | DecodeType.QR | DecodeType.DataMatrix))
{
    // Same iteration logic as before
}
```

### 2. 大きな画像を扱う

大きな画像はメモリ使用量が高くなる可能性があります。リーダーに渡す前に画像を縮小してください。

```csharp
using (Bitmap original = new Bitmap("large.png"))
using (Bitmap resized = new Bitmap(original, new Size(1024, 768)))
{
    // Save resized image to a temporary stream and feed it to BarCodeReader
}
```

### 3. エラーハンドリング

デコード失敗を検出するために、読み取りロジックを try‑catch ブロックでラップします。

```csharp
try
{
    // reading code from previous steps
}
catch (BarCodeException ex)
{
    Console.Error.WriteLine($"Barcode decoding failed: {ex.Message}");
}
```

## 完全動作サンプル

以下はコピーして貼り付け、実行できる完全なプログラムです。すべての手順、必要な `using` ディレクティブ、シンプルなエラーハンドリングの雛形が含まれています。

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

class Program
{
    static void Main()
    {
        const string imagePath = "YOUR_DIRECTORY/ExtPDF417Meta.png";

        try
        {
            using (BarCodeReader barcodeReader = new BarCodeReader(
                       imagePath,
                       DecodeType.MacroPdf417))
            {
                bool anyFound = false;

                foreach (BarCodeResult barcodeResult in barcodeReader.ReadBarCodes())
                {
                    anyFound = true;
                    var macroInfo = barcodeResult.Extended.Pdf417;

                    Console.WriteLine($"Code Type: {barcodeResult.CodeTypeName}");
                    Console.WriteLine($"Code Text: {barcodeResult.CodeText}");
                    Console.WriteLine($"Macro PDF417 File ID: {macroInfo.MacroPdf417FileID}");
                    Console.WriteLine($"Segment ID: {macroInfo.MacroPdf417SegmentID}");
                    Console.WriteLine($"Segments Count: {macroInfo.MacroPdf417SegmentsCount}");
                    Console.WriteLine(new string('-', 40));
                }

                if (!anyFound)
                {
                    Console.WriteLine("No barcodes were detected in the image.");
                }
            }
        }
        catch (BarCodeException ex)
        {
            Console.Error.WriteLine($"Error reading barcode: {ex.Message}");
        }
    }
}
```

**プログラムを実行すると**、検出された各 Macro PDF417 バーコードとその拡張フィールドが表示されるか、バーコードが見つからなかった旨が通知されます。

## 結論

これで **BarCodeReader の使い方** をマスターし、画像 C# アプリケーションからバーコードを読み取る方法、さらに Macro PDF417 のメタデータ抽出まで習得できました。初期化、反復処理、拡張プロパティへのアクセス、複数形式・大画像・エラー処理の実践的なコツを網羅しています。

次に試してみると良いでしょう：

* **QR コードの読み取り** – `DecodeType.MacroPdf417` を `DecodeType.QR` に置き換える。
* デコードしたデータを **データベースや JSON ファイルに保存** して、下流処理に活用する。
* **ASP.NET Core と統合** して、Web API 経由でアップロードされた画像を受け取る。

さまざまなバーコードタイプや画像ソースで実験してみてください。コーディングを楽しんでください！

## 次に学ぶべきことは？

以下のチュートリアルは、本ガイドで示した手法を基にした、密接に関連するトピックを扱っています。各リソースには、ステップバイステップの解説と完全な動作コード例が含まれており、追加の API 機能を習得したり、代替実装アプローチを自分のプロジェクトで探求したりするのに役立ちます。

- [c# barcode reader tutorial – read Macro PDF417 barcodes step by step using GroupDocs.Barcode](/barcode/english/net/compact-pdf417-encoding/c-barcode-reader-tutorial-read-macro-pdf417-barcodes-step-by/)
- [How to use a barcode generator C# for Macro PDF417](/barcode/english/net/compact-pdf417-encoding/how-to-use-a-barcode-generator-c-for-macro-pdf417/)
- [Read barcode from image C# – complete guide with Macro PDF417](/barcode/english/net/compact-pdf417-encoding/read-barcode-from-image-c-complete-guide-with-macro-pdf417/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}