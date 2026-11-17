---
category: general
date: 2026-11-17
description: C#でPDF417バーコードを作成する方法を学ぶ – C#のバーコードジェネレーターを使用して文字列からバーコードを生成する完全ガイド
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create PDF417 barcode
- how to generate barcode
- c# barcode generator
- generate barcode from string
- create gs1 barcode
language: ja
lastmod: 2026-11-17
og_description: C#でPDF417バーコードをすばやく作成する。このチュートリアルでは、C#のバーコードジェネレータを使用して文字列からバーコードを生成する方法を示し、完全なソースコードを含んでいます。
og_image_alt: Screenshot of a generated PDF417 barcode created with a C# barcode generator
og_title: C#でPDF417バーコードを作成する – ステップバイステップガイド
schemas:
- author: Aspose
  dateModified: '2026-11-17'
  description: Learn how to create PDF417 barcode in C# – a complete guide on how
    to generate barcode from string using a C# barcode generator.
  headline: How to create PDF417 barcode in C# with a barcode generator
  type: TechArticle
- description: Learn how to create PDF417 barcode in C# – a complete guide on how
    to generate barcode from string using a C# barcode generator.
  name: How to create PDF417 barcode in C# with a barcode generator
  steps:
  - name: Expected output
    text: '![Generated PDF417 barcode showing the GTIN (01)12345678901234](/images/pdf417-sample.png){:
      .center-image alt="Generated PDF417 barcode created with a C# barcode generator"}'
  - name: Changing the image format
    text: If you prefer JPEG or BMP, just replace `BarCodeImageFormat.Png` with `BarCodeImageFormat.Jpeg`
      or `BarCodeImageFormat.Bmp`. The rest of the code stays identical.
  - name: Adjusting error correction level
    text: PDF417 supports error correction levels 0‑8. Higher levels increase redundancy
      but also enlarge the barcode.
  - name: Generating other GS1 barcodes
    text: 'The same `BarcodeGenerator` can produce **create GS1 barcode** for other
      symbologies, such as `EncodeTypes.Gs1DataMatrix` or `EncodeTypes.Gs1Qr`. Just
      swap the enum value:'
  - name: Handling empty or null data
    text: 'When you **generate barcode from string**, always validate the input:'
  type: HowTo
- questions:
  - answer: Yes. The Aspose.BarCode library targets .NET Standard 2.0, which is compatible
      with .NET Framework 4.6 and later.
    question: Can I use this code on .NET Framework 4.6?
  - answer: 'Set the `Resolution` property before saving: ```csharp generator.Parameters.ImageResolution.DpiX
      = 300; generator.Parameters.ImageResolution.DpiY = 300; ```'
    question: What if I need a higher‑resolution image?
  - answer: 'It will be a standard PDF417 barcode, but it won’t be recognized as a
      GS1‑compliant symbol. Include the `(01)` prefix when you need **create GS1 barcode**
      compliance. ## Conclusion You now know how to **create PDF417 barcode** in C#
      using a robust **c# barcode generator**. The tutorial covered: * In'
    question: Is the barcode still valid without the GS1 Application Identifier?
  type: FAQPage
tags:
- barcode
- C#
- PDF417
- GS1
- code generation
title: C# とバーコードジェネレータを使用して PDF417 バーコードを作成する方法
url: /ja/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-in-c-with-a-barcode-generator/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# C# で PDF417 バーコードを作成する方法（バーコードジェネレータ使用）

.NET アプリケーションで **PDF417 バーコードを作成** したい場合、本ガイドが手順をすべて示します。プレーン文字列から **バーコードを生成** し、シンボルサイズを設定し、結果を PNG ファイルとして保存する方法を、信頼性の高い C# バーコードジェネレータを使って学びます。

プログラムでバーコードを生成すれば、手作業の工程が省け、品質が一定に保たれます。このチュートリアルでは、プロジェクトのセットアップから最終画像までを網羅し、あらゆる C# ソリューションにバーコード作成機能をすぐに組み込めるようにします。

## 前提条件

開始する前に、以下を用意してください。

* .NET 6.0 SDK 以降（コードは .NET Core と .NET Framework でも動作します）
* Visual Studio 2022（または C# をサポートする任意の IDE）
* **Aspose.BarCode for .NET** のライセンスまたは無料トライアル – 本例で使用するライブラリ
* C# の基本的な構文に慣れていること

追加のパッケージは不要です。NuGet パッケージ `Aspose.BarCode` に必要なクラスがすべて含まれています。

## 手順 1 – C# バーコードジェネレータのセットアップ

**PDF417 バーコードを作成** する最初のステップは、`BarcodeGenerator` オブジェクトをインスタンス化することです。このオブジェクトがエンコード、描画、保存を担当する **c# barcode generator** を表します。

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Step 1: Create a barcode generator for PDF417 with the data to encode
        // The data string follows the GS1 Application Identifier (01) for a GTIN
        BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
            EncodeTypes.Pdf417, "(01)12345678901234");
```

