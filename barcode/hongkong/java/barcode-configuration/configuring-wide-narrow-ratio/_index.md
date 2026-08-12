---
date: 2026-08-12
description: 了解如何在 Java 中使用 Aspose.BarCode 自訂 CODE_128 wide‑narrow ratio 以提升條碼可讀性，並高效產生
  PNG 圖像。跟隨我們的 Java 條碼產生逐步教學。
keywords:
- improve barcode readability
- customize code128 barcode
- barcode generation tutorial java
- step by step barcode
lastmod: 2026-08-12
linktitle: 設定 wide‑narrow ratio
og_description: 了解如何在 Java 中使用 Aspose.BarCode 自訂 CODE_128 wide‑narrow ratio 以提升條碼可讀性。本逐步教學示範如何快速產生
  PNG 條碼。
og_image_alt: Guide to creating CODE_128 barcode with custom wide‑narrow ratio in
  Java
og_title: 透過 CODE_128 wide‑narrow ratio 提升條碼可讀性 (58 個字元)
schemas:
- author: Aspose
  dateModified: '2026-08-12'
  description: Learn how to improve barcode readability by customizing the CODE_128
    wide‑narrow ratio in Java using Aspose.BarCode, and generate PNG images efficiently.
    Follow our step‑by‑step barcode generation tutorial Java.
  headline: Improve barcode readability with CODE_128 wide‑narrow ratio
  type: TechArticle
- description: Learn how to improve barcode readability by customizing the CODE_128
    wide‑narrow ratio in Java using Aspose.BarCode, and generate PNG images efficiently.
    Follow our step‑by‑step barcode generation tutorial Java.
  name: Improve barcode readability with CODE_128 wide‑narrow ratio
  steps:
  - name: set document directory
    text: Make sure the directory exists and you have write permissions; this is where
      the **saved barcode image** file will be placed.
  - name: instantiate barcode object
    text: The `BarcodeGenerator` class creates barcode images based on the specified
      symbology and encoding options. Here we **create a CODE_128 barcode** by passing
      `EncodeTypes.CODE_128` to the constructor.
  - name: set wide‑narrow ratio
    text: '`setWideNarrowRatio` sets the proportion between wide and narrow bars for
      the generated barcode. The `setWideNarrowRatio` method lets you fine‑tune the
      visual spacing. A value of `3.0f` means the wide bar is three times the width
      of a narrow bar, which falls within the optimal 2.0‑3.0 range for most'
  - name: save image to disk
    text: Calling `save` will **generate a barcode image** and store it as a PNG file,
      completing the **save barcode image** step.
  type: HowTo
