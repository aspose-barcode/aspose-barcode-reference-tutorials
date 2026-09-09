---
category: general
date: 2026-07-18
description: C# の PDF417 バーコードジェネレーターを使用して C# で PDF417 バーコードを作成します。拡張コードテキストを構築し、外観を設定し、画像を保存する手順ごとのチュートリアルに従ってください。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create pdf417 barcode
- c# pdf417 barcode generator
language: ja
lastmod: 2026-07-18
og_description: C#ですぐにPDF417バーコードを作成します。このガイドでは、C# PDF417バーコードジェネレーターの使用方法、拡張モードの設定、そしてPNGへのエクスポート方法を紹介します。
og_image_alt: Generated PDF417 barcode image created with C# PDF417 barcode generator
og_title: C#でPDF417バーコードを作成 – 完全ジェネレータ解説
schemas:
- author: Aspose
  dateModified: '2026-07-18'
  description: Create PDF417 barcode in C# using the C# PDF417 barcode generator.
    Follow a step‑by‑step tutorial to build extended codetext, set appearance, and
    save the image.
  headline: Create PDF417 Barcode in C# – Barcode Generator Guide
  type: TechArticle
- description: Create PDF417 barcode in C# using the C# PDF417 barcode generator.
    Follow a step‑by‑step tutorial to build extended codetext, set appearance, and
    save the image.
  name: Create PDF417 Barcode in C# – Barcode Generator Guide
  steps:
  - name: 1. Install the barcode library
    text: 'Open your terminal in the project folder and run:'
  - name: 2. Build the extended codetext
    text: 'PDF417 supports **extended encoding**, allowing you to mix different character
      sets in a single barcode. Below we create three segments:'
  - name: 3. Initialise the **C# PDF417 barcode generator**
    text: Now that we have a valid codetext string, we hand it to the generator. The
      `using` statement ensures the underlying resources are released automatically.
  - name: 4. Configure appearance and encoding mode
    text: 'The default settings give you a tiny barcode that might be hard to read.
      Let’s tweak a few parameters:'
  - name: 5. Save the barcode image
    text: Finally, write the image to disk. The library supports PNG, JPEG, BMP, and
      several vector formats—PNG is a safe default because it preserves crisp edges.
  - name: Handling Unicode and special characters
    text: When you feed Unicode symbols directly into a plain‑text barcode, the generator
      may fall back to a fallback encoding, resulting in garbled output. By using
      `AddECICodetext` you explicitly tell the encoder which character set to apply,
      eliminating guesswork. If you ever need to support **Arabic**, **
  - name: Adjusting error correction level
    text: 'PDF417 offers four error‑correction levels (0‑8). Higher levels increase
      resilience but also enlarge the barcode. Adjust it via:'
  - name: Scaling for print vs. screen
    text: 'For on‑screen display you might keep the default 96 dpi. For high‑resolution
      printing (300 dpi or more), set:'
  - name: Common pitfalls
    text: '- **Missing `using` directive** – Forgetting `using Aspose.BarCode.Encoding;`
      will cause `ECIEncodings` to be undefined. - **Directory not found** – The `Save`
      method won’t create intermediate folders; create them beforehand or use `Path.Combine`
      with `Environment.CurrentDirectory`. - **Wrong encode'
  type: HowTo
tags:
- barcode
- pdf417
- csharp
title: C#でPDF417バーコードを作成する – バーコードジェネレーターガイド
url: /ja/net/compact-pdf417-encoding/create-pdf417-barcode-in-c-barcode-generator-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# C# で PDF417 バーコードを作成 – バーコードジェネレータガイド

C# アプリケーションで **PDF417 バーコードを作成** したいが、どこから始めればいいか分からないことはありませんか？同じ壁にぶつかる開発者は多いです。朗報です！組み込みの **C# PDF417 バーコードジェネレータ** を使えば、数行のコードでフル機能のバーコードを生成できます。

このチュートリアルでは、異なる文字セットを組み合わせた拡張 codetext の作成、適切なビジュアルスタイルへのジェネレータ設定、そして最終的に PNG ファイルとして保存するまでの全工程を解説します。最後まで読めば、任意の .NET プロジェクトにすぐ貼り付けられるコードスニペットと、Unicode 文字やカスタムモジュール幅といったエッジケースの対処法が手に入ります。

