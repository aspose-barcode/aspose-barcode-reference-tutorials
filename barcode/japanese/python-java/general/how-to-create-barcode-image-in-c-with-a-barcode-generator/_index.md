---
category: general
date: 2026-10-02
description: バーコードジェネレーターを使用してC#でバーコード画像を作成し、バーコードのピクセルサイズを制御し、カスタムバーコード寸法に合わせてバーコードの高さを調整します。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode image
- barcode generator c#
- barcode pixel size
- adjust barcode height
- custom barcode dimensions
language: ja
lastmod: 2026-10-02
og_description: バーコードジェネレーターを使用してC#でバーコード画像を作成します。バーコードのピクセルサイズの設定、バーコードの高さの調整、カスタムバーコード寸法の定義方法を学びましょう。
og_image_alt: Sample DataBar Omnidirectional barcode saved at 30 px height and 60 px
  height
og_title: C#でバーコード画像を作成 – バーコードジェネレーターとカスタムサイズのガイド
schemas:
- author: Aspose
  dateModified: '2026-10-02'
  description: Create barcode image in C# using a barcode generator, control barcode
    pixel size and adjust barcode height for custom barcode dimensions.
  headline: How to create barcode image in C# with a barcode generator
  type: TechArticle
tags:
- barcode
- C#
- image generation
title: バーコードジェネレーターを使用してC#でバーコード画像を作成する方法
url: /ja/python-java/general/how-to-create-barcode-image-in-c-with-a-barcode-generator/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# C# でバーコードジェネレータを使用してバーコード画像を作成する方法

プログラムで **バーコード画像** ファイルを作成する必要がある場合、このガイドでは C# の完全な実行可能サンプルを示します。バーコードジェネレータを使用すれば、**バーコードのピクセルサイズ** を制御し、**バーコードの高さを調整** し、**カスタムバーコード寸法** を IDE から離れることなく定義できます。

30 px のバー高さと 60 px のバー高さの PNG ファイルを 2 つ生成し、モジュール幅は一定に保つ方法を学びます。この手順はライブラリがサポートするすべてのバーコードタイプで機能するため、QR コードや Code 128、その他のシンボロジーにも応用できます。

## 必要なもの

- .NET 6.0 以降（コードは .NET Framework 4.8 でもコンパイル可能）
- バーコードライブラリへの参照（例: Aspose.BarCode for .NET または互換性のある `BarcodeGenerator` クラス）
- 基本的な C# の知識
- PNG ファイルを書き込むフォルダーへの書き込み権限

## 手順 1: **バーコード画像を作成** するためにジェネレータを初期化

まず必要な名前空間をインポートし、`BarcodeGenerator` をインスタンス化します。コンストラクタにはバーコードタイプ（`EncodeTypes.DatabarOmniDirectional`）とエンコードしたいデータ文字列を渡します。

```csharp
using Aspose.BarCode.Generation;   // or the namespace of your barcode library
using Aspose.BarCode;               // for BarCodeImageFormat
using System.IO;

class Program
{
    static void Main()
    {
        // Step 1: Create a barcode generator to create barcode image
        BarcodeGenerator barcode = new BarcodeGenerator(
            EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");
```

ジェネレータの作成は、**barcode generator c#** ワークフローの基礎です。内部描画キャンバスを確保し、レンダリング用データを準備します。

## 手順 2: **バーコードピクセルサイズ** と初期バー高さを定義

最終画像の視覚品質は次の 2 つのパラメータに依存します。

| パラメータ | 意味 |
|-----------|------|
| `XDimension.Pixels` | 1 つのモジュール（最小の黒/白要素）の幅 |
| `BarHeight.Pixels` | 現在の画像のバー高さ |

```csharp
        // Step 2: Set common visual parameters – module size and initial bar height
        barcode.Parameters.Barcode.XDimension.Pixels = 2;   // barcode pixel size (module width)
        barcode.Parameters.Barcode.BarHeight.Pixels = 30; // first image height in pixels
```

**バーコードピクセルサイズ** を一定に保ちつつ高さを変更することで、ブランドガイドラインやスキャン要件に合わせた **カスタムバーコード寸法** を作成できます。

## 手順 3: 最初の PNG ファイル（30 px 高さ）を保存

画像をディスクに書き出します。`Save` メソッドはファイルパスと希望の画像形式を受け取ります。

```csharp
        // Step 3: Save the first barcode image (30 px height)
        string outputFolder = @"YOUR_DIRECTORY";
        Directory.CreateDirectory(outputFolder); // ensure the folder exists

        barcode.Save(Path.Combine(outputFolder, "DatabarBarHeight30Pixels.png"),
                     BarCodeImageFormat.Png);
```

生成されたファイルは **バーコード画像** で、バー高さが 30 px、モジュール幅が 2 px です。コンパクトなラベルに最適です。

## 手順 4: 大きいバージョン用に **バーコード高さを調整**

別の視覚サイズの画像を作成するには、`BarHeight.Pixels` プロパティだけを変更すれば済みます。これにより、ジェネレータを再作成せずに **バーコード高さを調整** できることが示されます。

```csharp
        // Step 4: Change the bar height to 60 px for a larger barcode
        barcode.Parameters.Barcode.BarHeight.Pixels = 60;
```

**バーコードピクセルサイズ** を維持したまま高さを変えることで、バーが鮮明に保たれ、全体のアスペクト比も一貫します。

## 手順 5: 2 番目の PNG ファイル（60 px 高さ）を保存

最後に大きいバージョンを永続化します。