*ポイント*: `EncodeTypes.Pdf417` 列挙体は、ライブラリに PDF417 シンボルを使用するよう指示します。これは身分証明書や輸送ラベルで使われる標準です。文字列 `"(01)12345678901234"` は **文字列からバーコードを生成** する例であり、同時に **GS1 バーコードを作成** するデータのサンプルでもあります。

## 手順 2 – X‑ディメンション（モジュール幅）の設定

X‑ディメンションは最小バー（モジュール）の幅を決定します。画面表示向けの一般的な値は 2 ピクセルです。

```csharp
        // Step 2: Set the X‑dimension (module width) to 2 pixels
        barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

X‑ディメンションを明示的に設定することで、デフォルト設定による過小サイズのバーコード生成を防げます。

## 手順 3 – 列数の定義

PDF417 では列数を調整でき、バーコードの形状とデータ容量の両方に影響します。コンパクトなラベルの場合、4 列が適しています。

```csharp
        // Step 3: Define the number of columns (e.g., 4) for a compact barcode
        barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 4;
```

より高いバーコードが必要な場合は列数を増やしてください。ライブラリが自動で必要な行数を計算します。

## 手順 4 – バーコードを画像として保存

最後に、バーコードを PNG ファイルとしてエクスポートします。PNG はエッジが鮮明で、透過もサポートします。

```csharp
        // Step 4: Save the generated barcode as a PNG image
        barcodeGenerator.Save("output/Gs1Pdf417.png", BarCodeImageFormat.Png);
    }
}
```

プログラムを実行すると `output/Gs1Pdf417.png` が生成されます。任意の画像ビューアで開くと、指定した GS1 データをエンコードした **PDF417 バーコード** が確認できます。

### 期待される出力

![Generated PDF417 barcode showing the GTIN (01)12345678901234](/images/pdf417-sample.png){: .center-image alt="C# バーコードジェネレータで作成された PDF417 バーコード"}

*上記画像は、完全なコードサンプルの結果を示しています。任意の PDF417 対応リーダーでスキャン可能です。*

## 追加オプションと一般的なバリエーション

### 画像形式の変更

JPEG や BMP が必要な場合は、`BarCodeImageFormat.Png` を `BarCodeImageFormat.Jpeg` または `BarCodeImageFormat.Bmp` に置き換えるだけです。その他のコードは同じです。

### 誤り訂正レベルの調整

PDF417 は誤り訂正レベル 0‑8 をサポートします。レベルを上げると冗長性が増し、バーコードが大きくなります。

```csharp
barcodeGenerator.Parameters.Barcode.Pdf417.ErrorCorrectionLevel = 5; // medium redundancy
```

### 他の GS1 バーコードの生成

同じ `BarcodeGenerator` を使って、`EncodeTypes.Gs1DataMatrix` や `EncodeTypes.Gs1Qr` など、他のシンボル向けに **GS1 バーコードを作成** できます。列挙体の値を差し替えるだけです。

```csharp
BarcodeGenerator gs1Generator = new BarcodeGenerator(
    EncodeTypes.Gs1DataMatrix, "(01)12345678901234");
