---
date: 2025-11-29
description: 學習如何在 Java 中使用 Aspose.BarCode 讀取 1D 條碼 – 使用功能強大的 Java 條碼庫快速從圖像解碼條碼。
linktitle: read 1d barcodes java
second_title: Aspose.BarCode Java API
title: 如何在 Java 中使用 Aspose.BarCode 讀取一維條碼
url: /zh-hant/java/advanced-settings-and-optimization/getting-all-possible-1d-barcodes-image/
weight: 20
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 使用 Aspose.BarCode 讀取 1D 條碼（Java）

## 介紹

在本實作指南中，您將學會如何使用功能強大的 **Aspose.BarCode** 程式庫 **在 Java 中讀取 1D 條碼**。無論您需要掃描產品標籤、庫存標籤，或是任何嵌入於影像中的線性條碼，本教學都會一步步帶您完成——從環境設定到擷取影像中所有可能的條碼。完成後，您只需幾行 Java 程式碼，即可 **從影像檔案解碼條碼**。

## 快速回答
- **Aspose.BarCode 有什麼功能？** 它提供完整的 Java 條碼程式庫，能產生與解碼 1D/2D 條碼。  
- **可以從同一張影像讀取多個條碼嗎？** 可以——`BarCodeReader.readBarCodes()` 方法會回傳所有偵測到的符號。  
- **開發時需要授權嗎？** 測試可使用臨時授權；正式上線則需商業授權。  
- **支援哪些 Java 版本？** Java 8 以上（建議使用 JDK 11）。  
- **此程式庫的速度足以即時掃描嗎？** 絕對足夠——已針對高效能批次處理進行最佳化。

## 什麼是「read 1d barcodes java」？

在 Java 中讀取 1D 條碼即是使用 **Java 條碼程式庫** 解析影像、定位線性條碼圖樣，並回傳編碼文字以及符號類型、方向等中繼資料。Aspose.BarCode 把繁重的影像處理工作抽象化，讓您專注於業務邏輯。

## 為何選擇 Aspose.BarCode 來解碼影像中的條碼？

- **支援廣泛的符號集**——超過 50 種 1D 與 2D 類型。  
- **偵測精準**——即使在低對比或旋轉的條碼上亦能正常運作。  
- **API 簡潔**——幾個方法呼叫即可取得全部結果。  
- **無外部相依**——純 Java，易於嵌入任何專案。  

## 前置需求

在撰寫程式碼之前，請先確保您已具備以下項目：

- **Java Development Kit (JDK)**——版本 8 或更新。可從官方 [Oracle JDK page](https://www.oracle.com/java/technologies/javase-downloads.html) 下載。  
- **Aspose.BarCode for Java**——從 [Aspose release page](https://releases.aspose.com/barcode/java/) 取得最新 JAR。  

環境準備完成後，我們即可開始編寫程式。

## 匯入命名空間

加入必要的 `import` 陳述式，讓編譯器能找到 Aspose 的類別。

```java
import java.awt.Point;

import com.aspose.barcode.barcoderecognition.BarCodeReader;
import com.aspose.barcode.barcoderecognition.BarCodeResult;
import com.aspose.barcode.barcoderecognition.DecodeType;
```

## 步驟 1：初始化 BarCodeReader 物件

建立指向影像檔案的 `BarCodeReader` 實例。`DecodeType` 參數告訴引擎要偵測哪些符號類型；以 `CODE_128` 為例，可涵蓋多數常見的 1D 條碼。

```java
BarCodeReader reader = new BarCodeReader("path/to/your/image.png", DecodeType.CODE_128);
```

> **小技巧：** 若想掃描 *所有* 支援的 1D 類型，請傳入 `DecodeType.ALL_1D`，而非單一符號。

## 步驟 2：讀取所有可能的條碼

遍歷 `readBarCodes()` 回傳的集合。對每個 `BarCodeResult`，我們會印出解碼文字、符號名稱、偵測角度，以及條碼區域的四個角座標。

```java
int iCount = 0;
for (BarCodeResult result : reader.readBarCodes()) {
    // Display code text, symbology, detected angle, recognition percentage of the barcode
    System.out.println("Code Text: " + result.getCodeText() + " Symbology: " + result.getCodeTypeName()
            + " Recognition percentage: " + result.getRegion().getAngle());

    // Display x and y coordinates of barcode detected
    Point[] point = result.getRegion().getPoints();

    System.out.println("Top left coordinates: X = " + point[0].getX() + ", Y = " + point[0].getY());
    System.out.println("Bottom left coordinates: X = " + point[1].getX() + ", Y = " + point[1].getY());
    System.out.println("Bottom right coordinates: X = " + point[2].getX() + ", Y = " + point[2].getY());
    System.out.println("Top right coordinates: X = " + point[3].getX() + ", Y = " + point[3].getY());

    iCount = iCount + 1;
}
```

此迴圈會自動處理找到的每一個條碼，無需重複呼叫讀取器。迴圈結束後，`iCount` 便保存了偵測到的條碼總數。

## 常見問題與解決方式

| 症狀 | 可能原因 | 解決方案 |
|------|----------|----------|
| 沒有回傳條碼 | 影像過於模糊或對比度低 | 在送入讀取器前先前處理影像（提升對比、二值化）。 |
| 符號類型錯誤 | 使用了不正確的 `DecodeType` | 改用 `DecodeType.ALL_1D` 讓引擎自動偵測任何 1D 類型。 |
| 角度數值不正確 | 影像已旋轉 | API 已回傳旋轉角度，必要時可自行將影像旋回正向。 |

## 常見問答

**Q: Aspose.BarCode for Java 可用於商業專案嗎？**  
A: 可以。商業授權會移除所有評估限制，並授予完整的再發佈權限。

**Q: 可以在未購買授權的情況下測試程式庫嗎？**  
A: 當然可以。可從 [Aspose temporary‑license page](https://purchase.aspose.com/temporary-license/) 取得臨時授權，用於開發與測試。

**Q: 完整的 API 參考文件在哪裡？**  
A: 完整文件可在 [here](https://reference.aspose.com/barcode/java/) 找到。

**Q: 若遇到問題該向誰求助？**  
A: 可在 [Aspose.BarCode forum](https://forum.aspose.com/c/barcode/13) 發問，社群與 Aspose 工程師會提供協助。

**Q: 有免費試用版可以下載嗎？**  
A: 有——可從 [Aspose releases page](https://releases.aspose.com/) 下載試用版本。

## 結論

您現在已掌握如何使用 Aspose.BarCode 這套強大的 **Java 條碼程式庫**，在 Java 中 **讀取 1D 條碼**，並輕鬆從影像檔案解碼條碼。將此程式碼片段整合至自己的應用程式，即可自動化庫存掃描、票證驗證，或任何需要在影像中辨識線性條碼的情境。

---

**最後更新：** 2025-11-29  
**測試環境：** Aspose.BarCode 24.11 for Java  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}