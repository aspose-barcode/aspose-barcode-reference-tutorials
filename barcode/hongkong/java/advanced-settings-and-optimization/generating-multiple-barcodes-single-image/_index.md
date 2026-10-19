---
date: 2026-10-19
description: 了解如何使用 Aspose.BarCode for Java 建立 QR code java，並在單一圖像上產生多個條碼。內容包括設定、程式碼與故障排除。
keywords:
- create qr code java
- how to create qr
- java barcode library
- generate multiple barcodes
- aspose trial license
lastmod: 2026-10-19
linktitle: 在單一圖像上產生多個條碼
og_description: 使用 Aspose.BarCode for Java 建立 QR code java，並將多種條碼類型合併至單一圖像。依循步驟說明、檢視程式碼片段，並學習故障排除技巧。
og_image_alt: Screenshot of a Java application generating a QR code and other barcodes
  on one combined image
og_title: 建立 QR code java – 在單一圖像上產生多個條碼
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
title: 建立 QR code java – 在單一圖像上產生多個條碼
url: /zh-hant/java/advanced-settings-and-optimization/generating-multiple-barcodes-single-image/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 建立 QR code java – 在單一圖像上產生多個條碼

## 介紹

在本教學中，您將學習 **how to create QR code java** 並使用 **Aspose.BarCode for Java** 將多種不同類型的條碼合併到同一畫布上。無論您需要緊湊的 QR 標籤、產品條碼，或是 2‑D 與線性條碼的混合，本指南將逐步說明——從專案設定到儲存最終合併圖像——讓您立即在 Java 應用程式中整合條碼產生功能。

## 快速解答
- **應該使用哪個函式庫？** Aspose.BarCode for Java 提供最完整的條碼類型集合。  
- **我可以一起產生不同類型的條碼嗎？** 可以，您可以在同一畫布上混合 CODE_39、QR、AZTEC 等條碼。  
- **開發是否需要授權？** 免費試用版可用於測試；正式環境需購買商業授權。  
- **支援哪個 Java 版本？** Java 8 及以上版本皆完全相容。  
- **輸出格式是否可設定？** 您可以將合併圖像匯出為 PNG、JPEG、BMP 或 TIFF。

## 什麼是 create QR code java？

`create QR code java` 指的是將文字字串轉換為可供智慧手機或條碼讀取器掃描的二維矩陣的過程。Aspose.BarCode for Java 負責編碼與渲染，讓您專注於業務邏輯，而不必處理像素層級的圖像處理。

## 為什麼使用 Aspose.BarCode Java 產生條碼？

Aspose.BarCode 支援 **超過 50 種條碼類型**——包括 QR、Data Matrix、Code 128、AZTEC 以及傳統線性條碼——使其成為功能最全面的 Java 條碼函式庫。它可渲染 **最高 1200 dpi 的抗鋸齒圖像**，確保螢幕與列印時的掃描清晰度。此 API 僅需 JVM，即可透過流暢的設定模型，以簡短程式碼自訂尺寸、顏色、邊距與錯誤更正等參數。

## 前置條件

- 對 Java 基礎有扎實的了解。  
- 已安裝 JDK 8 或更新版本，且在 PATH 中正確設定。  
- Aspose.BarCode for Java 的 JAR（從官方 Aspose.BarCode for Java 下載頁面下載）。  
- 使用如 IntelliJ IDEA 或 Eclipse 等 IDE 來編輯與執行範例。  

## 匯入命名空間

匯入語句將 Aspose.BarCode 的類別（如 `BarcodeGenerator`、`EncodeTypes` 與 `BarCodeImageFormat`）引入作用域，使您無需使用完整限定名稱即可引用它們。  
`BarcodeGenerator` 為用於設定與產生條碼圖像的主要類別。  
`EncodeTypes` 是 Aspose.BarCode 中的列舉，用於指定要產生的條碼類型。  
`BarCodeImageFormat` 定義產生條碼的輸出圖像格式。

## 步驟 1：設定資源目錄

**資源目錄** 是您檔案系統中用來寫入所有產生的條碼圖像的資料夾。一次性定義可保持專案有序，且方便清理舊檔案。

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

## 步驟 2：建立條碼集合

`HashMap<String, EncodeTypes>` 用於儲存每個條碼的資料字串以及您想使用的條碼類型。`HashMap` 是 Java 的集合，用於將鍵映射到值。此集合驅動後續的產生迴圈。`EncodeTypes` 為列舉，指定要產生的條碼類型。

```java
// The path to the resource directory.
String dataDir = Utils.getDataDir(GenerateMultipleBarcodesOnASingleImage.class)
        + "BarcodeReader/advanced_features/";
```

## 步驟 3：產生條碼圖像

產生迴圈會遍歷 `HashMap`，為每個條目建立 `BarcodeGenerator`，並呼叫 `generateBarCodeImage()` 取得 `BufferedImage`。`generateBarCodeImage()` 會產生包含已渲染條碼的 `BufferedImage`。`BufferedImage` 是 Java 中代表記憶體中圖像的類別。所有圖像會加入 `ArrayList<BufferedImage>`，以便稍後合成。`ArrayList` 是 Java 的可調整大小的列表實作。

