---
category: general
date: 2026-08-22
description: barcode generator C# チュートリアルでは、数ステップでバーコードの PNG ファイルを生成し、DataBar バーコードを作成し、バーコードの高さを調整する方法を示します。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- barcode generator C#
- how to generate barcode
- generate barcode PNG
- create DataBar barcode
- adjust barcode height
language: ja
lastmod: 2026-08-22
og_description: バーコードジェネレーター C# ガイドでは、バーコード PNG の生成方法、DataBar バーコードの作成、そしてバーコードの高さを効率的に調整する方法をステップバイステップで解説します。
og_image_alt: Screenshot of two DataBar Omni‑directional barcodes with different heights
  saved as PNG files
og_title: バーコードジェネレーター C# – DataBar バーコードを作成し高さを調整
schemas:
- author: Aspose
  dateModified: '2026-08-22'
  description: barcode generator C# tutorial shows how to generate barcode PNG files,
    create DataBar barcodes, and adjust barcode height in just a few steps.
  headline: How to use a barcode generator C# to create DataBar Omni‑directional barcodes
  type: TechArticle
tags:
- barcode
- C#
- Aspose.BarCode
title: C#のバーコードジェネレーターを使用してDataBar Omni‑directionalバーコードを作成する方法
url: /ja/python-java/general/how-to-use-a-barcode-generator-c-to-create-databar-omni-dire/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# C# バーコードジェネレーターを使用して DataBar Omni‑directional バーコードを作成する方法

高品質な PNG 画像を生成できる **barcode generator C#** が必要な場合、このガイドが役立ちます。バーコード PNG ファイルの生成方法、DataBar Omni‑directional バーコードの作成方法、IDE を離れずにバーコードの高さを調整する方法を学びます。

プログラムでバーコードを生成すれば、グラフィックエディタを手作業で使用する手間が省けます。このチュートリアルの最後までに、30 ピクセルのバー高さと 60 ピクセルのバー高さの PNG ファイルがそれぞれ 1 つずつ作成でき、請求書、ラベル、在庫システムへの組み込みがすぐに可能になります。

**Prerequisites**

- .NET 6.0 以降（コードは .NET Framework 4.7+ でも動作します）
- `Aspose.BarCode` NuGet パッケージへの参照（または同様の API を提供するライブラリ）
- C# と Visual Studio もしくはお好みの IDE に関する基本的な知識

---

## Step 1: Set up the barcode generator C# project

**barcode generator C#** のインスタンスを作成するのが最初のステップです。コンストラクタは 2 つの引数を受け取ります：バーコードタイプ（`EncodeTypes.DatabarOmniDirectional`）とデータペイロードです。この例ではペイロードは 14 桁 GTIN 用の GS1 アプリケーション識別子形式に従っています。

```csharp
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Initialize the barcode generator for a DataBar Omni‑directional code
        BarcodeGenerator generator = new BarcodeGenerator(
            EncodeTypes.DatabarOmniDirectional,
            "(01)12345678901231");   // GTIN‑14 example
```

**Why this matters:** `EncodeTypes.DatabarOmniDirectional` 列挙体は、任意の方向から読み取れる DataBar をレンダリングするようライブラリに指示します。これは小さな小売ラベルに最適です。

---

## Step 2: Define the module dimension (X‑dimension)

X‑dimension は単一モジュールの幅を制御します。2 ピクセルに設定すると、画像が鮮明で読み取りやすく、かつファイルサイズが抑えられます。

```csharp
        // Set the module (X) dimension to 2 pixels per module
        generator.Parameters.Barcode.XDimension.Pixels = 2;
```

**Tip:** スペースが限られている場合は、値を 1 ピクセルに下げてバーコードを細くできますが、スキャナでの読み取り可否は必ずテストしてください。

---

## Step 3: Generate the first PNG with a 30‑pixel bar height

バー高さはバーの縦長さを決定します。30 ピクセルの高さは標準ラベルでよく使われるデフォルトです。

```csharp
        // Set bar height to 30 pixels
        generator.Parameters.Barcode.BarHeight.Pixels = 30;

        // Save the first image as PNG
        generator.Save(@"YOUR_DIRECTORY\DatabarBarHeight30Pixels.png",
                       BarCodeImageFormat.Png);
```

ファイル `DatabarBarHeight30Pixels.png` には **generate barcode PNG** が格納されており、ウェブページで直接使用したり、オンデマンドで印刷したりできます。

---

## Step 4: Adjust barcode height to 60 pixels and save a second PNG

バー高さを変更するのは、同じプロパティに新しい値を代入するだけです。これにより、ジェネレーターの **adjust barcode height** 機能が実証されます。

