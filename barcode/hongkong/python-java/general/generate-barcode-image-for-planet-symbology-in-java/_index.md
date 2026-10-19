---
category: general
date: 2026-10-18
description: 使用 Java 產生行星符號的條碼圖像。學習如何使用自訂條碼尺寸和空白條製作行星條碼。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate barcode image
- create planet barcode
- custom barcode dimensions
language: zh-hant
lastmod: 2026-10-18
og_description: 在 Java 中產生 Planet 符號的條碼圖像。本教學示範如何使用自訂條碼尺寸與外框條，建立 Planet 條碼。
og_image_alt: Generated barcode image showing a Planet barcode with empty outline
  bars
og_title: 為 Planet 符號學產生條碼圖像 – Java 指南
schemas:
- author: Aspose
  dateModified: '2026-10-18'
  description: Generate barcode image for Planet symbology using Java. Learn to create
    planet barcode with custom barcode dimensions and empty bars.
  headline: Generate barcode image for Planet symbology in Java
  type: TechArticle
tags:
- barcode
- Java
- imaging
title: 使用 Java 為 Planet 符號生成條碼圖像
url: /zh-hant/python-java/general/generate-barcode-image-for-planet-symbology-in-java/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 產生 Planet 符號的條碼圖像（Java）

如果您需要 **產生條碼圖像** 用於 Planet 符號，本指南將帶您完成整個流程。無論您是構建郵件自動化系統或自訂追蹤解決方案，您都將學會如何 **建立 planet 條碼**，並設定 **自訂條碼尺寸** 以及輪廓（空心）條。

本範例使用 Aspose.BarCode for Java 函式庫，提供對所有主要條碼標準的流暢 API。無需額外的影像處理工具，程式碼可在任何 Java 8+ 執行環境上執行。

## 前置條件

* 已安裝 Java 8 或更新版本（本教學已在 JDK 17 上測試）。
* Maven 或 Gradle 以管理相依性。
* 具備 Java 語法與條碼概念的基本認識。

如果您是 Maven 新手，可以使用 `mvn archetype:generate` 建立簡易專案，並加入下方顯示的 Aspose.BarCode 相依性。

## 新增 Aspose.BarCode 相依性

```xml
<!-- pom.xml -->
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-barcode</artifactId>
    <version>23.12</version> <!-- Use the latest version available -->
</dependency>
```

> **專業提示：** 鎖定版本號，以避免函式庫更新時出現意外的破壞性變更。

## 步驟 1：為 Planet 符號初始化條碼產生器

```java
import com.aspose.barcode.BarCodeImageFormat;
import com.aspose.barcode.EncodeTypes;
import com.aspose.barcode.generator.BarcodeGenerator;

public class PlanetBarcodeDemo {
    public static void main(String[] args) {
        // Step 1 – create a generator that encodes data using the Planet symbology
        BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
                EncodeTypes.PLANET,          // Planet is the barcode type
                "123456");                   // Data to encode
```

**此步驟的重要性：**  
`EncodeTypes.PLANET` 告訴函式庫使用 Planet 條碼規範，該規範常用於郵務服務。資料字串 `"123456"` 為將顯示於產生圖像中的內容。

## 步驟 2：設定自訂條碼尺寸（X 維度）

```java
        // Step 2 – adjust the X dimension (module width) to 4 pixels.
        // This controls the thickness of each bar.
        barcodeGenerator.getParameters()
                        .getBarcode()
                        .getXDimension()
                        .setPixels(4);
```

**此步驟的重要性：**  
*X 維度* 定義每條單獨條的寬度。將其設為 **4 像素** 後，可得到大多數掃描器易於辨識且仍能容納於標準標籤上的條碼。變更此數值是實現 **自訂條碼尺寸** 的主要方式。

## 步驟 3：使用空心（輪廓）條而非實心條

```java
        // Step 3 – configure the generator to draw empty bars (outline only)
        barcodeGenerator.getParameters()
                        .getBarcode()
                        .setFilledBars(false);
```

**此步驟的重要性：**  
`setFilledBars(false)` 告訴渲染器僅繪製條的輪廓，內部保持透明。此樣式常在背景可能包含其他印刷資訊的郵務條碼中需要使用。

## 步驟 4：將條碼圖像儲存為 PNG