- questions:
  - answer: Yes, Aspose.BarCode works seamlessly with Spring, Java EE, Android, and
      other Java environments.
    question: Can I use Aspose.BarCode with other Java frameworks?
  - answer: Change the symbology type in the `BarcodeGenerator` constructor, for example
      `EncodeTypes.QR` for QR codes.
    question: How can I generate barcodes with different symbologies?
  - answer: Yes, you can access the free trial version on the [Aspose.BarCode free
      trial page](https://releases.aspose.com/).
    question: Is there a trial version available for Aspose.BarCode?
  - answer: Refer to the documentation on the [Aspose.BarCode Java API documentation](https://reference.aspose.com/barcode/java/).
    question: Where can I find detailed documentation for Aspose.BarCode?
  - answer: Visit the Aspose.BarCode community forum at [Aspose.BarCode community
      forum](https://forum.aspose.com/c/barcode/13) for support and community discussions.
    question: How to get support for Aspose.BarCode?
  type: FAQPage
second_title: Aspose.BarCode Java API
tags:
- barcode readability
- Aspose.BarCode
- Java barcode tutorial
title: 透過 CODE_128 wide‑narrow ratio 提升條碼可讀性
url: /zh-hant/java/barcode-configuration/configuring-wide-narrow-ratio/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 提升 CODE_128 條碼可讀性：寬窄比例調整

## 介紹

如果您需要 **提升條碼可讀性**，無論是庫存標籤、運輸標籤，或任何使用 CODE_128 的應用，調整寬窄比例是最有效的技巧。在本教學中，我們將逐步說明如何使用 Aspose.BarCode for Java 建立 **步驟式條碼**，示範如何設定比例、**產生條碼 PNG** 圖片，並 **將條碼圖像儲存** 到磁碟。您也會了解比例對掃描器效能的影響，以及如何針對特定列印環境進行微調。

## 快速答覆
- **什麼是寬窄比例？** 它控制條碼中寬條與窄條的相對寬度。  
- **哪些條碼類型支援比例調整？** 大多數 1‑D 條碼類型，包括 CODE_128，都允許自訂比例。  
- **需要授權嗎？** 提供免費試用版，但正式使用需購買商業授權。  
- **可以產生 PNG 格式的條碼圖像嗎？** 可以——使用 `generator.save(...)` 產生條碼 PNG 圖片。  
- **程式碼相容於 Java 8+ 嗎？** 完全相容；Aspose.BarCode 支援所有現代 Java 版本。

## 前置條件

在開始撰寫程式碼之前，請確保您已具備以下項目：

- 已在電腦上安裝 Java Development Kit (JDK)。  
- Aspose.BarCode for Java 套件。可從 [download link](https://releases.aspose.com/barcode/java/) 下載。

## 匯入套件

首先，將 Aspose.BarCode 的核心類別匯入專案中。  
`BarcodeGenerator` 為產生條碼圖像的主要類別，可設定條碼類型與各種選項。  

```java
// Import Aspose.BarCode library
import com.aspose.barcode.generation.BarcodeGenerator;
```

## 什麼是寬窄比例，為什麼要調整？

寬窄比例定義「寬」條相對於「窄」條的寬度倍數。調整此比例可提升掃描器相容性（大多數掃描器在 2.0 至 3.0 的比例下表現最佳），彌補印表機 DPI 限制，並讓您在不犧牲可靠性的前提下，符合品牌的視覺風格。

## 如何在 Java 中使用寬窄比例建立 CODE_128 條碼以提升可讀性

先將 Aspose.BarCode 套件加入 Java 專案，接著建立 `BarcodeGenerator` 實例並指定 `EncodeTypes.CODE_128`。使用 `setWideNarrowRatio` 設定所需的寬窄比例，必要時調整其他視覺設定，最後呼叫 `save` 將條碼寫入 PNG 檔案。此簡潔流程可確保條碼品質一致，提升各種裝置的掃描成功率。

### 步驟 1：設定文件目錄

```java
// The path to the resource directory.
String dataDir = "Your Document Directory";
```

請確保目錄已存在且您具有寫入權限；此目錄將放置 **已儲存的條碼圖像** 檔案。

### 步驟 2：實例化條碼物件

`BarcodeGenerator` 類別根據指定的條碼類型與編碼選項產生條碼圖像。  
```java
// Instantiate barcode object
// Create an instance of BarcodeGenerator, specify codetext and symbology in the constructor
BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.CODE_128, "12345678");
```

此處我們 **建立 CODE_128 條碼**，方式是將 `EncodeTypes.CODE_128` 傳入建構子。

### 步驟 3：設定寬窄比例

`setWideNarrowRatio` 用於設定產生條碼時寬條與窄條之間的比例。  
```java
// Set the wide to narrow ratio for the barcode
generator.getParameters().getBarcode().setWideNarrowRatio(3.0f);
```

`setWideNarrowRatio` 方法讓您微調視覺間距。`3.0f` 代表寬條寬度是窄條的三倍，屬於大多數掃描器的最佳 2.0‑3.0 範圍內。

### 步驟 4：將圖像儲存至磁碟

```java
// Save the image to disk in PNG format
generator.save(dataDir + "wideNarrowRatio.png");
```

呼叫 `save` 會 **產生條碼圖像** 並以 PNG 檔案形式儲存，完成 **儲存條碼圖像** 的步驟。

## 為什麼要調整寬窄比例？

調整寬窄比例可提升掃描器相容性，因為大多數工業掃描器在比例介於 2.0 至 3.0 時讀取效果最佳。此舉亦能透過補償 150–300 dpi 的印表機解析度，減少條紋變形，提升列印品質。此外，比例的調整讓企業能在符合品牌指引的同時，維持可靠的掃描效能。

## 常見問題與解決方案

| 問題 | 原因 | 解決方式 |
|------|------|----------|
| 條碼變形 | 比例對印表機而言過高或過低 | 調整傳入 `setWideNarrowRatio` 的數值（例如 2.0‑2.5）。 |
| 檔案未建立 | `dataDir` 路徑無效或權限不足 | 確認目錄路徑正確，並確保應用程式具有寫入權限。 |
| 掃描器無法讀取條碼 | 比例超出該條碼類型的建議範圍 | 使用標準比例（2.0‑3.0）或以目標掃描器進行測試。 |

## 常見問答

**Q: 可以在其他 Java 框架中使用 Aspose.BarCode 嗎？**  
A: 可以，Aspose.BarCode 可無縫整合至 Spring、Java EE、Android 以及其他 Java 環境。

**Q: 如何產生不同條碼類型的條碼？**  
A: 在 `BarcodeGenerator` 建構子中更換條碼類型，例如使用 `EncodeTypes.QR` 產生 QR Code。

**Q: 是否提供 Aspose.BarCode 的試用版？**  
A: 有，您可於 [Aspose.BarCode free trial page](https://releases.aspose.com/) 取得免費試用版。

**Q: 哪裡可以找到 Aspose.BarCode 的詳細文件？**  
A: 請參考 [Aspose.BarCode Java API documentation](https://reference.aspose.com/barcode/java/)。

**Q: 如何取得 Aspose.BarCode 的技術支援？**  
A: 前往 [Aspose.BarCode community forum](https://forum.aspose.com/c/barcode/13) 取得支援與社群討論。

---

**最後更新：** 2026-08-12  
**測試環境：** Aspose.BarCode for Java 24.11（撰寫時最新版本）  
**作者：** Aspose  

{{< blocks/products/products-backtop-button >}}

## 相關教學

- [Generate Barcode Java – Set Image Resolution with Aspose.BarCode](/barcode/java/advanced-settings-and-optimization/setting-image-resolution-barcode/)
- [Detect Barcode Orientation in Java with Aspose.BarCode](/barcode/java/advanced-settings-and-optimization/configuring-barcode-orientation/)
- [How to create code128 barcode images in Java with Aspose.BarCode](/barcode/java/advanced-settings-and-optimization/saving-barcode-images-different-formats/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}