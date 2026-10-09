---
category: general
date: 2026-10-09
description: Aspose.BarCode を使用して C# で PDF417 バーコードを作成する方法を学びます – 完全なメタデータサポートを備えた
  Macro PDF417 を生成します。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create pdf417 barcode c#
- macro pdf417 c#
- aspose barcode c#
- barcode generator c#
lastmod: 2026-10-09
og_description: Aspose.BarCode を使用して C# で PDF417 バーコードを作成する方法を学びます – ファイル ID、セグメント
  データ、タイムスタンプなどを含む完全なメタデータサポートを備えた Macro PDF417 を生成します。
og_image_alt: Screenshot of a Macro PDF417 barcode generated with Aspose.BarCode in
  C#
og_title: Aspose.BarCode を使用した C# で PDF417 バーコードを作成する方法
schemas:
- author: Aspose
  dateModified: '2026-10-09'
  description: Aspose barcode example showing how to use a barcode generator C# to
    create a Macro PDF417 with full metadata support.
  headline: 'Aspose barcode example: generate Macro PDF417 in C#'
  type: TechArticle
tags:
- aspose barcode
- pdf417 barcode
- c# barcode generation
- macro pdf417
title: Aspose.BarCode を使用した C# で PDF417 バーコードを作成する方法
url: /ja/net/compact-pdf417-encoding/aspose-barcode-example-generate-macro-pdf417-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# C# と Aspose.BarCode を使用して PDF417 バーコードを作成する方法

PDF417 バーコード C# を迅速かつ確実に作成する必要がある場合、このチュートリアルでは Aspose.BarCode を使用した完全な手順を説明します。基本的なサイズ設定から Macro PDF417 メタデータフィールドの全セットまで、必要な設定をすべて確認でき、最終的に下流処理用の PNG 画像が得られます。

## クイック回答
- **PDF417 バーコードを生成するライブラリはどれですか？** Aspose.BarCode for .NET.
- **例の出力フォーマットは何ですか？** ロスレス PNG 画像.
- **ライセンスは必要ですか？** サンプルには無料トライアルで動作しますが、実稼働には商用ライセンスが必要です.
- **サポートされている .NET バージョンはどれですか？** .NET 6.0 以降.
- **バーコードにメタデータを追加できますか？** はい – Macro PDF417 はファイル ID、セグメント数、タイムスタンプなどをサポートします.

## PDF417 バーコードとは何ですか？

PDF417 バーコードは、シンボルあたり約 1 KB のデータをエンコードでき、マルチセグメントファイル用のオプションのマクロメタデータをサポートするスタック型リニアシンボルです。複数行のスタック型リニアパターンで構成され、高いデータ容量を実現しつつ、標準的な 2‑D スキャナで読み取れます。このフォーマットには信頼性向上のためのエラー訂正レベルが含まれ、オプションのマクロ機能により、メタデータで大きなファイルを複数のバーコードに分割し、再構築を支援できます。

## PDF417 に Aspose.BarCode を使用する理由

Aspose.BarCode は **50 以上のバーコードシンボロジー** をサポートし、最大 **2 000 列** の Macro PDF417 バーコードを生成でき、**10 MB** を超えるファイルでもペイロード全体をメモリにロードせずに処理できます。この定量的な機能により、高スループットのエンタープライズシナリオが円滑に実行され、豊富なカスタマイズオプションが提供されます。

## 前提条件

開始する前に、以下がインストールされていることを確認してください：

- .NET 6.0（またはそれ以降）がインストールされていること  
- Visual Studio 2022 または任意の C# 対応 IDE  
- **Aspose.BarCode for .NET** の有効なライセンス（この例では無料トライアルで動作します）  

プロジェクトに Aspose.BarCode NuGet パッケージを追加します：

```bash
dotnet add package Aspose.BarCode
```

## C# で PDF417 バーコードを作成する方法？

`BarcodeGenerator` はバーコード画像を作成するための主要クラスです。  
`EncodeTypes.MacroPdf417` はバーコード生成のために Macro PDF417 シンボロジーを選択します。  
`Save` は生成されたバーコードを画像ファイルに書き込みます。

