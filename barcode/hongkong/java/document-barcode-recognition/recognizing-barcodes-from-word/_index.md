---
title: 輕鬆識別 Word 文件中的條碼
linktitle: 識別Word文件中的條碼
second_title: Aspose.BarCode Java API
description: 探索使用 Aspose.BarCode 將條碼識別無縫整合到您的 Java 應用程式中。請依照本教學識別 Word 文件中的條碼。
weight: 12
url: /zh-hant/java/document-barcode-recognition/recognizing-barcodes-from-word/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 輕鬆識別 Word 文件中的條碼


## 介紹

在 Java 程式設計的動態世界中，高效率使用條碼的需求不斷增長。從 Word 文件中識別條碼是一個常見的需求，幸運的是，Aspose.BarCode for Java 提供了一個強大的解決方案。在本教學中，我們將引導您完成使用 Aspose.BarCode for Java 從 Word 文件中識別條碼的過程。

## 先決條件

在我們深入學習本教程之前，請確保您符合以下先決條件：

- Java 開發工具包 (JDK)：Aspose.BarCode for Java 需要 Java 開發環境。確保您的系統上安裝了最新的 JDK。

-  Aspose.BarCode for Java：下載並安裝 Aspose.BarCode for Java 函式庫。你可以找到下載鏈接[這裡](https://releases.aspose.com/barcode/java/).

- 整合開發環境 (IDE)：選擇您喜歡的 IDE，例如 Eclipse 或 IntelliJ，以跟隨範例進行操作。

## 導入包

在您的 Java 專案中，匯入必要的 Aspose.BarCode 套件即可開始：

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

## 第 1 步：產生條碼圖像

首先，使用 Aspose.BarCode 建立條碼圖像。設定程式碼文字並儲存圖像：

```java
BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.CODE_39_STANDARD);
generator.setCodeText("test-123");
String strBarCodeImageSave = dataDir + "img.jpg";
generator.save(strBarCodeImageSave);
```

## 步驟 2：將圖片新增至 Word 文件

現在，使用 Aspose.Words 將產生的條碼圖片插入 Word 文件中：

```java
Document doc = new Document();
DocumentBuilder docBuilder = new DocumentBuilder(doc);
docBuilder.insertImage(strBarCodeImageSave);
String strWordFile = "docout.doc";
doc.save(dataDir + strWordFile);
```

## 步驟 3：識別 Word 文件中的條碼

接下來，從 Word 文件中提取圖像並使用 Aspose.BarCode 識別條碼：

```java
NodeCollection<Shape> shapes = doc.getChildNodes(NodeType.SHAPE, true);
int imageIndex = 0;

for (Shape shape : shapes) {
    if (shape.hasImage()) {
        //將圖像提取到文件
        String extension = ImageTypeToExtension(shape.getImageData().getImageType());
        String imageFileName = MessageFormat.format("Image.ExportImages.{0} Out.{1}", imageIndex, extension);
        String strBarCodeImageExtracted = "" + imageFileName;
        shape.getImageData().save(strBarCodeImageExtracted);

        //從此影像中辨識條碼
        BarCodeReader reader = new BarCodeReader(strBarCodeImageSave, DecodeType.CODE_39_STANDARD);
        for (BarCodeResult result : reader.readBarCodes()) {
            System.out.println("CodeText: " + result.getCodeText());
            System.out.println("Symbology type: " + result.getCodeType());
        }
        imageIndex++;
    }
}
```

重複這些步驟，您將使用 Aspose.BarCode for Java 成功識別 Word 文件中的條碼。

## 結論

總之，利用 Aspose.BarCode for Java 簡化了從 Word 文件中辨識條碼的過程。按照上述步驟操作，您將可以將條碼識別無縫整合到您的 Java 應用程式中。

## 常見問題 (FAQ)

### Q：我可以在商業專案中使用 Aspose.BarCode for Java 嗎？
是的，Aspose.BarCode for Java 可用於商業用途。您可以找到許可詳細信息[這裡](https://purchase.aspose.com/buy).

### Q：Aspose.BarCode for Java 是否有免費試用版？
是的，您可以透過下載免費試用版來探索 Aspose.BarCode for Java 的功能[這裡](https://releases.aspose.com/).

### Q：如何獲得 Aspose.BarCode for Java 支援？
如需任何協助或疑問，請造訪 Aspose.BarCode 論壇[這裡](https://forum.aspose.com/c/barcode/13).

### Q：Aspose.BarCode for Java 是否有臨時授權？
是的，您可以獲得臨時許可證[這裡](https://purchase.aspose.com/temporary-license/).

### Q：在哪裡可以找到 Aspose.BarCode for Java 的文檔？
請參閱綜合文檔[這裡](https://reference.aspose.com/barcode/java/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
