---
date: 2026-10-19
description: Aspose.BarCode for Java を使用して、QR code java の作成方法と、1つの画像で複数のバーコードを生成する方法を学びます。セットアップ、コード、トラブルシューティングを含みます。
keywords:
- create qr code java
- how to create qr
- java barcode library
- generate multiple barcodes
- aspose trial license
lastmod: 2026-10-19
linktitle: 1つの画像で複数のバーコードを生成
og_description: Aspose.BarCode for Java を使用して、QR code java を作成し、複数のバーコードタイプを1つの画像に結合します。ステップバイステップのガイドに従い、コードスニペットを確認し、トラブルシューティングのヒントを学びます。
og_image_alt: Screenshot of a Java application generating a QR code and other barcodes
  on one combined image
og_title: Create QR code java – 1つの画像で複数のバーコードを生成
schemas:
- author: Aspose
  dateModified: '2026-10-19'
  description: Learn how to create QR code java and generate multiple barcodes on
    a single image using Aspose.BarCode for Java. Includes setup, code, and troubleshooting.
  headline: Create QR code java – generate multiple barcodes on one image
  type: TechArticle
- questions:
  - answer: Yes. Use the `BarcodeGenerator` properties such as `setBarColor`, `setBackgroundColor`,
      and `setXDimension` to style each barcode independently before adding it to
      the canvas.
    question: Can I customize the appearance of individual barcodes in the generated
      image?
  - answer: Absolutely. The library supports 50+ symbologies, including CODE_39, DATA_MATRIX,
      QR, CODE_128, EAN_13, and AZTEC, as demonstrated in this tutorial.
    question: Is Aspose.BarCode compatible with different barcode symbologies?
  - answer: Download the JAR from the Aspose.BarCode for Java library download page,
      add it to your project’s classpath, and import the required namespaces as shown
      in the “Import namespaces” section.
    question: How do I integrate Aspose.BarCode into my Java project?
  - answer: Yes. Purchase a license from the Aspose.BarCode license purchase page
      to remove trial limitations and obtain full production support.
    question: Can I use Aspose.BarCode for commercial applications?
  - answer: Certainly. A free trial license is available from the Aspose.BarCode free
      trial download page, giving you full API access for evaluation.
    question: Are there trial options available for Aspose.BarCode?
  type: FAQPage
second_title: Aspose.BarCode Java API
tags:
- create qr code
- aspose barcode
- java barcode generation
- multiple barcodes image
title: Create QR code java – 1つの画像で複数のバーコードを生成
url: /ja/java/advanced-settings-and-optimization/generating-multiple-barcodes-single-image/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# QRコード Java の作成 – 1つの画像に複数のバーコードを生成

## はじめに

このチュートリアルでは、**how to create QR code java** を学び、**Aspose.BarCode for Java** を使用して複数の異なるバーコードタイプを単一のキャンバスに結合する方法を紹介します。コンパクトなQRラベル、製品バーコード、または2次元と一次元シンボルの組み合わせが必要な場合でも、本ガイドはプロジェクトのセットアップから最終的な結合画像の保存まで、すべてのステップを順を追って説明しますので、すぐに Java アプリケーションにバーコード生成を組み込むことができます。

## 簡単な回答

- **どのライブラリを使用すべきですか？** Aspose.BarCode for Java は最も完全なシンボルセットを提供します。  
- **異なるバーコードタイプを同時に生成できますか？** はい、CODE_39、QR、AZTEC などを単一のキャンバス上で混在させることができます。  
- **開発にライセンスは必要ですか？** 無料トライアルはテストに使用できますが、本番環境では商用ライセンスが必要です。  
- **サポートされている Java バージョンは？** Java 8 以降はすべて完全に互換性があります。  
- **出力フォーマットは設定可能ですか？** 結合画像を PNG、JPEG、BMP、または TIFF としてエクスポートできます。

## create QR code java とは何ですか？

`create QR code java` は、テキスト文字列をスマートフォンやバーコードリーダーでスキャン可能な二次元マトリックスに変換するプロセスを指します。Aspose.BarCode for Java がエンコードとレンダリングを行うため、ピクセルレベルの画像処理ではなくビジネスロジックに集中できます。