```csharp
        // Step 5: Save the second barcode image (60 px height)
        barcode.Save(Path.Combine(outputFolder, "DatabarBarHeight60Pixels.png"),
                     BarCodeImageFormat.Png);
    }
}
```

これで 2 つの **カスタムバーコード寸法** が横並びで保存されました。

- `DatabarBarHeight30Pixels.png` – 30 px バー高さ
- `DatabarBarHeight60Pixels.png` – 60 px バー高さ

どちらの画像も **バーコードピクセルサイズ** が 2 px で統一されているため、サイズが異なっても視覚的な一貫性が保たれます。

## これらの設定が重要な理由

- **バーコードピクセルサイズ**（`XDimension`）はスキャナの読み取りやすさに影響します。2 px の幅はファイルサイズとスキャン信頼性のバランスが取れた一般的なデフォルトです。
- **バー高さ** はラベル上でのバーコードの見た目の高さを決定します。小売スキャナの中には最小高さが必要なものもあれば、デザイン上の理由で高めのバーを許容するものもあります。
- `BarHeight` だけを調整し、ジェネレータインスタンスを再利用することでメモリ割り当てが減り、バッチ処理の速度が向上します。

## エッジケースとベストプラクティスのヒント

| 状況 | 推奨アプローチ |
|------|----------------|
| **異なる画像形式**（JPEG、BMP） | `Save` 呼び出しで `BarCodeImageFormat.Jpeg` または `.Bmp` に変更します。JPEG はサイズが小さくなりますが、圧縮アーティファクトが入る可能性があります。 |
| **高解像度出力**（例: 300 DPI） | `XDimension.Pixels` を比例的に増やす（例: 4 px）と同時に `BarHeight.Pixels` も調整し、実際のサイズを維持します。 |
| **動的データ文字列** | ジェネレータ作成をデータ文字列を受け取るメソッドにラップし、同じ `barcode` インスタンスを複数回保存に再利用します。 |
| **スレッドセーフなバッチ生成** | スレッドごとに別々の `BarcodeGenerator` をインスタンス化するか、スレッドローカルプールを使用して競合を回避します。 |
| **ファイルシステムの権限エラー** | `outputFolder` が存在し、プロセスに書き込み権限があることを確認し、`IOException` を適切にハンドリングします。 |

## 完全なソースリスト

以下はコピー＆ペーストして実行できる、自己完結型のプログラム全体です。

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;
using System.IO;

class Program
{
    static void Main()
    {
        // Create a barcode generator – this is the core of the create barcode image workflow
        BarcodeGenerator barcode = new BarcodeGenerator(
            EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");

        // Define barcode pixel size (module width) and initial height
        barcode.Parameters.Barcode.XDimension.Pixels = 2;   // barcode pixel size
        barcode.Parameters.Barcode.BarHeight.Pixels = 30; // first image height

        // Prepare output folder
        string outputFolder = @"YOUR_DIRECTORY";
        Directory.CreateDirectory(outputFolder);

        // Save first image (30 px height)
        barcode.Save(Path.Combine(outputFolder, "DatabarBarHeight30Pixels.png"),
                     BarCodeImageFormat.Png);

        // Adjust height for the second image
        barcode.Parameters.Barcode.BarHeight.Pixels = 60; // adjust barcode height

        // Save second image (60 px height)
        barcode.Save(Path.Combine(outputFolder, "DatabarBarHeight60Pixels.png"),
                     BarCodeImageFormat.Png);
    }
}
```

### 期待される出力

プログラム実行後、`YOUR_DIRECTORY` フォルダーに 2 つの PNG ファイルが生成されます。

- **DatabarBarHeight30Pixels.png** – 小さなラベル向けのコンパクトなバーコード
- **DatabarBarHeight60Pixels.png** – 高視認性が求められる用途向けの大きめバージョン

どちらのファイルも任意の画像ビューアで開くことができ、印刷や PDF への埋め込みも可能です。

## 結論

これで **C# でバーコード画像** を **barcode generator c#** を使って作成し、**バーコードピクセルサイズ** を制御し、**バーコード高さを調整** して、特定のスキャン要件やブランドガイドラインに合った **カスタムバーコード寸法** を実現する方法が分かりました。この例はクリーンで再利用可能なパターンを示しており、バッチ処理や他のシンボロジーへの拡張にも適しています。

### 次に探求すべきこと

- `EncodeTypes.DatabarOmniDirectional` を `EncodeTypes.Code128` や `EncodeTypes.QR` など他のタイプに置き換える
- `barcode.Parameters.Barcode.ForeColor` と `BackColor` で前景・背景色を設定する
- ベクターベース印刷用に SVG や PDF 出力を生成する
- `Graphics` を使って複数のバーコードを 1 枚の画像に合成し、複合ラベルを作成する

パラメータを自由に試し、在庫管理、チケット発行、またはプログラムでバーコード作成が必要なシステムにこのパターンを組み込んでみてください。コーディングを楽しんで！

## 次に学ぶべきこと

以下のチュートリアルは、本ガイドで示したテクニックを基にした、密接に関連するトピックをカバーしています。各リソースには、ステップバイステップの解説と完全な動作コード例が含まれており、API の追加機能を習得したり、代替実装アプローチを自分のプロジェクトで試したりするのに役立ちます。

- [How to create barcode image in C# with adjustable height](/barcode/english/python-java/general/how-to-create-barcode-image-in-c-with-adjustable-height/)
- [How to generate barcode set custom size and save image in C#](/barcode/english/python-java/general/how-to-generate-barcode-set-custom-size-and-save-image-in-c/)
- [Create barcode image C# with barcode generator example](/barcode/english/python-java/general/create-barcode-image-c-with-barcode-generator-example/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}