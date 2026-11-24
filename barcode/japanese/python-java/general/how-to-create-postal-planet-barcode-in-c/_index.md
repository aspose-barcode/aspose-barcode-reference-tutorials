---
category: general
date: 2026-11-23
description: Aspose.BarCode を使用して C# で郵便用プラネットバーコードを作成します。プラネットバーコードの生成方法、X ディメンションの設定、塗りつぶしバーまたは空白バーの保存方法を学びましょう。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create postal planet barcode
- how to generate planet barcode
- Aspose.BarCode C#
- postal barcode example
- Planet barcode settings
language: ja
lastmod: 2026-11-23
og_description: C#で郵便用プラネットバーコードを作成し、Aspose.BarCodeを使用したプラネットバーコードの生成方法を学びましょう。完全なサンプルに従って、塗りつぶしバーと空白バーを生成します。
og_image_alt: Example of a created postal planet barcode with filled bars
og_title: C#で郵便プラネットバーコードを作成する方法 – ステップバイステップガイド
schemas:
- author: Aspose
  dateModified: '2026-11-23'
  description: Create postal planet barcode in C# with Aspose.BarCode. Learn how to
    generate planet barcode, set X‑dimension, and save filled or empty bars.
  headline: How to create postal planet barcode in C#
  type: TechArticle
- description: Create postal planet barcode in C# with Aspose.BarCode. Learn how to
    generate planet barcode, set X‑dimension, and save filled or empty bars.
  name: How to create postal planet barcode in C#
  steps:
  - name: Changing the image format
    text: If your downstream system prefers JPEG, replace `BarCodeImageFormat.Png`
      with `BarCodeImageFormat.Jpeg`. JPEG introduces compression artifacts, so use
      it only when file size is a critical constraint.
  - name: Scaling the barcode
    text: 'You can enlarge the barcode while preserving the module width by adjusting
      the `Resolution` property:'
  - name: Using a custom background color
    text: 'The background can be set with:'
  type: HowTo
tags:
- barcode
- C#
- Aspose
title: C#で郵便プラネットバーコードを作成する方法
url: /ja/python-java/general/how-to-create-postal-planet-barcode-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# C#で郵便プラネットバーコードを作成する方法

.NET アプリケーションで **郵便プラネットバーコードを作成** する必要がある場合、このガイドでは Aspose.BarCode ライブラリを使用して **プラネットバーコードを生成する方法** を正確に示します。X‑dimension の設定方法、塗りつぶしバーと空白バーの切り替え、PNG 形式での画像保存方法が分かります。

プラネットバーコードの生成は、高密度で機械可読なシンボルを必要とする郵便サービスで一般的です。このチュートリアルの最後までに、実線バーと空洞バーの 2 つの PNG ファイルが作成され、任意のメールワークフローに統合できるようになります。

## 前提条件

開始する前に、以下がインストールされていることを確認してください。

* .NET 6.0 SDK 以降
* .NET 開発用に設定された Visual Studio 2022（または任意の C# エディタ）
* **Aspose.BarCode for .NET** の有効な NuGet ライセンス。パッケージは次のコマンドでインストールします：

```bash
dotnet add package Aspose.BarCode
```

追加の外部サービスは不要です。ライブラリはすべてローカルでエンコードを行います。

## 手順 1 – 郵便プラネットバーコードを作成する

最初の操作は、**Planet** シンボル用の `BarcodeGenerator` をインスタンス化し、エンコードするデータを提供することです。データ文字列は数値のみで、郵便仕様に従い最大 12 桁までです。

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

