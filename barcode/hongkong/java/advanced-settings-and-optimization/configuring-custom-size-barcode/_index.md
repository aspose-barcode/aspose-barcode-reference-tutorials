---
date: 2026-09-13
description: 了解如何在 Java 中設定自訂條碼尺寸，並使用 Aspose.BarCode for Java 產生條碼影像，只需幾個簡單步驟。
keywords:
- custom barcode size java
- barcode size for printing
- custom barcode for labels
- how to set barcode size
lastmod: 2026-09-13
linktitle: 設定條碼自訂尺寸
og_description: 了解如何使用 Aspose.BarCode for Java 設定自訂條碼尺寸。本指南提供逐步程式碼示例，協助控制條碼尺寸以供列印與
  UI 整合。
og_image_alt: Guide showing Java code to configure exact barcode dimensions with Aspose.BarCode
og_title: 如何使用 Aspose.BarCode 在 Java 中設定自訂條碼尺寸
schemas:
- author: Aspose
  dateModified: '2026-09-13'
  description: Learn how to set custom barcode size java and generate barcode images
    using Aspose.BarCode for Java in a few simple steps.
  headline: How to set custom barcode size java with Aspose.BarCode
  type: TechArticle
- questions:
  - answer: Yes, Aspose.BarCode for Java supports a wide range of symbologies. Replace
      `EncodeTypes.CODE_39_STANDARD` with the desired type, such as `EncodeTypes.QR`
      or `EncodeTypes.DATA_MATRIX`.
    question: Can I customize the symbology type for my barcode?
  - answer: Yes, you can explore the capabilities of Aspose.BarCode by obtaining a
      free trial **[from the Aspose releases page](https://releases.aspose.com/)**.
    question: Is there a trial version available?
  - answer: Refer to the comprehensive documentation **[Aspose.BarCode Java reference](https://reference.aspose.com/barcode/java/)**
      for in‑depth information on Aspose.BarCode for Java.
    question: Where can I find detailed documentation?
  - answer: Visit the Aspose.BarCode forum **[Aspose.BarCode community forum](https://forum.aspose.com/c/barcode/13)**
      to seek assistance and connect with the community.
    question: How can I get support for any issues or queries?
  - answer: Yes, you can acquire a temporary license **[on the temporary license page](https://purchase.aspose.com/temporary-license/)**
      for testing purposes.
    question: Is there a temporary license option available?
  type: FAQPage
second_title: Aspose.BarCode Java API
tags:
- custom barcode size
- Aspose.BarCode
- Java barcode
- barcode for printing
- custom barcode for labels
title: 如何使用 Aspose.BarCode 在 Java 中設定自訂條碼尺寸
url: /zh-hant/java/advanced-settings-and-optimization/configuring-custom-size-barcode/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 Java 中使用 Aspose.BarCode 設定自訂條碼尺寸

## 介紹

如果您是需要 **custom barcode size java** 的 Java 開發人員，Aspose.BarCode for Java 可讓您輕鬆完成。在本教學中，您將學習如何在 Java 中產生具備精確寬度與高度的條碼影像，讓您全面掌控版面配置、列印與 UI 整合。

## 快速解答
- **需要的函式庫是什麼？** Aspose.BarCode for Java（提供免費試用）。  
- **可以設定精確的寬度與高度嗎？** 可以——使用 `ImageWidth` 與 `ImageHeight` 屬性（單位為毫米）。  
- **開發時需要授權嗎？** 暫時或試用授權可用於測試；正式環境需購買正式授權。  
- **哪些條碼符號支援自訂尺寸？** 大多數 1‑D 與 2‑D 符號皆支援，包括 Code 39、QR 與 DataMatrix。  
- **實作需要多久？** 基本的自訂尺寸條碼通常在 10 分鐘以內完成。

## 什麼是自訂條碼尺寸（Java）？

Custom barcode size java 讓您自行決定產生影像的實體尺寸，而不必依賴函式庫的自動調整演算法。當標籤、收據或嵌入式 PDF 必須精確到毫米時，此功能相當重要，因為它可確保列印出的條碼符合設計規格，且在各種裝置上皆能順利掃描。

## 為何要設定自訂條碼尺寸？

設定自訂條碼尺寸可確保條碼以掃描器所需的大小列印，與周圍的 UI 元件完美對齊，減少不必要的檔案大小，並協助您符合行業特定的尺寸規範。精確的控制亦能防止響應式設計中的版面移位，避免因尺寸不符而產生昂貴的重新列印。

## 前置條件

- 具備 Java 程式設計的基本知識。  
- Java 開發環境（IDE、JDK 8 以上）。  
- 已安裝 Aspose.BarCode for Java 函式庫——請從 **[Aspose.BarCode Java 下載頁面](https://releases.aspose.com/barcode/java/)** 下載。

## 匯入命名空間

`com.aspose.barcode` 套件提供處理條碼所需的全部類別。請在 Java 檔案的開頭匯入以下類別：

```java
import com.aspose.barcode.generation.AutoSizeMode;
import com.aspose.barcode.generation.BarcodeGenerator;
```

## 步驟 1：設定資源目錄路徑

定義產生的條碼影像要儲存的位置。使用專屬的 `dataDir` 資料夾可讓專案保持有序，並避免 `FileNotFoundException`。

```java
// The path to the resource directory.
String dataDir = "Your Document Directory";
```

> **小技巧：** 使用絕對路徑或相對於專案 `resources` 資料夾的路徑，可避免 `FileNotFoundException`。

## 步驟 2：實例化條碼物件

`BarcodeGenerator` 類別用於建立與設定條碼影像。建立 `BarcodeGenerator` 實例，指定條碼類型（例如 Code 39）與要編碼的資料：

```java
// Instantiate barcode object, Set the Code text for the barcode and the
// symbology type to Code39Standard
BarcodeGenerator generator = new BarcodeGenerator(com.aspose.barcode.EncodeTypes.CODE_39_STANDARD,
        "1234567890");
```

您可以將 `EncodeTypes.CODE_39_STANDARD` 替換為其他支援的條碼類型，例如 `EncodeTypes.QR` 或 `EncodeTypes.DATA_MATRIX`。

## 步驟 3：停用自動尺寸

關閉自動尺寸功能，以便自行設定尺寸：

```java
// Set auto size false
generator.getParameters().setAutoSizeMode(AutoSizeMode.NEAREST);
```

`NEAREST` 模式會停用自動尺寸，同時仍保留條碼的可讀性。

## 步驟 4：設定高度

以毫米為單位指定所需的高度。此處設定為 **50 mm**：

```java
// Set height
generator.getParameters().getImageHeight().setMillimeters(50);
```

## 步驟 5：設定寬度

以毫米為單位定義寬度——本例為 **120 mm**：

```java
// Set width
generator.getParameters().getImageWidth().setMillimeters(120);
```

> **為何使用毫米？** 使用實體單位可確保條碼在列印時達到精確尺寸，且不受螢幕 DPI 影響。

## 步驟 6：儲存影像

最後，產生並將條碼影像儲存至先前定義的目錄：

```java
// Save the image
generator.save(dataDir + "barcode-custom-size.jpg");
```

`save` 方法會自動產生高品質的 JPEG（您亦可選擇 PNG、BMP 等格式）。

### 背後的運作原理？

當呼叫 `save` 時，Aspose.BarCode 會根據您設定的尺寸繪製條碼、編碼資料，並寫入影像檔案。由於已停用自動尺寸，函式庫會遵循您提供的精確寬高，產生完美貼合版面的條碼。

## 常見問題與解決方案

| 問題 | 原因 | 解決方案 |
|------|------|----------|
| 條碼顯示拉伸 | 寬高比例與條碼類型不相容 | 保持所選條碼類型建議的長寬比（請參考 Aspose 文件）。 |
| 掃描器無法讀取條碼 | 尺寸過小 | 確保符合條碼規範的最小尺寸（例如 Code 39 高度至少 15 mm）。 |
| 影像未儲存 | `dataDir` 路徑無效 | 在儲存前使用 `new File(dataDir).mkdirs();`，或提供絕對路徑。 |

## 常見問答

**Q: 我可以自訂條碼的符號類型嗎？**  
A: 可以，Aspose.BarCode for Java 支援多種條碼符號。將 `EncodeTypes.CODE_39_STANDARD` 替換為您想要的類型，例如 `EncodeTypes.QR` 或 `EncodeTypes.DATA_MATRIX`。

**Q: 是否提供試用版？**  
A: 可以，您可從 **[Aspose 下載頁面](https://releases.aspose.com/)** 取得免費試用版，以探索 Aspose.BarCode 的功能。

**Q: 哪裡可以找到詳細文件？**  
A: 請參考完整文件 **[Aspose.BarCode Java 參考文件](https://reference.aspose.com/barcode/java/)**，以取得 Aspose.BarCode for Java 的深入資訊。

**Q: 如何取得問題或諮詢的支援？**  
A: 請前往 Aspose.BarCode 論壇 **[Aspose.BarCode 社群論壇](https://forum.aspose.com/c/barcode/13)** 尋求協助並與社群交流。

**Q: 是否有臨時授權選項？**  
A: 可以，您可於 **[臨時授權頁面](https://purchase.aspose.com/temporary-license/)** 取得臨時授權以供測試使用。

**Q: 我可以產生 PNG 格式的條碼影像（Java）而非 JPEG 嗎？**  
A: 當然可以。使用 `generator.save(dataDir + "barcode.png", com.aspose.barcode.BarCodeImageFormat.PNG);` 輸出 PNG。

**Q: 如果之後需要將條碼嵌入 PDF 該怎麼辦？**  
A: 產生影像後，您可將其載入任意 PDF 函式庫（例如 Aspose.PDF），並使用該函式庫的影像插入 API 將其放置於頁面上。

## 結論

透過這七個簡單步驟，您即可掌控使用 Aspose.BarCode for Java 產生的任何條碼的精確寬度與高度。此精確度有助於符合列印標準、保持 UI 版面整潔，並遵守行業規範，同時不影響掃描可靠性。

**最後更新：** 2026-09-13  
**測試環境：** Aspose.BarCode for Java 24.11  
**作者：** Aspose

## 相關教學

- [使用 Aspose 建立條碼 - 在 Java 中設定 X 與 Y 尺寸](/barcode/java/barcode-configuration/managing-x-y-dimension-barcode/)
- [如何在 Java 中產生條碼：建立與設定整體圖片尺寸](/barcode/java/barcode-basics/creating-setting-size-whole-picture-barcode/)
- [如何在 Java 中使用 Aspose.BarCode 建立小尺寸條碼標籤](/barcode/java/advanced-settings-and-optimization/getting-minimum-barcode-size/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}