```csharp
        // Change bar height to 60 pixels for a larger barcode
        generator.Parameters.Barcode.BarHeight.Pixels = 60;

        // Save the second image
        generator.Save(@"YOUR_DIRECTORY\DatabarBarHeight60Pixels.png",
                       BarCodeImageFormat.Png);
    }
}
```

これで `DatabarBarHeight60Pixels.png` が作成され、遠距離からのスキャンが必要な大きめのパッケージに最適です。

**Expected output**

- `DatabarBarHeight30Pixels.png` – コンパクトな DataBar Omni‑directional バーコード、30 px の高さ。
- `DatabarBarHeight60Pixels.png` – 同じバーコードを高さ 2 倍にしたもの、視認性が向上。

どちらも PNG 形式で、ロスレス品質を保ち、必要に応じて透過もサポートします。

---

## How to generate barcode PNG files in different formats

本チュートリアルは PNG に焦点を当てていますが、`Save` メソッドは `Jpeg`、`Bmp`、`Svg` など他のフォーマットも受け付けます。別の形式で **how to generate barcode** ファイルを作成したい場合は、`BarCodeImageFormat.Png` を目的の列挙値に置き換えるだけです。

```csharp
generator.Save(@"path\barcode.svg", BarCodeImageFormat.Svg);
```

SVG を選択すると、ピクセル化せずに拡大縮小できるベクター画像が必要なシーンで便利です。

---

## Common pitfalls when you **create DataBar barcode** images

| Issue | Cause | Fix |
|-------|-------|-----|
| バーコードがぼやけて見える | 対象解像度に対して X‑dimension が低すぎる | `XDimension.Pixels` を 3 または 4 に増やす |
| スキャナがコードを読めない | バー高さがスキャナの光学系に対して短すぎる | 最低 30 ピクセルを使用するか、スキャナの仕様に従う |
| データ文字列が拒否される | GS1 フォーマットが誤っている | 正しいアプリケーション識別子で始まっているか確認する（例: GTIN‑14 の場合は `(01)`） |

これらのポイントに早めに対処すれば、バーコードを本番環境に組み込む際の手間が大幅に削減できます。

---

## Advanced tip: Reusing the same generator for multiple barcodes

大量の商品向けに **generate barcode PNG** ファイルを作成する必要がある場合は、同じ `BarcodeGenerator` インスタンスを再利用し、`CodeText` プロパティだけを更新します。

```csharp
string[] gtins = { "(01)12345678901231", "(01)98765432109876" };
int[] heights = { 30, 60 };

foreach (var gtin in gtins)
{
    generator.CodeText = gtin;          // Change data payload
    foreach (var h in heights)
    {
        generator.Parameters.Barcode.BarHeight.Pixels = h;
        string fileName = $"Databar_{gtin.Substring(4)}_{h}Px.png";
        generator.Save($@"YOUR_DIRECTORY\{fileName}", BarCodeImageFormat.Png);
    }
}
```

このパターンはオブジェクト生成のオーバーヘッドを最小限に抑え、コードを簡潔に保ちます。

---

## Conclusion

これで **barcode generator C#** の完全なワークフローが完成し、**creates DataBar barcodes**、**generates barcode PNG** ファイルの作成、そして単一プロパティの変更だけで **adjust barcode height** が可能になります。プロジェクトのセットアップからエッジケースの処理まで網羅しているので、あらゆる .NET アプリケーションに自信を持ってバーコード生成機能を組み込めます。

**Next steps**

- 他のバーコードシンボル（`EncodeTypes.QR`、`EncodeTypes.Code128`）を試して、ソリューションの幅を広げましょう。
- ジェネレーターを ASP.NET Core と組み合わせ、API エンドポイント経由でオンデマンドにバーコードを配信します。
- カラーパラメータ（`generator.Parameters.Barcode.ForeColor`）を活用し、ブランディングに合わせた色設定を実験してみてください。

Happy coding, and may your scans always be swift!

## What Should You Learn Next?

以下のチュートリアルは、本ガイドで示した手法を基にした、密接に関連するトピックを扱っています。各リソースには完全な動作コード例とステップバイステップの解説が含まれており、追加の API 機能を習得したり、独自プロジェクトで代替実装アプローチを探求したりするのに役立ちます。

- [Aspose.BarCode for .NET を使用した 1 次元 Databar のバーコード高さの生成と調整方法](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-barcode-height-adjustment/)
- [Aspose.BarCode .NET API を使用した 1 次元 Databar 2D バーコードの生成](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-2d-component-configuration/)
- [Aspose.BarCode for .NET を使用した DataMatrix バーコードの生成 – ステップバイステップガイド](/barcode/english/net/datamatrix-barcode-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}