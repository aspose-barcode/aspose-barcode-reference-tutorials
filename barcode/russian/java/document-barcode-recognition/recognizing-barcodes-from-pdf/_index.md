---
date: 2025-12-19
description: Узнайте, как считывать штрихкоды Java из PDF‑файлов с помощью Aspose.BarCode.
  Это пошаговое руководство показывает, как эффективно генерировать изображение штрихкода
  и декодировать его.
linktitle: Recognizing Barcodes from PDF
second_title: Aspose.BarCode Java API
title: Чтение штрихкодов Java – Распознавание штрихкодов из PDF
url: /ru/java/document-barcode-recognition/recognizing-barcodes-from-pdf/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Считывание штрихкода Java – Распознавание штрихкодов из PDF

## Введение

Добро пожаловать в наше пошаговое руководство по **how to read barcode java** из PDF‑файлов с использованием Aspose.BarCode for Java. Штрихкоды играют важную роль в управлении данными и их организации, а с Aspose.BarCode процесс становится бесшовным. В этом учебнике мы пройдем всё необходимое — от настройки предварительных требований до генерации изображения штрихкода, его добавления в PDF, преобразования PDF в изображения и, наконец, декодирования изображения штрихкода.

## Быстрые ответы
- **What does this tutorial cover?** Генерация изображения штрихкода, внедрение его в PDF, извлечение изображений и чтение штрихкода обратно.  
- **Which library is required?** Aspose.BarCode for Java (с Aspose.PDF для работы с PDF).  
- **Do I need a license?** Да — требуется лицензия Aspose.BarCode и лицензия Aspose.PDF для использования в продакшене.  
- **Can I use other barcode types?** Конечно — API поддерживает множество символогий; в примере используется CODE‑39.  
- **How long does implementation take?** Около 10‑15 минут для базового сквозного процесса.

## Что такое **read barcode java**?
Считывание штрихкода в Java означает извлечение закодированных данных из изображения или документа с помощью библиотеки распознавания штрихкодов. Aspose.BarCode предоставляет простой API, который выполняет декодирование без необходимости внешних инструментов.

## Почему использовать Aspose.BarCode for Java?
- **All‑in‑one solution** – генерация, внедрение и декодирование штрихкодов с помощью единого SDK.  
- **High accuracy** – поддерживает 1D, 2D и почтовые символогии.  
- **No external dependencies** – работает с обычными Java‑проектами.  
- **Robust PDF support** – тесно интегрируется с Aspose.PDF для бесшовной работы с PDF.

## Предварительные требования

Прежде чем приступать к учебнику, убедитесь, что у вас есть следующие предварительные требования:

