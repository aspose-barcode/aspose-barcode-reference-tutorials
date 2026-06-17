---
date: 2026-02-22
description: .NETでAspose.BarCodeを使用してバーコードのカスタム高さを作成する方法を学び、一次元バーコードの高さを迅速かつ正確に調整します。
linktitle: Create Barcode Custom Height – One-Dimensional Barcodes
second_title: Aspose.BarCode .NET API
title: バーコードのカスタム高さを作成 – 一次元バーコード
url: /ja/net/one-dimensional-barcode-types/one-dimensional-barcode-height-adjustment/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# バーコードのカスタム高さの作成 – 1次元バーコード

.NET アプリケーションで **バーコードのカスタム高さを作成** する必要がある場合、Aspose.BarCode for .NET は 1 次元バーコードの外観を完全にコントロールできる機能を提供します。在庫ラベル、POS レシート、出荷タグなどを作成する際に、バーコードの高さを微調整できることで、最適なスキャン性能と洗練された外観を実現できます。このステップバイステップガイドでは、Aspose.BarCode for .NET を使用して 1 次元バーコードの高さを調整する方法をすべて解説します。

## Quick Answers
- **「バーコードのカスタム高さ」とは何ですか？** 1‑D バーコードシンボルのピクセル単位の垂直サイズです。  
- **高さを制御するプロパティはどれですか？** `Parameters.Barcode.BarHeight.Pixels`。  
- **1 回の実行で複数の高さを生成できますか？** はい、プロパティを変更して `Save()` を再度呼び出すだけです。  
- **サポートされている画像形式は？** PNG、JPEG、TIFF、BMP、GIF など。  
- **高さ調整にライセンスは必要ですか？** いいえ、無料トライアルでも機能します。製品版で使用する場合はライセンスが必要です。

## 「バーコードのカスタム高さを作成」とは？
カスタム高さのバーコードを作成するとは、バーコードのバーの垂直寸法に対して正確なピクセル値を指定することです。レイアウト要件が厳しい場合や、既存の印刷物に合わせる必要がある場合、または異なる媒体でスキャナの読み取りやすさを向上させたいときに便利です。

## なぜ Aspose.BarCode for .NET を使うのか？
- **リッチな API** – サイズ、色、テキストなどをシンプルなプロパティ設定で調整できます。  
- **クロスプラットフォーム** – .NET Framework、.NET Core、.NET 5/6+ で動作します。  
- **外部依存なし** – 追加のライブラリなしで画像を生成します。  
- **高品質レンダリング** – カスタム寸法でもスキャン可能なバーコードを保証します。

## 前提条件

開始する前に、以下の前提条件が整っていることを確認してください：

- .NET Framework または .NET Core がインストールされた開発環境。  
- Aspose.BarCode for .NET がインストールされていること。ダウンロードはウェブサイト [here](https://releases.aspose.com/barcode/net/) から。  
- お好みのコードエディタ。

前提条件が整ったので、1 次元バーコードの高さを調整する手順に進みましょう。

## 名前空間のインポート

まず、プロジェクトに必要な名前空間をインポートする必要があります。これらの名前空間は Aspose.BarCode for .NET を使用する際に必須です。以下のように記述します：

```csharp
using Aspose.BarCode.Generation;
```

## 手順 1: ディレクトリ パスの設定

生成したバーコード画像を保存したいディレクトリ パスを定義します。`"Your Directory Path"` を実際のパスに置き換えてください。

```csharp
string path = "Your Directory Path";
```

## 手順 2: バーコード ジェネレータの作成

次に、`BarcodeGenerator` クラスのインスタンスを作成します。バーコードタイプ（ここでは `Code128`）とバーコード値（例として `"ASPOSE"`）を指定できます。

```csharp
BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.Code128, "ASPOSE");
```

## 手順 3: バーコード高さの調整

この手順では、`BarHeight` プロパティを使用してバーコードの高さを設定します。例として高さを 40 ピクセルと 80 ピクセルに変更し、2 つのバーコード画像を保存します。これにより、**バーコードのカスタム高さ** を動的に作成するのがいかに簡単かが分かります。

```csharp
// Set BarHeight to 40 pixels
gen.Parameters.Barcode.BarHeight.Pixels = 40;
gen.Save($"{path}BarHeight40Code128.png", BarCodeImageFormat.Png);

// Set BarHeight to 80 pixels
gen.Parameters.Barcode.BarHeight.Pixels = 80;
gen.Save($"{path}BarHeight80Code128.png", BarCodeImageFormat.Png);
```

## よくある問題と解決策

| 問題 | 原因 | 対策 |
|------|------|------|
| 高さ変更後にバーコードが細すぎる | 幅が比例して調整されていない | 必要に応じて `Parameters.Barcode.XDimension` を使用してバー幅を変更してください。 |
| 画像が保存されない | パスが無効、または書き込み権限がない | `path` がバックスラッシュで終わっているか、フォルダーが存在するか確認してください。 |
| 生成されたバーコードがスキャンできない | スキャナーに対して高さが低すぎる／高すぎる | 一般的なスキャナーでテストし、ほとんどの1次元コードでは高さを30〜100ピクセルの範囲に保ってください。 |

## FAQ

**Q: Aspose.BarCode for .NET がサポートしているバーコードタイプは何ですか？**  
A: Aspose.BarCode for .NET は、Code128、QR Code、DataMatrix などを含む幅広いバーコードタイプをサポートしています。詳細な一覧はドキュメントで確認できます。

**Q: 1次元バーコードの幅も調整できますか？**  
A: はい、Aspose.BarCode for .NET を使用して1次元バーコードの幅も調整できます。手順は高さの調整と同様で、バーコードの寸法を完全にコントロールできます。

**Q: Aspose.BarCode for .NET の無料トライアルはありますか？**  
A: はい、無料トライアルで Aspose.BarCode for .NET を試すことができます。ダウンロードは [here](https://releases.aspose.com/) から行えます。

**Q: 異なる画像形式でバーコードを生成できますか？**  
A: はい、Aspose.BarCode for .NET は PNG、JPEG、TIFF など様々な画像形式をサポートしています。アプリケーションの要件に最適な形式を選択できます。

**Q: Aspose.BarCode for .NET の詳細なドキュメントはどこで見つけられますか？**  
A: Aspose.BarCode の .NET プロジェクトでの使用方法についての詳細は、ドキュメント [here](https://reference.aspose.com/barcode/net/) を参照してください。

## 結論

このチュートリアルでは、Aspose.BarCode for .NET を使用して 1 次元バーコードの **バーコードのカスタム高さ** を作成する手順を解説しました。`BarHeight` プロパティを調整することで、コンパクトなラベルから大きく視認性の高いコードまで、レイアウト要件に完全に合致したバーコード画像を生成できます。

課題が発生したり、追加の質問がある場合は、Aspose コミュニティの [support forum](https://forum.aspose.com/c/barcode/13) までお気軽にお問い合わせください。

---

**最終更新日:** 2026-02-22  
**テスト環境:** Aspose.BarCode 24.11 for .NET  
**作者:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}