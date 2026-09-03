---
date: 2026-05-24
description: Aspose.BarCode for .NETを使用して、開始および停止文字付きのCodabarバーコードを作成する方法を学びます。開発者向けのステップバイステップのバーコード生成チュートリアルです。
keywords:
- create codabar barcode
- codabar start stop characters
- aspose barcode example
- barcode generation .net core
linktitle: Codabar 開始/停止文字
schemas:
- author: Aspose
  dateModified: '2026-05-24'
  description: Learn how to create codabar barcode with start and stop characters
    using Aspose.BarCode for .NET. Step‑by‑step barcode generation tutorial for developers.
  headline: Create Codabar Barcode with Start/Stop Characters in Aspose.BarCode for
    .NET
  type: TechArticle
- description: Learn how to create codabar barcode with start and stop characters
    using Aspose.BarCode for .NET. Step‑by‑step barcode generation tutorial for developers.
  name: Create Codabar Barcode with Start/Stop Characters in Aspose.BarCode for .NET
  steps:
  - name: Initialize the Barcode Generator
    text: '`BarcodeGenerator` is the core class that creates barcode images. It takes
      the symbology type and the data string as constructor arguments. > **Pro tip:**
      The dash (`-`) is one of the valid start/stop symbols for Codabar. You can also
      use `A`, `B`, `C`, or `D` depending on your application’s require'
  - name: Set the X‑Dimension (barcode element width)
    text: '`XDimension` controls the width of the narrowest bar. Larger values improve
      readability on low‑resolution printers, while smaller values conserve space
      on high‑density labels. > **Why it matters:** Adjusting `XDimension` helps you
      meet scanner specifications that often require a minimum bar width of'
  - name: Define Start and Stop Characters
    text: Codabar supports four start/stop symbols (A, B, C, D). Below are examples
      for each option. Choose the one that matches the specification of the system
      you’re integrating with.
  - name: Save the Generated Barcode Images (PNG)
    text: '`Save` writes the barcode to a file. Using `BarCodeImageFormat.Png` produces
      lossless PNG images that are ideal for web and print use cases. Each file now
      contains a **codabar barcode example** with the corresponding start/stop symbols.'
  type: HowTo
- questions:
  - answer: Aspose.BarCode for .NET
    question: What library do I need?
  - answer: PNG (`BarCodeImageFormat.Png`)
    question: Which format can I save the barcode in?
  - answer: A free trial works for testing; a commercial license is required for production.
    question: Do I need a license for development?
  - answer: Yes – use `CodabarSymbol.A`, `B`, `C`, or `D`.
    question: Can I change the start/stop symbols?
  - answer: .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.
    question: What .NET versions are supported?
  type: FAQPage
second_title: Aspose.BarCode .NET API
title: Aspose.BarCode for .NETで開始/停止文字付きCodabarバーコードを作成する
url: /ja/net/codabar-encoding-and-checksum/codabar-start-stop-characters/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.BarCode for .NET で開始/停止文字付き Codabar バーコードを作成する

## はじめに

このチュートリアルでは、Aspose.BarCode for .NET を使用して **Codabar バーコード** 画像を作成し、開始/停止文字を明示的に含めます。小売在庫システム、ラボサンプルトラッカー、医療記録ソリューションなど、Codabar の数値シンボロジーは境界シンボルに依存して信頼性の高いスキャンを保証します。数分で環境設定から PNG ファイルの保存までをカバーし、すぐに Codabar バーコードの生成を開始できるようにします。

## クイック回答
- **必要なライブラリは何ですか？** Aspose.BarCode for .NET  
- **どの形式でバーコードを保存できますか？** PNG (`BarCodeImageFormat.Png`)  
- **開発にライセンスは必要ですか？** テスト用の無料トライアルで動作しますが、商用利用にはライセンスが必要です。  
- **開始/停止シンボルは変更できますか？** はい – `CodabarSymbol.A`, `B`, `C`, または `D` を使用します。  
- **サポートされている .NET バージョンは？** .NET Framework 4.5+、.NET Core 3.1+、.NET 5/6/7。

