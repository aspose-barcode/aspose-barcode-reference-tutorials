---
category: general
date: 2026-08-09
description: Aspose バーコードの例で、C# のバーコードジェネレータを使用して、フルメタデータサポート付きの Macro PDF417 を作成する方法を示しています。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- aspose barcode example
- barcode generator c#
language: ja
lastmod: 2026-08-09
og_description: Aspose バーコードのサンプルは、C# のバーコードジェネレーターを使用して、ファイル ID、セグメント データ、タイムスタンプ、その他のメタデータを含む
  Macro PDF417 バーコードを生成する方法を示しています。
og_image_alt: Screenshot of a Macro PDF417 barcode generated with Aspose.BarCode in
  C#
og_title: Aspose バーコードの例 – C#でマクロ PDF417 を作成
schemas:
- author: Aspose
  dateModified: '2026-08-09'
  description: Aspose barcode example showing how to use a barcode generator C# to
    create a Macro PDF417 with full metadata support.
  headline: 'Aspose barcode example: generate Macro PDF417 in C#'
  type: TechArticle
tags:
- Aspose.BarCode
- C#
- Macro PDF417
title: Aspose バーコードの例：C#でMacro PDF417を生成
url: /ja/net/compact-pdf417-encoding/aspose-barcode-example-generate-macro-pdf417-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose バーコード例: C# で Macro PDF417 を生成する

**aspose barcode example** が必要で、Macro PDF417 バーコードを作成したい場合、このガイドでは **barcode generator C#** を使用した手順を示します。基本的なサイズ設定から Macro PDF417 のメタデータフィールド全体まで、必要な設定をすべて確認でき、下流処理に使用できる PNG 画像が得られます。

このチュートリアルは完全なワークフローをカバーし、各パラメータが重要な理由を解説し、すぐに実行できるコードサンプルを提供します。外部参照は不要で、コードをコピーして値を調整し、すぐに実行できます。

## 前提条件

- .NET 6.0 (またはそれ以降) がインストールされていること  
- Visual Studio 2022 または任意の C# 対応 IDE  
- **Aspose.BarCode for .NET** の有効なライセンス (この例では無料トライアルでも動作します)  

プロジェクトに Aspose.BarCode NuGet パッケージを追加します:

```bash
dotnet add package Aspose.BarCode
```

## ステップ 1: バーコードジェネレータ C# インスタンスの作成

最初のステップは、`EncodeTypes.MacroPdf417` 列挙値とエンコードしたいテキストを指定して `BarcodeGenerator` をインスタンス化することです。テキストには Unicode 文字を含めることができ、ライブラリが自動的に処理します。

```csharp
using Aspose.BarCode.Generation;
using System;

using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MacroPdf417, "Åspóse.Barcóde©"))
{
    // Subsequent steps are performed inside this using block.
```

*この重要性*: `EncodeTypes.MacroPdf417` はエンジンに Macro PDF417 シンボルを生成させ、セグメント化されたデータと追加のファイルレベルメタデータをサポートします。`using` ステートメントは、画像保存後にアンマネージドリソースが解放されることを保証します。

## ステップ 2: 基本的なバーコード外観の定義

Macro PDF417 バーコードは正方形のモジュールで構成されます。モジュールサイズと列数を制御することで、可読性とファイルサイズの両方に影響を与えます。

```csharp
    // Pixel size of a single module (X dimension)
    generator.Parameters.Barcode.XDimension.Pixels = 2;

    // Number of columns in the symbol; fewer columns produce a taller barcode
    generator.Parameters.Barcode.Pdf417.Columns = 5;
```

*この重要性*: `XDimension.Pixels` は視覚的密度を決定します。2 ピクセルの値は画面表示に適しつつ画像を小さく保ちます。レイアウト制約に合わせて列数を調整してください。列数を増やすと、より幅広く短いバーコードになります。

## ステップ 3: Macro PDF417 固有のメタデータ設定

Macro PDF417 は標準の PDF417 形式に、複数のバーコードセグメントから大きなファイルを再構築できるフィールドを追加します。各フィールドはオプションですが、設定することで API のフル機能を示すことができます。

```csharp
    // Unique identifier for the entire file
    generator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;

    // Identifier of the current segment (zero‑based)
    generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;

    // Total number of segments that compose the file
    generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;

    // Logical name of the source file
    generator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";

    // 16‑bit CCITT checksum for error detection
    generator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234;

    // Approximate size of the original file in bytes
    generator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400000;

    // Timestamp when the file was generated
    generator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2019, 11, 1);

    // Optional address fields for routing information
    generator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
    generator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";

    // Terminator indicates that this is the last segment
    generator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;
```

*この重要性*:  
- `MacroPdf417FileID` は同一論理ファイルに属するすべてのセグメントをリンクします。  
- `MacroPdf417SegmentID` と `MacroPdf417SegmentsCount` はデコーダがフラグメントを正しく順序付けできるようにします。  
- `MacroPdf417Checksum` はペイロード全体をデコードせずに迅速な整合性チェックを提供します。  
- `MacroPdf417FileSize` と `MacroPdf417TimeStamp` は下流システムが再構築されたファイルが元と一致するか検証できるようにします。  
- `MacroPdf417Addressee` / `MacroPdf417Sender` は物流や文書交換シナリオで有用です。  
- `MacroPdf417Terminator` を `Set` に設定すると、このバーコードが最終セグメントであることを示し、再構築アルゴリズムを簡素化します。

