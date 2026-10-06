---
category: general
date: 2026-09-10
description: C# のバーコードジェネレータ例を使って、サイズを設定し PNG ファイルとして保存する方法を示す、バーコード画像を素早く作成する方法。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode image c#
- barcode generator example c#
language: ja
lastmod: 2026-09-10
og_description: C#で簡潔なバーコードジェネレータの例を使ってバーコード画像を作成。サイズや高さの設定、PNGファイルのエクスポートを数分で学べます。
og_image_alt: Screenshot of a barcode image created with C# code
og_title: C#でバーコード画像を作成 – ステップバイステップジェネレータ例
schemas:
- author: Aspose
  dateModified: '2026-09-10'
  description: Create barcode image C# quickly using a barcode generator example C#
    that shows how to set dimensions and save PNG files.
  headline: Create barcode image C# with barcode generator example
  type: TechArticle
tags:
- barcode
- C#
- image generation
title: C#でバーコードジェネレーターを使用したバーコード画像の作成例
url: /ja/python-java/general/create-barcode-image-c-with-barcode-generator-example/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# C#でバーコード画像を作成する – バーコードジェネレータ例

製品ラベリング、在庫管理、モバイルスキャン用に **create barcode image C#** が必要な場合、本ガイドでは完全なソリューションを示します。**barcode generator example C#** を使用して、モジュール幅、バーの高さを設定し、数行のコードで PNG ファイルを保存する方法が分かります。

このチュートリアルでは、必要なライブラリのインストールからコンパイル可能なコンソールプログラムの実行までを網羅しています。最後には、30 ピクセルのバー高さと 60 ピクセルのバー高さを持つ 2 つのバーコード PNG ファイルが生成され、任意の .NET アプリケーションで使用できるようになります。

## 前提条件

* .NET 6.0 SDK 以降がインストールされていること  
* Visual Studio 2022 や VS Code などの開発環境  
* **Aspose.BarCode** NuGet パッケージ（コードはこのライブラリの `BarcodeGenerator` を使用）

以下の CLI コマンドでパッケージを追加できます。

```bash
dotnet add package Aspose.BarCode
```

## ステップ 1: コンソールプロジェクトの設定

新しいコンソールプロジェクトを作成し、バーコードライブラリを参照します。

```bash
dotnet new console -n BarcodeDemo
cd BarcodeDemo
dotnet add package Aspose.BarCode
```

このコマンドにより `Program.cs` ファイルが作成され、そこに **barcode generator example C#** のコードを配置します。

## ステップ 2: 完全なバーコード生成プログラムの作成

