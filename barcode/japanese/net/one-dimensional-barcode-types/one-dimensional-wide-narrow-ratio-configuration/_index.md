---
title: 1 次元のワイド/ナロー比構成
linktitle: 1 次元のワイド/ナロー比構成
second_title: Aspose.BarCode .NET API
description: Aspose.BarCode for .NET を使用して、カスタマイズされたバーコードを簡単に生成します。 1 次元のワイド/ナロー比構成のステップバイステップ ガイド。
type: docs
weight: 22
url: /ja/net/one-dimensional-barcode-types/one-dimensional-wide-narrow-ratio-configuration/
---

.NET アプリケーションでバーコードを簡単に生成およびカスタマイズしたいと考えていますか?これ以上探さない！ Aspose.BarCode for .NET は、バーコードの生成とカスタマイズを簡単にする堅牢なライブラリです。このステップバイステップ ガイドでは、Aspose.BarCode for .NET の機能を活用して、ワイド/ナロー比構成のバーコードを作成する方法を詳しく説明します。

## 前提条件

Aspose.BarCode for .NET を使用してバーコードの世界に入る前に、次の前提条件を満たしている必要があります。

### 1. Visual Studio環境
   - .NET アプリケーションを操作するには、システムに Visual Studio がインストールされていることを確認してください。
   
### 2. .NET ライブラリ用の Aspose.BarCode
   -  Aspose.BarCode for .NET ライブラリがインストールされている必要があります。からダウンロードできます。[Webサイト](https://releases.aspose.com/barcode/net/).

### 3. ライセンスキー (オプション)
   - ライセンス キーをお持ちの場合は、それを使用してライブラリの追加機能のロックを解除できます。一時ライセンスは次から取得できます。[ここ](https://purchase.aspose.com/temporary-license/).

前提条件が整ったので、Aspose.BarCode for .NET を使用してワイド/ナロー比率構成で 1 次元バーコードの作成に移りましょう。

## 名前空間のインポート

まず、Aspose.BarCode for .NET の機能にアクセスするために必要な名前空間をプロジェクトに含める必要があります。これを行うには、コードの先頭に次の using ステートメントを追加します。

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;
```

## ステップ 1: ディレクトリ パスを定義する

まず、生成されたバーコード画像を保存するパスを定義します。これは次のコードで実行できます。

```csharp
string path = "Your Directory Path";
```

交換する`"Your Directory Path"`バーコード画像を保存する実際のディレクトリパスに置き換えます。

## ステップ 2: 1 次元のワイド/ナロー比バーコードを作成する

次に、Aspose.BarCode for .NET を使用して、ワイド/ナロー比率構成の 1 次元バーコードを作成してみましょう。この例では、Code39Extended エンコード タイプを使用し、データを「ASPOSE」に設定します。

```csharp
BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.Code39Extended, "ASPOSE");
```

このコード行は、指定されたエンコード タイプとデータを使用してバーコード ジェネレーターを初期化します。

## ステップ 3: ワイド/ナロー比を設定する

幅狭比は、バーコード内の幅広要素と幅狭要素の比率を決定します。このステップでは、幅狭比を 2 に設定します。

```csharp
gen.Parameters.Barcode.WideNarrowRatio = 2;
```

次に、生成されたバーコード画像を指定されたパスに保存します。

```csharp
gen.Save($"{path}WideNarrow2Code39.png", BarCodeImageFormat.Png);
```

## ステップ 4: ワイド/ナロー比を調整する

目的のバーコードの外観を実現するために、さまざまな幅と幅の比率を試してみることができます。たとえば、バーコードの幅を広くしたい場合は、幅狭比を 5 に設定します。

```csharp
gen.Parameters.Barcode.WideNarrowRatio = 5;
```

そして、バーコード画像を保存します。

```csharp
gen.Save($"{path}WideNarrow5Code39.png", BarCodeImageFormat.Png);
```

これで、Aspose.BarCode for .NET を使用して、幅狭比が異なる 1 次元バーコードを正常に作成できました。このライブラリは、特定の要件に合わせてバーコードを生成する柔軟性を提供します。

## 結論

Aspose.BarCode for .NET は、.NET アプリケーションでのバーコードの生成とカスタマイズを簡素化する多用途ライブラリです。このチュートリアルでは、ワイドとナローの比率構成で 1 次元バーコードを作成する基本について説明しました。さまざまなパラメータを微調整できるため、ニーズにぴったり合ったバーコードを作成できます。

## よくある質問

### 1. Aspose.BarCode for .NET のライセンスを取得するにはどうすればよいですか?
からライセンスを購入できます。[Aspose ウェブサイト](https://purchase.aspose.com/buy).

### 2. ライセンスなしで Aspose.BarCode for .NET を使用できますか?
はい、機能が制限された一時ライセンスで使用できます。

### 3. Aspose.BarCode for .NET は .NET Core と互換性がありますか?
はい、Aspose.BarCode for .NET は .NET Core および .NET Framework と互換性があります。

### 4. 生成できるバーコードの種類に制限はありますか?
Aspose.BarCode for .NET は、QR コード、Code 39 などを含む幅広いバーコード シンボルをサポートしています。

### 5. Aspose.BarCode for .NET についてサポートを受けたり、質問したりするにはどうすればよいですか?
訪問できます。[Aspose.BarCode フォーラム](https://forum.aspose.com/c/barcode/13)サポートとディスカッションのため。