`BarcodeGenerator` を `EncodeTypes.MacroPdf417` 列挙体と対象テキストでロードし、`Save` を呼び出すだけで、3 行で完結する作成フローが完了します。ジェネレータは Unicode を自動的に処理し、`using` ステートメントは画像保存後にアンマネージドリソースが解放されることを保証します。

### 手順 1: バーコードジェネレータ C# インスタンスの作成

`BarcodeGenerator` クラスはバーコード画像を作成および構成します。  

`EncodeTypes.MacroPdf417` 列挙値とエンコードしたいテキストで `BarcodeGenerator` をインスタンス化します。テキストは Unicode 文字を含めることができ、ライブラリが自動的に処理します。

```csharp
using Aspose.BarCode.Generation;
using System;

using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MacroPdf417, "Åspóse.Barcóde©"))
{
    // Subsequent steps are performed inside this using block.
```

*Why this matters*: `EncodeTypes.MacroPdf417` はエンジンに Macro PDF417 シンボルを生成させ、セグメント化データと追加のファイルレベルメタデータをサポートします。`using` ステートメントは画像保存後にアンマネージドリソースが解放されることを保証します。

### 手順 2: 基本的なバーコード外観の定義

`XDimension.Pixels` は各バーコードモジュールのピクセルサイズを設定します。

Macro PDF417 バーコードは正方形モジュールで構成されます。モジュールサイズと列数を制御することで、読み取りやすさとファイルサイズの両方に影響します。

```csharp
    // Pixel size of a single module (X dimension)
    generator.Parameters.Barcode.XDimension.Pixels = 2;

    // Number of columns in the symbol; fewer columns produce a taller barcode
    generator.Parameters.Barcode.Pdf417.Columns = 5;
```

*Why this matters*: `XDimension.Pixels` は視覚的密度を決定します。2 ピクセルの値は画面表示に適しつつ画像を小さく保ちます。レイアウト制約に合わせて列数を調整してください。列数が多いほど幅が広く、短いバーコードになります。

### 手順 3: Macro PDF417 固有のメタデータを設定

`MacroPdf417FileID` はすべてのバーコードセグメントが属するファイルを識別します。

Macro PDF417 は標準 PDF417 フォーマットを拡張し、複数のバーコードセグメントから大きなファイルを再構築できるフィールドを提供します。各フィールドはオプションですが、設定することで API の完全な機能を示すことができます。

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

*Why this matters*:  
- `MacroPdf417FileID` は同一論理ファイルに属するすべてのセグメントをリンクします。  
- `MacroPdf417SegmentID` と `MacroPdf417SegmentsCount` はデコーダがフラグメントを正しく再順序付けできるようにします。  
- `MacroPdf417Checksum` はペイロード全体をデコードせずに迅速な整合性チェックを提供します。  
- `MacroPdf417FileSize` と `MacroPdf417TimeStamp` は下流システムが再構築されたファイルが元のファイルと一致することを検証できるようにします。  
- `MacroPdf417Addressee` / `MacroPdf417Sender` は物流や文書交換シナリオで有用です。  
- `MacroPdf417Terminator` を `Set` に設定すると、このバーコードが最終セグメントであることを示し、再構築アルゴリズムが簡素化されます。

### 手順 4: 生成されたバーコード画像を保存

`Save` はバーコード画像を指定されたファイルパスに書き込みます。

最後に、バーコードを PNG ファイルに書き出します。サポートされている任意の形式（`Png`, `Jpeg`, `Bmp`, `Gif`, `Tiff`）を選択できます。

```csharp
    // Save the barcode image to the specified path
    generator.Save("YOUR_DIRECTORY/ExtPDF417Meta.png", BarCodeImageFormat.Png);
}
```

*Why this matters*: PNG はロスレスのピクセルデータを保持し、スキャナが設定した正確なモジュールパターンを読み取れるようにします。形式を変更すると視覚品質やファイルサイズに影響する可能性があります。

#### 期待される出力

