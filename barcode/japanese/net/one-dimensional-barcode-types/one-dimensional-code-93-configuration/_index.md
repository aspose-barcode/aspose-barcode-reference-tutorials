---
date: 2026-02-25
description: Aspose.BarCode for .NET を使用してバーコード画像を生成し、バーコード PNG を保存する方法を学びましょう – 完全な
  Aspose バーコードの例です。
linktitle: One-Dimensional Code 93 Configuration
second_title: Aspose.BarCode .NET API
title: バーコード画像の生成 – Aspose.BarCodeでCode 93
url: /ja/net/one-dimensional-barcode-types/one-dimensional-code-93-configuration/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# バーコード画像の生成 – ワンディメンション Code 93 (Aspose.BarCode 使用)

## はじめに

今日のデジタル時代において、バーコードは在庫管理、製品ラベリング、POS（ポイント・オブ・セール）追跡などのプロセスを簡素化する、私たちの生活に欠かせないものとなっています。**バーコード画像の生成**は、これらの識別子をアプリケーションに統合する最初のステップであることが多いです。Aspose.BarCode for .NET は、数行の C# コードで高品質な Code 93 バーコードを作成できる、堅牢で使いやすい API を提供します。倉庫システム、小売アプリ、カスタムレポートツールのいずれを構築する場合でも、このチュートリアルでは **aspose barcode example** を通じて、バーコードの生成、カスタマイズ、**barcode PNG の保存** 方法を詳しく解説します。

## クイック回答
- **このチュートリアルの内容は？** チェックサム処理付きの Code 93 バーコード画像の作成と保存。  
- **使用されているライブラリは？** Aspose.BarCode for .NET（最新の安定版）。  
- **ライセンスは必要ですか？** 開発には無料トライアルで動作しますが、本番環境では商用ライセンスが必要です。  
- **出力形式を変更できますか？** はい – `BarCodeImageFormat` を変更することで PNG、JPEG、BMP などで保存できます。  
- **最小要件は何ですか？** .NET Framework 4.6+ または .NET Core 3.1+ と Visual Studio。

## Code 93 バーコードとは？

Code 93 は高密度の英数字シンボロジーで、フル ASCII 文字セットをサポートします。そのコンパクトなサイズと組み込みチェックサムにより、スキャン時のデータ整合性が確保されるため、よく選ばれます。

## なぜ Aspose.BarCode でバーコード画像を生成するのか？

- **エンコーディングタイプ、チェックサム、サイズ、画像形式** をフルコントロールできます。  
- **外部依存なし** – ライブラリは任意の .NET プラットフォームで動作します。  
- **優れた描画品質**で、画面表示と高解像度印刷の両方に適しています。  
- **包括的なドキュメント**と多数のサンプルがあり、開発を迅速化します。

## 前提条件

コードに入る前に、以下が揃っていることを確認してください：

1. **Visual Studio**（任意の最新バージョン）。  
2. **Aspose.BarCode for .NET** をインストール – 公式ダウンロードページから取得できます。  
3. **C#** と .NET プロジェクト構造の基本的な知識。

準備ができたので、ステップバイステップのガイドに進みましょう。

## 名前空間のインポート

まず、必要な名前空間をインポートして、バーコード生成クラスにアクセスできるようにします。

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;
```

## 手順 1: ディレクトリパスの設定

生成されたバーコード画像の保存先を定義します。プレースホルダーを、マシン上の有効なフォルダーに置き換えてください。

```csharp
string path = "Your Directory Path";
```

## 手順 2: ワンディメンション Code 93 バーコードの作成

`BarcodeGenerator` を `Code93Extended` タイプでインスタンス化し、エンコードしたいデータを指定します。

```csharp
BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.Code93Extended, "CODE");
```

## 手順 3: チェックサムの有効化（オプション）

Code 93 はデフォルトでチェックサムを含みます。`IsChecksumEnabled` プロパティで有効/無効を切り替えられます。

```csharp
gen.Parameters.Barcode.IsChecksumEnabled = EnableChecksum.Yes;
```

## 手順 4: バーコード画像の保存（バーコード PNG の保存）

画像を生成し、先ほど指定したフォルダーに PNG ファイルとして保存します。

```csharp
gen.Save($"{path}OneCSCode93WithChecksum.png", BarCodeImageFormat.Png);
```

## 手順 5: 例外処理 – チェックサムなしで生成

チェックサム **なし**でバーコードを作成する必要がある場合、発生し得る例外を適切に処理する必要があります。

```csharp
try
{
    gen.Parameters.Barcode.IsChecksumEnabled = EnableChecksum.No;
    gen.GenerateBarCodeImage();
}
catch (Exception e)
{
    Console.WriteLine(e.Message);
}
```

### よくある問題と解決策
- **無効なパス** – ディレクトリが存在し、アプリケーションに書き込み権限があることを確認してください。  
- **サポートされていない文字** – Code 93 はフル ASCII をサポートしますが、制御文字はエラーの原因になることがあります。  
- **ライセンス未設定** – 有効なライセンスがない場合、ライブラリは評価モードで動作し、透かしが付くことがあります。

## よくある質問 (FAQ)

### Q: Aspose.BarCode for .NET のドキュメントはどこで見つけられますか？
A: ドキュメントは [Aspose.BarCode for .NET Documentation](https://reference.aspose.com/barcode/net/) で確認できます。

### Q: Aspose.BarCode for .NET はどこからダウンロードできますか？
A: ウェブサイトの [Aspose.BarCode for .NET Download](https://releases.aspose.com/barcode/net/) からダウンロードできます。

### Q: Aspose.BarCode for .NET の無料トライアルはありますか？
A: はい、[here](https://releases.aspose.com/) から Aspose.BarCode for .NET の無料トライアルを取得できます。

### Q: Aspose.BarCode for .NET のライセンスはどこで購入できますか？
A: 購入ページの [Aspose.BarCode for .NET Purchase](https://purchase.aspose.com/buy) からライセンスを購入できます。

### Q: Aspose.BarCode for .NET のサポートや質問はどこで受けられますか？
A: サポートやディスカッション用のコミュニティフォーラムは [Aspose.BarCode for .NET Support](https://forum.aspose.com/c/barcode/13) で利用できます。

---

**最終更新日:** 2026-02-25  
**テスト環境:** Aspose.BarCode 24.11 for .NET  
**作者:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}