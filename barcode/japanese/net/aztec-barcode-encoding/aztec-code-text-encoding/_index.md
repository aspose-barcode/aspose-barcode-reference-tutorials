---
date: 2026-01-02
description: Aspose.BarCode for .NET を使用して Aztec コードの作成方法と認識方法を学びましょう。このガイドでは、.NET
  アプリで Aztec コードのエンコード、保存、読み取りについて解説します。
linktitle: Aztec Code Text Encoding
second_title: Aspose.BarCode .NET API
title: .NET 用 Aspose.BarCode でアズテックコードを作成する方法
url: /ja/net/aztec-barcode-encoding/aztec-code-text-encoding/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.BarCode for .NET を使用した Aztec コード テキスト エンコーディング

## はじめに

Aspose.BarCode for .NET を使用して **Aztec コードの作成** の魅力的な世界に飛び込む準備はできましたか？この包括的なガイドでは、**Aztec コードの作成** 方法、カスタムテキストのエンコード、画像の保存、そして読み取りまでを順を追って説明します。このチュートリアルの最後までに、技術的な手順を理解するだけでなく、なぜこのフォーマットが現代のアプリケーションでコンパクトなデータ保存に最適なのかが分かります。それでは始めましょう！

## クイック回答
- **このチュートリアルで学べることは？** .NET でテキストエンコードされた Aztec コードを作成、保存、認識する方法です。  
- **必要なライブラリは？** Aspose.BarCode for .NET。  
- **ライセンスは必要ですか？** 開発には無料トライアルで動作しますが、本番環境では商用ライセンスが必要です。  
- **サポートされている .NET バージョンは？** .NET Framework 4.5 以上、.NET Core 3.1 以上、.NET 5/6 以上。  
- **実装にかかる時間は？** 基本的な例で約 10〜15 分です。

## Aztec コードとは？

Aztec Code は、コンパクトな正方形パターンに大量のデータを格納できる二次元バーコードです。QR コードとは異なり、周囲の「クワイエットゾーン」を必要としないため、スペースが限られたデザインに最適です。

## なぜ Aspose.BarCode for .NET を使用して Aztec コードを作成するのか？

- **フルコントロール** エンコードオプション（文字セット、エラー訂正、サイズ）を設定可能。  
- **高性能な認識** エンジンで、画像、ストリーム、ウェブカメラフィードから Aztec コードを読み取れます。  
- **クロスプラットフォーム** 対応（.NET Framework、.NET Core、.NET 5/6）。  
- **外部依存なし** – すべてマネージドコードで動作します。

## 前提条件

このエキサイティングな旅に出る前に、いくつかの前提条件を用意してください：

