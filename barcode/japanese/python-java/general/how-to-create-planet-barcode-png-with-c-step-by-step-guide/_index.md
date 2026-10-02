---
category: general
date: 2026-09-07
description: C#で素早くプラネットバーコードPNGを作成する。Aspose.BarCodeを使用し、塗りつぶしバーと空白バーでプラネットバーコード画像を生成する方法を学びましょう。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create planet barcode png
- how to generate planet barcode
language: ja
lastmod: 2026-09-07
og_description: C#で高速にプラネットバーコードPNGを作成します。このガイドに従って、Aspose.BarCodeを使用し、塗りつぶしバーと空白バーを持つプラネットバーコード画像の生成方法を学びましょう。
og_image_alt: Planet barcode PNG image showing filled bars and empty‑bars version
og_title: C#で惑星バーコードPNGを作成する – 完全コーディングチュートリアル
schemas:
- author: Aspose
  dateModified: '2026-09-07'
  description: Create planet barcode PNG in C# quickly. Learn how to generate planet
    barcode images using Aspose.BarCode with filled and empty bars.
  headline: How to create planet barcode PNG with C# – step‑by‑step guide
  type: TechArticle
- description: Create planet barcode PNG in C# quickly. Learn how to generate planet
    barcode images using Aspose.BarCode with filled and empty bars.
  name: How to create planet barcode PNG with C# – step‑by‑step guide
  steps:
  - name: What if I need a different data format?
    text: 'Planet barcodes accept numeric strings up to 12 digits. If you pass a non‑numeric
      value, Aspose throws an `ArgumentException`. Validate the input before creating
      the generator:'
  - name: How do I change the image size without altering bar thickness?
    text: 'Use the `Resolution` property or scale the resulting bitmap after saving:'
  - name: Can I generate other image formats?
    text: Yes. Replace `BarCodeImageFormat.Png` with `BarCodeImageFormat.Jpeg`, `Bmp`,
      or `Gif`. The API supports all common raster formats.
  - name: What about color customization?
    text: 'Set `BarColor` and `BackColor` on the `Barcode` parameters:'
  type: HowTo
tags:
- barcode
- C#
- Aspose.BarCode
title: C#でプラネットバーコードPNGを作成する方法 – ステップバイステップガイド
url: /ja/python-java/general/how-to-create-planet-barcode-png-with-c-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# C# でプラネットバーコード PNG を作成する方法 – ステップバイステップガイド

C# で **プラネットバーコード PNG** ファイルを作成する必要がある場合、このガイドでは正確な手順を示します。郵便サービスの統合や物流ダッシュボードの構築など、**プラネットバーコード** の画像を塗りつぶしバーと空バーの両方で生成する方法を学べます。

このチュートリアルで学べること：

* 画像の出力フォルダーを設定する。  
* Planet シンボロジー用に `BarcodeGenerator` を構成する。  
* デフォルトの塗りつぶしバー形式で PNG を生成する。  
* 視覚的コントラストのために空バーで PNG を生成する。  

外部サービスは不要です。すべて .NET 6 以降でローカル実行できます。

## 前提条件

開始する前に、以下を確認してください：

| 必要条件 | 理由 |
|-------------|----------------|
| .NET 6 SDK（またはそれ以降） | C# コンソールアプリの実行環境を提供します。 |
| Visual Studio 2022 または VS Code | C# プロジェクトをコンパイルできる任意の IDE。 |
| Aspose.BarCode for .NET（NuGet パッケージ `Aspose.BarCode`） | Planet バーコードの描画に使用する `BarcodeGenerator` クラスを提供します。 |
| ディスク上のフォルダーへの書き込み権限 | PNG ファイルはこの場所に保存されます。 |

以下のコマンドで NuGet パッケージをインストールします：

```bash
dotnet add package Aspose.BarCode
```

## 手順 1: 新しいコンソールプロジェクトを作成

ターミナルを開き、次を実行します：

```bash
dotnet new console -n PlanetBarcodeDemo
cd PlanetBarcodeDemo
```

これにより **PlanetBarcodeDemo** という名前の最小限の C# コンソール アプリケーションが作成されます。

## 手順 2: 出力ディレクトリを定義

最初のコードは、生成された PNG ファイルの保存先を決定します。絶対パスでも相対パスでも構いませんが、フォルダーが存在することを確認するか、プログラムに作成させてください。

```csharp
using System;
using System.IO;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        // Step 2: Define the output directory
        string outputDir = Path.Combine(Directory.GetCurrentDirectory(), "Barcodes");
        Directory.CreateDirectory(outputDir); // Guarantees the folder exists
```

*この手順の目的*：出力をソースコードから分離することで、プロジェクトを整理し、誤って上書きするリスクを防ぎます。

## 手順 3: 塗りつぶしバーの Planet バーコードを生成

Planet バーコードは同心円（デフォルトで塗りつぶし）で構成されます。X ディメンション（各バーのピクセル幅）を設定し、画像を PNG として保存します。

```csharp
        // Step 3: Create a Planet barcode with the default (filled) bars
        BarcodeGenerator planetFilled = new BarcodeGenerator(EncodeTypes.Planet, "123456");
        planetFilled.Parameters.Barcode.XDimension.Pixels = 4; // Controls bar thickness

        // Save the filled‑bars barcode as PNG
        string filledPath = Path.Combine(outputDir, "PostalPlanetFilledBars.png");
        planetFilled.Save(filledPath, BarCodeImageFormat.Png);
        Console.WriteLine($"Filled‑bars barcode saved to: {filledPath}");
```

