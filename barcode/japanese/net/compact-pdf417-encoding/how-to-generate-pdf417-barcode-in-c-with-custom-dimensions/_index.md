---
category: general
date: 2026-09-07
description: C#でPDF417バーコードを生成し、バーコードのサイズを正確に設定する方法を学びましょう。ステップバイステップのガイドに従ってPNG画像を作成してください。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate pdf417 barcode
- how to generate pdf417 barcode
- how to set barcode dimensions
language: ja
lastmod: 2026-09-07
og_description: C#でPDF417バーコードを生成し、バーコードのサイズ設定方法を学びましょう。このチュートリアルでは、完全な実行可能なサンプルを示しています。
og_image_alt: Generated PDF417 barcode image with custom dimensions
og_title: C#でPDF417バーコードを生成する – 寸法付き完全ガイド
schemas:
- author: Aspose
  dateModified: '2026-09-07'
  description: Generate PDF417 barcode in C# and learn how to set barcode dimensions
    for precise control. Follow this step‑by‑step guide to create a PNG image.
  headline: How to generate PDF417 barcode in C# with custom dimensions
  type: TechArticle
- description: Generate PDF417 barcode in C# and learn how to set barcode dimensions
    for precise control. Follow this step‑by‑step guide to create a PNG image.
  name: How to generate PDF417 barcode in C# with custom dimensions
  steps:
  - name: Expected output
    text: '- **File:** `Pdf417Layout.png` (PNG, lossless) - **Dimensions:** Determined
      by `XDimension` (2 px) × (columns × rows) matrix - **Content:** A scannable
      PDF417 barcode encoding the Unicode string `Åspóse.Barcóde©`'
  - name: What if I need a larger image for printing?
    text: Increase `XDimension.Pixels` to 4 or 5. Larger values produce a higher‑resolution
      barcode but also increase file size.
  - name: Can I encode more data than the example string?
    text: Yes. PDF417 can hold up to 1,850 characters. Just replace the text argument
      in the `BarcodeGenerator` constructor. If the data exceeds the matrix capacity,
      the library automatically adds extra rows.
  - name: How does error correction work?
    text: 'PDF417 includes built‑in error correction. You can adjust its level via:'
  - name: What if the barcode appears blurry on screen?
    text: 'Make sure the output image’s DPI matches the display environment. You can
      set DPI when saving:'
  - name: Next steps
    text: '- Explore **how to generate PDF417 barcode** with different image formats
      (JPEG, BMP). - Learn **how to set barcode dimensions** dynamically based on
      user input or device DPI. - Integrate the barcode generation into an ASP.NET
      Core API to serve barcodes on demand.'
  type: HowTo
tags:
- barcode generation
- PDF417
- C#
title: C#でカスタム寸法のPDF417バーコードを生成する方法
url: /ja/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-with-custom-dimensions/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# C#でカスタムサイズのPDF417バーコードを生成する方法

.NET アプリケーションで **PDF417 バーコードを生成** する必要がある場合、このガイドで具体的な手順を示します。バーコードのサイズを制御しながら PNG 画像を作成する、完全に実行可能なサンプルが確認できます。

PDF417 バーコードの生成は、在庫管理システム、搭乗券、機密文書などで一般的な要件です。このチュートリアルでは、**バーコードのサイズを設定**する方法も学び、出力がレイアウト要件に合致するようにします。

## 前提条件

- .NET 6.0 SDK 以降がインストールされていること  
- Visual Studio 2022（または任意の C# 対応 IDE）  
- **Aspose.BarCode for .NET** NuGet パッケージ（または PDF417 をサポートする互換ライブラリ）  

以下のコマンドでパッケージを追加できます。

```bash
dotnet add package Aspose.BarCode
```

## 手順 1: PDF417 バーコードジェネレータの作成

最初のステップは、`EncodeTypes.Pdf417` タイプとエンコードしたいテキストを指定して `BarcodeGenerator` のインスタンスを作成することです。ジェネレータオブジェクトはバーコードのすべての設定を保持します。

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Step 1: Create a PDF417 barcode generator with the desired text
        BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
            EncodeTypes.Pdf417,
            "Åspóse.Barcóde©");
```

**重要ポイント:** `EncodeTypes.Pdf417` 列挙体はライブラリに PDF417 シンボルを使用させ、大量のデータペイロードとエラー訂正をサポートします。テキスト文字列は Unicode 文字を含められるため、追加の作業なしで国際的な記号をエンコードできます。

## 手順 2: バーコードのサイズを設定する方法

各モジュール（最小の黒/白の正方形）のサイズを制御することで、画像全体の解像度が決まります。`XDimension.Pixels` プロパティは 1 モジュールのピクセル幅を設定します。

```csharp
        // Step 2: Set the size of each barcode module (pixel resolution)
        barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

**重要ポイント:** `XDimension` を大きくすると高解像度画像になり、遠距離からの印刷やスキャンに適します。逆に小さい値にするとウェブ用のファイルサイズが削減されます。

## 手順 3: PDF417 のレイアウトを定義する（列と行）

PDF417 では、列数と行数を指定してマトリックス形状に影響を与えることができます。これにより可読性やバーコードの実際のサイズが変わります。

```csharp
        // Step 3: Define the layout – number of columns and rows in the PDF417 matrix
        barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 4; // 4 columns
        barcodeGenerator.Parameters.Barcode.Pdf417.Rows    = 9; // 9 rows
```

