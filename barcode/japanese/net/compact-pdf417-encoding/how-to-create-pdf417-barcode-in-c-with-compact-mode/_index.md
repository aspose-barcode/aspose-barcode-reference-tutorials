---
category: general
date: 2026-09-10
description: C#でPDF417バーコードを素早く作成する。コンパクトモードの有効化、列数の設定、そしてBarcodeGeneratorでPNGを生成する方法を学ぶ。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create PDF417 barcode
- enable compact mode
- barcode generator C#
- how to generate barcode
- how to set columns
language: ja
lastmod: 2026-09-10
og_description: C#でコンパクトモードを有効にし、列数を設定し、PNGとして保存してPDF417バーコードを作成します。完全なステップバイステップガイドに従ってください。
og_image_alt: Screenshot of a compact PDF417 barcode generated with C#
og_title: C#でPDF417バーコードを作成する – コンパクトモードチュートリアル
schemas:
- author: Aspose
  dateModified: '2026-09-10'
  description: Create PDF417 barcode in C# quickly. Learn how to enable compact mode,
    set columns, and generate a PNG with BarcodeGenerator.
  headline: How to create PDF417 barcode in C# with compact mode
  type: TechArticle
tags:
- barcode
- C#
- PDF417
title: C#でコンパクトモードを使用してPDF417バーコードを作成する方法
url: /ja/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-in-c-with-compact-mode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# C#でコンパクトモードを使用してPDF417バーコードを作成する方法

.NETアプリケーションで**PDF417バーコードを作成**する必要がある場合、このガイドで具体的な手順を示します。**コンパクトモードを有効に**し、列数を設定し、BarcodeGenerator C#ライブラリを使用して結果をPNG画像として保存する方法が分かります。

バーコードの生成は、在庫管理、チケットシステム、モバイルスキャンアプリなどで一般的な要件です。このチュートリアルの最後までに、実運用に適したコンパクトPDF417バーコードを生成する自己完結型の実行可能サンプルを手に入れることができます。

## 前提条件

開始する前に、以下を確認してください。

* .NET 6.0以降がインストールされていること（コードは.NET Framework 4.7+でも動作します）
* 最新バージョンの**BarcodeGenerator**ライブラリ（例: Aspose.BarCode for .NET）
* Visual Studio 2022やVS CodeなどのIDEまたはエディタ
* PNGを保存するフォルダーへの書き込み権限

バーコードライブラリ自体以外に追加のNuGetパッケージは必要ありません。

## 手順 1: PDF417バーコードジェネレータの作成

最初のステップは、`EncodeTypes.Pdf417`列挙体とエンコードしたいテキストを指定して`BarcodeGenerator`オブジェクトをインスタンス化することです。このオブジェクトが生成プロセス全体を制御します。

```csharp
using Aspose.BarCode.Generation;

// Step 1: Create a PDF417 barcode generator with the desired text
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(EncodeTypes.Pdf417, "Compact mode");
```

*Why this matters*: `EncodeTypes.Pdf417` の値はライブラリにPDF417シンボルを使用するよう指示し、2番目の引数がペイロードを提供します。`"Compact mode"` はエンコードしたい任意の英数字文字列に置き換えることができます。

## 手順 2: X次元（モジュール幅）の設定

X次元はバーコード内の各小さな正方形（モジュール）の幅を制御します。値を小さくすると画像がタイトになり、スペースが限られている場合に有用です。

