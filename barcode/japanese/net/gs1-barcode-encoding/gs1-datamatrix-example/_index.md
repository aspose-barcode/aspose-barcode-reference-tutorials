---
date: 2026-02-22
description: Aspose.BarCode for .NET を使用して C# でバーコード画像を作成し、GS1 DataMatrix バーコードを迅速かつ効率的に生成する方法を学びましょう。
linktitle: GS1 DataMatrix Example
second_title: Aspose.BarCode .NET API
title: C#でバーコード画像を作成 – GS1 DataMatrixの例
url: /ja/net/gs1-barcode-encoding/gs1-datamatrix-example/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# GS1 DataMatrix の例

.NET アプリケーションで **C# を使ってバーコード画像を作成する** 信頼性の高い方法をお探しなら、Aspose.BarCode for .NET がプロセスを簡素化します。この強力なライブラリは、GS1 DataMatrix を含む幅広いシンボル体系をサポートし、低レベルのバーコードの詳細ではなくビジネスロジックに集中できるクリーンな API を提供します。次の数分で、GS1 DataMatrix バーコードの生成、外観のカスタマイズ、画像ファイルとしての保存方法を示す、実践的なサンプルを詳しく解説します。

## クイック回答
- **例は何を生成しますか？** A GS1 DataMatrix barcode containing sample product data.  
- **どのライブラリが使用されていますか？** Aspose.BarCode for .NET.  
- **出力形式を変更できますか？** Yes, you can save as PNG, JPEG, BMP, etc.  
- **開発にライセンスは必要ですか？** A free trial works for testing; a commercial license is required for production.  
- **コードは .NET Core と互換性がありますか？** Absolutely – the same API works on .NET Framework and .NET Core/5/6.

## GS1 DataMatrix バーコードとは何ですか？
GS1 DataMatrixは、製品レベルの情報（GTIN、シリアル番号、その他のアプリケーション識別子など）をエンコードする2次元バーコードです。小売、医療、物流などの分野で、コンパクトで高密度なデータストレージとして広く利用されています。

## なぜ Aspose.BarCode を使用して barcode image C# を作成するのですか？
- **フル機能API** – GS1規格、エラー訂正、サイズ制御をサポート。
- **外部依存関係なし** – 純粋な.NETライブラリで、簡単に統合可能。
- **クロスプラットフォーム** – Windows、Linux、macOSで動作。
- **充実したドキュメント** – すぐに使い始められるよう、この例のようなサンプルコードも含まれています。

## 前提条件

チュートリアルを始める前に、以下の前提条件を満たしていることを確認してください。

