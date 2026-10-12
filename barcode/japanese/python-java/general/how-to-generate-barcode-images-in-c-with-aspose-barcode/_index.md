---
category: general
date: 2026-10-12
description: C#でバーコードを素早く生成する方法。空のバーコードを作成し、バー幅をカスタマイズして鮮明な郵便バーコードを作る方法を学びましょう。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to generate barcode
- create empty barcode
language: ja
lastmod: 2026-10-12
og_description: C#でAspose.BarCodeを使用してバーコードを生成する方法。このガイドでは、空のバーコードを作成し、郵便規格に合わせてバーの寸法を調整する方法を示します。
og_image_alt: Screenshot of generated barcode image created with how to generate barcode
  tutorial
og_title: C#でバーコード画像を生成する方法 – ステップバイステップガイド
schemas:
- author: Aspose
  dateModified: '2026-10-12'
  description: How to generate barcode in C# quickly. Learn to create empty barcode
    and customize bar width for clear postal barcodes.
  headline: How to generate barcode images in C# with Aspose.BarCode
  type: TechArticle
- description: How to generate barcode in C# quickly. Learn to create empty barcode
    and customize bar width for clear postal barcodes.
  name: How to generate barcode images in C# with Aspose.BarCode
  steps:
  - name: Why this step matters
    text: '* **Project scaffolding** ensures the tutorial is runnable without extra
      configuration. * The `using Aspose.BarCode.Generation;` and `using Aspose.BarCode;`
      namespaces expose the `BarcodeGenerator` class and image formats. * Creating
      the output folder programmatically avoids “directory not found” er'
  - name: Expected output
    text: Running the program will create an image similar to the one below (the actual
      image is not displayed here, but you’ll see a clear, 6‑digit barcode when you
      open the file).
  - name: Expected output
    text: 'The generated PNG contains only the bar outlines:'
  - name: Expected output
    text: '```text [PostalRM4SCCFilledBars.png] // solid bars representing "123456"
      ```'
  type: HowTo
tags:
- barcode generation
- C#
- Aspose.BarCode
title: Aspose.BarCode を使用して C# でバーコード画像を生成する方法
url: /ja/python-java/general/how-to-generate-barcode-images-in-c-with-aspose-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# C# と Aspose.BarCode を使用してバーコード画像を生成する方法

文字列から **バーコード画像を生成する方法** が必要な .NET アプリケーション向けに、このガイドは完全で実行可能なソリューションを提供します。標準の Planet と RM4SCC バーコードの生成方法、可読性のためのバー幅の調整、そして **空のバーコードを作成する** バリアントの作成方法を紹介します。コードは最新の Aspose.BarCode for .NET (v.24.10) で動作し、.NET 6 以降で実行できます。

バーコードの生成は、配送ラベル、在庫システム、チケットプラットフォームなどで一般的な要件です。このチュートリアルの最後までに、外部ツールを使用せずに、塗りつぶされたバーコードと空のバーコードの両方をプログラムで生成できるようになります。

## 前提条件

開始する前に、以下が揃っていることを確認してください。

* .NET 6 SDK（またはそれ以降の .NET バージョン）
* Visual Studio 2022 または VS Code
* 有効な Aspose.BarCode for .NET ライセンス（無料評価版でもテストは可能です）
* C# コンソールアプリケーションの基本的な知識

Aspose.BarCode NuGet パッケージは次のコマンドでインストールできます。

```bash
dotnet add package Aspose.BarCode
```

## 手順 1: 最小限のコンソールプロジェクトを設定する

新しいコンソールプロジェクトを作成し、必要な `using` ディレクティブを追加します。以下のコードは単体で動作する例ですので、`Program.cs` にコピーして実行してください。

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

namespace BarcodeDemo
{
    class Program
    {
        static void Main(string[] args)
        {
            // Define output folder (adjust to your environment)
            string outputFolder = @"C:\Barcodes";

            // Ensure the folder exists
            System.IO.Directory.CreateDirectory(outputFolder);

            // Generate filled Planet barcode
            GeneratePlanetBarcode(outputFolder, "123456", filled: true);

            // Generate empty Planet barcode
            GeneratePlanetBarcode(outputFolder, "123456", filled: false);

            // Generate filled RM4SCC barcode
            GenerateRM4SCCBarcode(outputFolder, "123456");

            Console.WriteLine("All barcodes have been saved to " + outputFolder);
        }

        /// <summary>
        /// Generates a Planet barcode and optionally disables bar filling.
        /// </summary>
        static void GeneratePlanetBarcode(string folder, string data, bool filled)
        {
            // Create generator for Planet symbology
            BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Planet, data);

            // Set X dimension (bar width) to 4 pixels for better visibility
            generator.Parameters.Barcode.XDimension.Pixels = 4;

            // Control whether bars are filled or left empty
            generator.Parameters.Barcode.FilledBars = filled;

            // Choose a file name that reflects the filling mode
            string fileName = filled
                ? "PostalPlanetFilledBars.png"
                : "PostalPlanetEmptyBars.png";

            // Save the image as PNG
            generator.Save(System.IO.Path.Combine(folder, fileName), BarCodeImageFormat.Png);
        }

        /// <summary>
        /// Generates an RM4SCC barcode with default filled bars.
        /// </summary>
        static void GenerateRM4SCCBarcode(string folder, string data)
        {
            BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.RM4SCC, data);

            // Consistent bar width with Planet example
            generator.Parameters.Barcode.XDimension.Pixels = 4;

            string fileName = "PostalRM4SCCFilledBars.png";
            generator.Save(System.IO.Path.Combine(folder, fileName), BarCodeImageFormat.Png);
        }
    }
}
```

