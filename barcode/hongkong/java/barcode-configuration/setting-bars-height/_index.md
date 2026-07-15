---
date: 2026-02-15
description: 學習如何使用 Aspose.BarCode 在 Java 中建立 Code128 條碼、客製化條碼大小、調整條碼尺寸，並高效產生條碼圖像。
linktitle: Setting Bars Height
second_title: Aspose.BarCode Java API
title: 如何在 Java 中建立 Code128 條碼並設定條碼高度
url: /zh-hant/java/barcode-configuration/setting-bars-height/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 設定 Java 條碼的高度

## 介紹

如果您需要 **create code128 barcode java** 來列印標籤、發票或行動應用程式，您會希望能完整控制其視覺尺寸。Aspose.BarCode for Java 讓您 **customize barcode size**，設定精確的條碼高度，並即時產生符合設計需求的條碼影像。在本教學中，我們將一步步說明如何建立 CODE_128 條碼、調整其高度，並儲存影像，讓您每次都能產生尺寸完美的條碼。

## 快速回答
- **主要方法的功能是什麼？** 它會建立一個 CODE_128 條碼，並讓您設定條碼高度。  
- **使用哪個類別？** 來自 Aspose.BarCode 套件的 `BarcodeGenerator`。  
- **測試需要授權嗎？** 提供免費試用版；正式環境需購買授權。  
- **可以變更其他尺寸嗎？** 可以，您可以調整寬度、邊距及其他尺寸參數。  
- **輸出影像的格式是什麼？** 任意 Aspose.BarCode 支援的格式（如 JPEG、PNG）。  

## 什麼是 CODE_128 條碼，為什麼要設定其高度？
CODE_128 是一種高密度線性條碼，可編碼完整的 ASCII 集。調整條碼高度在條碼必須符合實體標籤尺寸或嵌入 UI 元件時尤為重要。適當的高度可確保掃描器的可讀性，同時保持視覺布局的平衡。

## 為什麼選擇 Aspose.BarCode for Java？
- **完整控制** 條碼尺寸（高度、寬度、邊距）。  
- **廣泛格式支援** – 可產生 PNG、JPEG、BMP 等多種格式。  
- **無外部相依** – 純 Java 函式庫，易於整合。  
- **豐富 API** – 輕鬆自訂顏色、文字與錯誤更正等。  

## 前置條件

開始之前，請確保您已具備：

- Java 開發環境（JDK 8 或以上）。  
- Aspose.BarCode for Java – 可從 [download link](https://releases.aspose.com/barcode/java/) 下載。  

## 匯入套件

在您的 Java 專案中，匯入提供條碼產生功能的主要類別：

```java
import com.aspose.barcode.generation.BarcodeGenerator;
```

## 如何建立 code128 barcode java 並設定其高度

### 步驟 1：初始化條碼物件

為 CODE_128 條碼建立 `BarcodeGenerator` 實例，並傳入您想編碼的資料（例如 “12345678”）。

```java
// Instantiate barcode object
BarcodeGenerator generator = new BarcodeGenerator(com.aspose.barcode.EncodeTypes.CODE_128, "12345678");
```

### 步驟 2：調整條碼尺寸 – 設定條碼高度

使用 `BarHeight` 屬性以毫米為單位定義高度。這是 **adjust barcode dimensions** 的主要方式。

```java
// Set the bar height to be 3 millimeters
generator.getParameters().getBarcode().getBarHeight().setMillimeters(3.0f);
```

> **專業提示：** 您也可以修改 `XDimension` 來改變單根條的寬度，從而完整掌控 **customize barcode size**。

### 步驟 3：儲存條碼影像 – generate barcode image java

最後，將條碼寫入檔案。`save` 方法會自動依檔案副檔名判斷影像格式。

```java
// Save the Barcode image to file
generator.save(dataDir + "barsHeight.jpg");
```

> **注意：** 請將 `dataDir` 替換為您實際想存放影像的路徑。

## 常見使用情境

- **標籤列印的條碼** – 確保條碼符合預先設定的標籤尺寸。  
- **發票產生** – 在 PDF 發票版面中嵌入尺寸匹配的緊湊條碼。  
- **行動應用程式** – 動態產生具精確尺寸的條碼，以供螢幕掃描使用。

## 疑難排解與技巧

| 問題 | 解決方案 |
|-------|----------|
| 條碼看起來太細或太粗 | 透過 `generator.getParameters().getBarcode().getXDimension().setMillimeters(value)` 調整 `XDimension`。 |
| 影像模糊 | 呼叫 `generator.save(..., BarCodeImageFormat.JPEG, 300)` 提升 DPI。 |
| 掃描器無法讀取 | 確認條碼高度符合掃描器的最小需求（通常 ≥ 2 mm）。 |

## 常見問與答

**Q: 可以在 Aspose.BarCode for Java 中自訂條碼類型嗎？**  
A: 當然可以！此函式庫支援多種符號，如 QR、DataMatrix、PDF417 等，只需在建構子中更改 `EncodeTypes` 即可。

**Q: Aspose.BarCode 是否相容於不同的 Java IDE？**  
A: 是的，無論是 Eclipse、IntelliJ IDEA、NetBeans，或任何支援標準 Java 專案的 IDE，都能順利使用。

**Q: 能產生包含數字與字母的條碼嗎？**  
A: 能，CODE_128 能編碼數字與字母，適用於大多數應用情境。

**Q: 有提供 Aspose.BarCode for Java 的試用版嗎？**  
A: 有，您可於此取得免費試用版 [here](https://releases.aspose.com/)。  

**Q: 在哪裡可以取得 Aspose.BarCode for Java 的支援？**  
A: 前往 Aspose.BarCode 論壇 [here](https://forum.aspose.com/c/barcode/13) 取得社群支援與討論。

---

**最後更新：** 2026-02-15  
**測試環境：** Aspose.BarCode for Java 24.12（最新）  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}