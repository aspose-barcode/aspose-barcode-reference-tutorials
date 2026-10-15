---
category: general
date: 2026-10-08
description: C#でバーコード画像の作成方法を学び、DataBar スタック型全方向バーコードのアスペクト比の調整方法を発見しましょう。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode image
- how to adjust aspect ratio
- Aspose.BarCode C#
- DataBar stacked omni‑directional
- barcode X‑dimension
language: ja
lastmod: 2026-10-08
og_description: C#でバーコード画像を作成し、DataBarスタック型全方向バーコードのアスペクト比を調整する方法を、完全なコードサンプルとともに学びましょう。
og_image_alt: Result of create barcode image with aspect ratio 15 using Aspose.BarCode
og_title: C#でバーコード画像を作成する – ステップバイステップガイド
schemas:
- author: Aspose
  dateModified: '2026-10-08'
  description: Learn how to create barcode image in C# and discover how to adjust
    aspect ratio for DataBar stacked omni‑directional barcodes.
  headline: How to create barcode image and adjust its aspect ratio in C#
  type: TechArticle
- description: Learn how to create barcode image in C# and discover how to adjust
    aspect ratio for DataBar stacked omni‑directional barcodes.
  name: How to create barcode image and adjust its aspect ratio in C#
  steps:
  - name: Expected output
    text: 'After running the program you will find two PNG files in the execution
      directory:'
  - name: What if I need a different X‑dimension?
    text: You can change `barcodeGenerator.Parameters.Barcode.XDimension.Pixels` to
      any integer greater than zero. For very high‑resolution output (e.g., 300 dpi),
      a value of 3‑4 pixels often yields clearer results.
  - name: How do I choose the right aspect ratio?
    text: 'The optimal ratio depends on the scanning environment: * **Low‑profile
      labels** – use a smaller ratio (e.g., 10‑15) to keep the barcode compact. *
      **Large shipping containers** – a higher ratio (e.g., 25‑35) improves readability
      from a distance. * **Regulatory requirements** – some standards mandate'
  - name: Can I generate other barcode formats with the same code?
    text: Yes. Replace `EncodeTypes.DatabarStackedOmniDirectional` with any other
      `EncodeTypes` value (e.g., `EncodeTypes.Code128`). The rest of the code—X‑dimension,
      aspect ratio (if applicable), and saving—remains the same.
  - name: What if I need to create the image in a different format?
    text: '`BarCodeImageFormat` supports PNG, JPEG, BMP, GIF, and TIFF. Just change
      the second argument of `Save`, for example:'
  - name: Next steps
    text: '* Explore other symbologies such as **Code128** or **QR Code** by swapping
      the `EncodeTypes` value. * Combine the barcode generation with PDF creation
      (e.g., using Aspose.PDF) to embed barcodes directly into invoices. * Experiment
      with dynamic aspect‑ratio selection based on label size—this extends '
  type: HowTo
tags:
- barcode
- C#
- Aspose.BarCode
title: C#でバーコード画像を作成し、アスペクト比を調整する方法
url: /ja/python-java/general/how-to-create-barcode-image-and-adjust-its-aspect-ratio-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# C# でバーコード画像を作成し、アスペクト比を調整する方法

プログラムで **バーコード画像を作成** する必要がある場合、本ガイドでは完全な実行可能ソリューションを示します。**アスペクト比の調整方法** を DataBar スタックド・オムニディレクショナルバーコードで具体的に確認でき、これは小売や物流のアプリケーションで頻繁に求められる要件です。

このチュートリアルで学べること
* DataBar スタックド・オムニディレクショナルシンボル用に Aspose.BarCode の `BarcodeGenerator` を初期化する方法  
* ピクセル単位で X‑ディメンション（モジュール幅）を設定し、バーの太さを制御する方法  
* 2 つの異なるアスペクト比を適用し、各結果を PNG ファイルとして保存する方法  
* 出力結果を確認し、アスペクト比が重要になる理由を理解する方法  

外部ツールは不要です — Aspose.BarCode for .NET ライブラリと .NET 6（以降）開発環境だけで完結します。

## Aspose.BarCode でバーコード画像を作成する方法

最初のステップは、目的のシンボルとデータ文字列でジェネレータをインスタンス化することです。`EncodeTypes.DatabarStackedOmniDirectional` 列挙体は、Aspose.BarCode に DataBar スタックド・オムニディレクショナルバーコードを生成させます。これは GS1‑128 アプリケーションで広く使用されています。

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        // 1️⃣ Create a BarcodeGenerator for DataBar stacked omni‑directional.
        // The data string "(01)12345678901231" follows the GS1 Application Identifier format.
        BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
            EncodeTypes.DatabarStackedOmniDirectional,
            "(01)12345678901231");
```

**重要ポイント:** `BarcodeGenerator` オブジェクトはすべてのバーコード生成タスクのエントリーポイントです。シンボルと生データを事前に指定することで、生成される画像が GS1 標準に準拠していることが保証されます。

## X‑ディメンション（モジュール幅）の設定

X‑ディメンションは最も細いバー（モジュール）の幅を定義します。X‑ディメンションを大きくするとバーが太くなり、低解像度プリンターでの印刷に有利です。

```csharp
        // 2️⃣ Define the X‑dimension in pixels.
        // A value of 2 pixels provides a good balance between readability and file size.
        barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

**重要ポイント:** X‑ディメンションの調整は視覚的チューニングの一部です。エンコードされたデータには影響しませんが、さまざまなデバイスでのスキャン信頼性に影響します。

## アスペクト比の調整 – バージョン 1（15）

アスペクト比は DataBar バーコードの高さと幅の関係を制御します。`DataBar.AspectRatio` プロパティは整数値を受け取り、数値が大きいほどバーが高くなります。

