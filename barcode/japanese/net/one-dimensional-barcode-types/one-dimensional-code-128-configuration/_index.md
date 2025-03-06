---
title: 一次元コード 128 の構成
linktitle: 一次元コード 128 の構成
second_title: Aspose.BarCode .NET API
description: Aspose.BarCode を使用して .NET で 1 次元の Code 128 バーコードを生成する方法を学びます。シームレスなバーコード統合については、ステップバイステップのガイドに従ってください。
weight: 10
url: /ja/net/one-dimensional-barcode-types/one-dimensional-code-128-configuration/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 一次元コード 128 の構成


アプリケーションでバーコードを生成する強力なツールを探している .NET 開発者にとって、Aspose.BarCode for .NET は頼りになるソリューションです。この包括的なガイドでは、Aspose.BarCode for .NET の機能を利用して 1 次元の Code 128 バーコードを作成するプロセスを説明し、初心者と経験豊富な開発者の両方を対象に設計されています。 

## 前提条件

Aspose.BarCode を使用したバーコード生成のエキサイティングな世界に入る前に、次の前提条件が満たされていることを確認してください。

1. Visual Studio: システムに Visual Studio がインストールされていることを確認します。

2.  Aspose.BarCode for .NET: Aspose.BarCode for .NET をダウンロードしてインストールする必要があります。から入手できます[ここ](https://releases.aspose.com/barcode/net/).

3. .NET プロジェクト: .NET プロジェクトをセットアップし、バーコード生成を統合する準備ができている必要があります。

さあ、始めましょう！

## 名前空間のインポート

最初のステップは、プロジェクトに必要な名前空間をインポートすることです。これらの名前空間を使用すると、Aspose.BarCode の機能にアクセスできます。

### ステップ 1: 名前空間をインポートする

```csharp
using Aspose.BarCode.Generation;
```

## 一次元コード 128 の構成

次に、Aspose.BarCode for .NET を使用して Code 128 バーコードを作成しましょう。各ステップを詳しく説明し、プロセスを明確に理解できるようにします。

### ステップ 2: パスを設定する

まず、生成されたバーコード画像を保存するディレクトリへのパスを設定します。

```csharp
string path = "Your Directory Path";
```

### ステップ 3: Code 128 バーコード ジェネレーターを作成する

を作成します`BarcodeGenerator`Code 128 バーコードを生成するためのインスタンス。生成するバーコードのタイプ (この場合は Code128) とエンコードする値を指定できます。

```csharp
BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.Code128, "CODE");
```

### ステップ 4: バーコードパラメータを設定する

バーコードを生成する前に、さまざまなパラメータを設定できます。たとえば、チェックサムを表示するか非表示にするかを選択できます。

#### オプション 1: チェックサムを表示しない

```csharp
gen.Parameters.Barcode.ChecksumAlwaysShow = false;
```

#### オプション 2: チェックサムを表示する

```csharp
gen.Parameters.Barcode.ChecksumAlwaysShow = true;
```

### ステップ 5: バーコード画像を保存する

次に、生成されたバーコード画像を指定したディレクトリに保存します。前の手順で選択した構成に応じて、チェックサム付きまたはチェックサムなしでバーコードを保存できます。

#### チェックサムなしでバーコードを保存

```csharp
gen.Save($"{path}OneCSCode128NotShowChecksum.png", BarCodeImageFormat.Png);
```

#### バーコードをチェックサム付きで保存

```csharp
gen.Save($"{path}OneCSCode128ShowChecksum.png", BarCodeImageFormat.Png);
```

それでおしまい！ Aspose.BarCode for .NET を使用して 1 次元 Code 128 バーコードを生成することに成功しました。これらのバーコードは、在庫管理、製品のラベル付けなど、さまざまなアプリケーションで使用できます。

## 結論

Aspose.BarCode for .NET は、.NET アプリケーションでのバーコード生成のための強力でユーザーフレンドリーなソリューションを提供します。直感的な API と広範なドキュメントにより、バーコード機能をプロジェクトに簡単に統合できます。 1 次元バーコードを作成する必要がある場合も、2 次元バーコードを作成する必要がある場合も、Aspose.BarCode が対応します。

今すぐ Aspose.BarCode を .NET アプリケーションに組み込み、バーコード生成プロセスを簡単に合理化してください。

### よくある質問

### Aspose.BarCode for .NET は .NET Core と互換性がありますか?
はい、Aspose.BarCode for .NET は .NET Framework と .NET Core の両方と互換性があります。

### 生成されたバーコードの外観をカスタマイズできますか?
絶対に！ Aspose.BarCode を使用すると、サイズ、色、テキストの配置など、バーコードのさまざまな側面をカスタマイズできます。

### Aspose.BarCode は QR コードの生成に適していますか?
Aspose.BarCode は主に 1 次元バーコードに焦点を当てていますが、Aspose.BarCode for .NET を使用して QR コードを生成することもできます。

### 無料トライアルはありますか?
はい、試用版をダウンロードすると、Aspose.BarCode for .NET を無料で試すことができます[ここ](https://releases.aspose.com/).

### Aspose.BarCode for .NET のサポートはどこで入手できますか?
Aspose.BarCode for .NET フォーラムで助けを求め、経験を共有できます。[ここ](https://forum.aspose.com/c/barcode/13).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
