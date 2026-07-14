---
date: 2026-02-25
description: Aspose.BarCode for .NET を使用してバーコード画像を生成する方法を学びましょう。このステップバイステップガイドでは、チェックサムあり・なしの
  Code 39 バーコードの生成方法を示します。
linktitle: One-Dimensional Code 39 Configuration
second_title: Aspose.BarCode .NET API
title: バーコードの生成方法 – Aspose.BarCode を使用した Code 39 の設定
url: /ja/net/one-dimensional-barcode-types/one-dimensional-code-39-configuration/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 一次元 Code 39 設定

## はじめに

このチュートリアルでは、Aspose.BarCode for .NET を使用して **バーコードを生成する方法** を学びます。具体的には一次元 Code 39 バーコードの画像を生成します。バーコードは在庫管理から迅速かつ正確なデータ取得まで、現代のビジネスにおいて重要な役割を果たします。Aspose.BarCode for .NET は、.NET アプリケーションでのバーコード生成とカスタマイズを簡素化する強力なライブラリです。このステップバイステップガイドはプロセスを分かりやすい部分に分割し、バーコード生成が初めての開発者でもスムーズに進められるようにしています。

## クイック回答
- **主要なライブラリは何ですか？** Aspose.BarCode for .NET  
- **チェックサム付きのバーコードを作成できますか？** はい – `IsChecksumEnabled = EnableChecksum.Yes` を設定します  
- **チェックサムは必須ですか？** いいえ – 無効にすればチェックサムなしでバーコードを生成できます  
- **例で使用されている画像形式は何ですか？** PNG (`BarCodeImageFormat.Png`)  
- **開発にライセンスは必要ですか？** 評価用の一時ライセンスが利用可能です  

## Aspose.BarCode を使用したバーコード生成とは？
バーコード生成とは、テキストや数値データを機械が読み取れる視覚パターンに変換するプロセスです。Aspose.BarCode for .NET は Code 39 を含む多数のシンボロジーをサポートし、サイズや色からチェックサム計算まであらゆる要素を制御できます。

## Code 39 とチェックサムオプションを使用する理由
Code 39 は物流や製造業で広く採用されており、特殊文字を使用せずに英数字データをエンコードできます。チェックサムを追加（または省略）することで、エラー検出とシンプルさのバランスを取ることができ、在庫タグ、出荷ラベル、シンプルな POS システムに最適です。

## 前提条件

作業を始める前に、以下を用意してください。

