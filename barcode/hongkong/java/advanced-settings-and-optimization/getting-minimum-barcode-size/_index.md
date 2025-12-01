---
date: 2025-12-01
description: 了解如何在 Java 中使用 Aspose.BarCode 建立最小條碼並設定條碼尺寸。跟隨我們的逐步指南，實現高效且節省空間的條碼產生。
language: zh-hant
linktitle: Getting Minimum BarCode Size
second_title: Aspose.BarCode Java API
title: 如何在 Java 中使用 Aspose.BarCode 建立最小條碼
url: /java/advanced-settings-and-optimization/getting-minimum-barcode-size/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 Java 中使用 Aspose.BarCode 建立最小條碼

## 介紹

如果您需要 **建立最小條碼** 圖片，使其佔用盡可能小的面積，同時仍能被掃描，這裡正是您要找的地方。在許多行動、物聯網或大量列印的應用中，每一毫米都很重要，而 Aspose.BarCode for Java 為您提供精細的控制，讓您 **設定條碼尺寸** 正好符合需求。本教學將帶您完成整個流程——從設定產生器、停用自動調整大小，到定義最小可行尺寸。

## 快速答覆
- **「最小條碼」是什麼意思？** 指仍符合條碼規格可讀性要求的最小影像尺寸。  
- **我可以使用任何條碼類型嗎？** 可以，但某些條碼規格對最小尺寸有更嚴格的限制。  
- **開發時需要授權嗎？** 免費試用可用於評估；正式上線需購買商業授權。  
- **支援哪個 Java 版本？** Java 8 或更新版本。  
- **停用 AutoSize 會影響品質嗎？** 不會，它只會阻止 Aspose 自動放大影像。

## 前置條件

在開始編寫程式碼之前，請確保您已具備：

1. **Java Development Kit (JDK)** – 已安裝並設定 Java 8 或更新版本。  
2. **Aspose.BarCode for Java** – 從官方網站下載最新程式庫：[Aspose.BarCode Java 下載](https://releases.aspose.com/barcode/java/)。  

您還需要一個資料夾（例如 `dataDir`）來儲存產生的 PNG 檔案。

## 匯入命名空間

首先，匯入產生條碼與調整尺寸所需的類別。

```java
import com.aspose.barcode.generation.AutoSizeMode;
import com.aspose.barcode.generation.BarcodeGenerator;
```

## 如何在 Java 中設定條碼尺寸

以下是一個簡潔的逐步指南，說明如何透過手動控制寬度與高度 **建立最小條碼** 圖片。

### 步驟 1：建立最小條碼 – 設定產生器
建立 `BarcodeGenerator`，選擇條碼類型（本例使用 CODE_128），並提供要編碼的資料。

```java
BarcodeGenerator bb = new BarcodeGenerator(EncodeTypes.CODE_128, "1234567");
```

### 步驟 2：停用 AutoSizeMode
預設情況下，Aspose 會自動放大影像以符合條碼規格的最小要求。關閉此功能，讓您自行定義尺寸。

```java
bb.getParameters().setAutoSizeMode(AutoSizeMode.NONE);
```

### 步驟 3：將影像高度與寬度設定為最小
現在明確設定影像大小。下列示範的數值（1 mm × 1 mm）僅供說明；請依您選擇的條碼規格調整至仍能可靠掃描的最小尺寸。

```java
bb.getParameters().getImageWidth().setMillimeters(1);
bb.getParameters().getImageHeight().setMillimeters(1);
```

> **小技巧：** 每次調整尺寸後，使用實體掃描器測試產生的條碼，以確保可讀性。

### 步驟 4：儲存條碼影像
產生位圖並寫入 PNG 檔案。將 `dataDir` 替換為您的輸出資料夾路徑。

```java
javax.imageio.ImageIO.write(bb.generateBarCodeImage(), "PNG", new java.io.File(dataDir + "minimumresult.png"));
```

對於需要產生多個最小尺寸條碼的情況，請重複上述步驟。

## 常見問題與解決方案

| 問題 | 原因 | 解決方式 |
|------|------|----------|
| 條碼無法掃描 | 尺寸對所選條碼規格太小 | 以 0.5 mm 為單位增加 `ImageWidth`/`ImageHeight`，並重新測試 |
| 影像模糊 | 影像以低 DPI 儲存 | 在儲存前使用 `bb.getParameters().getResolution().setDpi(300)` |
| 找不到 `EncodeTypes` | 未匯入 `EncodeTypes` 類別 | 加入 `import com.aspose.barcode.EncodeTypes;` |

## 常見問答

**問：我可以使用 Aspose.BarCode for Java 自訂其他條碼類型的尺寸嗎？**  
答：當然可以！Aspose.BarCode 支援多種條碼規格，您可以使用相同的 `setAutoSizeMode` 以及尺寸屬性來 **設定條碼尺寸**。

**問：Aspose.BarCode 適合企業級應用嗎？**  
答：適合。它提供高效能產生、廣泛的格式支援，且授權模式可隨企業需求擴展。

**問：商業專案需要注意哪些授權事項？**  
答：正式上線必須使用有效的商業授權。您可於 [Aspose 購買入口](https://purchase.aspose.com/buy) 取得授權。

**問：如果遇到問題，該如何取得協助？**  
答：請前往 Aspose.BarCode [論壇](https://forum.aspose.com/c/barcode/13) 尋求社群協助，或直接聯繫 Aspose 支援團隊。

**問：是否提供試用版？**  
答：提供。您可從 [Aspose.BarCode 免費試用頁面](https://releases.aspose.com/) 下載功能完整的試用版。

---

**最後更新：** 2025-12-01  
**測試環境：** Aspose.BarCode for Java 24.12（撰寫時的最新版本）  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}