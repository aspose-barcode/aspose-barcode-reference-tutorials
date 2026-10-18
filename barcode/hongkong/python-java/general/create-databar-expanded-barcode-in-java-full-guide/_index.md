---
category: general
date: 2026-10-18
description: 使用 Aspose.BarCode 在 Java 中建立 DataBar Expanded 條碼。了解如何產生 DataBar、設定列數，並將條碼影像匯出為
  PNG。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create databar expanded barcode
- how to generate databar
- barcode generator rows
- export barcode image
language: zh-hant
lastmod: 2026-10-18
og_description: 在 Java 中建立 DataBar 擴充條碼。遵循本指南了解如何產生 DataBar、設定列，並將條碼圖像匯出為 PNG。
og_image_alt: Screenshot of a Databar Expanded barcode saved as PNG
og_title: 使用 Java 創建 Databar Expanded 條碼 – 逐步教學
schemas:
- author: Aspose
  dateModified: '2026-10-18'
  description: Create databar expanded barcode in Java with Aspose.BarCode. Learn
    how to generate databar, set rows, and export barcode image as PNG.
  headline: Create databar expanded barcode in Java – full guide
  type: TechArticle
tags:
- barcode
- Java
- Aspose
title: 在 Java 中建立 DataBar Expanded 條碼 – 完整指南
url: /zh-hant/python-java/general/create-databar-expanded-barcode-in-java-full-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 在 Java 中建立 Databar Expanded 條碼 – 完整指南

如果你需要在 Java 中 **建立 Databar Expanded 條碼**，本教學將會精確示範如何使用 Aspose.BarCode 函式庫 **產生 Databar** 圖片。你還會學習如何設定 **條碼產生器列** 以及 **匯出條碼圖像** 為 PNG 格式的檔案。

在以下各節中，你會找到完整、可執行的程式、每個 API 呼叫的逐步說明，以及處理常見例外情況（例如不支援的字元或自訂版面大小）的技巧。完成本指南後，你將能產生 4 欄與 3 列的 Databar Expanded 條碼，並將其儲存至任意位置。

## 前置條件

* Java 17 或更新版本（程式碼可在任何 JDK 11+ 上編譯）
* Maven 或 Gradle 來管理相依性
* Aspose.BarCode for Java – 在你的 `pom.xml` 或 `build.gradle` 中加入最新版本
* 基本熟悉 Java 的 `main` 方法與物件導向概念

```xml
<!-- Maven dependency -->
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-barcode</artifactId>
    <version>23.10</version>
</dependency>
```

> **專業提示：** 免費評估授權可用於開發；在部署至正式環境前請改用購買的授權。

## 建立 Databar Expanded 條碼 – 初始設定

第一步是建立一個 `BarcodeGenerator`，使用 `EncodeTypes.DatabarExpandedStacked` 類型並提供範例資料。此資料可以是符合 Databar 規範的任意字母數字字串。

```java
import com.aspose.barcode.*;
import com.aspose.barcode.barcodeimageformat.*;
import com.aspose.barcode.encode.*;

public class DatabarExpandedDemo {

    public static void main(String[] args) throws Exception {
        // Step 1: Create a barcode generator for Databar Expanded Stacked with sample text
        BarcodeGenerator generator = new BarcodeGenerator(
                EncodeTypes.DatabarExpandedStacked,
                "Databar Expanded Stacked long");
```

*為什麼這很重要*：`EncodeTypes.DatabarExpandedStacked` 告訴函式庫使用 Databar Expanded Stacked 符號，該符號支援比一般 Databar 更長的資料字串。

## 如何使用自訂欄位產生 Databar

Databar Expanded 允許你控制堆疊版面中的欄位數量。設定欄位在需要緊湊且仍能容納所需資料寬度的條碼時相當有用。

```java
        // Step 2: Configure a 4‑column layout for the DataBar
        generator.getParameters().getBarcode().getDataBar().setColumns(4);
```

*說明*：`setColumns(4)` 強制產生器將條碼分成四個垂直區段。函式庫會自動調整模組寬度，以保持整體尺寸合理。

## 匯出條碼圖像為 PNG – 4 欄版本