// Step 1: Create a Planet barcode generator with the data to encode
BarcodeGenerator planetFilled = new BarcodeGenerator(EncodeTypes.Planet, "123456");
```

ジェネレータを作成すると、レンダリングに必要な内部構造がすべて確保されます。`EncodeTypes.Planet` 列挙値は、郵便フォーマット用の正しいエンコードアルゴリズムを選択します。

## 手順 2 – 可視性向上のために X‑dimension を設定する

X‑dimension は単一モジュール（最小のバー要素）の幅を定義します。4 ピクセルの値は、全体画像を拡大せずに明瞭な視覚表現を提供します。

```csharp
// Step 2: Set the X‑dimension (module width) to 4 pixels
planetFilled.Parameters.Barcode.XDimension.Pixels = 4;
```

低解像度メディアに印刷する場合は、X‑dimension の調整が不可欠です。同じ設定を空白バー版でも再利用し、両画像の一貫性を保ちます。

## 手順 3 – 塗りつぶしバーでバーコードを保存する

デフォルトでは、ジェネレータは **塗りつぶしバー**（実線の黒モジュール）を描画します。画像の保存は、PNG ファイルを書き出す単一メソッド呼び出しで完了します。

```csharp
// Step 3: Save the barcode with the default setting (filled bars)
planetFilled.Save("YOUR_DIRECTORY/PostalPlanetFilledBars.png", BarCodeImageFormat.Png);
```

`YOUR_DIRECTORY` を実際に出力ファイルを保存したいパスに置き換えてください。`BarCodeImageFormat.Png` 列挙はロスレス圧縮を保証し、下流処理に最適です。

## 手順 4 – 空白バー用に別の Planet バーコードジェネレータを作成する

**空白バー**（黒背景に白モジュール）バージョンを作成するには、2 番目の `BarcodeGenerator` インスタンスが必要です。同じデータ文字列を再利用することで、両画像が同一の郵便コードを表すことが保証されます。

```csharp
// Step 4: Create another Planet barcode generator for the same data
BarcodeGenerator planetEmpty = new BarcodeGenerator(EncodeTypes.Planet, "123456");
```

別々のジェネレータを作成すると、`FilledBars` プロパティが分離され、最初の画像に影響を与えることなく視覚スタイルを切り替えられます。

## 手順 5 – 空白バーを描画するようジェネレータを構成する

`FilledBars` フラグは描画モードを切り替えます。`false` に設定すると、ライブラリはバーを空白（透明）として描画し、背景は実線のままになります。

```csharp
// Step 5: Apply the same X‑dimension and configure empty bars
planetEmpty.Parameters.Barcode.XDimension.Pixels = 4;
planetEmpty.Parameters.Barcode.FilledBars = false;
```

塗りつぶし版と X‑dimension を同一に保つことで、両 PNG ファイルのサイズが一致し、印刷テンプレートでのレイアウト計算が簡素化されます。

## 手順 6 – 空白バーを描画したバーコードを保存する

最後に、空白バー画像をディスクに書き出します。PNG 形式は引き続き使用しますが、`BarCodeImageFormat` の値を変更すれば JPEG や BMP に切り替えることも可能です。

```csharp
// Step 6: Save the barcode that renders empty bars
planetEmpty.Save("YOUR_DIRECTORY/PostalPlanetEmptyBars.png", BarCodeImageFormat.Png);
```

この時点で以下の 2 つのファイルが生成されています：

* `PostalPlanetFilledBars.png` – 実線の黒バー
* `PostalPlanetEmptyBars.png` – 黒背景に空洞バー

どちらも Planet シンボルの郵便仕様を満たしています。

## 完全なソースコード

すべての手順を組み合わせると、直接実行できるコンパクトなコンソールアプリケーションが完成します。

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace PlanetBarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // Create a Planet barcode with filled bars
            BarcodeGenerator planetFilled = new BarcodeGenerator(EncodeTypes.Planet, "123456");
            planetFilled.Parameters.Barcode.XDimension.Pixels = 4;
            planetFilled.Save("PostalPlanetFilledBars.png", BarCodeImageFormat.Png);

            // Create a Planet barcode with empty bars
            BarcodeGenerator planetEmpty = new BarcodeGenerator(EncodeTypes.Planet, "123456");
            planetEmpty.Parameters.Barcode.XDimension.Pixels = 4;
            planetEmpty.Parameters.Barcode.FilledBars = false;
            planetEmpty.Save("PostalPlanetEmptyBars.png", BarCodeImageFormat.Png);

            Console.WriteLine("Barcodes generated successfully.");
        }
    }
}
```

