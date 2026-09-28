---
category: general
date: 2026-07-15
description: C# のバーコードジェネレータ例です。列の設定方法、行の設定方法、そしてバーコード画像をすばやくエクスポートする方法を示しています。ステップバイステップのガイドに従ってください。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- barcode generator example
- how to set columns
- how to set rows
- export barcode image
- create barcode image c#
language: ja
lastmod: 2026-07-15
og_description: C# のバーコードジェネレーター例では、列の設定方法、行の設定方法、そしてバーコード画像のエクスポート方法を示します。数分でフルワークフローを学びましょう。
og_image_alt: Screenshot of a barcode generator example showing column and row settings
  in C#
og_title: C# のバーコードジェネレーター例 – 列、行、画像エクスポート
schemas:
- author: Aspose
  dateModified: '2026-07-15'
  description: Barcode generator example in C# showing how to set columns, how to
    set rows, and export barcode image quickly. Follow this step‑by‑step guide.
  headline: Barcode Generator Example in C# – Set Columns, Rows & Export Image
  type: TechArticle
- description: Barcode generator example in C# showing how to set columns, how to
    set rows, and export barcode image quickly. Follow this step‑by‑step guide.
  name: Barcode Generator Example in C# – Set Columns, Rows & Export Image
  steps:
  - name: '**Add colors** – Set `generator.Parameters.Barcode.ForegroundColor` to
      `Color.Blue`.'
    text: '**Add colors** – Set `generator.Parameters.Barcode.ForegroundColor` to
      `Color.Blue`.'
  - name: '**Encode different data** – Pass a variable string instead of the hard‑coded
      `"Databar Expanded Stacked long"`.'
    text: '**Encode different data** – Pass a variable string instead of the hard‑coded
      `"Databar Expanded Stacked long"`.'
  - name: '**Batch processing** – Loop over a CSV file of product codes, generating
      a PNG for each.'
    text: '**Batch processing** – Loop over a CSV file of product codes, generating
      a PNG for each.'
  - name: '**Integrate with a web API** – Expose an endpoint that returns the barcode
      as a base64‑encoded string.'
    text: '**Integrate with a web API** – Expose an endpoint that returns the barcode
      as a base64‑encoded string.'
  type: HowTo
tags:
- barcode
- C#
- image export
title: C# バーコードジェネレータの例 – 列・行の設定と画像のエクスポート
url: /ja/python-java/general/barcode-generator-example-in-c-set-columns-rows-export-image/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# C# のバーコードジェネレータ例 – 完全ガイド

DataBar Expanded Stacked バーコードを、列や行のレイアウトを調整しながら画像としてエクスポートする **バーコードジェネレータ例** を作りたいと思ったことはありませんか？同じ悩みを抱える開発者は多いです。カスタムレイアウトオプションを備えた DataBar Expanded Stacked バーコードを手軽に生成する方法が必要です。このチュートリアルでは、**列の設定方法**、**行の設定方法**、そして最終的に **バーコード画像** をエクスポートする手順をステップバイステップで解説し、クリーンで本番環境でも使えるコードを提供します。

このガイドを最後まで読むと、バーコード画像を生成し、レイアウトを調整し、2 つの PNG ファイルをディスクに保存する完全な実行可能プログラムが手に入ります。謎のライブラリや隠された設定は不要です。純粋な C# と信頼性の高いバーコード SDK だけです。

---

## 前提条件

作業を始める前に、以下が揃っていることを確認してください。

- **.NET 6.0**（またはそれ以降の .NET バージョン）。コードは .NET Framework でもコンパイルできますが、.NET 6 以上を推奨します。
- DataBar Expanded Stacked をサポートする **バーコード生成ライブラリ**。本例では **Aspose.BarCode for .NET**（トライアル版は無料）を使用します。
- 開発環境 – Visual Studio 2022、Rider、または VS Code のいずれか。
- PNG ファイルを書き込むフォルダーへの書き込み権限。

ライブラリがまだ無い場合は、NuGet から取得してください。

```bash
dotnet add package Aspose.BarCode
```

この 1 行で、後で使用する `BarcodeGenerator` クラスや `BarCodeImageFormat` 列挙体など、必要なすべてがインストールされます。