```

### 空または null データの取り扱い

**文字列からバーコードを生成** する際は、必ず入力を検証してください。

```csharp
string data = GetUserInput();
if (string.IsNullOrWhiteSpace(data))
{
    throw new ArgumentException("Data to encode cannot be null or empty.");
}
BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, data);
```

これにより実行時例外を防ぎ、GS1 フォーマット規則に準拠したバーコードが生成されます。

## 完全な実行可能サンプル

以下は新しいコンソールプロジェクトにコピー＆ペーストできるフルプログラムです。`using` ディレクティブ、フォルダー作成、エラーハンドリングをすべて含んでいます。

```csharp
using System;
using System.IO;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Input data – GS1 GTIN with Application Identifier (01)
        const string gs1Data = "(01)12345678901234";

        // Validate input
        if (string.IsNullOrWhiteSpace(gs1Data))
        {
            Console.WriteLine("Error: Barcode data cannot be empty.");
            return;
        }

        // Ensure output directory exists
        string outputDir = Path.Combine(Directory.GetCurrentDirectory(), "output");
        Directory.CreateDirectory(outputDir);

        // Create the generator for PDF417 (GS1 optional)
        BarcodeGenerator generator = new BarcodeGenerator(
            EncodeTypes.Pdf417, gs1Data);

        // Configure appearance
        generator.Parameters.Barcode.XDimension.Pixels = 2;   // module width
        generator.Parameters.Barcode.Pdf417.Columns = 4;    // compact layout
        generator.Parameters.Barcode.Pdf417.ErrorCorrectionLevel = 5; // optional

        // Save as PNG
        string outputPath = Path.Combine(outputDir, "Gs1Pdf417.png");
        generator.Save(outputPath, BarCodeImageFormat.Png);

        Console.WriteLine($"Barcode saved to: {outputPath}");
    }
}
```

**プログラムを実行**（`dotnet run`）すると、*output* フォルダー内に `Gs1Pdf417.png` が作成されます。任意の PDF417 リーダーでスキャンし、GTIN `(01)12345678901234` が正しくエンコードされていることを確認してください。

## よくある質問

**Q: .NET Framework 4.6 でもこのコードは使えますか？**  
A: はい。Aspose.BarCode ライブラリは .NET Standard 2.0 を対象としており、.NET Framework 4.6 以降と互換性があります。

**Q: より高解像度の画像が必要な場合は？**  
A: 保存前に `Resolution` プロパティを設定してください。

```csharp
generator.Parameters.ImageResolution.DpiX = 300;
generator.Parameters.ImageResolution.DpiY = 300;
```

**Q: GS1 アプリケーション識別子がなくてもバーコードは有効ですか？**  
A: 標準的な PDF417 バーコードにはなりますが、GS1 準拠シンボルとしては認識されません。**GS1 バーコードを作成** する必要がある場合は、`(01)` プレフィックスを必ず付けてください。

## 結論

これで、堅牢な **c# barcode generator** を使って C# で **PDF417 バーコードを作成** する方法が分かりました。本チュートリアルで扱った内容は以下の通りです。

* GS1 データで `BarcodeGenerator` をインスタンス化  
* X‑ディメンションと列数の設定  
* PNG 画像として保存  
* 誤り訂正、異なる画像形式、入力検証を組み合わせた拡張方法  

この基礎があれば、文字列から任意の PDF417 または GS1 バーコードを生成し、レポートに埋め込んだり、プリンターへ直接送信したりできます。Aspose.BarCode API を活用して色付けや余白追加、複数バーコードの合成など、さらに高度なカスタマイズに挑戦してください。

**次のステップ**: DataMatrix 用に **GS1 バーコードを作成** してみる、動的列計算を試す、あるいは ASP.NET Core Web サービスに組み込んでオンデマンドでバーコード画像を返す実装を行う。

Happy coding!

## 次に学ぶべきこと

以下のチュートリアルは、本ガイドで示したテクニックを応用した関連トピックを扱っています。各リソースには完全なコード例とステップバイステップの解説が含まれており、API の追加機能を習得したり、別の実装アプローチを探求したりするのに役立ちます。

- [How to generate PDF417 barcode in C# – complete guide](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-complete-guide/)
- [How to create micro pdf417 barcode and generate PNG in C#](/barcode/english/net/compact-pdf417-encoding/how-to-create-micro-pdf417-barcode-and-generate-png-in-c/)
- [How to create macro PDF417 barcode in C# using Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/how-to-create-macro-pdf417-barcode-in-c-using-aspose-barcode/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}