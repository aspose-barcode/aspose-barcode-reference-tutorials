---
date: 2026-06-09
description: 了解如何使用 Aspose.BarCode 建立 Code128 條碼（Java）。本分步指南說明如何產生 Java 條碼、設定自訂文字、調整條寬，並儲存影像。
keywords:
- create code128 barcode java
- how to generate barcode java
- java barcode generator example
linktitle: 設定條碼文字
schemas:
- author: Aspose
  dateModified: '2026-06-09'
  description: Learn how to create Code128 barcode Java using Aspose.BarCode. This
    step‑by‑step guide shows how to generate barcode Java, set custom text, adjust
    bar width, and save the image.
  headline: Create Code128 Barcode Java – Set Code Text using Aspose.BarCode
  type: TechArticle
- description: Learn how to create Code128 barcode Java using Aspose.BarCode. This
    step‑by‑step guide shows how to generate barcode Java, set custom text, adjust
    bar width, and save the image.
  name: Create Code128 Barcode Java – Set Code Text using Aspose.BarCode
  steps:
  - name: Create an Instance of `BarcodeGenerator`
    text: 'The `BarcodeGenerator` constructor takes two arguments: the barcode symbology
      (`CODE_128`) and the **custom code text** you want to encode, such as `"12345678"`.'
  - name: Adjust Barcode Width for Custom Barcode Text
    text: Set the `XDimension` property (bar width) to control how wide each bar appears.
      In this example we use `0.5` mm, a size that balances readability and label
      space for most applications.
  - name: Save the Barcode Image
    text: Call the `save` method, specifying the output path and image format (JPEG,
      PNG, SVG, etc.). The example saves the file as **`setCodeText.jpg`** in the
      project’s document folder.
  type: HowTo
- questions:
  - answer: Aspose.BarCode for Java.
    question: What library should I use?
  - answer: CODE_128.
    question: Which barcode type is demonstrated?
  - answer: Use the `BarcodeGenerator` constructor or the `setCodeText` method.
    question: How do I set custom barcode text?
  - answer: Yes—adjust `XDimension` (bar width) in millimetres.
    question: Can I change the bar width?
  - answer: A commercial license is required for non‑trial deployments.
    question: Do I need a license for production?
  type: FAQPage
second_title: Aspose.BarCode Java API
title: 使用 Aspose.BarCode 建立 Code128 條碼（Java） – 設定條碼文字
url: /zh-hant/java/text-and-styling/setting-code-text/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 建立 Code128 條碼（Java） – 使用 Aspose.BarCode 設定條碼文字

在本教學中，您將學習如何使用 Aspose.BarCode Java 函式庫 **建立 Code128 條碼（Java）**。無論是建置庫存系統、文件追蹤解決方案，或任何需要條碼的應用程式，我們都會一步步帶您完成——從實例化 **Code128** 條碼到自訂條碼文字以及微調條寬。完成後，您將得到一張可直接嵌入任意位置的即用圖像。

## 快速解答
- **應該使用哪個程式庫？** Aspose.BarCode for Java。  
- **示範的條碼類型是什麼？** CODE_128。  
- **如何設定自訂條碼文字？** 使用 `BarcodeGenerator` 建構子或 `setCodeText` 方法。  
- **可以調整條寬嗎？** 可以——調整 `XDimension`（條寬）以毫米為單位。  
- **正式環境需要授權嗎？** 非試用部署必須使用商業授權。

## 如何在 Java 中建立 Code128 條碼？

載入 `BarcodeGenerator`，指定 `CODE_128` 符號與您想要的文字，透過 `XDimension` 設定條寬，最後呼叫 `save` 寫入影像檔案。這個三步驟模式可在數秒內產生高品質條碼，且相容於任何 Java 8+ 執行環境、Windows、Linux 或 macOS。

## 產生條碼（Java）前置條件

