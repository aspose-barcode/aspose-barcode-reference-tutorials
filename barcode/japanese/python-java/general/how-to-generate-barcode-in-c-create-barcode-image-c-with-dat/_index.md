---
category: general
date: 2026-08-22
description: Aspose.BarCode を使用して C# でバーコードを生成する方法。C# でバーコード画像をステップバイステップで作成し、2‑D
  コンポーネントを無効にして PNG ファイルとして保存する方法を学びます。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to generate barcode
- create barcode image c#
language: ja
lastmod: 2026-08-22
og_description: Aspose.BarCode を使用して C# でバーコードを生成する方法。このチュートリアルでは、DataBar Expanded
  を使用して C# でバーコード画像を作成し、2‑D コンポーネントを切り替えて PNG ファイルとして保存する方法を示します。
og_image_alt: C# code screenshot generating a DataBar Expanded barcode image without
  the 2‑D component
og_title: C#でバーコードを生成する方法 – バーコード画像作成の完全ガイド
schemas:
- author: Aspose
  dateModified: '2026-08-22'
  description: How to generate barcode in C# using Aspose.BarCode. Learn to create
    barcode image c# step‑by‑step, disable the 2‑D component, and save PNG files.
  headline: How to generate barcode in C# – create barcode image c# with DataBar Expanded
  type: TechArticle
tags:
- barcode
- C#
- Aspose.BarCode
- image generation
title: C#でバーコードを生成する方法 – DataBar Expandedでバーコード画像を作成する
url: /ja/python-java/general/how-to-generate-barcode-in-c-create-barcode-image-c-with-dat/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# C#でバーコードを生成する方法 – DataBar Expandedでバーコード画像を作成する

C#でバーコードを生成することは、アプリケーションに機械可読データを埋め込む必要がある場合に頻繁に求められる要件です。このガイドでは、Aspose.BarCode ライブラリを使用して barcode image c# を作成し、2‑D コンポジットコンポーネントを無効にして、結果を PNG ファイルとして保存する方法を示します。

完全に実行可能なプログラム、すべての設定オプションの説明、出力をカスタマイズするためのヒントをご覧いただけます。外部ドキュメントは不要です—以下のコードと .NET 開発環境だけで完了します。

## 前提条件

開始する前に、以下が揃っていることを確認してください。

* .NET 6.0 SDK 以降がインストールされていること  
* Visual Studio 2022（または .NET をサポートする任意の IDE）  
* Aspose.BarCode for .NET NuGet パッケージ（`Aspose.BarCode`）  

以下のコマンドでパッケージを追加できます:

```bash
dotnet add package Aspose.BarCode
```

このライブラリは、本チュートリアル全体で使用する `BarcodeGenerator` クラスを提供します。

## 手順 1: プロジェクトを設定し名前空間をインポートする

新しいコンソール アプリケーションを作成し、必要な名前空間をインポートします:

```csharp
using System;
using Aspose.BarCode.Generation;

namespace BarcodeDemo
{
    internal class Program
    {
        private static void Main()
        {
            // The rest of the code lives here
        }
    }
}
```

`Aspose.BarCode.Generation` 名前空間には、バーコードの設定とレンダリングに必要なすべてのクラスが含まれています。

## 手順 2: DataBar Expanded バーコードジェネレータを初期化する

最初の実装行は、**DataBar Expanded** シンボロジー用の `BarcodeGenerator` を作成し、生データ文字列を供給します。データ文字列は GS1 アプリケーション識別子形式 `(01)12345678901231` に従います。

```csharp
// Step 2: Create a DataBar Expanded barcode generator with the desired data
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarExpanded, "(01)12345678901231");
```

ジェネレータを作成すると内部のビットマップ キャンバスが確保されるため、レンダリング前にサイズや外観を調整できます。

## 手順 3: モジュール幅 (X‑dimension) を定義する

X‑dimension は最小バーコード要素の幅を制御します。ピクセル単位で設定すると、最終画像サイズを正確にコントロールできます。

```csharp
// Step 3: Set the X‑dimension (module width) in pixels
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

`2` ピクセルの値は画面表示に適しています。高解像度印刷の場合は増やしてください。

## 手順 4: 2‑D コンポジットコンポーネントを無効にする

DataBar Expanded は、追加情報を保持する 2‑D コンポーネントをオプションで含めることができます。このコンポーネントなしでバーコードを生成するには、フラグを `false` に設定します。

```csharp
// Step 4: Disable the 2‑D composite component of the DataBar barcode
barcodeGenerator.Parameters.Barcode.DataBar.Is2DCompositeComponent = false;
```

コンポーネントを無効にすると視覚的な複雑さが減り、PNG ファイルも小さくなります。

## 手順 5: 2‑D コンポーネントなしでバーコード画像を保存する

出力ディレクトリを選択し、画像をディスクに書き込みます。`BarCodeImageFormat.Png` 列挙体によりロスレス PNG ファイルが保証されます。

```csharp
// Step 5: Save the barcode image without the 2‑D component
string outputDir = "YOUR_DIRECTORY/"; // replace with your actual path
barcodeGenerator.Save($"{outputDir}Databar2DComponentDisabled.png", BarCodeImageFormat.Png);
```

この呼び出し後、`Databar2DComponentDisabled.png` にはクリーンな DataBar Expanded バーコードが格納されます。

## 手順 6: 2‑D コンポジットコンポーネントを有効にする

追加データ層が必要な場合は、フラグを再度有効にします。同じジェネレータ インスタンスを再利用できるため、オブジェクトを二度作成する必要がありません。

```csharp
// Step 6: Enable the 2‑D composite component
barcodeGenerator.Parameters.Barcode.DataBar.Is2DCompositeComponent = true;
```

## 手順 7: 2‑D コンポーネント有効でバーコード画像を保存する

2‑D フラグだけを除いて、同じ設定で二番目の画像をレンダリングします。

```csharp
// Step 7: Save the barcode image with the 2‑D component enabled
barcodeGenerator.Save($"{outputDir}Databar2DComponentEnabled.png", BarCodeImageFormat.Png);
```

これで `Databar2DComponentEnabled.png` は追加の 2‑D パターンを含むバーコードを示します。

## 完全なソースコード

以下のスニペット全体を `Program.cs` にコピーし、プロジェクトを実行してください。指定したフォルダーに両方の PNG ファイルが作成されます。

```csharp
using System;
using Aspose.BarCode.Generation;