## Javaでバーコードを生成するために Aspose.BarCode Java を使用する理由は？

Aspose.BarCode は **over 50 barcode symbologies**（QR、Data Matrix、Code 128、AZTEC、従来の一次元コードなど）をサポートし、最も汎用性の高い Java バーコードライブラリとなっています。**anti‑aliased images at up to 1200 dpi** をレンダリングし、画面や印刷で鮮明なスキャンを保証します。API は JVM のみで動作し、数行のコードでサイズ、色、余白、エラー訂正をカスタマイズできる流暢な設定モデルを提供します。

## 前提条件

- Java の基礎に関する確固たる理解。  
- JDK 8 以上がインストールされ、PATH に設定されていること。  
- Aspose.BarCode for Java の JAR（公式の Aspose.BarCode for Java ダウンロードページからダウンロード）。  
- IntelliJ IDEA や Eclipse などの IDE がサンプルの編集と実行に使用できること。  

## 名前空間のインポート

インポート文は `BarcodeGenerator`、`EncodeTypes`、`BarCodeImageFormat` などの Aspose.BarCode クラスをスコープに持ち込み、完全修飾名なしで参照できるようにします。  
`BarcodeGenerator` はバーコード画像の設定と生成に使用されるメインクラスです。  
`EncodeTypes` は生成するバーコードのシンボル種別を指定する Aspose.BarCode の列挙型です。  
`BarCodeImageFormat` は生成されたバーコードの出力画像フォーマットを定義します。

## ステップ 1: リソースディレクトリを設定

**resource directory** は、生成されたすべてのバーコード画像が書き込まれるファイルシステム上のフォルダーです。一度設定すればプロジェクトが整理され、古いファイルのクリーンアップも容易になります。

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

## ステップ 2: バーコードのコレクションを作成

`HashMap<String, EncodeTypes>` は、各バーコードのデータ文字列と使用したいシンボル種別を格納します。`HashMap` はキーと値をマッピングする Java のコレクションです。このコレクションが続く生成ループを駆動します。`EncodeTypes` は生成するバーコードタイプを指定する列挙型です。

```java
// The path to the resource directory.
String dataDir = Utils.getDataDir(GenerateMultipleBarcodesOnASingleImage.class)
        + "BarcodeReader/advanced_features/";
```

## ステップ 3: バーコード画像を生成

生成ループは `HashMap` を反復し、各エントリに対して `BarcodeGenerator` を作成し、`generateBarCodeImage()` を呼び出して `BufferedImage` を取得します。`generateBarCodeImage()` はレンダリングされたバーコードを含む `BufferedImage` を生成します。`BufferedImage` はメモリ内の画像を表す Java クラスです。すべての画像は後で合成するために `ArrayList<BufferedImage>` に追加されます。`ArrayList` は Java の可変長リスト実装です。

```java
HashMap<String, EncodeTypes> collection = new HashMap<>();
collection.put("ONE123", EncodeTypes.CODE_39_STANDARD);
collection.put("Process Collection", EncodeTypes.DATA_MATRIX);
collection.put("Dictionary Collection", EncodeTypes.QR);
collection.put("X06712AT", EncodeTypes.CODE_128);
collection.put("979026000043", EncodeTypes.EAN_13);
collection.put("Aztec BarCode", EncodeTypes.AZTEC);
```

## ステップ 4: 結合画像を作成

まず、アルゴリズムはすべてのバーコード画像の **maximum width** と、オプションの間隔を含めて縦に積むために必要な **total height** を計算します。その後、そのサイズの `BufferedImage` を作成し、`Graphics2D` オブジェクトを使用して各バーコードをキャンバスに描画します。`Graphics2D` は形状や画像の描画のための 2D レンダリング機能を提供する Java クラスです。

```java
ArrayList<BufferedImage> images = new ArrayList<>();
for (Object key : collection.keySet()) {
    BarcodeGenerator bb = new BarcodeGenerator((BaseEncodeType) collection.get(key));
    bb.setCodeText((String) key);
    images.add(bb.generateBarCodeImage());
}
```

