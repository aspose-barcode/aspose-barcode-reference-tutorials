---
date: 2026-04-08
description: Узнайте, как считывать штрих‑код из PDF в Java с помощью Aspose.BarCode.
  Это руководство также показывает, как генерировать изображение штрих‑кода в Java
  и извлекать изображения из PDF в Java.
keywords:
- read barcode from pdf java
- generate barcode image java
- extract images from pdf java
linktitle: Распознавание штрих‑кодов из PDF
second_title: Aspose.BarCode Java API
title: Как считать штрих‑код из PDF в Java с помощью Aspose.BarCode
url: /ru/java/document-barcode-recognition/recognizing-barcodes-from-pdf/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Чтение штрих‑кода из PDF на Java

## Введение

Добро пожаловать в наше пошаговое руководство по **how to read barcode from PDF in Java** с использованием Aspose.BarCode. Штрих‑коды необходимы для автоматизации захвата данных, и с Aspose.BarCode вы можете бесшовно обнаруживать их в PDF‑документах. В этом уроке мы пройдем всё, что вам нужно — от настройки лицензий до генерации изображения штрих‑кода Java, добавления его в PDF, извлечения изображений из PDF Java и, наконец, чтения штрих‑кода.

## Быстрые ответы
- **Какая библиотека нужна?** Aspose.BarCode for Java (plus Aspose.PDF for PDF handling).  
- **Могу ли я сгенерировать изображение штрих‑кода в Java?** Yes – the `BarcodeGenerator` class lets you create PNG/JPEG images.  
- **Как извлекаются изображения из PDF?** Use `PdfExtractor` from Aspose.PDF.  
- **Какой тип штрих‑кода демонстрируется?** CODE‑39 (standard).  
- **Нужна ли лицензия?** A valid Aspose.BarCode and Aspose.PDF license is required for production use.

## Почему использовать Aspose.BarCode для Java?
- **Высокая точность** – supports dozens of symbologies and works on low‑resolution images.  
- **Нет внешних зависимостей** – pure Java, no native libraries.  
- **Полная интеграция с PDF** – combine with Aspose.PDF to read or embed barcodes directly in PDF files.

## Предварительные требования

Before diving into the code, ensure you have:

1. **Aspose.BarCode for Java License** – obtain one from [Aspose Purchase](https://purchase.aspose.com/buy).  
2. **Aspose.PDF License** – required for PDF manipulation; you can apply for a license [here](https://purchase.aspose.com/temporary-license/).  
3. **Aspose.BarCode library** – download the latest JAR from [here](https://releases.aspose.com/barcode/java/).  

Now that you have the necessary prerequisites, let’s import the required packages and start coding.

## Импорт пакетов

In your Java project, add the Aspose.BarCode and Aspose.PDF imports. This block is unchanged from the original tutorial:

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

## Шаг 1: Сгенерировать изображение штрих‑кода Java

First, we create a barcode image that we will later embed into a PDF. This demonstrates the **generate barcode image java** capability.

```java
BarcodeGenerator builder = new BarcodeGenerator(com.aspose.barcode.EncodeTypes.CODE_39_STANDARD);
builder.setCodeText("test123");
String strBarCodeImageSave = dataDir + "input_image1.jpg";
builder.save(strBarCodeImageSave);
```

## Шаг 2: Создать PDF и добавить изображение штрих‑кода

Next, we build a new PDF document and insert the barcode image we just generated.

```java
Document pdf1 = new Document();
Page page = pdf1.getPages().add();
BufferedImage originalImage = ImageIO.read(new File(strBarCodeImageSave));
page.getResources().getImages().add(originalImage);
pdf1.save(strPdfDoc);
```

## Шаг 3: Извлечь изображения из PDF Java

With the PDF ready, we need to pull the embedded image back out so the barcode can be read. This uses **extract images from pdf java**.

```java
PdfExtractor extractor = new PdfExtractor();
extractor.bindPdf(strPdfDoc);
extractor.extractImage();
```

## Шаг 4: Распознать штрих‑код из извлечённых изображений

Finally, we feed each extracted image to `BarCodeReader` to retrieve the encoded text.

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

Repeat these steps as needed, adjusting filenames and paths to fit your project structure.

## Распространённые проблемы и решения

| Проблема | Причина | Решение |
|----------|---------|----------|
| **Штрих‑код не обнаружен** | Качество изображения слишком низкое или штрих‑код слишком маленький. | Увеличьте разрешение изображения при сохранении (`builder.save(..., BarCodeImageFormat.JPEG, 300)`). |
| **`PdfExtractor` throws an exception** | PDF‑файл не найден или путь неверный. | Убедитесь, что `strPdfDoc` указывает на существующий файл и приложение имеет права чтения. |
| **Лицензия не применена** | Компоненты Aspose работают в пробном режиме, ограничивая вывод. | Загрузите файлы лицензий в начале программы: `new License().setLicense("Aspose.BarCode.lic");` и аналогично для Aspose.PDF. |

## Часто задаваемые вопросы (FAQ)

### Q: Можно ли использовать Aspose.BarCode для Java без лицензии?
While Aspose.BarCode can be used without a license, it is recommended to obtain one for full functionality and to comply with licensing terms.

### Q: Как получить временную лицензию для Aspose.BarCode для Java?
You can obtain a temporary license [here](https://purchase.aspose.com/temporary-license/).

### Q: Есть ли ограничения на типы штрих‑кодов, поддерживаемые Aspose.BarCode?
Aspose.BarCode supports a wide range of barcode types. Refer to the documentation for a complete list.

### Q: Есть ли пробная версия Aspose.BarCode для Java?
Yes, you can download the trial version from [here](https://releases.aspose.com/).

### Q: Где можно получить поддержку или задать вопросы о Aspose.BarCode для Java?
Visit the Aspose.BarCode [forum](https://forum.aspose.com/c/barcode/13) for support and discussions.

## Заключение

Congratulations! You’ve learned how to **read barcode from PDF in Java** using Aspose.BarCode, how to **generate barcode image Java**, and how to **extract images from PDF Java** for further processing. Feel free to explore additional features such as batch processing, handling different barcode symbologies, or integrating with other Aspose products. For deeper details, check the official [documentation](https://reference.aspose.com/barcode/java/).

---

**Последнее обновление:** 2026-04-08  
**Тестировано с:** Aspose.BarCode for Java 24.12, Aspose.PDF for Java 24.12  
**Автор:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}