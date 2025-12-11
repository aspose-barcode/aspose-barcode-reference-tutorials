---
date: 2025-12-10
description: Aspose.BarCode を使用して Java で単一の画像にバーコードを生成する方法を学びます。このガイドでは、Aspose バーコード
  Java の統合と複数のバーコード生成について説明します。
linktitle: Generating Multiple Barcodes on a Single Image
second_title: Aspose.BarCode Java API
title: Javaで単一画像にバーコードを生成する方法
url: /ja/java/advanced-settings-and-optimization/generating-multiple-barcodes-single-image/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Java と Aspose.BarCode を使用した単一画像への複数バーコード生成

## はじめに

Java アプリケーションで **バーコードの生成方法** を探しているなら、ここが最適です。Aspose.BarCode for Java を使用すれば、数行のコードで複数の異なるバーコードタイプを1つの画像に配置できます。このチュートリアルでは、プロジェクトの設定から結合画像の保存までの全工程を順を追って説明するので、すぐに自分のソリューションでバーコード生成を利用できます。

## クイック回答
- **どのライブラリを使用すべきですか？** Aspose.BarCode for Java は最も完全なシンボロジーセットを提供します。  
- **異なるバーコードタイプを同時に生成できますか？** はい、CODE_39、QR、AZTEC などを単一のキャンバス上で混在させることができます。  
- **開発にライセンスは必要ですか？** テスト用には無料トライアルが利用でき、商用環境では商用ライセンスが必要です。  
- **対応している Java バージョンは？** Java 8 以降すべて対応しています。  
- **出力形式は設定可能ですか？** 結合画像を PNG、JPEG、BMP などでエクスポートできます。

## Java における「バーコード生成方法」とは？

バーコードの生成とは、データ文字列をスキャナが読み取れる視覚的パターンに変換することです。Aspose.BarCode はエンコード、レンダリング、画像作成の各工程を自動で処理するため、低レベルの画像処理に時間を取られず、ビジネスロジックに集中できます。

## なぜ Aspose.BarCode for Java のバーコード生成を使用するのか？

- **幅広いシンボロジーサポート** – 従来の線形コードから最新の 2 次元マトリックスまで。  
- **高品質なレンダリング** – アンチエイリアス出力で、どのデバイスでも美しく表示されます。  
- **シンプルな API** – 数回のメソッド呼び出しでバーコードの作成、カスタマイズ、結合が可能です。  
- **外部依存なし** – ネイティブライブラリ不要で、JVM 上ですべて動作します。

## 前提条件

チュートリアルに入る前に、以下の前提条件が揃っていることを確認してください：

