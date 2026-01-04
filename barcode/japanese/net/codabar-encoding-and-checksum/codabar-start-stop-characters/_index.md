---
date: 2026-01-04
description: Aspose.BarCode for .NET を使用して、開始文字と停止文字を含む Codabar バーコードの生成方法を学びましょう。開発者向けのステップバイステップのバーコード生成チュートリアルです。
linktitle: Codabar Start/Stop Characters
second_title: Aspose.BarCode .NET API
title: Aspose.BarCode for .NET で開始/停止文字付き Codabar バーコードを生成する
url: /ja/net/codabar-encoding-and-checksum/codabar-start-stop-characters/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.BarCode for .NET で開始/停止文字付き Codabar バーコードを生成する

## はじめに

この包括的なガイドへようこそ。Aspose.BarCode for .NET を使用して **Codabar バーコード** 画像を開始/停止文字付きで生成する方法をご紹介します。小売在庫システム、ラボサンプルトラッカー、医療記録ソリューションなど、Codabar は正確なスキャンのために明示的な開始・停止シンボルが必要な信頼性の高い数値シンボロジーです。数分で前提条件から最終 PNG ファイルの保存まで、必要なすべてを解説しますので、すぐに Codabar バーコードの作成を開始できます。

## クイック回答
- **必要なライブラリは何ですか？** Aspose.BarCode for .NET  
- **バーコードはどの形式で保存できますか？** PNG (BarCodeImageFormat.Png)  
- **開発にライセンスは必要ですか？** テストには無料トライアルで動作しますが、製品版には商用ライセンスが必要です。  
- **開始/停止シンボルを変更できますか？** はい – CodabarSymbol.A、B、C、または D を使用します。  
- **サポートされている .NET バージョンは何ですか？** .NET Framework 4.5 以上、.NET Core 3.1 以上、.NET 5/6/7。

## 前提条件

開始する前に、このチュートリアルを進めるために必要なものがすべて揃っていることを確認しましょう。

1. **環境設定** – マシンに動作する .NET 開発環境があることを確認してください。ガイダンスが必要な場合は、[ドキュメント](https://reference.aspose.com/barcode/net/) を参照してください。  
2. **Aspose.BarCode for .NET ライブラリ** – 公式の [ソース](https://releases.aspose.com/barcode/net/) からダウンロードしてインストールします。  
3. **基本的な .NET 知識** – C# と Visual Studio（または好みの IDE）に慣れていると手順がスムーズです。  
4. **IDE** – Visual Studio、Rider、または Visual Studio Code のいずれでも構いません。

前提条件の説明が終わったので、実際のコードに入りましょう。

## 名前空間のインポート

Aspose.BarCode for .NET を使い始めるには、必要な名前空間をインポートしてください。

```csharp
using Aspose.BarCode.Generation;
```

## Codabar バーコード生成手順 – ステップバイステップガイド

### ステップ 1: バーコードジェネレータの初期化

`BarcodeGenerator` インスタンスを作成し、エンコーディングタイプとして **Codabar** を指定し、開始/停止文字をすでに含んだデータ文字列（例: “-12345-”）を提供します。

```csharp
string path = "Your Directory Path";
System.Console.WriteLine("CodabarStartStop:");

BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.Codabar, "-12345-");
```

> **Pro tip:** ダッシュ (`-`) は Codabar の有効な開始/停止シンボルの一つです。アプリケーションの要件に応じて A、B、C、または D も使用できます。

### ステップ 2: X‑Dimension の設定（バーコード要素の幅）

X‑Dimension は最も細いバーの幅を制御します。スキャン環境に合わせて調整してください。

```csharp
gen.Parameters.Barcode.XDimension.Pixels = 2;
```

> **Why it matters:** 大きな X‑Dimension は低解像度プリンターでの可読性を向上させ、逆に小さな値は高密度ラベルでのスペース節約につながります。

### ステップ 3: 開始・停止文字の定義

Codabar は 4 つの開始/停止シンボル (A, B, C, D) をサポートします。以下に各オプションの例を示します。統合するシステムの仕様に合うものを選んでください。

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

必要なシンボルごとに設定を繰り返すことができます。以下の例では、4 つの開始/停止ペアそれぞれに対して別々の画像を保存しています。

### ステップ 4: 生成したバーコード画像の保存 (PNG)

最後に、バーコードを PNG ファイルとして書き出します。これにより **save barcode png** のユースケースが示され、テスト用のすぐに使えるアセットが手に入ります。

```csharp
gen.Save($"{path}CodabarStartAStopA.png", BarCodeImageFormat.Png);
gen.Save($"{path}CodabarStartBStopB.png", BarCodeImageFormat.Png);
gen.Save($"{path}CodabarStartCStopC.png", BarCodeImageFormat.Png);
gen.Save($"{path}CodabarStartDStopD.png", BarCodeImageFormat.Png);
```

各ファイルには対応する開始/停止シンボルを持つ **codabar barcode example** が含まれています。

## よくある問題とトラブルシューティング

| 症状 | 考えられる原因 | 対策 |
|------|----------------|------|
| バーコードが歪んで見える | 選択したプリンター解像度に対して X‑Dimension が低すぎる | `XDimension.Pixels` を増やす（例: 3 または 4 に） |
| スキャナーが開始/停止文字を読み取れない | 対象システムに対して誤った開始/停止シンボルを使用している | 必要なシンボル (A‑D) を確認し、適切に設定する |
| PNG ファイルが空または破損している | 出力パスが無効、または書き込み権限が不足している | `path` が既存のフォルダーを指し、アプリに書き込み権限があることを確認する |

## よくある質問

### Q1: Codabar とは何ですか、そして開始・停止文字が重要な理由は？

**A1:** Codabar は在庫管理、図書館、医療分野で広く使用されている数値バーコードシンボロジーです。開始・停止文字はバーコードの境界を定義し、スキャナーがデータの開始位置と終了位置を正しく認識できるようにします。

### Q2: Aspose.BarCode for .NET で Codabar バーコードの外観をカスタマイズできますか？

**A2:** はい。X‑Dimension に加えて、色の変更、余白の追加、さらには同じ API を使用して PDF や SVG 形式に埋め込むことも可能です。

### Q3: データエンコードに関して Codabar バーコードに制限はありますか？

**A3:** Codabar は主に数値データ (0‑9) といくつかの特殊文字をサポートします。フルアルファベット文字列には適していません。

### Q4: Aspose.BarCode for .NET は商用利用に適していますか、ライセンスはどう取得すればよいですか？

**A4:** はい、製品版として使用可能です。ライセンスは [Aspose の購入ページ](https://purchase.aspose.com/buy) から購入してください。

### Q5: Aspose.BarCode for .NET に関するサポートや議論はどこでできますか？

**A5:** [Aspose.BarCode for .NET サポートフォーラム](https://forum.aspose.com/c/barcode/13) に参加すれば、Aspose エンジニアや他の開発者から支援を受けられます。

**最終更新日:** 2026-01-04  
**テスト環境:** Aspose.BarCode 24.11 for .NET  
**作者:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}