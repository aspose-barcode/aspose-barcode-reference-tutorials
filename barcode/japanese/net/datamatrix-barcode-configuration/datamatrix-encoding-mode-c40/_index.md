---
date: 2026-06-09
description: Aspose.BarCode を使用した C40 エンコーディングで DataMatrix バーコードを生成し PNG として保存する方法
  – .NET Core 用バーコード生成の完全ガイド。
keywords:
- how to generate datamatrix
- barcode generation .net core
- datamatrix c40 png
linktitle: DataMatrix エンコーディングモード (C40)
schemas:
- author: Aspose
  dateModified: '2026-06-09'
  description: Learn how to generate DataMatrix barcodes and save PNG using C40 encoding
    with Aspose.BarCode – full guide for .NET Core barcode generation.
  headline: How to Generate DataMatrix PNG with C40 using Aspose.BarCode
  type: TechArticle
- description: Learn how to generate DataMatrix barcodes and save PNG using C40 encoding
    with Aspose.BarCode – full guide for .NET Core barcode generation.
  name: How to Generate DataMatrix PNG with C40 using Aspose.BarCode
  steps:
  - name: Define the Directory Path
    text: Set the folder where the PNG image will be stored. Replace the placeholder
      with an actual path on your machine.
  - name: Set Up Barcode Generation
    text: Create a `BarcodeGenerator` instance, specify `EncodeTypes.DataMatrix`,
      and provide the data you want to encode.
  - name: Customize Barcode
    text: Configure the X‑dimension (pixel width of the modules) and switch the encoding
      mode to C40.
  - name: Save the Barcode Image
    text: Finally, save the generated barcode as a PNG file. This is the concrete
      answer to **how to save png** with Aspose.BarCode. When you run the program,
      you’ll find `DataMatrixEncodeModeC40.png` in the folder you specified, ready
      to be used in reports, labels, or web pages.
  type: HowTo