---

## 必要なもの

作業を始める前に、以下が環境に揃っていることを確認してください。

- **.NET 6.0** 以上（例は .NET Framework 4.6+ でも動作します）
- **Aspose.BarCode for .NET**（`BarcodeGenerator`、`EncodeTypes.Pdf417` などを提供する互換ライブラリでも可）
- コードエディタ – Visual Studio、Rider、あるいは VS Code など
- 書き込み可能なフォルダ – ジェネレータが PNG を保存します

以上だけです。バーコードライブラリ以外に追加の NuGet パッケージは不要です。

---

## **PDF417 バーコードを作成**するステップバイステップガイド

### 1. バーコードライブラリをインストール

プロジェクトフォルダでターミナルを開き、次のコマンドを実行します。

```bash
dotnet add package Aspose.BarCode
```

このパッケージにより、`Aspose.BarCode` 名前空間が追加され、以降で使用する `BarcodeGenerator` クラスが利用可能になります。

### 2. 拡張 codetext を構築

PDF417 は **拡張エンコーディング** をサポートしており、1 つのバーコードに複数の文字セットを混在させられます。以下では 3 つのセグメントを作成します。

- Windows‑1251（キリル文字）セグメント
- Unicode 文字（「犬」と「右」の日本語漢字）を含む UTF‑8 セグメント
- プレーンテキストセグメント

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode.Encoding;

// Step 1: Build the extended codetext for the PDF417 barcode
Pdf417ExtCodetextBuilder builder = new Pdf417ExtCodetextBuilder();

// Add a Win1251‑encoded segment
builder.AddECICodetext(ECIEncodings.Win1251, "Will");

// Add a UTF‑8 segment with Unicode characters
builder.AddECICodetext(ECIEncodings.UTF8, "犬Right狗");

// Add a plain‑text segment
builder.AddPlainCodetext("Plain text");

// Retrieve the combined codetext string
string extendedCodetext = builder.GetExtendedCodetext();
```

**重要ポイント:**  
プレーンテキストだけを使用するとデフォルトの ASCII サブセットに制限されます。ECI（Extended Channel Interpretation）セグメントを明示的に宣言することで、スキャナが言語や記号に関係なく各部分を正しく解釈できるようになります。

### 3. **C# PDF417 バーコードジェネレータ** を初期化

有効な codetext 文字列ができたら、ジェネレータに渡します。`using` ステートメントにより、基底リソースが自動的に解放されます。

```csharp
// Step 2: Create a PDF417 barcode generator using the extended codetext
using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, extendedCodetext))
{
    // Configuration goes here (see next step)
}
```

### 4. 外観とエンコードモードを設定

デフォルト設定では非常に小さなバーコードになるため、読み取りにくくなることがあります。いくつかのパラメータを調整しましょう。

- **X‑Dimension** – 各モジュール（ピクセル）の幅を制御
- **EncodeMode** – 入力を拡張モードとして扱うようエンジンに指示
- **TwoDDisplayText** – バーコード下に表示する任意のヒューマンリーダブルテキスト

```csharp
    // Step 3: Configure barcode appearance and encoding mode
    generator.Parameters.Barcode.XDimension.Pixels = 15; // Wider modules for better scannability
    generator.Parameters.Barcode.Pdf417.EncodeMode = Pdf417EncodeMode.Extended; // Activate extended encoding
    generator.Parameters.Barcode.CodeTextParameters.TwoDDisplayText = "Extended mode"; // Display text under the symbol