- 具備基本的 Java 程式設計知識。  
- Java 開發環境（JDK 8 或以上）。  
- Aspose.BarCode for Java 程式庫 – 於 **[此處](https://releases.aspose.com/barcode/java/)** 下載。  
- 您偏好的 IDE（IntelliJ IDEA、Eclipse 等）。

## 匯入套件

匯入必要的 Aspose.BarCode 命名空間，使類別在專案中可用。

## 什麼是 BarcodeGenerator 類別？

`BarcodeGenerator` 是 Aspose.BarCode 的核心類別，用於在記憶體中建立條碼影像。它提供流暢的 API，可設定符號、條碼文字、尺寸、顏色以及其他渲染選項，然後將結果匯出為 PNG、JPEG、SVG 或 PDF 等格式。您亦可依需求自訂說明文字、邊距與錯誤更正等層級。

## 條碼產生器教學：建立 Code128 條碼

### 步驟 1：建立 `BarcodeGenerator` 實例

`BarcodeGenerator` 建構子接受兩個參數：條碼符號（`CODE_128`）以及您想編碼的 **自訂條碼文字**，例如 `"12345678"`。

```java
// The path to the documents directory.
String path = "Your Directory Path";
// The path to the resource directory.
String dataDir = "Your Document Directory";
BarcodeGenerator generator = new BarcodeGenerator(com.aspose.barcode.EncodeTypes.CODE_128, "12345678");
```

### 步驟 2：調整條碼寬度以符合自訂條碼文字

設定 `XDimension` 屬性（條寬）以控制每根條的寬度。此範例使用 `0.5` mm，這個尺寸在大多數應用中兼顧可讀性與標籤空間。

```java
generator.getParameters().getBarcode().getXDimension().setMillimeters(0.5f);
```

### 步驟 3：儲存條碼影像

呼叫 `save` 方法，指定輸出路徑與影像格式（JPEG、PNG、SVG 等）。範例將檔案儲存為 **`setCodeText.jpg`**，位於專案的 document 資料夾中。

```java
generator.save(dataDir + "setCodeText.jpg");
```

## 為何使用 Aspose.BarCode for Java？

Aspose.BarCode for Java 提供完整功能集，簡化跨平台條碼產生。支援超過六十種符號，輸出高解析度點陣與向量圖檔，且針對大量處理進行效能最佳化，是企業級應用與與現有 Java 專案無縫整合的理想選擇。

- **廣泛的條碼支援** – 超過 **60** 種條碼類型，包括 Code128、QR、DataMatrix 與 PDF417。  
- **高解析度渲染** – 可產生清晰的 PNG、JPEG、SVG 與 PDF 影像，寬度最高可達 **2000 mm**，且不失真。  
- **效能導向** – 在標準伺服器硬體上，處理 500 頁條碼批次耗時不到 **2 秒**。  
- **跨平台** – 完全相容於 Windows、Linux 與 macOS，且支援任何 Java 8+ 執行環境。

## 常見問題與解決方案

| 問題 | 解決方案 |
|------|----------|
| **條碼模糊** | 提升影像解析度或匯出為向量格式（SVG、PDF）。 |
| **文字被截斷** | 放大 `XDimension` 與 `BarHeight`，為條碼提供足夠空間。 |
| **授權未套用** | 將 `Aspose.BarCode.lic` 放置於專案根目錄，並使用 `License license = new License(); license.setLicense("Aspose.BarCode.lic");` 載入。 |

## 常見問與答

**Q:** *`CODE_128` 與其他 Code128 變體有何不同？*  
**A:** `CODE_128` 會根據輸入自動選擇最有效的編碼方式（A、B 或 C），提供最佳密度與速度。

**Q:** *可以將輸出格式改為 PNG 而非 JPEG 嗎？*  
**A:** 可以——使用 `generator.save(dataDir + "setCodeText.png", com.aspose.barcode.BarcodeImageFormat.PNG);`。

**Q:** *能在條碼下方加入可讀的說明文字嗎？*  
**A:** 當然可以。設定 `generator.getParameters().getBarcode().getCaption().setTopMargin(5);`，並透過 `setText` 定義說明文字。

**Q:** *Aspose.BarCode 支援 Unicode 字元嗎？*  
**A:** 支援。提供 UTF‑8 編碼的文字，並確保所選符號支援該字元集。

**Q:** *如何在迴圈中產生多個條碼？*  
**A:** 在迴圈內實例化新的 `BarcodeGenerator`，為每次迭代指派唯一文字，然後以不同檔名呼叫 `save`。

---

**最後更新：** 2026-06-09  
**測試環境：** Aspose.BarCode 24.12 for Java  
**作者：** Aspose  

{{< blocks/products/products-backtop-button >}}

## 相關教學

- [在 Java 中建立 Data Matrix 條碼並設定條碼文字位置](/barcode/java/text-and-styling/setting-code-text-location/)
- [如何在 Java 中使用 Aspose.BarCode 設定條碼文字顏色](/barcode/java/text-and-styling/setting-code-text-foreground-color/)
- [在 Java 中產生條碼 – 使用 Aspose.BarCode 設定影像解析度](/barcode/java/advanced-settings-and-optimization/setting-image-resolution-barcode/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

```java
import com.aspose.barcode.generation.BarcodeGenerator;
```