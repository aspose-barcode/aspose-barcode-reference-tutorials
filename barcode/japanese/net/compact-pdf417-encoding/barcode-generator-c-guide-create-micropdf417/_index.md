---
category: general
date: 2026-09-29
description: Barcode generator C# ガイドでは、MicroPdf417 バーコードの生成、サイズの変更、列の設定、そして数行でバーコードのサイズをカスタマイズする方法を示しています。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- barcode generator c#
- how to generate barcode
- how to change dimensions
- how to set columns
- customize barcode size
language: ja
lastmod: 2026-09-29
og_description: Barcode generator C# ガイドでは、MicroPdf417 バーコードの生成、サイズ変更、列数設定、そして数行のコードでバーコードサイズをカスタマイズする方法を紹介しています。
og_image_alt: Screenshot of a MicroPdf417 barcode generated with a C# barcode generator
og_title: C# バーコードジェネレーターガイド – MicroPdf417 の作成とカスタマイズ
schemas:
- author: GroupDocs
  dateModified: '2026-09-29'
  description: Barcode generator C# guide shows how to generate a MicroPdf417 barcode,
    change dimensions, set columns, and customize barcode size in just a few lines.
  headline: 'Barcode generator C# guide: create MicroPdf417'
  type: TechArticle
tags:
- barcode
- C#
- MicroPdf417
- barcode generation
title: バーコードジェネレータ C# ガイド：MicroPdf417 の作成
url: /ja/net/compact-pdf417-encoding/barcode-generator-c-guide-create-micropdf417/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# バーコードジェネレータ C# ガイド: MicroPdf417 の作成

.NET プロジェクト向けに **barcode generator C#** が必要な場合、このチュートリアルでは最初から MicroPdf417 バーコードを作成する手順を説明します。**バーコードの生成方法**、寸法の変更、列の設定、そして **バーコードサイズのカスタマイズ** を簡単に学べます。

MicroPdf417 は、部品のラベル、チケット、在庫タグなどの小さなラベル付けに適したコンパクトな 2‑D シンボルです。このガイドの最後までに、バーコードの PNG 画像を出力する完全な実行可能コンソール アプリケーションが作成でき、各パラメータが最終サイズにどのように影響するかが理解できるようになります。

## 前提条件

* .NET 6.0 SDK またはそれ以降 (コードは .NET Framework 4.7+ でも動作します)
* C# 対応 IDE (Visual Studio、VS Code、Rider など)
* **GroupDocs.Barcode** NuGet パッケージ – 以下でインストールします  

  ```bash
  dotnet add package GroupDocs.Barcode
  ```

追加の外部ツールは必要ありません。ライブラリがエンコード、レンダリング、ファイル保存をすべて処理します。

## Barcode generator C#: ジェネレータの初期化

最初のステップは `BarcodeGenerator` のインスタンスを作成し、シンボロジー (`EncodeTypes.MicroPdf417`) とエンコードしたいデータを指定することです。

```csharp
using System;
using GroupDocs.Barcode;
using GroupDocs.Barcode.Enums;
using GroupDocs.Barcode.Common;

namespace MicroPdf417Demo
{
    class Program
    {
        static void Main()
        {
            // Step 1 – create the generator with the desired text
            var generator = new BarcodeGenerator(
                EncodeTypes.MicroPdf417,
                "Åspóse.Barcóde©"
            );

            // Subsequent configuration steps go here...

            // Save the final image
            generator.Save("MicroPdf417.png", BarCodeImageFormat.Png);
            Console.WriteLine("Barcode saved as MicroPdf417.png");
        }
    }
}
```

**なぜ重要か:**  
`BarcodeGenerator` はすべてのバーコード操作のエントリーポイントです。コンストラクタは選択した **EncodeTypes** (MicroPdf417) を生データ文字列にバインドします。ライブラリは “Å” や “©” といった Unicode 文字を自動的に処理するため、追加のエンコードロジックは不要です。

## バーコードの寸法を変更する方法

バーコードの読み取りやすさは、モジュール幅（X‑dimension）に大きく依存します。ピクセル数を増やすとバーが太くなり、特に低解像度ディスプレイでのスキャンが容易になります。

```csharp
// Step 2 – adjust the X‑dimension (module width) to 2 pixels
generator.Parameters.Barcode.XDimension.Pixels = 2;
```

**説明:**  
`XDimension.Pixels` は単一のバーコードモジュールの幅を制御します。デフォルトは 1 ピクセルで、高 DPI モニターでは細く見えることがあります。2 ピクセルに上げると、エンコードされたデータに影響を与えずに全体の幅が2倍になります。

**ヒント:** バーコードを 300 dpi で印刷する場合、3 ピクセルまたは 4 ピクセルの値がサイズとスキャン信頼性のバランスとして最適になることが多いです。

## サイズ制御のために列数を設定する方法

MicroPdf417 では列数（最大 4）を指定できます。列が少ないとバーコードが高くなり、列が多いと幅が広くなりますが高さは短くなります。この値を調整することが **バーコードサイズのカスタマイズ** の主な方法です。

