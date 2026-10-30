---
category: general
date: 2026-10-28
description: C#でバーコード画像を素早く作成する。バーコードジェネレーターC#の使い方、ピクセルサイズの設定方法、DataBarのアスペクト比の変更方法を学ぶ。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode image
- barcode generator c#
- how to set pixel size
- how to change aspect ratio
- how to generate databar
language: ja
lastmod: 2026-10-28
og_description: C#でバーコードジェネレータを使用してバーコード画像を作成します。このガイドに従ってピクセルサイズを設定し、アスペクト比を変更し、DataBarバーコードを生成してください。
og_image_alt: Screenshot of a generated barcode image created with C#
og_title: C#でバーコード画像を作成する – ステップバイステップガイド
schemas:
- author: GroupDocs
  dateModified: '2026-10-28'
  description: Create barcode image in C# quickly. Learn barcode generator c# usage,
    how to set pixel size, and how to change aspect ratio for DataBar.
  headline: How to create barcode image with C# using Barcode Generator
  type: TechArticle
tags:
- barcode
- C#
- imaging
title: C# と Barcode Generator を使用してバーコード画像を作成する方法
url: /ja/python-java/general/how-to-create-barcode-image-with-c-using-barcode-generator/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# C# と Barcode Generator を使用してバーコード画像を作成する方法

.NET アプリケーションで **バーコード画像を作成** したい場合、本ガイドが具体的な手順を示します。Barcode Generator C# ライブラリを使用して DataBar stacked omnidirectional バーコードを生成し、ピクセルサイズを設定し、アスペクト比を変更する完全な実行可能サンプルをご覧いただけます。

プログラムでバーコードを生成すれば外部ツールは不要になり、画像を PDF、レポート、UI コントロールに直接埋め込むことができます。以下の手順では **ピクセルサイズの設定方法** と **アスペクト比の変更方法** も解説します。これらは鮮明で正しくスケーリングされたバーコードが必要なときに頻出する要件です。

## 前提条件

開始する前に、以下がインストールされていることを確認してください。

* .NET 6.0 SDK 以降  
* C# 対応の IDE（Visual Studio、Rider、または VS Code）  
* プロジェクトに `BarcodeGenerator` NuGet パッケージ（例: `GroupDocs.Barcode` または `Aspose.Barcode`）がインストールされていること  

以下のコマンドでパッケージを追加できます。

```bash
dotnet add package GroupDocs.Barcode
```

> **プロのコツ:** パッケージのバージョンがターゲットフレームワークと一致しているか確認し、実行時の非互換性を防ぎましょう。

## Barcode Generator C# でバーコード画像を作成する

最初のステップは、目的のバーコードタイプとデータでジェネレータをインスタンス化することです。以下の例は、小売スキャンシナリオに最適な **DataBar stacked omnidirectional** バーコードを作成します。

```csharp
using System;
using GroupDocs.Barcode;
using GroupDocs.Barcode.Enums;
using GroupDocs.Barcode.Common;

class Program
{
    static void Main()
    {
        // Step 1: Create a BarcodeGenerator for DataBar stacked omnidirectional
        var barcode = new BarcodeGenerator(
            EncodeTypes.DatabarStackedOmniDirectional,
            "(01)12345678901231");   // GTIN‑14 example data

        // Step 2: Set the pixel size of the X‑dimension (how to set pixel size)
        barcode.Parameters.Barcode.XDimension.Pixels = 2;

        // Step 3: Save an image with the first aspect ratio (how to generate databar)
        barcode.Parameters.Barcode.DataBar.AspectRatio = 15;
        barcode.Save("DatabarAspectRatio15.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved barcode with aspect ratio 15.");

        // Step 4: Change the aspect ratio (how to change aspect ratio) and save a second image
        barcode.Parameters.Barcode.DataBar.AspectRatio = 30;
        barcode.Save("DatabarAspectRatio30.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved barcode with aspect ratio 30.");
    }
}
```

### 各行の重要ポイント

* **`BarcodeGenerator` のインスタンス化** – コンストラクタはバーコードシンボロジー（`EncodeTypes.DatabarStackedOmniDirectional`）と生データ文字列を受け取ります。正しいシンボロジーを選択することで、スキャナがコードを正しく読み取れます。  
* **`XDimension.Pixels` の設定** – このプロパティは最小バー要素の幅を制御します。`2` を指定すると、ほとんどの画面で読み取り可能な細かい画像が生成されます。低解像度プリンタ向けに大きなバーコードが必要な場合は、値を上げてください。  
* **`AspectRatio` の構成** – DataBar ファミリは高さと幅の比率を決める複数のアスペクト比をサポートしています。`15` と `30` が一般的で、`15` は短いバーコード、`30` は高いバーコードになります。  
* **`Save` メソッド** – 生成したバーコードを PNG ファイルに保存します。下流システムが別形式を要求する場合は、`BarCodeImageFormat.Png` を `Jpeg` や `Bmp` に置き換えられます。

## 異なる描画コンテキスト向けにピクセルサイズを設定する方法

ピクセルサイズはバーコードの視覚的密度を決定します。高 DPI モニタで表示する場合は、ピクセルサイズを `3` や `4` に増やすと見やすくなります。逆に低解像度のサーマルプリンタ向けには、ピクセルサイズを小さく（例: `1`）してインク使用量を抑えます。

