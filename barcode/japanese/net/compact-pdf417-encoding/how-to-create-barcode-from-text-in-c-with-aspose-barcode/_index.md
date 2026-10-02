---
category: general
date: 2026-10-02
description: C#でAspose.BarCodeを使用してテキストからバーコードを作成します。PDF417バーコードの生成方法を学び、コンパクトモードでのPDF417バーコードの生成方法をご確認ください。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode from text
- generate pdf417 barcode
- how to generate pdf417 barcode
language: ja
lastmod: 2026-10-02
og_description: C# と Aspose.BarCode を使用してテキストからバーコードを作成します。このガイドでは、PDF417 バーコードの生成方法と、コンパクトモードでの
  PDF417 バーコードの生成方法を示します。
og_image_alt: Screenshot showing create barcode from text output as a PNG image
og_title: C#でテキストからバーコードを作成する – ステップバイステップガイド
schemas:
- author: Aspose
  dateModified: '2026-10-02'
  description: Create barcode from text in C# using Aspose.BarCode. Learn how to generate
    PDF417 barcode and see how to generate PDF417 barcode in compact mode.
  headline: How to create barcode from text in C# with Aspose.BarCode
  type: TechArticle
- description: Create barcode from text in C# using Aspose.BarCode. Learn how to generate
    PDF417 barcode and see how to generate PDF417 barcode in compact mode.
  name: How to create barcode from text in C# with Aspose.BarCode
  steps:
  - name: '**Invalid characters** – PDF417 supports Unicode, but some older scanners
      may reject non‑ASCII symbols. Test with your target hardware.'
    text: '**Invalid characters** – PDF417 supports Unicode, but some older scanners
      may reject non‑ASCII symbols. Test with your target hardware.'
  - name: '**File path permissions** – Ensure the directory you write to is writable;
      otherwise `Save` throws an `UnauthorizedAccessException`.'
    text: '**File path permissions** – Ensure the directory you write to is writable;
      otherwise `Save` throws an `UnauthorizedAccessException`.'
  - name: '**Image size** – Very high `XDimension` values produce large PNG files.
      Keep the pixel size between 1 and 4 for most screen‑display scenarios.'
    text: '**Image size** – Very high `XDimension` values produce large PNG files.
      Keep the pixel size between 1 and 4 for most screen‑display scenarios.'
  type: HowTo
tags:
- barcode
- PDF417
- C#
- Aspose
title: C# と Aspose.BarCode でテキストからバーコードを作成する方法
url: /ja/net/compact-pdf417-encoding/how-to-create-barcode-from-text-in-c-with-aspose-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# C# と Aspose.BarCode を使用してテキストからバーコードを作成する方法

.NET アプリケーションで **テキストからバーコードを作成** する必要がある場合、このガイドが全工程を案内します。**PDF417 バーコードを生成** する実行可能なサンプルを確認でき、コンパクトレイアウトで **PDF417 バーコードを生成する方法** についても解説します。

プログラムでバーコードを生成すれば、手作業を省き、すべてのドキュメントで一貫性を確保できます。このチュートリアルの最後までに、請求書、チケット、身分証明書などに埋め込める PDF417 バーコードを含む PNG ファイルが作成できるようになります。

## 必要なもの

- .NET 6.0 SDK 以降（コードは .NET Framework 4.7.2+ でも動作します）
- Visual Studio 2022 または C# をサポートする任意のエディタ
- **Aspose.BarCode for .NET** の NuGet ライセンス（無料トライアルでテスト可能）

> **Pro tip:** CLI で NuGet パッケージを追加するとプロジェクトがすっきりします:  
> `dotnet add package Aspose.BarCode`

## 手順 1: コンソールプロジェクトの設定

新しいコンソールアプリケーションを作成し、Aspose.BarCode ライブラリを参照します。

```bash
dotnet new console -n BarcodeDemo
cd BarcodeDemo
dotnet add package Aspose.BarCode
```

`dotnet new console` コマンドで `Program.cs` ファイルが生成されます。このファイルを以下の完全なサンプルに置き換えます。

## 手順 2: テキストからバーコードを作成する方法 – コアコード

