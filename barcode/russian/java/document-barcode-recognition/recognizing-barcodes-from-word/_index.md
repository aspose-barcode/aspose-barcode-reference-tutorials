---
date: 2026-04-12
description: Узнайте, как распознавать штрих‑коды из документов Word с помощью Aspose.BarCode
  for Java. Это руководство также показывает, как добавить штрих‑код в Word и извлечь
  изображения из Word.
keywords:
- how to recognize barcode
- add barcode to word
- read barcode from image
- extract images from word
- barcode detection java
linktitle: Распознавание штрихкодов из документов Word
second_title: Aspose.BarCode Java API
title: Как распознать штрих‑код из документов Word — руководство по Java
url: /ru/java/document-barcode-recognition/recognizing-barcodes-from-word/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Как распознать штрих‑код из документов Word – Руководство Java

## Введение

Если вам нужно **как распознать штрих‑код**, встроенный в файл Microsoft Word, вы попали по адресу. В этом руководстве мы пройдем полный пример от начала до конца, используя Aspose.BarCode for Java для генерации штрих‑кода, вставки его в документ Word, извлечения изображения и, наконец, чтения данных штрих‑кода. К концу вы также увидите, как **добавить штрих‑код в Word**, **извлечь изображения из Word** и выполнить операции **распознавания штрих‑кода в Java** — всё это с несколькими строками кода.

## Быстрые ответы
- **Какая библиотека требуется?** Aspose.BarCode for Java (плюс Aspose.Words для работы с файлами .docx).  
- **Можно ли считать штрих‑код с изображения?** Да — `BarCodeReader` может декодировать изображения, извлечённые из Word.  
- **Нужна ли лицензия для продакшн?** Требуется коммерческая лицензия; доступна бесплатная пробная версия.  
- **Какая версия Java поддерживается?** Любой runtime JDK 8 +.  
- **Сколько времени занимает реализация?** Около 10‑15 минут для базового прототипа.

## Что такое распознавание штрих‑кода из документа Word?

Распознавание штрих‑кода означает сканирование изображения, находящегося внутри файла Word, и преобразование визуального шаблона обратно в исходную строку данных (например, “test‑123”). Aspose.BarCode предоставляет движок декодирования, а Aspose.Words позволяет извлечь изображение из контейнера .doc/.docx.

## Почему стоит использовать Aspose.BarCode for Java?

- **Высокая точность** более чем 60 символогий, включая Code 39, QR, DataMatrix и др.  
- **Отсутствие внешних зависимостей** — чистый Java, без нативных библиотек.  
- **Бесшовная интеграция** с Aspose.Words, что упрощает **извлечение изображений из Word** и последующее **чтение штрих‑кода с изображения**.  
- **Надёжная лицензия**, работающая на настольных, серверных и облачных платформах.

## Предварительные требования

Прежде чем перейти к коду, убедитесь, что у вас есть:

- **Java Development Kit (JDK)** — рекомендуется последняя версия.  
- **Aspose.BarCode for Java** — скачайте и установите библиотеку с официального сайта [здесь](https://releases.aspose.com/barcode/java/).  
- **IDE** — IntelliJ IDEA, Eclipse или любой другой редактор по вашему выбору.

## Импорт пакетов

В вашем Java‑проекте импортируйте необходимые классы Aspose.BarCode и Aspose.Words:

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

## Шаг 1: Генерация изображения штрих‑кода

Сначала создаём изображение штрих‑кода, которое позже вставим в файл Word.

```java
BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.CODE_39_STANDARD);
generator.setCodeText("test-123");
String strBarCodeImageSave = dataDir + "img.jpg";
generator.save(strBarCodeImageSave);
```

## Шаг 2: Добавление штрих‑кода в документ Word

Теперь вставим только что сгенерированное изображение в новый документ Word. Это демонстрирует сценарий **добавления штрих‑кода в Word**.

```java
Document doc = new Document();
DocumentBuilder docBuilder = new DocumentBuilder(doc);
docBuilder.insertImage(strBarCodeImageSave);
String strWordFile = "docout.doc";
doc.save(dataDir + strWordFile);
```

## Шаг 3: Извлечение изображений и распознавание штрих‑кода

После сохранения документа мы можем извлечь каждое изображение (включая наш штрих‑код) и выполнить **распознавание штрих‑кода в Java** для каждого из них.

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

> **Полезный совет:** Если вам нужно **читать штрих‑код с изображения**, которое находится не в документе Word, просто передайте путь к файлу в `BarCodeReader` — логика декодирования остаётся той же.

## Распространённые проблемы и решения

| Проблема | Причина | Решение |
|----------|---------|----------|
| `NullPointerException` на `shape.getImageData()` | Фигура не содержит изображение. | Добавьте проверку `shape.hasImage()` (уже показано). |
| Возвращён неверный тип штрих‑кода | Используется неправильный `DecodeType`. | Укажите тот же `EncodeTypes`, который использовался при генерации (например, `CODE_39_STANDARD`). |
| Изображение не сохраняется корректно | Отсутствуют права записи в `dataDir`. | Убедитесь, что каталог существует и доступен для записи. |
| Лицензия не применена | Режим оценки ограничивает функциональность. | Загрузите вашу лицензию Aspose при старте приложения: `License license = new License(); license.setLicense("Aspose.Total.Java.lic");` |

## Часто задаваемые вопросы

### В: Можно ли использовать Aspose.BarCode for Java в коммерческих проектах?  
О: Да, Aspose.BarCode for Java доступен для коммерческого использования. Подробности о лицензировании можно найти [здесь](https://purchase.aspose.com/buy).

### В: Есть ли бесплатная пробная версия Aspose.BarCode for Java?  
О: Да, вы можете скачать бесплатную пробную версию [здесь](https://releases.aspose.com/).

### В: Как получить поддержку по Aspose.BarCode for Java?  
О: Для получения помощи посетите форум Aspose.BarCode [здесь](https://forum.aspose.com/c/barcode/13).

### В: Доступны ли временные лицензии для Aspose.BarCode for Java?  
О: Да, временные лицензии можно получить [здесь](https://purchase.aspose.com/temporary-license/).

### В: Где найти документацию по Aspose.BarCode for Java?  
О: Обратитесь к полной документации [здесь](https://reference.aspose.com/barcode/java/).

---  

**Последнее обновление:** 2026-04-12  
**Тестировано с:** Aspose.BarCode 24.11 for Java  
**Автор:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}