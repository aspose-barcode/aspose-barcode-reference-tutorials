---
title: Aspose.BarCode for .NET を使用して DataMatrix バーコードを生成する
linktitle: データマトリックスのバージョン
second_title: Aspose.BarCode .NET API
description: Aspose.BarCode for .NET を使用して .NET で DataMatrix バーコードを生成する方法を学びます。カスタム ディメンション、ECC サポートなど。
weight: 12
url: /ja/net/datamatrix-barcode-reading/datamatrix-versions/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.BarCode for .NET を使用して DataMatrix バーコードを生成する

.NET アプリケーションで DataMatrix バーコードを生成するための信頼できるソリューションをお探しの場合は、Aspose.BarCode for .NET が最適です。このステップバイステップ ガイドでは、Aspose.BarCode for .NET を使用して DataMatrix バーコードを作成するプロセスを説明します。各例を複数のステップに分けて説明するので、簡単に理解できるようになります。

## 前提条件

コードに入る前に、次の前提条件が満たされていることを確認してください。
- .NET をサポートする開発環境。
-  Aspose.BarCode for .NET のコピー。以下からダウンロードできます。[このリンク](https://releases.aspose.com/barcode/net/).
- C# と .NET Framework の基本的な知識。

ここで、DataMatrix のバージョンと、Aspose.BarCode for .NET を使用してそれらを生成する方法を見てみましょう。

## 名前空間のインポート

どの C# プロジェクトでも、必要な名前空間をインポートすることが不可欠です。 Aspose.BarCode の場合は、以下を含める必要があります。

```csharp
using Aspose.BarCode.Generation;
```

この名前空間は、`BarcodeGenerator`クラス。これはバーコードを生成するために重要です。

ここで、例を複数のステップに分けてみましょう。

## ステップ 1: ディレクトリ パスを設定する

まず、生成された DataMatrix バーコードを保存するディレクトリ パスを定義します。

```csharp
string path = "Your Directory Path";
```

交換する`"Your Directory Path"`バーコード画像を保存する実際のパスを指定します。

## ステップ 2: バーコード ジェネレーターを初期化する

のインスタンスを作成します。`BarcodeGenerator`クラスを指定し、バーコード タイプを次のように指定します`DataMatrix`。バーコード内でエンコードするデータを指定することもできます。

```csharp
using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.DataMatrix, "Åspóse.Barcóde©"))
{
    //バーコードを生成するコードはここにあります
}
```

## ステップ 3: バーコードのプロパティを構成する

DataMatrix バーコードの寸法や ECC (エラー訂正コード) タイプなど、DataMatrix バーコードのさまざまなプロパティをカスタマイズできます。 X 次元を 4 ピクセルに設定し、ECC200 を選択する例を次に示します。

```csharp
generator.Parameters.Barcode.XDimension.Pixels = 4;
generator.Parameters.Barcode.DataMatrix.DataMatrixEcc = DataMatrixEccType.Ecc200;
```

## ステップ 4: DataMatrix バージョンを設定して保存する

行数と列数を設定することで、DataMatrix のバージョンを指定できます。バージョンを設定したら、バーコード画像を保存します。

たとえば、ECC200 を使用して 22 行 22 列の DataMatrix バーコードを作成するには、次のようにします。

```csharp
generator.Parameters.Barcode.DataMatrix.DataMatrixVersion = DataMatrixVersion.ECC200_22x22;
generator.Save($"{path}DataMatrixRows22Columns22Ecc200.png", BarCodeImageFormat.Png);
```

同様に、必要に応じてバージョンと ECC タイプを変更することで、異なるパラメータを持つバーコードを生成できます。

## ステップ 5: 他のバージョンについても繰り返します

他の DataMatrix バージョンに対してステップ 4 を繰り返すことができます。たとえば、ECC200 を使用して 12 行 64 列のバーコードを作成するには、次のようにします。

```csharp
generator.Parameters.Barcode.DataMatrix.DataMatrixVersion = DataMatrixVersion.DMRE_12x64;
generator.Save($"{path}DataMatrixRows12Columns64Ecc200.png", BarCodeImageFormat.Png);
```

## ステップ 6: ECC タイプを切り替える

ECC タイプを Ecc140 に変更する場合は、ECC プロパティを更新することで変更できます。

```csharp
generator.Parameters.Barcode.DataMatrix.DataMatrixEcc = DataMatrixEccType.Ecc140;
```

## ステップ 7: 異なるバージョンと ECC を使用してバーコードを生成する

他の DataMatrix バージョンおよび ECC タイプについてステップ 4 を繰り返し、各バーコードを一意のファイル名で保存します。

```csharp
generator.Parameters.Barcode.DataMatrix.DataMatrixVersion = DataMatrixVersion.ECC000_140_29x29;
generator.Save($"{path}DataMatrixRows29Columns29Ecc140.png", BarCodeImageFormat.Png);
```

Aspose.BarCode for .NET を使用して DataMatrix バーコードを生成する方法を学習したので、この機能を .NET アプリケーションに簡単に統合できます。

## 結論

Aspose.BarCode for .NET は、.NET アプリケーションで DataMatrix バーコードを生成するプロセスを簡素化します。このステップバイステップのガイドを使用すると、さまざまなバージョンと ECC タイプのバーコードを作成して、特定のニーズを満たす柔軟性とカスタマイズを実現できます。

ご質問がある場合やサポートが必要な場合は、お気軽に次のサイトにアクセスしてください。[Aspose.BarCode for .NET ドキュメント](https://reference.aspose.com/barcode/net/)またはチェックしてください[Aspose.BarCode フォーラム](https://forum.aspose.com/c/barcode/13)サポートのための。

## よくある質問

### Q1: DataMatrix バーコードの ECC とは何ですか?

A1: ECC (エラー訂正コード) は、データの整合性を確保するのに役立つ DataMatrix バーコードの重要なコンポーネントです。 ECC レベルが異なると、エラー訂正の程度も異なります。

### Q2: Aspose.BarCode for .NET を使用してカスタム ディメンションを持つ DataMatrix バーコードを生成できますか?

A2: はい、チュートリアルで説明されているように行と列の数を設定することで、DataMatrix バーコードの寸法をカスタマイズできます。

### Q3: Aspose.BarCode for .NET はどこでダウンロードできますか?

 A3: Aspose.BarCode for .NET は、以下からダウンロードできます。[このリンク](https://releases.aspose.com/barcode/net/).

### Q4: Aspose.BarCode for .NET の無料トライアルはありますか?

 A4: はい、Aspose.BarCode for .NET の無料トライアルにアクセスできます。[ここ](https://releases.aspose.com/).

### Q5: Aspose.BarCode for .NET の一時ライセンスを取得するにはどうすればよいですか?

 A5: Aspose.BarCode for .NET の一時ライセンスを取得するには、次のサイトにアクセスしてください。[このリンク](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
