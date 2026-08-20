---
date: 2026-06-09
description: Aspose.BarCode を使用して Java で Code128 バーコードを作成する方法を学びます。このステップバイステップ ガイドでは、Java
  でバーコードを生成し、カスタムテキストを設定し、バー幅を調整し、画像を保存する手順を示します。
keywords:
- create code128 barcode java
- how to generate barcode java
- java barcode generator example
linktitle: コードテキストの設定
schemas:
- author: Aspose
  dateModified: '2026-06-09'
  description: Learn how to create Code128 barcode Java using Aspose.BarCode. This
    step‑by‑step guide shows how to generate barcode Java, set custom text, adjust
    bar width, and save the image.
  headline: Create Code128 Barcode Java – Set Code Text using Aspose.BarCode
  type: TechArticle
- description: Learn how to create Code128 barcode Java using Aspose.BarCode. This
    step‑by‑step guide shows how to generate barcode Java, set custom text, adjust
    bar width, and save the image.
  name: Create Code128 Barcode Java – Set Code Text using Aspose.BarCode
  steps:
  - name: Create an Instance of `BarcodeGenerator`
    text: 'The `BarcodeGenerator` constructor takes two arguments: the barcode symbology
      (`CODE_128`) and the **custom code text** you want to encode, such as `"12345678"`.'
  - name: Adjust Barcode Width for Custom Barcode Text
    text: Set the `XDimension` property (bar width) to control how wide each bar appears.
      In this example we use `0.5` mm, a size that balances readability and label
      space for most applications.
  - name: Save the Barcode Image
    text: Call the `save` method, specifying the output path and image format (JPEG,
      PNG, SVG, etc.). The example saves the file as **`setCodeText.jpg`** in the
      project’s document folder.
  type: HowTo
- questions:
  - answer: Aspose.BarCode for Java.
    question: What library should I use?
  - answer: CODE_128.
    question: Which barcode type is demonstrated?
  - answer: Use the `BarcodeGenerator` constructor or the `setCodeText` method.
    question: How do I set custom barcode text?
  - answer: Yes—adjust `XDimension` (bar width) in millimetres.
    question: Can I change the bar width?
  - answer: A commercial license is required for non‑trial deployments.
    question: Do I need a license for production?
  type: FAQPage
second_title: Aspose.BarCode Java API
title: Aspose.BarCode を使用した Code128 バーコード（Java）の作成 – コードテキストの設定
url: /ja/java/text-and-styling/setting-code-text/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Code128 バーコード Java の作成 – Aspose.BarCode を使用したコードテキストの設定

このチュートリアルでは、Aspose.BarCode Java ライブラリを使用して **Code128 バーコード Java を作成**する方法を学びます。 在庫管理システムや文書追跡ソリューション、あるいはバーコードが必要な任意のアプリケーションを構築している場合でも、**Code128** バーコードのインスタンス化からコードテキストのカスタマイズ、バー幅の微調整まで、すべての手順を順を追って説明します。最後には、必要な場所に埋め込めるすぐに使用できる画像が手に入ります。

## クイック回答
- **どのライブラリを使用すべきですか？** Aspose.BarCode for Java.  
- **どのバーコードタイプがデモされていますか？** CODE_128.  
- **カスタムバーコードテキストはどう設定しますか？** Use the `BarcodeGenerator` constructor or the `setCodeText` method.  
- **バー幅を変更できますか？** Yes—adjust `XDimension` (bar width) in millimetres.  
- **本番環境でライセンスが必要ですか？** A commercial license is required for non‑trial deployments.

## Java で Code128 バーコードを作成する方法？

`BarcodeGenerator` に `CODE_128` シンボロジーと希望のテキストをロードし、`XDimension` でバー幅を設定してから `save` を呼び出して画像ファイルを書き出します。この 3 ステップのパターンにより、数秒で高品質なバーコードが生成され、Java 8+ のランタイム、Windows、Linux、macOS のいずれでも動作します。

