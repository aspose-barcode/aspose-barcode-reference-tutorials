---
date: 2026-02-17
description: Aspose Barcode Java の使い方を学び、バーコード画像を作成し、CODABAR の開始・終了シンボルを設定し、透かしのない
  PNG ファイルを生成します。
linktitle: Setting Start and Stop Symbols
second_title: Aspose.BarCode Java API
title: Aspose Barcode Java – 開始/停止シンボル付きバーコード画像の作成
url: /ja/java/barcode-configuration/setting-start-stop-symbols/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose Barcode Java – 開始/停止シンボル付きバーコード画像の作成

## Introduction

この包括的なチュートリアルでは、**Aspose Barcode Java** を使用して **barcode image java** ファイルを **作成**し、Codabar バーコードの **シンボル設定方法** を学びます。POS システム、物流アプリケーション、あるいは信頼性の高いバーコード生成が必要なあらゆるソリューションを構築する場合でも、開始シンボルと停止シンボルをカスタマイズすることでバーコード形式を完全にコントロールできます。各ステップを順に解説し、設定が重要な理由を説明し、トライアル透かしなしで使用可能な PNG 画像を生成する方法を示します。

## Quick Answers
- **Javaでバーコード画像を生成するライブラリは何ですか？** Aspose.BarCode for Java.  
- **開始/停止シンボルをカスタマイズできますか？** はい、`setCodabarStartSymbol` と `setCodabarStopSymbol` を使用します。  
- **この例で使用されているバーコードタイプは何ですか？** CODABAR.  
- **本番環境でライセンスが必要ですか？** トライアル以外の使用には商用ライセンスが必要です。  
- **生成される出力形式は何ですか？** ディスクに保存される PNG 画像。

## What is Aspose Barcode Java?

Aspose Barcode Java は、依存関係のない強力なライブラリで、プログラムから幅広いバーコードシンボロジーを生成できます。低レベルのエンコードロジックを抽象化するため、ビジネスロジックに集中しながら、業界標準に準拠した出力を確保できます。

## Why Use Aspose Barcode Java for Barcode Generation Without Watermark?

- **本番環境で透かしなし** – 有効なライセンスを適用すれば画像はクリーンです。  
- **豊富なシンボロジーサポート** – CODABAR などのクラシック 1D コードから QR や DataMatrix といった 2D コードまで対応。  
- **細かな制御** – 開始/停止シンボル、色、サイズの設定や、Web アプリ向けにストリームへ直接画像を生成可能。  
- **クロスプラットフォーム** – Android でも手動で依存関係を処理すれば動作します。

## Prerequisites

開始する前に以下を用意してください：

