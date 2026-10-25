---
category: general
date: 2026-10-24
description: Aspose.BarCode を使用して ASP.NET で GS1 バーコードを作成する方法を学びましょう。文字列からバーコードを生成し、PNG
  としてレンダリングするステップバイステップガイド。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to create GS1 barcode
- generate barcode from string
- barcode generator asp.net
- create barcode with aspose
language: ja
lastmod: 2026-10-24
og_description: Aspose.BarCode を使用して ASP.NET で GS1 バーコードを作成する方法。このチュートリアルに従って文字列からバーコードを生成し、ビジュアル設定を構成し、PNG
  ファイルとして保存します。
og_image_alt: Screenshot of a generated GS1 Micro PDF417 barcode saved as PNG
og_title: ASP.NETでGS1バーコードを作成する方法 – 完全なAsposeガイド
schemas:
- author: Aspose
  dateModified: '2026-10-24'
  description: Learn how to create GS1 barcode in ASP.NET using Aspose.BarCode. Step‑by‑step
    guide to generate barcode from string and render PNG.
  headline: How to create GS1 barcode in ASP.NET with Aspose.BarCode
  type: TechArticle
- description: Learn how to create GS1 barcode in ASP.NET using Aspose.BarCode. Step‑by‑step
    guide to generate barcode from string and render PNG.
  name: How to create GS1 barcode in ASP.NET with Aspose.BarCode
  steps:
  - name: 4.1 Prepare the GS1 data string
    text: 'GS1 data must be wrapped in parentheses with the AI code. For a product
      identifier (01) and a batch number (10) the string looks like:'
  - name: 4.2 Build the GS1 Micro PDF417 generator
    text: '```csharp public static byte[] GenerateGs1MicroPdf417(string gs1Data, string
      outputFolder) { // Step 4.2.1: Create a generator for Micro PDF417 using the
      GS1 data. BarcodeGenerator gs1Generator = new BarcodeGenerator(EncodeTypes.MicroPdf417,
      gs1Data);'
  - name: 4.3 Expose the generator through an ASP.NET endpoint
    text: '```csharp app.MapGet("/gs1barcode", (HttpContext context) => { string outputFolder
      = Path.Combine(Directory.GetCurrentDirectory(), "wwwroot", "barcodes"); Directory.CreateDirectory(outputFolder);
      // Ensure the folder exists'
  type: HowTo
tags:
- Aspose.BarCode
- GS1
- ASP.NET
- C#
title: Aspose.BarCode を使用して ASP.NET で GS1 バーコードを作成する方法
url: /ja/net/gs1-barcode-encoding/how-to-create-gs1-barcode-in-asp-net-with-aspose-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# ASP.NET と Aspose.BarCode で GS1 バーコードを作成する方法

ASP.NET アプリケーションで **GS1 バーコードの作成方法** が必要な場合、このガイドでは正確な手順を示します。文字列からバーコードを生成し、外観を設定し、結果を PNG 画像として保存する方法が分かります。

GS1 バーコードの作成にはカスタムエンコーディングロジックは不要です。Aspose.BarCode を使用すれば、.NET 6+ およびそれ以前のフレームワークでも動作する、信頼性の高い標準準拠のソリューションが得られます。このチュートリアルではプロジェクトのセットアップから出力の検証までをすべてカバーしているので、コードをそのまま自分の Web プロジェクトにコピーして使用できます。

## Prerequisites

開始する前に、以下が揃っていることを確認してください。

* Visual Studio 2022（または .NET をサポートする任意の IDE）
* .NET 6 SDK（または .NET Framework 4.7.2 以上）
* ASP.NET Core または ASP.NET Framework の基本知識
* Aspose.BarCode ライセンス（無料評価版でもテストは可能）

追加のサードパーティライブラリは不要です。Aspose.BarCode がエンコーディングとレンダリングをすべて内部で処理します。

## Step 1: Create a new ASP.NET project

Visual Studio を開き、**ASP.NET Core Web App**（*Empty* テンプレートを選択）を作成します。従来の Web Forms プロジェクトでも、同じコードをコードビハインド ファイル内で使用できます。

```csharp
// Program.cs (ASP.NET Core minimal API example)
using Microsoft.AspNetCore.Builder;
using Microsoft.Extensions.Hosting;

var builder = WebApplication.CreateBuilder(args);
var app = builder.Build();

app.MapGet("/", () => "GS1 barcode generator is ready.");
app.Run();
```

プロジェクトを実行すると、ブラウザに *GS1 barcode generator is ready.* と表示されます。これで Web ホストが正常に動作していることが確認できます。

## Step 2: Install Aspose.BarCode via NuGet

**Package Manager Console** を開き、以下を実行します。

```powershell
Install-Package Aspose.BarCode
```

このパッケージにより `Aspose.BarCode.Generation` 名前空間がプロジェクトに追加され、`BarcodeGenerator` クラスを使用して **generate barcode from string** が可能になります。NuGet コマンドは必要な参照をプロジェクト ファイルに自動で追加します。

## Step 3: Generate a simple barcode from a string

基本的な使い方を示すため、PNG バイト配列を返すヘルパーメソッドを作成します。このメソッドはコントローラ、Razor ページ、または任意のエンドポイントから呼び出すことができます。

```csharp
using Aspose.BarCode.Generation;
using System.IO;

/// <summary>
/// Generates a barcode image from the supplied text.
/// </summary>
/// <param name="text">The data to encode.</param>
/// <param name="encodeType">The barcode symbology.</param>
/// <returns>PNG image bytes.</returns>
public static byte[] GenerateBarcode(string text, EncodeTypes encodeType)
{
    // Step 3.1: Initialize the generator with the desired symbology and data.
    BarcodeGenerator generator = new BarcodeGenerator(encodeType, text);

    // Step 3.2: Set a modest module width – 2 pixels gives a clear image.
    generator.Parameters.Barcode.XDimension.Pixels = 2;

    // Step 3.3: Render the barcode to a memory stream in PNG format.
    using MemoryStream ms = new MemoryStream();
    generator.Save(ms, BarCodeImageFormat.Png);
    return ms.ToArray();
}
```

これで任意のエンドポイントから `GenerateBarcode("HelloWorld", EncodeTypes.Code128)` を呼び出し、生成されたバイト列を HTTP 応答に書き込めます。これが **barcode generator asp.net** パターンのデモです。

## Step 4: How to create GS1 barcode – Micro PDF417 example

GS1 バーコードは、製品情報を伝えるアプリケーション識別子（AI）を埋め込みます。Aspose.BarCode は、コンパクトなデータ表現に最適な GS1 互換の Micro PDF417 をサポートしています。

### 4.1 Prepare the GS1 data string

GS1 データは AI コードを括弧で囲む必要があります。製品識別子 (01) とロット番号 (10) の場合、文字列は次のようになります。

```csharp
string gs1Data = "(01)12345678901234(10)ABCD";
```

括弧は標準の一部であり、Aspose.BarCode が自動的に解析します。

### 4.2 Build the GS1 Micro PDF417 generator

```csharp
public static byte[] GenerateGs1MicroPdf417(string gs1Data, string outputFolder)
{
    // Step 4.2.1: Create a generator for Micro PDF417 using the GS1 data.
    BarcodeGenerator gs1Generator = new BarcodeGenerator(EncodeTypes.MicroPdf417, gs1Data);

    // Step 4.2.2: Apply the same visual settings used for other barcodes.
    gs1Generator.Parameters.Barcode.XDimension.Pixels = 2;

    // Step 4.2.3: Micro PDF417 allows 1‑4 columns; 4 gives a more square shape.
    gs1Generator.Parameters.Barcode.Pdf417.Columns = 4;

    // Step 4.2.4: Save the image to the specified folder.
    string filePath = Path.Combine(outputFolder, "GS1MicroPdf417.png");
    gs1Generator.Save(filePath, BarCodeImageFormat.Png);

    // Return the file bytes for immediate HTTP response if needed.
    return File.ReadAllBytes(filePath);
}
```

### 4.3 Expose the generator through an ASP.NET endpoint

```csharp
app.MapGet("/gs1barcode", (HttpContext context) =>
{
    string outputFolder = Path.Combine(Directory.GetCurrentDirectory(), "wwwroot", "barcodes");
    Directory.CreateDirectory(outputFolder); // Ensure the folder exists

    byte[] pngBytes = GenerateGs1MicroPdf417("(01)12345678901234(10)ABCD", outputFolder);

    context.Response.ContentType = "image/png";
    return context.Response.Body.WriteAsync(pngBytes, 0, pngBytes.Length);
});
```

`https://localhost:5001/gs1barcode` にアクセスすると、生成された PNG がストリームされます。画像は GS1 仕様に準拠しており、後で使用できるようディスクにも保存されます。

## Step 5: Rendering additional barcode types

同じ **create barcode with aspose** 手法で他のシンボロジーも生成できます。以下は URL から QR コードを作成する簡単な例です。

```csharp
byte[] qrBytes = GenerateBarcode("https://example.com", EncodeTypes.QR);
File.WriteAllBytes(Path.Combine(outputFolder, "ExampleQR.png"), qrBytes);
```

`EncodeTypes.QR` を `EncodeTypes.Code128`、`EncodeTypes.DataMatrix` など、サポートされている任意のタイプに置き換えられます。視覚パラメータ（`XDimension`、`Resolution`、`Color`）は `Parameters` オブジェクトを通じて設定可能です。

## Step 6: Common pitfalls and best‑practice tips

| Issue | Why it happens | How to avoid it |
|-------|----------------|-----------------|
| **Incorrect AI formatting** | 括弧が欠落している、または AI の長さが間違っているとエンコードエラーが発生します。 | 標準が指定する通りに GS1 文字列を正確に構築してください。AI を連結するヘルパーメソッドを使用すると安全です。 |
| **Too many columns** | Micro PDF417 は 1‑4 列しかサポートしておらず、5 列を設定すると例外がスローされます。 | 列数を設定する前に検証します: `if (columns < 1 || columns > 4) throw …` |
| **Low image resolution** | `XDimension` が小さすぎると、プリンタで読み取れないバーコードになることがあります。 | 印刷向けバーコードの場合は `Resolution` を上げます（例: `generator.Parameters.Image.Resolution = 300`）。 |
| **File path issues on Linux** | ハードコーディングしたバックスラッシュは非 Windows 環境で失敗します。 | `Path.Combine` を使用してパスを組み立て、OS 固有の区切り文字に対応させます。 |
| **License not applied** | 無料評価版は 30 日後に透かしが付加されます。 | ライセンスは早めに適用してください: `new License().SetLicense("Aspose.BarCode.lic");` |

## Step 7: Verify the generated barcode

エンドポイントを実行したら、PNG を任意の画像ビューアで開きます。GS1 データが正しくエンコードされているか確認するには、GS1 Micro PDF417 に対応した無料のモバイルスキャナアプリを使用します（多くのバーコードスキャナアプリがこのシンボロジーをサポートしています）。画像をスキャンすると、アプリは次のように返します。

```
(01)12345678901234
(10)ABCD
```

スキャナがエラーを返した場合は、AI の書式や列数を再確認してください。

## Conclusion

これで **ASP.NET 環境で Aspose.BarCode を使用して GS1 バーコードを作成する方法** が分かりました。本チュートリアルでは以下をカバーしました。

* ASP.NET プロジェクトのセットアップと Aspose.BarCode NuGet パッケージのインストール  
* 汎用バーコード向けの **generate barcode from string** の使用方法  
* **create barcode with aspose** を利用した GS1 互換 Micro PDF417 画像の生成  
* 画像のディスク保存と HTTP エンドポイント経由でのストリーミング  

ここからは、GS1 DataMatrix など他の GS1 シンボロジーを調査したり、ジェネレータを受注処理ワークフローに統合したりできます。`XDimension`、色、誤り訂正レベルなどを調整して、ブランドやスキャン環境に最適なバーコードを作成してください。

Happy coding, and let your applications speak the universal language of barcodes!

## What Should You Learn Next?

以下のチュートリアルは、本ガイドで示した手法を応用した関連トピックを扱っています。各リソースには完全なコード例とステップバイステップの解説が含まれており、API の追加機能を習得したり、代替実装アプローチを自分のプロジェクトで試したりするのに役立ちます。

- [How to create code 128 barcode with GS1 using Aspose.BarCode](/barcode/english/net/gs1-barcode-encoding/gs1-code-128-example/)
- [How to Create Barcode Quiet Zone for ITF-14 Using Aspose.BarCode for .NET](/barcode/english/net/itf-14-barcode-customization/itf-14-barcode-quiet-zone-configuration/)
- [How to Create ITF-14 Barcode .NET – Comprehensive Aspose.BarCode Tutorials](/barcode/english/net/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}