1. **Aspose.BarCode for .NET** – Aspose.BarCode for .NETがインストールされている必要があります。まだインストールしていない場合は、[こちらからダウンロードできます](https://releases.aspose.com/barcode/net/)。

2. **開発環境** – システムに.NET開発環境（Visual Studio、VS Code、またはお好みのIDE）がセットアップされている必要があります。

前提条件が揃ったので、GS1 DataMatrixバーコードの生成を開始しましょう。

## 名前空間のインポート

まず、Aspose.BarCode for .NET を使用するために必要な名前空間をインポートします。これらの名前空間を使用することで、バーコード生成機能にアクセスできるようになります。

```csharp
using Aspose.BarCode;
using System;
```

## barcode image C# の作成方法 – ステップバイステップガイド

### ステップ 1: バーコードジェネレータの設定

まず、`BarcodeGenerator` インスタンスを作成し、エンコードするデータとともに **GS1 DataMatrix** シンボルを指定します。この例では、GS1 アプリケーション識別子形式に従う文字列 **"(01)12345678901231(21)ASPOSE(30)9876"** をエンコードします。

```csharp
// The path to the documents directory.
string path = "Your Directory Path";
System.Console.WriteLine("Gs1DataMatrixExample:");

BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.GS1DataMatrix, "(01)12345678901231(21)ASPOSE(30)9876");
```

*ヒント:* サンプルデータを、製品カタログに合わせて独自のGS1識別子に置き換えてください。

### ステップ 2: バーコードプロパティのカスタマイズ

`Parameters`オブジェクトを使用して、バーコードの外観をカスタマイズできます。ここでは、X軸（最小モジュールのサイズ）を8ピクセルに設定し、マトリックスサイズを36列×12行と定義しています。スキャン要件に合わせてこれらの値を調整してください。

```csharp
gen.Parameters.Barcode.XDimension.Pixels = 8;
gen.Parameters.Barcode.DataMatrix.Columns = 36;
gen.Parameters.Barcode.DataMatrix.Rows = 12;
```

*X寸法を調整する理由* X寸法を大きくすると、低解像度デバイスでもバーコードが読みやすくなります。一方、X寸法を小さくすると、画像サイズが小さくなります。

### ステップ 3: バーコード画像の保存

最後に、生成されたバーコードをディスクに保存します。この例ではPNG形式を使用していますが、Aspose.BarCodeでサポートされているJPEG、GIF、BMPなどの形式を選択することもできます。

```csharp
gen.Save($"{path}Gs1DataMatrixExample.png", BarCodeImageFormat.Png);
```

コードを実行すると、指定したフォルダに**Gs1DataMatrixExample.png**というファイルが作成され、ラベル、パッケージ、またはデジタルアプリケーションで使用できるようになります。

## 一般的な使用例

- **小売製品ラベル** – GTIN、ロット番号、有効期限をエンコードします。
- **医薬品追跡** – GS1準拠データで規制要件を満たします。
- **倉庫物流** – 保管場所と在庫情報をコンパクトに保存します。 

## トラブルシューティングとヒント

- **データ形式が正しくありません** – 文字列がGS1アプリケーション識別子の構文に従っていることを確認してください。そうでない場合、バーコードがスキャンできない可能性があります。
- **画像サイズの問題** – 生成された画像がぼやけている場合は、`XDimension.Pixels`の値を増やしてください。
- **ライセンスエラー** – 試用版ライセンスは評価には使用できますが、本番環境での導入にはフルライセンスが必要です。

## 追加 FAQ (AI 最適化)

**Q: GS1フォーマットを使用せずにC#でDataMatrixバーコードを生成するにはどうすればよいですか？** 
A: `EncodeTypes.GS1DataMatrix`の代わりに`EncodeTypes.DataMatrix`を使用し、プレーンなデータ文字列を`BarcodeGenerator`に渡してください。

**Q: バーコードの色をプログラムで変更できますか？** 
A: はい、`gen.Parameters.Barcode.ForeColor`と`gen.Parameters.Barcode.BackColor`を設定することで、前景色と背景色をカスタマイズできます。

**Q: 生成したバーコードをPDFに直接埋め込むことはできますか？** 
A: はい、可能です。バーコードを`System.Drawing.Image`として取得し、Aspose.PDFなどのPDFライブラリを使用してPDFに追加してください。


**Q: サポートされている.NETバージョンは？** 
A: Aspose.BarCode for .NETは、.NET Framework 4.5以降、.NET Core 3.1以降、.NET 5、.NET 6以降をサポートしています。

**Q: 小さなラベルのスキャン精度を向上させるにはどうすればよいですか？** 
A: X軸の寸法を大きくし、静止領域（`gen.Parameters.Barcode.Margin`）を追加し、バーコードと背景のコントラストを十分に確保してください。


## 結論

このチュートリアルでは、Aspose.BarCode for .NETを使用してGS1 DataMatrixバーコードを生成する**C#によるバーコード画像の作成**方法について説明しました。わずか数行のコードで、小売ソリューション、医療システム、物流プラットフォームなど、あらゆるアプリケーションに高品質のバーコードを組み込むことができます。ライブラリをさらに詳しく調べて、その他のシンボル体系、高度なレンダリングオプション、統合シナリオをご確認ください。


詳細情報および詳細なドキュメントについては、[Aspose.BarCode for .NET のドキュメント](https://reference.aspose.com/barcode/net/) を参照してください。

---

**最終更新日:** 2026-02-22  
**テスト環境:** Aspose.BarCode for .NET (latest version)  
**作者:** Aspose  

---

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