1. **Aspose.BarCode for Java License** – Получите и настройте действующую лицензию для Aspose.BarCode for Java. Вы можете приобрести лицензию по ссылке [Aspose Purchase](https://purchase.aspose.com/buy).
2. **Aspose.PDF License** – Кроме того, настройте лицензию для Aspose.PDF, которая требуется для работы с PDF‑файлами. Вы можете запросить лицензию [здесь](https://purchase.aspose.com/temporary-license/).
3. **Download Aspose.BarCode for Java** – Скачайте библиотеку Aspose.BarCode по ссылке [here](https://releases.aspose.com/barcode/java/).

Теперь, когда у вас есть все необходимые предварительные требования, перейдём к импорту требуемых пакетов и начнём наш учебник.

## Импорт пакетов

В вашем Java‑проекте включите пакеты Aspose.BarCode и Aspose.PDF. Ниже приведён пример кода, с которого можно начать:

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

## Как считывать штрихкод java из PDF

Ниже представлен полный сквозной рабочий процесс. Каждый шаг объяснён простым языком, а сопутствующий код остаётся неизменным по сравнению с оригинальным учебником.

### Шаг 1: Генерация штрихкода и добавление в PDF

Сначала мы **генерируем изображение штрихкода** с помощью `BarcodeGenerator`. Это изображение позже будет внедрено в документ PDF.

```java
BarcodeGenerator builder = new BarcodeGenerator(com.aspose.barcode.EncodeTypes.CODE_39_STANDARD);
builder.setCodeText("test123");
String strBarCodeImageSave = dataDir + "input_image1.jpg";
builder.save(strBarCodeImageSave);
```

### Шаг 2: Создание PDF и добавление изображения штрихкода

Затем мы **добавляем сгенерированное изображение штрихкода в новый PDF** (т.е. *add barcode pdf*). Это демонстрирует, как внедрять изображения непосредственно на страницу PDF.

```java
Document pdf1 = new Document();
Page page = pdf1.getPages().add();
BufferedImage originalImage = ImageIO.read(new File(strBarCodeImageSave));
page.getResources().getImages().add(originalImage);
pdf1.save(strPdfDoc);
```

### Шаг 3: Извлечение изображений из PDF

Чтобы **преобразовать PDF в изображения**, мы используем `PdfExtractor`. Этот шаг извлекает внедрённое изображение штрихкода из PDF для последующего декодирования.

```java
PdfExtractor extractor = new PdfExtractor();
extractor.bindPdf(strPdfDoc);
extractor.extractImage();
```

### Шаг 4: Распознавание штрихкода из извлечённых изображений

Наконец, мы **декодируем изображение штрихкода** (т.е. *decode barcode image*) с помощью `BarCodeReader`. Цикл обрабатывает каждое извлечённое изображение и выводит декодированный текст и символогию.

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

Повторяйте эти шаги по мере необходимости, корректируя имена файлов и пути соответственно.

## Распространённые проблемы и решения

| Issue | Solution |
|-------|----------|
| **License not found** | Убедитесь, что лицензии Aspose.BarCode и Aspose.PDF правильно загружены до любых вызовов API. |
| **No images extracted** | Убедитесь, что PDF действительно содержит изображения и что `extractImage()` вызывается после привязки PDF. |
| **Incorrect barcode type** | Используйте соответствующий `DecodeType`, соответствующий символогии, которую вы сгенерировали (например, `CODE_39_EXTENDED`). |
| **File path problems** | Используйте абсолютные пути или убедитесь, что рабочий каталог установлен в папку, содержащую ваши ресурсы. |

## Часто задаваемые вопросы (FAQ)

### В: Можно ли использовать Aspose.BarCode for Java без лицензии?
Хотя Aspose.BarCode можно использовать без лицензии, рекомендуется получить её для полной функциональности и соблюдения условий лицензирования.

### В: Как получить временную лицензию для Aspose.BarCode for Java?
Вы можете получить временную лицензию [здесь](https://purchase.aspose.com/temporary-license/).

### В: Есть ли ограничения на типы штрихкодов, поддерживаемые Aspose.BarCode?
Aspose.BarCode поддерживает широкий спектр типов штрихкодов. Обратитесь к документации для полного списка.

### В: Доступна ли пробная версия Aspose.BarCode for Java?
Да, вы можете скачать пробную версию [здесь](https://releases.aspose.com/).

### В: Где я могу получить поддержку или задать вопросы о Aspose.BarCode for Java?
Посетите форум Aspose.BarCode [forum](https://forum.aspose.com/c/barcode/13) для поддержки и обсуждений.

**Дополнительные быстрые FAQ**

**В: Можно ли считывать штрихкоды из PDF, защищённых паролем?**  
**О:** Да — загрузите PDF с соответствующим паролем, используя Aspose.PDF перед извлечением.

**В: Работает ли этот подход с другими символогиями штрихкодов?**  
**О:** Абсолютно. Измените `EncodeTypes` и `DecodeType` в соответствии с требуемой символогией.

## Заключение

Поздравляем! Вы успешно узнали, как **read barcode java** из PDF с помощью Aspose.BarCode for Java. В этом учебнике рассматривалось создание изображения штрихкода, внедрение его в PDF, преобразование PDF в изображения и декодирование изображения штрихкода — всё с понятным пошаговым кодом. Не стесняйтесь исследовать дополнительные возможности и функции, предлагаемые Aspose.BarCode в [документации](https://reference.aspose.com/barcode/java/).

---

**Последнее обновление:** 2025-12-19  
**Тестировано с:** Aspose.BarCode for Java 24.11, Aspose.PDF for Java 24.11  
**Автор:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}