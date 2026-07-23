---
date: 2026-07-23
description: 使用 Aspose.BarCode 建立 code128 條碼 Java。產生條碼影像 Java，設定精確的尺寸單位，並優化庫存系統或運送標籤。
keywords:
- create code128 barcode java
- barcode for inventory system
- generate shipping label barcode
- generate barcode image java
lastmod: 2026-07-23
linktitle: 設定條碼影像的尺寸單位
og_description: 使用 Aspose.BarCode 建立 code128 條碼 Java。學習產生條碼影像 Java、控制尺寸單位，並提升庫存或運送標籤工作流程。
og_image_alt: 'Guide: create code128 barcode java with size unit settings'
og_title: 建立 code128 條碼 Java：設定條碼影像的尺寸單位
schemas:
- author: Aspose
  dateModified: '2026-07-23'
  description: Create code128 barcode java with Aspose.BarCode. Generate barcode image
    java, set precise size units, and optimize for inventory systems or shipping labels.
  headline: 'create code128 barcode java: Set Size Unit for Barcode Image'
  type: TechArticle
- description: Create code128 barcode java with Aspose.BarCode. Generate barcode image
    java, set precise size units, and optimize for inventory systems or shipping labels.
  name: 'create code128 barcode java: Set Size Unit for Barcode Image'
  steps:
  - name: Define the Resource Directory
    text: First, specify the folder where the generated files will be written. This
      directory must exist and be writable by the Java process. Replace `"Your Document
      Directory"` with the absolute path where you want the barcode image saved. This
      folder will hold the generated PNG/JPEG files that you can later
  - name: Instantiate the Barcode Object
    text: '`EncodeTypes.CODE_128` specifies the CODE_128 barcode symbology. `BarcodeGenerator`
      is Aspose.BarCode''s core class that represents a barcode image in memory. Creating
      a `create code128 barcode java` instance is as simple as passing the `EncodeTypes.CODE_128`
      enum and the data string you wish to enco'
  - name: Set Bar Height (Size Unit)
    text: '`BarHeight` defines the vertical size of the bars. The `.setPoint()` method
      sets this height in points (1 point = 1/72 inch), giving you precise control
      over the final visual size. The `setPoint()` method defines the height in points.
      Adjust this value to meet your layout requirements—larger values '
  - name: Save the Image
    text: Calling `save()` writes the barcode to the folder you specified. The image
      format is inferred from the file extension; you can switch to PNG, BMP, or TIFF
      simply by changing the extension. The `save()` call writes the generated barcode
      to the folder you specified. The image format is inferred from t
  type: HowTo