```csharp
// Example: increase pixel size for a high‑resolution display
barcode.Parameters.Barcode.XDimension.Pixels = 4;
```

**エッジケース:** ピクセルサイズを 1 未満に設定すると `ArgumentOutOfRangeException` がスローされます。割り当てる前に必ず値を検証してください。

## ジェネレータを再作成せずにアスペクト比を変更する方法

アスペクト比の変更は単純なプロパティ更新で済みます。`BarcodeGenerator` インスタンスを **再作成する必要はありません**。これによりメモリ使用量が削減され、異なる形状の画像を複数生成する際のパフォーマンスが向上します。

```csharp
// Switch from a short to a tall barcode
barcode.Parameters.Barcode.DataBar.AspectRatio = 30;
barcode.Save("TallDatabar.png", BarCodeImageFormat.Png);
```

2 つ以上の比率が必要な場合は、配列をループで処理できます。

```csharp
int[] ratios = { 15, 20, 25, 30 };
foreach (int ratio in ratios)
{
    barcode.Parameters.Barcode.DataBar.AspectRatio = ratio;
    string fileName = $"DatabarAspectRatio{ratio}.png";
    barcode.Save(fileName, BarCodeImageFormat.Png);
    Console.WriteLine($"Saved {fileName}");
}
```

## 期待される出力

プログラムを実行すると、2 つの PNG ファイル（ループを使用すればそれ以上）が作成されます。任意の画像ビューアで開くと、クリーンな DataBar バーコードが確認できます。

* **DatabarAspectRatio15.png** – ラベル幅が狭い場所に適した、短くて横長のバーコード。  
* **DatabarAspectRatio30.png** – 角度スキャナでの読み取り信頼性が向上する、縦長のバーコード。

両画像は同じピクセルサイズ（モジュールあたり 2 px）ですが、高さだけが異なり、**アスペクト比を変更しながら他のパラメータは一定に保つ** 方法を示しています。

## よくある落とし穴と回避策

| 症状 | 原因 | 対策 |
|------|------|------|
| バーコードがぼやけて見える | `XDimension.Pixels` が出力解像度に対して低すぎる | 画面表示なら最低 `2`、印刷なら `3` 以上に増やす |
| スキャナがコードを読めない | データ形式に合わない `EncodeTypes` を使用 | GTIN‑14 データが選択したシンボロジーに合致しているか確認 |
| アスペクト比で `ArgumentOutOfRangeException` が発生 | ライブラリがサポートしない比率（有効範囲: 15‑30） | ドキュメントで記載された値のみ使用するか、例外を捕捉してデフォルトにフォールバック |
| `Save` 後にファイルが見つからない | 相対パスが存在しないディレクトリを指している | 絶対パスを使用するか、事前に `Directory.CreateDirectory` を呼び出す |

```csharp
// Ensure the output folder exists
string outputDir = Path.Combine(Environment.CurrentDirectory, "Barcodes");
Directory.CreateDirectory(outputDir);
barcode.Save(Path.Combine(outputDir, "DatabarAspectRatio15.png"), BarCodeImageFormat.Png);
```

## 次のステップ – バーコードワークフローの拡張

**バーコード画像を作成** できたら、以下のような拡張が考えられます。

* `PdfSharp` や `iTextSharp` などのライブラリを使って PNG を PDF に埋め込む。  
* `EncodeTypes` 列挙体を変更して、QR、Code128、PDF417 など他のシンボロジーを生成する。  
* `barcode.Parameters.Barcode.Image.Color` にアクセスしてカラー変換を適用する。  
* ASP.NET Core エンドポイントで画像をオンデマンド生成し、Web アプリで配信する。

これらのトピックはすべて、本チュートリアルで扱った **barcode generator c#** の基本概念（ピクセルサイズ制御、アスペクト比操作）を土台にしています。

## 結論

C# と Barcode Generator を使って **バーコード画像を作成** し、ピクセルサイズの設定方法、アスペクト比の変更方法、DataBar バーコードの効率的な生成方法を習得しました。完全な実行可能サンプルは任意の .NET プロジェクトにコピーでき、他のシンボロジー向けに適応したり、実務フローに合わせて拡張したりできます。

`XDimension` の値、アスペクト比、出力形式をいろいろ試してみてください。問題が発生したら「よくある落とし穴」表を再確認するか、ライブラリの公式ドキュメントで詳細設定を調べましょう。Happy coding!

## 次に学ぶべきことは？

以下のチュートリアルは、本ガイドで示したテクニックを基にした、密接に関連するトピックを扱っています。各リソースには、ステップバイステップの解説と完全なコード例が含まれており、追加の API 機能をマスターしたり、別の実装アプローチを自分のプロジェクトで試したりするのに役立ちます。

- [How to create barcode image and adjust its aspect ratio in C#](/barcode/english/python-java/general/how-to-create-barcode-image-and-adjust-its-aspect-ratio-in-c/)
- [How to generate barcode set custom size and save image in C#](/barcode/english/python-java/general/how-to-generate-barcode-set-custom-size-and-save-image-in-c/)
- [How to use a barcode generator C# to create DataBar barcodes](/barcode/english/python-java/general/how-to-use-a-barcode-generator-c-to-create-databar-barcodes/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}