```java
HashMap<String, EncodeTypes> collection = new HashMap<>();
collection.put("ONE123", EncodeTypes.CODE_39_STANDARD);
collection.put("Process Collection", EncodeTypes.DATA_MATRIX);
collection.put("Dictionary Collection", EncodeTypes.QR);
collection.put("X06712AT", EncodeTypes.CODE_128);
collection.put("979026000043", EncodeTypes.EAN_13);
collection.put("Aztec BarCode", EncodeTypes.AZTEC);
```

## 步驟 4：建立合併圖像

首先，演算法會計算所有條碼圖像的 **最大寬度** 以及垂直堆疊（含可選間距）所需的 **總高度**。接著建立相同尺寸的 `BufferedImage`，並使用 `Graphics2D` 物件將每個條碼繪製到畫布上。`Graphics2D` 是 Java 提供 2D 繪圖功能的類別，可用於繪製形狀與圖像。

```java
ArrayList<BufferedImage> images = new ArrayList<>();
for (Object key : collection.keySet()) {
    BarcodeGenerator bb = new BarcodeGenerator((BaseEncodeType) collection.get(key));
    bb.setCodeText((String) key);
    images.add(bb.generateBarCodeImage());
}
```

## 步驟 5：儲存結果

最後，使用 `ImageIO.write` 將合成圖像寫入磁碟，格式為您指定的 PNG、JPEG、BMP 或 TIFF。`ImageIO.write` 會將 `BufferedImage` 以指定格式寫入檔案。檔案路徑相對於先前定義的資源目錄。

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

## 產生多條碼的常見使用情境

- **包裝標籤** – 在單一標籤上結合產品、批次與運送碼，以降低印刷成本。  
- **活動票券** – 嵌入 QR、Data Matrix 與 Code 128 識別碼，以供場地不同掃描站使用。  
- **庫存管理** – 同時顯示 SKU、RFID 標籤資料與序號，便於快速稽核與追蹤。

## 疑難排解與技巧

- **圖像尺寸問題** – 調整 `offset` 變數以增減條碼之間的間距。  
- **不支援的條碼類型** – 確認您使用的 Aspose.BarCode 版本支援目標條碼；較新版本會加入更多 2‑D 條碼。  
- **效能** – 在迴圈中產生大量圖像時，重複使用同一個 `Graphics2D` 物件，以減少物件分配開銷。  

## 常見問題

**Q: 我可以自訂產生圖像中各條碼的外觀嗎？**  
A: 可以。使用 `BarcodeGenerator` 的屬性，如 `setBarColor`、`setBackgroundColor` 與 `setXDimension`，在將條碼加入畫布前分別設定每個條碼的樣式。

**Q: Aspose.BarCode 是否相容於不同的條碼類型？**  
A: 當然。此函式庫支援超過 50 種條碼類型，包括 CODE_39、DATA_MATRIX、QR、CODE_128、EAN_13 與 AZTEC，如本教學所示。

**Q: 我要如何將 Aspose.BarCode 整合到我的 Java 專案中？**  
A: 從 Aspose.BarCode for Java 函式庫下載頁面取得 JAR，將其加入專案的 classpath，並依「匯入命名空間」章節所示匯入所需的命名空間。

**Q: 我可以在商業應用中使用 Aspose.BarCode 嗎？**  
A: 可以。請於 Aspose.BarCode 授權購買頁面購買授權，以移除試用限制並取得完整的正式支援。

**Q: Aspose.BarCode 有提供試用方案嗎？**  
A: 當然有。可從 Aspose.BarCode 免費試用下載頁面取得免費試用授權，讓您完整使用 API 進行評估。

**Q: 我要如何產生高解析度的 QR code 以供列印？**  
A: 在呼叫 `generateBarCodeImage()` 前，於 `BarcodeGenerator` 設定 `setResolutionDpi` 屬性，然後以 PNG 等無損格式儲存結果。

**Q: 若合併圖像被截斷，我該怎麼辦？**  
A: 請確認 `offset` 與畫布尺寸計算正確考慮所有條碼的高度；增加畫布高度或縮小單一條碼尺寸通常可解決截斷問題。

---

**最後更新日期：** 2026-10-19  
**測試環境：** Aspose.BarCode for Java 24.11  
**作者：** Aspose  








```java
File outputfile = new File(dataDir + "output.png");
ImageIO.write(resultBitmap, "png", outputfile);
```

## 相關教學

- [如何使用 Aspose 建立條碼圖像 Java – 添加邊框](/barcode/java/image-manipulation/adding-borders-barcode-image/)
- [如何使用 Aspose.BarCode 產生條碼 Java：儲存至串流](/barcode/java/advanced-settings-and-optimization/saving-barcode-image-streams/)
- [如何使用 Aspose 產生條碼 Java 並列印條碼](/barcode/java/barcode-rendering-techniques/rendering-barcode-printer/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}