`Program.cs` の内容を以下の完全な実行可能サンプルに置き換えます。このプログラムは、カスタム寸法で **create barcode image C#** を作成し、結果を PNG ファイルとして保存する方法を示します。

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Create a DataBar Omnidirectional barcode generator with the desired data.
            // The string "(01)12345678901231" follows the GS1 Application Identifier format.
            var generator = new BarcodeGenerator(
                EncodeTypes.DatabarOmniDirectional,
                "(01)12345678901231");

            // 2️⃣ Set the X‑dimension (module width) to 2 pixels.
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // 3️⃣ Configure a 30‑pixel bar height and save the first image.
            generator.Parameters.Barcode.BarHeight.Pixels = 30;
            SaveBarcode(generator, "DatabarBarHeight30Pixels.png");

            // 4️⃣ Change the bar height to 60 pixels and save the second image.
            generator.Parameters.Barcode.BarHeight.Pixels = 60;
            SaveBarcode(generator, "DatabarBarHeight60Pixels.png");

            Console.WriteLine("Barcode images have been saved to the output folder.");
        }

        /// <summary>
        /// Saves the current barcode image as a PNG file.
        /// </summary>
        /// <param name="generator">The configured BarcodeGenerator instance.</param>
        /// <param name="fileName">The file name for the PNG image.</param>
        private static void SaveBarcode(BarcodeGenerator generator, string fileName)
        {
            // Ensure the output directory exists.
            string outputPath = System.IO.Path.Combine(
                AppDomain.CurrentDomain.BaseDirectory, "output");
            System.IO.Directory.CreateDirectory(outputPath);

            // Combine the directory and file name.
            string fullPath = System.IO.Path.Combine(outputPath, fileName);

            // Save the barcode as a PNG image.
            generator.Save(fullPath, BarCodeImageFormat.Png);
        }
    }
}
```

### 各行が重要な理由

* **EncodeTypes.DatabarOmniDirectional** – DataBar Omnidirectional シンボルを選択します。数値データをエンコードし、小売業で広く使用されています。  
* **XDimension.Pixels = 2** – モジュール幅を設定します。値が小さいほどコンパクトなバーコードになります。  
* **BarHeight.Pixels** – バーの視覚的な高さを制御します。この値を調整することで、さまざまなラベルサイズに合わせたバーコードを作成できます。  
* **Save method** – バーコードを PNG ファイルに書き出します。PNG はエッジを鮮明に保ち、ほとんどの画像ライブラリで利用可能な形式です。

## ステップ 3: プログラムのビルドと実行

プロジェクトフォルダーから次のコマンドを実行します。

```bash
dotnet run
```

プログラムが終了すると、`output` サブフォルダーに 2 つの PNG ファイルが作成されます。

* `DatabarBarHeight30Pixels.png` – 30 ピクセルのバー高さ  
* `DatabarBarHeight60Pixels.png` – 60 ピクセルのバー高さ  

両画像は同じデータをエンコードしていますが、視覚的な高さが異なるため、**barcode generator example C#** をさまざまなラベル要件に合わせて調整できることが分かります。

## ステップ 4: 生成されたバーコードの検証

任意の画像ビューアで PNG ファイルを開きます。はっきりとした高コントラストの DataBar バーコードが表示されるはずです。バーコードが読み取れることを確認するには、モバイルスキャナアプリ（例: ZXing 系アプリ）やデスクトップ向けライブラリ **Aspose.BarCode** のデコードモードを使用します。

```csharp
var reader = new BarCodeReader(fullPath, DecodeType.DatabarOmniDirectional);
foreach (BarCodeResult result in reader.ReadBarCodes())
{
    Console.WriteLine($"Decoded value: {result.CodeText}");
}
```

出力が `(01)12345678901231` と一致すれば、生成は成功です。

## 一般的なバリエーションとエッジケース

| Situation | Adjustment | Code snippet |
|-----------|------------|--------------|
| **Different symbology** (e.g., QR, Code128) | `EncodeTypes` の値を変更 | `new BarcodeGenerator(EncodeTypes.QR, "Hello World")` |
| **Custom image format** (JPEG, BMP) | 別の `BarCodeImageFormat` 列挙体を使用 | `generator.Save(path, BarCodeImageFormat.Jpeg)` |
| **Dynamic data** (user input) | ハードコードされた文字列を変数に置き換え | `string data = Console.ReadLine(); var generator = new BarcodeGenerator(EncodeTypes.DatabarOmniDirectional, data);` |
| **Invalid data length** | ジェネレータがスローする `ArgumentException` を捕捉 | ```csharp try { ... } catch (ArgumentException ex) { Console.WriteLine(ex.Message); }``` |

プロのコツ: 選択したシンボルに対して入力長を必ず検証してください。Aspose.BarCode は仕様に合わないデータが渡されると例外をスローします。

## トラブルシューティングチェックリスト

* **Directory not found** – `SaveBarcode` ヘルパーが `output` フォルダーを自動作成しますが、アプリケーションに書き込み権限があることを確認してください。  
* **Unexpected image size** – `Save` を呼び出す前に `XDimension.Pixels` と `BarHeight.Pixels` が設定されているか確認してください。保存後にこれらの値を変更しても、既に書き込まれたファイルには影響しません。  
* **Unreadable barcode** – DataBar シンボルを使用する場合、エンコード文字列が GS1 形式に従っていることを確認してください。括弧の欠落や Application Identifier の誤りはデコード失敗の原因となります。

## 結論

これで実用的な **barcode generator example C#** を使って **create barcode image C#** を行う方法が分かりました。完全なプログラムはモジュール幅を設定し、バー高さを調整し、最小限のコードで PNG ファイルを保存します。ここからは、カラーカスタマイズ、マルチページ PDF エクスポート、ASP.NET Core Web API におけるリアルタイム生成など、追加機能を自由に探求できます。

**次のステップ**

* 他のシンボル（`EncodeTypes.Code128`、`EncodeTypes.QR` など）を試して、スキャンオプションを拡充してください。  
* ジェネレータを Web サービスに統合し、オンデマンドでバーコード画像を返すようにします。  
* Aspose.PDF を使用して、バーコードと製品メタデータを PDF 請求書に組み合わせます。

Happy coding, and enjoy the flexibility that C# provides for barcode image creation!

## 次に学ぶべきことは？

以下のチュートリアルは、本ガイドで示した手法を基にした密接に関連するトピックをカバーしています。各リソースには、完全な動作コード例とステップバイステップの解説が含まれており、追加の API 機能を習得したり、独自プロジェクトで代替実装アプローチを検討したりするのに役立ちます。

- [Barcode Generator Example in C# – Set Columns, Rows & Export Image](/barcode/english/python-java/general/barcode-generator-example-in-c-set-columns-rows-export-image/)
- [Create barcode image C# – GS1 DataMatrix Example](/barcode/english/net/gs1-barcode-encoding/gs1-datamatrix-example/)
- [Barcode Generator Example – Build DataBar Image in C#](/barcode/english/python-java/general/barcode-generator-example-build-databar-image-in-c/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}