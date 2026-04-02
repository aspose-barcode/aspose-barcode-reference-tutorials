---
date: 2025-12-30
description: Aspose.BarCode を使用して Java でバーコードを生成する方法を学びましょう。このステップバイステップガイドでは、カスタムバーコードテキストの設定、幅の調整、画像の保存方法を示します。
linktitle: Setting Code Text
second_title: Aspose.BarCode Java API
title: 'Javaでバーコードを生成 - Aspose.BarCodeを使用してコードテキストを設定'
url: /ja/java/text-and-styling/setting-code-text/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Javaでバーコード生成: Aspose.BarCode を使用したコードテキストの設定

## はじめに

このチュートリアルでは、Aspose.BarCode Java ライブラリを使用して **Javaでバーコードを生成** する方法を学びます。在庫管理システムや文書追跡ソリューション、その他バーコードが必要なアプリケーションを構築する場合でも、本ガイドは **Code128** バーコードの作成からコードテキストのカスタマイズ、バー幅の調整まで、すべての手順を丁寧に案内します。最後まで実行すれば、任意の場所に埋め込める使用可能な画像が手に入ります。

## クイック回答
- **どのライブラリを使用すべきですか？** Aspose.BarCode for Java。  
- **デモで使用されているバーコードタイプは？** CODE_128。  
- **カスタムバーコードテキストはどう設定しますか？** `BarcodeGenerator` コンストラクタまたは `setCodeText` メソッドを使用します。  
- **バー幅は変更できますか？** はい、ミリメートル単位の `XDimension` で設定できます。  
- **本番環境でライセンスは必要ですか？** はい、商用ライセンスが必要です。

## 前提条件

チュートリアルに入る前に、以下が準備できていることを確認してください。

- Java プログラミングの基本的な理解。  
- 動作する Java 開発環境がインストール済み。  
- Aspose.BarCode for Java ライブラリ。**[こちら](https://releases.aspose.com/barcode/java/)** からダウンロードできます。  
- IntelliJ IDEA や Eclipse などのコードエディタ。  

## パッケージのインポート

Java プロジェクトに必要なパッケージをインポートします。これらのパッケージは Aspose.BarCode を使用するために必須です。

```java
import com.aspose.barcode.generation.BarcodeGenerator;
```

次に、Aspose.BarCode を使用した Java でのコードテキスト設定プロセスを見ていきます。以下の手順に従ってください。

## バーコードジェネレータチュートリアル: Code128 バーコードの作成

### 手順 1: `BarcodeGenerator` のインスタンスを作成

```java
// The path to the documents directory.
String path = "Your Directory Path";
// The path to the resource directory.
String dataDir = "Your Document Directory";
BarcodeGenerator generator = new BarcodeGenerator(com.aspose.barcode.EncodeTypes.CODE_128, "12345678");
```

ここでは、バーコードシンボロジー (**CODE_128**) と **カスタムバーコードテキスト** `"12345678"` を指定して `BarcodeGenerator` インスタンスを作成します。

### 手順 2: カスタムバーコードテキスト用にバー幅を調整

```java
generator.getParameters().getBarcode().getXDimension().setMillimeters(0.5f);
```

バーの幅を好みに合わせて調整します。この例では、**バー幅** を `0.5` mm に設定しており、ほとんどのラベルサイズでうまく機能します。

### 手順 3: バーコード画像を保存

```java
generator.save(dataDir + "setCodeText.jpg");
```

生成されたバーコード画像を指定ディレクトリに保存します。この場合、ファイルは **`setCodeText.jpg`** としてドキュメントディレクトリ内に保存されます。

## なぜ Aspose.BarCode for Java を使用するのか？

- **包括的な API** – Code128、QR、DataMatrix など 60 種類以上のバーコードシンボロジーをサポート。  
- **高品質なレンダリング** – PNG、JPEG、SVG、PDF 形式で鮮明な画像を生成。  
- **簡単なカスタマイズ** – テキスト、サイズ、色の変更や、数行のコードで人が読めるキャプションの追加が可能。  
- **クロスプラットフォーム** – Windows、Linux、macOS で Java 8 以上のランタイムと共に動作。

## よくある問題と解決策

| 問題 | 解決策 |
|------|--------|
| **バーコードがぼやけて見える** | 画像解像度を上げるか、ベクターフォーマット（SVG、PDF）でエクスポートしてください。 |
| **テキストが切り取られる** | `XDimension`（バー幅）と `BarHeight` が選択したシンボロジーに対して十分大きいことを確認してください。 |
| **ライセンスが適用されない** | ライセンスファイル (`Aspose.BarCode.lic`) をプロジェクトルートに配置し、`License license = new License(); license.setLicense("Aspose.BarCode.lic");` でロードしてください。 |

## 追加のよくある質問

**Q:** *`CODE_128` と他の Code128 バリアントの違いは何ですか？*  
**A:** `CODE_128` は標準シンボロジーで、入力テキストに基づいて最も効率的なエンコーディング（A、B、または C）を自動的に選択します。

**Q:** *出力形式を JPEG ではなく PNG に変更できますか？*  
**A:** もちろんです。`generator.save(dataDir + "setCodeText.png", com.aspose.barcode.BarcodeImageFormat.PNG);` を使用してください。

**Q:** *バーコードの下に人が読めるキャプションを追加できますか？*  
**A:** はい。`generator.getParameters().getBarcode().getCaption().setTopMargin(5);` で上余白を設定し、キャプションテキストを指定します。

**Q:** *Aspose.BarCode は Unicode 文字をサポートしていますか？*  
**A:** サポートしています。テキストを UTF‑8 で提供し、選択したシンボロジーが文字セットをサポートしていることを確認してください。

**Q:** *ループ内で複数のバーコードを生成するにはどうすればよいですか？*  
**A:** ループ内で新しい `BarcodeGenerator` をインスタンス化し、各イテレーションでテキストを設定し、固有のファイル名で `save` を呼び出します。

**最終更新日:** 2025-12-30  
**テスト環境:** Aspose.BarCode 24.12 for Java  
**作者:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}