### この手順が重要な理由

* **Project scaffolding** は、チュートリアルが追加設定なしで実行可能であることを保証します。
* `using Aspose.BarCode.Generation;` と `using Aspose.BarCode;` 名前空間は `BarcodeGenerator` クラスと画像フォーマットを利用可能にします。
* 出力フォルダーをプログラムで作成することで、初回実行時の “directory not found” エラーを回避できます。

## 手順 2: 塗りつぶされた Planet バーコードを生成する

`GeneratePlanetBarcode` の最初の呼び出しでは `filled: true` を渡します。これにより、各バーが実線の黒い矩形として描画される標準的な Planet バーコードが生成されます。

* **生成ファイル:** `PostalPlanetFilledBars.png`
* **視覚的な手がかり:** バーは黒く表示され、印刷郵便物の郵便仕様に合致します。

### 期待される出力

プログラムを実行すると、以下のような画像が作成されます（実際の画像はここに表示されませんが、ファイルを開くと 6 桁のはっきりしたバーコードが確認できます）。

```text
[PostalPlanetFilledBars.png]  // image shows solid black bars
```

## 手順 3: 空のバーコードを作成する（塗りつぶされていない Planet）

**空のバーコード** を作成するには、同じメソッドを `filled: false` で呼び出します。`FilledBars` プロパティは Aspose.BarCode に対し、バーの輪郭だけを描画し、内部を透明にするよう指示します。

* **生成ファイル:** `PostalPlanetEmptyBars.png`
* **使用例:** 背景にロゴやカラーを表示したいが、バーコードの可読性は保ちたい場合に空のバーコードが有用です。

### 期待される出力

生成された PNG にはバーの輪郭のみが含まれます:

```text
[PostalPlanetEmptyBars.png]  // image shows hollow bar shapes
```

## 手順 4: 塗りつぶされた RM4SCC バーコードを生成する

RM4SCC はオランダの郵便バーコード規格です。この例では、Planet バーコードと視覚的な一貫性を保つために同じ X‑dimension（4 ピクセル）を使用しています。

* **生成ファイル:** `PostalRM4SCCFilledBars.png`
* **なぜ RM4SCC か:** 多くの欧州郵便サービスで受け入れられる、数値データをコンパクトにエンコードする形式です。

### 期待される出力

```text
[PostalRM4SCCFilledBars.png]  // solid bars representing "123456"
```

## 実践的なヒントと一般的な落とし穴

| Tip | Explanation |
|-----|-------------|
| **Consistent X‑dimension** | 異なるシンボロジー間で同じ `XDimension.Pixels` 値を使用することで、印刷ラベル上で統一された外観が保証されます。 |
| **Do not reuse the same generator instance** | `FilledBars` を既存のジェネレーターで変更すると予期しない結果になる可能性があります。各バーコードごとに新しい `BarcodeGenerator` をインスタンス化してください。 |
| **Verify image format** | PNG はロスレスでバーコードに最適です。JPEG 圧縮は細いバーをぼやけさせ、スキャン失敗の原因となります。 |
| **License handling** | ライセンスなしでコードを実行すると、生成された画像に透かしが入ります。`Main` の早い段階で `License license = new License(); license.SetLicense("Aspose.BarCode.lic");` を使用してライセンスを適用してください。 |
| **Thread safety** | `BarcodeGenerator` は **スレッドセーフではありません**。並列でバーコードを生成する場合は、スレッドごとに別々のインスタンスを作成してください。 |

