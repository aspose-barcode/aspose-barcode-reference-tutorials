---
title: 使用 Aspose.BarCode 在 Java 中的單一影像上產生多個條碼
linktitle: 在單一影像上產生多個條碼
second_title: Aspose.BarCode Java API
description: 使用 Aspose.BarCode for Java 在單一影像上輕鬆產生多個條碼。請按照我們的逐步指南進行無縫整合。
weight: 19
url: /zh-hant/java/advanced-settings-and-optimization/generating-multiple-barcodes-single-image/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 使用 Aspose.BarCode 在 Java 中的單一影像上產生多個條碼

## 介紹

在 Java 程式設計的動態世界中，有效地建立和管理條碼對於各種應用程式至關重要。 Aspose.BarCode for Java 簡化了這個過程，讓開發人員在單一影像上無縫產生多個條碼。本教學將引導您完成在 Java 環境中使用 Aspose.BarCode 實現此目的的步驟。

## 先決條件

在深入學習本教程之前，請確保您具備以下先決條件：

- 對 Java 程式設計有基本的了解。
- 您的系統上安裝了 Java 開發工具包 (JDK)。
- 下載並設定了 Aspose.BarCode for Java 函式庫。你可以下載它[這裡](https://releases.aspose.com/barcode/java/).
- 整合開發環境 (IDE)，例如 Eclipse 或 IntelliJ IDEA。

## 導入命名空間

在您的 Java 專案中，匯入必要的命名空間以存取 Aspose.BarCode 功能。在 Java 類別的開頭新增以下導入語句：

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

## 第1步：設定資源目錄

定義保存產生的條碼的資源目錄的路徑。該目錄對於組織和管理條碼影像至關重要。

```java
//資源目錄的路徑。
String dataDir = Utils.getDataDir(GenerateMultipleBarcodesOnASingleImage.class)
        + "BarcodeReader/advanced_features/";
```

## 第 2 步：建立條碼集合

初始化一個HashMap來儲存條碼資料。集合中的每個條目代表一個條碼及其各自的編碼類型。

```java
HashMap<String, EncodeTypes> collection = new HashMap<>();
collection.put("ONE123", EncodeTypes.CODE_39_STANDARD);
collection.put("Process Collection", EncodeTypes.DATA_MATRIX);
collection.put("Dictionary Collection", EncodeTypes.QR);
collection.put("X06712AT", EncodeTypes.CODE_128);
collection.put("979026000043", EncodeTypes.EAN_13);
collection.put("Aztec BarCode", EncodeTypes.AZTEC);
```

## 第 3 步：產生條碼圖像

迭代集合併使用 Aspose.BarCode 庫產生條碼圖像。將圖像儲存在 ArrayList 中以供進一步處理。

```java
ArrayList<BufferedImage> images = new ArrayList<>();
for (Object key : collection.keySet()) {
    BarcodeGenerator bb = new BarcodeGenerator((BaseEncodeType) collection.get(key));
    bb.setCodeText((String) key);
    images.add(bb.generateBarCodeImage());
}
```

## 第 4 步：建立組合影像

確定條碼影像的最大寬度和總高度。建立 BufferedImage 將各個條碼影像組合成單一輸出影像。

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
## 第 5 步：儲存結果

將最終組合影像儲存到指定的檔案位置。

```java
File outputfile = new File(dataDir + "output.png");
ImageIO.write(resultBitmap, "png", outputfile);
```

## 結論

恭喜！您已使用 Aspose.BarCode for Java 在單一影像上成功產生了多個條碼。這個強大的函式庫簡化了條碼處理，使其成為 Java 開發人員的寶貴工具。

## 常見問題解答

### 問題 1：我可以自訂產生影像中各個條碼的外觀嗎？

A1：是的，Aspose.BarCode 為條碼外觀提供了廣泛的自訂選項，可讓您根據自己的喜好自訂每個條碼的樣式。

### Q2：Aspose.BarCode 是否相容於不同的條碼符號？

A2：當然！ Aspose.BarCode 支援多種符號系統，包括 CODE_39、DATA_MATRIX、QR、CODE_128、EAN_13 和 AZTEC，如本教學所示。

### Q3：如何將 Aspose.BarCode 整合到我的 Java 專案中？

 A3：只需從下列位置下載 Aspose.BarCode for Java 函式庫：[這裡](https://releases.aspose.com/barcode/java/)並按照文件中提供的安裝說明進行操作。

### Q4：我可以將Aspose.BarCode用於商業應用嗎？

 A4：是的，您可以從以下位置取得許可證[這裡](https://purchase.aspose.com/buy)將 Aspose.BarCode 用於商業目的。

### Q5：Aspose.BarCode 有可用的試用選項嗎？

 A5：當然！您可以透過取得免費試用授權來探索 Aspose.BarCode 的功能[這裡](https://releases.aspose.com/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
