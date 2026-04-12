---
date: 2026-04-12
description: Aspose.BarCode を使用して Java で空白バー付きの Code128 バーコードを作成する方法を学びましょう。このガイドでは、Java
  でバーコード画像を素早く生成する手順を示します。
keywords:
- create code128 barcode
- generate barcode java
- barcode generator java example
- java generate barcode image
linktitle: 空白バー付きバーコードの生成
second_title: Aspose.BarCode Java API
title: Javaで空白バー付きCode128バーコードを作成する方法
url: /ja/java/image-manipulation/generating-barcode-empty-bars/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Javaで空白バー付きCode128バーコードを作成する方法

## はじめに

Javaアプリケーションにバーコード生成機能を組み込むことは、在庫管理システム、チケットプラットフォーム、POSソリューションなど、さまざまな場面で頻繁に求められます。**Aspose.BarCode for Java** を使用すれば、数行のコードで **Code128バーコード** 画像を **作成** できます。このチュートリアルでは、空白（塗りつぶしなし）バーを持つバーコード画像を **生成** する手順を解説し、バーコードのビジュアルスタイルを自由にコントロールできるようにします。

## クイック回答
- **どのライブラリですか？** Aspose.BarCode for Java  
- **主なユースケースは？** カスタム UI デザイン向けに空白バー付き Code128 バーコードを作成  
- **前提条件は？** Java JDK 8+、Aspose.BarCode JAR、出力画像を保存するフォルダーへの書き込み権限  
- **実装にかかる時間は？** 基本例で 5‑10 分  
- **色のカスタマイズは可能ですか？** はい – API には豊富なスタイリングオプションがあります  

## Code128バーコードとは？

Code128 は、フル ASCII 文字セットをエンコードできる高密度の線形バーコードシンボロジーです。物流、出荷、小売などで広く使用され、英数字データをコンパクトに表現できます。デフォルトでは、Aspose.BarCode は Code128 のバーを実線の長方形として描画しますが、**FilledBars** プロパティを `false` に設定すると、空白（アウトライン）バーに変わり、ブランディングのデザインに役立ちます。

## なぜAspose.BarCode for Javaを使用するのか？

- **豊富な機能セット** – QR、DataMatrix、PDF417 など 50 種類以上のバーコードをサポート  
- **外部依存なし** – 単一 JAR で任意の Java ランタイム上で動作  
- **細かな制御** – バー幅、色、フォント、`FilledBars` プロパティなどを調整可能  
- **クロスプラットフォーム** – Windows、Linux、macOS でネイティブライブラリ不要で動作  

## 前提条件

開始する前に以下を用意してください。

1. **Java 開発環境** – JDK 8 以上がインストールされ、`JAVA_HOME` が設定されていること。  
2. **Aspose.BarCode for Java** – 最新の JAR を [ダウンロードページ](https://releases.aspose.com/barcode/java/) から取得。  
3. **ドキュメントディレクトリ** – 生成したバーコード画像を保存するローカルフォルダー。

## パッケージのインポート

Java プロジェクトで Aspose.BarCode を使用するために必要なクラスをインポートします。

```java
import java.io.IOException;
import com.aspose.barcode.BarCodeImageFormat;
import com.aspose.barcode.generation.BarcodeGenerator;
```

これらのインポートにより、バーコードジェネレータ、画像フォーマット列挙型、例外処理にアクセスできます。

## 手順 1: リソースディレクトリの設定

```java
// The path to the resource directory.
String dataDir = "Your Document Directory";
```

`"Your Document Directory"` を、前項で作成したフォルダーへの絶対パスに置き換えてください。ここに PNG ファイルが書き込まれます。

## 手順 2: Code128バーコードジェネレータインスタンスの作成

```java
// Create an instance of BarcodeGenerator and initialize it with CodeText and Symbology
BarcodeGenerator generator = new BarcodeGenerator(com.aspose.barcode.EncodeTypes.CODE_128, "TEXT");
```

ここでは **CODE_128** シンボロジーとサンプルテキスト `"TEXT"` を使用して `BarcodeGenerator` をインスタンス化しています。これは任意の文字列をエンコードできる **バーコードジェネレータ Java の例** です。

## 手順 3: FilledBarsプロパティをfalseに設定

```java
// Set the FilledBars property to false
generator.getParameters().getBarcode().setFilledBars(false);
```

`FilledBars` を `false` に設定することで、生成されるバーコードは実線ではなく空白バーとして表示され、目的のビジュアル効果が得られます。

## 手順 4: バーコード画像の保存

```java
// Save the resultant barcode image on disk
generator.save(dataDir + "barcodeWithEmptyBars.png", BarCodeImageFormat.PNG);
```

`save` メソッドは指定ディレクトリに PNG 形式でバーコードを書き出します。必要に応じて `BarCodeImageFormat.PNG` を `JPG`、`BMP`、`TIFF` などに変更可能です。

## 主な使用例

- **カスタムブランディング** – 空白バーに背景パターンやカラーを重ねることができる  
- **印刷用資産** – 請求書や出荷ラベルに組み込む高解像度 PNG を生成  
- **動的生成** – Web サービスやデスクトップアプリでリアルタイムにバーコードを作成  

## トラブルシューティングのヒント

- **パスが無効** – `dataDir` がファイル区切り文字（`/` または `\\`）で終わっているか、`File.separator` を使用して連結してください。  
- **ライセンスが必要** – 評価版はトライアルで動作しますが、本番環境ではフルライセンスが必要です。  
- **サポートされていない文字** – Code128 はフル ASCII をサポートします。Unicode 文字は別のシンボロジーに切り替えるまで使用しないでください。  

## 結論

これで **Aspose.BarCode for Java** を使用して、空白バー付きの **Code128バーコード** 画像を作成する方法を習得しました。このシンプルな手順により、デスクトップ在庫ツールやクラウドベース API など、さまざまな環境でカスタマイズ可能なバーコードグラフィックを迅速に生成できます。

## FAQ

### Aspose.BarCode はすべての Java 開発環境と互換性がありますか？
はい、Aspose.BarCode は Maven、Gradle、単体 JAR プロジェクトなど、あらゆる Java IDE やビルドシステムとシームレスに統合できるよう設計されています。

### 生成されたバーコードの外観をカスタマイズできますか？
もちろんです！`FilledBars` に加えて、色、バー幅、余白、さらには人が読めるテキストの追加も豊富な API で設定可能です。

### Aspose.BarCode のトライアル版は利用できますか？
はい、無料トライアルは [こちら](https://releases.aspose.com/) から取得できます。

### Aspose.BarCode のサポートはどこで受けられますか？
ご質問や支援が必要な場合は、[Aspose.BarCode フォーラム](https://forum.aspose.com/c/barcode/13)をご利用ください。

### Aspose.BarCode の詳細ドキュメントはどこにありますか？
包括的なドキュメントは [こちら](https://reference.aspose.com/barcode/java/) でご覧いただけます。

**追加の質問**

**Q: JPEG など別の形式でバーコード画像を生成するにはどうすればよいですか？**  
A: `save` の第2引数を `BarCodeImageFormat.JPEG` に変更してください。

**Q: ループ内で複数のバーコードを生成できますか？**  
A: はい – ループ内で新しい `BarcodeGenerator` をインスタンス化するか、同一インスタンスに新しい `CodeText` を設定して再利用できます。

---

**最終更新日:** 2026-04-12  
**テスト環境:** Aspose.BarCode for Java 24.11  
**作者:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}