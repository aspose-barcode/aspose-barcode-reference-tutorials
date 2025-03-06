---
title: Aspose.BarCode for .NET を使用した DataMatrix コード テキストの構成
linktitle: DataMatrix 拡張コードテキスト構成
second_title: Aspose.BarCode .NET API
description: Aspose.BarCode for .NET を使用して DataMatrix 拡張コード テキストを構成する方法を学びます。バーコードを生成、認識し、.NET アプリケーションに統合します。
weight: 17
url: /ja/net/datamatrix-barcode-configuration/datamatrix-extended-code-text-configuration/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.BarCode for .NET を使用した DataMatrix コード テキストの構成

ソフトウェア開発の世界では、バーコードの統合はさまざまなアプリケーションにとって極めて重要な要素となっています。 Aspose.BarCode for .NET などのライブラリを利用すると、.NET アプリケーションでバーコードを簡単に生成して認識できます。このチュートリアルでは、Aspose.BarCode for .NET を使用して DataMatrix 拡張コード テキストを構成するプロセスについて説明します。詳細に入る前に、このガイドの前提条件を見てみましょう。

## 前提条件

始める前に、次のものが整っていることを確認してください。

1. .NET ライブラリ用の Aspose.BarCode
Aspose.BarCode for .NET をインストールする必要があります。まだダウンロードしていない場合は、Web サイトからダウンロードできます[ここ](https://releases.aspose.com/barcode/net/).

2. .NET開発環境
このチュートリアルを進めるには、システム上に .NET 開発環境がセットアップされている必要があります。 Visual Studio またはその他の任意の IDE を使用できます。

3. C# の基礎知識
このチュートリアルには、C# プログラミングの基本的な理解が不可欠です。

必要なツールと知識が得られたので、Aspose.BarCode for .NET を使用して DataMatrix 拡張コード テキストを構成するプロセスを、簡単なステップバイステップの手順に分解してみましょう。

## 名前空間のインポート

Aspose.BarCode for .NET を使用する最初のステップは、必要な名前空間をインポートすることです。次の名前空間をコードに追加します。

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode.BarCodeRecognition;
```

これらの名前空間は、バーコードを操作するために必要なクラスとメソッドを提供します。

## ステップ 1: DataMatrix 拡張コード テキストの構成

このステップでは、DataMatrix 拡張コード テキストを構成するプロセスについて説明します。

## ステップ 2: ディレクトリ パスを定義する

生成された DataMatrix バーコードを保存するディレクトリ パスを指定する必要があります。交換する`"Your Directory Path"`システム上の実際のパスに置き換えます。

```csharp
string path = "Your Directory Path";
```

## ステップ 3: コードテキストを作成する

DataMatrix バーコードのコードテキストを作成するには、`DataMatrixExtCodetextBuilder`。このビルダーを使用すると、さまざまなエンコーディングを持つさまざまなタイプのコードテキストを追加できます。

```csharp
DataMatrixExtCodetextBuilder codetextBuilder = new DataMatrixExtCodetextBuilder();
codetextBuilder.AddECICodetext(ECIEncodings.UTF8, "犬Right狗");
codetextBuilder.AddECICodetextWithEncodeMode(ECIEncodings.UTF8, DataMatrixEncodeMode.C40, "ABCDE");
codetextBuilder.AddPlainCodetext("test");
codetextBuilder.AddCodetextWithEncodeMode(DataMatrixEncodeMode.Text, "abcde");
```

このコードは、さまざまなエンコーディングを組み合わせてコードテキストを構成します。

## ステップ 4: コードテキストを生成する

コードテキストを構成した後、DataMatrix コードテキスト文字列を生成します。

```csharp
string codetext = codetextBuilder.GetExtendedCodetext();
```

## ステップ 5: DataMatrix バーコードを生成する

ここで、生成されたコードテキストを使用して DataMatrix バーコードを作成します。 X 寸法やコード テキスト表示など、バーコードのさまざまなパラメータを設定することもできます。

```csharp
using (var generator = new BarcodeGenerator(EncodeTypes.DataMatrix, codetext))
{
    generator.Parameters.Barcode.XDimension.Pixels = 4;
    generator.Parameters.Barcode.CodeTextParameters.TwoDDisplayText = "Extended Codetext";
    generator.Parameters.Barcode.DataMatrix.DataMatrixEncodeMode = DataMatrixEncodeMode.ExtendedCodetext;

    generator.Save($"{path}DataMatrixExtendedCodetext.png", BarCodeImageFormat.Png);
}
```

このコードは、指定された設定で DataMatrix バーコード イメージを生成し、保存します。

## ステップ 6: 認識しようとする

バーコードを確実に認識できるようにするには、`BarCodeReader`バーコードを読み取るクラス。

```csharp
using (var reader = new BarCodeReader(generator.GenerateBarCodeImage(), DecodeType.DataMatrix))
{
    foreach (BarCodeResult result in reader.ReadBarCodes())
        Console.WriteLine("DataMatrixExtendedCodetext:" + result.CodeText);
}
```

このステップでは、生成されたバーコードの認識を試みることにより、そのバーコードを検証します。

おめでとう！ Aspose.BarCode for .NET を使用して DataMatrix 拡張コード テキストを正常に構成しました。この機能を .NET アプリケーションに統合できるようになりました。

## 結論

このチュートリアルでは、Aspose.BarCode for .NET を使用して DataMatrix 拡張コード テキストを構成するプロセスについて説明しました。前提条件、段階的な手順を説明し、バーコードを生成して認識する方法を示しました。この知識があれば、バーコード生成および認識機能を追加して .NET アプリケーションを強化できます。

## よくある質問

### Q1: Aspose.BarCode for .NET とは何ですか?

A1: Aspose.BarCode for .NET は、開発者が .NET アプリケーションでバーコードを生成および認識できるようにする強力なライブラリです。幅広いバーコード シンボルをサポートし、さまざまなカスタマイズ オプションを提供します。

### Q2: Aspose.BarCode for .NET のドキュメントはどこで見つけられますか?

A2: Aspose.BarCode for .NET のドキュメントにアクセスできます。[ここ](https://reference.aspose.com/barcode/net/).

### Q3: Aspose.BarCode for .NET の無料トライアルはありますか?

 A3: はい、Aspose.BarCode for .NET の無料試用版を入手できます。[ここ](https://releases.aspose.com/).

### Q4: Aspose.BarCode for .NET の一時ライセンスを取得するにはどうすればよいですか?

 A4: テストまたは評価の目的で一時ライセンスが必要な場合は、一時ライセンスを取得できます。[ここ](https://purchase.aspose.com/temporary-license/).

### Q5: Aspose.BarCode for .NET に関するサポートや質問はどこで受けられますか?

 A5: Aspose.BarCode for .NET に関するサポートや質問については、Aspose.BarCode フォーラムにアクセスしてください。[ここ](https://forum.aspose.com/c/barcode/13).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
