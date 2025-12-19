---
date: 2025-12-19
description: 學習如何使用 Aspose.BarCode 從 PDF 檔案讀取 Java 條碼。本分步指南示範如何高效產生條碼圖像並進行解碼。
linktitle: Recognizing Barcodes from PDF
second_title: Aspose.BarCode Java API
title: 使用 Java 讀取條碼 – 從 PDF 識別條碼
url: /zh-hant/java/document-barcode-recognition/recognizing-barcodes-from-pdf/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Read Barcode Java – 從 PDF 識別條碼

## Introduction

歡迎閱讀我們的逐步指南，說明如何使用 Aspose.BarCode for Java 從 PDF 檔案 **read barcode java**。條碼在資料管理與組織中扮演關鍵角色，使用 Aspose.BarCode 可讓流程變得順暢。本教學將帶您完成所有步驟——從設定前置條件、產生條碼影像、將其加入 PDF、將 PDF 轉換為影像，最後解碼條碼影像。

## Quick Answers
- **此教學涵蓋什麼內容？** 產生條碼影像、將其嵌入 PDF、擷取影像，並重新讀取條碼。  
- **需要哪個函式庫？** Aspose.BarCode for Java（搭配 Aspose.PDF 用於 PDF 處理）。  
- **需要授權嗎？** 需要——在正式環境使用時必須擁有 Aspose.BarCode 授權與 Aspose.PDF 授權。  
- **可以使用其他條碼類型嗎？** 當然可以——API 支援多種條碼規格；本範例使用 CODE‑39。  
- **實作需要多久？** 基本的端對端流程大約需要 10‑15 分鐘。

## What is **read barcode java**?

在 Java 中讀取條碼是指使用條碼辨識函式庫，從影像或文件中擷取編碼資料。Aspose.BarCode 提供簡易的 API，無需外部工具即可完成解碼。

## Why use Aspose.BarCode for Java?
- **一站式解決方案** – 使用單一 SDK 即可產生、嵌入與解碼條碼。  
- **高精準度** – 支援 1D、2D 以及郵件條碼規格。  
- **無外部相依** – 可直接於純 Java 專案使用。  
- **完整 PDF 支援** – 與 Aspose.PDF 緊密整合，實現無縫的 PDF 操作。

## Prerequisites

在深入教學之前，請確保已完成以下前置作業：

