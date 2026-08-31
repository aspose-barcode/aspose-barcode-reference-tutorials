---
date: 2026-03-07
description: .NETでAspose.BarCodeを使用して、1次元データバーGS1エンコードバーコードの作成方法を学びましょう。このガイドでは、GS1の設定方法、バーコードジェネレータの構成、そしてバーコードを迅速に生成する方法を示します。
linktitle: One-Dimensional Databar GS1 Encoding
second_title: Aspose.BarCode .NET API
title: Aspose.BarCode を使用した一次元データバー GS1 エンコーディングの作成
url: /ja/net/one-dimensional-barcode-types/one-dimensional-databar-gs1-encoding/
weight: 18
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.BarCode を使用した 1 次元 Databar の GS1 エンコードの作成

このチュートリアルでは、.NET 用 Aspose.BarCode ライブラリを使用して、GS1 標準に準拠した **1 次元 Databar** バーコードを **作成** します。厳格な GS1 検証が必要な場合でも、より柔軟なバーコードが必要な場合でも、ライブラリのインストールからエンコード例外の処理まで、すべての手順を詳しく解説しますので、独自のアプリケーションで信頼性の高いバーコードを生成できます。

## Quick Answers
- **「create one-dimensional databar」とは何ですか？** Databar ファミリーの線形（1‑D）バーコードを生成することを意味し、小売や物流でよく使用されます。  
- **GS1 検証はどう設定しますか？** `DataBar` パラメータの `IsAllowOnlyGS1Encoding` を `true` に設定します。  
- **ライセンスは必要ですか？** 開発目的なら無料トライアルで動作しますが、本番環境では商用ライセンスが必要です。  
- **対応している .NET バージョンは？** .NET Framework 4.5 以上、.NET Core 3.1 以上、.NET 5/6/7。  
- **ライブラリはどこからダウンロードできますか？** 公式 Aspose リリースページ（前提条件をご参照）から入手してください。

## 「create one-dimensional databar」とは？
1 次元 Databar（RSS とも呼ばれる）は、数値データ、日付、または AI（Application Identifier）文字列をエンコードできるコンパクトな線形バーコードです。GS1 エンコードと組み合わせることで、世界的に認識されたデータ構造に従い、小売、医療、サプライチェーンなどのシナリオに最適です。

## なぜ .NET 用 Aspose.BarCode を使うのか？
Aspose.BarCode は流暢な API、完全な GS1 サポート、そしてバーコードの視覚的側面を細かく調整できる機能を提供します。低レベルのエンコード作業を省き、ビジネスロジックに集中できます。

## 前提条件

1. **Aspose.BarCode for .NET** – [here](https://releases.aspose.com/barcode/net/) からダウンロードしてインストールします。  
2. **Your Directory Path** – サンプル中の `"Your Directory Path"` を、書き込み権限のあるフォルダーに置き換えてください。

## 名前空間のインポート

C# ファイルの先頭に必要な `using` 文を追加します:

```csharp
using Aspose.BarCode;
using System;
```

## 手順 1: バーコードジェネレータの初期化

`BarcodeGenerator` インスタンスを作成し、**Databar Expanded** シンボロジーを指定します:

```csharp
string path = "Your Directory Path";
System.Console.WriteLine("OneDDatabarGS1Encoding:");

BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.DatabarExpanded, "");
```

## 手順 2: GS1 の設定 – 厳格な GS1 検証でバーコードを生成

GS1 のみのエンコードを有効にし、GS1 準拠のコードテキストを割り当て、画像として保存します:

```csharp
gen.CodeText = "(01)12345678901231";
gen.Parameters.Barcode.DataBar.IsAllowOnlyGS1Encoding = true;
gen.Save($"{path}DatabarGS1RightEncoding.png", BarCodeImageFormat.Png);
```

## 手順 3: Aspose によるバーコード生成 – 可変エンコード（GS1 チェックなし）

GS1 ルールを **適用しない** バーコードが必要な場合は、チェックをオフにします:

```csharp
gen.CodeText = "ASPOSE";
gen.Parameters.Barcode.DataBar.IsAllowOnlyGS1Encoding = false;
gen.Save($"{path}DatabarGS1VariableEncoding.png", BarCodeImageFormat.Png);
```

## 手順 4: バーコードジェネレータの GS1 チェック – 例外処理

`IsAllowOnlyGS1Encoding` が `true` なのにコードテキストが GS1 準拠でない場合、Aspose は例外をスローします。以下のパターンは例外を捕捉してログに記録する方法を示しています:

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

### よくある落とし穴とヒント
- **落とし穴:** GS1 チェックが有効な状態で非 GS1 文字列を指定すると、バーコード生成が中止されます。  
- **プロ・ヒント:** `CodeText` に割り当てる前に AI 文字列を検証し、実行時エラーを防ぎましょう。  
- **ヒント:** 絶対パスや `Path.Combine` を使用して、**プラットフォーム間** で安全にファイル名を構築してください。

## 結論

これで、GS1 エンコード付きの **1 次元 Databar** バーコードの作成方法、GS1 チェックの切り替え方法、そして関連例外の処理方法を Aspose.BarCode for .NET を使って習得できました。`Parameters.Barcode` オブジェクトを通じて、バーコードサイズ、色、余白などの追加スタイリングオプションも自由に設定できます。

問題が発生した場合は、公式ドキュメントとコミュニティフォーラムが有用です:

- [Aspose.BarCode documentation](https://reference.aspose.com/barcode/net/)  
- [Aspose.BarCode support forum](https://forum.aspose.com/c/barcode/13)

## Frequently Asked Questions

### 1. バーコードにおける GS1 エンコードとは何ですか？
GS1 エンコードは、バーコード内のデータ（例: 製品識別子）を標準化された構造で表現する方式で、販売店、メーカー、物流事業者間の相互運用性を確保します。

### 2. 生成したバーコードの外観はカスタマイズできますか？
はい。Aspose.BarCode では、サイズ、色、余白、さらには `Parameters.Barcode` 設定を使って人が読めるテキストを追加することも可能です。

### 3. Aspose.BarCode の追加リソースやドキュメントはどこで入手できますか？
包括的なドキュメントとサンプルは [Aspose.BarCode documentation](https://reference.aspose.com/barcode/net/) にあります。学習やトラブルシューティングに役立ちます。

### 4. Aspose.BarCode のトライアル版はありますか？
はい、[here](https://releases.aspose.com/) から .NET 用の無料トライアル版を取得できます。

### 5. Aspose.BarCode for .NET のライセンスはどうやって購入しますか？
ライセンス購入は Aspose 公式サイトの [purchase page](https://purchase.aspose.com/buy) から行えます。

---

**Last Updated:** 2026-03-07  
**Tested With:** Aspose.BarCode 24.11 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}