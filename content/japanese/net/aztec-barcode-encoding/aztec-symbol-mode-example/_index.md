---
title: Aspose.BarCode for .NET を使用してアステカ シンボル モードをマスターする
linktitle: アステカシンボルモードの例
second_title: Aspose.BarCode .NET API
description: Aspose.BarCode for .NET の Aztec Symbol Mode を探索し、多用途のバーコードを簡単に生成する方法を学びましょう。この包括的なチュートリアルで、Auto、FullRange、Compact、Rune モードを実際に試してみましょう。
type: docs
weight: 14
url: /ja/net/aztec-barcode-encoding/aztec-symbol-mode-example/
---
強力なバーコード生成機能を .NET アプリケーションに組み込むことを検討している場合、Aspose.BarCode for .NET は素晴らしいソリューションです。このチュートリアルでは、Aztec Symbol Mode を詳しく調べ、Aspose.BarCode for .NET を使用してそのさまざまなオプションを調べます。前提条件を説明し、名前空間をインポートし、各例を複数のステップに分けてプロセスをガイドします。

## 前提条件

始める前に、次の前提条件が満たされていることを確認してください。

- .NET 開発に関する実践的な知識。
- Visual Studio がマシンにインストールされていること。
-  Aspose.BarCode for .NET のコピー。ダウンロードできます[ここ](https://releases.aspose.com/barcode/net/).

これですべての準備が整ったので、アステカ シンボル モードの例に移りましょう。

## 名前空間のインポート

まず、Aspose.BarCode for .NET を操作するために必要な名前空間をインポートする必要があります。 Visual Studio プロジェクトを開き、コード ファイルの先頭に次の using ステートメントを追加します。

```csharp
using Aspose.BarCode.Generation;
```

ネームスペースを設定したら、Aspose.BarCode for .NET の使用を開始できるようになります。

## ステップ 1: バーコード ジェネレーターのセットアップ

まず、バーコード ジェネレーターを Aztec エンコード タイプで初期化し、コード テキストを指定します。その方法は次のとおりです。

```csharp
string path = "Your Directory Path";
System.Console.WriteLine("AztecSymbolModeExample:");

BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.Aztec, "Åspóse.Barcóde©");
```

このステップでは、ジェネレーターをセットアップし、エンコード用のコード テキストを提供しました。

## ステップ 2: シンボル モードを自動に設定する

次に、アステカ シンボル モードを「自動」に設定し、バーコード イメージを PNG ファイルとして保存しましょう。その方法は次のとおりです。

```csharp
gen.Parameters.Barcode.Aztec.AztecSymbolMode = AztecSymbolMode.Auto;
gen.Save($"{path}AztecSymbolModeAuto.png", BarCodeImageFormat.Png);
```

この手順により、アステカ シンボル モードが自動的に決定され、その結果のバーコード イメージが保存されます。

## ステップ 3: シンボル モードを FullRange に設定する

アステカ シンボル モードを「FullRange」として指定する場合は、次のコードを使用して指定できます。

```csharp
gen.Parameters.Barcode.Aztec.AztecSymbolMode = AztecSymbolMode.FullRange;
gen.Save($"{path}AztecSymbolModeFullRange.png", BarCodeImageFormat.Png);
```

これにより、FullRange Aztec Symbol Mode でバーコードが作成されます。

## ステップ 4: シンボル モードをコンパクトに設定する

アステカ シンボル モードを「コンパクト」に設定してバーコードを作成するには、次のコードを使用します。

```csharp
gen.Parameters.Barcode.Aztec.AztecSymbolMode = AztecSymbolMode.Compact;
gen.Save($"{path}AztecSymbolModeCompact.png", BarCodeImageFormat.Png);
```

この手順では、コンパクト アステカ シンボル モードで生成されるバーコードを構成します。

## ステップ 5: シンボル モードを Rune に設定する

最後に、「ルーン」アステカ シンボル モードを使用したい場合は、次のように設定することで使用できます。

```csharp
gen.CodeText = "123"; //必要に応じてコードテキストを変更します
gen.Parameters.Barcode.Aztec.AztecSymbolMode = AztecSymbolMode.Rune;
gen.Save($"{path}AztecSymbolModeRune.png", BarCodeImageFormat.Png);
```

この手順では、コード テキストを「123」に変更し、ルーン アステカ シンボル モードでバーコードを生成します。

## 結論

このチュートリアルでは、Aspose.BarCode for .NET のアステカ シンボル モードを調べました。バーコード ジェネレーターのセットアップ、Aztec Symbol Mode の Auto、FullRange、Compact、Rune の設定、生成されたバーコード イメージの保存について説明しました。この知識があれば、汎用性の高いバーコード生成を .NET アプリケーションに簡単に組み込むことができるようになります。

ご質問がある場合、またはさらにサポートが必要な場合は、遠慮なく Aspose.BarCode コミュニティにお問い合わせください。[サポートフォーラム](https://forum.aspose.com/c/barcode/13).

## よくある質問

### Q1: バーコード生成における Aztec Symbol Mode の目的は何ですか?

A1: アステカ シンボル モードを使用すると、アステカ バーコードのエンコード方法を指定できるため、バーコード生成が柔軟になります。

### Q2: Aspose.BarCode for .NET の Aztec バーコードのコード テキストを変更できますか?

A2: はい、Aztec バーコードを生成するときに、特定の要件に応じてコード テキストを簡単に変更できます。

### Q3: Aspose.BarCode for .NET の無料試用版は利用可能ですか?

A3: はい、Aspose.BarCode for .NET の無料試用版をダウンロードできます。[ここ](https://releases.aspose.com/).

### Q4: Aspose.BarCode for .NET の完全なドキュメントはどこで見つけられますか?

 A4: Aspose.BarCode for .NET の完全なドキュメントを参照できます。[ここ](https://reference.aspose.com/barcode/net/).

### Q5: Aspose.BarCode for .NET の一時ライセンスを取得するにはどうすればよいですか?

 A5: Aspose.BarCode for .NET の一時ライセンスは、次のサイトにアクセスして取得できます。[このリンク](https://purchase.aspose.com/temporary-license/).