`Program.cs` を開き、内容を以下のコードに置き換えます。各行にはその目的を説明するコメントが付いています。

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;
using Aspose.BarCode.Image;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Define the text that will be encoded.
            // The PDF417 symbology supports a wide range of Unicode characters.
            string textToEncode = "Åspóse.Barcóde©";

            // 2️⃣ Create a BarcodeGenerator for PDF417 using the desired text.
            // This object holds all settings and performs the rendering.
            BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, textToEncode);

            // 3️⃣ Adjust module (X) dimension for better readability on screen.
            // XDimension defines the width of a single barcode column in pixels.
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // 4️⃣ Set the number of columns – a smaller column count yields a denser image.
            generator.Parameters.Barcode.Pdf417.Columns = 3;

            // 5️⃣ Enable compact mode by truncating the data.
            // Truncate = true removes padding, making the barcode smaller while preserving scannability.
            generator.Parameters.Barcode.Pdf417.Truncate = true;

            // 6️⃣ Choose the output path. Adjust the folder to match your environment.
            string outputPath = "CompactPdf417.png";

            // 7️⃣ Save the barcode as a PNG image.
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"Barcode saved to {outputPath}");
        }
    }
}
```

### 各設定が重要な理由

| Setting | Purpose |
|--------|----------|
| `EncodeTypes.Pdf417` | PDF417 シンボロジーを選択します。これは二次元マトリックスに大量のデータを格納できます。 |
| `XDimension.Pixels = 2` | 各モジュールの幅を制御します。2 ピクセルの値は可読性とファイルサイズのバランスが取れています。 |
| `Pdf417.Columns = 3` | 列数を減らし、データを失うことなくバーコードをよりコンパクトにします。 |
| `Pdf417.Truncate = true` | コンパクトモードを有効にし、不要な余白を除去してバーコードを短くします。 |
| `BarCodeImageFormat.Png` | PNG はロスレス品質を保持し、さらなる処理や印刷に最適です。 |

## 手順 3: PDF417 バーコードの生成 – サンプル実行

プロジェクトをビルドして実行します。

```bash
dotnet run
```

実行が完了すると次のように表示されます:

```
Barcode saved to CompactPdf417.png
```

`CompactPdf417.png` を開いて結果を確認してください。この画像には文字列 **Åspóse.Barcóde©** をエンコードした PDF417 バーコードが含まれています。

![テキストからバーコードを作成 – PNG として保存された PDF417 バーコード](barcode-example.png)

*Alt text: テキストからバーコードを作成 – PNG として保存された PDF417 バーコード*

## 手順 4: カスタムエラー訂正付き PDF417 バーコードの生成方法（オプション）

スキャン環境がノイズの多い場合、エラー訂正レベルを上げることができます:

```csharp
generator.Parameters.Barcode.Pdf417.ErrorLevel = 5; // Levels 0–5, higher = more redundancy
```

エラー訂正レベルを上げるとバーコードは大きくなりますが、損傷に対する耐性が向上します。

## 手順 5: よくある落とし穴とエッジケースの対処法

1. **Invalid characters** – PDF417 は Unicode をサポートしますが、古いスキャナの中には非 ASCII 記号を拒否するものがあります。対象ハードウェアでテストしてください。
2. **File path permissions** – 書き込み先ディレクトリが書き込み可能であることを確認してください。そうでない場合、`Save` は `UnauthorizedAccessException` をスローします。
3. **Image size** – `XDimension` の値が非常に高いと大きな PNG ファイルになります。ほとんどの画面表示シナリオではピクセルサイズを 1〜4 の範囲に保ってください。

## まとめ

これで、C# と Aspose.BarCode を使用して **テキストからバーコードを作成** する方法、コンパクトレイアウトで **PDF417 バーコードを生成** する方法、そしてカスタム設定で **PDF417 バーコードを生成** する具体的な手順が分かりました。上記の完全な実行可能コードは任意の .NET プロジェクトにコピーでき、異なるテキスト入力や出力形式（例: JPEG、BMP）に合わせて調整可能です。

## 次のステップ

- `EncodeTypes` を変更して、QR Code や Code128 など他のシンボロジーを試してみましょう。
- 生成した PNG を Aspose.PDF を使って PDF に統合し、エンドツーエンドのドキュメント作成を実現します。
- `generator.Parameters.Barcode.Pdf417.Rows` を試して、垂直方向の密度を制御します。

例を自由に変更し、バーコードを自分のアプリケーションに組み込み、コミュニティと結果を共有してください。コーディングを楽しんで！

## 次に学ぶべきことは？

以下のチュートリアルは、本ガイドで示した手法を基にした密接に関連するトピックを扱っています。各リソースには、ステップバイステップの解説と完全な動作コード例が含まれており、追加の API 機能を習得し、独自プロジェクトで代替実装アプローチを検討するのに役立ちます。

- [C# で PDF417 バーコードを生成する – コンパクト例](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-compact-example/)
- [C# でコンパクトモードで PDF417 バーコードを作成する](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-in-c-with-compact-mode/)
- [C# で PDF417 バーコードを生成する – ステップバイステップガイド](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-step-by-step-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}