## 発生し得るエッジケース

* **データ長の制限** – Planet バーコードは最大 6 桁の数値を受け付けます。これ以上の文字数を指定すると `ArgumentException` がスローされます。ジェネレーター呼び出し前に入力長を検証してください。
* **非数値データ** – RM4SCC も数値入力を前提とします。英数字データの場合は別のシンボロジー（例: Code128）を使用してください。`FilledBars` の設定パターンは、対応するすべてのバーコードタイプで機能します。
* **高解像度印刷** – 画面サイズより大きなバーコードが必要な場合は、`XDimension.Pixels` を増やします（例: 8 または 10）。さらに、`generator.Parameters.Image` の `Resolution` を設定すると、300 dpi の印刷でもバーが鮮明に保たれます。

## 完全なソースファイルのまとめ

以下に、コピー＆ペースト用に全ソースファイルを再掲します。すべての手順、コメント、およびオプションのライセンススニペット（コメントアウト済み）が含まれています。

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

namespace BarcodeDemo
{
    class Program
    {
        static void Main(string[] args)
        {
            // Optional: apply your Aspose.BarCode license here
            // var license = new License();
            // license.SetLicense("Aspose.BarCode.lic");

            string outputFolder = @"C:\Barcodes";
            System.IO.Directory.CreateDirectory(outputFolder);

            // Filled Planet barcode
            GeneratePlanetBarcode(outputFolder, "123456", filled: true);

            // Empty Planet barcode (create empty barcode)
            GeneratePlanetBarcode(outputFolder, "123456", filled: false);

            // Filled RM4SCC barcode
            GenerateRM4SCCBarcode(outputFolder, "123456");

            Console.WriteLine("All barcodes saved to " + outputFolder);
        }

        static void GeneratePlanetBarcode(string folder, string data, bool filled)
        {
            var generator = new BarcodeGenerator(EncodeTypes.Planet, data);
            generator.Parameters.Barcode.XDimension.Pixels = 4;
            generator.Parameters.Barcode.FilledBars = filled;

            string fileName = filled ? "PostalPlanetFilledBars.png"
                                     : "PostalPlanetEmptyBars.png";

            generator.Save(System.IO.Path.Combine(folder, fileName),
                           BarCodeImageFormat.Png);
        }

        static void GenerateRM4SCCBarcode(string folder, string data)
        {
            var generator = new BarcodeGenerator(EncodeTypes.RM4SCC, data);
            generator.Parameters.Barcode.XDimension.Pixels = 4;

            string fileName = "PostalRM4SCCFilledBars.png";
            generator.Save(System.IO.Path.Combine(folder, fileName),
                           BarCodeImageFormat.Png);
        }
    }
}
```

## 結論

これで、C# で Aspose.BarCode を使用して **バーコード画像を生成する方法** を理解し、`FilledBars` プロパティを切り替えることで **空のバーコード** バリアントを作成できるようになりました。本チュートリアルでは以下を取り上げました:

* コンソールプロジェクトの設定と Aspose.BarCode パッケージのインストール
* 塗りつぶされた Planet と RM4SCC バーコードの生成
* 空（輪郭のみ）の Planet バーコードの作成
* 可読性のためのバー幅調整と一般的な落とし穴への対処

次に、他のシンボロジー（Code128、QR、DataMatrix）を検討し、色、サイズ、画像フォーマットで実験してみてください。バーコード生成を Web API や Windows サービスに組み込む場合も同様のパターンで行えます—コンソールの `Main` メソッドをアプリケーションのエントリーポイントに置き換えるだけです。

コーディングを楽しんで、アプリケーションでスキャンを開始しましょう！

## 次に学ぶべきことは？

以下のチュートリアルは、本ガイドで示した手法を基にした密接に関連するトピックを取り上げています。各リソースには、ステップバイステップの解説と完全な動作コード例が含まれており、追加の API 機能を習得し、独自プロジェクトで代替実装アプローチを検討するのに役立ちます。

- [Aspose.BarCode を使用して C# で郵便バーコード画像を作成する方法](/barcode/english/python-java/general/how-to-create-postal-barcode-image-in-c-using-aspose-barcode/)
- [カスタム寸法で C# の郵便バーコードを生成する方法](/barcode/english/python-java/general/how-to-generate-postal-barcode-in-c-with-custom-dimensions/)
- [C# で Aspose.BarCode を使用してバーコード画像を生成する方法](/barcode/english/python-java/general/how-to-generate-barcode-image-with-aspose-barcode-in-c/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}