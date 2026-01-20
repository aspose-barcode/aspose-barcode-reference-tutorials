---
date: 2026-01-20
description: Aspose.BarCode for .NET を使用して、ASCII モードでバーコード画像をプログラム的に作成する方法を学びましょう。コードサンプル付きのステップバイステップガイド。
linktitle: DataMatrix Encoding Mode (ASCII)
second_title: Aspose.BarCode .NET API
title: プログラムでバーコード画像を作成する方法 – Aspose.BarCode for .NET を使用した DataMatrix ASCII エンコーディング
url: /ja/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-ascii/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.BarCode for .NET を使用した ASCII モードのマスターデータマトリックスエンコーディング

## Introduction

プログラムから **バーコード画像を作成** したい場合、ASCII モードの DataMatrix 形式は高速で信頼性の高い選択肢です。このチュートリアルでは、Aspose.BarCode for .NET を使用して、プロジェクトの設定からラベルや請求書、その他のドキュメントに埋め込める PNG ファイルの生成までの全工程を解説します。経験豊富な開発者でも、バーコード生成を始めたばかりの方でも、分かりやすく会話調の説明とすぐに実行できるコードが手に入ります。

## Quick Answers
- **必要なライブラリは？** Aspose.BarCode for .NET
- **ワンラインで画像を生成できるか？** はい、いくつかのパラメータを設定すれば可能です
- **例で使用している画像形式は？** PNG
- **開発時にライセンスは必要か？** テスト用の無料トライアルで動作しますが、本番環境ではライセンスが必要です
- **コードは .NET Core / .NET 5+ と互換性があるか？** もちろん

## What is DataMatrix ASCII Encoding?
DataMatrix は、限られたスペースに大量のデータをードはするため、製品 ID や短い URL などの英数字文字列に最適です。

## Why use Aspose.BarCode for .NET?
Aspose.BarCode は、バーコード生成に伴う複雑な数学処理を抽象化したハイレベル API を提供します。数行のプロパティ設定だけで **プログラムからバーコード画像を作成なフォーマットに対応し、サイズ・色・余白など多彩なカスタマイズが可能です。

## Prerequisites

1. **開発環境** – Visual Studio、Visual Studio Code、または .NET 対応の任意の IDE。  
2. **Aspose.BarCode for .NET** – ライブラリは [here](https://releases.aspose.com/barcode/net/) からダウンロードしてください。  
3. **基本的な C# の知識** – コードはシンプルですが、C# の構文に慣れているとスムーズです。

すべての準備が整ったので、実装に入りましょう。

## How to create barcode image programmatically using DataMatrix ASCII mode

### Import Namespaces

まず、必要な名前空間を追加してジェネレータクラスを利用できるようにします。

```csharp
using Aspose.BarCode.Generation;
```

### Step 1: Create a Directory

生成されたバーコードを保存するフォルダーを選択します。`"Your Directory Path"` をマシン上の絶対パスまたは相対パスに置き換えてください。

```csharp
string path = "Your Directory Path";
```

### Step 2: Encode Data in ASCII Mode

チュートリアルの核心です。`BarcodeGenerator` をインスタンス化し、DataMatrix 設定を構成、エンコーディングモードを ASCII に設定し、最後に画像を保存します。このスニペットは **プログラムからバーコード画像を作成** する方法を正確に示しています。

```csharp
System.Console.WriteLine("DataMatrixEncodeModeASCII:");

using (BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.DataMatrix, "Aspose"))
{
    // Set the X-dimension (size) of the barcode in pixels
    gen.Parameters.Barcode.XDimension.Pixels = 4;
    
    // Set the encoding mode to ASCII
    gen.Parameters.Barcode.DataMatrix.DataMatrixEncodeMode = DataMatrixEncodeMode.ASCII;
    
    // Save the barcode as a PNG image
    gen.Save($"{path}DataMatrixEncodeModeASCII.png", BarCodeImageFormat.Png);
}
```

プログラムを実行すると、指定したフォルダーに `DataMatrixEncodeModeASCII.png` という名前のファイルが作成されます。任意の画像ビューアで開き、生成されたバーコードを確認してください。

## Common Issues and Solutions

| Issue | Reason | Fix |
|-------|--------|-----|
| **File not saved** | `path` が存在しないフォルダーを指している、または書き込み権限がありません。 | フォルダーが存在すること、アプリケーションに書き込み権限があることを確認してください。 |
| **Barcode looks blurry** | データ量に対して X‑dimension が小さすぎます。 | `gen.Parameters |
 ASCII モードは 0‑127 の文字しかサポートしません。 | バイナリデータが必要な場合は別のエンコーディングモード（例: Base256）に切り替えてください。 |

## Frequently Asked Questions

**Q: Can I use Aspose.BarCode for .NET with other programming languages besides C#?**  
A: Asp**  
、Q: Can I customize the appearance of the generated barcode, such as its size and color?**  
A: はい、`Parameters.Barcode` プロパティを使用してサイズ、色、余白などを自由に調整できます。

**Q: Is there a free trial version of Aspose.BarCode for .NET available?**  
A: はい、[here](https://releases.aspose.com/) から無料トライアル版を試すことができます。

**Q: Where can I purchase a license for Aspose.BarCode for .NET?**  
A: ライセンスは Aspose のウェブサイトの [here](https://purchase.aspose.com/buy) から購入できます。

## Conclusion

本ガイドでは、Aspose.BarCode for .NET の DataMatrix ASCII エンコーディングを使用して **プログラムからバーコード画像を作成** する方法を示しました。数行のコードで必要なアプリケーション向けの高品質バーコードを生成できます。シナリオに合わせて他のエンコーディングモードや色、サイズを自由に試してみてください。

詳細が必要な場合は、公式ドキュメントの [Aspose.BarCode for .NET documentation](https://reference.aspose.com/barcode/net/) を参照するか、[Aspose.BarCode forum](https://forum.aspose.com/c/barcode/13) でコミュニティに参加してください。

---

**Last Updated:** 2026-01-20  
**Tested With:** Aspose.BarCode 24.11 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}