1. Aspose.BarCode for .NET: この強力なライブラリをインストールしてください。ドキュメントは [Aspose.BarCode for .NET Documentation](https://reference.aspose.com/barcode/net/) にあります。  
2. Visual Studio: .NET アプリケーションを作成・実行するために、システムに Visual Studio がインストールされている必要があります。  
3. C# の基本知識: C# プログラミングに慣れていると有利ですが、すべての方が理解できるように詳細な説明を提供します。  

前提条件の説明が終わったので、Aztec コード テキスト エンコーディングの手順に進みましょう。

## 名前空間のインポート

まず、C# アプリケーションで Aspose.BarCode for .NET を使用するために必要な名前空間をインポートします。`.cs` ファイルの先頭に以下のコードを追加してください：

```csharp
using System;
using System.Text;
using Aspose.BarCode.Generation;
using Aspose.BarCode.BarCodeRecognition;
```

## Aspose.BarCode for .NET を使用して Aztec コードを作成する方法

### 手順 1: ディレクトリ パスの定義

生成した Aztec コード画像を保存するパスを設定します。`"Your Directory Path"` を目的のディレクトリ パスに置き換えてください。

```csharp
string path = "Your Directory Path";
```

### 手順 2: Aztec コード ジェネレータの初期化

`EncodeTypes` を Aztec に設定し、エンコードしたいテキストを指定して `BarcodeGenerator` のインスタンスを作成します。

```csharp
BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.Aztec, "Aspose常に先を行く");
```

### 手順 3: バーコード パラメータの設定

バーコードのパラメータを構成します。この例では、XDimension をピクセル単位で設定し、コードテキストのエンコーディングを UTF‑8 にしています。

```csharp
gen.Parameters.Barcode.XDimension.Pixels = 4;
gen.Parameters.Barcode.Aztec.CodeTextEncoding = Encoding.UTF8;
```

### 手順 4: Aztec コード画像の保存

生成した Aztec コード画像を指定したディレクトリに保存します。

```csharp
gen.Save($"{path}AztecCodeTextEncoding.png", BarCodeImageFormat.Png);
```

### 手順 5: Aztec コードの認識

作成した Aztec コードを認識してみましょう。この目的のために `BarCodeReader` を使用します。

```csharp
BarCodeReader read = new BarCodeReader(gen.GenerateBarCodeImage(), DecodeType.Aztec);
foreach (BarCodeResult result in read.ReadBarCodes())
    Console.WriteLine("AztecCodeTextEncoding:" + result.GetCodeText(Encoding.UTF8));
```

## よくある落とし穴とヒント

- **ファイルパスの問題** – `path` 変数が OS に適したディレクトリ区切り文字（`\` または `/`）で終わっていることを確認してください。  
- **エンコーディングの不一致** – `CodeTextEncoding` をソーステキストの文字セットに合わせて必ず設定してください。そうしないと文字化けが発生する可能性があります。  
- **ライセンス例外** – 有効なライセンスがない場合、生成された画像に透かしが入ることがあります。  

## FAQ

### Q1: Aztec コードとは？

A1: Aztec Code は、テキストや URL などさまざまなデータタイプをエンコードできる二次元バーコード形式です。

### Q2: なぜ Aspose.BarCode for .NET を使用すべきか？

A2: Aspose.BarCode for .NET は、.NET アプリケーションでのバーコードの作成と認識を簡素化する強力なライブラリで、時間と労力を節約できます。

### Q3: Aspose.BarCode for .NET で Aztec コードの外観をカスタマイズできますか？

A3: はい、サイズ、色、エンコードオプションなど、Aztec コードのさまざまな側面をニーズに合わせてカスタマイズできます。

### Q4: Aspose.BarCode for .NET の無料トライアルはありますか？

A4: はい、[here](https://releases.aspose.com/) から無料トライアルで Aspose.BarCode for .NET を試すことができます。

### Q5: Aspose.BarCode for .NET に関するサポートや質問はどこで受けられますか？

A5: サポートフォーラム [https://forum.aspose.com/c/barcode/13](https://forum.aspose.com/c/barcode/13) の Aspose.BarCode for .NET コミュニティに参加して、支援を受けたり経験を共有したりできます。

### Q6: ファイルではなくストリームから Aztec コードを読み取れますか？

A6: もちろんです。`BarCodeReader` は `Stream` オブジェクトも受け付けるため、メモリ、ネットワークソース、データベース BLOB から読み取れます。

### Q7: Aztec コードのエラー訂正レベルを変更するには？

A7: `gen.Parameters.Barcode.Aztec.ErrorCorrection` を使用して希望のレベル（例: `ErrorCorrectionLevel.L`、`M`、`Q`、`H`）を設定します。

## 結論

このチュートリアルでは、Aspose.BarCode for .NET を使用した **Aztec コード テキスト エンコーディング** の魅力的な世界を探求しました。前提条件の説明、必要な名前空間のインポート、そして **Aztec コードの作成**、外観のカスタマイズ、画像としての保存、再認識までの各手順を分解して解説しました。これで、在庫管理から安全なデータ送信まで、さまざまなシナリオで .NET アプリケーションに Aztec コードを統合するための確固たる基盤ができました。

さらに詳しい情報や高度な機能については、[Aspose.BarCode for .NET Documentation](https://reference.aspose.com/barcode/net/) をご覧ください。コーディングをお楽しみください！

---

**Last Updated:** 2026-01-02  
**Tested With:** Aspose.BarCode 24.11 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}