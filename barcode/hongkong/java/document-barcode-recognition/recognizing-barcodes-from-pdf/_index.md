---
date: 2026-04-08
description: 學習如何在 Java 中使用 Aspose.BarCode 從 PDF 讀取條碼。本指南亦示範如何在 Java 中產生條碼圖像以及從 PDF
  中提取圖像。
keywords:
- read barcode from pdf java
- generate barcode image java
- extract images from pdf java
linktitle: 從 PDF 識別條碼
second_title: Aspose.BarCode Java API
title: 如何在 Java 中使用 Aspose.BarCode 從 PDF 讀取條碼
url: /zh-hant/java/document-barcode-recognition/recognizing-barcodes-from-pdf/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 從 PDF 讀取條碼（Java）

## 介紹

歡迎閱讀我們的逐步指南，說明如何使用 Aspose.BarCode 在 Java 中 **從 PDF 讀取條碼**。條碼對於自動化資料擷取至關重要，透過 Aspose.BarCode 您可以在 PDF 文件中無縫偵測條碼。本教學將帶您完成所有步驟——從設定授權、產生條碼影像（Java）、將其加入 PDF、從 PDF（Java）提取影像，最後讀取條碼。

## 快速解答
- **需要哪個函式庫？** Aspose.BarCode for Java（加上用於 PDF 處理的 Aspose.PDF）。  
- **我可以在 Java 中產生條碼影像嗎？** 可以——`BarcodeGenerator` 類別可用於建立 PNG/JPEG 影像。  
- **如何從 PDF 中提取影像？** 使用 Aspose.PDF 的 `PdfExtractor`。  
- **示範使用哪種條碼類型？** CODE‑39（標準）。  
- **是否需要授權？** 生產環境必須擁有有效的 Aspose.BarCode 與 Aspose.PDF 授權。

## 為何選擇 Aspose.BarCode for Java？
- **高精度**——支援數十種編碼規格，且在低解析度影像上亦能正常運作。  
- **無外部相依性**——純 Java，無需本機函式庫。  
- **完整 PDF 整合**——結合 Aspose.PDF，可直接在 PDF 檔案中讀取或嵌入條碼。

## 前置條件

在深入程式碼之前，請先確認您已具備以下項目：

1. **Aspose.BarCode for Java 授權**——可從 [Aspose Purchase](https://purchase.aspose.com/buy) 取得。  
2. **Aspose.PDF 授權**——PDF 操作所必需，您可於 [此處](https://purchase.aspose.com/temporary-license/) 申請授權。  
3. **Aspose.BarCode 程式庫**——可從 [此處](https://releases.aspose.com/barcode/java/) 下載最新的 JAR。  

取得上述前置條件後，讓我們匯入所需的套件並開始編寫程式。

## 匯入套件

在您的 Java 專案中，加入 Aspose.BarCode 與 Aspose.PDF 的匯入語句。以下程式碼區塊與原教學相同：

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

## 步驟 1：產生條碼影像（Java）

首先，我們產生一個條碼影像，稍後會將其嵌入 PDF 中。此步驟示範 **generate barcode image java** 功能。

```java
BarcodeGenerator builder = new BarcodeGenerator(com.aspose.barcode.EncodeTypes.CODE_39_STANDARD);
builder.setCodeText("test123");
String strBarCodeImageSave = dataDir + "input_image1.jpg";
builder.save(strBarCodeImageSave);
```

## 步驟 2：建立 PDF 並加入條碼影像

接著，我們建立新的 PDF 文件，並插入剛才產生的條碼影像。

```java
Document pdf1 = new Document();
Page page = pdf1.getPages().add();
BufferedImage originalImage = ImageIO.read(new File(strBarCodeImageSave));
page.getResources().getImages().add(originalImage);
pdf1.save(strPdfDoc);
```

## 步驟 3：從 PDF 提取影像（Java）

PDF 準備完成後，我們需要將嵌入的影像取出，以便讀取條碼。此步驟使用 **extract images from pdf java**。

```java
PdfExtractor extractor = new PdfExtractor();
extractor.bindPdf(strPdfDoc);
extractor.extractImage();
```

## 步驟 4：從提取的影像辨識條碼

最後，我們將每個提取的影像傳入 `BarCodeReader`，以取得編碼文字。

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

依需求重複上述步驟，並依專案結構調整檔名與路徑。

## 常見問題與解決方案

| 問題 | 原因 | 解決方法 |
|-------|--------|-----|
| **未偵測到條碼** | 影像品質過低或條碼尺寸過小。 | 儲存時提高影像解析度（例如 `builder.save(..., BarCodeImageFormat.JPEG, 300)`）。 |
| **`PdfExtractor` 拋出例外** | 找不到 PDF 檔案或路徑不正確。 | 確認 `strPdfDoc` 指向已存在的檔案，且應用程式具備讀取權限。 |
| **授權未套用** | Aspose 元件以試用模式執行，導致輸出受限。 | 在程式開始時載入授權檔案：`new License().setLicense("Aspose.BarCode.lic");`，Aspose.PDF 亦同。 |

## 常見問題 (FAQs)

### Q: 我可以在沒有授權的情況下使用 Aspose.BarCode for Java 嗎？
雖然 Aspose.BarCode 可在未取得授權的情況下使用，但建議取得授權以獲得完整功能並遵守授權條款。

### Q: 如何取得 Aspose.BarCode for Java 的臨時授權？
您可於 [此處](https://purchase.aspose.com/temporary-license/) 取得臨時授權。

### Q: Aspose.BarCode 支援的條碼類型是否有限制？
Aspose.BarCode 支援多種條碼類型，完整清單請參考文件說明。

### Q: 是否提供 Aspose.BarCode for Java 的試用版？
是的，您可從 [此處](https://releases.aspose.com/) 下載試用版。

### Q: 我可以在哪裡取得 Aspose.BarCode for Java 的支援或提問？
請前往 Aspose.BarCode [論壇](https://forum.aspose.com/c/barcode/13) 取得支援與討論。

## 結論

恭喜！您已學會如何使用 Aspose.BarCode **在 Java 中從 PDF 讀取條碼**、**產生條碼影像（Java）**，以及 **從 PDF（Java）提取影像** 以進行後續處理。歡迎探索其他功能，例如批次處理、不同條碼編碼的處理，或與其他 Aspose 產品整合。欲取得更深入的資訊，請參考官方 [文件](https://reference.aspose.com/barcode/java/)。

---

**最後更新：** 2026-04-08  
**測試環境：** Aspose.BarCode for Java 24.12, Aspose.PDF for Java 24.12  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}