namespace BarcodeDemo
{
    internal class Program
    {
        private static void Main()
        {
            // Create a DataBar Expanded barcode generator with the desired data
            BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
                EncodeTypes.DatabarExpanded, "(01)12345678901231");

            // Set the X‑dimension (module width) in pixels
            barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;

            // Define the output directory (change to a valid path on your machine)
            string outputDir = "YOUR_DIRECTORY/";

            // ---------- First image: 2‑D component disabled ----------
            barcodeGenerator.Parameters.Barcode.DataBar.Is2DCompositeComponent = false;
            barcodeGenerator.Save($"{outputDir}Databar2DComponentDisabled.png",
                                 BarCodeImageFormat.Png);

            // ---------- Second image: 2‑D component enabled ----------
            barcodeGenerator.Parameters.Barcode.DataBar.Is2DCompositeComponent = true;
            barcodeGenerator.Save($"{outputDir}Databar2DComponentEnabled.png",
                                 BarCodeImageFormat.Png);

            Console.WriteLine("Barcode images generated successfully.");
        }
    }
}
```

### 期待される出力

プログラムを実行すると次が表示されます:

```
Barcode images generated successfully.
```

そして二つのファイルが作成されます:

* `Databar2DComponentDisabled.png` – 2‑D コンポーネントなしのバーコード  
* `Databar2DComponentEnabled.png` – 2‑D コンポーネントありのバーコード  

任意の画像ビューアで PNG を開き、視覚的な違いを確認してください。

## 一般的なバリエーションとエッジケース

| 状況 | 調整 |
|-----------|------------|
| **異なるシンボロジー** | `EncodeTypes.DatabarExpanded` を別の値（例: `EncodeTypes.Code128`）に置き換えます。 |
| **高解像度** | `XDimension.Pixels` を 4 または 5 に増やすか、`barcodeGenerator.Parameters.Image` の `Resolution` を設定します。 |
| **その他の画像形式** | `BarCodeImageFormat.Jpeg`、`BarCodeImageFormat.Bmp`、または `BarCodeImageFormat.Svg` を使用します。 |
| **Web アプリでの実行** | 画像バイトをディスクに保存せず、直接 HTTP 応答にストリームします。 |
| **メモリ管理** | .NET Framework を対象とする場合、アンマネージドリソースが解放されるように `using` ブロックでジェネレータをラップします。 |

## プロのコツ

* **ジェネレータを再利用** – 2‑D フラグだけを変更することでオブジェクトの再生成を避け、CPU サイクルを節約します。  
* **データの検証** – GS1 データは正確な長さとチェックサム規則に従う必要があり、無効な入力は `ArgumentException` をスローします。  
* **バッチ処理** – データ文字列のコレクションをループし、必要に応じて 2‑D フラグを切り替え、各画像をユニークなファイル名で保存します。  

## 結論

これで C# でバーコードを生成し、2‑D コンポジットコンポーネントを完全に制御しながら barcode image c# を作成する方法が分かりました。例ではジェネレータの初期化、X‑dimension の設定、コンポーネントの切り替え、PNG ファイルの保存を示しました。ここからは他のシンボロジーを試したり、画像を PDF に埋め込んだり、ASP.NET Core サービスにバーコード生成を統合したりできます。

--- 

*次のステップ*: QR コードの生成を試したり、異なる画像解像度で実験したり、生成した PNG を Aspose.PDF を使って PDF に埋め込んだりしてください。これらの拡張は同じ `BarcodeGenerator` API 上に構築され、ワークフローの一貫性を保ちます。

## 次に学ぶべきことは？

以下のチュートリアルは、本ガイドで示した手法を基にした密接に関連するトピックをカバーしています。各リソースには、完全な動作コード例とステップバイステップの解説が含まれており、追加の API 機能を習得し、独自プロジェクトで代替実装アプローチを探求するのに役立ちます。

- [.NET 用 Aspose.BarCode で DataMatrix バーコードを生成する方法 – ステップバイステップガイド](/barcode/english/net/datamatrix-barcode-configuration/)
- [.NET 用 Aspose.BarCode で 1 次元 Databar のバーコード高さを生成・調整する方法](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-barcode-height-adjustment/)
- [.NET 用 Aspose.BarCode でカスタムアスペクト比の Aztec バーコードを生成する方法](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}