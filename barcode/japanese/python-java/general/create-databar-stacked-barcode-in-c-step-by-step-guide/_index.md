---
category: general
date: 2026-08-06
description: C#でデータバー スタック型バーコードをすばやく作成します。X寸法の設定、アスペクト比の調整、DataBar Stacked Omnidirectional
  ジェネレータを使用した PNG ファイルのエクスポート方法を学びましょう。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create databar stacked barcode
- DataBar Stacked Omnidirectional
- barcode aspect ratio
- BarcodeGenerator C#
- BarCodeImageFormat PNG
language: ja
lastmod: 2026-08-06
og_description: Aspose.BarCode を使用して C# でデータバー スタック型バーコードを作成します。このチュートリアルでは、X 次元の設定方法、アスペクト比の変更方法、PNG
  画像の保存方法を示します。
og_image_alt: Screenshot of two PNG files generated from a DataBar Stacked Omnidirectional
  barcode with different aspect ratios
og_title: C#でデータバー スタックドバーコードを作成する – 完全プログラミングガイド
schemas:
- author: Aspose
  dateModified: '2026-08-06'
  description: Create databar stacked barcode in C# quickly. Learn to set X dimension,
    adjust aspect ratio, and export PNG files using the DataBar Stacked Omnidirectional
    generator.
  headline: Create databar stacked barcode in C# – step‑by‑step guide
  type: TechArticle
tags:
- barcode
- C#
- Aspose.BarCode
title: C#でデータバー スタックドバーコードを作成する – ステップバイステップガイド
url: /ja/python-java/general/create-databar-stacked-barcode-in-c-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# C# でデータバー スタックド バーコードを作成する – ステップバイステップ ガイド

C# で **create databar stacked barcode** 画像を作成する必要がある場合、このガイドでは Aspose.BarCode ライブラリを使用して正確に行う方法を示します。X 次元の設定、バーコードのアスペクト比の変更、結果を PNG ファイルとして保存する方法を、簡潔な手順で学べます。

DataBar Stacked バーコードの生成は、小売スキャンや物流追跡のために GS1‑128 データをエンコードする必要がある場合に一般的です。以下のセクションでは、プロジェクトのセットアップから出力の検証までをすべてカバーし、詳細を見逃すことなく任意の .NET アプリケーションにソリューションを統合できるようにします。

## 前提条件

* **.NET 6.0**（またはそれ以降）がインストールされていること – コードは最新の SDK を対象としています。
* **Aspose.BarCode for .NET** の **licensed** コピー。無料評価版はテストに使用できますが、透かしが追加されます。
* **Visual Studio 2022** や **VS Code** など、C# 拡張機能がインストールされた IDE。
* **C#** の構文と GS1 アプリケーション識別子の概念に関する基本的な知識。

> **Pro tip:** NuGet パッケージマネージャーを使用する場合、コマンド `dotnet add package Aspose.BarCode` がすべての依存関係を自動的に解決します。

## 手順 1: 新しいコンソール プロジェクトを作成する

ターミナルまたは Package Manager Console を開き、次のコマンドを実行します：

```bash
dotnet new console -n DatabarStackedDemo
cd DatabarStackedDemo
dotnet add package Aspose.BarCode
```

`dotnet new console` コマンドは最小限の **Program.cs** ファイルを作成します。**Aspose.BarCode** パッケージを追加すると、`BarcodeGenerator` クラスが利用可能になります。

## 手順 2: DataBar Stacked Omnidirectional ジェネレータを初期化する

**Program.cs** を開き、デフォルトの内容を以下のコードに置き換えます。最初の行は **DataBar Stacked Omnidirectional** シンボル用に構成された **BarcodeGenerator** を作成し、GS1‑128 ペイロードを供給します。

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Step 2: Initialize the generator for a DataBar Stacked Omnidirectional barcode
        // "(01)12345678901231" encodes a GTIN‑14 with Application Identifier (01)
        var generator = new BarcodeGenerator(
            EncodeTypes.DatabarStackedOmniDirectional,
            "(01)12345678901231");

        // Continue with configuration...
```

**Why this matters:** `EncodeTypes.DatabarStackedOmniDirectional` 列挙値は、ライブラリに **databar stacked barcode** を生成させることを指示します。これは omnidirectional DataBar ファミリーのスタックド バリアントです。このシンボルは最大 14 桁の数字を保持でき、GTIN‑14 コードに最適です。

## 手順 3: X 次元（モジュール幅）を設定する

X 次元は最小バー（モジュール）の幅を制御します。値が小さすぎると低解像度プリンターでの描画が不十分になり、逆に大きすぎるとラベルのスペースを超えてしまう可能性があります。

```csharp
        // Step 3: Define the module width – 2 pixels gives a crisp, printable barcode
        generator.Parameters.Barcode.XDimension.Pixels = 2;
```

> **Tip:** `Pixels` プロパティは画面ベースのテストに便利です。印刷重視のシナリオでは、代わりに `generator.Parameters.Barcode.XDimension.Millimeters` を使用してください。

## 手順 4: アスペクト比を調整し、最初の画像を保存する

**アスペクト比** はスタックド バーコードの高さと幅の関係に影響します。DataBar Stacked Omnidirectional タイプは 10 から 30 の比率をサポートしています。視覚的な影響を示すために 2 枚の画像を生成します。

```csharp
        // Step 4a: Set aspect ratio to 15 (default is 15) and save as PNG
        generator.Parameters.Barcode.DataBar.AspectRatio = 15;
        generator.Save("DatabarAspectRatio15.png", BarCodeImageFormat.Png);
