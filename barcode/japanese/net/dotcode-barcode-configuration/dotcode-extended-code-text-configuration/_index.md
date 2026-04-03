---
date: 2026-01-27
description: Aspose.BarCode for .NET を使用して DotCode の拡張コードテキストを作成する方法を学びましょう – 拡張コードテキスト付き
  DotCode バーコードを生成するためのステップバイステップガイドです。
linktitle: DotCode Extended Code Text Configuration
second_title: Aspose.BarCode .NET API
title: Aspose.BarCode for .NET を使用してドットコードの拡張コードテキストを作成する方法
url: /ja/net/dotcode-barcode-configuration/dotcode-extended-code-text-configuration/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.BarCode for .NET を使用して DotCode 拡張コードテキストを作成する方法

## はじめに

バーコードの生成と管理の領域において、Aspose.BarCode for .NET は多用途で効率的なソリューションとして際立っています。製品、在庫、またはその他のアプリケーション向けにバーコードを生成する必要がある場合でも、Aspose.BarCode for .NET が対応します。この包括的なチュートリアルでは、**create dotcode extended codetext** を作成し、この機能が現代のデータリッチな環境でなぜ重要かを探ります。DotCode はテキストデータとバイナリデータの両方をエンコードできる二次元マトリックスバーコードで、さまざまな業界で有用なツールです。

## クイック回答
- **“create dotcode extended codetext” とは何ですか？** それは、FNC1、ECICodetext、プレーンテキスト、シンボルセパレータを単一の拡張ペイロードに含む DotCode バーコードを構築することを意味します。  
- **どのライブラリが必要ですか？** Aspose.BarCode for .NET。  
- **ライセンスは必要ですか？** 評価用には一時ライセンスで動作しますが、本番環境ではフルライセンスが必要です。  
- **対応している .NET バージョンは？** .NET Framework 4.5 以上、.NET Core 3.1 以上、.NET 5/6/7 以上。  
- **実装にどれくらい時間がかかりますか？** 基本的な例で約 10〜15 分です。

## DotCode 拡張コードテキストの作成方法

以下は、拡張コードテキストを構築し、バーコード画像をレンダリングする手順を簡潔に示したステップバイステップの walkthrough です。

## 前提条件

ステップバイステップのガイドに入る前に、効果的に進めるために以下の前提条件を整えてください。