1. **Java Development Kit (JDK)** – 最新の JDK を [Oracle](https://www.oracle.com/java/technologies/javase-downloads.html) からインストール。  
2. **Aspose.BarCode for Java library** – [download link](https://releases.aspose.com/barcode/java/) からダウンロード。

これらが揃っていれば、**barcode image java** を問題なく生成できます。

## Import Packages

Java プロジェクトで Aspose.BarCode を使用するために必要なクラスをインポートします：

```java
// Import Aspose.BarCode classes
import com.aspose.barcode.CodabarSymbol;
import com.aspose.barcode.generation.BarcodeGenerator;
```

## Step‑by‑Step Guide

### Step 1: Define the Document Directory

```java
// The path to the resource directory.
String dataDir = "Your Document Directory";
```

`"Your Document Directory"` を、バーコード画像を保存したい絶対パスまたは相対パスに置き換えてください。パスは適切なファイル区切り文字（`/` または `\`）で終えるか、`Paths.get` を使用してプラットフォーム非依存に扱うことを忘れずに。

### Step 2: Create Barcode Generator Instance

```java
// Create instance of BarcodeGenerator, specify codetext and symbology in the constructor
BarcodeGenerator generator = new BarcodeGenerator(com.aspose.barcode.EncodeTypes.CODABAR, "12345678");
```

ここでは **CODABAR** シンボロジーとデータ文字列 `"12345678"` を使用するよう Aspose.BarCode に指示しています。

### Step 3: Set Codabar Start Symbol

```java
// Set the Codabar start symbol to A
generator.getParameters().getBarcode().getCodabar().setCodabarStartSymbol(CodabarSymbol.A);
```

`setCodabarStartSymbol` メソッドで開始文字の **バーコードシンボル** を設定できます。この例では `A` を選択しています。

### Step 4: Set Codabar Stop Symbol

```java
// Set the Codabar stop symbol to D
generator.getParameters().getBarcode().getCodabar().setCodabarStopSymbol(CodabarSymbol.D);
```

同様に、`setCodabarStopSymbol` で停止文字を定義します。`D` を使用すると、多くのレガシーシステムで要求される CODABAR 形式が完成します。

### Step 5: Save the Generated Image

```java
// Save the image to disk in PNG format
generator.save(dataDir + "startAndStopSymbols.png");
```

`save` 呼び出しにより、先ほど指定したディレクトリに **startAndStopSymbols.png** という名前の PNG ファイルが書き込まれます。

## Common Pitfalls & Tips

- **ディレクトリパスが正しくない** – `dataDir` がファイル区切り文字（`/` または `\`）で終わっているか、`Paths.get` で連結しているか確認してください。  
- **サポート外の開始/停止シンボル** – CODABAR は開始/停止シンボルとして `A`, `B`, `C`, `D` のみをサポートします。その他の値を使用すると例外がスローされます。  
- **ライセンスが適用されていない** – トライアルモードでは生成画像に透かしが入ります。本番環境で **barcode generation without watermark** を実現するには、ライセンスを適用してください。

## Frequently Asked Questions

### Can I use Aspose.BarCode for Java in a commercial project?
はい、商用プロジェクトで使用できます。商用ライセンスは [here](https://purchase.aspose.com/buy) から購入してください。

### Is there a free trial available?
はい、無料トライアル版は [here](https://releases.aspose.com/) から入手可能です。

### How can I get support for Aspose.BarCode for Java?
サポートや質問は Aspose.BarCode フォーラム [here](https://forum.aspose.com/c/barcode/13) で受け付けています。

### How do I obtain a temporary license?
必要に応じて、臨時ライセンスは [here](https://purchase.aspose.com/temporary-license/) から取得できます。

### Are there more barcode symbologies supported by Aspose.BarCode for Java?
はい、Aspose.BarCode は多数のバーコードシンボロジーをサポートしています。完全な一覧はドキュメントをご参照ください。

## Additional Q&A (AI‑Friendly)

**Q:** PNG 以外にエクスポートできる画像形式はありますか？  
**A:** Aspose.BarCode は PNG、JPEG、BMP、GIF、TIFF をサポートしています。`save` メソッドで適切な拡張子を指定してください。

**Q:** ディスクに書き込まずにメモリ上でバーコード画像を生成できますか？  
**A:** はい、`generator.save(OutputStream)` を呼び出すことでストリームへ直接書き込めます。Web 応答に最適です。

**Q:** ライブラリは Android で動作しますか？  
**A:** Java バージョンは Android と互換性がありますが、必要な依存関係を手動で追加する必要があります。

## Conclusion

これで **barcode image java** ファイルの作成方法と、**Aspose Barcode Java** を使用した Codabar バーコードの **シンボル設定** 方法を習得しました。この手法により、業界固有のバーコード仕様に柔軟に対応しつつ、コードをクリーンで保守しやすく保てます。色の変更やヒューマンリーダブルテキストの追加、他のシンボロジーへの切り替えなど、さらなるカスタマイズは公式 API ドキュメント [documentation](https://reference.aspose.com/barcode/java/) を参照してください。

---

**Last Updated:** 2026-02-17  
**Tested With:** Aspose.BarCode for Java 24.12  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}