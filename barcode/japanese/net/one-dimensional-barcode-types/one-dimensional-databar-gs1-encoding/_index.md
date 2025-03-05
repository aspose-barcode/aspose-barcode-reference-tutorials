---
title: 1次元データバーのGS1エンコーディング
linktitle: 1次元データバーのGS1エンコーディング
second_title: Aspose.BarCode .NET API
description: Aspose.BarCode を使用して、.NET で Databar GS1 エンコードされたバーコードを作成する方法を学びます。バーコードを簡単に生成します。ステップバイステップのガイドに従ってください。
type: docs
weight: 18
url: /ja/net/one-dimensional-barcode-types/one-dimensional-databar-gs1-encoding/
---

このチュートリアルでは、Aspose.BarCode for .NET ライブラリを使用して、1 次元 Databar GS1 エンコードされたバーコードを作成するプロセスを説明します。 GS1 エンコーディングを使用してバーコードを生成したい場合でも、GS1 エンコーディングを使用せずにバーコードを生成したい場合でも、当社が対応します。このステップバイステップのガイドは、前提条件を理解し、名前空間をインポートし、Databar GS1 でエンコードされたバーコードを簡単に作成するための各例を示すのに役立ちます。

## 前提条件

コードに入る前に、次の前提条件が満たされていることを確認してください。

1.  Aspose.BarCode for .NET: Aspose.BarCode for .NET がインストールされている必要があります。まだダウンロードしていない場合は、からダウンロードできます[ここ](https://releases.aspose.com/barcode/net/).

2. ディレクトリ パス: 置き換えます`"Your Directory Path"`コード例では、生成されたバーコード画像を保存する実際のパスを指定します。

必要な前提条件が準備できたので、コーディング部分に進みましょう。

## 名前空間のインポート

まず、Aspose.BarCode に関連する名前空間をインポートする必要があります。 .NET プロジェクトの先頭に次のコード行を追加します。

```csharp
using Aspose.BarCode;
using System;
```

## ステップ 1: バーコード ジェネレーターを初期化する

最初のステップは、目的のエンコーディング タイプで BarcodeGenerator オブジェクトを初期化することです。この場合、Databar Expanded エンコーディングを使用しています。 

```csharp
string path = "Your Directory Path";
System.Console.WriteLine("OneDDatabarGS1Encoding:");

BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.DatabarExpanded, "");
```

## ステップ 2: GS1 エンコーディングを使用してバーコードを生成する

ここで、GS1Encoding チェックを使用してコードテキストを設定し、生成されたバーコード画像を保存します。 

```csharp
gen.CodeText = "(01)12345678901231";
gen.Parameters.Barcode.DataBar.IsAllowOnlyGS1Encoding = true;
gen.Save($"{path}DatabarGS1RightEncoding.png", BarCodeImageFormat.Png);
```

## ステップ 3: 変数エンコーディング バーコードを生成する

このステップでは、GS1Encoding チェックを行わずに、可変コードテキストを含むバーコードを生成します。

```csharp
gen.CodeText = "ASPOSE";
gen.Parameters.Barcode.DataBar.IsAllowOnlyGS1Encoding = false;
gen.Save($"{path}DatabarGS1VariableEncoding.png", BarCodeImageFormat.Png);
```

## ステップ 4: GS1 エンコーディング チェックの例外を処理する

GS1Encoding チェックを有効にして変数 codetext を使用してバーコードを生成しようとすると、例外がスローされます。対処方法は次のとおりです。

```csharp
try
{
    gen.CodeText = "ASPOSE";
    gen.Parameters.Barcode.DataBar.IsAllowOnlyGS1Encoding = true;
    gen.GenerateBarCodeImage();
}
catch (Exception e)
{
    Console.WriteLine(e.Message);
}
```

これで、Aspose.BarCode for .NET を使用して、1 次元の Databar GS1 エンコードされたバーコードが正常に作成されました。特定の要件に基づいて、バーコード生成をさらに探索してカスタマイズできます。

## 結論

このチュートリアルでは、Aspose.BarCode for .NET を使用して 1 次元 Databar GS1 エンコードされたバーコードを生成するプロセスについて説明しました。前提条件について説明し、必要な名前空間をインポートし、GS1 エンコード バーコードと可変エンコード バーコードの両方を作成するための段階的なガイダンスを提供しました。

 Aspose.BarCode for .NET を使用すると、バーコード生成がシームレスなタスクになり、バーコード作成のニーズに対する柔軟性と制御が提供されます。問題が発生したり、質問がある場合は、お気軽に次のサイトにアクセスしてください。[Aspose.BarCode ドキュメント](https://reference.aspose.com/barcode/net/)または、[Aspose.BarCode サポート フォーラム](https://forum.aspose.com/c/barcode/13).

## よくある質問

### 1. バーコードの GS1 エンコーディングとは何ですか?
GS1 エンコーディングは、適切なデータ構造と識別を保証するためにバーコーディングで使用される標準です。正確な追跡と情報交換を容易にするために、小売、ヘルスケア、物流の品目によく使用されます。

### 2. 生成されたバーコードの外観をカスタマイズできますか?
はい、Aspose.BarCode for .NET で生成されたバーコードの外観をカスタマイズできます。サイズ、色、スタイルなどのさまざまなパラメータを制御できます。

### 3. Aspose.BarCode の追加リソースとドキュメントはどこで入手できますか?
包括的なドキュメントと例は、次の場所にあります。[Aspose.BarCode ドキュメント](https://reference.aspose.com/barcode/net/)。これは、学習とトラブルシューティングのための貴重なリソースです。

### 4. Aspose.BarCode の試用版はありますか?
はい、Aspose.BarCode for .NET の無料試用版を次のサイトから入手できます。[ここ](https://releases.aspose.com/).

### 5. Aspose.BarCode for .NET のライセンスはどのように購入できますか?
 Aspose.BarCode for .NET のライセンスを購入するには、次のサイトにアクセスしてください。[購入ページ](https://purchase.aspose.com/buy) Aspose Web サイトで。
