---
category: general
date: 2026-07-24
description: Aspose.BarCode を使用して C# で PDF417 バーコードを生成します。数分でコンパクトモードの PDF417 バーコードを
  C# で作成する方法を学びましょう。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate pdf417 barcode
- create pdf417 barcode c#
- c# barcode generator pdf417
- how to generate pdf417 barcode
language: ja
lastmod: 2026-07-24
og_description: Aspose.BarCode を使用して C# で PDF417 バーコードを迅速に生成します。このチュートリアルでは、コンパクトモードで
  PDF417 バーコードを C# で作成する方法を、セットアップ、コード、検証を含めて解説します。
og_image_alt: Screenshot of generated compact PDF417 barcode saved as PNG using C#
  code
og_title: C#でPDF417バーコードを生成 – クイックガイド
schemas:
- author: Aspose
  dateModified: '2026-07-24'
  description: Generate PDF417 barcode in C# using Aspose.BarCode. Learn how to create
    PDF417 barcode C# with compact mode in minutes.
  headline: Generate PDF417 Barcode in C# – Create PDF417 Barcode C#
  type: TechArticle
- description: Generate PDF417 barcode in C# using Aspose.BarCode. Learn how to create
    PDF417 barcode C# with compact mode in minutes.
  name: Generate PDF417 Barcode in C# – Create PDF417 Barcode C#
  steps:
  - name: '**Data definition** – PDF417 can store up to ~1850 characters, but we keep
      it short for the demo. Unicode support means those accented characters won’t
      break anything.'
    text: '**Data definition** – PDF417 can store up to ~1850 characters, but we keep
      it short for the demo. Unicode support means those accented characters won’t
      break anything.'
  - name: '**Generator construction** – The `EncodeTypes.Pdf417` enum value tells
      Aspose which symbology to use; swapping it for `EncodeTypes.QR` would give you
      a QR code instead.'
    text: '**Generator construction** – The `EncodeTypes.Pdf417` enum value tells
      Aspose which symbology to use; swapping it for `EncodeTypes.QR` would give you
      a QR code instead.'
  - name: '**X‑dimension** – This controls the width of each module (the tiny squares
      that make up the barcode). A value of `2` pixels yields a crisp image that’s
      still readable when printed at 300 dpi.'
    text: '**X‑dimension** – This controls the width of each module (the tiny squares
      that make up the barcode). A value of `2` pixels yields a crisp image that’s
      still readable when printed at 300 dpi.'
  - name: '**PDF417 options** – `Columns` influences the barcode’s aspect ratio; fewer
      columns make the image taller, which can be useful for receipts. `Truncate`
      (also called *Compact mode*) removes the start/stop pattern padding, reducing
      file size without sacrificing data integrity.'
    text: '**PDF417 options** – `Columns` influences the barcode’s aspect ratio; fewer
      columns make the image taller, which can be useful for receipts. `Truncate`
      (also called *Compact mode*) removes the start/stop pattern padding, reducing
      file size without sacrificing data integrity.'
  - name: '**Output path** – Using `Environment.CurrentDirectory` ensures the image
      lands next to the executable, making it easy to locate during development.'
    text: '**Output path** – Using `Environment.CurrentDirectory` ensures the image
      lands next to the executable, making it easy to locate during development.'
  - name: '**Saving** – `BarCodeImageFormat.Png` gives lossless quality, perfect for
      further processing or embedding in PDFs.'
    text: '**Saving** – `BarCodeImageFormat.Png` gives lossless quality, perfect for
      further processing or embedding in PDFs.'
  type: HowTo
tags:
- barcode
- pdf417
- csharp
title: C#でPDF417バーコードを生成 – PDF417バーコードをC#で作成
url: /ja/net/compact-pdf417-encoding/generate-pdf417-barcode-in-c-create-pdf417-barcode-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# C# で PDF417 バーコードを生成する – 完全プログラミングウォークスルー