**解説**

* `EncodeTypes.Planet` は Aspose に Planet シンボロジーを使用するよう指示し、郵便サービスで一般的です。  
* `XDimension.Pixels = 4` は手動スケーリング不要の、はっきりした印刷可能サイズを実現します。  
* `Save` メソッドは PNG ファイルを書き出します。`BarCodeImageFormat` を変更すれば JPEG や BMP も選択可能です。

## 手順 4: 空バーの Planet バーコードを生成

背景がカラーの場合など、空（透明）バーのビジュアルが必要になることがあります。`FilledBars` を `false` に設定するとこのスタイルが生成されます。

```csharp
        // Step 4: Create a Planet barcode with empty bars
        BarcodeGenerator planetEmpty = new BarcodeGenerator(EncodeTypes.Planet, "123456");
        planetEmpty.Parameters.Barcode.XDimension.Pixels = 4;
        planetEmpty.Parameters.Barcode.FilledBars = false; // Switch to empty‑bars mode

        // Save the empty‑bars barcode as PNG
        string emptyPath = Path.Combine(outputDir, "PostalPlanetEmptyBars.png");
        planetEmpty.Save(emptyPath, BarCodeImageFormat.Png);
        Console.WriteLine($"Empty‑bars barcode saved to: {emptyPath}");
```

**解説**

* `FilledBars = false` にすると実体の円が無効化され、輪郭だけが残ります。  
* その他の設定（X ディメンション、データ文字列）は同一で、両画像が同じデータを表すことが保証されます。

## 手順 5: プログラムを実行し、出力を確認

コンパイルして実行します：

```bash
dotnet run
```

コンソールに保存完了のメッセージが表示され、`Barcodes` フォルダーには以下が作成されます：

* `PostalPlanetFilledBars.png` – 従来の塗りつぶしバーの Planet バーコード。  
* `PostalPlanetEmptyBars.png` – 空バーで同じデータを描画したもの。

任意の画像ビューアで PNG を開いてください。両画像は数値文字列 **123456** をエンコードしており、標準的な郵便バーコードリーダーで読み取れます。

## よくある質問とエッジケースの対処

### データ形式を変更したい場合は？

Planet バーコードは最大 12 桁の数値文字列を受け付けます。数値以外を渡すと Aspose は `ArgumentException` をスローします。ジェネレータ作成前に入力を検証してください：

```csharp
if (!Regex.IsMatch(data, @"^\d{1,12}$"))
    throw new ArgumentException("Planet barcode data must be numeric and up to 12 digits.");
```

### バーの太さは変えずに画像サイズだけ変更したい場合は？

`Resolution` プロパティを使用するか、保存後にビットマップをスケーリングしてください：

```csharp
planetFilled.Parameters.ImageResolution = 300; // DPI for high‑resolution print
```

### 他の画像形式も生成できる？

はい。`BarCodeImageFormat.Png` を `BarCodeImageFormat.Jpeg`、`Bmp`、`Gif` などに置き換えます。API は一般的なラスタ形式すべてをサポートしています。

### カラーカスタマイズは可能か？

`Barcode` パラメータの `BarColor` と `BackColor` を設定します：

```csharp
planetFilled.Parameters.Barcode.BarColor = Color.DarkBlue;
planetFilled.Parameters.Barcode.BackColor = Color.LightYellow;
```

これらのオプションは塗りつぶしバー版・空バー版の両方で機能します。

## 本番環境でのプロのコツ

* 同一設定で多数のバーコードを描画する場合は **ジェネレータをキャッシュ** してください。オブジェクトを毎回初期化するとオーバーヘッドが増えます。  
* ループ内で多数作成する場合は **Dispose** して `BarcodeGenerator` オブジェクトを解放しましょう（`IDisposable` を実装）。  
* 書き込み保護されたディレクトリで例外が発生しないよう、**出力フォルダーを早期に検証** してください。  

## 結論

これで C# で **プラネットバーコード PNG** を作成する方法と、塗りつぶしバーと空バーの両スタイルで画像を生成する手順が分かりました。完全な実行可能サンプルは、出力ディレクトリの設定、`BarcodeGenerator` の構成、PNG への保存を示しています。

次に試すこと：

* バーコード下に **人間可読テキスト** を追加（`planetFilled.Parameters.Caption.Visible = true`）。  
* Aspose.PDF を使用して生成した PNG を **PDF 請求書** に組み込む。  
* **IMB** や **ITF** など他の郵便シンボロジーに切り替える（`EncodeTypes.IMB`、`EncodeTypes.ITF`）。  

バーの太さ、色、画像解像度を自由に調整し、アプリケーション要件に合わせてください。コーディングを楽しんでください！

## 次に学ぶべきこと

以下のチュートリアルは、本ガイドで示したテクニックを基にした関連トピックを扱っています。各リソースには、ステップバイステップの解説と完全なコード例が含まれており、API の追加機能を習得したり、独自プロジェクトで代替実装を検討したりするのに役立ちます。

- [Create Planet Barcode Image in C# – How to Generate Postal Barcode](/barcode/english/python-java/general/create-planet-barcode-image-in-c-how-to-generate-postal-barc/)
- [Create Planet Barcode in C# – Full Step‑by‑Step Guide](/barcode/english/python-java/general/create-planet-barcode-in-c-full-step-by-step-guide/)
- [Generate PNG Barcode with Aspose.BarCode for .NET: One-Dimensional Filled Bars](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-filled-bars-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}