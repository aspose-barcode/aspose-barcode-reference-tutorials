---
date: 2025-12-22
description: Aspose.BarCode for Java を使用して、空白バーのあるバーコード画像の作成方法を学びましょう。このステップバイステップのバーコード生成例は、Java
  でバーコードを迅速に生成するのに役立ちます。
linktitle: Generating Barcode with Empty Bars
second_title: Aspose.BarCode Java API
title: Javaで空白バー付きのバーコード画像を作成する方法
url: /ja/java/image-manipulation/generating-barcode-empty-bars/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Javaで空白バーのバーコード画像を作成する方法

## Introduction

モダンな Java アプリケーションでは、**バーコード画像** ファイルをその場で作成できることは、在庫管理、チケットシステム、その他多くのビジネスシナリオで貴重な機能です。Aspose.BarCode for Java は、数行のコードで高品質なバーコードを生成できる強力かつ使いやすい API を提供します。本チュートリアルでは、空白（塗りつぶしなし）のバーを持つバーコードを作成する **ステップバイステップのバーコード** 作成プロセスを解説します。デザイン上、空洞の外観が必要な場合に最適です。

## Quick Answers
- **What does “empty bars” mean?** バーはデフォルトの実線塗りつぶしが行われず、空洞の外観になります。  
- **Which barcode type is used?** Code 128（広くサポートされている線形シンボロジー）。  
- **Do I need a license to try it?** 無料トライアルが利用可能です。製品版の使用にはライセンスが必要です。  
- **What output formats are supported?** PNG、JPEG、BMP、GIF、TIFF など多数。  
- **Is this compatible with all Java versions?** はい、Java 8 以降で動作します。

## What is create barcode image?
バーコード画像の作成とは、データ文字列をスキャナーが読み取れる視覚的表現に変換することです。生成された画像は PNG、JPEG などの一般的な形式で保存でき、PDF に埋め込んだり、ラベルに印刷したり、UI に表示したりできます。

## Why use Aspose.BarCode Java library?
- **Rich feature set** – Code 128、QR、DataMatrix など 50 種類以上のバーコードシンボロジーに対応。  
- **Fine‑grained control** – `FilledBars`、色、余白、画像サイズなどのプロパティを簡単に設定可能。  
- **No external dependencies** – 単一の JAR ファイルですべてが完結し、デプロイがシンプル。  
- **Comprehensive documentation** – サンプル、API リファレンス、フォーラムが充実しており、すぐに使い始められます。

## Prerequisites

バーコード生成の旅に出る前に、以下の前提条件を満たしていることを確認してください。

1. **Java Development Environment** – Java 8 以上がインストールされ、対応する IDE またはビルドツールが利用可能であること。  
2. **Aspose.BarCode for Java Library** – [download page](https://releases.aspose.com/barcode/java/) から Aspose.BarCode for Java ライブラリをダウンロードしてインストール。  
3. **Document Directory** – 生成したバーコード画像を保存するディレクトリをシステム上に作成。

## Import Packages

Java プロジェクトで Aspose.BarCode を使用するために、必要なパッケージをインポートします。

```java
import java.io.IOException;
import com.aspose.barcode.BarCodeImageFormat;
import com.aspose.barcode.generation.BarcodeGenerator;
```

## How to Create Barcode Image with Empty Bars

### Step 1: Set Up the Resource Directory

```java
// The path to the resource directory.
String dataDir = "Your Document Directory";
```

`"Your Document Directory"` を、出力ファイルを保存したい実際のパスに置き換えてください。

### Step 2: Create Barcode Generator Instance (Code128 Barcode Java)

```java
// Create an instance of BarcodeGenerator and initialize it with CodeText and Symbology
BarcodeGenerator generator = new BarcodeGenerator(com.aspose.barcode.EncodeTypes.CODE_128, "TEXT");
```

ここでは **Code 128** シンボロジーを使用しています。これは最も一般的な線形バーコードの一つで、**code128 barcode java** の典型的な例となります。

### Step 3: Set FilledBars Property to False

```java
// Set the FilledBars property to false
generator.getParameters().getBarcode().setFilledBars(false);
```

`FilledBars` を `false` に設定すると、Aspose.BarCode はバーを実線ではなく空洞（ホロウ）形状として描画します。

### Step 4: Save the Barcode Image

```java
// Save the resultant barcode image on disk
generator.save(dataDir + "barcodeWithEmptyBars.png", BarCodeImageFormat.PNG);
```

画像は PNG 形式で保存されますが、`BarCodeImageFormat` 列挙体を変更すれば JPEG、BMP など他のサポート形式でも出力可能です。

これらの手順を Java アプリケーションに組み込めば、Aspose.BarCode for Java を使用して空白バー付きの **バーコード画像** を簡単に作成できます。

## Conclusion

本チュートリアルでは、Java で空白バーの **バーコード画像** を **ステップバイステップ** で作成する方法を解説しました。直感的な API と豊富なカスタマイズオプションにより、Aspose.BarCode は信頼性の高い **java barcode library** を求める開発者にとって価値あるツールとなります。

## FAQs

### Is Aspose.BarCode compatible with all Java development environments?
はい、Aspose.BarCode はさまざまな Java 開発環境とシームレスに統合できるよう設計されています。

### Can I customize the appearance of the generated barcode?
もちろんです！Aspose.BarCode は多数のカスタマイズオプションを提供しており、用途に合わせてバーコードの外観を自由に調整できます。

### Is a trial version available for Aspose.BarCode?
はい、無料トライアルをご利用いただけます。詳細は [here](https://releases.aspose.com/) をご確認ください。

### How can I get support for Aspose.BarCode?
ご質問やサポートが必要な場合は、[Aspose.BarCode forum](https://forum.aspose.com/c/barcode/13) へお越しください。

### Where can I find detailed documentation for Aspose.BarCode?
包括的なドキュメントは [here](https://reference.aspose.com/barcode/java/) にあります。

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Last Updated:** 2025-12-22  
**Tested With:** Aspose.BarCode Java 24.11 (latest)  
**Author:** Aspose  

---