```

`generator.Save` の呼び出しにより、現在の作業ディレクトリに **PNG** ファイルが書き込まれます。`BarCodeImageFormat.Png` 列挙値はロスレス圧縮を保証し、さらなる処理や PDF への埋め込みに最適です。

## 手順 5: アスペクト比を 30 に変更し、2 番目の画像を保存する

ここでは、アスペクト比を **30** に変更してスタックド バーの高さを増やします。これにより X 次元を変更せずにバーコードが高くなります。

```csharp
        // Step 5a: Increase aspect ratio to 30 for a taller barcode
        generator.Parameters.Barcode.DataBar.AspectRatio = 30;
        generator.Save("DatabarAspectRatio30.png", BarCodeImageFormat.Png);

        Console.WriteLine("Two barcode images have been generated:");
        Console.WriteLine(" • DatabarAspectRatio15.png");
        Console.WriteLine(" • DatabarAspectRatio30.png");
    }
}
```

プログラムを実行すると、2 つの PNG ファイルが生成されます：

* **DatabarAspectRatio15.png** – 小さなラベルに適したコンパクトなバーコード。
* **DatabarAspectRatio30.png** – 低コントラストの表面でスキャン信頼性を向上させる、より高いバーコード。

任意のビューアで画像を開き、バーが正しくスタックされていること、エンコードされたデータが元の GS1 文字列と一致していることを確認できます。

## 手順 6: エンコードされた値を検証する（オプション）

バーコードが入力文字列を正しく表していることを確認する必要がある場合、同じライブラリでデコードできます：

```csharp
        // Optional: Decode the generated PNG to ensure correctness
        var decoder = new BarCodeReader("DatabarAspectRatio15.png", DecodeType.DatabarStackedOmniDirectional);
        foreach (BarCodeResult result in decoder.ReadBarCodes())
        {
            Console.WriteLine($"Decoded text: {result.CodeText}");
        }
```

デコーダは `(01)12345678901231` を出力すべきで、**create databar stacked barcode** プロセスがデータを保持したことが証明されます。

## よくある落とし穴と回避方法

| Issue | Why it happens | Fix |
|-------|----------------|-----|
| バーコードがぼやけて表示される | 出力解像度に対して X 次元が低すぎるため | `XDimension.Pixels` を増やすか、印刷時は `Millimeters` を使用する |
| スキャナーが「シンボルが見つかりません」と報告する | サポートされている 10‑30 の範囲外のアスペクト比であるため | 比率を 10〜30 の間に保つ。15 と 30 は安全なデフォルトです |
| PNG に透かしが入っている | Aspose.BarCode の無料評価ライセンスを使用しているため | フルライセンスを購入するか、テスト目的でトライアルを使用する |
| 2 番目の画像でデコードに失敗する | デコーダが誤ったシンボルに設定されていたため | スタックド バーコードを読む際は `DecodeType.DatabarStackedOmniDirectional` を使用する |

## 次のステップ

これで **create databar stacked barcode** 画像を作成できるようになったので、以下を検討できるでしょう：

* **Aspose.PDF** などの PDF ライブラリを使用して PNG を PDF 請求書に埋め込む。
* Web API でバーコードをリアルタイムに生成する – ASP.NET Core コントローラから PNG バイト列を直接返す。
* `EncodeTypes` 列挙体を変更して、他の DataBar バリアント（例：`DatabarExpanded`、`DatabarLimited`）を試す。
* `generator.Parameters.Barcode.ForeColor` と `BackColor` を設定して、ブランド固有のデザインに合わせて色を調整する。

これらのトピックはすべて、ここで扱ったコア概念（`BarcodeGenerator` の初期化、視覚パラメータの設定、`BarCodeImageFormat` での保存）に基づいています。

---

### 結論

このチュートリアルでは、Aspose.BarCode を使用して C# で **create databar stacked barcode** 画像を作成する方法を示しました。**X 次元** の設定、**バーコードのアスペクト比** の変更、`BarcodeGenerator` を使用した **PNG** ファイルへのエクスポートを学びました。オプションのデコード手順により、エンコードされた GS1 データが正確であることも確認できます。これらのパターンを在庫管理、出荷、POS アプリケーションに適用し、ライブラリが提供する多数のカスタマイズオプションを探求してください。コーディングを楽しんで！

## 次に学ぶべきことは？

以下のチュートリアルは、本ガイドで示した手法を基にした密接に関連するトピックを取り上げています。各リソースには、ステップバイステップの解説付きの完全な動作コード例が含まれており、追加の API 機能を習得し、独自プロジェクトで代替実装アプローチを検討するのに役立ちます。

- [一次元データバーバーコードの高さ調整](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-barcode-height-adjustment/)
- [バーコード画像の生成 – GS1 クーポン UPC-A データバー](/barcode/english/net/gs1-barcode-encoding/gs1-coupon-upc-a-databar-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}