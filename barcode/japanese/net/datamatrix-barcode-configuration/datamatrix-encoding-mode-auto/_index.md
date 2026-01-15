---
date: 2026-01-15
description: Aspose.BarCode for .NET を使用した、DataMatrix バーコードを C# で読み取り、バーコード画像を C#
  で生成するステップバイステップのチュートリアルガイド。
linktitle: DataMatrix Encoding Mode (Auto)
second_title: Aspose.BarCode .NET API
title: DataMatrixバーコードを読み取る C# – DataMatrixモード生成（自動）
url: /ja/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-auto/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# DataMatrixバーコードの読み取り C# – AutoモードでDataMatrixを生成

今日の急速に変化するデジタル社会では、**DataMatrixバーコードの読み取り C#** を迅速かつ確実に行うことが、在庫管理から機密文書の取り扱いまであらゆる場面で不可欠です。このチュートリアルでは、Aspose.BarCode for .NET を使用して *Auto* モードで DataMatrix バーコードを生成し、C# でそのバーコードを読み取る方法を順を追って説明します。**バーコードチュートリアルガイド** に従っている場合でも、単に実用的なコード例が必要な場合でも、最終的にプロジェクトに組み込める動作するソリューションが得られます。

## クイック回答
- **“Auto”モードは何をするのですか？** Aspose.BarCode がデータに最適なエンコーディング方式を自動的に選択します。  
- **どのライブラリが必要ですか？** Aspose.BarCode for .NET（無料トライアルあり）。  
- **同じアプリでバーコードを読み取れますか？** はい – `BarCodeReader` と `DecodeType.DataMatrix` を使用します。  
- **本番環境でライセンスが必要ですか？** 本番利用には商用ライセンスが必要です。  
- **サポートされている .NET バージョンは？** .NET Framework 4.5 以上、.NET Core 3.1 以上、.NET 5/6/7。

## DataMatrixバーコードの読み取り C# とは？
DataMatrixバーコードを C# で読み取ることは、黒と白のモジュールからなる二次元マトリックスを元のテキストやデータにデコードすることを意味します。Aspose.BarCode は低レベルの画像処理を抽象化したシンプルな API を提供し、ビジネスロジックに集中できるようにします。

## なぜ Aspose.BarCode を使用してバーコード画像 C# を生成するのか？
- **信頼性:** すべての DataMatrix 標準に対応し、最適なエンコーディングを自動的に選択します。  
- **柔軟性:** サイズ、ECI エンコーディング、画像フォーマットを完全に制御できます。  
- **クロラットフォーム:** .NET Framework、.NET Core、.NET 5 以降のアプリケーションで動作します。  

## 前提条件

1. **.NET 環境** – 最新の .NET ランタイムを [.NET website](https://dotnet.microsoft.com/download/dotnet) からインストールします。  
2. **Aspose.BarCode for .NET** – ライブラリを [website](https://releases.aspose.com/barcode/net/) からダウンロードします。  

## 名前空間のインポート

```csharp
using Aspose.BarCode.BarCodeRecognition;
using Aspose.BarCode.Generation;
using System;
using System.Drawing;
```

名前空間がインポートされたので、コードをステップバイステップで見ていきましょう。

## 手順 1: ディレクトリパスの設定

```csharp
string path = "Your Directory Path";
```

`"Your Directory Path"` を、生成された PNG（または他の形式）を保存したいフォルダーに置き換えてください。

## 手順 2: Auto モードで DataMatrix バーコードを作成

```csharp
using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.DataMatrix, "Aspose常に先を行く"))
{
    generator.Parameters.Barcode.XDimension.Pixels = 4;
    generator.Parameters.Barcode.DataMatrix.DataMatrixEncodeMode = DataMatrixEncodeMode.Auto;
    generator.Parameters.Barcode.DataMatrix.ECIEncoding = ECIEncodings.UTF8;
    Bitmap bitmap = generator.GenerateBarCodeImage();
}
```

`DataMatrixEncodeMode.Auto` 設定により、ライブラリが提供されたテキストに最適なエンコーディングを自動的に決定します。サンプルテキストは、**バーコード画像 C# を生成**したい任意の文字列に置き換えて構いません。

## 手順 3: バーコードを読み取る（DataMatrixバーコードの読み取り C#）

```csharp
using (BarCodeReader reader = new BarCodeReader(bitmap, DecodeType.DataMatrix))
{
    reader.ReadBarCodes();
    Console.WriteLine(reader.FoundBarCodes[0].CodeText);
}
```

このスニペットは、先ほど生成した画像をデコードし、元のテキストをコンソールに出力します。生成から読み取りまでのフルラウンドトリップを実演しています。

## よくある問題と解決策

| 問題 | 原因 | 対策 |
|------|------|------|
| **バーコードが検出されません** | 画像解像度が低すぎる | `XDimension.Pixels` を増やす（例: 6 に設定） |
| **文字化け** | ECI エンコーディングが間違っている | `ECIEncoding` をデータに合わせて設定する（UTF‑8、ASCII など）。 |
| **`ReadBarCodes` の例外** | 読み取り前に Bitmap が破棄された | 読み取りが終わるまで `Bitmap` インスタンスを保持する |

## よくある質問

**Q: DataMatrix エンコーディングモード「Auto」とは何ですか？**  
A: Aspose.BarCode が提供されたデータに対して最適なエンコーディング方式を自動的に選択できるようにし、**DataMatrix バーコードの生成方法** のプロセスを簡素化します。

**Q: 生成されたバーコードのサイズをカスタマイズできますか？**  
A: はい – `generator.Parameters.Barcode.XDimension.Pixels` を調整してモジュールサイズを変更できます。

**Q: Aspose.BarCode for .NET は商用利用に適していますか？**  
A: もちろんです。ライセンスは [website](https://purchase.aspose.com/buy) から購入してください。

**Q: 無料トライアルは利用できますか？**  
A: はい、[this link](https://releases.aspose.com/) から無料トライアルで Aspose.BarCode をお試しできます。

**Q: DataMatrix バーコードで利用できるエンコーディングオプションは何ですか？**  
A: Aspose.BarCode は UTF‑8、ASCII、その他の ECI エンコーディングをサポートしています。`ECIEncoding` で目的の値を設定してください。

## 結論

これで、**DataMatrixバーコードの読み取り C#**、Auto モードでのバーコード生成、結果の検証を行う、完全な本番対応サンプルが手に入りました。すべて Aspose.BarCode for .NET を使用しています。さまざまなテキスト、サイズ、ECI 設定を試して、特定のシナリオに合わせて調整してください。詳細なカスタマイズについては、公式 [documentation](https://reference.aspose.com/barcode/net/) を参照してください。

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**最終更新日:** 2026-01-15  
**テスト環境:** Aspose.BarCode 24.12 for .NET  
**作者:** Aspose