---
date: 2025-12-22
description: 學習如何使用 Aspose.BarCode for Java 建立帶有空白條的條碼圖像。此一步一步的條碼產生範例可協助您快速產生 Java
  條碼。
linktitle: Generating Barcode with Empty Bars
second_title: Aspose.BarCode Java API
title: 如何在 Java 中創建帶空白條的條碼圖像
url: /zh-hant/java/image-manipulation/generating-barcode-empty-bars/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 Java 中建立空條碼圖像

## 簡介

在現代的 Java 應用程式中，即時 **create barcode image** 檔案的能力是庫存管理、票務系統以及其他許多商業情境中的寶貴功能。Aspose.BarCode for Java 提供功能強大且易於使用的 API，讓您只需幾行程式碼即可產生高品質的條碼。在本教學中，我們將逐步說明 **step‑by‑step barcode** 的建立流程，產生條碼的空白（未填滿）條紋，適合需要空心外觀的設計。

## 快速解答
- **What does “empty bars” mean?** **empty bars** 是什麼意思？條紋會以未填滿的方式呈現，呈現空心外觀。  
- **Which barcode type is used?** 使用 Code 128（廣泛支援的線性條碼）。  
- **Do I need a license to try it?** 可使用免費試用版；正式使用時需購買授權。  
- **What output formats are supported?** 支援 PNG、JPEG、BMP、GIF、TIFF 等多種格式。  
- **Is this compatible with all Java versions?** 是，函式庫相容於 Java 8 及以上版本。

## 什麼是 create barcode image？

建立條碼圖像是指將資料字串轉換為掃描器可讀取的視覺表示。產生的圖像可儲存為 PNG、JPEG 或其他常見格式，可嵌入 PDF、列印於標籤或顯示於使用者介面上。

## 為什麼使用 Aspose.BarCode Java 函式庫？

- **Rich feature set** – 支援超過 50 種條碼符號，包括 Code 128、QR、DataMatrix 等。  
- **Fine‑grained control** – 如 `FilledBars`、顏色、邊距及圖像尺寸等屬性皆可輕鬆設定。  
- **No external dependencies** – 只需一個 JAR 檔即可完成所有功能，簡化部署。  
- **Comprehensive documentation** – 範例、API 參考與論壇可協助您快速上手。

## 先決條件

在開始條碼產生之前，請確保已具備以下先決條件：

1. **Java Development Environment** – 確認已安裝 Java 8 以上版本，並具備相容的 IDE 或建置工具。  
2. **Aspose.BarCode for Java Library** – 從[下載頁面](https://releases.aspose.com/barcode/java/)下載並安裝 Aspose.BarCode for Java 函式庫。  
3. **Document Directory** – 在系統上建立目錄，以儲存產生的條碼圖像。

## 匯入套件

在您的 Java 專案中，匯入使用 Aspose.BarCode 所需的套件：

```java
import java.io.IOException;
import com.aspose.barcode.BarCodeImageFormat;
import com.aspose.barcode.generation.BarcodeGenerator;
```

## 如何建立空條碼圖像

### 步驟 1：設定資源目錄

```java
// The path to the resource directory.
String dataDir = "Your Document Directory";
```

將 `"Your Document Directory"` 替換為您想要儲存輸出檔案的實際路徑。

### 步驟 2：建立條碼產生器實例（Code128 Barcode Java）

```java
// Create an instance of BarcodeGenerator and initialize it with CodeText and Symbology
BarcodeGenerator generator = new BarcodeGenerator(com.aspose.barcode.EncodeTypes.CODE_128, "TEXT");
```

此處使用 **Code 128** 符號——最受歡迎的線性條碼之一——因此這是一個經典的 **code128 barcode java** 範例。

### 步驟 3：將 FilledBars 屬性設為 False

```java
// Set the FilledBars property to false
generator.getParameters().getBarcode().setFilledBars(false);
```

將 `FilledBars` 設為 `false`，即告訴 Aspose.BarCode 將條紋以空白（空心）形狀呈現，而非實心方塊。

### 步驟 4：儲存條碼圖像

```java
// Save the resultant barcode image on disk
generator.save(dataDir + "barcodeWithEmptyBars.png", BarCodeImageFormat.PNG);
```

圖像以 PNG 格式儲存，您亦可變更 `BarCodeImageFormat` 列舉，以產生 JPEG、BMP 或其他支援的格式。

在您的 Java 應用程式中重複上述步驟，即可輕鬆使用 Aspose.BarCode for Java **create barcode image** 空條碼檔案。

## 結論

總結來說，本教學帶您完成 **step‑by‑step barcode** 的建立流程，示範如何在 Java 中 **create barcode image** 空條碼檔案。憑藉直觀的 API 與豐富的自訂選項，Aspose.BarCode 簡化條碼整合，成為需要可靠 **java barcode library** 的開發者的寶貴資產。

## 常見問題

### Aspose.BarCode 是否相容於所有 Java 開發環境？
是的，Aspose.BarCode 設計上能無縫整合各種 Java 開發環境。

### 我可以自訂產生的條碼外觀嗎？
當然！Aspose.BarCode 提供多種自訂選項，讓您依需求調整條碼外觀。

### 是否提供 Aspose.BarCode 的試用版？
是的，您可透過[此處](https://releases.aspose.com/)取得免費試用版，探索 Aspose.BarCode 的功能。

### 我該如何取得 Aspose.BarCode 的支援？
如有任何問題或需要協助，請前往 [Aspose.BarCode 論壇](https://forum.aspose.com/c/barcode/13)。

### 我在哪裡可以找到 Aspose.BarCode 的詳細文件？
完整文件可在[此處](https://reference.aspose.com/barcode/java/)取得。

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Last Updated:** 2025-12-22  
**Tested With:** Aspose.BarCode Java 24.11 (latest)  
**Author:** Aspose