## ステップ 5: 結果を保存

最後に、合成画像は `ImageIO.write` を使用してディスクに書き込まれ、指定したフォーマット（PNG、JPEG、BMP、または TIFF）で保存されます。`ImageIO.write` は `BufferedImage` を指定されたフォーマットのファイルに書き出します。ファイルパスは前述のリソースディレクトリに対する相対パスです。

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

## 複数のバーコード生成の一般的なユースケース

- **Packaging labels** – 製品、ロット、出荷コードを単一のラベルに結合し、印刷コストを削減します。  
- **Event tickets** – 会場の異なるスキャンステーション用に QR、Data Matrix、Code 128 識別子を埋め込みます。  
- **Inventory management** – SKU、RFID タグデータ、シリアル番号を一緒に表示し、迅速な監査とトレーサビリティを実現します。

## トラブルシューティングとヒント

- **Image size issues** – バーコード間の間隔を増減するには `offset` 変数を調整します。  
- **Unsupported symbology** – 使用している Aspose.BarCode のバージョンが目的のバーコードタイプをサポートしているか確認してください。新しいリリースでは追加の 2‑D コードが含まれます。  
- **Performance** – ループで多数の画像を生成する際は、`Graphics2D` オブジェクトを単一で再利用し、オブジェクト割り当てのオーバーヘッドを最小化します。

## よくある質問

**Q: 生成された画像内の個々のバーコードの外観をカスタマイズできますか？**  
A: はい。`BarcodeGenerator` の `setBarColor`、`setBackgroundColor`、`setXDimension` などのプロパティを使用して、キャンバスに追加する前に各バーコードを個別にスタイル設定できます。

**Q: Aspose.BarCode はさまざまなバーコードシンボルに対応していますか？**  
A: もちろんです。このライブラリは CODE_39、DATA_MATRIX、QR、CODE_128、EAN_13、AZTEC など、50 以上のシンボルをサポートしており、本チュートリアルでも実演しています。

**Q: Aspose.BarCode を Java プロジェクトに統合するには？**  
A: Aspose.BarCode for Java ライブラリのダウンロードページから JAR を取得し、プロジェクトのクラスパスに追加し、「名前空間のインポート」セクションに示されたように必要な名前空間をインポートします。

**Q: Aspose.BarCode を商用アプリケーションで使用できますか？**  
A: はい。Aspose.BarCode のライセンス購入ページからライセンスを購入すれば、トライアルの制限が解除され、フルサポートが受けられます。

**Q: Aspose.BarCode のトライアルオプションはありますか？**  
A: もちろんです。Aspose.BarCode の無料トライアルダウンロードページから無料トライアルライセンスを取得でき、評価のために API へのフルアクセスが可能です。

**Q: 印刷用に高解像度の QR コードを生成するには？**  
A: `generateBarCodeImage()` を呼び出す前に `BarcodeGenerator` の `setResolutionDpi` プロパティを設定し、結果を PNG などのロスレス形式で保存します。

**Q: 結合画像が切り取られているように見える場合はどうすればよいですか？**  
A: `offset` とキャンバスサイズの計算がすべてのバーコード高さを正しく考慮しているか確認してください。キャンバスの高さを増やすか、個々のバーコードサイズを縮小すれば、ほとんどの切り取り問題が解決します。

---

**最終更新日:** 2026-10-19  
**テスト環境:** Aspose.BarCode for Java 24.11  
**作者:** Aspose  








```java
File outputfile = new File(dataDir + "output.png");
ImageIO.write(resultBitmap, "png", outputfile);
```

## 関連チュートリアル

- [How to Create Barcode Image Java – Add Border with Aspose](/barcode/java/image-manipulation/adding-borders-barcode-image/)
- [How to Generate Barcode Java: Save to Streams with Aspose.BarCode](/barcode/java/advanced-settings-and-optimization/saving-barcode-image-streams/)
- [How to Generate Barcode Java and Print Barcode with Aspose](/barcode/java/barcode-rendering-techniques/rendering-barcode-printer/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}