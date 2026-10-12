---
category: general
date: 2026-10-12
description: C# を使用してマイクロ PDF417 バーコードを作成し、バーコードを PNG に変換する方法を学びましょう。フルコードとヒント付きのステップバイステップガイドです。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create micro PDF417 barcode
- convert barcode to PNG
- micro PDF417 C# example
- GS1 micro PDF417 generation
- barcode image settings
language: ja
lastmod: 2026-10-12
og_description: C#でマイクロPDF417バーコードを作成し、バーコードをPNGに変換します。標準版とGS1版の両方を生成する完全ガイドをご覧ください。
og_image_alt: Screenshot of a generated micro PDF417 barcode saved as a PNG file
og_title: マイクロPDF417バーコードを作成しPNGに変換する – C#チュートリアル
schemas:
- author: Aspose
  dateModified: '2026-10-12'
  description: Learn to create micro PDF417 barcode and convert barcode to PNG using
    C#. Step‑by‑step guide with full code and tips.
  headline: How to create micro PDF417 barcode and convert it to PNG in C#
  type: TechArticle
tags:
- barcode
- C#
- PDF417
title: C#でマイクロPDF417バーコードを作成し、PNGに変換する方法
url: /ja/net/compact-pdf417-encoding/how-to-create-micro-pdf417-barcode-and-convert-it-to-png-in/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# C# でマイクロ PDF417 バーコードを作成し PNG に変換する方法

.NET アプリケーションで **マイクロ PDF417 バーコードを作成** する必要がある場合、このチュートリアルで手順を正確に示します。標準の Micro PDF417 バーコードと GS1 準拠バージョンの両方を生成し、**バーコードを PNG に変換** して印刷やウェブ表示などの下流利用に使える、完全で実行可能なサンプルをご覧いただけます。

バーコードの生成は単にメソッドを呼び出すだけではなく、適切なモジュールサイズ、列数、エンコーディング形式を選択することでスキャンの信頼性が決まります。本ガイドの最後までに、各設定が重要な理由と、プロジェクトに合わせて調整する方法が理解できるようになります。

## 前提条件

開始する前に、以下が揃っていることを確認してください：

