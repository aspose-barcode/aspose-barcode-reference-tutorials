---
date: 2026-06-09
description: Aspose.BarCode for .NET を使用して ASCII モードで DataMatrix バーコードを作成する方法を学びます。このガイドでは、C#
  でバーコードを迅速に生成する方法を示します。
keywords:
- create datamatrix barcode
- generate barcode c#
- how to encode barcode
- barcode generator example
linktitle: DataMatrix エンコーディングモード (ASCII)
schemas:
- author: Aspose
  dateModified: '2026-06-09'
  description: Learn how to create DataMatrix barcode in ASCII mode using Aspose.BarCode
    for .NET. This guide shows how to generate barcode C# quickly.
  headline: Create DataMatrix barcode in ASCII mode with Aspose.BarCode for .NET
  type: TechArticle
- description: Learn how to create DataMatrix barcode in ASCII mode using Aspose.BarCode
    for .NET. This guide shows how to generate barcode C# quickly.
  name: Create DataMatrix barcode in ASCII mode with Aspose.BarCode for .NET
  steps:
  - name: '**Development Environment** – Visual Studio, Rider, or any C#‑compatible
      IDE.'
    text: '**Development Environment** – Visual Studio, Rider, or any C#‑compatible
      IDE.'
  - name: '**Aspose.BarCode for .NET** – Download the latest package from [here](https://releases.aspose.com/barcode/net/).'
    text: '**Aspose.BarCode for .NET** – Download the latest package from [here](https://releases.aspose.com/barcode/net/).'
  - name: '**Basic C# knowledge** – Familiarity with .NET project structure will help
      you follow the steps quickly.'
    text: '**Basic C# knowledge** – Familiarity with .NET project structure will help
      you follow the steps quickly.'
  - name: '**Other Aspose products** can be found [here](https://releases.aspose.com/).'
    text: '**Other Aspose products** can be found [here](https://releases.aspose.com/).'
  type: HowTo
- questions:
  - answer: Yes, a valid Aspose license is required for production use; a free trial
      is available for evaluation.
    question: Can I use this in a commercial application?
  - answer: Absolutely – Aspose.BarCode fully supports .NET Core 3.1+, .NET 5, .NET
      6, and later versions.
    question: Does the library work with .NET Core?
  - answer: Up to 2,335 alphanumeric characters fit in a single DataMatrix symbol
      when using ASCII encoding.
    question: How many characters can I encode in ASCII mode?
  - answer: Yes, adjust `generator.Parameters.Image.ForeColor` and `BackColor` to
      any `System.Drawing.Color` value.
    question: Can I change the barcode’s foreground or background color?
  - answer: The official documentation contains dozens of samples covering custom
      sizes, colors, and error‑correction levels.
    question: Where can I find more advanced examples?
  type: FAQPage
second_title: Aspose.BarCode .NET API
title: Aspose.BarCode for .NET を使用して ASCII モードで DataMatrix バーコードを作成する
url: /ja/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-ascii/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# .NET 用 Aspose.BarCode で ASCII モードの DataMatrix バーコードを作成する

## はじめに

効率的な ASCII エンコーディングを使用した **DataMatrix バーコードを作成** する準備はできましたか？このチュートリアルでは、Aspose.BarCode for .NET を使用して ASCII モードで DataMatrix バーコードを生成する方法を学びます。プロジェクトの設定から最終画像の保存まで、すべての手順を順に解説するので、数分で C# アプリケーションにバーコード生成機能を追加できます。

## クイック回答
- **.NET で DataMatrix に最適なライブラリは何ですか？** Aspose.BarCode for .NET  
- **必要なコード行数は？** 基本的な ASCII バーコードで約 5‑7 行  
- **ライセンスは必要ですか？** 開発には無料トライアルで動作しますが、本番環境ではライセンスが必要です  
- **サポートプラットフォームは？** .NET Framework 4.5+、.NET Core 3.1+、.NET 5/6/7  
- **サイズや色を変更できますか？** はい、Aspose.BarCode は寸法や前景/背景色のプロパティを提供しています  

