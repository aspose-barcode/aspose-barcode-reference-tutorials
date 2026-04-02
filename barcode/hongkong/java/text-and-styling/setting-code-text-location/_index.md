---
date: 2025-12-27
description: 了解如何使用 Aspose.BarCode 在 Java 中建立資料矩陣條碼以及設定條碼文字位置。請參考我們的逐步指南，完成完整客製化。
linktitle: Setting Code Text Location
second_title: Aspose.BarCode Java API
title: 在 Java 中建立 Data Matrix 條碼並設定代碼文字位置
url: /zh-hant/java/text-and-styling/setting-code-text-location/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 在 Java 中建立 Data Matrix 條碼並設定文字位置

## 簡介

產生條碼是庫存、運輸以及許多其他基於 Java 的應用程式的日常需求。使用 **Aspose.BarCode for Java**，您可以快速 **建立 Data Matrix 條碼**，並控制每個視覺細節，包括人類可讀文字出現的位置。在本教學中，我們將逐步說明 **建立 Data Matrix 條碼** 的完整流程，並示範 **如何將條碼文字設定在符號上方**，以符合您的設計規範。

## 快速答覆
- **使用的函式庫是什麼？** Aspose.BarCode for Java  
- **示範的條碼類型是？** Data Matrix  
- **如何設定文字位置？** 使用 `CodeLocation.ABOVE`  
- **正式環境是否需要授權？** 是，需要商業授權  
- **程式碼能在 Java 8 以上執行嗎？** 當然，支援 Java 8 及更高版本  

## 什麼是 Data Matrix 條碼？
Data Matrix 條碼是一種二維（2‑D）符號，以緊湊的方形或矩形圖案儲存大量資料。它廣泛用於標記小型物品、電子產品與醫療裝置，因為它可編碼多達 2,335 個字母數字字元。

## 為什麼要設定條碼文字位置？
將人類可讀文字 **放在條碼上方**、**下方** 或 **旁邊**，可讓使用者在未掃描前快速驗證編碼內容。調整文字位置有助於提升 UI 一致性，並符合品牌指引。

## 先決條件

- 具備 Java 程式設計的基本知識。  
- 已安裝 Java Development Kit (JDK)。  
- 使用 Eclipse 或 IntelliJ IDEA 等 IDE。  
- Aspose.BarCode for Java 函式庫（從 [here](https://releases.aspose.com/barcode/java/) 下載）。  

## 匯入套件

首先，將必要的 Aspose.BarCode 類別匯入您的專案：

```java
import com.aspose.barcode.generation.CodeLocation;
import com.aspose.barcode.generation.BarcodeGenerator;
```

這些匯入讓您可以使用條碼產生器以及控制文字放置的列舉型別。

## 逐步指南

### 步驟 1：定義目錄路徑
指定您要讀寫檔案的位置。請將佔位符替換為您機器上的實際路徑。

```java
String path = "Your Directory Path";
String dataDir = "Your Document Directory";
```

### 步驟 2：建立 BarcodeGenerator 實例
以 **Data Matrix** 類型建立 `BarcodeGenerator`，並提供您想要編碼的文字內容。

```java
BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.DATA_MATRIX,
        "GTIN:898978777776665655 " + "UID: 121212121212121212 " + "Batch:GH768 " + "Exp.Date:150923");
```

### 步驟 3：設定條碼文字位置
使用 `CodeLocation` 列舉將人類可讀文字移動位置。本例中，我們將文字 **放在條碼上方**。

```java
generator.getParameters().getBarcode().getCodeTextParameters().setLocation(CodeLocation.ABOVE);
```

### 步驟 4：儲存產生的條碼影像
最後，將條碼影像寫入磁碟。檔案將包含 Data Matrix 符號，且文字位於上方。

```java
generator.save(dataDir + "codetextAbove.png");
```

## 常見問題與解決方案
- **文字未顯示：** 請確認使用的 Aspose.BarCode 版本支援 `CodeLocation`。  
- **檔案路徑錯誤：** 請確認 `dataDir` 以符合作業系統的檔案分隔符 (`/` 或 `\\`) 結尾。  
- **不支援的字元：** Data Matrix 只能編碼有限的字元，請避免使用 ISO/IEC 16022 標準未包含的特殊符號。  

## 常見問與答 (FAQs)

### Q：我可以自訂產生的條碼外觀嗎？
A：可以，Aspose.BarCode 提供廣泛的自訂選項，讓您控制顏色、邊距與字型樣式。

### Q：Aspose.BarCode 是否相容於 Java 8 及更高版本？
A：當然，該函式庫支援 Java 8 以及之後的所有版本。

### Q：如何將 Aspose.BarCode 整合到現有的 Java 專案中？
A：將 Aspose.BarCode 的 JAR 檔加入專案的 classpath，匯入所需套件，即可開始產生條碼。

### Q：是否提供 Aspose.BarCode 的試用版？
A：是的，您可透過取得免費試用版 [here](https://releases.aspose.com/) 來體驗 Aspose.BarCode 的功能。

### Q：我可以從哪裡取得 Aspose.BarCode 的協助或支援？
A：請前往 [Aspose.BarCode forum](https://forum.aspose.com/c/barcode/13) 取得社群協助與官方支援。

## 其他常見問與答

**Q：我可以產生文字位於符號下方的條碼嗎？**  
A：可以，在相同的 `setLocation` 方法中設定 `CodeLocation.BELOW`。

**Q：函式庫是否支援其他 2‑D 條碼，如 QR Code？**  
A：絕對支援，只需將 `EncodeTypes.DATA_MATRIX` 改為 `EncodeTypes.QR`。

**Q：如何變更條碼文字的字型大小？**  
A：使用 `generator.getParameters().getBarcode().getCodeTextParameters().setFontSize(double size)`。

## 結論

您現在已學會如何在 Java 中 **建立 Data Matrix 條碼**，並使用 Aspose.BarCode 精確控制 **條碼文字的位置**。請嘗試其他 `CodeLocation` 值與樣式設定，以符合您應用程式的設計需求。

---

**最後更新：** 2025-12-27  
**測試環境：** Aspose.BarCode for Java 24.11  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}