| Requirement | Reason |
|-------------|--------|
| .NET 6.0 SDK or later | C# コンソール アプリのランタイムを提供します |
| Visual Studio 2022 (or any C# IDE) | 編集やデバッグが容易になります |
| **Aspose.BarCode for .NET** NuGet package | `BarcodeGenerator`、`EncodeTypes`、`BarCodeImageFormat` クラスを提供します |
| Write permission to the output folder | PNG ファイルを作成する `Save` 呼び出しに必要です |

CLI を使用して Aspose.BarCode パッケージを追加できます：

```bash
dotnet add package Aspose.BarCode
```

## 手順 1: 最小限のコンソール プロジェクトを設定する

新しいコンソール プロジェクトを作成し、バーコード ライブラリを参照します。以下の `Program.cs` には必要なコードがすべて含まれており、外部ファイルは不要です。

```csharp
using System;
using Aspose.BarCode.Generation;   // Core barcode generation classes
using Aspose.BarCode;               // For BarCodeImageFormat enum

namespace MicroPdf417Demo
{
    internal class Program
    {
        static void Main()
        {
            // Define the folder where PNG files will be saved
            string outputFolder = Environment.CurrentDirectory;

            // ------------------------------------------------------------
            // 1️⃣ Create a Micro PDF417 barcode generator with plain data
            // ------------------------------------------------------------
            BarcodeGenerator microGen = new BarcodeGenerator(
                EncodeTypes.MicroPdf417,          // Micro PDF417 symbology
                "Micro data");                    // Simple alphanumeric payload

            // ------------------------------------------------------------
            // 2️⃣ Adjust the X dimension (module size) and set column count
            // ------------------------------------------------------------
            // XDimension controls the physical size of each barcode module.
            // A value of 2 pixels gives a compact yet readable barcode.
            microGen.Parameters.Barcode.XDimension.Pixels = 2;

            // For Micro PDF417 you can limit the number of columns.
            // Four columns keep the barcode small enough for labels.
            microGen.Parameters.Barcode.Pdf417.Columns = 4;

            // ------------------------------------------------------------
            // 3️⃣ Convert barcode to PNG and save the image
            // ------------------------------------------------------------
            string microPath = System.IO.Path.Combine(outputFolder, "MicroPdf417.png");
            microGen.Save(microPath, BarCodeImageFormat.Png);
            Console.WriteLine($"Standard Micro PDF417 saved to: {microPath}");

            // ------------------------------------------------------------
            // 4️⃣ Create a GS1 Micro PDF417 barcode with AI‑encoded data
            // ------------------------------------------------------------
            // GS1 syntax requires Application Identifiers (AIs) wrapped in parentheses.
            // Example: (01) – GTIN, (21) – serial number.
            BarcodeGenerator gs1MicroGen = new BarcodeGenerator(
                EncodeTypes.Gs1MicroPdf417,
                "(01)12345678901231(21)ABC123");

            // ------------------------------------------------------------
            // 5️⃣ Set the X dimension for the GS1 barcode (same as step 2)
            // ------------------------------------------------------------
            gs1MicroGen.Parameters.Barcode.XDimension.Pixels = 2;

            // ------------------------------------------------------------
            // 6️⃣ Convert barcode to PNG and save the GS1 image
            // ------------------------------------------------------------
            string gs1Path = System.IO.Path.Combine(outputFolder, "GS1MicroPdf417.png");
            gs1MicroGen.Save(gs1Path, BarCodeImageFormat.Png);
            Console.WriteLine($"GS1 Micro PDF417 saved to: {gs1Path}");

            // End of demo
            Console.WriteLine("Barcode generation complete.");
        }
    }
}
```

### 各行が重要な理由

* **`EncodeTypes.MicroPdf417` vs `EncodeTypes.Gs1MicroPdf417`** – 前者はシンプルな Micro PDF417 バーコードを生成し、後者は GS1 標準に従いアプリケーション識別子 (AI) を埋め込みます。下流システムが GS1 データを期待するかどうかで選択してください。
* **`XDimension.Pixels = 2`** – モジュール幅を制御します。値が小さいほど画像は密になりますが、低解像度スキャナでは読めなくなる可能性があります。2 ピクセルは多くのラベルプリンタで安全なデフォルトです。
* **`Pdf417.Columns = 4`** – Micro PDF417 では列数を制限でき、全体の幅を縮小できます。4 列は短いペイロードでもデータ容量を犠牲にせず、バーコードをコンパクトに保ちます。
* **`BarCodeImageFormat.Png`** – PNG はロスレス品質を保ち、バーコードの鮮明さに不可欠です。そのため **バーコードを PNG に変換** しており、JPEG ではありません。

## 手順 2: プログラムを実行し、出力を確認する

1. プロジェクトをビルド: `dotnet build`。
2. 実行: `dotnet run`。

以下のようなコンソール メッセージが表示されます：

```
Standard Micro PDF417 saved to: C:\Path\To\Project\MicroPdf417.png
GS1 Micro PDF417 saved to: C:\Path\To\Project\GS1MicroPdf417.png
Barcode generation complete.
```

生成された PNG ファイルを任意の画像ビューアで開きます。どちらの画像も鮮明で高コントラストなバーコードを示し、スキャンの準備ができています。

### 期待されるビジュアル結果

| Barcode type | Appearance |
|--------------|------------|
| **Micro PDF417** | 4 列の小さな長方形パターンで、ほとんどの 2‑D バーコードスキャナで読み取れます。 |
| **GS1 Micro PDF417** | 同じサイズですが GS1 AI をエンコードします。GS1 を理解するスキャナは GTIN とシリアル番号を返します。 |

スキャナが画像を読み取れない場合は、`XDimension.Pixels` を **3** または **4** に増やすか、標準の Micro PDF417 の列数を減らしてみてください。

## よくある落とし穴と回避策

| Issue | Cause | Fix |
|-------|-------|-----|
| 印刷後のバーコードがぼやける | 低 DPI のプリンタ設定 | PNG を 300 dpi 以上でエクスポートするか、プリンタドライバにスケーリングを任せます。 |
| スキャナが「無効なデータ」を返す | GS1 AI 形式が欠落または不正 | すべての AI が丸括弧で囲まれ、GS1 仕様に従っていることを確認します（例: GTIN‑14 の場合は `(01)`）。 |
| 画像ファイルが作成されない | 出力フォルダに書き込み権限がない | プログラムを管理者権限で実行するか、`Environment.GetFolderPath(Environment.SpecialFolder.MyDocuments)` のようなフォルダを選択します。 |
| ラベルに対してバーコードが大きすぎる | デフォルトの列数が多すぎる | `Pdf417.Columns` を減らす（例: **3**）か、`XDimension` を増やして全体サイズを縮小します。 |

## サンプルの拡張

* **異なる画像形式** – ワークフローで必要な場合は `BarCodeImageFormat.Png` を `Jpeg` や `Bmp` に置き換えます。PNG はロスレス品質の点で依然として最適です。
* **動的データ** – ユーザー入力やデータベースの値を `BarcodeGenerator` コンストラクタに渡して、リアルタイムにバーコードを生成します。
* **バッチ生成** – CSV ファイルから行を読み取り、各バーコードをユニークなファイル名で保存するループで生成ロジックを囲みます。

## 結論

これで C# で **マイクロ PDF417 バーコードを作成** し、標準シナリオと GS1 準拠シナリオの両方で **バーコードを PNG に変換** する方法が分かりました。完全で実行可能なコードは、X ディメンション、列数、エンコーディングタイプという重要な設定を示しており、コンパクトで高品質な 2‑D バーコードが必要な任意の .NET プロジェクトにこのソリューションを適用できます。

*次のステップ*: Aspose.BarCode がサポートする他のシンボル（例: QR、DataMatrix）を調査し、高解像度印刷のためにさまざまな `XDimension` 値を試すか、生成した PNG をオンデマンドでバーコードを提供する Web API に統合します。

## 次に学ぶべきことは？

以下のチュートリアルは、本ガイドで示した手法を基にした密接に関連するトピックを取り上げています。各リソースには、ステップバイステップの解説と完全な動作コード例が含まれており、追加の API 機能を習得し、プロジェクトで代替実装アプローチを検討するのに役立ちます。

- [C# でマイクロ PDF417 バーコードを作成し PNG として保存する方法](/barcode/english/net/compact-pdf417-encoding/how-to-create-micro-pdf417-barcode-in-c-and-save-it-as-png/)
- [C# でバーコード PNG を作成 – GS1 マイクロ PDF417 完全ガイド](/barcode/english/net/gs1-barcode-encoding/create-barcode-png-in-c-full-guide-to-gs1-micro-pdf417/)
- [C# でマイクロ PDF417 バーコードを生成 – 完全ガイド](/barcode/english/net/compact-pdf417-encoding/generate-micro-pdf417-barcode-in-c-complete-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}