## DataMatrix バーコードとは？

DataMatrix は、テキストとバイナリデータをコンパクトな正方形パターンに格納する二次元バーコードです。  
DataMatrix バーコードは、黒と白のモジュールのグリッドに情報をエンコードし、1 つのシンボルで最大 2,335 文字の英数字を格納できます。製造業、物流、医療分野で広く使用されており、非常に小さなサイズでも印刷でき、スキャン性が高いことが特徴です。

## ASCII モードで DataMatrix バーコードを作成する方法

Aspose.BarCode 名前空間をロードし、`BarcodeGenerator` のインスタンスを作成し、`EncodeMode` を **EncodeMode.ASCII** に設定し、データ文字列を割り当て、`Save` を呼び出して画像ファイルを書き出します。この方法により、数行の C# コードだけで ASCII のみのエンコーディングを使用した完全に準拠した DataMatrix バーコードが生成されます。

## DataMatrix で ASCII エンコーディングを使用する理由

ASCII モードはプレーンテキストデータに対するデフォルトかつ最も効率的なエンコーディングで、英数字文字列に対して最小のシンボルサイズを実現します。128 文字すべての ASCII をサポートし、拡張モードよりも高速にデータを処理し、標準 ASCII シンボルを期待するレガシースキャナーとの最大互換性を保証します。

## 前提条件