---

## 手順 1: プロジェクトの骨組みを作成

新しいコンソール アプリケーションを作成し、必要な `using` ディレクティブを追加します。

```csharp
using System;
using Aspose.BarCode.Generation;   // Core barcode generation classes
using Aspose.BarCode;               // For BarCodeImageFormat enum
```

以下が **完全な** `Program.cs` の雛形です。

```csharp
namespace BarcodeDemo
{
    internal class Program
    {
        static void Main(string[] args)
        {
            // We'll fill this in in the next steps.
        }
    }
}
```

> **プロのコツ:** `Main` メソッドはシンプルに保ちましょう。重い処理はヘルパーメソッドに委譲すれば、テストや再利用が容易になります。

---

## 手順 2: バーコードジェネレータ例を作成

ここで、DataBar Expanded Stacked バーコードを生成するコアとなる **バーコードジェネレータ例** を構築します。

```csharp
static BarcodeGenerator CreateGenerator()
{
    // Step 1: Instantiate the generator for DataBar Expanded Stacked.
    // The second argument is the text you want encoded.
    var generator = new BarcodeGenerator(
        EncodeTypes.DatabarExpandedStacked,
        "Databar Expanded Stacked long");

    // Optional: fine‑tune image size or resolution if needed.
    generator.Parameters.Image.Width = 300;
    generator.Parameters.Image.Height = 150;

    return generator;
}
```

なぜこのロジックを別メソッドに分けるかというと、**バーコードジェネレータ例** の処理を分離でき、異なるデータで複数のバーコードを生成したいときに再利用しやすくなるからです。

---

## 手順 3: 列の設定方法

DataBar Expanded Stacked 形式は列指向のレイアウトで描画できます。デフォルトでも問題ありませんが、ラベルサイズに合わせて列数を指定したいことが多いです。以下は **列を 4 に設定** する例です。

```csharp
static void SetColumns(BarcodeGenerator generator, int columns)
{
    // Step 2: Adjust the column count.
    generator.Parameters.Barcode.DataBar.Columns = columns;
}
```

> **列が重要な理由:** 各列は垂直方向の余白を増やし、狭いラベルに印刷する際に有効です。`4` に設定すれば、スキャン信頼性を損なうことなくバランスの取れた可読性の高いバーコードが得られます。

メインフローではこのメソッドを次のように呼び出します。

```csharp
var generator = CreateGenerator();
SetColumns(generator, 4);
```

---

## 手順 4: 行の設定方法

短くて横長のラベルに印刷する場合、よりコンパクトなレイアウトが必要になることがあります。そこで **行の設定方法** が役立ちます。列指向から行指向に切り替えることで、バーコードの占有面積を縮小できます。

```csharp
static void SetRows(BarcodeGenerator generator, int rows)
{
    // Step 4: Change the layout to use rows instead of columns.
    generator.Parameters.Barcode.DataBar.Rows = rows;
}
```

呼び出し例は次の通りです。

```csharp
SetRows(generator, 3);
```

> **エッジケース:** 列と行を同時に設定することはできません。`Rows` に非ゼロ値を設定すると SDK は行優先で処理します。レイアウトを切り替える際は、もう一方のプロパティを `0` にリセットしてください。

```csharp
generator.Parameters.Barcode.DataBar.Columns = 0; // Disable columns when using rows
```

---

## 手順 5: バーコード画像をエクスポート

レイアウト設定が完了したら、最後に **バーコード画像** をエクスポートします。SDK は PNG、JPEG、BMP などをサポートしていますが、PNG はロスレスで多くのラベルプリンターに最適です。

```csharp
static void SaveBarcode(BarcodeGenerator generator, string filePath)
{
    // Step 5: Save the image using the PNG format.
    generator.Save(filePath, BarCodeImageFormat.Png);
}
```

`Main` での全体像は次の通りです。