```csharp
        // 3️⃣ Set the aspect ratio to 15 and save the first image.
        barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 15;
        barcodeGenerator.Save("DatabarAspectRatio15.png", BarCodeImageFormat.Png);
```

**重要ポイント:** アスペクト比 15 は小売スキャナーでのデフォルト設定として一般的です。生成される PNG（`DatabarAspectRatio15.png`）は高さが強調され、ハンドヘルドデバイスでのスキャン成功率が向上する可能性があります。

## アスペクト比の調整 – バージョン 2（30）

特定のラベル形式では、より高いバーコードが必要になることがあります。`Save` を再度呼び出す前に新しい整数値を代入するだけで、アスペクト比を簡単に変更できます。

```csharp
        // 4️⃣ Change the aspect ratio to 30 and save a second image.
        barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 30;
        barcodeGenerator.Save("DatabarAspectRatio30.png", BarCodeImageFormat.Png);
    }
}
```

**重要ポイント:** **アスペクト比の調整方法** を示すことで、同一データソースから複数のバーコード画像を生成でき、ジェネレータを再作成する必要がなくなります。これによりメモリ使用量が削減され、バッチ処理が高速化します。

### 期待される出力

プログラム実行後、実行ディレクトリに以下の 2 つの PNG ファイルが生成されます。

| ファイル名                     | アスペクト比 | ビジュアル説明 |
|-------------------------------|--------------|----------------|
| `DatabarAspectRatio15.png`    | 15           | 標準的な高さで、ほとんどの POS スキャナーに適合 |
| `DatabarAspectRatio30.png`    | 30           | バーが高く、ラベルが大きい場合や低解像度プリンターに有用 |

両画像は同一のエンコード済み GTIN `(01)12345678901231` を含みますが、アスペクト比に応じて視覚的な比率が異なります。

## よくある質問とエッジケースの対処

### X‑ディメンションを別の値にしたい場合は？

`barcodeGenerator.Parameters.Barcode.XDimension.Pixels` を 0 より大きい任意の整数に変更できます。たとえば 300 dpi の高解像度出力では、3〜4 ピクセルの値が比較的クリアな結果をもたらします。

### 適切なアスペクト比の選び方は？

最適な比率はスキャン環境によって異なります:
* **低プロファイルラベル** – コンパクトに保つため、比較的小さい比率（例: 10‑15）を使用  
* **大型出荷コンテナ** – 距離からの読み取り性を向上させるため、より高い比率（例: 25‑35）を推奨  
* **規制要件** – 一部の標準では最小高さが定められているため、GS1 仕様書で正確な数値を確認してください

### 同じコードで他のバーコード形式も生成できる？

はい。`EncodeTypes.DatabarStackedOmniDirectional` を任意の `EncodeTypes` 値（例: `EncodeTypes.Code128`）に置き換えるだけです。X‑ディメンション、アスペクト比（該当する場合）、保存処理は同じままです。

### 画像形式を別のものにしたい場合は？

`BarCodeImageFormat` は PNG、JPEG、BMP、GIF、TIFF をサポートしています。`Save` の第 2 引数を変更するだけです。例:

```csharp
barcodeGenerator.Save("barcode.jpg", BarCodeImageFormat.Jpeg);
```

## プロのコツ：バッチ処理でジェネレータを再利用する

多数のバーコードを同一の視覚設定で作成する必要がある場合、ジェネレータを一度だけインスタンス化し、`CodeText` プロパティだけを更新して `Save` を繰り返し呼び出します。これにより内部バッファの再割り当てオーバーヘッドが回避されます。

```csharp
// Example of batch creation
string[] gtins = { "(01)12345678901231", "(01)98765432109876", "(01)55555555555555" };
foreach (var gtin in gtins)
{
    barcodeGenerator.CodeText = gtin;
    barcodeGenerator.Save($"Barcode_{gtin.Substring(4, 6)}.png", BarCodeImageFormat.Png);
}
```

## まとめ

これで C# と Aspose.BarCode を使用して **バーコード画像を作成** し、DataBar スタックド・オムニディレクショナルシンボルの **アスペクト比を正確に調整** する方法が分かりました。X‑ディメンションとアスペクト比を制御することで、あらゆるスキャン環境やレイアウト要件に合致したバーコードを、シンプルかつ保守しやすい実装で生成できます。

### 次のステップ

* `EncodeTypes` の値を変更して **Code128** や **QR Code** など他のシンボルを試す  
* Aspose.PDF などと組み合わせて、請求書などの PDF に直接バーコードを埋め込む  
* ラベルサイズに応じた動的アスペクト比選択を実装し、**アスペクト比の調整方法** パターンをフル機能のラベル設計エンジンへ拡張する

サンプルを自由にカスタマイズし、結果を共有したり、コメントで質問を投稿したりしてください。コーディングを楽しんでください！

## 次に学ぶべきこと

以下のチュートリアルは、本ガイドで示したテクニックを基にした関連トピックを扱っています。各リソースには、ステップバイステップの解説と完全な動作コード例が含まれており、API の追加機能を習得したり、代替実装アプローチを自プロジェクトで試したりするのに役立ちます。

- [How to create databar stacked barcode in C# with Aspose.Barcode](/barcode/english/python-java/general/how-to-create-databar-stacked-barcode-in-c-with-aspose-barco/)
- [How to create barcode image with Aspose.Barcode in C#](/barcode/english/python-java/general/how-to-create-barcode-image-with-aspose-barcode-in-c/)
- [How to Adjust Barcode Size – Codablock F Aspect Ratio with Aspose.BarCode for .NET](/barcode/english/net/codablock-f-encoding/codablock-f-aspect-ratio-customization/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}