1. **.NET 開発環境** – .NET フレームワークの基本的な知識と Visual Studio などの IDE が必要です。.NET が初めての場合は、公式ドキュメントから始めましょう: [Microsoft .NET Documentation](https://docs.microsoft.com/en-us/dotnet/)。  
2. **Aspose.BarCode for .NET** – ライブラリをダウンロードしてインストールします。ドキュメントとダウンロードは以下から入手できます: [Aspose.BarCode for .NET Documentation](https://reference.aspose.com/barcode/net/) と [Download Aspose.BarCode for .NET](https://releases.aspose.com/barcode/net/)。

前提条件の確認ができたら、一次元 Code 39 バーコード作成の主要手順に進みましょう。

## バーコード生成の開始: 名前空間のインポート
Aspose.BarCode for .NET を使用するには、プロジェクトに必要な名前空間をインポートします。以下の `using` 文を追加すると、バーコード生成クラスにアクセスできるようになります。

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;
```

## Code 39 バーコードの生成方法（チェックサムあり・なし）

以下では、**チェックサムなし** と **チェックサムあり** の 2 つのバーコードを作成します。コードは `IsChecksumEnabled` フラグだけが異なります。

```csharp
// The path to the documents directory.
string path = "Your Directory Path";
System.Console.WriteLine("OneCSCode39:");

BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.Code39Extended, "CODE");

// Example 1: Create a Code 39 barcode without checksum
gen.Parameters.Barcode.IsChecksumEnabled = EnableChecksum.No;
gen.Save($"{path}OneCSCode39WithoutChecksum.png", BarCodeImageFormat.Png);

// Example 2: Create a Code 39 barcode with checksum
gen.Parameters.Barcode.IsChecksumEnabled = EnableChecksum.Yes;
gen.Save($"{path}OneCSCode39WithChecksum.png", BarCodeImageFormat.Png);
```

**コードの内容**

1. **Instantiate** `BarcodeGenerator` に `EncodeTypes.Code39Extended` とデータ文字列 `"CODE"` を指定してインスタンス化します。  
2. **Toggle** `IsChecksumEnabled` でチェックサム桁を付加するかどうかを制御します。  
3. **Save** 各バーコードを PNG ファイルとして指定フォルダーに保存します。

これで、`OneCSCode39WithoutChecksum.png` と `OneCSCode39WithChecksum.png` の 2 つの使用可能なバーコード画像が作成されました。

## よくある問題と解決策
| 問題 | 発生原因 | 対策 |
|------|----------|------|
| **File path not found** | `path` 変数が存在しないフォルダーを指しています。 | ディレクトリが存在することを確認するか、`Directory.CreateDirectory(path)` を使用してください。 |
| **Invalid characters in data** | Code 39 は英数字と一部の特殊記号しかサポートしていません。 | 上記のように拡張 Code 39 (`Code39Extended`) を使用すれば、全 ASCII 文字セットを扱えます。 |
| **Checksum error** | 必要なときに `IsChecksumEnabled` を設定し忘れています。 | シナリオに応じてフラグを `EnableChecksum.Yes` または `No` に明示的に設定してください。 |

## Frequently Asked Questions (FAQs):

### Q: Can I use Aspose.BarCode for .NET with other programming languages?
A: Aspose.BarCode is primarily designed for .NET, but Aspose offers barcode libraries for other platforms as well.

### Q: Are there any licensing options available for Aspose.BarCode for .NET?
A: Yes, you can explore licensing options and request a temporary license on the Aspose website: [Aspose.BarCode Licensing](https://purchase.aspose.com/temporary-license/).

### Q: Is Aspose.BarCode for .NET suitable for web applications?
A: Yes, Aspose.BarCode for .NET can be used in web applications, making it suitable for a wide range of development projects.

### Q: Can I customize the appearance of the generated barcodes?
A: Absolutely, you can customize various aspects of the barcode, including size, colors, and fonts.

### Q: Where can I get support or ask questions about Aspose.BarCode for .NET?
A: You can find answers to your questions and seek support on the Aspose.BarCode forum: [Aspose.BarCode Forum](https://forum.aspose.com/c/barcode/13).

## 追加のよくある質問

**Q: チェックサム付きバーコードとなしバーコードの違いは何ですか？**  
A: チェックサムは転記エラーを検出するための余分な桁です。データの完全性が重要な場合に使用します。

**Q: 生成される PNG のサイズ上限はどれくらいですか？**  
A: サイズは `gen.Parameters.ImageWidth/Height` で制御します。`Save` を呼び出す前にこれらのプロパティを調整してください。

**Q: 他の画像形式でバーコードを生成できますか？**  
A: はい、Aspose.BarCode は JPEG、BMP、GIF、TIFF などをサポートしています。`BarCodeImageFormat` 列挙体を変更するだけです。

**Q: ディスクに書き込まずに Web アプリでバーコードを生成する方法はありますか？**  
A: `MemoryStream` に保存し、バイト配列を直接クライアントに返すことで実現できます。

## 結論
これらのシンプルな手順に従うだけで、.NET で **バーコードを生成** でき、チェックサムの有無、画像形式、ビジュアルスタイルをフルコントロールできます。在庫管理、注文処理、バーコード対応の Web ポータル構築など、さまざまなシナリオで Aspose.BarCode for .NET は信頼性の高い開発者フレンドリーなソリューションを提供します。

---

**Last Updated:** 2026-02-25  
**Tested With:** Aspose.BarCode 24.11 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}