```csharp
// Step 2: Set the X dimension (module width) in pixels
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

`2` ピクセルの値は、ほとんどの画面ベーススキャナで可読性とコンパクトさのバランスが取れた設定です。

## 手順 3: 列数の定義

PDF417はデータを行と列のグリッドに配置できます。列数を調整するとバーコードのアスペクト比が変わります。

```csharp
// Step 3: Define the number of columns for the PDF417 barcode
barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 3;
```

**列数の設定**を`3`にすると、ラベルにうまく収まる短くて横長のバーコードが得られます。データ量や対象スキャナに応じて、`1`〜`30` の範囲で試してみてください。

## 手順 4: コンパクトモードの有効化

コンパクトモードは不要なパディング行を除去し、データの完全性を損なうことなくバーコードを小さくします。これが**コンパクトPDF417**を実現する重要なステップです。

```csharp
// Step 4: Enable compact mode by truncating the barcode
barcodeGenerator.Parameters.Barcode.Pdf417.Truncate = true;
```

`Truncate` が `true` の場合、ライブラリはデータを格納するために必要な最小行数を自動的に計算するため、最終画像が「タイト」に見えます。

## 手順 5: 生成したバーコードをPNG画像として保存

最後に、バーコードをファイルに書き出します。PNGはスキャン時に必要な鮮明なエッジを保持します。

```csharp
// Step 5: Save the generated barcode as a PNG image
barcodeGenerator.Save("YOUR_DIRECTORY/CompactPdf417.png", BarCodeImageFormat.Png);
```

`YOUR_DIRECTORY` を、アプリケーションが書き込み可能な絶対パスまたは相対パスに置き換えてください。実行後、`CompactPdf417.png` というファイルが生成され、そこにバーコードが格納されています。

### 完全なソースコード

すべての手順をまとめると、以下のような単一の実行可能プログラムになります。

```csharp
using System;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Create a PDF417 barcode generator with the desired text
        BarcodeGenerator barcodeGenerator = new BarcodeGenerator(EncodeTypes.Pdf417, "Compact mode");

        // Set the X dimension (module width) in pixels
        barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;

        // Define the number of columns for the PDF417 barcode
        barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 3;

        // Enable compact mode by truncating the barcode
        barcodeGenerator.Parameters.Barcode.Pdf417.Truncate = true;

        // Save the generated barcode as a PNG image
        barcodeGenerator.Save("CompactPdf417.png", BarCodeImageFormat.Png);

        Console.WriteLine("PDF417 barcode created successfully.");
    }
}
```

このプログラムを実行すると、実行ファイルと同じフォルダーに `CompactPdf417.png` が作成されます。任意のビューアで画像を開くと、スキャン可能な高コントラストの密なPDF417バーコードが表示されます。

## 他のシナリオでコンパクトモードを有効にする方法

* **バッチ生成** – 多数のバーコードを作成する場合、ジェネレータで `Truncate` を一度設定し、各ペイロードに対して再利用します。
* **異なる画像形式** – 同じ `Save` メソッドで `BarCodeImageFormat.Jpeg` や `BarCodeImageFormat.Bmp` を指定すれば、別のファイルタイプで保存できます。
* **動的列数** – エンコード文字列の長さが変わる場合、文字列長とスキャナの解像度に基づいて最適な列数を計算します。

## 特定のユースケース向け列数の設定

* **ラベル印刷** – 列数を低め（例: `2`‑`5`）にして、狭いラベルに収まるようにします。
* **モバイルスキャン** – 列数を高め（`10`‑`15`）にすると、スマートフォンのカメラがフォーカスしやすい縦長のバーコードになります。
* **誤り訂正のトレードオフ** – 列数が増えると行数が減り、組み込みの誤り訂正に影響します。対象スキャナでテストし、最適なバランスを見つけてください。

## よくある落とし穴とプロのコツ

| Issue | Why it happens | Fix |
|-------|----------------|-----|
| バーコードが読めない | X次元が小さすぎる（例: `1` ピクセル） | `XDimension.Pixels` を少なくとも `2` に増やす |
| 画像が大きすぎる | 短いペイロードに対して列数が高すぎる | `Pdf417.Columns` を減らすか `Truncate` を有効にする |
| PNGファイルが空白 | 出力フォルダーが存在しない、または書き込み権限がない | ディレクトリが存在し、プロセスに書き込み権限があることを確認 |
| スキャナが「データが破損」と報告 | 多くの列を使用しながら `Truncate` が無効 | `Truncate` を有効にするか列数を下げる |

## 結果の検証

任意のPDF417スキャナアプリ（Android/iOS の無料アプリが多数あります）でバーコードを確認できます。`CompactPdf417.png` をアプリで開き、デコードされたテキストが元のペイロード（「Compact mode」）と一致することを確認してください。テキストが異なる場合は、`Truncate` フラグと列設定を再確認してください。

## 次のステップ

* **ASP.NET Core への統合** – コントローラアクションから PNG を直接返却し、ディスクへの保存を省略します。
* **ヒューマンリーダブルテキストの追加** – `barcodeGenerator.Parameters.Barcode.CodeTextParameters` を使用して、バーコード下部にエンコード文字列を表示します。
* **他のシンボロジーの探索** – 同じ `BarcodeGenerator` クラスは QR、Code128、DataMatrix などもサポートしています。`EncodeTypes` を切り替えて試してみてください。

---

### 結論

これで **C#でPDF417バーコードを作成**しながら **コンパクトモードを有効化**し、**列数の設定方法**を制御し、**BarcodeGenerator C# API** を使用して実際のサイズ制約を満たすバーコードを **生成**できるようになりました。コンパクトで高密度なバーコードが必要な任意の .NET プロジェクトにこの手順を適用し、必要に応じて他のバーコード形式にもパターンを拡張してください。コーディングを楽しんでください！

## 次に学ぶべきこと

以下のチュートリアルは、本ガイドで示したテクニックを基にした密接に関連するトピックをカバーしています。各リソースには、ステップバイステップの説明と完全な動作コード例が含まれており、API の追加機能を習得したり、プロジェクトで代替実装アプローチを探求したりするのに役立ちます。

- [Create PDF417 Barcode in C# – Complete Step‑by‑Step Guide](/barcode/english/net/compact-pdf417-encoding/create-pdf417-barcode-in-c-complete-step-by-step-guide/)
- [How to Set Error Level in PDF417 Barcode – Complete Guide](/barcode/english/net/compact-pdf417-encoding/how-to-set-error-level-in-pdf417-barcode-complete-guide/)
- [How to Save Barcode in C# – Generate PDF417 Barcodes](/barcode/english/net/compact-pdf417-encoding/how-to-save-barcode-in-c-generate-pdf417-barcodes/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}