版面設定完成後，你可以將條碼匯出為檔案。PNG 是大多數 UI 情境下建議的無損格式。

```java
        // Step 3: Save the 4‑column barcode image
        generator.save("output/DatabarExpandedCols4.png", BarCodeImageFormat.Png);
```

`save` 方法會將影像寫入指定的目錄。若目錄不存在，Java 會自動建立。

## 設定條碼產生器列

除了欄位外，Databar Expanded Stacked 符號亦支援列為基礎的版面配置。將欄位切換為列可提升高解析度列印時的可讀性。

```java
        // Step 4: Create a new generator for the same data (demonstrates a different layout)
        BarcodeGenerator rowGenerator = new BarcodeGenerator(
                EncodeTypes.DatabarExpandedStacked,
                "Databar Expanded Stacked long");

        // Step 5: Configure a 3‑row layout for the DataBar
        rowGenerator.getParameters().getBarcode().getDataBar().setRows(3);
```

*為什麼使用列？* 3 列版面會將資料垂直分佈，對於水平空間受限的窄標籤特別有利。

## 匯出條碼圖像為 PNG – 3 列版本

儲存第二種版面遵循與先前相同的步驟。保持檔名不同可協助你比較視覺差異。

```java
        // Step 6: Save the 3‑row barcode image
        rowGenerator.save("output/DatabarExpandedRows3.png", BarCodeImageFormat.Png);
    }
}
```

### 預期輸出

執行程式會產生兩個 PNG 檔案：

| File name                     | Layout description                |
|------------------------------|-----------------------------------|
| `DatabarExpandedCols4.png`   | 4 欄堆疊條碼                       |
| `DatabarExpandedRows3.png`   | 3 列堆疊條碼                       |

兩張影像皆顯示相同的編碼字串，但視覺密度會依欄位或列的設定而有所不同。

## 常見陷阱與避免方法

| Issue                               | Cause                                   | Fix |
|------------------------------------|------------------------------------------|-----|
| 條碼顯示模糊                         | 以低 DPI 儲存                             | 在 `save` 前使用 `generator.getParameters().setResolution(300)`。 |
| 文字被截斷                           | 資料超出 Databar 容量                     | 縮短資料或改用 `EncodeTypes.DatabarExpanded`（非堆疊）。 |
| `NullPointerException` on `setRows`| 使用 20.12 之前的 Aspose.BarCode 版本      | 升級至最新函式庫版本。 |

## 進階變化（可選）

* **變更前景/背景顏色** – 呼叫 `generator.getParameters().getBarcode().setForeColor(Color.BLUE)` 與 `setBackColor(Color.WHITE)`。
* **產生 SVG 而非 PNG** – 將 `BarCodeImageFormat.Png` 替換為 `BarCodeImageFormat.Svg`。
* **將條碼嵌入 PDF** – 使用 Aspose.PDF 建立文件，並將 PNG 作為影像加入。

## 結論

現在你已了解如何在 Java 中 **建立 Databar Expanded 條碼**、如何在欄位與列配置下 **產生 Databar**，以及如何 **匯出條碼圖像** 為 PNG 格式。完整的原始碼已可直接複製、貼上並在任何 Java 專案中執行。

歡迎嘗試其他版面、顏色或輸出格式。如果你覺得本指南對你有幫助，建議進一步閱讀 Aspose.BarCode 文件，了解如 *micro‑PDF417*、*QR code 錯誤更正* 與 *條碼掃描* 等主題。

祝開發順利！

## 接下來該學什麼？

以下教學涵蓋與本指南密切相關的主題，並以此為基礎延伸技術。每個資源皆提供完整可執行的程式碼範例與逐步說明，協助你精通其他 API 功能，並在自己的專案中探索替代實作方式。

- [如何在 Java 產生條碼：建立精確條碼圖像](/barcode/english/java/barcode-basics/creating-image-exact-barcode/)
- [Databar Expanded Stacked 條碼指南 – 如何在 C# 產生與調整大小](/barcode/english/python-java/general/databar-expanded-stacked-barcode-guide-how-to-generate-and-s/)
- [如何在 C# 建立全向 Databar 條碼](/barcode/english/python-java/general/how-to-create-omnidirectional-databar-barcode-in-c/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}