## Codabar とは何か、開始/停止文字が重要な理由

Codabar は図書館、医療、在庫管理で広く使用される数値バーコードシンボロジーです。開始文字と停止文字（A‑D またはハイフン）はバーコードの境界を定義し、スキャナーがデータの開始と終了を 99.9 % の読み取り精度で検出できるようにします。

## なぜ Aspose.BarCode for .NET を使用するのか

Aspose.BarCode は **30 以上のバーコードシンボロジー** をサポートし、**10,000 × 10,000 px** までの画像をメモリ全体をロードせずに生成できます。Windows、Linux、macOS 上で動作し、.NET Framework、.NET Core、.NET 5+ と互換性があるため、すべての最新プラットフォームで柔軟に利用できます。

## 前提条件

1. **環境設定** – 動作する .NET 開発環境を確保してください。ガイダンスが必要な場合は、[documentation](https://reference.aspose.com/barcode/net/) を参照してください。  
2. **Aspose.BarCode for .NET ライブラリ** – 公式 [source](https://releases.aspose.com/barcode/net/) からダウンロードしてインストールしてください。  
3. **基本的な .NET 知識** – C# と Visual Studio、Rider、または VS Code などの IDE に慣れていること。  
4. **IDE** – Visual Studio、Rider、または Visual Studio Code のいずれでも構いません。

前提条件の説明が終わったので、実際のコードに入りましょう。

## 開始/停止文字付き Codabar バーコードはどのように生成しますか？

`BarcodeGenerator` をロードし、エンコーディングタイプを **Codabar** に設定し、必要な開始/停止シンボルをすでに含むデータ文字列（例: “-12345-”）を渡します。次に X‑Dimension を構成し、必要に応じて別の開始/停止シンボルを選択し、最後に PNG として画像を保存します。このエンドツーエンドのフローにより、数行の C# で使用可能なバーコードがすぐに作成できます。

### 名前空間のインポート

`BarcodeGenerator` と関連型は `Aspose.BarCode.Generation` 名前空間にあります。

```csharp
using Aspose.BarCode.Generation;
```

### ステップ 1: Barcode Generator の初期化

`BarcodeGenerator` はバーコード画像を作成するコアクラスです。シンボロジータイプとデータ文字列をコンストラクタ引数として受け取ります。

```csharp
string path = "Your Directory Path";
System.Console.WriteLine("CodabarStartStop:");

BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.Codabar, "-12345-");
```

> **プロのコツ:** ハイフン（`-`）は Codabar の有効な開始/停止シンボルの一つです。アプリケーションの要件に応じて `A`, `B`, `C`, `D` も使用できます。

### ステップ 2: X‑Dimension の設定（バーコード要素の幅）

`XDimension` は最も狭いバーの幅を制御します。値を大きくすると低解像度プリンターでの可読性が向上し、値を小さくすると高密度ラベルでのスペースが節約できます。

```csharp
gen.Parameters.Barcode.XDimension.Pixels = 2;
```

> **重要性:** `XDimension` を調整することで、しばしば最小バー幅 0.25 mm が求められるスキャナー仕様を満たすことができます。

### ステップ 3: 開始文字と停止文字の定義

Codabar は 4 つの開始/停止シンボル（A, B, C, D）をサポートします。以下に各オプションの例を示します。統合するシステムの仕様に合うものを選択してください。

#### 開始 A と停止 A の設定

```csharp
gen.Parameters.Barcode.Codabar.CodabarStartSymbol = CodabarSymbol.A;
gen.Parameters.Barcode.Codabar.CodabarStopSymbol = CodabarSymbol.A;
```

#### 開始 B と停止 B の設定

```csharp
gen.Parameters.Barcode.Codabar.CodabarStartSymbol = CodabarSymbol.B;
gen.Parameters.Barcode.Codabar.CodabarStopSymbol = CodabarSymbol.B;
```

#### 開始 C と停止 C の設定

```csharp
gen.Parameters.Barcode.Codabar.CodabarStartSymbol = CodabarSymbol.C;
gen.Parameters.Barcode.Codabar.CodabarStopSymbol = CodabarSymbol.C;
```

#### 開始 D と停止 D の設定

```csharp
gen.Parameters.Barcode.Codabar.CodabarStartSymbol = CodabarSymbol.D;
gen.Parameters.Barcode.Codabar.CodabarStopSymbol = CodabarSymbol.D;
```

必要なシンボルごとに構成を繰り返すことができます。以下の例は、4 つの開始/停止ペアそれぞれに対して別々の画像を保存します。

### ステップ 4: 生成されたバーコード画像の保存（PNG）

`Save` はバーコードをファイルに書き込みます。`BarCodeImageFormat.Png` を使用すると、ウェブや印刷で理想的なロスレス PNG 画像が生成されます。

```csharp
gen.Save($"{path}CodabarStartAStopA.png", BarCodeImageFormat.Png);
gen.Save($"{path}CodabarStartBStopB.png", BarCodeImageFormat.Png);
gen.Save($"{path}CodabarStartCStopC.png", BarCodeImageFormat.Png);
gen.Save($"{path}CodabarStartDStopD.png", BarCodeImageFormat.Png);
```

各ファイルには対応する開始/停止シンボルを持つ **Codabar バーコードの例** が含まれます。

## 一般的な問題とトラブルシューティング

| 症状 | 考えられる原因 | 対処法 |
|------|----------------|--------|
| バーコードが歪んで見える | X‑Dimension が選択したプリンター解像度に対して低すぎる | `XDimension.Pixels` を増やす（例: 3 または 4） |
| スキャナーが開始/停止文字を読めない | 対象システムに合わない開始/停止シンボルを使用している | 必要なシンボル（A‑D）を確認し、正しく設定する |
| PNG ファイルが空または破損している | 出力パスが無効、または書き込み権限が不足している | `path` が既存フォルダーを指しているか、アプリに書き込み権限があるか確認する |

## よくある質問

**Q1: Codabar とは何か、開始/停止文字が重要な理由は？**  
A: Codabar は在庫、図書館、医療で使用される数値バーコードシンボロジーです。開始/停止文字はバーコードの境界を定義し、スキャナーがデータの開始と終了を正確に認識できるようにします。

**Q2: Aspose.BarCode for .NET で Codabar バーコードの外観をカスタマイズできますか？**  
A: はい。X‑Dimension 以外にも色の変更、余白の追加、PDF や SVG へのエクスポートなど、同じ API で行えます。

**Q3: Codabar バーコードのデータエンコードに制限はありますか？**  
A: Codabar は主に数値データ（0‑9）と限られた特殊文字をサポートします。完全な英数字文字列には適していません。

**Q4: Aspose.BarCode for .NET は商用利用に適していますか？ライセンスはどこで取得できますか？**  
A: はい、商用利用に対応しています。ライセンスは [Aspose の購入ページ](https://purchase.aspose.com/buy) から入手してください。

**Q5: Aspose.BarCode for .NET に関するサポートや議論はどこで行えますか？**  
A: [Aspose.BarCode for .NET サポートフォーラム](https://forum.aspose.com/c/barcode/13) に参加すると、Aspose エンジニアや他の開発者から支援を受けられます。

---

**最終更新日:** 2026-05-24  
**テスト環境:** Aspose.BarCode 24.11 for .NET  
**作者:** Aspose

## 関連チュートリアル

- [Codabar Start Stop Characters and Checksum](/barcode/net/codabar-encoding-and-checksum/)
- [How to Add Checksum to Codabar Barcodes Using Aspose.BarCode for .NET](/barcode/net/codabar-encoding-and-checksum/codabar-checksum-calculation/)
- [Comprehensive Tutorials and Examples of Aspose.BarCode for .NET](/barcode/net/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< blocks/products/products-backtop-button >}}

{{< /blocks/products/pf/main-wrap-class >}}