## Java でバーコードを生成するための前提条件
- Java プログラミングの基本知識。  
- Java 開発環境 (JDK 8 以上)。  
- Aspose.BarCode for Java ライブラリ – **[here](https://releases.aspose.com/barcode/java/)** からダウンロードしてください。  
- お好みの IDE (IntelliJ IDEA、Eclipse など)。  

## パッケージのインポート

プロジェクトでクラスを使用できるように、必須の Aspose.BarCode 名前空間をインポートします。

## BarcodeGenerator クラスとは？

`BarcodeGenerator` は、メモリ内でバーコード画像を作成する Aspose.BarCode のコアクラスです。シンボロジー、コードテキスト、サイズ、色、その他のレンダリングオプションを設定するためのフルエント API を提供し、PNG、JPEG、SVG、PDF などの形式で結果をエクスポートできます。必要に応じてキャプション、余白、誤り訂正レベルもカスタマイズ可能です。

## バーコードジェネレーターチュートリアル: Code128 バーコードの作成

### 手順 1: `BarcodeGenerator` のインスタンスを作成

`BarcodeGenerator` コンストラクタは 2 つの引数を受け取ります: バーコードシンボロジー (`CODE_128`) と、エンコードしたい **カスタムコードテキスト**（例: `"12345678"`）。

```java
// The path to the documents directory.
String path = "Your Directory Path";
// The path to the resource directory.
String dataDir = "Your Document Directory";
BarcodeGenerator generator = new BarcodeGenerator(com.aspose.barcode.EncodeTypes.CODE_128, "12345678");
```

### 手順 2: カスタムバーコードテキスト用にバー幅を調整

`XDimension` プロパティ（バー幅）を設定して、各バーの幅を制御します。この例では `0.5` mm を使用しています。これは、ほとんどのアプリケーションで可読性とラベルスペースのバランスが取れたサイズです。

```java
generator.getParameters().getBarcode().getXDimension().setMillimeters(0.5f);
```

### 手順 3: バーコード画像を保存

`save` メソッドを呼び出し、出力パスと画像形式（JPEG、PNG、SVG など）を指定します。例では、プロジェクトの document フォルダーに **`setCodeText.jpg`** としてファイルを保存します。

```java
generator.save(dataDir + "setCodeText.jpg");
```

## なぜ Aspose.BarCode for Java を使用するのか？

Aspose.BarCode for Java は、プラットフォームを超えてバーコード生成を簡素化する包括的な機能セットを提供します。60 種類以上のシンボロジーをサポートし、高解像度のラスターおよびベクター出力を提供、バルク処理向けのパフォーマンス最適化も備えているため、エンタープライズ向けアプリケーションや既存の Java プロジェクトへのシームレスな統合に最適です。

- **広範なシンボロジーサポート** – Code128、QR、DataMatrix、PDF417 など、**60** 種類以上のバーコードタイプをサポート。  
- **高解像度レンダリング** – **2000 mm** 幅までの PNG、JPEG、SVG、PDF 画像を品質低下なしで生成。  
- **パフォーマンス重視** – 標準サーバーハードウェア上で、500 ページのバーコードバッチを **2 秒** 未満で処理。  
- **クロスプラットフォーム** – Windows、Linux、macOS と完全に互換性があり、任意の Java 8+ ランタイムで動作。  

## よくある問題と解決策

| 問題 | 解決策 |
|-------|----------|
| **バーコードがぼやけている** | 画像解像度を上げるか、ベクターフォーマット（SVG、PDF）でエクスポートしてください。 |
| **テキストが切り捨てられる** | `XDimension` と `BarHeight` を拡大して、シンボロジーに十分なスペースを確保してください。 |
| **ライセンスが適用されていない** | `Aspose.BarCode.lic` をプロジェクトルートに配置し、`License license = new License(); license.setLicense("Aspose.BarCode.lic");` でロードしてください。 |

## よくある質問

**Q:** *`CODE_128` と他の Code128 バリアントの違いは何ですか？*  
**A:** `CODE_128` は入力に基づいて最も効率的なエンコーディング（A、B、または C）を自動的に選択し、最適な密度と速度を提供します。

**Q:** *出力形式を JPEG ではなく PNG に変更できますか？*  
**A:** はい。`generator.save(dataDir + "setCodeText.png", com.aspose.barcode.BarcodeImageFormat.PNG);` を使用してください。

**Q:** *バーコードの下に人が読めるキャプションを追加できますか？*  
**A:** もちろんです。`generator.getParameters().getBarcode().getCaption().setTopMargin(5);` を設定し、`setText` でキャプションテキストを定義してください。

**Q:** *Aspose.BarCode は Unicode 文字をサポートしていますか？*  
**A:** サポートしています。UTF‑8 エンコードされたテキストを提供し、選択したシンボロジーが文字セットをサポートしていることを確認してください。

**Q:** *ループ内で複数のバーコードを生成するにはどうすればよいですか？*  
**A:** ループ内で新しい `BarcodeGenerator` をインスタンス化し、各イテレーションに固有のテキストを割り当て、異なるファイル名で `save` を呼び出してください。

---

**最終更新日:** 2026-06-09  
**テスト環境:** Aspose.BarCode 24.12 for Java  
**作者:** Aspose  

{{< blocks/products/products-backtop-button >}}

## 関連チュートリアル

- [Java でデータマトリックスバーコードを作成し、コードテキスト位置を設定](/barcode/java/text-and-styling/setting-code-text-location/)
- [Aspose.BarCode を使用して Java でバーコードテキストの色を設定する方法](/barcode/java/text-and-styling/setting-code-text-foreground-color/)
- [Java でバーコードを生成 – Aspose.BarCode で画像解像度を設定](/barcode/java/advanced-settings-and-optimization/setting-image-resolution-barcode/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

```java
import com.aspose.barcode.generation.BarcodeGenerator;
```