- questions:
  - answer: C40 is a compact alphanumeric encoding scheme for DataMatrix symbols,
      ideal for text that includes letters, numbers, and a limited set of special
      characters.
    question: What is DataMatrix Encoding Mode (C40)?
  - answer: You can find the documentation [here](https://reference.aspose.com/barcode/net/).
      It provides detailed guidance on all barcode types and encoding options.
    question: Where can I find the Aspose.BarCode for .NET documentation?
  - answer: Yes, the library supports a wide range of .NET versions, from .NET Framework
      4.5+ to .NET 6 and later.
    question: Is Aspose.BarCode for .NET compatible with all .NET versions?
  - answer: Yes, you can explore a free trial of Aspose.BarCode for .NET by visiting
      [this link](https://releases.aspose.com/). It allows you to test the library’s
      features and capabilities.
    question: Can I try Aspose.BarCode for .NET before purchasing?
  - answer: You can find a supportive community and access support for Aspose.BarCode
      for .NET on the [Aspose forum](https://forum.aspose.com/c/barcode/13).
    question: Where can I get support for Aspose.BarCode for .NET?
  type: FAQPage
second_title: Aspose.BarCode .NET API
title: Aspose.BarCode を使用して C40 で DataMatrix PNG を生成する方法
url: /ja/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-c40/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.BarCode for .NET を使用したマスターデータマトリックスエンコーディングモード (C40)

## はじめに

このチュートリアルでは、**C40 エンコーディングモード**を使用して Aspose.BarCode for .NET でデータマトリックスバーコードを生成し、PNG ファイルとして保存する方法を学びます。在庫管理システムや出荷ラベルジェネレータ、あるいはコンパクトで高密度なシンボルが必要なあらゆるソリューションにおいて、C40 をマスターすれば可読性を損なうことなく小さなシンボルを実現できます。環境設定から最終的な PNG の生成まで、すべての手順を順を追って解説するので、コードをすぐにプロジェクトに組み込めます。

## クイック回答
- **「how to generate datamatrix」とは何を指しますか？** プログラムで DataMatrix バーコード画像を作成することです。  
- **どのエンコーディングモードが対象ですか？** DataMatrix C40、効率的な英数字スキームです。  
- **ライセンスは必要ですか？** テストには無料トライアルで動作しますが、製品版には商用ライセンスが必要です。  
- **.NET Core で実行できますか？** はい、Aspose.BarCode は .NET Core、.NET 5、.NET 6 以降を完全にサポートしています。  
- **生成されるファイル形式は何ですか？** PNG – ロスレスでウェブに適した画像形式です。

## C40 エンコーディングで DataMatrix を生成する方法

データをロードし、ジェネレータを構成し、`Save` を呼び出すだけで完了です。`BarcodeGenerator` クラスがシンボル作成を担当し、`BarCodeImageFormat.Png` 列挙体が Aspose.BarCode に PNG ファイルとして書き出すよう指示します。`Save` は生成されたバーコード画像を指定されたファイルパスに選択した形式で保存します。この段落でエンドツーエンドの解決策を示した後、各コード行を詳しく見ていきます。

## DataMatrix エンコーディングモード (C40) とは？

`DataMatrixEncodeMode` は、Aspose.BarCode が DataMatrix シンボルに使用するエンコーディング方式を指定する列挙体です。`DataMatrixEncodeMode.C40` オプションは C40 英数字エンコーディングを選択し、文字、数字、および限定された句読点を少ないモジュールに詰め込むことで、全体のシンボルサイズを削減しつつ在庫テキストなどの可読性を維持します。この効率的な方式は、コンパクトに英数字データをエンコードする必要がある場合に最適です。

## .NET 用 Aspose.BarCode を使用する理由

Aspose.BarCode は **30 以上の構成パラメータ**（サイズ、誤り訂正レベル、エンコーディングモードなど）を提供し、**50 以上の画像およびバーコード形式**をサポートします。ライブラリは **.NET Framework 4.5+、.NET Core 2.0+、.NET 5/6+** 上で動作し、サーバー、デスクトップ、モバイルデバイスすべてで依存関係なしに生成できます。

## 前提条件

コードに入る前に、以下を用意してください。

1. **.NET 開発環境** – Visual Studio、Rider、または C# をサポートする任意の IDE。  
2. **Aspose.BarCode for .NET** – NuGet または公式インストーラでインストールします。詳細は [documentation](https://reference.aspose.com/barcode/net/) を参照してください。  
3. **基本的な C# の知識** – 名前空間、クラス、using 文に慣れている必要があります。  
4. **書き込み権限のあるフォルダー** – PNG を保存するローカルディレクトリ。

## 必要な名前空間のインポート

`BarcodeGenerator` クラスはあらゆるバーコード作成のエントリーポイントです。C# ソースファイルの先頭に必要な名前空間を追加して、生成 API にアクセスできるようにします。

```csharp
using Aspose.BarCode.Generation;
```

## ステップバイステップのバーコード生成

以下は **ステップバイステップのバーコード** ガイドです。各ステップは平易な言葉で説明し、プレースホルダーはそのまま残してコピー＆ペーストしやすくしています。

### 手順 1: ディレクトリパスの定義
PNG 画像を保存するフォルダーを設定します。プレースホルダーを実際のパスに置き換えてください。

```csharp
string path = "Your Directory Path";
```

### 手順 2: バーコード生成の設定
`BarcodeGenerator` インスタンスを作成し、`EncodeTypes.DataMatrix` を指定し、エンコードしたいデータを渡します。

```csharp
using (BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.DataMatrix, "ASPOSE.BARCODE"))
{
    // Additional steps go here
}
```

### 手順 3: バーコードのカスタマイズ
X ディメンション（モジュールのピクセル幅）を設定し、エンコーディングモードを C40 に切り替えます。

```csharp
gen.Parameters.Barcode.XDimension.Pixels = 6;
gen.Parameters.Barcode.DataMatrix.DataMatrixEncodeMode = DataMatrixEncodeMode.C40;
```

### 手順 4: バーコード画像の保存
最後に、生成したバーコードを PNG ファイルとして保存します。これが **Aspose.BarCode で png を保存する方法** の具体的な回答です。

```csharp
gen.Save($"{path}DataMatrixEncodeModeC40.png", BarCodeImageFormat.Png);
```

プログラムを実行すると、指定したフォルダーに `DataMatrixEncodeModeC40.png` が作成され、レポートやラベル、ウェブページで使用できる状態になります。

## よくある問題とヒント

- **無効なパス** – ディレクトリが存在し、書き込み権限があることを確認してください。そうでない場合、`gen.Save` が例外をスローします。  
- **エンコーディングモードが不正** – C40 セット外の文字をエンコードする必要がある場合は、`DataMatrixEncodeMode.Auto` など適切なモードに切り替えてください。  
- **画像サイズ** – `XDimension.Pixels` を調整して、可読性を損なわずに全体のバーコードサイズを増減できます。

## よくある質問

**Q: DataMatrix エンコーディングモード (C40) とは何ですか？**  
A: C40 は DataMatrix シンボル用のコンパクトな英数字エンコーディング方式で、文字、数字、限定された特殊文字を含むテキストに最適です。

**Q: Aspose.BarCode for .NET のドキュメントはどこで見つけられますか？**  
A: ドキュメントは [here](https://reference.aspose.com/barcode/net/) にあります。すべてのバーコードタイプとエンコーディングオプションに関する詳細なガイダンスが提供されています。

**Q: Aspose.BarCode for .NET はすべての .NET バージョンと互換性がありますか？**  
A: はい、ライブラリは .NET Framework 4.5+ から .NET 6 以降まで、幅広い .NET バージョンをサポートしています。

**Q: 購入前に Aspose.BarCode for .NET を試すことはできますか？**  
A: はい、[this link](https://releases.aspose.com/) から無料トライアルを利用できます。ライブラリの機能と性能をテストできます。

**Q: Aspose.BarCode for .NET のサポートはどこで受けられますか？**  
A: サポートは [Aspose forum](https://forum.aspose.com/c/barcode/13) で受けられ、コミュニティも活発です。

## 結論

この **ステップバイステップのバーコード** ガイドに従うことで、C40 エンコーディングモードを使用した Aspose.BarCode for .NET による **データマトリックスの生成方法** と PNG への保存方法を完全に習得できました。この手法により、バーコードの外観、サイズ、データ表現をフルコントロールでき、任意の .NET アプリケーションに高品質なバーコードを簡単に埋め込めます。

---

**最終更新日:** 2026-06-09  
**テスト対象:** Aspose.BarCode 24.11 for .NET  
**作者:** Aspose  

{{< blocks/products/products-backtop-button >}}

## 関連チュートリアル

- [Aspose.BarCode for .NET を使用したバイト単位の DataMatrix エンコーディング](/barcode/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-bytes/)
- [Aspose.BarCode for .NET を使用した ASCII のマスターデータマトリックスエンコーディング](/barcode/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-ascii/)
- [Aspose.BarCode for .NET を使用した DataMatrix バーコード (ECC 200) の生成方法](/barcode/net/datamatrix-barcode-configuration/datamatrix-ecc-200-configuration/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}