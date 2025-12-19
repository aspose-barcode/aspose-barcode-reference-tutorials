---
date: 2025-12-19
description: 學習如何使用 Aspose.BarCode 從 Word 文件中讀取 Java 條碼。本指南涵蓋生成條碼圖像、將其插入 Word，以及提取圖像以進行條碼讀取。
linktitle: read barcode java from Word Documents
second_title: Aspose.BarCode Java API
title: 如何用 Java 從 Word 文件讀取條碼
url: /zh-hant/java/document-barcode-recognition/recognizing-barcodes-from-word/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何從 Word 文件中讀取條碼（Java）

## Introduction

在 Java 應用程式中處理條碼是常見需求，尤其是當條碼嵌入於 Microsoft Word 檔案時。在本教學中，您將學習 **如何讀取條碼 Java** 從 Word 文件使用 Aspose.BarCode for Java。我們將示範產生條碼影像、將條碼加入 Word 檔案、從 Word 文件中擷取影像，最後以 Java 條碼讀取器範例解碼條碼。

## Quick Answers
- **使用的函式庫是？** Aspose.BarCode for Java（搭配 Aspose.Words 處理影像）  
- **可以將條碼加入 Word 嗎？** 可以 – 先產生影像，再使用 Aspose.Words 插入  
- **如何從 Word 擷取影像？** 使用 `Document.getChildNodes(NodeType.SHAPE, true)`  
- **有 Java 條碼讀取器範例嗎？** 第 3 步的程式碼展示完整範例  
- **前置需求是什麼？** JDK、Aspose.BarCode for Java、IDE（Eclipse/IntelliJ）

## What is barcode recognition in Java?

在 Java 中的條碼辨識指的是使用如 Aspose.BarCode 等函式庫，從影像或文件中偵測並解碼條碼符號的過程。它讓應用程式能自動讀取產品代碼、庫存編號或任何編碼資料，無需人工輸入。

## Why read barcode java from Word documents?

在 Word 檔案中直接嵌入條碼對於合約、運送標籤或報告等需要視覺呈現代碼的情境非常有用。能夠 **從 Word 擷取影像** 並以程式方式解碼，省去手動掃描的步驟，降低錯誤率。

## Prerequisites

在開始之前，請確保您已具備：

- **Java Development Kit (JDK)** – 在機器上安裝最新的 JDK。  
- **Aspose.BarCode for Java** – 從官方網站 [here](https://releases.aspose.com/barcode/java/) 下載函式庫。  
- **整合開發環境 (IDE)** – 如 Eclipse 或 IntelliJ IDEA，用於編寫與執行程式碼。

## Import Packages

在您的 Java 專案中，匯入必要的 Aspose.BarCode 與 Aspose.Words 套件：

```java
import java.text.MessageFormat;

import com.aspose.barcode.EncodeTypes;
import com.aspose.barcode.barcoderecognition.BarCodeReader;
import com.aspose.barcode.barcoderecognition.BarCodeResult;
import com.aspose.barcode.barcoderecognition.DecodeType;
import com.aspose.barcode.generation.BarcodeGenerator;
import com.aspose.words.ImageType;
import com.aspose.words.NodeCollection;
import com.aspose.words.NodeType;
```

## Step 1: Generate a barcode image (generate barcode image java)

首先，使用 Aspose.BarCode 建立條碼影像。此影像將稍後 **加入條碼至 Word**：

```java
BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.CODE_39_STANDARD);
generator.setCodeText("test-123");
String strBarCodeImageSave = dataDir + "img.jpg";
generator.save(strBarCodeImageSave);
```

## Step 2: Insert the barcode image into a Word document (insert image into word)

接下來，我們使用 Aspose.Words **將影像插入 Word** 並儲存文件：

```java
Document doc = new Document();
DocumentBuilder docBuilder = new DocumentBuilder(doc);
docBuilder.insertImage(strBarCodeImageSave);
String strWordFile = "docout.doc";
doc.save(dataDir + strWordFile);
```

## Step 3: Recognize barcodes from the Word document (java barcode reader example)

最後，從 Word 檔案中擷取每張影像，並執行 **java 條碼讀取器範例** 以解碼條碼：

```java
NodeCollection<Shape> shapes = doc.getChildNodes(NodeType.SHAPE, true);
int imageIndex = 0;

for (Shape shape : shapes) {
    if (shape.hasImage()) {
        // Extract image to file
        String extension = ImageTypeToExtension(shape.getImageData().getImageType());
        String imageFileName = MessageFormat.format("Image.ExportImages.{0} Out.{1}", imageIndex, extension);
        String strBarCodeImageExtracted = "" + imageFileName;
        shape.getImageData().save(strBarCodeImageExtracted);

        // Recognize barcode from this image
        BarCodeReader reader = new BarCodeReader(strBarCodeImageSave, DecodeType.CODE_39_STANDARD);
        for (BarCodeResult result : reader.readBarCodes()) {
            System.out.println("CodeText: " + result.getCodeText());
            System.out.println("Symbology type: " + result.getCodeType());
        }
        imageIndex++;
    }
}
```

> **注意：** 上述迴圈示範了 **從 Word 擷取影像**，將每張影像儲存後，再使用相同的影像檔案路徑解碼條碼。請依您的環境調整檔案路徑（`dataDir`）。

## Common Issues & Tips

- **檔案路徑不匹配** – 確認 `dataDir` 指向有效資料夾；否則讀取器會拋出 `FileNotFoundException`。  
- **不支援的條碼類型** – 範例使用 `CODE_39_STANDARD`。若需 QR、DataMatrix 等，請同時更改 `EncodeTypes` 與 `DecodeType`。  
- **效能** – 對於大型文件，考慮使用平行串流處理影像，以加速辨識。

## Frequently Asked Questions (FAQs)

### Q: Can I use Aspose.BarCode for Java in commercial projects?
可以，Aspose.BarCode for Java 可用於商業專案。您可於 [here](https://purchase.aspose.com/buy) 查看授權細節。

### Q: Is there a free trial available for Aspose.BarCode for Java?
可以，您可從 [here](https://releases.aspose.com/) 下載免費試用版，體驗 Aspose.BarCode for Java 的功能。

### Q: How do I get support for Aspose.BarCode for Java?
如需協助或詢問，請前往 Aspose.BarCode 論壇 [here](https://forum.aspose.com/c/barcode/13)。

### Q: Are temporary licenses available for Aspose.BarCode for Java?
可以，您可於 [here](https://purchase.aspose.com/temporary-license/) 取得臨時授權。

### Q: Where can I find the documentation for Aspose.BarCode for Java?
請參考完整文件說明 [here](https://reference.aspose.com/barcode/java/)。

## Additional FAQs

**Q: Can I read other barcode symbologies besides Code 39?**  
A: 當然可以。只要在產生時更改 `EncodeTypes`，在讀取時更改 `DecodeType`，即可匹配所需的條碼類型（例如 `EncodeTypes.QR`、`DecodeType.QR`）。

**Q: Does this approach work with .docx files as well?**  
A: 是的。Aspose.Words 能透明處理 `.doc` 與 `.docx` 格式，相同程式碼皆可使用。

**Q: How can I improve recognition accuracy for low‑resolution images?**  
A: 可在儲存條碼影像時提升 DPI（例如 `generator.save(strBarCodeImageSave, BarCodeImageFormat.JPEG, 300)`），或改用 PNG 等較高品質的影像格式，以提升低解析度影像的辨識準確度。

---

**最後更新：** 2025-12-19  
**測試環境：** Aspose.BarCode for Java 24.11 與 Aspose.Words for Java 24.11  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}