無限に続くフォーラムスレッドを探さずに **PDF417 バーコードを生成** したいと思ったことはありませんか？ あなたは一人ではありません。チケットシステムや安全な ID カードを作成する場合、あるいは印刷可能な形式でデータを埋め込む簡単な方法が必要な場合でも、PDF417 フォーマットをマスターすれば試行錯誤に費やす時間を大幅に削減できます。

このガイドでは、人気の Aspose.BarCode ライブラリを使用して **PDF417 バーコード C# を作成** する **完全な実行可能サンプル** を順を追って解説します。NuGet パッケージのインストールからコンパクトモードの調整まで網羅しているので、コードをコピー＆ペーストしてすぐに結果を確認できます。

## 学べること

- .NET プロジェクトに Aspose.BarCode ライブラリを設定する方法。  
- カスタムテキスト、モジュールサイズ、列数を指定して **PDF417 バーコードを生成** する正確な C# 文。  
- 密度の高いデータに対して *Compact*（Truncate）オプションを切り替える重要性。  
- バーコードを PNG として保存し、出力を検証する方法。  

バーコードの経験は不要です。C# と Visual Studio（またはお好みの IDE）に関する基本的な知識があれば大丈夫です。最後には、どのプロジェクトにも組み込める再利用可能なメソッドが手に入ります。

## 前提条件

| 要件 | 理由 |
|-------------|----------------|
| .NET 6.0 以降（または .NET Framework 4.7 以上） | Aspose.BarCode は両方をサポートしており、最新ランタイムの方がパフォーマンスが向上します。 |
| Visual Studio 2022（または C# 拡張機能付き VS Code） | IntelliSense とデバッグが容易になります。 |
| インターネット接続（最初の NuGet 復元用） | ライブラリは NuGet.org から取得します。 |
| 基本的な C# の知識 | クラス構造やメソッド呼び出しを理解するために必要です。 |

これらが揃っていれば、さっそく始めましょう。

## Aspose.BarCode NuGet パッケージのインストール

ターミナルでプロジェクトフォルダーを開き、次のコマンドを実行します：

```bash
dotnet add package Aspose.BarCode
```

または Visual Studio で **Dependencies → Manage NuGet Packages** を右クリックし、*Aspose.BarCode* を検索して **Install** をクリックします。この一行で `BarcodeGenerator`、`EncodeTypes`、`BarCodeImageFormat` など、今回使用するすべての型が導入されます。

> **プロのコツ:** インストール後、ソリューションをクリーン＆リビルドしてアセンブリが正しく参照されていることを確認してください。

## PDF417 バーコード生成 – 設定と依存関係

まず最初に、必要な名前空間をスコープに取り込む `using` ブロックが必要です。

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;
```

これらの名前空間により、ジェネレータクラスやバーコード種別の列挙体にアクセスできます。特別なことはなく、3 行だけでバーコード作成の準備が整います。

## PDF417 バーコード C# 作成 – ステップバイステップ実装

以下は、文字列 `"Åspóse.Barcóde©"` からコンパクトな PDF417 バーコードを作成し、`CompactPdf417.png` として保存する **自己完結型コンソールプログラム** です。必要に応じてテキストを好きなものに置き換えて構いません。ジェネレータは Unicode 文字をそのまま扱います。

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

namespace Pdf417Demo
{
    class Program
    {
        static void Main(string[] args)
        {
            // 1️⃣ Define the data you want to encode.
            string data = "Åspóse.Barcóde©";

            // 2️⃣ Initialise the generator for PDF417.
            //    EncodeTypes.Pdf417 tells Aspose we want a PDF417 barcode.
            BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, data);

            // 3️⃣ Adjust the module (X‑dimension) size.
            //    Smaller values give a tighter image; 2 pixels works well for most screens.
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // 4️⃣ Configure PDF417‑specific options.
            //    • Columns = 3 → fewer columns, taller barcode.
            //    • Truncate = true → enables Compact mode, which removes unnecessary padding.
            generator.Parameters.Barcode.Pdf417.Columns = 3;
            generator.Parameters.Barcode.Pdf417.Truncate = true;

            // 5️⃣ Choose the output folder – adjust as needed.
            string outputPath = System.IO.Path.Combine(
                Environment.CurrentDirectory, "CompactPdf417.png");

            // 6️⃣ Save the image as PNG.
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"✅ PDF417 barcode saved to: {outputPath}");
        }
    }
}
```