1. **開発環境** – Visual Studio、Rider、または任意の C# 対応 IDE。  
2. **Aspose.BarCode for .NET** – 最新パッケージを [here](https://releases.aspose.com/barcode/net/) からダウンロードしてください。  
   - ドキュメント: [Aspose.BarCode for .NET documentation](https://reference.aspose.com/barcode/net/)  
   - コミュニティサポート: [Aspose.BarCode forum](https://forum.aspose.com/c/barcode/13)  
3. **基本的な C# の知識** – .NET プロジェクト構成に慣れていると手順をすぐに追いやすくなります。  
4. **その他の Aspose 製品** は [here](https://releases.aspose.com/) で確認できます。

## 名前空間のインポート

まず、C# ファイルの先頭に必要な `using` ディレクティブを追加します:

```csharp
using Aspose.BarCode.Generation;
using System.Drawing;
```

これらの名前空間により、`BarcodeGenerator` クラスや出力保存に必要な画像関連の型にアクセスできるようになります。

## 手順 1: ディレクトリの作成

生成されたバーコード画像を保存するフォルダーを選択します。`"Your Directory Path"` を、マシン上に存在する絶対パスまたは相対パスに置き換えてください。

```csharp
string outputDir = @"C:\Barcodes";
if (!System.IO.Directory.Exists(outputDir))
{
    System.IO.Directory.CreateDirectory(outputDir);
}
```

このコードは、ファイルを書き込む前にディレクトリが存在することを確認し、実行時エラーを防止します。

## 手順 2: ASCII モードでデータをエンコード

`BarcodeGenerator` クラスはバーコード画像を作成・設定します。`DataMatrixEncodeMode` 列挙体は DataMatrix シンボルのエンコーディングアルゴリズムを選択します。

```csharp
// Initialise the generator with the data you want to encode
BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.DataMatrix, "1234567890");

// Set the encoding mode to ASCII for optimal size
generator.Parameters.Barcode.DataMatrixEncodeMode = DataMatrixEncodeMode.ASCII;

// Optional: adjust image dimensions or colors here
generator.Parameters.Image.Width = 200;
generator.Parameters.Image.Height = 200;

// Save the barcode as a PNG file
string filePath = System.IO.Path.Combine(outputDir, "datamatrix_ascii.png");
generator.Save(filePath, BarCodeImageFormat.Png);
```

コードを実行すると、指定したフォルダーに `datamatrix_ascii.png` が作成されます。この画像は、文字列 `"1234567890"` をコンパクトな ASCII モードでエンコードした DataMatrix バーコードを含んでいます。

## よくある問題と解決策

- **ファイルアクセスエラー** – アプリケーションが対象フォルダーに書き込み権限を持っていることを確認してください。Windows では Visual Studio を管理者として実行すると権限問題が解決することがあります。  
- **シンボルサイズが不正** – バーコードが大きすぎるまたは小さすぎる場合、`generator.Parameters.Image.Width` と `Height` を調整するか、これらのプロパティを省略して Aspose に最適サイズを自動計算させてください。  
- **サポート外の文字** – ASCII モードは 0‑127 の範囲の文字のみ受け付けます。Unicode データの場合は `DataMatrixEncodeMode.Base256` などの適切なモードに切り替えてください。

## よくある質問

**Q: 商用アプリケーションで使用できますか？**  
A: はい、本番環境で使用するには有効な Aspose ライセンスが必要です。評価用に無料トライアルが利用可能です。

**Q: ライブラリは .NET Core で動作しますか？**  
A: 完全にサポートしています – Aspose.BarCode は .NET Core 3.1+、.NET 5、.NET 6、以降のバージョンをフルサポートしています。

**Q: ASCII モードでエンコードできる文字数は？**  
A: ASCII エンコーディングを使用した場合、1 つの DataMatrix シンボルに最大 2,335 文字の英数字を格納できます。

**Q: バーコードの前景色や背景色を変更できますか？**  
A: はい、`generator.Parameters.Image.ForeColor` と `BackColor` を任意の `System.Drawing.Color` 値に設定してください。

**Q: より高度なサンプルはどこで見つけられますか？**  
A: 公式ドキュメントには、カスタムサイズ、色、エラー訂正レベルなどをカバーする多数のサンプルが掲載されています。

## FAQ

### Q1: C# 以外のプログラミング言語でも Aspose.BarCode for .NET を使用できますか？

A1: Aspose.BarCode は複数のプログラミング言語をサポートしていますが、このチュートリアルは C# に焦点を当てています。

### Q2: DataMatrix バーコードで利用可能なエンコーディングモードにはどのようなものがありますか？

A2: DataMatrix バーコードは ASCII、C40、Text、Base256 などのさまざまなエンコーディングモードをサポートしています。各モードは異なるデータタイプに適しています。

### Q3: 生成されたバーコードの外観（サイズや色など）をカスタマイズできますか？

A3: はい、Aspose.BarCode はサイズ、色など、バーコードの外観をカスタマイズするための豊富なパラメータを提供しています。

### Q4: Aspose.BarCode for .NET の無料トライアル版はありますか？

A4: はい、[here](https://releases.aspose.com/) から無料トライアルで Aspose.BarCode for .NET をお試しできます。

### Q5: Aspose.BarCode for .NET のライセンスはどこで購入できますか？

A5: Aspose のウェブサイトの [here](https://purchase.aspose.com/buy) からライセンスを購入できます。

---

**最終更新日:** 2026-06-09  
**テスト環境:** Aspose.BarCode 24.11 for .NET  
**作者:** Aspose

## 関連チュートリアル

- [Aspose.BarCode for .NET を使用したバイト単位の DataMatrix エンコーディング](/barcode/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-bytes/)
- [DataMatrix バーコードの読み取り C# – DataMatrix モード（自動）生成](/barcode/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-auto/)
- [Aspose.BarCode for .NET で DataMatrix バーコード（ECC 200）を生成する方法](/barcode/net/datamatrix-barcode-configuration/datamatrix-ecc-200-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< blocks/products/products-backtop-button >}}

```csharp
using Aspose.BarCode.Generation;
```

```csharp
string path = "Your Directory Path";
```

```csharp
System.Console.WriteLine("DataMatrixEncodeModeASCII:");

using (BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.DataMatrix, "Aspose"))
{
    // Set the X-dimension (size) of the barcode in pixels
    gen.Parameters.Barcode.XDimension.Pixels = 4;
    
    // Set the encoding mode to ASCII
    gen.Parameters.Barcode.DataMatrix.DataMatrixEncodeMode = DataMatrixEncodeMode.ASCII;
    
    // Save the barcode as a PNG image
    gen.Save($"{path}DataMatrixEncodeModeASCII.png", BarCodeImageFormat.Png);
}
```

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}