**重要ポイント:** 列と行を調整することで、特定のスペースにバーコードを収めたり、スキャナのアスペクト比要件を満たしたりできます。データがマトリックスを完全に埋めない場合、ライブラリが自動的に余白を追加します。

## 手順 4: バーコードを PNG 画像として保存する

最後に、生成したバーコードをファイルに書き出します。PNG はロスレス品質を保つため、後続の処理に最適です。

```csharp
        // Step 4: Save the generated barcode as a PNG image
        barcodeGenerator.Save("Pdf417Layout.png", BarCodeImageFormat.Png);
    }
}
```

プログラムを実行すると、`Pdf417Layout.png` がプロジェクトの出力フォルダーに生成されます。画像は以下のようになります。

![カスタムサイズの PDF417 バーコード画像](og_image_placeholder.png)

*画像の代替テキスト: カスタムサイズの PDF417 バーコード画像*  

**重要ポイント:** PNG で保存することで、設定したモジュールサイズが正確に保持され、下流のスキャンアプリケーションにとって重要です。

## 1 つのブロックにまとめた完全な例

以下は、コピーして貼り付け、必要に応じて出力パスを変更する以外はそのまま実行できる完全なプログラムです。

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Create a PDF417 barcode generator with the desired text
        BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
            EncodeTypes.Pdf417,
            "Åspóse.Barcóde©");

        // Set the size of each barcode module (pixel resolution)
        barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;

        // Define the layout – number of columns and rows in the PDF417 matrix
        barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 4; // 4 columns
        barcodeGenerator.Parameters.Barcode.Pdf417.Rows    = 9; // 9 rows

        // Save the generated barcode as a PNG image
        barcodeGenerator.Save("Pdf417Layout.png", BarCodeImageFormat.Png);
    }
}
```

### 期待される出力

- **ファイル:** `Pdf417Layout.png` (PNG、ロスレス)  
- **サイズ:** `XDimension` (2 px) × (columns × rows) マトリックスで決定  
- **内容:** Unicode 文字列 `Åspóse.Barcóde©` をエンコードしたスキャン可能な PDF417 バーコード  

## よくある質問とエッジケース

### 印刷用により大きな画像が必要な場合は？

`XDimension.Pixels` を 4 または 5 に増やします。大きな値は高解像度のバーコードを生成しますが、ファイルサイズも増加します。

### サンプル文字列以上のデータをエンコードできますか？

はい。PDF417 は最大 1,850 文字まで保持できます。`BarcodeGenerator` コンストラクタのテキスト引数を置き換えるだけです。データがマトリックス容量を超える場合、ライブラリが自動的に余分な行を追加します。

### エラー訂正はどのように機能しますか？

PDF417 には組み込みのエラー訂正があり、以下のようにレベルを調整できます。

```csharp
barcodeGenerator.Parameters.Barcode.Pdf417.ErrorLevel = 5; // 0‑8, higher = more correction
```

レベルを上げると堅牢性が向上しますが、バーコードは大きくなります。

### 画面上でバーコードがぼやけて見える場合は？

出力画像の DPI が表示環境に合っていることを確認してください。保存時に DPI を設定できます。

```csharp
barcodeGenerator.Save("Pdf417Layout.png", BarCodeImageFormat.Png, 300);
```

## プロのコツ

- **プロのコツ:** 実際に使用するスキャナで必ず生成したバーコードをテストしてください。デバイスによってモジュールサイズやクワイエットゾーンの許容範囲が異なります。  
- **注意点:** 非常に小さい `XDimension` 値（< 1 px）は、高 DPI 画面で見えない線になることがあります。  
- **Web アプリ向けのヒント:** PNG を `Cache-Control: public, max-age=86400` で配信し、再生成のオーバーヘッドを削減します。

## 結論

これで C# で **PDF417 バーコードを生成**し、任意の要件に合わせて **バーコードのサイズを正確に設定**する方法が分かりました。完全な実行可能サンプルは、カスタム列/行レイアウトとモジュールサイズで PNG 画像を作成し、印刷やデジタル配布にすぐに使用できることを示しています。

### 次のステップ

- 異なる画像形式（JPEG、BMP）で **PDF417 バーコードを生成**する方法を探る。  
- ユーザー入力やデバイス DPI に基づいて **バーコードのサイズを動的に設定**する方法を学ぶ。  
- バーコード生成を ASP.NET Core API に統合し、オンデマンドでバーコードを提供する。

エラー訂正、余白、カラーなど、他の PDF417 設定も自由に試してみてください。コーディングを楽しんでください！

## 次に学ぶべきことは？

以下のチュートリアルは、本ガイドで示した手法を基にした密接に関連するトピックを取り上げています。各リソースは、ステップバイステップの解説と完全な動作コード例を含み、追加の API 機能を習得し、プロジェクトで代替実装アプローチを探求するのに役立ちます。

- [PDF417 バーコードのエラーレベル設定方法 – 完全ガイド](/barcode/english/net/compact-pdf417-encoding/how-to-set-error-level-in-pdf417-barcode-complete-guide/)
- [C# でバーコードを保存する方法 – PDF417 バーコード生成](/barcode/english/net/compact-pdf417-encoding/how-to-save-barcode-in-c-generate-pdf417-barcodes/)
- [C# で PDF417 バーコードを生成 – 完全ガイド](/barcode/english/net/compact-pdf417-encoding/generate-pdf417-barcode-in-c-complete-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}