1. Aspose.BarCode for .NET: Aspose.BarCode for .NET ライブラリがインストールされ、使用できることを確認してください。まだの場合は、[Aspose.BarCode for .NET ドキュメント](https://reference.aspose.com/barcode/net/) からダウンロードできます。  
2. 開発環境: システムに Visual Studio などの .NET 開発環境がインストールされていることが望ましいです。

これらの前提条件が整ったら、DotCode 拡張コードテキストの生成に進みます。

## 名前空間のインポート

まず、Aspose.BarCode ライブラリの必要な機能にアクセスできるように、.NET プロジェクトに必要な名前空間をインポートする必要があります。以下のように行います。

```csharp
using Aspose.BarCode.Generation;
```

前提条件が整ったので、DotCode 拡張コードテキスト生成プロセスをステップバイステップで分解していきましょう。

## ステップ 1: ディレクトリパスの定義

このステップでは、生成した DotCode 拡張コードテキスト画像を保存するディレクトリパスを指定する必要があります。

```csharp
string path = "Your Directory Path";
```

`"Your Directory Path"` をシステム上の実際のパスに置き換えてください。

## ステップ 2: DotCode 拡張コードテキストの作成

DotCode 拡張コードテキストを作成するには、以下のサブステップに従ってください。

### 2.1 FNC1 フォーマット識別子の追加

FNC1 フォーマット識別子は、新しいデータフィールドの開始を示すために使用されます。DotCode 拡張コードテキストの重要な部分です。

```csharp
DotCodeExtCodetextBuilder textBuilder = new DotCodeExtCodetextBuilder();
textBuilder.AddFNC1FormatIdentifier();
```

### 2.2 ECICodetext の追加

ECICodetext は、特殊文字や国際文字列をエンコードできる領域です。この例では、UTF‑8 エンコーディングを使用して `"犬Right狗"` をエンコードしています。

```csharp
textBuilder.AddECICodetext(ECIEncodings.UTF8, "犬Right狗");
```

### 2.3 プレーン Codetext の追加

DotCode 拡張コードテキストにプレーンテキストを追加することもできます。ここでは `"Plain text"` を追加しています。

```csharp
textBuilder.AddPlainCodetext("Plain text");
```

### 2.4 FNC3 シンボルセパレータの追加

FNC3 シンボルセパレータは、コードの異なるセクションを区切るために使用されます。

```csharp
textBuilder.AddFNC3SymbolSeparator();
```

### 2.5 FNC3 リーダー初期化の追加

このステップでは、FNC3 リーダー初期化情報を追加します。

```csharp
textBuilder.AddFNC3ReaderInitialization();
```

### 2.6 コードテキストの生成

`textBuilder` オブジェクトの `GetExtendedCodetext` メソッドを呼び出して、DotCode 拡張コードテキストを生成します。

```csharp
string codetext = textBuilder.GetExtendedCodetext();
```

## ステップ 3: DotCode 画像の生成

DotCode 拡張コードテキストを画像として生成するには、以下のサブステップに従います。

#### 4.1 バーコードジェネレータの初期化

適切なパラメータで `BarcodeGenerator` を初期化します。この場合、`EncodeTypes.DotCode` と生成したコードテキストを使用します。

```csharp
using (BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.DotCode, codetext))
{
    // Set the X-dimension for the barcode (adjust as needed).
    gen.Parameters.Barcode.XDimension.Pixels = 10;

    // Set the DotCode encoding mode to ExtendedCodetext.
    gen.Parameters.Barcode.DotCode.DotCodeEncodeMode = DotCodeEncodeMode.ExtendedCodetext;

    // Save the generated barcode image.
    gen.Save($"{path}DotCodeExtendedCodetext.png", BarCodeImageFormat.Png);
}
```

以上です！Aspose.BarCode for .NET を使用して DotCode 拡張コードテキストを正常に生成できました。

## 結論

Aspose.BarCode for .NET はバーコード生成をシンプルにする強力なツールです。本チュートリアルでは、特に多言語や特殊文字エンコーディングが必要とされる業界で重要な **create dotcode extended codetext** の作成方法に焦点を当てました。上記の手順に従うことで、目的に合わせた DotCode 拡張コードテキストを簡単に作成できます。

さらにガイダンスが必要な場合や質問がある場合は、[Aspose.BarCode for .NET ドキュメント](https://reference.aspose.com/barcode/net/) をご覧いただくか、[Aspose.BarCode サポートフォーラム](https://forum.aspose.com/c/barcode/13) でコミュニティと交流してください。

## FAQ

### Q1: DotCode は何に使用されますか？

**A1:** DotCode はテキストデータとバイナリデータの両方をエンコードするために使用され、医療や物流などの業界で追跡やデータエンコード目的で一般的に利用されています。

### Q2: DotCode バーコードの外観をカスタマイズできますか？

**A2:** はい。Aspose.BarCode for .NET はサイズやエンコーディングモードなど、DotCode バーコードの外観をカスタマイズするオプションを提供しています。

### Q3: Aspose.BarCode for .NET はさまざまな .NET フレームワークと互換性がありますか？

**A3:** はい。Aspose.BarCode for .NET は幅広い .NET フレームワークに対応しており、柔軟性と統合の容易さを実現しています。

### Q4: Aspose.BarCode for .NET の一時ライセンスはどのように取得しますか？

**A4:** 評価およびテスト目的で、[Aspose のウェブサイト](https://purchase.aspose.com/temporary-license/) から一時ライセンスを取得できます。

### Q5: Aspose.BarCode for .NET はエンタープライズレベルのバーコード生成に適していますか？

**A5:** もちろんです。Aspose.BarCode for .NET は小規模からエンタープライズレベルまでのバーコード生成ニーズに対応できるよう設計されており、スケーラビリティと信頼性を提供します。

## よくある質問

**Q: 生成したバーコードをモバイルアプリで使用できますか？**  
**A:** はい。ジェネレータが生成する PNG 画像は iOS、Android、または任意のクロスプラットフォームモバイルアプリに埋め込むことができます。

**Q: テキストではなくバイナリデータをエンコードしたい場合はどうすればよいですか？**  
**A:** `AddECICodetext` メソッドに適切な `ECIEncodings`（例: `ECIEncodings.Base64`）を指定して、バイナリペイロードを埋め込んでください。

**Q: 可読性に影響を与えずにバーコードのサイズを変更するには？**  
**A:** `XDimension.Pixels` プロパティを調整します。値を大きくするとモジュールサイズが増加し、値を小さくするとバーコードがコンパクトになります。

**Q: バーコードの周囲に静かな領域（quiet zone）を追加できますか？**  
**A:** はい。`gen.Parameters.Barcode.Margin` を設定して、ピクセル単位で希望の quiet zone を定義できます。

**Q: ライブラリは .NET 8 をサポートしていますか？**  
**A:** 最新の Aspose.BarCode リリースは .NET 8 と互換性があります。適切な NuGet パッケージバージョンを参照してください。

---

**最終更新日:** 2026-01-27  
**テスト環境:** Aspose.BarCode 24.12 for .NET  
**作者:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}