```java
        // Step 4 – save the generated barcode as a PNG file
        String outputPath = "output/PlanetEmptyBars.png";
        barcodeGenerator.save(outputPath, BarCodeImageFormat.Png);

        System.out.println("Barcode image generated at: " + outputPath);
    }
}
```

**此步驟的重要性：**  
選擇 `BarCodeImageFormat.Png` 可取得無損圖像，保留輪廓條的清晰邊緣。檔案路徑可為任何您有寫入權限的目錄；範例使用相對於專案根目錄的 `output` 資料夾。

### 預期輸出

執行程式會產生類似下圖的檔案：

![Planet 符號產生的條碼圖像](/images/planet-barcode.png){.align-center alt="產生的條碼圖像顯示 Planet 條碼，使用空心輪廓條"}

圖像顯示一個 **Planet 條碼**，條紋細且為空心，完全符合您設定的自訂尺寸。

## 常見變化與邊緣情況

| 情況 | 調整 |
|-----------|------------|
| **不同的資料長度** | Planet 條碼支援最多 12 個數字字元。請相應更改建構子第二個參數。 |
| **更高解析度** | 提升 X 維度（`setPixels`）或設定 `YDimension` 以控制條的高度。 |
| **彩色條碼** | 使用 `barcodeGenerator.getParameters().getImageOptions().setForeColor(Color.BLUE);` 變更條的顏色。 |
| **儲存為 SVG** | 將 `BarCodeImageFormat.Png` 替換為 `BarCodeImageFormat.Svg` 以取得向量輸出。 |
| **在 Android 上執行** | 使用 Android 相容的 Aspose.BarCode for Android，並將檔案系統路徑改為 `Context.getFilesDir()`。 |

> **注意：** 將 X 維度設定過低（例如 1 像素）可能導致條碼在低解析度印表機上無法辨識。變更尺寸後務必使用實體掃描器測試。

## 完整原始碼（快速複製貼上）

```java
package com.example.barcode;

import com.aspose.barcode.BarCodeImageFormat;
import com.aspose.barcode.EncodeTypes;
import com.aspose.barcode.generator.BarcodeGenerator;

public class PlanetBarcodeDemo {
    public static void main(String[] args) {
        // Create the generator for Planet barcode with sample data
        BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
                EncodeTypes.PLANET,
                "123456");

        // Custom X dimension – 4 pixels per module
        barcodeGenerator.getParameters()
                        .getBarcode()
                        .getXDimension()
                        .setPixels(4);

        // Use outline (empty) bars
        barcodeGenerator.getParameters()
                        .getBarcode()
                        .setFilledBars(false);

        // Save as PNG
        String outputPath = "output/PlanetEmptyBars.png";
        barcodeGenerator.save(outputPath, BarCodeImageFormat.Png);

        System.out.println("Barcode image generated at: " + outputPath);
    }
}
```

將程式碼複製到名為 `PlanetBarcodeDemo.java` 的檔案中，放置於 `src/main/java/com/example/barcode/` 目錄下，執行 `mvn compile exec:java`，即可在 `output` 資料夾看到 **產生條碼圖像** 的結果。

## 結論

現在您已了解如何在 Java 中 **產生 Planet 符號的條碼圖像**、如何使用 **自訂條碼尺寸** **建立 planet 條碼**，以及如何將實心條切換為空心條以獲得更清晰的視覺風格。完整範例示範了從初始化產生器到儲存 PNG 檔案的所有必要 API 呼叫。

**下一步** – 探索其他條碼類型（`EncodeTypes.CODE_128`、`EncodeTypes.QR`），並嘗試額外的影像選項，如背景顏色、邊距與 DPI 設定。若需將條碼嵌入 PDF，可將此程式碼與 Aspose.PDF for Java 結合，實現無縫的端對端解決方案。

祝開發順利！

## 接下來應該學什麼？

以下教學涵蓋與本指南緊密相關的主題，並以此為基礎。每個資源皆提供完整可執行的程式碼範例與逐步說明，協助您精通其他 API 功能，並在自己的專案中探索替代實作方式。

- [如何建立帶實心與空心條的 planet 條碼](/barcode/english/python-java/general/how-to-create-planet-barcode-with-filled-and-empty-bars/)
- [建立 planet 條碼圖像 – 步驟指南](/barcode/english/python-java/general/create-planet-barcode-image-step-by-step-guide/)
- [如何在 Java 產生條碼：建立精確條碼圖像](/barcode/english/java/barcode-basics/creating-image-exact-barcode/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}