- Java プログラミングの基本的な理解。  
- システムに Java Development Kit (JDK) がインストールされていること。  
- Aspose.BarCode for Java ライブラリをダウンロードして設定済みであること。ダウンロードは[こちら](https://releases.aspose.com/barcode/java/)から。  
- Eclipse や IntelliJ IDEA などの統合開発環境 (IDE)。

## 名前空間のインポート

Java プロジェクトで Aspose.BarCode の機能にアクセスするために必要な名前空間をインポートします。Java クラスの冒頭に以下のインポート文を追加してください：

```java
import java.awt.Color;
import java.awt.Graphics;
import java.awt.image.BufferedImage;
import java.io.File;
import java.util.ArrayList;
import java.util.HashMap;

import javax.imageio.ImageIO;

import com.aspose.barcode.BaseEncodeType;
import com.aspose.barcode.EncodeTypes;


import com.aspose.barcode.generation.BarcodeGenerator;
```

## ステップ 1: リソースディレクトリの設定

生成されたバーコードを保存するリソースディレクトリへのパスを定義します。このディレクトリはバーコード画像の整理・管理に重要です。

```java
// The path to the resource directory.
String dataDir = Utils.getDataDir(GenerateMultipleBarcodesOnASingleImage.class)
        + "BarcodeReader/advanced_features/";
```

## ステップ 2: バーコードコレクションの作成

`HashMap` を初期化してバーコードデータを格納します。コレクション内の各エントリは、対応するエンコードタイプを持つバーコードを表します。

```java
HashMap<String, EncodeTypes> collection = new HashMap<>();
collection.put("ONE123", EncodeTypes.CODE_39_STANDARD);
collection.put("Process Collection", EncodeTypes.DATA_MATRIX);
collection.put("Dictionary Collection", EncodeTypes.QR);
collection.put("X06712AT", EncodeTypes.CODE_128);
collection.put("979026000043", EncodeTypes.EAN_13);
collection.put("Aztec BarCode", EncodeTypes.AZTEC);
```

## ステップ 3: バーコード画像の生成

コレクションを反復処理し、Aspose.BarCode ライブラリを使用してバーコード画像を生成します。生成した画像は `ArrayList` に格納し、後続の処理に備えます。

```java
ArrayList<BufferedImage> images = new ArrayList<>();
for (Object key : collection.keySet()) {
    BarcodeGenerator bb = new BarcodeGenerator((BaseEncodeType) collection.get(key));
    bb.setCodeText((String) key);
    images.add(bb.generateBarCodeImage());
}
```

## ステップ 4: 結合画像の作成

バーコード画像の最大幅と総高さを算出します。`BufferedImage` を作成し、個々のバーコード画像を単一の出力画像に結合します。

```java
int maxWidth = 0;
int sumHeight = 0;
for (BufferedImage bmp : images) {
    sumHeight += bmp.getHeight();
    if (maxWidth < bmp.getWidth())
        maxWidth = bmp.getWidth();
}

int offset = 10;
BufferedImage resultBitmap = new BufferedImage(maxWidth + offset * 2, sumHeight + offset * images.size(),
        BufferedImage.TYPE_INT_ARGB);
Graphics g = resultBitmap.getGraphics();
g.setColor(Color.white);
g.fillRect(0, 0, resultBitmap.getWidth(), resultBitmap.getHeight());

int yPosition = offset;
for (int i = 0; i < images.size(); ++i) {
    BufferedImage currentBitmap = images.get(i);
    g.drawImage(currentBitmap, offset, yPosition, null);
    yPosition += currentBitmap.getHeight() + offset;
}
```

## ステップ 5: 結果の保存

最終的な結合画像を指定したファイル場所に保存します。

```java
File outputfile = new File(dataDir + "output.png");
ImageIO.write(resultBitmap, "png", outputfile);
```

## 複数バーコード生成の一般的なユースケース

- **包装ラベル** – 製品コード、ロットコード、出荷コードを単一ラベルに組み合わせます。  
- **イベントチケット** – 異なるスキャンステーション用に QR、Data Matrix、Code 128 識別子を埋め込みます。  
- **在庫管理** – SKU、RFID タグデータ、シリアル番号を同時に表示し、迅速な監査を可能にします。

## トラブルシューティングとヒント

- **画像サイズの問題** – `offset` 変数を調整してバーコード間の間隔を増減します。  
- **未対応シンボロジー** – 使用したいバーコードタイプが Aspose.BarCode のバージョンでサポートされているか確認してください。  
- **パフォーマンス** – ループで多数の画像を生成する場合、単一の `Graphics` オブジェクトを再利用します。

## FAQ

### Q1: 生成画像内の個々のバーコードの外観をカスタマイズできますか？

A1: はい、Aspose.BarCode はバーコードの外観に関する豊富なカスタマイズオプションを提供しており、各バーコードのスタイルを好みに合わせて調整できます。

### Q2: Aspose.BarCode はさまざまなバーコードシンボロジーに対応していますか？

A2: もちろんです！Aspose.BarCode は CODE_39、DATA_MATRIX、QR、CODE_128、EAN_13、AZTEC など、幅広いシンボロジーをサポートしています。本チュートリアルでも実演しています。

### Q3: Aspose.BarCode を Java プロジェクトに統合するには？

A3: Aspose.BarCode for Java ライブラリを[こちら](https://releases.aspose.com/barcode/java/)からダウンロードし、ドキュメントに記載されたインストール手順に従ってください。

### Q4: 商用アプリケーションで Aspose.BarCode を使用できますか？

A4: はい、商用目的で Aspose.BarCode を使用するには、[こちら](https://purchase.aspose.com/buy)からライセンスを取得してください。

### Q5: Aspose.BarCode のトライアルオプションはありますか？

A5: もちろんです！[こちら](https://releases.aspose.com/)から無料トライアルライセンスを取得し、Aspose.BarCode の機能をお試しください。

**追加の質問**

**Q: Java で特に QR コードを生成するにはどうすればよいですか？**  
A: コレクション例に示したように、`BarcodeGenerator` インスタンス作成時に `EncodeTypes.QR` を使用します。

**Q: Aspose.BarCode は印刷用の高解像度出力をサポートしていますか？**  
A: はい、画像保存時に DPI を指定して印刷品質の要件を満たすことができます。

---

**Last Updated:** 2025-12-10  
**Tested With:** Aspose.BarCode for Java 24.11  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}