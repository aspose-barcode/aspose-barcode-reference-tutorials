---
category: general
date: 2026-09-29
description: C#で、塗りつぶしバーと空白バーの両方を持つプラネットバーコードを作成する – Aspose.Barcode を使用したステップバイステップガイド
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create planet barcode
- Planet barcode XDimension
- filled bars
- empty bars
- Aspose.Barcode C#
language: ja
lastmod: 2026-09-29
og_description: C#でプラネットバーコードを素早く作成します。塗りつぶしバーの描画方法、空白バーへの切り替え、そして Aspose.Barcode
  を使用した X 軸寸法の調整方法を学びましょう。
og_image_alt: 'Screenshot of two Planet barcodes: one with filled bars, one with empty
  bars'
og_title: 塗りつぶしと空白のバーで惑星バーコードを作成 – C#チュートリアル
schemas:
- author: Aspose
  dateModified: '2026-09-29'
  description: Create planet barcode in C# with both filled and empty bars – step‑by‑step
    guide using Aspose.Barcode.
  headline: How to create planet barcode with filled and empty bars
  type: TechArticle
- description: Create planet barcode in C# with both filled and empty bars – step‑by‑step
    guide using Aspose.Barcode.
  name: How to create planet barcode with filled and empty bars
  steps:
  - name: Changing the bar width
    text: If your label printer expects a different bar width, modify the `XDimension.Pixels`
      value. For high‑resolution printers, a value of **2** or **3** pixels may be
      preferable; for low‑resolution printers, **5** or **6** pixels can improve scan
      reliability.
  - name: Using a different image format
    text: Aspose.Barcode supports PNG, JPEG, BMP, GIF, and TIFF. Swap `BarCodeImageFormat.Png`
      with another enum value to match your downstream workflow.
  - name: Generating multiple barcodes in a loop
    text: When you need a batch of Planet barcodes (e.g., for a mailing list), wrap
      the generator logic in a `foreach` loop and change the data string each iteration.
  - name: Handling invalid input
    text: The Planet symbology accepts only numeric strings of **5‑8** digits. Supplying
      an invalid value throws an `ArgumentException`. Guard against this with a simple
      validation method.
  type: HowTo
tags:
- barcode
- C#
- Aspose
title: 塗りつぶしと空白のバーで惑星バーコードを作成する方法
url: /ja/python-java/general/how-to-create-planet-barcode-with-filled-and-empty-bars/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# フィルドバーとエンプティバーでプラネットバーコードを作成する方法

C#で **planet barcode** 画像を作成する必要がある場合、このガイドではフィルドバーとエンプティバーの両方のバージョンを生成する方法を正確に示します。バー幅（X‑dimension）の設定方法、`FilledBars` プロパティの切り替え、結果を PNG ファイルとして保存する方法を、すべて Aspose.Barcode ライブラリを使用して解説します。

郵便バーコードの生成は、出荷システム、メールリストアプリケーション、物流ダッシュボードで一般的な要件です。このチュートリアルの最後までに、レポートやメール、印刷物に埋め込める、すぐに使用できる PNG ファイルが 2 つ手に入ります。

## 前提条件

開始する前に、以下が揃っていることを確認してください。

| 要件 | 重要な理由 |
|------|------------|
| .NET 6.0 以降 | C# サンプルの実行環境を提供します。 |
| Visual Studio 2022（または任意の C# IDE） | コードのコンパイルと実行が可能です。 |
| **Aspose.Barcode for .NET** NuGet パッケージ | `BarcodeGenerator` クラスと `EncodeTypes.Planet` を提供します。`dotnet add package Aspose.Barcode` でインストールしてください。 |
| ディスク上のフォルダーへの書き込み権限 | `Save` メソッドが PNG ファイルを書き込むために必要です。 |

## 手順 1: プロジェクトをセットアップし名前空間をインポートする

新しいコンソールプロジェクトを作成（または既存プロジェクトにコードを追加）し、Aspose.Barcode 名前空間を参照します。

```csharp
using System;
using Aspose.Barcode;
using Aspose.Barcode.Generation;
```

これらの `using` ディレクティブにより、チュートリアルで使用する `BarcodeGenerator`、`EncodeTypes`、画像形式列挙体にアクセスできます。

## 手順 2: デフォルト（フィルド）バーで Planet バーコードを作成する

最初のバーコードはライブラリのデフォルト描画を使用し、バーが塗りつぶされます。

```csharp
// Initialise a generator for the Planet (postal) barcode with sample data.
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(EncodeTypes.Planet, "123456");

// Optional: adjust the bar width (X dimension) to 4 pixels for clearer printing.
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 4;

// Save the image with filled bars.
string filledPath = @"C:\Barcodes\PlanetFilledBars.png";
barcodeGenerator.Save(filledPath, BarCodeImageFormat.Png);

Console.WriteLine($"Filled Planet barcode saved to: {filledPath}");
```

**動作の理由:**  
`EncodeTypes.Planet` は Aspose.Barcode に対し、米国郵便公社（USPS）が使用する **Planet** シンボルを使用するよう指示します。`XDimension` プロパティは各バーの幅を制御し、4 ピクセルに設定すると標準的なラベルプリンターでの印刷に適したバーコードが生成されます。デフォルトでは `FilledBars` が `true` になっているため、バーは実線で描画されます。

## 手順 3: エンプティバーで Planet バーコードを作成する

同じデータを *エンプティ* バーで生成するには、`FilledBars` フラグを反転させるだけで、他の設定はそのままで構いません。

