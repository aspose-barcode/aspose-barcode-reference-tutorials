---
title: Aspose.BarCode を使用して Java で単一の画像に複数のバーコードを生成する
linktitle: 単一の画像上で複数のバーコードを生成する
second_title: Aspose.BarCode Java API
description: Aspose.BarCode for Java を使用して、単一の画像上に複数のバーコードを簡単に生成します。シームレスな統合については、ステップバイステップのガイドに従ってください。
type: docs
weight: 19
url: /ja/java/advanced-settings-and-optimization/generating-multiple-barcodes-single-image/
---
## 導入

Java プログラミングの動的な世界では、さまざまなアプリケーションにとってバーコードを効率的に作成および管理することが重要です。 Aspose.BarCode for Java はこのプロセスを簡素化し、開発者が 1 つの画像上に複数のバーコードをシームレスに生成できるようにします。このチュートリアルでは、Java 環境で Aspose.BarCode を使用してこれを実現する手順を説明します。

## 前提条件

チュートリアルに進む前に、次の前提条件を満たしていることを確認してください。

- Java プログラミングの基本的な理解。
- Java Development Kit (JDK) がシステムにインストールされています。
- Aspose.BarCode for Java ライブラリをダウンロードしてセットアップしました。ダウンロードできます[ここ](https://releases.aspose.com/barcode/java/).
- Eclipse や IntelliJ IDEA などの統合開発環境 (IDE)。

## 名前空間のインポート

Java プロジェクトで、Aspose.BarCode 機能にアクセスするために必要な名前空間をインポートします。 Java クラスの先頭に次のインポート ステートメントを追加します。

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

## ステップ 1: リソース ディレクトリを設定する

生成されたバーコードが保存されるリソース ディレクトリへのパスを定義します。このディレクトリは、バーコード画像を整理および管理するために重要です。

```java
//リソース ディレクトリへのパス。
String dataDir = Utils.getDataDir(GenerateMultipleBarcodesOnASingleImage.class)
        + "BarcodeReader/advanced_features/";
```

## ステップ 2: バーコードのコレクションを作成する

HashMap を初期化してバーコード データを保存します。コレクション内の各エントリは、それぞれのエンコード タイプのバーコードを表します。

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

コレクションを反復処理し、Aspose.BarCode ライブラリを使用してバーコード イメージを生成します。さらに処理するために、画像を ArrayList に保存します。

```java
ArrayList<BufferedImage> images = new ArrayList<>();
for (Object key : collection.keySet()) {
    BarcodeGenerator bb = new BarcodeGenerator((BaseEncodeType) collection.get(key));
    bb.setCodeText((String) key);
    images.add(bb.generateBarCodeImage());
}
```

## ステップ 4: 結合イメージを作成する

バーコード画像の最大幅と合計高さを決定します。 BufferedImage を作成して、個々のバーコード イメージを 1 つの出力イメージに結合します。

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
## ステップ 5: 結果を保存する

最終的に結合されたイメージを指定したファイルの場所に保存します。

```java
File outputfile = new File(dataDir + "output.png");
ImageIO.write(resultBitmap, "png", outputfile);
```

## 結論

おめでとう！ Aspose.BarCode for Java を使用して、単一の画像上に複数のバーコードを生成することに成功しました。この強力なライブラリはバーコードの処理を簡素化し、Java 開発者にとって非常に貴重なツールになります。

## よくある質問

### Q1: 生成された画像内の個々のバーコードの外観をカスタマイズできますか?

A1: はい、Aspose.BarCode にはバーコードの外観に関する広範なカスタマイズ オプションが用意されており、各バーコードのスタイルを好みに合わせて調整できます。

### Q2: Aspose.BarCode はさまざまなバーコード シンボルと互換性がありますか?

A2: もちろんです！このチュートリアルで説明するように、Aspose.BarCode は、CODE_39、DATA_MATRIX、QR、CODE_128、EAN_13、AZTEC などの幅広いシンボルをサポートしています。

### Q3: Aspose.BarCode を Java プロジェクトに統合するにはどうすればよいですか?

 A3: Aspose.BarCode for Java ライブラリを次のサイトからダウンロードするだけです。[ここ](https://releases.aspose.com/barcode/java/)ドキュメントに記載されているインストール手順に従ってください。

### Q4: Aspose.BarCode を商用アプリケーションに使用できますか?

 A4: はい、次からライセンスを取得できます。[ここ](https://purchase.aspose.com/buy) Aspose.BarCode を商業目的で使用すること。

### Q5: Aspose.BarCode に利用できる試用オプションはありますか?

 A5：確かに！無料試用ライセンスを取得すると、Aspose.BarCode の機能を試すことができます[ここ](https://releases.aspose.com/).