1. **Aspose.BarCode for Java 授權** – 取得並設定有效的 Aspose.BarCode for Java 授權。您可從 [Aspose Purchase](https://purchase.aspose.com/buy) 取得授權。  
2. **Aspose.PDF 授權** – 另外，設定 Aspose.PDF 授權，此授權在處理 PDF 檔案時必須。您可於 [此處](https://purchase.aspose.com/temporary-license/) 申請授權。  
3. **下載 Aspose.BarCode for Java** – 從 [此處](https://releases.aspose.com/barcode/java/) 下載 Aspose.BarCode 函式庫。  

完成上述前置作業後，讓我們繼續匯入所需套件，開始本教學。

## Import Packages

在您的 Java 專案中，加入 Aspose.BarCode 與 Aspose.PDF 套件。以下提供範例程式碼供您參考：

```java
import com.aspose.barcode.*;
import com.aspose.barcode.License;
import com.aspose.barcode.barcoderecognition.BarCodeReader;
import com.aspose.barcode.barcoderecognition.BarCodeResult;
import com.aspose.barcode.barcoderecognition.BaseDecodeType;
import com.aspose.barcode.barcoderecognition.DecodeType;
import com.aspose.pdf.*;
import com.aspose.pdf.facades.PdfExtractor;
import java.awt.image.BufferedImage;
import java.io.File;
import javax.imageio.ImageIO;
```

## How to read barcode java from PDF

以下為完整的端對端工作流程。每一步皆以簡明文字說明，並保留原教學中的程式碼不變。

### Step 1: 產生條碼並加入 PDF

首先，我們使用 `BarcodeGenerator` **產生條碼影像**。此影像稍後會嵌入 PDF 文件中。

```java
BarcodeGenerator builder = new BarcodeGenerator(com.aspose.barcode.EncodeTypes.CODE_39_STANDARD);
builder.setCodeText("test123");
String strBarCodeImageSave = dataDir + "input_image1.jpg";
builder.save(strBarCodeImageSave);
```

### Step 2: 建立 PDF 並加入條碼影像

接著，我們 **將產生的條碼影像加入新 PDF**（即 *add barcode pdf*）。此步驟示範如何直接將影像嵌入 PDF 頁面。

```java
Document pdf1 = new Document();
Page page = pdf1.getPages().add();
BufferedImage originalImage = ImageIO.read(new File(strBarCodeImageSave));
page.getResources().getImages().add(originalImage);
pdf1.save(strPdfDoc);
```

### Step 3: 從 PDF 擷取影像

為了 **將 PDF 轉換為影像**，我們使用 `PdfExtractor`。此步驟將嵌入的條碼影像從 PDF 中抽取出來，以便進行解碼。

```java
PdfExtractor extractor = new PdfExtractor();
extractor.bindPdf(strPdfDoc);
extractor.extractImage();
```

### Step 4: 從抽取的影像辨識條碼

最後，我們使用 `BarCodeReader` **解碼條碼影像**（即 *decode barcode image*）。迴圈會處理每一張抽取的影像，並輸出解碼後的文字與條碼類型。

```java
String suffix = ".jpg";
int imageCount = 1;

while (extractor.hasNextImage()) {
    System.out.println("Extracting image " + imageCount);
    strBarCodeImage = "tmpbarcode" + imageCount + suffix;
    extractor.getNextImage(strBarCodeImage);

    BarCodeReader reader = new BarCodeReader(strBarCodeImage, DecodeType.CODE_39_EXTENDED);

    for (BarCodeResult result : reader.readBarCodes()) {
        System.out.println("CodeText: " + result.getCodeText());
        System.out.println("Symbology type: " + result.getCodeType());
    }

    imageCount++;
}
```

視需要重複上述步驟，並依實際情況調整檔名與路徑。

## Common Issues and Solutions

| Issue | Solution |
|-------|----------|
| **找不到授權** | 確保在呼叫任何 API 之前，已正確載入 Aspose.BarCode 與 Aspose.PDF 的授權。 |
| **未擷取到影像** | 確認 PDF 確實包含影像，且在綁定 PDF 後呼叫 `extractImage()`。 |
| **條碼類型不正確** | 使用與產生的條碼規格相符的 `DecodeType`（例如 `CODE_39_EXTENDED`）。 |
| **檔案路徑問題** | 使用絕對路徑，或確保工作目錄指向包含資源的資料夾。 |

## Frequently Asked Questions (FAQs)

### Q: 可以在沒有授權的情況下使用 Aspose.BarCode for Java 嗎？

雖然 Aspose.BarCode 可在未授權的情況下使用，但建議取得授權以獲得完整功能並遵守授權條款。

### Q: 如何取得 Aspose.BarCode for Java 的臨時授權？

您可於 [此處](https://purchase.aspose.com/temporary-license/) 取得臨時授權。

### Q: Aspose.BarCode 支援的條碼類型有什麼限制嗎？

Aspose.BarCode 支援多種條碼類型。完整清單請參考文件說明。

### Q: 是否提供 Aspose.BarCode for Java 的試用版？

是的，您可從 [此處](https://releases.aspose.com/) 下載試用版。

### Q: 在哪裡可以取得 Aspose.BarCode for Java 的支援或提問？

請前往 Aspose.BarCode [論壇](https://forum.aspose.com/c/barcode/13) 獲取支援與討論。

**Additional Quick FAQ**

**Q: 能從受密碼保護的 PDF 讀取條碼嗎？**  
A: 可以——在抽取前使用 Aspose.PDF 以正確的密碼載入 PDF。

**Q: 此方法能支援其他條碼規格嗎？**  
A: 當然可以。只需將 `EncodeTypes` 與 `DecodeType` 改為目標規格即可。

## Conclusion

恭喜！您已成功學會如何使用 Aspose.BarCode for Java 從 PDF **read barcode java**。本教學涵蓋產生條碼影像、將其嵌入 PDF、將 PDF 轉為影像，以及解碼條碼影像——全部以清晰的步驟說明。歡迎進一步探索 Aspose.BarCode 在 [文件](https://reference.aspose.com/barcode/java/) 中提供的更多功能與特性。

---

**最後更新：** 2025-12-19  
**測試環境：** Aspose.BarCode for Java 24.11, Aspose.PDF for Java 24.11  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}