- questions:
  - answer: Yes, the library supports both generation and recognition of a wide range
      of symbologies.
    question: Is Aspose.BarCode for Java suitable for both barcode generation and
      recognition?
  - answer: Absolutely. You can change colors, add captions, modify margins, and even
      embed logos using the extensive `Parameters` API.
    question: Can I customize the appearance of the generated barcode images?
  - answer: Visit [here](https://purchase.aspose.com/temporary-license/) to request
      a temporary license for evaluation.
    question: How can I obtain a temporary license for Aspose.BarCode for Java?
  - answer: The Aspose.BarCode community forum is the best place for help. Check the
      [forum](https://forum.aspose.com/c/barcode/13) for answers and to ask new questions.
    question: Where can I find support for Aspose.BarCode for Java?
  - answer: The library supports dozens of symbologies, including CODE_128, QR_CODE,
      UPC_A, DataMatrix, PDF417, and many more.
    question: What are the supported barcode symbologies in Aspose.BarCode for Java?
  type: FAQPage
second_title: Aspose.BarCode Java API
tags:
- create code128 barcode java
- barcode for inventory system
- Aspose.BarCode
- Java barcode generation
title: 建立 code128 條碼 Java：設定條碼影像的尺寸單位
url: /zh-hant/java/advanced-settings-and-optimization/setting-size-unit-barcode-image/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 建立 code128 條碼 Java：設定條碼圖像的尺寸單位

## 介紹

在本分步教學中，您將 **使用 Aspose.BarCode for Java** 來 **建立 code128 條碼 Java**、產生條碼圖像 Java，並精確控制輸出圖像的尺寸單位。無論您是為庫存系統、運送標籤產生器，或任何需要可靠條碼的 Java 應用程式開發，Aspose.BarCode 都能以極少的程式碼提供完整的彈性。

## 快速回答
- **需要哪個函式庫？** Aspose.BarCode for Java（aspose barcode java）。  
- **支援哪種條碼類型？** CODE_128（create code128 barcode java）。  
- **如何設定尺寸單位？** 使用 `BarHeight` 屬性搭配 `.setPoint()`。  
- **可以產生其他格式的 barcode image java 嗎？** 可以 – PNG、JPEG、BMP 等。  
- **前置需求是什麼？** 已安裝 JDK、Aspose.BarCode 函式庫，以及 Java IDE。

## 什麼是 **create code128 barcode java**？

`create code128 barcode java` 指的是使用 `BarcodeGenerator` 類別與 `EncodeTypes.CODE_128` 列舉，將資料字串編碼為 CODE_128 符號。此符號支援完整的 ASCII 集，且資料密度高，非常適合庫存系統與運送標籤等情境。

## 為什麼使用 Aspose.BarCode 來 **generate barcode image java**？

使用 Aspose.BarCode 產生 barcode image java 可讓您在純 Java 環境下控制尺寸、顏色與解析度。此函式庫支援 **超過 50 種輸入與輸出格式**，且能在不將整個檔案載入記憶體的情況下建立上百頁的條碼圖像，為批次標籤製作提供毫秒級效能。

## 前置條件

開始之前，請確保您已具備：

1. **Java Development Kit (JDK)** – 版本 8 或更新版本已安裝於您的機器。  
2. **Aspose.BarCode for Java 函式庫** – 從 Aspose 官方網站下載最新的 JAR（試用版或正式授權）。  
3. **Java IDE** – 如 IntelliJ IDEA、Eclipse，或具 Java 擴充功能的 VS Code。  

## 匯入命名空間

在 Java 類別的頂部加入必要的匯入，以便存取 Aspose.BarCode 的 API：

```java
import java.io.IOException;

import com.aspose.barcode.*;

import com.aspose.barcode.generation.BarcodeGenerator;
```

## 如何使用 Aspose.BarCode **generate barcode image java**？

載入 `BarcodeGenerator`、設定尺寸，然後儲存圖像——整個流程清晰線性，亦可包在迴圈中以進行批次處理。以下段落直接說明操作步驟，接著再深入說明每一步。

### 步驟 1：定義資源目錄

首先，指定產生檔案的資料夾。此目錄必須已存在且允許 Java 程序寫入。

```java
// The path to the resource directory.
String dataDir = "Your Document Directory";
```

將 `"Your Document Directory"` 替換為您希望儲存條碼圖像的絕對路徑。此資料夾將保存產生的 PNG/JPEG 檔案，您可稍後將其嵌入發票、裝箱單或庫存報表中。

### 步驟 2：實例化條碼物件

`EncodeTypes.CODE_128` 指定 CODE_128 條碼符號。

`BarcodeGenerator` 是 Aspose.BarCode 的核心類別，代表記憶體中的條碼圖像。建立 **create code128 barcode java** 實例只需傳入 `EncodeTypes.CODE_128` 列舉與欲編碼的資料字串。

```java
// Instantiate barcode object, Set the symbology type to code128 and Set the
// Code text for the barcode
BarcodeGenerator bb = new BarcodeGenerator(EncodeTypes.CODE_128, "1234567");
```

此處我們透過傳入 `EncodeTypes.CODE_128` 與資料字串 `"1234567"` 來 **create code128 barcode java**。

### 步驟 3：設定條碼高度（尺寸單位）

`BarHeight` 定義條碼垂直方向的大小。`.setPoint()` 方法以點 (1 point = 1/72 英吋) 為單位設定此高度，讓您能精確控制最終視覺尺寸。

```java
// Set the bar height to 3 points
bb.getParameters().getBarcode().getBarHeight().setPoint(3.0f);
```

`setPoint()` 方法以點為單位定義高度。依需求調整此數值——較大的值會產生較高的條碼，這在高解析度的運送標籤上常有需求。

### 步驟 4：儲存圖像

呼叫 `save()` 即可將條碼寫入先前指定的資料夾。圖像格式會根據檔案副檔名自動推斷；只要變更副檔名，即可切換為 PNG、BMP 或 TIFF。

```java
// Save the image
bb.save(dataDir + "barcode-size-unit.jpg");
```

`save()` 呼叫會將產生的條碼寫入您指定的資料夾。此例的圖像格式由副檔名 (JPEG) 推斷。只要更改副檔名，即可切換為 PNG、BMP 或 TIFF。

## 常見問題與解決方案

| 問題 | 原因 | 解決方案 |
|------|------|----------|
| **未建立圖像** | `dataDir` 路徑不正確或缺少寫入權限。 | 確認資料夾已存在且應用程式具備寫入權限。 |
| **條碼顯示過小** | 條碼高度以點為單位設定過低，與 DPI 不匹配。 | 增加傳入 `setPoint()` 的數值，或透過 `bb.getParameters().getImage().setResolution()` 調整圖像 DPI。 |
| **不支援的字元** | CODE_128 只支援 ASCII，您傳入了 Unicode。 | 使用其他符號 (例如 QR_CODE) 以處理非 ASCII 資料。 |

## 常見問答

**Q: Aspose.BarCode for Java 是否同時支援條碼產生與辨識？**  
A: 是，函式庫同時支援多種符號的產生與辨識。

**Q: 我可以自訂產生的條碼圖像外觀嗎？**  
A: 當然可以。您可以變更顏色、加入說明文字、調整邊距，甚至使用 `Parameters` API 嵌入商標。

**Q: 如何取得 Aspose.BarCode for Java 的臨時授權？**  
A: 前往 [此處](https://purchase.aspose.com/temporary-license/) 申請臨時授權以供評估。

**Q: 在哪裡可以取得 Aspose.BarCode for Java 的支援？**  
A: Aspose.BarCode 社群論壇是最佳求助管道。請至 [論壇](https://forum.aspose.com/c/barcode/13) 查詢答案或提出新問題。

**Q: Aspose.BarCode for Java 支援哪些條碼符號？**  
A: 函式庫支援數十種符號，包括 CODE_128、QR_CODE、UPC_A、DataMatrix、PDF417 等。

### 其他技巧（專業提示）

`getParameters().getImage().setResolution()` 可設定圖像 DPI。

- **批次處理：** 將上述步驟包在迴圈中，可一次產生上百條條碼，適合大量庫存上傳。  
- **解析度控制：** 使用 `bb.getParameters().getImage().setResolution(300)` 產生 300 dpi 圖像，適合高品質列印標籤。  

---

**最後更新：** 2026-07-23  
**測試環境：** Aspose.BarCode for Java 24.12（撰寫時最新版本）  
**作者：** Aspose  

{{< blocks/products/products-backtop-button >}}

## 相關教學

- [Generate Barcode Java – Set Image Resolution with Aspose.BarCode](/barcode/java/advanced-settings-and-optimization/setting-image-resolution-barcode/)
- [How to create small barcode labels in Java with Aspose.BarCode](/barcode/java/advanced-settings-and-optimization/getting-minimum-barcode-size/)
- [Custom Barcode Size Java - Configure Exact Dimensions with Aspose.BarCode](/barcode/java/advanced-settings-and-optimization/configuring-custom-size-barcode/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}