```csharp
// Step 3 – set the maximum number of columns (4 is the limit for MicroPdf417)
generator.Parameters.Barcode.Pdf417.Columns = 4;
```

**なぜ機能するか:**  
`Pdf417.Columns` プロパティは、MicroPdf417 を含むすべての PDF417 系シンボロジーで共有されています。最大値 (4) に設定すると、データが最も広いレイアウトに分散され、全体の高さが減少します。よりコンパクトな高さが必要な場合は、列数を 2 または 3 に下げてください。

**エッジケース:** データ文字列が長い場合、列数に関係なくライブラリが自動的に行数を増やして内容を収めることがあります。予測可能なサイズにするため、ペイロードは 50 文字未満に抑えてください。

## 異なる出力向けにバーコードサイズをカスタマイズする

X‑dimension と列数に加えて、適切な画像フォーマットと DPI を選択することで最終画像サイズに影響を与えることができます。PNG はロスレスでウェブ表示に最適ですが、BMP や TIFF は高品質印刷に適している場合があります。

```csharp
// Step 4 – save as PNG (lossless) with default 96 dpi
generator.Save("MicroPdf417.png", BarCodeImageFormat.Png);
```

より高い DPI が必要な場合は、明示的に設定できます：

```csharp
generator.Parameters.Image.DpiX = 300;
generator.Parameters.Image.DpiY = 300;
generator.Save("MicroPdf417_300dpi.png", BarCodeImageFormat.Png);
```

**結果:** 保存された PNG ファイルには、設定した寸法を保持した鮮明な MicroPdf417 バーコードが含まれます。任意の画像ビューアでファイルを開き、視覚的なサイズを確認してください。

### 期待される出力

プログラムを実行すると、**MicroPdf417.png**（DPI を設定した場合は **MicroPdf417_300dpi.png**）という名前のファイルが生成されます。バーコードは以下のイラストと同様になります：

![Barcode generator C# output showing a MicroPdf417 PNG](barcode-micro-pdf417.png)

*代替テキスト:* *Barcode generator C# の出力で MicroPdf417 PNG を示す*

## 簡単にコピー＆ペーストできる完全なソースコード

```csharp
using System;
using GroupDocs.Barcode;
using GroupDocs.Barcode.Enums;
using GroupDocs.Barcode.Common;

namespace MicroPdf417Demo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Create the generator with the desired text
            var generator = new BarcodeGenerator(
                EncodeTypes.MicroPdf417,
                "Åspóse.Barcóde©"
            );

            // 2️⃣ Change dimensions – make modules 2 pixels wide
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // 3️⃣ Set columns – use the maximum of 4 for a wider, shorter barcode
            generator.Parameters.Barcode.Pdf417.Columns = 4;

            // (Optional) Increase DPI for high‑resolution output
            // generator.Parameters.Image.DpiX = 300;
            // generator.Parameters.Image.DpiY = 300;

            // 4️⃣ Save the barcode as a PNG image
            generator.Save("MicroPdf417.png", BarCodeImageFormat.Png);

            Console.WriteLine("Barcode saved as MicroPdf417.png");
        }
    }
}
```

コードを新しいコンソール プロジェクトに貼り付け、NuGet パッケージを復元し、`dotnet run` を実行します。コンソールに画像の場所が表示され、プロジェクト フォルダーに生成されたバーコードが確認できます。

## よくある質問とトラブルシューティング

| 質問 | 回答 |
|----------|--------|
| **バーコードがぼやけて見える場合はどうすればいいですか？** | `XDimension.Pixels` または DPI (`Parameters.Image.DpiX/Y`) を増やします。どちらもモジュールを拡大し、視覚的な忠実度を向上させます。 |
| **別の画像フォーマットを使用できますか？** | はい。`BarCodeImageFormat.Png` を `Jpeg`、`Bmp`、または `Tiff` に置き換えます。PNG はロスレス品質の最も安全な選択肢です。 |
| **データに絵文字が含まれています—エンコードされますか？** | MicroPdf417 は UTF‑8 をサポートしているため、ほとんどの絵文字は正しくエンコードされます。エラーが発生した場合は、文字列が正しく正規化されているか (`System.Text.Encoding.UTF8`) を確認してください。 |
| **他のシンボロジーはどうやって生成しますか？** | `EncodeTypes.MicroPdf417` を `EncodeTypes` の他の任意の値に変更します ( |

## 次に学ぶべきことは？

以下のチュートリアルは、本ガイドで示した手法に基づく密接に関連したトピックを取り上げています。各リソースには、ステップバイステップの解説と完全な動作コード例が含まれており、追加の API 機能を習得し、プロジェクトで代替実装アプローチを検討するのに役立ちます。

- [C# でバーコード画像を生成する方法 – MicroPdf417 ガイド](/barcode/english/net/compact-pdf417-encoding/how-to-generate-barcode-image-in-c-micropdf417-guide/)
- [C# でカスタム寸法の PDF417 バーコードを生成する方法](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-with-custom-dimensions/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}