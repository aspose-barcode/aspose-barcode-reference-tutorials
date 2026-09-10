---
date: 2026-04-03
description: Aspose.BarCode for Java を使用して QR コードを作成し、1 つの画像に複数のバーコードを生成する方法を学びます。セットアップ、コード、トラブルシューティングを含みます。
keywords:
- create qr code java
- aspose barcode java
- generate barcodes java
linktitle: 単一画像上で複数のバーコードを生成する
second_title: Aspose.BarCode Java API
title: JavaでQRコードを作成 – 1つの画像に複数のバーコードを生成
url: /ja/java/advanced-settings-and-optimization/generating-multiple-barcodes-single-image/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# QRコード Java の作成 – 1つの画像に複数のバーコードを生成

## はじめに

このチュートリアルでは、**how to create QR code java** を学び、**Aspose.BarCode for Java** を使用して複数の異なるバーコードタイプを単一の画像に結合する方法を紹介します。コンパクトな QR ラベル、製品バーコード、あるいは 2‑D と線形シンボルの組み合わせが必要な場合でも、本ガイドはプロジェクトのセットアップから最終的な結合画像の保存までのすべての手順を案内するので、すぐに Java アプリケーションにバーコード生成を組み込むことができます。

## クイック回答
- **What library should I use?** Aspose.BarCode for Java provides the most complete set of symbologies.  
- **Can I generate different barcode types together?** Yes, you can mix CODE_39, QR, AZTEC, and more on a single canvas.  
- **Do I need a license for development?** A free trial works for testing; a commercial license is required for production.  
- **Which Java version is supported?** Java 8 and newer are fully compatible.  
- **Is the output format configurable?** You can export the combined image as PNG, JPEG, BMP, etc.  

## create QR code java とは？

Java で QR コードを作成することは、テキスト文字列をスマートフォンやバーコードリーダーでスキャン可能な二次元マトリックスに変換することを意味します。**Aspose.BarCode for Java** がエンコードとレンダリングを処理するため、低レベルの画像処理に時間を取られることなくビジネスロジックに集中できます。

## Aspose.BarCode Java を使用してバーコードを生成する理由は？

- **Broad symbology support** – from classic linear codes to modern 2‑D matrices.  
- **High‑quality rendering** – anti‑aliased output that works on any device.  
- **Simple API** – create, customize, and combine barcodes with just a few method calls.  
- **No external dependencies** – everything runs on the JVM without native libraries.  

## 前提条件

- Basic understanding of Java programming.  
- Java Development Kit (JDK) installed on your system.  
- Aspose.BarCode for Java library downloaded and set up. You can download it [here](https://releases.aspose.com/barcode/java/).  
- An integrated development environment (IDE) such as Eclipse or IntelliJ IDEA.

## 名前空間のインポート

In your Java project, import the necessary namespaces to access the Aspose.BarCode functionality. Add the following import statements at the beginning of your Java class:

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

## 手順 1: リソースディレクトリの設定

Define the path to the resource directory where the generated barcodes will be saved. This directory is crucial for organizing and managing your barcode images.

```java
// The path to the resource directory.
String dataDir = Utils.getDataDir(GenerateMultipleBarcodesOnASingleImage.class)
        + "BarcodeReader/advanced_features/";
```

## 手順 2: バーコードのコレクションを作成

Initialize a `HashMap` to store the barcode data. Each entry in the collection represents a barcode with its respective encoding type.

```java
HashMap<String, EncodeTypes> collection = new HashMap<>();
collection.put("ONE123", EncodeTypes.CODE_39_STANDARD);
collection.put("Process Collection", EncodeTypes.DATA_MATRIX);
collection.put("Dictionary Collection", EncodeTypes.QR);
collection.put("X06712AT", EncodeTypes.CODE_128);
collection.put("979026000043", EncodeTypes.EAN_13);
collection.put("Aztec BarCode", EncodeTypes.AZTEC);
```

## 手順 3: バーコード画像を生成

Iterate through the collection and generate barcode images using the Aspose.BarCode library. Store the images in an `ArrayList` for further processing.

```java
ArrayList<BufferedImage> images = new ArrayList<>();
for (Object key : collection.keySet()) {
    BarcodeGenerator bb = new BarcodeGenerator((BaseEncodeType) collection.get(key));
    bb.setCodeText((String) key);
    images.add(bb.generateBarCodeImage());
}
```

## 手順 4: 結合画像を作成

Determine the maximum width and total height of the barcode images. Create a `BufferedImage` to combine individual barcode images into a single output image.

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

## 手順 5: 結果を保存

Save the final combined image to a specified file location.

```java
File outputfile = new File(dataDir + "output.png");
ImageIO.write(resultBitmap, "png", outputfile);
```

## 複数のバーコード生成の一般的なユースケース

- **Packaging labels** – combine product, batch, and shipping codes on a single label.  
- **Event tickets** – embed QR, Data Matrix, and Code 128 identifiers for different scanning stations.  
- **Inventory management** – display SKU, RFID tag data, and serial numbers together for quick audit.

## トラブルシューティングとヒント

- **Image size issues** – adjust the `offset` variable to increase or decrease spacing between barcodes.  
- **Unsupported symbology** – verify that your Aspose.BarCode version supports the desired barcode type.  
- **Performance** – reuse a single `Graphics` object if you generate many images in a loop.

## よくある質問

**Q1: Can I customize the appearance of individual barcodes in the generated image?**  
A1: Yes, Aspose.BarCode provides extensive customization options for barcode appearance, allowing you to tailor each barcode's style to your preferences.

**Q2: Is Aspose.BarCode compatible with different barcode symbologies?**  
A2: Absolutely! Aspose.BarCode supports a wide range of symbologies, including CODE_39, DATA_MATRIX, QR, CODE_128, EAN_13, and AZTEC, as demonstrated in this tutorial.

**Q3: How can I integrate Aspose.BarCode into my Java project?**  
A3: Simply download the Aspose.BarCode for Java library from [here](https://releases.aspose.com/barcode/java/) and follow the installation instructions provided in the documentation.

**Q4: Can I use Aspose.BarCode for commercial applications?**  
A4: Yes, you can obtain a license from [here](https://purchase.aspose.com/buy) to use Aspose.BarCode for commercial purposes.

**Q5: Are there any trial options available for Aspose.BarCode?**  
A5: Certainly! You can explore the features of Aspose.BarCode by obtaining a free trial license [here](https://releases.aspose.com/).

**Q6: How do I generate a high‑resolution QR code for printing?**  
A6: Set the desired DPI on the `BarcodeGenerator` before calling `generateBarCodeImage()`, then save the image in a loss‑less format such as PNG.

**Q7: What should I do if the combined image appears truncated?**  
A7: Verify that the `offset` and canvas size calculations correctly account for all barcode heights; increasing the canvas height or reducing individual barcode sizes resolves most truncation issues.

---

**最終更新日:** 2026-04-03  
**テスト環境:** Aspose.BarCode for Java 24.11  
**作者:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}