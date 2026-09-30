---
category: general
date: 2026-07-27
description: Aspose.BarCode を使用して全方向バーコード画像を作成します。Aspose でバーコードを生成し、アスペクト比を調整し、PNG
  ファイルとして保存する方法を学びましょう。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create omnidirectional barcode image
- generate barcode with aspose
language: ja
lastmod: 2026-07-27
og_description: Asposeを使用して全方向バーコード画像を作成します。このガイドに従い、Asposeでバーコードを生成し、アスペクト比を調整してPNGとしてエクスポートしましょう。
og_image_alt: Screenshot of two omnidirectional barcode images with different aspect
  ratios
og_title: Asposeで全方向バーコード画像を作成する – ステップバイステップ
schemas:
- author: Aspose
  dateModified: '2026-07-27'
  description: Create omnidirectional barcode image using Aspose.BarCode. Learn how
    to generate barcode with Aspose, adjust aspect ratio, and save PNG files.
  headline: Create Omnidirectional Barcode Image with Aspose – Full Guide
  type: TechArticle
- description: Create omnidirectional barcode image using Aspose.BarCode. Learn how
    to generate barcode with Aspose, adjust aspect ratio, and save PNG files.
  name: Create Omnidirectional Barcode Image with Aspose – Full Guide
  steps:
  - name: 1. Different Image Formats
    text: 'Aspose supports BMP, JPEG, TIFF, and SVG in addition to PNG. Swap the enum
      value:'
  - name: 2. Customizing Colors
    text: 'You might need a white barcode on a dark background. Set `ForeColor` and
      `BackColor`:'
  - name: 3. Handling Invalid Aspect Ratios
    text: 'Aspose validates the range (usually 5‑50). If you pass an out‑of‑range
      value, an `ArgumentException` is thrown. Wrap the save call in a try‑catch to
      give a friendly message:'
  - name: 4. Batch Generation
    text: When you have a list of GTINs, loop over them, update `CodeText`, and save
      each file with a unique name. The generator object can be reused, keeping memory
      usage low.
  type: HowTo
tags:
- barcode
- Aspose
- C#
- image-generation
title: Asposeで全方向バーコード画像を作成する – 完全ガイド
url: /ja/python-java/general/create-omnidirectional-barcode-image-with-aspose-full-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose で全方向バーコード画像を作成 – 完全ガイド

**全方向バーコード画像**を作成したいが、どのライブラリを選べばよいか分からないことはありませんか？物流や小売のプロジェクトでは、DataBar Stacked Omnidirectional 形式がコンパクトで高密度なエンコードの秘訣です。  

良いニュースは、**Aspose.BarCode** を使えば数行のコードでバーコードを生成し、アスペクト比を調整し、PNG をそのままディスクに保存できることです。以下では **Aspose でバーコードを生成** する方法、各設定が重要な理由、アスペクト比を変更する際の注意点を詳しく解説します。

---

## 本チュートリアルでカバーする内容

全ライフサイクルを順に見ていきます。

1. 出力フォルダーの設定。
2. DataBar Stacked Omnidirectional ジェネレータのインスタンス化。
3. ピクセル寸法とアスペクト比の設定。
4. バーコードを PNG ファイルとして保存。
5. 他フォーマットやエッジケースへの拡張例。

最後まで実行すれば、2 種類のバーコード画像を出力する C# コンソールアプリが完成します。外部ツールは不要で、純粋に Aspose のコードだけです。

**前提条件**

- .NET 6.0 SDK 以降（コードは .NET Framework 4.7.2 でも動作します）。
- Aspose.BarCode for .NET NuGet パッケージ（`Install-Package Aspose.BarCode`）。
- 画像を書き込めるディスク上のフォルダー。

上記が揃っていれば、さっそく始めましょう。

---

## 手順 1: 出力フォルダーの準備

まず最初に、PNG ファイルを保存する場所をプログラムに伝えます。デモではハードコーディングでも構いませんが、本番環境では設定ファイルから取得するのが一般的です。