```

**プロのコツ:** ラベルプリンタで印刷する場合は、`XDimension` を 20 px 以上に上げると、ほとんどのスキャナが好む余裕が生まれます。

### 5. バーコード画像を保存

最後に画像をディスクに書き出します。ライブラリは PNG、JPEG、BMP、そしていくつかのベクターフォーマットをサポートしていますが、エッジがくっきり保たれる PNG が安全なデフォルトです。

```csharp
    // Step 4: Save the generated barcode image
    generator.Save("YOUR_DIRECTORY/Pdf417Extended.png", BarCodeImageFormat.Png);
}
```

`YOUR_DIRECTORY` が存在し、書き込み可能であることを確認してください。プログラム実行後、以下のスクリーンショットに似たファイルが生成されます。

![C# PDF417 バーコードジェネレータで作成された PDF417 バーコードのサンプル](https://example.com/images/pdf417-extended.png "C# PDF417 バーコードジェネレータで作成された PDF417 バーコードのサンプル")

---

## **C# PDF417 バーコードジェネレータ** の詳細解説

### Unicode と特殊文字の取り扱い

Unicode 記号をプレーンテキストバーコードに直接渡すと、ジェネレータがフォールバックエンコーディングに切り替わり、文字化けが発生します。`AddECICodetext` を使用すれば、エンコーダに適用すべき文字セットを明示でき、推測による失敗を防げます。**アラビア語**、**ヘブライ語**、**絵文字** などをサポートしたい場合は、対応する `ECIEncodings` 値を選択してください。

### 誤り訂正レベルの調整

PDF417 には 0〜8 の 4 段階の誤り訂正レベルがあります。レベルが高いほど耐障害性は向上しますが、バーコードは大きくなります。次のように設定します。

```csharp
generator.Parameters.Barcode.Pdf417.ErrorCorrectionLevel = 5; // Balanced level
```

### 印刷用と画面表示用のスケーリング

画面表示だけならデフォルトの 96 dpi で問題ありませんが、高解像度印刷（300 dpi 以上）を行う場合は次を設定します。

```csharp
generator.Parameters.ImageResolution = 300;
```

これにより、保存された PNG がレーザープリンタ向けに十分なディテールを保持します。

### よくある落とし穴

- **using ディレクティブの欠如** – `using Aspose.BarCode.Encoding;` を忘れると `ECIEncodings` が未定義になります。
- **ディレクトリが見つからない** – `Save` メソッドは中間フォルダを自動作成しません。事前に作成するか、`Path.Combine` と `Environment.CurrentDirectory` を組み合わせて使用してください。
- **エンコードモードの誤設定** – `EncodeMode` を `Pdf417EncodeMode.Auto` のままにすると、拡張 codetext がプレーンテキストとして扱われ、ECI マーカーが除去されてしまいます。

---

## 完全に実行可能なサンプルコード

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode.Encoding;

class Program
{
    static void Main()
    {
        // 1️⃣ Build extended codetext
        Pdf417ExtCodetextBuilder builder = new Pdf417ExtCodetextBuilder();
        builder.AddECICodetext(ECIEncodings.Win1251, "Will");
        builder.AddECICodetext(ECIEncodings.UTF8, "犬Right狗");
        builder.AddPlainCodetext("Plain text");
        string extendedCodetext = builder.GetExtendedCodetext();

        // 2️⃣ Initialise generator with the extended codetext
        using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, extendedCodetext))
        {
            // 3️⃣ Configure appearance
            generator.Parameters.Barcode.XDimension.Pixels = 15;
            generator.Parameters.Barcode.Pdf417.EncodeMode = Pdf417EncodeMode.Extended;
            generator.Parameters.Barcode.Pdf417.ErrorCorrectionLevel = 5;
            generator.Parameters.Barcode.CodeTextParameters.TwoDDisplayText = "Extended mode";

            // 4️⃣ Save to PNG (ensure the folder exists)
            string outputPath = System.IO.Path.Combine(
                Environment.CurrentDirectory, "Pdf417Extended.png");
            generator.Save(outputPath, BarCodeImageFormat.Png);
        }

        Console.WriteLine("PDF417 barcode generated successfully!");
    }
}
```

## 次に学ぶべきことは？

以下のチュートリアルは、本ガイドで示したテクニックを基にした、密接に関連するトピックを扱っています。各リソースには、ステップバイステップの解説と完全なコード例が含まれているので、API の追加機能をマスターしたり、独自プロジェクトで代替実装を試したりする際に役立ちます。

- [バーコード作成 – コンパクト PDF417 を Aspose.BarCode で実装](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [dotcode の拡張 codetext を Aspose.BarCode for .NET で作成](/barcode/english/net/dotcode-barcode-configuration/dotcode-extended-code-text-configuration/)
- [C# でバーコード画像を作成 – Codablock F の行と列を設定](/barcode/english/net/codablock-f-encoding/codablock-f-row-column-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}