```csharp
static void Main(string[] args)
{
    // 1️⃣ Create the generator (barcode generator example)
    var generator = CreateGenerator();

    // 2️⃣ Set columns and save the first image
    SetColumns(generator, 4);
    string colsPath = @"YOUR_DIRECTORY\DatabarCols4.png";
    SaveBarcode(generator, colsPath);
    Console.WriteLine($"Barcode with 4 columns saved to {colsPath}");

    // 3️⃣ Switch to rows and save the second image
    SetRows(generator, 3);
    // Clear columns to avoid conflict
    generator.Parameters.Barcode.DataBar.Columns = 0;
    string rowsPath = @"YOUR_DIRECTORY\DatabarRows3.png";
    SaveBarcode(generator, rowsPath);
    Console.WriteLine($"Barcode with 3 rows saved to {rowsPath}");
}
```

### 期待される出力

プログラムを実行すると、`YOUR_DIRECTORY` に以下の 2 つの PNG ファイルが生成されます。

- **DatabarCols4.png** – 4 列の垂直レイアウトで描画されたバーコード。
- **DatabarRows3.png** – 同じデータを 3 行の水平レイアウトで描画したバーコード。

どちらの画像も `CreateGenerator` で設定した 300 × 150 px のサイズで、印刷や PDF への埋め込みにすぐ使用できます。

---

## よくある落とし穴と対策

| 問題 | 発生理由 | 対策 |
|------|----------|------|
| **ファイルパスエラー** | ディレクトリが存在しない相対パスを使用すると `DirectoryNotFoundException` がスローされる | `Path.Combine(Environment.CurrentDirectory, "output", "file.png")` を使用するか、`Directory.CreateDirectory` でフォルダーを事前に作成 |
| **行と列の競合** | 両方のプロパティを設定すると SDK が列を無視する | レイアウトを切り替える際は、反対側のプロパティを明示的に `0` に設定 |
| **未対応のバーコード種別** | ライブラリによっては DataBar Expanded Stacked をサポートしていない | 使用しているライブラリが `EncodeTypes.DatabarExpandedStacked` を含んでいるか確認 |
| **画像品質が低い** | デフォルト DPI が高解像度プリンターに不足することがある | `generator.Parameters.Image.ResolutionX/Y` を `300` 以上に設定 |

---

## バーコードジェネレータ例の拡張

**バーコードジェネレータ例** が完成したので、次にできることをいくつか紹介します。

1. **カラーを追加** – `generator.Parameters.Barcode.ForegroundColor` に `Color.Blue` を設定。
2. **データを変更** – ハードコードされた `"Databar Expanded Stacked long"` の代わりに変数文字列を渡す。
3. **バッチ処理** – CSV ファイルの製品コードをループし、各コードごとに PNG を生成。
4. **Web API と統合** – エンドポイントを公開し、バーコードを Base64 文字列として返す。

これらの拡張はすべて同じパターンに従います。`BarcodeGenerator` インスタンスを設定し、必要に応じて `Save` または `Export` を呼び出すだけです。

---

## 結論

C# で **バーコードジェネレータ例** を作成し、**列の設定方法**、**行の設定方法**、そして **バーコード画像のエクスポート** 方法を順に解説しました。コードは自己完結型で、Aspose.BarCode があればすぐに動作し、可読性と保守性のベストプラクティスを示しています。

ぜひデータ文字列を変えてみたり、画像サイズを調整したり、別のシンボルに切り替えてみてください。ここで学んだ「ジェネレータの初期化」「レイアウトパラメータの設定」「エクスポート」の流れは、SDK がサポートするほぼすべてのバーコード種別に応用できます。

C# でバーコード画像を作成する際の質問や、特定のラベルプリンターに関するサポートが必要な場合は、下のコメント欄にご相談ください。Happy coding!

---

## 次に学ぶべきこと

以下のチュートリアルは、本ガイドで示したテクニックを応用した関連トピックを扱っています。各リソースには、ステップバイステップの解説と完全なコード例が含まれているので、API の追加機能や別実装アプローチを自分のプロジェクトに取り入れる際に役立ちます。

- [Create DotCode barcode image – rows & columns (Aspose.BarCode)](/barcode/english/net/dotcode-barcode-configuration/dotcode-rows-columns-configuration/)
- [Create barcode image c# – Configure Codablock F Rows & Columns](/barcode/english/net/codablock-f-encoding/codablock-f-row-column-configuration/)
- [Create barcode image C# – GS1 DataMatrix Example](/barcode/english/net/gs1-barcode-encoding/gs1-datamatrix-example/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}