```csharp
using System;
using System.IO;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Step 1: Define the folder where the images will be saved
        string outputFolder = Path.Combine(Environment.CurrentDirectory, "Barcodes");
        Directory.CreateDirectory(outputFolder);   // ensures the folder exists
```

*ポイント:* `Directory.CreateDirectory` は冪等（べきとう）で、フォルダーが既に存在していても例外を投げません。そのため try‑catch が不要です。

---

## 手順 2: DataBar Stacked Omnidirectional ジェネレータの作成

次に、特定のエンコードタイプとサンプルデータでジェネレータを起動します。文字列 `"(01)12345678901231"` は 14 桁 GTIN の GS1 アプリケーション識別子構文に従っています。

```csharp
        // Step 2: Create a DataBar Stacked Omnidirectional barcode generator with sample data
        BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
            EncodeTypes.DatabarStackedOmniDirectional,
            "(01)12345678901231");
```

*解説:* `EncodeTypes.DatabarStackedOmniDirectional` を指定すると、どの方向からでも読み取れる全方向バリアントが使用されます。回転する可能性のある小さなラベルに最適です。

---

## 手順 3: 共通バーコードパラメータの設定

実際に描画する前に、最小要素サイズ（X‑Dimension）を定義します。**2 ピクセル** の設定で、ファイルサイズを肥大化させずに鮮明な画像が得られます。

```csharp
        // Step 3: Set common barcode parameters (pixel size of the smallest element)
        barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

*ヒント:* 印刷用に高解像度が必要な場合は 3 か 4 に上げても構いません。ただし X‑Dimension を大きくすると幅と高さが比例して拡大します。

---

## 手順 4: アスペクト比 15 で生成・保存

DataBar ファミリーでは **アスペクト比** を調整でき、高さと幅の比率を制御します。アスペクト比 **15** は全方向バーコードの一般的なデフォルトです。

```csharp
        // Step 4: Generate a barcode with an aspect ratio of 15 and save it as PNG
        barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 15;
        barcodeGenerator.Save(Path.Combine(outputFolder, "DatabarAspectRatio15.png"),
                              BarCodeImageFormat.Png);
```

*期待される結果:* 2 × 1 cm ラベルに快適に収まる、やや高めのバーコードが生成されます。PNG はロスレス品質を保つため、後続の処理や印刷に最適です。

---

## 手順 5: アスペクト比を 30 に変更して再保存

もっと横に広いバーコードが欲しいですか？`AspectRatio` プロパティを変更し、再度 `Save` を呼び出すだけです。ジェネレータを作り直す必要はありません。

```csharp
        // Step 5: Change the aspect ratio to 30 and save the new image
        barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 30;
        barcodeGenerator.Save(Path.Combine(outputFolder, "DatabarAspectRatio30.png"),
                              BarCodeImageFormat.Png);
    }
}
```

*なぜ同じジェネレータを再利用するのか？* Aspose オブジェクトは軽量です。プロパティを変更して再保存する方が新しいインスタンスを構築するより高速で、X‑Dimension などの設定が一貫したまま保たれます。

---

## 完全動作サンプル

全体をまとめると、以下の自己完結型プログラムを新しいコンソールプロジェクトにコピペすれば動作します。

```csharp
using System;
using System.IO;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Define output folder
        string outputFolder = Path.Combine(Environment.CurrentDirectory, "Barcodes");
        Directory.CreateDirectory(outputFolder);

        // Initialize generator with omnidirectional DataBar
        BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
            EncodeTypes.DatabarStackedOmniDirectional,
            "(01)12345678901231");

        // Common settings
        barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;

        // First image – aspect ratio 15
        barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 15;
        barcodeGenerator.Save(Path.Combine(outputFolder, "DatabarAspectRatio15.png"),
                              BarCodeImageFormat.Png);
        Console.WriteLine("Saved: DatabarAspectRatio15.png");

        // Second image – aspect ratio 30
        barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 30;
        barcodeGenerator.Save(Path.Combine(outputFolder, "DatabarAspectRatio30.png"),
                              BarCodeImageFormat.Png);
        Console.WriteLine("Saved: DatabarAspectRatio30.png");
    }
}
```

**期待される出力**

プログラム実行後、`Barcodes` サブフォルダーが作成され、以下のファイルが格納されます。

- `DatabarAspectRatio15.png` – 高めでクラシックな外観。
- `DatabarAspectRatio30.png` – 横長でラベルが広い場合に最適。

どちらも同じ GTIN データを表現していますが、視覚的な比率だけが異なります。

---

## サンプルの拡張（エッジケース＆バリエーション）

### 1. 別の画像フォーマット

Aspose は PNG に加えて BMP、JPEG、TIFF、SVG もサポートしています。列挙子を次のように置き換えてください。

```csharp
barcodeGenerator.Save(Path.Combine(outputFolder, "Databar.svg"),
                      BarCodeImageFormat.Svg);
