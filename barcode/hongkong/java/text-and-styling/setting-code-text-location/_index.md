---
date: 2026-05-04
description: 學習如何使用 Java 條碼函式庫建立資料矩陣條碼，並使用 Aspose.BarCode 將條碼文字位置設定在符號上方。請參考我們的一步一步條碼產生範例。
keywords:
- java barcode library
- barcode generation example
- barcode text above
- customize barcode text
linktitle: 設定程式碼文字位置
second_title: Aspose.BarCode Java API
title: 使用 Java 條碼庫建立 Data Matrix 條碼並設定代碼文字位置
url: /zh-hant/java/text-and-styling/setting-code-text-location/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 使用 Java 條碼庫建立 Data Matrix 條碼並設定代碼文字位置

## 簡介

如果您正在使用 Java 建立庫存、運輸或追蹤系統，您會很快發現可靠的 **java barcode library** 是必不可少的。使用 **Aspose.BarCode for Java**，您只需幾行程式碼即可產生 **Data Matrix barcode**，並完整控制視覺版面配置，包括人類可讀文字的顯示位置。在本教學中，我們將逐步說明完整的 **barcode generation example**，示範如何 **customize barcode text** 的放置，並解釋為何將文字置於符號上方可以提升可用性。

## 快速回答
- **使用的函式庫是什麼？** Aspose.BarCode for Java  
- **示範的條碼類型是什麼？** Data Matrix  
- **如何設定代碼文字的位置？** Using `CodeLocation.ABOVE` (you can also use `BELOW`)  
- **生產環境是否需要授權？** Yes, a commercial license is required  
- **程式碼能在 Java 8 以上執行嗎？** Absolutely, it supports Java 8 and later  

## 什麼是 Java 條碼庫？

A **java barcode library** provides developers with ready‑made APIs to create, read, and style 1‑D and 2‑D barcodes directly from Java applications. It abstracts the complex encoding rules and lets you focus on business logic instead of low‑level image processing.

## 為何在條碼產生範例中使用 Java 條碼庫？

- **Speed:** 以毫秒級別產生高品質條碼。  
- **Reliability:** 內建符合 ISO/IEC 標準。  
- **Flexibility:** 完全掌控尺寸、顏色、邊距，以及 **barcode text** 的放置。  
- **Cross‑platform:** 可於任何基於 JVM 的環境執行，從桌面應用程式到雲端服務皆適用。

## 什麼是 Data Matrix 條碼？

A Data Matrix barcode is a two‑dimensional (2‑D) symbol that stores large amounts of data in a compact square or rectangular pattern. It’s widely used for marking small items, electronics, and medical devices because it can encode up to 2,335 alphanumeric characters.

## 為何設定條碼文字位置？

將人類可讀文字 **above**、**below** 或 **beside** 條碼，可協助使用者在未掃描時快速驗證編碼資料。調整文字位置能提升 UI 一致性、符合品牌指引，並減少手動輸入資料時的錯誤。

## 先決條件

- 具備 Java 程式設計的基礎知識。  
- 已安裝 Java Development Kit (JDK)。  
- 使用 Eclipse 或 IntelliJ IDEA 等 IDE。  
- Aspose.BarCode for Java 函式庫（從 [here](https://releases.aspose.com/barcode/java/) 下載）。

## 匯入套件

首先，將必要的 Aspose.BarCode 類別匯入您的專案：

```java
import com.aspose.barcode.generation.CodeLocation;
import com.aspose.barcode.generation.BarcodeGenerator;
```

## 逐步指南

### 步驟 1：定義目錄路徑
指定要讀寫檔案的位置。將佔位符替換為您機器上的實際路徑。

```java
String path = "Your Directory Path";
String dataDir = "Your Document Directory";
```

### 步驟 2：建立 BarcodeGenerator 實例
使用 **Data Matrix** 類型實例化 `BarcodeGenerator`，並提供您想要編碼的代碼文字。

```java
BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.DATA_MATRIX,
        "GTIN:898978777776665655 " + "UID: 121212121212121212 " + "Batch:GH768 " + "Exp.Date:150923");
```

### 步驟 3：設定條碼文字位置（自訂條碼文字）
使用 `CodeLocation` 列舉來移動人類可讀文字。在此範例中，我們將文字放置於條碼 **above**。

```java
generator.getParameters().getBarcode().getCodeTextParameters().setLocation(CodeLocation.ABOVE);
```

> **專業提示：** 若要將文字放在符號 **below**，只需將 `CodeLocation.ABOVE` 改為 `CodeLocation.BELOW`。

### 步驟 4：儲存產生的條碼影像
最後，將條碼影像寫入磁碟。檔案將包含 Data Matrix 符號，且文字位於其上方。

```java
generator.save(dataDir + "codetextAbove.png");
```

## 常見問題與解決方案
- **Text not appearing:** 確認您使用的 Aspose.BarCode 版本支援 `CodeLocation`。  
- **File path errors:** 確認 `dataDir` 以適合您作業系統的檔案分隔符（`/` 或 `\\`）結尾。  
- **Unsupported characters:** Data Matrix 只能編碼有限的字元集；請避免使用 ISO/IEC 16022 標準未包含的特殊符號。  

## 常見問題 (FAQs)

### Q：我可以自訂產生的條碼外觀嗎？
A：可以，Aspose.BarCode 提供廣泛的自訂選項，讓您控制顏色、邊距與字型樣式。

### Q：Aspose.BarCode 是否相容於 Java 8 及更高版本？
A：當然，該函式庫支援 Java 8 以及之後的所有版本。

### Q：我該如何將 Aspose.BarCode 整合到現有的 Java 專案中？
A：將 Aspose.BarCode 的 JAR 檔案加入專案的 classpath，匯入所需套件，即可開始產生條碼。

### Q：是否提供 Aspose.BarCode 的試用版？
A：是的，您可透過取得免費試用版於 [here](https://releases.aspose.com/) 來體驗 Aspose.BarCode 的功能。

### Q：我可以在哪裡尋求 Aspose.BarCode 的協助或支援？
A：請前往 [Aspose.BarCode forum](https://forum.aspose.com/c/barcode/13) 取得社群協助與官方支援。

## 其他常見問題

**Q：我可以產生文字位於符號下方的條碼嗎？**  
A：可以，在相同的 `setLocation` 方法中設定 `CodeLocation.BELOW`。

**Q：函式庫是否支援其他 2‑D 條碼，例如 QR Code？**  
A：當然，只需將 `EncodeTypes.DATA_MATRIX` 改為 `EncodeTypes.QR`。

**Q：我該如何變更條碼文字的字型大小？**  
A：使用 `generator.getParameters().getBarcode().getCodeTextParameters().setFontSize(double size)`。

## 結論

您現在已學會如何在 Java 中使用 **java barcode library** **create a Data Matrix barcode**，並透過 Aspose.BarCode 精確控制 **how to set barcode text** 位置。請嘗試其他 `CodeLocation` 值、字型設定與顏色選項，以符合您應用程式的設計需求。

---

**最後更新：** 2026-05-04  
**測試環境：** Aspose.BarCode for Java 24.11  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}