```csharp
// Re‑use the same variable for clarity.
barcodeGenerator = new BarcodeGenerator(EncodeTypes.Planet, "123456");

// Keep the same X‑dimension for visual consistency.
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 4;

// Render empty bars instead of filled ones.
barcodeGenerator.Parameters.Barcode.FilledBars = false;

// Save the image with empty bars.
string emptyPath = @"C:\Barcodes\PlanetEmptyBars.png";
barcodeGenerator.Save(emptyPath, BarCodeImageFormat.Png);

Console.WriteLine($"Empty Planet barcode saved to: {emptyPath}");
```

**重要なポイント:**  
一部のメールシステムでは、暗い背景やコントラストの高い配色で印刷した際の可読性向上のために **エンプティバー** スタイルが求められます。`FilledBars = false` と設定すると、バーの輪郭だけが描画され、内部は透明（背景が透けて見える）になります。

## 期待される出力

プログラム実行後、`C:\Barcodes`（または指定したパス）に以下の 2 つの PNG ファイルが作成されます。

| ファイル | ビジュアル説明 |
|----------|----------------|
| `PlanetFilledBars.png` | 白背景に黒の実線長方形が並んだバーコード。 |
| `PlanetEmptyBars.png`  | 黒い輪郭だけで内部が透明なバーコード（背景が透けて見える）。 |

両画像は同じ数列 `"123456"` をエンコードし、バー幅は 4 ピクセルで統一されているため、塗りつぶしスタイル以外は見た目が一致します。

## よくあるバリエーションとエッジケース

### バー幅を変更する

ラベルプリンターが別のバー幅を要求する場合は、`XDimension.Pixels` の値を変更します。高解像度プリンターでは **2**〜**3** ピクセル、低解像度プリンターでは **5**〜**6** ピクセルが走査信頼性を向上させます。

```csharp
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 5; // example for coarse printers
```

### 別の画像形式を使用する

Aspose.Barcode は PNG、JPEG、BMP、GIF、TIFF をサポートしています。`BarCodeImageFormat.Png` を別の列挙値に置き換えて、 downstream のワークフローに合わせてください。

```csharp
barcodeGenerator.Save("Planet.tiff", BarCodeImageFormat.Tiff);
```

### ループで複数のバーコードを生成する

大量の Planet バーコード（例: メーリングリスト用）が必要な場合は、ジェネレータロジックを `foreach` ループで囲み、各イテレーションでデータ文字列を変更します。

```csharp
string[] postalCodes = { "123456", "654321", "112233" };
int index = 1;
foreach (var code in postalCodes)
{
    var gen = new BarcodeGenerator(EncodeTypes.Planet, code);
    gen.Parameters.Barcode.XDimension.Pixels = 4;
    gen.Save($@"C:\Barcodes\Planet_{index}_filled.png", BarCodeImageFormat.Png);
    gen.Parameters.Barcode.FilledBars = false;
    gen.Save($@"C:\Barcodes\Planet_{index}_empty.png", BarCodeImageFormat.Png);
    index++;
}
```

### 無効な入力の取り扱い

Planet シンボルは **5〜8 桁** の数値文字列のみ受け付けます。無効な値を渡すと `ArgumentException` がスローされます。簡易的なバリデーションメソッドで事前にチェックしましょう。

```csharp
bool IsValidPlanet(string value) => System.Text.RegularExpressions.Regex.IsMatch(value, @"^\d{5,8}$");

string data = "ABC123";
if (!IsValidPlanet(data))
{
    Console.WriteLine("Invalid Planet data – must be 5 to 8 digits.");
    return;
}
```

## プロのコツ: スキャナーエミュレータでバーコードを検証する

Aspose.Barcode には生成した画像が元データに正しくデコードできるか確認できる `BarcodeReader` クラスが用意されています。

```csharp
using Aspose.Barcode.Reader;

// Verify filled barcode
using (BarCodeReader reader = new BarCodeReader(filledPath, DecodeType.Planet))
{
    if (reader.Read())
        Console.WriteLine($"Decoded from filled image: {reader.GetCodeText()}");
}

// Verify empty barcode
using (BarCodeReader reader = new BarCodeReader(emptyPath, DecodeType.Planet))
{
    if (reader.Read())
        Console.WriteLine($"Decoded from empty image: {reader.GetCodeText()}");
}
```

両ファイルで `"123456"` が出力されれば、バーコードは正しく生成されています。

## 結論

これで C# で **planet barcode** 画像を、フィルドバーとエンプティバーの両スタイルで作成し、**Planet バーコード XDimension** を制御し、**Aspose.Barcode** ライブラリを使って PNG 形式で保存する方法が分かりました。バー幅を調整したり、画像形式を変更したり、値のコレクションをループ処理したりすれば、あらゆる郵便コードワークフローに対応できます。

次に試してみると良い項目:

* バーコード下に **人が読めるテキスト** を追加する (`barcodeGenerator.Parameters.Caption.Show = true`)。
* Aspose.PDF を使って **PDF 文書にバーコードを埋め込む**。
* **USPS POSTNET** や **Intelligent Mail** など、他の郵便シンボルを生成する。

パラメータを自由にいじって、出荷システムやメール配信システムに組み込んでみてください。コーディングを楽しんで！

## 次に学ぶべきことは？

以下のチュートリアルは、本ガイドで示したテクニックを応用した関連トピックを扱っています。各リソースには完全なコード例とステップバイステップの解説が含まれており、API の追加機能習得や代替実装アプローチの探求に役立ちます。

- [Create Planet Barcode in C# – Full Step‑by‑Step Guide](/barcode/english/python-java/general/create-planet-barcode-in-c-full-step-by-step-guide/)
- [Create planet barcode in C# – complete programming guide](/barcode/english/python-java/general/create-planet-barcode-in-c-complete-programming-guide/)
- [Barcode generator C# – create Planet barcode and RM4SCC example](/barcode/english/python-java/general/barcode-generator-c-create-planet-barcode-and-rm4scc-example/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}