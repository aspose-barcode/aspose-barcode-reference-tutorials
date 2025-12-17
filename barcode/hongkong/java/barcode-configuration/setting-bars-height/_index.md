---
date: 2025-12-16
description: 學習如何在 Java 中使用 Aspose.BarCode 建立 Code_128 條碼，客製化條碼尺寸、設定條碼高度，並有效率地產生條碼圖像。
linktitle: Setting Bars Height
second_title: Aspose.BarCode Java API
title: 如何在 Java 中建立 code_128 條碼並設定條碼高度
url: /zh-hant/java/barcode-configuration/setting-bars-height/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 在 Java 中設定條碼高度

## Introduction

在現代的 Java 應用程式中，您常常需要 **建立 code_128 條碼** 圖片，以符合報表、標籤或收據的精確視覺設計。Aspose.BarCode for Java 讓這變得簡單，您可以 **自訂條碼尺寸**、調整尺寸，並即時產生 Java 可直接儲存的條碼圖像。在本教學中，我們將說明在產生 CODE_128 條碼時如何設定條碼高度，讓您每次都能產出尺寸恰當的條碼。

## Quick Answers
- **主要方法的功能是什麼？** 它會建立 CODE_128 條碼，並讓您設定條碼的高度。  
- **使用哪個類別？** 來自 Aspose.BarCode 函式庫的 `BarcodeGenerator`。  
- **測試是否需要授權？** 提供免費試用版；正式環境需購買授權。  
- **可以調整其他尺寸嗎？** 可以，您能調整寬度、邊距及其他尺寸參數。  
- **輸出圖像的格式為何？** 任意 Aspose.BarCode 支援的格式（例如 JPEG、PNG）。  

## What is a CODE_128 barcode and why set its height?

CODE_128 是一種高密度線性條碼，可編碼完整的 ASCII 集。當條碼必須與實體標籤尺寸對齊或適配於 UI 元件時，調整條碼高度是必須的。適當的高度可確保掃描器的可讀性，同時保持視覺版面的平衡。

## Why use Aspose.BarCode for Java?
- **完整控制** 條碼尺寸（高度、寬度、邊距）。  
- **廣泛的格式支援** – 可產生 PNG、JPEG、BMP 等多種格式。  
- **無外部相依性** – 純 Java 函式庫，易於整合。  
- **豐富的 API** – 輕鬆自訂顏色、文字與錯誤更正。

## Prerequisites

在開始之前，請確保您已具備：

- Java 開發環境（JDK 8 或以上）。  
- Aspose.BarCode for Java – 從 [download link](https://releases.aspose.com/barcode/java/) 下載。

## Import Packages

在您的 Java 專案中，匯入提供條碼產生功能的主要類別：

```java
import com.aspose.barcode.generation.BarcodeGenerator;
```

## How to create code_128 barcode and set its height

### Step 1：初始化條碼物件

建立一個 `BarcodeGenerator` 實例，用於產生 CODE_128 條碼，並傳入您想編碼的資料（例如 “12345678”）。

```java
// Instantiate barcode object
BarcodeGenerator generator = new BarcodeGenerator(com.aspose.barcode.EncodeTypes.CODE_128, "12345678");
```

### Step 2：調整條碼尺寸 – 設定條碼高度

使用 `BarHeight` 屬性以毫米為單位定義高度。這是 **設定條碼高度** 的主要方式。

```java
// Set the bar height to be 3 millimeters
generator.getParameters().getBarcode().getBarHeight().setMillimeters(3.0f);
```

> **專業提示：** 您也可以修改 `XDimension` 以變更單根條的寬度，從而完整掌控 **調整條碼尺寸**。

### Step 3：儲存條碼圖像 – generate barcode image java

最後，將條碼寫入檔案。`save` 方法會自動根據檔案副檔名判斷圖像格式。

```java
// Save the Barcode image to file
generator.save(dataDir + "barsHeight.jpg");
```

> **注意：** 請將 `dataDir` 替換為您希望儲存圖像的實際路徑。

## Common Use Cases

- **標籤列印** – 確保條碼符合預先設定的標籤尺寸。  
- **發票產生** – 嵌入與 PDF 發票版面相匹配的緊湊條碼。  
- **行動應用程式** – 動態產生具精確尺寸的條碼，以供螢幕掃描使用。

## Troubleshooting & Tips

| 問題 | 解決方案 |
|-------|----------|
| 條碼顯示過細或過粗 | 透過 `generator.getParameters().getBarcode().getXDimension().setMillimeters(value)` 調整 `XDimension`。 |
| 圖像模糊 | 呼叫 `generator.save(..., BarCodeImageFormat.JPEG, 300)` 提高 DPI。 |
| 掃描器無法讀取條碼 | 確認條碼高度符合掃描器的最小需求（通常 ≥ 2 mm）。 |

## Frequently Asked Questions

**問：我可以在 Aspose.BarCode for Java 中自訂條碼類型嗎？**  
**答：當然可以！此函式庫支援多種符號，如 QR、DataMatrix、PDF417 等，只需在建構子中變更 `EncodeTypes` 即可。**

**問：Aspose.BarCode 是否相容於不同的 Java IDE？**  
**答：是的，它可無縫運作於 Eclipse、IntelliJ IDEA、NetBeans 以及任何支援標準 Java 專案的 IDE。**

**問：我能產生包含數字與字母的條碼嗎？**  
**答：可以，CODE_128 能編碼數字與字母混合的資料，適用於大多數應用情境。**

**問：是否提供 Aspose.BarCode for Java 的試用版？**  
**答：有的，您可透過此免費試用版 [here](https://releases.aspose.com/) 了解 Aspose.BarCode 的功能。**

**問：在哪裡可以取得 Aspose.BarCode for Java 的支援？**  
**答：請前往 Aspose.BarCode 論壇 [here](https://forum.aspose.com/c/barcode/13) 獲得社群支援與討論。**

---

**最後更新：** 2025-12-16  
**測試環境：** Aspose.BarCode for Java 24.12（最新）  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}