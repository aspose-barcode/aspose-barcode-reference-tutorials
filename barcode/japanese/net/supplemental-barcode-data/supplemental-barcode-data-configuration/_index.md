---
title: Aspose.BarCode for .NET を使用した補足バーコード データの作成
linktitle: 補足的なバーコードデータ構成
second_title: Aspose.BarCode .NET API
description: Aspose.BarCode for .NET を使用して補足バーコード データを生成します。 EAN-2 および EAN-5 バーコードを簡単にカスタマイズします。 .NET 開発者向けのステップバイステップ ガイド。
weight: 10
url: /ja/net/supplemental-barcode-data/supplemental-barcode-data-configuration/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.BarCode for .NET を使用した補足バーコード データの作成


バーコードの生成とカスタマイズの世界では、Aspose.BarCode for .NET は強力で多用途のツールとして際立っています。経験豊富な開発者でも、初心者でも、このステップバイステップのガイドでは、Aspose.BarCode for .NET を使用して補足バーコード データを構成するプロセスを説明します。 

## 前提条件

補足バーコード データの世界に入る前に、次の前提条件が満たされていることを確認してください。

- Visual Studio またはその他の .NET 開発ツールを使用してセットアップされた開発環境。
-  Aspose.BarCode for .NET のコピー。まだダウンロードしていない場合は、ダウンロードできます[ここ](https://releases.aspose.com/barcode/net/).
- C# プログラミングの基本的な知識。
- 生成されたバーコード画像を保存できるディレクトリ。

## 名前空間のインポート

まず、Aspose.BarCode for .NET を操作するために必要な名前空間が C# コードに含まれていることを確認します。 C# ファイルの先頭に必要な名前空間をインポートします。

```csharp
using Aspose.BarCode.Generation;
```

ここで、補足バーコード データを構成するプロセスを複数のステップに分割してみましょう。

## ステップ 1: ディレクトリ パスの設定

C# コードで、生成されたバーコード イメージを保存するディレクトリへのパスを定義します。交換する`"Your Directory Path"`実際のディレクトリパスに置き換えます。

```csharp
string path = "Your Directory Path";
```

## ステップ 2: バーコード ジェネレーターの作成

のインスタンスを作成します`BarcodeGenerator`バーコードの種類とエンコードするデータを指定します。この例では、データ「1234567890128」を持つ EAN-13 バーコードを使用しています。

```csharp
BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.EAN13, "1234567890128");
```

## ステップ 3: バーコード寸法のカスタマイズ

寸法 (バーコード内の最小要素の幅) や補助スペースなどのバーコードの寸法を設定します。この例では、X 次元を 2 ピクセルに設定し、補足スペースを 20 ピクセルに設定します。

```csharp
gen.Parameters.Barcode.XDimension.Pixels = 2;
gen.Parameters.Barcode.Supplement.SupplementSpace.Pixels = 20;
```

## ステップ 4: EAN-2 補足の構成

EAN-2 補足バーコードを設定するには、補足データを目的の値に設定します。今回は「12」に設定しました。 

```csharp
gen.Parameters.Barcode.Supplement.SupplementData = "12";
```

## ステップ 5: バーコード画像を保存する

生成されたバーコード画像を、わかりやすい名前を付けて指定したディレクトリに保存します。この例では、EAN-2 補足バーコードを「SupplementEAN2.png」として保存します。

```csharp
gen.Save($"{path}SupplementEAN2.png", BarCodeImageFormat.Png);
```

## ステップ 6: EAN-5 補足の構成

EAN-5 補足バーコードを設定するには、単に`SupplementData`希望の値にします。ここでは「12345」に設定します。

```csharp
gen.Parameters.Barcode.Supplement.SupplementData = "12345";
```

## ステップ 7: バーコード画像の保存 (EAN-5)

最後に、EAN-5 補足バーコード イメージを指定したディレクトリに保存します。今回は「SupplementEAN5.png」として保存します。

```csharp
gen.Save($"{path}SupplementEAN5.png", BarCodeImageFormat.Png);
```

これで、Aspose.BarCode for .NET を使用して補足バーコード データが正常に構成され、生成されました。このアプローチを使用すると、さまざまな補足データを含む幅広い種類のバーコードを作成できます。

## 結論

Aspose.BarCode for .NET は、バーコードの生成とカスタマイズのための強力なツールです。このガイドでは、補足バーコード データの構成と生成のプロセスを段階的に説明しました。適切な前提条件と少しのコーディングにより、バーコード データを効率的に操作し、特定のニーズを満たすことができます。

詳細および高度な使用方法については、「[Aspose.BarCode for .NET ドキュメント](https://reference.aspose.com/barcode/net/).

## よくある質問

### .NET Core プロジェクトで Aspose.BarCode for .NET を使用できますか?
はい、Aspose.BarCode for .NET は .NET Core と互換性があります。

### Aspose.BarCode for .NET に利用できる無料トライアルはありますか?
はい、次のサイトにアクセスして無料で試すことができます。[このリンク](https://releases.aspose.com/).

### Aspose.BarCode for .NET の一時ライセンスはどこで入手できますか?
一時ライセンスは次から取得できます。[このリンク](https://purchase.aspose.com/temporary-license/).

### Aspose.BarCode は幅広い種類のバーコードをサポートしていますか?
はい、EAN-13、QR コード、Code 128 などを含むさまざまなバーコード タイプをサポートしています。

### 生成されたバーコードの外観をカスタマイズできますか?
もちろん、要件に合わせてバーコードの寸法、色、その他の側面をカスタマイズできます。

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