## ステップ 4: 生成されたバーコード画像の保存

最後に、バーコードを PNG ファイルとして書き出します。`Png`、`Jpeg`、`Bmp`、`Gif`、`Tiff` のいずれか、サポートされている形式を選択できます。

```csharp
    // Save the barcode image to the specified path
    generator.Save("YOUR_DIRECTORY/ExtPDF417Meta.png", BarCodeImageFormat.Png);
}
```

*この重要性*: PNG はロスレスのピクセルデータを保持し、スキャナが設定した正確なモジュールパターンを読み取れるようにします。形式を変更すると、視覚品質やファイルサイズに影響する可能性があります。

### 期待される出力

プログラムを実行すると **ExtPDF417Meta.png** という名前のファイルが作成されます。画像を開くと、テキスト “Åspóse.Barcóde©” がエンコードされた長方形の Macro PDF417 バーコードが表示され、視覚的密度は設定した 2 ピクセルの X 次元と一致します。PDF417 対応リーダで画像をスキャンすると、ステップ 3 で定義したすべてのメタデータフィールドが取得されます。

## 完全な動作例

以下のコードを新しいコンソールプロジェクト (`dotnet new console`) にコピーし、`YOUR_DIRECTORY` をマシン上に存在する絶対パスまたは相対パスに置き換えてください。

```csharp
using Aspose.BarCode.Generation;
using System;

namespace MacroPdf417Demo
{
    class Program
    {
        static void Main()
        {
            // Step 1: Create a barcode generator for Macro PDF417 with the desired text
            using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MacroPdf417, "Åspóse.Barcóde©"))
            {
                // Step 2: Define the basic barcode appearance
                generator.Parameters.Barcode.XDimension.Pixels = 2;          // pixel size of a single module
                generator.Parameters.Barcode.Pdf417.Columns = 5;           // number of columns in the symbol

                // Step 3: Set Macro PDF417 specific metadata
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
                generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;
                generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";
                generator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234; // CCITT‑16 example
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400000;
                generator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2019, 11, 1);
                generator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
                generator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
                generator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;

                // Step 4: Save the generated barcode image
                generator.Save("YOUR_DIRECTORY/ExtPDF417Meta.png", BarCodeImageFormat.Png);
            }

            Console.WriteLine("Macro PDF417 barcode generated successfully.");
        }
    }
}
```

プログラムを実行します (`dotnet run`)。実行後、指定した場所に PNG ファイルが作成されていることを確認してください。Macro PDF417 をサポートする任意のバーコードリーダーアプリを使用して、メタデータが正しく埋め込まれていることを確認します。

## 一般的なバリエーションとエッジケース

- **Different image formats**: 下流システムが別の形式を好む場合、`BarCodeImageFormat.Png` を `Jpeg`、`Bmp`、または `Tiff` に置き換えます。  
- **Changing module size**: `XDimension.Pixels` の値を大きくすると、低解像度スキャナでの読み取り信頼性が向上しますが、画像サイズが大きくなります。  
- **Multiple segments**: マルチセグメントファイルを生成するには、複数のバーコードを作成し、各バーコードで `MacroPdf417SegmentID` をインクリメントし、`MacroPdf417FileID` は一定に保ちます。最後のセグメントだけが `MacroPdf417Terminator` を設定すべきです。  
- **Unicode support**: ジェネレータは Unicode 文字を自動的にエンコードします。外部ファイルから読み込む場合は、ソース文字列が UTF-8 エンコーディングであることを確認してください。  
- **Error handling**: `using` ブロックを try‑catch でラップし、無効なパラメータ（例: 列数が範囲外）の場合に `BarCodeException` を捕捉します。

## プロのコツ

- **Performance**: 同じ設定で多数のバーコードを作成する場合、単一の `BarcodeGenerator` インスタンスを再利用し、保存間で `CodeText` プロパティだけを変更します。  
- **File size estimation**: `MacroPdf417FileSize` フィールドは元のペイロードのバイト数と一致すべきです。不一致は下流の検証失敗を引き起こす可能性があります。  
- **Testing**: 生成したバーコードを Aspose の組み込みデコーダ (`BarCodeReader`) とサードパーティ製スキャナの両方で検証し、相互運用性を確保します。

## 結論

この **aspose barcode example

## 次に学ぶべきことは？

以下のチュートリアルは、本ガイドで示した手法に基づく密接に関連するトピックを取り上げています。各リソースには、ステップバイステップの解説と完全な動作コード例が含まれており、追加の API 機能を習得し、独自プロジェクトで代替実装アプローチを検討するのに役立ちます。

- [バーコードの作成方法 – Compact PDF417 (Aspose.BarCode 使用)](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [Aspose.BarCode for .NET を使用した Code 16K の静音領域の作成方法](/barcode/english/net/code-16k-encoding/code-16k-quiet-zone-settings/)
- [Aspose.BarCode for .NET を使用した ITF-14 の静音領域の作成方法](/barcode/english/net/itf-14-barcode-customization/itf-14-barcode-quiet-zone-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}