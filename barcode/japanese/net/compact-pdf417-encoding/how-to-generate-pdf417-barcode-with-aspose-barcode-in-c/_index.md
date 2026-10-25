---
category: general
date: 2026-10-24
description: C# で Aspose.BarCode を使用し、コンパクト設定とバーコードの XDimension 制御で PDF417 バーコードを生成する方法を学びましょう。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate PDF417 barcode
- Aspose.BarCode
- compact PDF417
- barcode XDimension
- PDF417 columns
language: ja
lastmod: 2026-10-24
og_description: Aspose.BarCode を使用して C# で PDF417 バーコードを生成します。この完全ガイドに従って、コンパクトな PDF417
  画像を作成し、XDimension を制御し、列数を設定してください。
og_image_alt: Screenshot of generated PDF417 barcode using Aspose.BarCode
og_title: Aspose.BarCodeでPDF417バーコードを生成する – C#ステップバイステップ
schemas:
- author: Aspose
  dateModified: '2026-10-24'
  description: Learn how to generate PDF417 barcode using Aspose.BarCode in C# with
    compact settings and barcode XDimension control.
  headline: How to generate PDF417 barcode with Aspose.BarCode in C#
  type: TechArticle
- description: Learn how to generate PDF417 barcode using Aspose.BarCode in C# with
    compact settings and barcode XDimension control.
  name: How to generate PDF417 barcode with Aspose.BarCode in C#
  steps:
  - name: 1. Changing the image format
    text: '```csharp generator.Save("CompactPdf417.svg", BarCodeImageFormat.Svg);
      ```'
  - name: 2. Encoding large amounts of data
    text: 'PDF417 can store up to ~1.1 KB of text. When the payload exceeds the capacity
      of three columns, the library automatically adds rows. To keep the barcode compact,
      you can:'
  - name: 3. Using a license to remove the trial watermark
    text: '```csharp Aspose.BarCode.License license = new Aspose.BarCode.License();
      license.SetLicense("Aspose.BarCode.lic"); ```'
  - name: 4. Handling exceptions
    text: '```csharp try { generator.Save(outputPath, BarCodeImageFormat.Png); } catch
      (Exception ex) { Console.Error.WriteLine($"Failed to generate barcode: {ex.Message}");
      } ```'
  type: HowTo
tags:
- barcode
- Aspose.BarCode
- PDF417
- C#
title: C#でAspose.BarCodeを使用してPDF417バーコードを生成する方法
url: /ja/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-with-aspose-barcode-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.BarCode を使用して C# で PDF417 バーコードを生成する方法

.NET アプリケーションで **PDF417 バーコードを生成** する必要がある場合、このガイドは完全に実行可能なソリューションを示します。Aspose.BarCode を使用すると、**コンパクト PDF417**、**バーコード XDimension**、および **PDF417 カラム** を細かく制御しながら、プロセスをシンプルに実行できます。

バーコードの生成は、在庫管理システム、チケットプラットフォーム、文書ワークフローなどで一般的な要件です。このチュートリアルの最後までに、PDF417 バーコードの鮮明な PNG 画像を生成し、任意の UI に埋め込んだりラベルに印刷したりできる、自己完結型の C# プログラムが完成します。

## 必要なもの

- .NET 6.0 SDK 以降（コードは .NET Framework 4.6+ でも動作します）
- Visual Studio 2022 またはお好みの C# エディタ
- 有効な Aspose.BarCode for .NET ライセンス（開発用に無料トライアルが利用可能）
- C# の基本的な構文に関する知識

> **プロのコツ:** Aspose.BarCode を評価中の場合は、公式サイトからトライアル版をダウンロードし、NuGet パッケージ `Aspose.BarCode` をプロジェクトに追加してください。トライアル版は生成された画像に小さな透かしを付加しますが、ライセンスを適用すれば透かしは消えます。

## 手順 1: Aspose.BarCode NuGet パッケージをインストール

ソリューション フォルダーでターミナルを開き、次のコマンドを実行します。

```bash
dotnet add package Aspose.BarCode
```

このコマンドは最新の安定版（2026 年 10 月時点でバージョン 23.12）を取得します。パッケージを追加すると、**PDF417 バーコード** 画像の生成に使用する `Aspose.BarCode.Generation` 名前空間が利用可能になります。

## 手順 2: 基本的な C# コンソール プロジェクトを作成

まだプロジェクトがない場合は、次のコマンドで作成します。

```bash
dotnet new console -n Pdf417Demo
cd Pdf417Demo
```

`Program.cs` を開きます。スケルトンにはすでに `Main` メソッドが含まれており、ここにバーコード生成コードを配置します。

## 手順 3: バーコードジェネレータを初期化

まず、必要な名前空間をインポートします。

```csharp
using Aspose.BarCode.Generation;
```

次に、`Main` 内で PDF417 シンボロジーとエンコードしたいデータを指定して `BarcodeGenerator` をインスタンス化します。

```csharp
// Step 3: Initialize the generator for a PDF417 barcode
BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Åspóse.Barcóde©");
```

文字列には Unicode 文字が含まれており、Aspose.BarCode が非 ASCII 入力を正しく処理できることを示しています。ASCII のみで構わない場合は、任意のプレーン文字列に置き換えてください。

## 手順 4: バーコード XDimension（モジュールサイズ）を調整

**バーコード XDimension** は最小バー（モジュール）の幅を決定します。ピクセル単位で設定すると、最終画像サイズをピクセル単位で正確にコントロールできます。

```csharp
// Step 4: Set the module size – XDimension in pixels
generator.Parameters.Barcode.XDimension.Pixels = 2;
```

`2` ピクセルの値は、スキャン信頼性を損なうことなくコンパクトな画像を生成します。より大きなバーコードが必要な場合は値を上げ、非常に密なレイアウトの場合は下げてください。

## 手順 5: コンパクト PDF417 オプションを構成

PDF417 固有の 2 つの設定が視覚的なフットプリントに大きく影響します。

| 設定 | 意味 | コンパクト出力の典型的な値 |
|------|------|----------------------------|
| `Columns` | データ列数 | `3` |
| `Truncate` (コンパクトモード) | 右側のクワイエットゾーンを省略し、行数を削減 | `true` |

以下のように適用します。

```csharp
// Step 5: Use a small number of columns and enable compact mode
generator.Parameters.Barcode.Pdf417.Columns = 3;      // PDF417 columns
generator.Parameters.Barcode.Pdf417.Truncate = true; // compact PDF417
```

`Columns` を `3`、`Truncate = true` に設定すると、標準ラベルにきれいに収まる *コンパクト PDF417* バーコードが生成され、ほとんどのスキャナで読み取れます。

## 手順 6: バーコード画像を保存

最後に、バーコードをディスクに書き出します。例では PNG を保存しますが、Aspose.BarCode は BMP、JPEG、GIF、TIFF、SVG もサポートしています。

```csharp
// Step 6: Save the barcode as a PNG file
string outputPath = Path.Combine(Environment.CurrentDirectory, "CompactPdf417.png");
generator.Save(outputPath, BarCodeImageFormat.Png);
Console.WriteLine($"Barcode saved to {outputPath}");
```

`BarCodeImageFormat.Png` 定数は、ロスレス PNG を生成するようライブラリに指示します。これは後続の処理や印刷に最適です。

## 完全な実行可能ソースコード

```csharp
using System;
using System.IO;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // 1️⃣ Create the generator for PDF417 with Unicode text
        BarcodeGenerator generator = new BarcodeGenerator(
            EncodeTypes.Pdf417,
            "Åspóse.Barcóde©");

        // 2️⃣ Set module size – barcode XDimension in pixels
        generator.Parameters.Barcode.XDimension.Pixels = 2;

        // 3️⃣ Configure compact PDF417 options
        generator.Parameters.Barcode.Pdf417.Columns = 3;      // PDF417 columns
        generator.Parameters.Barcode.Pdf417.Truncate = true; // compact PDF417

        // 4️⃣ Save as PNG
        string outputPath = Path.Combine(
            Environment.CurrentDirectory,
            "CompactPdf417.png");

        generator.Save(outputPath, BarCodeImageFormat.Png);
        Console.WriteLine($"Barcode saved to {outputPath}");
    }
}
```

プログラムを実行すると、プロジェクトのルート フォルダーに `CompactPdf417.png` が作成されます。任意の画像ビューアで開くと、文字列 *Åspóse.Barcóde©* をエンコードした、きつく詰められた PDF417 バーコードが確認できます。

![Aspose.BarCode を使用して生成された PDF417 バーコードのスクリーンショット](placeholder-image.png "生成された PDF417 バーコード")

*画像代替テキスト: Aspose.BarCode を使用して生成された PDF417 バーコードのスクリーンショット* – この代替テキストはアクセシビリティと SEO のための主要キーワードを含みます。

## 結果の検証

1. PNG ファイルを開きます。バーコードは 3 列の垂直データ列で構成され、右側に余分なクワイエットゾーンがないコンパクトなレイアウトになっているはずです。  
2. PDF417 に対応したスマートフォンのバーコードスキャナで画像をスキャンします。デコードされたテキストは元の入力文字列と一致する必要があります。  
3. スキャンに失敗した場合は、`XDimension.Pixels` を `3` または `4` に増やしてみてください。モジュールが大きいほど、低解像度デバイスでの可読性が向上します。

## 一般的なバリエーションとエッジケース

### 1. 画像形式の変更

```csharp
generator.Save("CompactPdf417.svg", BarCodeImageFormat.Svg);
```

SVG はベクターベースで、任意のズームレベルでもバーコードが鮮明に保たれるため、ウェブページに最適です。

### 2. 大量データのエンコード

PDF417 は最大約 1.1 KB のテキストを格納できます。ペイロードが 3 列の容量を超えると、ライブラリは自動的に行を追加します。バーコードをコンパクトに保つための対策は次のとおりです。

- データ長を削減する（例: 完全なメッセージの代わりに識別子を使用）
- **PDF417 カラム** を増やす（例: `generator.Parameters.Barcode.Pdf417.Columns = 5;`）

### 3. トライアル透かしを除去するためのライセンス使用

```csharp
Aspose.BarCode.License license = new Aspose.BarCode.License();
license.SetLicense("Aspose.BarCode.lic");
```

実行ファイルの隣にライセンス ファイルを配置します。ライセンス適用後は、生成された画像に透かしが表示されなくなります。

### 4. 例外処理

```csharp
try
{
    generator.Save(outputPath, BarCodeImageFormat.Png);
}
catch (Exception ex)
{
    Console.Error.WriteLine($"Failed to generate barcode: {ex.Message}");
}
```

典型的な失敗例としては、書き込み権限が不足している、またはサポートされていない画像形式を指定した場合などがあります。

## 設定が重要な理由

- **バーコード XDimension** – 各バーの視覚的な太さを制御します。小さすぎると読み取り不能になり、大きすぎるとスペースを無駄にします。  
- **PDF417 カラム** – 列数が少ないほどバーコードは狭くなりますが、行数が増えて全体のサイズが大きくなる可能性があります。

## 次に学ぶべきことは？

以下のチュートリアルは、本ガイドで示したテクニックを基に、さらに関連するトピックを深く掘り下げたものです。各リソースには、ステップバイステップの説明と完全なコード例が含まれており、API の追加機能を習得したり、独自プロジェクトで代替実装アプローチを検討したりする際に役立ちます。

- [Aspose を使用した PDF417 バーコード生成 – 完全ガイド](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-with-aspose-complete-guide/)
- [C# でコンパクト設定を使用して PDF417 バーコードを生成](/barcode/english/net/compact-pdf417-encoding/generate-pdf417-barcode-with-compact-settings-in-c/)
- [C# で Aspose を使用してバーコードを保存し PDF417 を生成](/barcode/english/net/compact-pdf417-encoding/how-to-save-barcode-and-generate-pdf417-with-aspose-in-c/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}