```

SVG はベクターベースなので、拡大縮小しても鮮明さが失われません。レスポンシブな Web アプリに便利です。

### 2. カラーカスタマイズ

暗い背景に白いバーコードが必要な場合は、`ForeColor` と `BackColor` を設定します。

```csharp
barcodeGenerator.Parameters.Barcode.ForeColor = System.Drawing.Color.White;
barcodeGenerator.Parameters.Barcode.BackColor = System.Drawing.Color.Black;
```

### 3. 無効なアスペクト比の取り扱い

Aspose は通常 5‑50 の範囲を検証します。範囲外の値を渡すと `ArgumentException` がスローされます。保存処理を try‑catch で囲み、ユーザーに分かりやすいメッセージを出すようにしましょう。

```csharp
try
{
    barcodeGenerator.Save(...);
}
catch (ArgumentException ex)
{
    Console.WriteLine($"Invalid aspect ratio: {ex.Message}");
}
```

### 4. バッチ生成

GTIN のリストがある場合は、ループで `CodeText` を更新し、ユニークな名前で各ファイルを保存します。ジェネレータオブジェクトは再利用できるため、メモリ使用量を抑えられます。

---

## よくある落とし穴とプロのコツ

- **`XDimension` を必ず設定** してください。デフォルト（0.33 mm）だと低解像度ディスプレイでぼやけた画像になります。
- **アスペクト比は「高さ ÷ 幅」** であり、逆ではありません。数値が大きいほどバーコードは垂直方向に *短く* なります。
- **ファイルパス:** `Path.Combine` を使ってプラットフォーム依存の区切り文字問題を回避しましょう。特に Linux コンテナで実行する場合に有効です。
- **ライセンス:** Aspose.BarCode は商用製品です。トライアルモードでは画像に透かしが入ります。本番環境では早めにライセンスを登録して予期せぬ表示を防ぎましょう。

---

## 結論

これで **Aspose を使って全方向バーコード画像を作成** し、アスペクト比を調整し、PNG としてエクスポートする方法を 30 行程度の C# コードで習得できました。本チュートリアルは手順ごとの解説と、フォーマット変更・カラー設定・バッチ処理といった拡張例も網羅しています。

次のステップに挑戦したいですか？QR コードの生成、PDF へのバーコード埋め込み、または ASP.NET Core API への統合などです。**Aspose でバーコードを生成** する基本原則はすべてのバーコードタイプで共通なので、今日学んだことをそのまま応用できます。

質問や独自のカスタマイズ例があれば、下のコメント欄でシェアしてください—ハッピーコーディング！

## 次に学ぶべきこと

以下のチュートリアルは、本ガイドで示したテクニックを応用した関連トピックを扱っています。各リソースには完全なコード例とステップバイステップの解説が含まれており、API の追加機能習得や別実装アプローチの探求に役立ちます。

- [How to generate Aztec barcode with custom aspect ratio using Aspose.BarCode for .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)
- [How to Create Barcode Aspose Java - Adjust Image Quality](/barcode/english/java/image-manipulation/adjusting-image-quality-barcode/)
- [How to Generate Barcode Image in Java with Aspose.BarCode](/barcode/english/java/barcode-rendering-techniques/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}