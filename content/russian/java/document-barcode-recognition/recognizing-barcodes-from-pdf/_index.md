---
title: Распознавание штрих-кодов из PDF в Java
linktitle: Распознавание штрих-кодов из PDF
second_title: API Aspose.BarCode Java
description: Узнайте, как распознавать штрих-коды в PDF-файлах на Java с помощью Aspose.BarCode. Пошаговое руководство с примерами кода. Повысьте эффективность управления данными!
type: docs
weight: 11
url: /ru/java/document-barcode-recognition/recognizing-barcodes-from-pdf/
---

## Введение

Добро пожаловать в наше пошаговое руководство по распознаванию штрих-кодов в PDF-файлах с помощью Aspose.BarCode для Java. Штрих-коды играют решающую роль в управлении и организации данных, а с Aspose.BarCode этот процесс становится гладким. В этом руководстве мы проведем вас через весь процесс: от настройки необходимых предварительных условий до реализации кода для распознавания штрих-кода в PDF-файле.

## Предварительные условия

Прежде чем приступить к изучению руководства, убедитесь, что у вас есть следующие предварительные условия:

1.  Лицензия Aspose.BarCode для Java: получите и настройте действительную лицензию для Aspose.BarCode для Java. Вы можете приобрести лицензию у[Aspose покупка](https://purchase.aspose.com/buy).

2.  Лицензия Aspose.PDF: дополнительно настройте лицензию для Aspose.PDF, которая необходима для работы с файлами PDF. Вы можете подать заявку на получение лицензии[здесь](https://purchase.aspose.com/temporary-license/).

3.  Загрузите Aspose.BarCode для Java: Загрузите библиотеку Aspose.BarCode с сайта[здесь](https://releases.aspose.com/barcode/java/).

Теперь, когда у вас есть необходимые предварительные условия, давайте приступим к импорту необходимых пакетов и начнем наше руководство.

## Импортировать пакеты

В свой проект Java включите пакеты Aspose.BarCode и Aspose.PDF. Вот пример фрагмента кода, который поможет вам начать:

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

## Шаг 1. Создайте штрих-код и добавьте в PDF

```java
BarcodeGenerator builder = new BarcodeGenerator(com.aspose.barcode.EncodeTypes.CODE_39_STANDARD);
builder.setCodeText("test123");
String strBarCodeImageSave = dataDir + "input_image1.jpg";
builder.save(strBarCodeImageSave);
```

## Шаг 2. Создайте PDF-файл и добавьте изображение штрих-кода

```java
Document pdf1 = new Document();
Page page = pdf1.getPages().add();
BufferedImage originalImage = ImageIO.read(new File(strBarCodeImageSave));
page.getResources().getImages().add(originalImage);
pdf1.save(strPdfDoc);
```

## Шаг 3. Извлечение изображений из PDF

```java
PdfExtractor extractor = new PdfExtractor();
extractor.bindPdf(strPdfDoc);
extractor.extractImage();
```

## Шаг 4. Распознайте штрих-код из извлеченных изображений

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

При необходимости повторите эти шаги, соответствующим образом изменив имена файлов и пути.

## Заключение

 Поздравляем! Вы успешно научились распознавать штрих-коды в PDF-файлах с помощью Aspose.BarCode для Java. Целью этого руководства было предоставить исчерпывающее руководство, сохраняя при этом простоту и ясность. Не стесняйтесь изучить дополнительные возможности и возможности, предлагаемые Aspose.BarCode в[документация](https://reference.aspose.com/barcode/java/).

## Часто задаваемые вопросы (FAQ)

### Вопрос: Могу ли я использовать Aspose.BarCode для Java без лицензии?
Хотя Aspose.BarCode можно использовать без лицензии, рекомендуется получить ее для обеспечения полной функциональности и соблюдения условий лицензирования.

### Вопрос: Как я могу получить временную лицензию на Aspose.BarCode для Java?
 Вы можете получить временную лицензию[здесь](https://purchase.aspose.com/temporary-license/).

### Вопрос: Существуют ли какие-либо ограничения на типы штрих-кодов, поддерживаемые Aspose.BarCode?
Aspose.BarCode поддерживает широкий спектр типов штрих-кодов. Полный список см. в документации.

### Вопрос: Доступна ли пробная версия Aspose.BarCode для Java?
 Да, вы можете скачать пробную версию с сайта[здесь](https://releases.aspose.com/).

### Вопрос: Где я могу обратиться за поддержкой или задать вопросы об Aspose.BarCode для Java?
 Посетите Aspose.BarCode[Форум](https://forum.aspose.com/c/barcode/13) за поддержку и обсуждения.