完全なプログラムを実行すると **ExtPDF417Meta.png** という名前のファイルが作成されます。画像を開くと、テキスト “Åspóse.Barcóde©” がエンコードされた長方形の Macro PDF417 バーコードが表示され、視覚的密度は設定した 2 ピクセルの X 次元と一致します。PDF417 対応リーダで画像をスキャンすると、ステップ 3 で定義したすべてのメタデータフィールドが返されます。

## 完全な動作例

以下のコードを新しいコンソールプロジェクト（`dotnet new console`）にコピーし、`YOUR_DIRECTORY` をマシン上に存在する絶対または相対パスに置き換えてください。

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

`dotnet run` でプログラムを実行します。実行後、指定した場所に PNG ファイルが作成されていることを確認してください。Macro PDF417 をサポートする任意のバーコードリーダーアプリでメタデータが正しく埋め込まれていることを確認します。

## 一般的なバリエーションとエッジケース

- **異なる画像フォーマット**: 下流システムが別のフォーマットを好む場合は、`BarCodeImageFormat.Png` を `Jpeg`、`Bmp`、または `Tiff` に置き換えます。  
- **モジュールサイズの変更**: 大きな `XDimension.Pixels` の値は低解像度スキャナでのスキャン信頼性を向上させますが、画像サイズが大きくなります。  
- **複数セグメント**: マルチセグメントファイルを作成するには、バーコードの系列を生成し、各バーコードで `MacroPdf417SegmentID` をインクリメントし、`MacroPdf417FileID` は一定に保ちます。最後のセグメントだけが `MacroPdf417Terminator` を設定すべきです。  
- **Unicode サポート**: ジェネレータは Unicode 文字を自動的にエンコードします。外部ファイルから読み込む場合は、ソース文字列が UTF‑8 エンコーディングであることを確認してください。  
- **エラーハンドリング**: `using` ブロックを try‑catch でラップし、無効なパラメータ（例: 列数が範囲外）の場合に `BarCodeException` を捕捉します。

## プロのコツ

- **パフォーマンス**: 同じ設定で多数のバーコードを作成する場合は、単一の `BarcodeGenerator` インスタンスを再利用し、保存間で `CodeText` プロパティだけを変更します。  
- **ファイルサイズの見積もり**: `MacroPdf417FileSize` フィールドは元のペイロードのバイト数と一致すべきです。不一致は下流の検証失敗を引き起こす可能性があります。  
- **テスト**: 生成されたバーコードを Aspose の組み込みデコーダ（`BarCodeReader`）とサードパーティ製スキャナの両方で検証し、相互運用性を確保します。

## 結論

この **Aspose.BarCode** の例は、**PDF417 バーコード C#** をフルマクロメタデータサポートで作成する方法を示し、堅牢なバーコードベースのデータ交換パイプラインを構築するための確固たる基盤を提供します。

## 次に学ぶべきことは？

以下のチュートリアルは、本ガイドで示した手法を基にした密接に関連するトピックをカバーしています。各リソースには、ステップバイステップの解説付きの完全な動作コード例が含まれ、追加の API 機能を習得し、独自プロジェクトで代替実装アプローチを探求するのに役立ちます。

- [バーコード作成方法 – Compact PDF417 with Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [Aspose.BarCode for .NET を使用した Code 16K のクワイエットゾーン作成方法](/barcode/english/net/code-16k-encoding/code-16k-quiet-zone-settings/)
- [Aspose.BarCode for .NET を使用した ITF-14 のクワイエットゾーン作成方法](/barcode/english/net/itf-14-barcode-customization/itf-14-barcode-quiet-zone-configuration/)

---

**最終更新日:** 2026-10-09  
**テスト環境:** Aspose.BarCode 24.11 for .NET  
**作者:** Aspose

## 関連チュートリアル

- [Aspose を使用した C での Pdf417 バーコード画像生成方法](/barcode/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-image-in-c-with-aspose/)
- [バーコード作成方法 – Compact PDF417 with Aspose.BarCode](/barcode/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [バーコードジェネレータチュートリアル – Pdf417 バーコード生成方法](/barcode/net/compact-pdf417-encoding/barcode-generator-tutorial-how-to-generate-pdf417-barcode-in/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}