プログラムのコンパイルと実行：

```bash
dotnet run
```

コンソールには *Barcodes generated successfully.* と表示され、2 つの PNG ファイルがプロジェクトフォルダーに作成されます。

## 期待される出力

以下は塗りつぶしバー画像の視覚的表現です。空白バー版はバーが透明になる点を除き、見た目は同一です。

![Example of a created postal planet barcode with filled bars](postal-planet-filled.png)

*画像代替テキスト:* **Example of a created postal planet barcode with filled bars** (contains the primary keyword).

デフォルトでは両画像とも 150 × 150 ピクセルですが、`ImageWidth` と `ImageHeight` パラメータを使用すれば、別の解像度に調整できます。

## オプションのバリエーション

### 画像形式の変更

下流システムが JPEG を好む場合は、`BarCodeImageFormat.Png` を `BarCodeImageFormat.Jpeg` に置き換えてください。JPEG は圧縮アーティファクトが発生するため、ファイルサイズが重要な制約になる場合にのみ使用してください。

### バーコードの拡大

`Resolution` プロパティを調整することで、モジュール幅を保ったままバーコードを拡大できます：

```csharp
planetFilled.Parameters.ImageResolution = 300; // DPI
```

DPI 値を高くすると、レーザープリンタでの印刷品質が向上します。

### カスタム背景色の使用

背景色は次のように設定できます：

```csharp
planetEmpty.Parameters.Barcode.BackColor = System.Drawing.Color.LightGray;
```

視覚テストには便利ですが、実際の郵便ラベルでは白背景が必須となるため、運用環境では使用しないでください。

## よくある質問

**このコードは .NET Core でも動作しますか？**  
はい。Aspose.BarCode ライブラリは .NET Standard 2.0 を対象としており、.NET 5、.NET 6、.NET Core 3.1 と互換性があります。

**データ文字列に数字以外の文字が含まれていたらどうなりますか？**  
Planet バーコードは数値入力のみ受け付けます。文字や記号が含まれると `BarcodeException` がスローされます。ジェネレータ作成前に入力を検証してください。

**ディスクに書き込まずにメモリ上でバーコードを生成できますか？**  
`GenerateBarCodeImage` メソッドを使用して `System.Drawing.Image` オブジェクトを取得し、直接レスポンスやデータベースにストリームできます。

## 結論

これで C# で **郵便プラネットバーコードを作成** する方法と、塗りつぶしバーと空白バーの両スタイルで **プラネットバーコードを生成** する手順が理解できました。本チュートリアルでは、ジェネレータの初期化、X‑dimension の設定、`FilledBars` フラグの切り替え、PNG ファイルの保存までの全工程をカバーしました。画像形式、DPI 設定、背景色を試して、特定のメールシステムに合わせてバーコードを調整してください。

次のステップとして、同じ Aspose.BarCode API を使用して **POSTNET** や **Intelligent Mail** などの他の郵便シンボルに挑戦してみましょう。`EncodeTypes.Postnet` などのパラメータを調整すれば、本ガイドと同様の手順で包括的なバーコード生成スイートを構築できます。

## 次に学ぶべきこと

以下のチュートリアルは、本ガイドで示したテクニックを応用した関連トピックを扱っています。各リソースには完全なコード例とステップバイステップの解説が含まれており、API の追加機能を習得したり、プロジェクトで代替実装を試したりするのに役立ちます。

- [Create empty planet barcode, generate postal barcode in C#](/barcode/english/python-java/general/create-empty-planet-barcode-generate-postal-barcode-in-c/)
- [How to set width and generate a Planet barcode in C#](/barcode/english/python-java/general/how-to-set-width-and-generate-a-planet-barcode-in-c/)
- [Generate Postal Barcode in C# – Complete Guide with Planet Barcode](/barcode/english/python-java/general/generate-postal-barcode-in-c-complete-guide-with-planet-barc/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}