### 各ステップの重要ポイント

1. **データ定義** – PDF417 は最大約 1850 文字まで格納可能ですが、デモ用に短くしています。Unicode 対応によりアクセント付き文字も問題なく処理されます。  
2. **ジェネレータ構築** – `EncodeTypes.Pdf417` 列挙値が Aspose にシンボロジーを指示します。`EncodeTypes.QR` に変更すれば QR コードが生成されます。  
3. **X‑dimension** – 各モジュール（バーコードを構成する小さな正方形）の幅を制御します。`2` ピクセルに設定すると、300 dpi で印刷しても読み取りやすい鮮明な画像になります。  
4. **PDF417 オプション** – `Columns` はバーコードのアスペクト比に影響し、列数が少ないほど画像は縦長になります。レシートなどで有用です。`Truncate`（*Compact mode* とも呼ばれる） は開始/停止パターンの余白を除去し、データの完全性を損なうことなくファイルサイズを削減します。  
5. **出力パス** – `Environment.CurrentDirectory` を使用すると、実行ファイルと同じディレクトリに画像が保存され、開発中の位置特定が容易です。  
6. **保存** – `BarCodeImageFormat.Png` はロスレス品質を提供し、後続の処理や PDF への埋め込みに最適です。

プログラムを実行します（`dotnet run` または Visual Studio で **F5**）。数秒後にコンソールにファイル位置が表示され、PNG がプロジェクトフォルダーに生成されます。

![Generate PDF417 barcode example](generated-pdf417.png)

*画像代替テキスト: generate pdf417 barcode example – C# で作成したコンパクト PDF417 バーコードの PNG 画像。*

## コンパクトモードの設定 – c# barcode generator pdf417 Options

より大きなバーコードが必要な場合（遠距離からのスキャンを想定）には、`Columns` と `Rows` プロパティを調整します。以下は代替構成を示す簡単なスニペットです：

```csharp
// Increase columns for a wider, shorter barcode.
generator.Parameters.Barcode.Pdf417.Columns = 6;

// Disable Compact mode if the scanning hardware struggles with it.
generator.Parameters.Barcode.Pdf417.Truncate = false;

// Optionally set error correction level (0–8). Higher values increase redundancy.
generator.Parameters.Barcode.Pdf417.ErrorCorrectionLevel = 5;
```

> **よくある質問:** *Truncate を無効にすると既存のスキャナーが動作しなくなるでしょうか？*  
> 通常は問題ありません。ほとんどの最新スキャナーはフルサイズとコンパクト PDF417 の両方を認識します。ただし、レガシーハードウェアを対象とする場合は `Truncate` を `false` のままにしておく方が安全です。

## 保存と検証 – how to generate pdf417 barcode Output

保存後は任意の画像ビューアで PNG を開くことができます。バーコードが意図したデータを正しくエンコードしているか二重チェックしたい場合は、Aspose の `BarCodeReader` を使用します：



## 次に学ぶべきことは？

以下のチュートリアルは、本ガイドで示したテクニックを基にした密接に関連するトピックを扱っています。各リソースには、ステップバイステップの解説と完全な動作コード例が含まれており、追加の API 機能を習得したり、独自プロジェクトで代替実装アプローチを探求したりするのに役立ちます。

- [Compact PDF417 を Aspose.BarCode で作成する方法](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [Aspose.BarCode for .NET でカスタムアスペクト比の Aztec バーコードを生成する方法](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)
- [java barcode library – Aspose を使用して PDF にバーコードを追加する](/barcode/english/java/barcode-basics/adding-barcode-to-pdf-document/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}