---
date: 2026-02-09
description: 學習如何在 Java 中使用 Aspose.BarCode（功能強大的 Java 條碼生成庫）於單一圖像上產生條碼。本指南涵蓋整合與多條碼產生。
linktitle: Generating Multiple Barcodes on a Single Image
second_title: Aspose.BarCode Java API
title: 如何在 Java 中於單一圖像生成條碼
url: /zh-hant/java/advanced-settings-and-optimization/generating-multiple-barcodes-single-image/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 在 Java 中使用 Aspose.BarCode 於單一圖像上產生多個條碼

## 簡介

如果你正在尋找在 Java 應用程式中**如何產生條碼**的可靠方法，你來對地方了。使用 Aspose.BarCode for Java，你只需幾行程式碼即可將多種不同類型的條碼放置於同一張圖像上。本教學將帶你完成整個流程——從專案設定到儲存合併圖像——讓你立即在自己的解決方案中使用條碼產生功能。

## 快速答覆
- **我應該使用哪個函式庫？** Aspose.BarCode for Java 提供最完整的條碼類型集合。  
- **我可以同時產生不同類型的條碼嗎？** 可以，你可以在同一個畫布上混合 CODE_39、QR、AZTEC 等條碼。  
- **開發時需要授權嗎？** 免費試用版可用於測試；正式上線需購買商業授權。  
- **支援哪個 Java 版本？** 完全相容於 Java 8 及以上版本。  
- **輸出格式可以自訂嗎？** 你可以將合併圖像匯出為 PNG、JPEG、BMP 等格式。

## 什麼是 Java 中的「如何產生條碼」？

產生條碼是指將資料字串轉換為掃描器可讀取的視覺圖案。Aspose.BarCode 會自動處理編碼、渲染與圖像產生的步驟，讓你專注於業務邏輯，而不必關注底層的圖像處理。

## 為什麼要在單一圖像上產生多個條碼？

- **節省空間的標籤** – 在同一標籤上結合產品、批次與運送識別碼。  
- **多掃描工作流程** – 嵌入 QR、Data Matrix 與 Code 128 條碼，以供不同掃描站使用。  
- **簡化資產追蹤** – 同時顯示 SKU、RFID 標籤資料與序號，方便快速稽核。  

## 先決條件

在開始本教學之前，請確保你具備以下先決條件：

- 具備 Java 程式設計的基本概念。  
- 系統已安裝 Java Development Kit (JDK)。  
- 已下載並設定 Aspose.BarCode for Java 函式庫。你可以在[此處](https://releases.aspose.com/barcode/java/)下載。  
- 使用如 Eclipse 或 IntelliJ IDEA 等整合開發環境 (IDE)。  

## 匯入命名空間

在你的 Java 專案中，匯入必要的命名空間以使用 Aspose.BarCode 功能。請在 Java 類別的開頭加入以下 import 陳述式：

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

初始化一個 `HashMap` 來儲存條碼資料。集合中的每個項目代表一個條碼及其對應的編碼類型。

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

計算條碼圖像的最大寬度與總高度。建立 `BufferedImage`，將各個條碼圖像合併為單一輸出圖像。

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

## 如何以 Java 方式產生 QR Code？

如果你需要 **generate qr code java** 範例，只需將集合中的項目換成 `EncodeTypes.QR`。相同的迴圈即可產生高解析度的 QR Code，可儲存 URL、聯絡資訊或任何字母數字資料。

## 如何在 Java 中產生 Code 128 條碼？

上述程式碼已示範如何使用 `EncodeTypes.CODE_128` **generate code 128 barcode**。Code 128 非常適合物流應用，因為它支援完整的 ASCII 集合且具備緊湊的編碼方式。

## 使用除 Aspose 之外的 Java 條碼產生函式庫

雖然 Aspose.BarCode 是功能完整的 **java barcode generation library**，你也可以探索如 ZXing 或 Barcode4J 等開源替代方案，以應對輕量需求。然而，Aspose 內建支援高解析度輸出、多種條碼類型以及簡易的圖像合成，全部集中於同一套件中。

## 產生多個條碼的常見使用情境

- **包裝標籤** – 在單一標籤上結合產品、批次與運送代碼。  
- **活動票券** – 嵌入 QR、Data Matrix 與 Code 128 識別碼，以供不同掃描站使用。  
- **庫存管理** – 同時顯示 SKU、RFID 標籤資料與序號，方便快速稽核。  

## 故障排除與技巧

- **圖像尺寸問題** – 調整 `offset` 變數以增減條碼之間的間距。  
- **不支援的條碼類型** – 確認你的 Aspose.BarCode 版本支援所需的條碼類型。  
- **效能** – 若在迴圈中產生大量圖像，請重複使用單一 `Graphics` 物件。  
- **記憶體管理** – 處理大量條碼時，可考慮暫時將每張圖像寫入磁碟，以避免過度佔用堆積記憶體。  

## 常見問題

### Q1：我可以自訂產生圖像中各條碼的外觀嗎？

A1：可以，Aspose.BarCode 提供廣泛的條碼外觀自訂選項，讓你依需求調整每個條碼的樣式。

### Q2：Aspose.BarCode 相容於不同的條碼類型嗎？

A2：當然！Aspose.BarCode 支援多種條碼類型，包括 CODE_39、DATA_MATRIX、QR、CODE_128、EAN_13 與 AZTEC，如本教學所示。

### Q3：我該如何將 Aspose.BarCode 整合到我的 Java 專案中？

A3：只需從[此處](https://releases.aspose.com/barcode/java/)下載 Aspose.BarCode for Java 函式庫，並依照文件中的安裝說明進行設定。

### Q4：我可以在商業應用中使用 Aspose.BarCode 嗎？

A4：可以，你可從[此處](https://purchase.aspose.com/buy)取得授權，以在商業用途上使用 Aspose.BarCode。

### Q5：Aspose.BarCode 有提供試用方案嗎？

A5：當然！你可透過取得免費試用授權[此處](https://releases.aspose.com/)來體驗 Aspose.BarCode 的功能。

**其他問題**

**Q：如何在 Java 中專門產生 QR Code？**  
A：在建立 `BarcodeGenerator` 實例時使用 `EncodeTypes.QR`，如集合範例所示。

**Q：Aspose.BarCode 是否支援高解析度的列印輸出？**  
A：可以，儲存圖像時可指定 DPI，以符合列印品質需求。

---

**最後更新：** 2026-02-09  
**測試環境：** Aspose.BarCode for Java 24.11  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}