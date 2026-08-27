---
date: 2026-04-03
description: 學習如何使用 Aspose.BarCode for Java 建立 QR 代碼並在單一圖像上產生多個條碼。包括設定、程式碼與故障排除。
keywords:
- create qr code java
- aspose barcode java
- generate barcodes java
linktitle: 在單一圖像上產生多個條碼
second_title: Aspose.BarCode Java API
title: 使用 Java 建立 QR Code – 在同一張圖片上生成多個條碼
url: /zh-hant/java/advanced-settings-and-optimization/generating-multiple-barcodes-single-image/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 建立 QR Code Java – 在單一圖像上產生多個條碼

## 簡介

在本教學中，您將學習 **how to create QR code java**，並使用 **Aspose.BarCode for Java** 將多種不同類型的條碼合併到單一圖像上。無論您需要緊湊的 QR 標籤、產品條碼，或是 2‑D 與線性符號的混合，本指南都會一步步帶領您，從專案設定到儲存最終合併圖像，讓您立即在 Java 應用程式中整合條碼產生。

## 快速解答
- **What library should I use?** Aspose.BarCode for Java 提供最完整的符號集。  
- **Can I generate different barcode types together?** 可以，您可以在同一畫布上混合 CODE_39、QR、AZTEC 等多種條碼。  
- **Do I need a license for development?** 免費試用可用於測試；正式環境需商業授權。  
- **Which Java version is supported?** 完全相容於 Java 8 及更新版本。  
- **Is the output format configurable?** 您可以將合併圖像匯出為 PNG、JPEG、BMP 等格式。  

## 什麼是 create QR code java？

在 Java 中建立 QR code 意味著將文字字串轉換為可供智慧手機或條碼閱讀器掃描的二維矩陣。**Aspose.BarCode for Java** 處理編碼與渲染，讓您專注於業務邏輯，而無需關注低階影像處理。

## 為何使用 Aspose.BarCode Java 產生條碼 java？

- **Broad symbology support** – 從傳統線性條碼到現代 2‑D 矩陣皆支援。  
- **High‑quality rendering** – 抗鋸齒輸出，適用於任何裝置。  
- **Simple API** – 只需少量方法呼叫即可建立、客製化及合併條碼。  
- **No external dependencies** – 完全在 JVM 上執行，無需原生函式庫。  

## 先決條件

在開始本教學之前，請確保您具備以下先決條件：

- 具備 Java 程式設計的基本概念。  
- 系統已安裝 Java Development Kit (JDK)。  
- 已下載並設定 Aspose.BarCode for Java 函式庫。您可於 [此處](https://releases.aspose.com/barcode/java/) 下載。  
- 整合開發環境 (IDE)，如 Eclipse 或 IntelliJ IDEA。  

## 匯入命名空間

在您的 Java 專案中，匯入必要的命名空間以使用 Aspose.BarCode 功能。於 Java 類別的開頭加入以下 import 陳述式：

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

## 步驟 1：設定資源目錄

定義儲存產生條碼的資源目錄路徑。此目錄對於條碼圖像的組織與管理至關重要。

```java
// The path to the resource directory.
String dataDir = Utils.getDataDir(GenerateMultipleBarcodesOnASingleImage.class)
        + "BarcodeReader/advanced_features/";
```

## 步驟 2：建立條碼集合

初始化一個 `HashMap` 以儲存條碼資料。集合中的每個項目代表一個條碼及其相應的編碼類型。

```java
HashMap<String, EncodeTypes> collection = new HashMap<>();
collection.put("ONE123", EncodeTypes.CODE_39_STANDARD);
collection.put("Process Collection", EncodeTypes.DATA_MATRIX);
collection.put("Dictionary Collection", EncodeTypes.QR);
collection.put("X06712AT", EncodeTypes.CODE_128);
collection.put("979026000043", EncodeTypes.EAN_13);
collection.put("Aztec BarCode", EncodeTypes.AZTEC);
```

## 步驟 3：產生條碼圖像

遍歷集合，使用 Aspose.BarCode 函式庫產生條碼圖像。將圖像存入 `ArrayList` 以便後續處理。

```java
ArrayList<BufferedImage> images = new ArrayList<>();
for (Object key : collection.keySet()) {
    BarcodeGenerator bb = new BarcodeGenerator((BaseEncodeType) collection.get(key));
    bb.setCodeText((String) key);
    images.add(bb.generateBarCodeImage());
}
```

## 步驟 4：建立合併圖像

確定條碼圖像的最大寬度與總高度。建立 `BufferedImage`，將各個條碼圖像合併為單一輸出圖像。

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

## 步驟 5：儲存結果

將最終合併圖像儲存至指定的檔案位置。

```java
File outputfile = new File(dataDir + "output.png");
ImageIO.write(resultBitmap, "png", outputfile);
```

## 產生多條碼的常見使用情境

- **Packaging labels** – 在單一標籤上結合產品、批次與運送代碼。  
- **Event tickets** – 為不同掃描站點嵌入 QR、Data Matrix 與 Code 128 識別碼。  
- **Inventory management** – 同時顯示 SKU、RFID 標籤資料與序號，以便快速稽核。  

## 故障排除與技巧

- **Image size issues** – 調整 `offset` 變數以增減條碼之間的間距。  
- **Unsupported symbology** – 確認您使用的 Aspose.BarCode 版本支援所需的條碼類型。  
- **Performance** – 若在迴圈中產生大量圖像，請重複使用同一個 `Graphics` 物件以提升效能。  

## 常見問題

**Q1: 我可以自訂產生圖像中各個條碼的外觀嗎？**  
A1: 可以，Aspose.BarCode 提供廣泛的條碼外觀自訂選項，讓您依需求調整每個條碼的樣式。

**Q2: Aspose.BarCode 是否相容於不同的條碼符號？**  
A2: 絕對相容！Aspose.BarCode 支援廣泛的符號，包括 CODE_39、DATA_MATRIX、QR、CODE_128、EAN_13 以及 AZTEC，如本教學所示。

**Q3: 我該如何將 Aspose.BarCode 整合到我的 Java 專案中？**  
A3: 只需從 [此處](https://releases.aspose.com/barcode/java/) 下載 Aspose.BarCode for Java 函式庫，並依照文件中的安裝說明進行設定。

**Q4: 我可以將 Aspose.BarCode 用於商業應用嗎？**  
A4: 可以，您可於 [此處](https://purchase.aspose.com/buy) 取得授權，以商業用途使用 Aspose.BarCode。

**Q5: Aspose.BarCode 有提供試用方案嗎？**  
A5: 當然！您可於 [此處](https://releases.aspose.com/) 取得免費試用授權，體驗 Aspose.BarCode 功能。

**Q6: 我該如何產生高解析度的 QR code 以供列印？**  
A6: 在呼叫 `generateBarCodeImage()` 前，於 `BarcodeGenerator` 設定所需的 DPI，然後將圖像儲存為 PNG 等無損格式。

**Q7: 若合併圖像被截斷，我該怎麼辦？**  
A7: 請確認 `offset` 與畫布尺寸計算正確考慮所有條碼高度；調整畫布高度或縮小單一條碼尺寸通常可解決截斷問題。

---

**最後更新:** 2026-04-03  
**測試環境:** Aspose.BarCode for Java 24.11  
**作者:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}