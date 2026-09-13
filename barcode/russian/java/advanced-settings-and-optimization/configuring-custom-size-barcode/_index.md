---
date: 2026-09-13
description: Узнайте, как задать пользовательский размер barcode в Java и генерировать
  изображения barcode с помощью Aspose.BarCode for Java за несколько простых шагов.
keywords:
- custom barcode size java
- barcode size for printing
- custom barcode for labels
- how to set barcode size
lastmod: 2026-09-13
linktitle: Настройка пользовательского размера для barcode
og_description: Узнайте, как задать пользовательский размер barcode в Java с помощью
  Aspose.BarCode for Java. Это руководство показывает пошаговый код для управления
  размерами barcode при печати и интеграции в пользовательский интерфейс.
og_image_alt: Guide showing Java code to configure exact barcode dimensions with Aspose.BarCode
og_title: Как установить пользовательский размер barcode в Java с Aspose.BarCode
schemas:
- author: Aspose
  dateModified: '2026-09-13'
  description: Learn how to set custom barcode size java and generate barcode images
    using Aspose.BarCode for Java in a few simple steps.
  headline: How to set custom barcode size java with Aspose.BarCode
  type: TechArticle
- questions:
  - answer: Yes, Aspose.BarCode for Java supports a wide range of symbologies. Replace
      `EncodeTypes.CODE_39_STANDARD` with the desired type, such as `EncodeTypes.QR`
      or `EncodeTypes.DATA_MATRIX`.
    question: Can I customize the symbology type for my barcode?
  - answer: Yes, you can explore the capabilities of Aspose.BarCode by obtaining a
      free trial **[from the Aspose releases page](https://releases.aspose.com/)**.
    question: Is there a trial version available?
  - answer: Refer to the comprehensive documentation **[Aspose.BarCode Java reference](https://reference.aspose.com/barcode/java/)**
      for in‑depth information on Aspose.BarCode for Java.
    question: Where can I find detailed documentation?
  - answer: Visit the Aspose.BarCode forum **[Aspose.BarCode community forum](https://forum.aspose.com/c/barcode/13)**
      to seek assistance and connect with the community.
    question: How can I get support for any issues or queries?
  - answer: Yes, you can acquire a temporary license **[on the temporary license page](https://purchase.aspose.com/temporary-license/)**
      for testing purposes.
    question: Is there a temporary license option available?
  type: FAQPage
second_title: Aspose.BarCode Java API
tags:
- custom barcode size
- Aspose.BarCode
- Java barcode
- barcode for printing
- custom barcode for labels
title: Как установить пользовательский размер barcode в Java с Aspose.BarCode
url: /ru/java/advanced-settings-and-optimization/configuring-custom-size-barcode/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Как установить пользовательский размер штрихкода java с Aspose.BarCode

## Введение

Если вы разработчик Java и вам нужен **custom barcode size java**, Aspose.BarCode for Java делает это простым. В этом руководстве вы узнаете, как сгенерировать изображение штрихкода в Java с точной шириной и высотой, которые вам требуются, получив полный контроль над макетом, печатью и интеграцией в пользовательский интерфейс.

## Быстрые ответы
- **Какая библиотека мне нужна?** Aspose.BarCode for Java (доступна бесплатная пробная версия).  
- **Могу ли я задать точную ширину и высоту?** Да — используйте свойства `ImageWidth` и `ImageHeight` в миллиметрах.  
- **Нужна ли лицензия для разработки?** Временная или пробная лицензия подходит для тестирования; полная лицензия требуется для продакшна.  
- **Какие символьные наборы штрихкодов поддерживают пользовательский размер?** Большинство 1‑D и 2‑D символьных наборов, включая Code 39, QR и DataMatrix.  
- **Сколько времени занимает реализация?** Обычно менее 10 минут для базового штрихкода с пользовательским размером.

## Что такое custom barcode size java?

Custom barcode size java позволяет задавать физические размеры генерируемого изображения вместо использования алгоритма автоматического масштабирования библиотеки. Это важно, когда точный размер в миллиметрах имеет значение для этикеток, чеков или встроенных PDF, поскольку гарантирует, что напечатанный штрихкод соответствует дизайнерским спецификациям и остаётся считываемым на разных устройствах.

## Почему стоит настраивать пользовательские размеры штрихкода?

Настройка пользовательских размеров штрихкода обеспечивает печать штрихкода требуемого размера для сканеров, идеальное выравнивание с элементами UI, уменьшает ненужный размер файла и помогает соблюдать отраслевые регуляции по размерам. Точный контроль также предотвращает сдвиги макета в адаптивных дизайнах и избавляет от дорогой пере‑печати из‑за несоответствия размеров.

## Предварительные требования

Перед тем как приступить к коду, убедитесь, что у вас есть:

- Базовые знания программирования на Java.  
- Среда разработки Java (IDE, JDK 8+).  
- Библиотека Aspose.BarCode for Java установлена – скачайте её **[со страницы загрузки Aspose.BarCode Java](https://releases.aspose.com/barcode/java/)**.  

## Импорт пространств имён

Пакет `com.aspose.barcode` предоставляет все необходимые классы для работы со штрихкодами. Импортируйте следующие классы в начале вашего Java‑файла:

```java
import com.aspose.barcode.generation.AutoSizeMode;
import com.aspose.barcode.generation.BarcodeGenerator;
```

## Шаг 1: задать путь к каталогу ресурсов

Определите, куда будет сохраняться сгенерированное изображение штрихкода. Использование отдельной папки `dataDir` упрощает организацию проекта и предотвращает `FileNotFoundException`.

```java
// The path to the resource directory.
String dataDir = "Your Document Directory";
```

> **Pro tip:** Используйте абсолютный путь или путь, относительный к папке `resources` вашего проекта, чтобы избежать `FileNotFoundException`.

## Шаг 2: создать объект штрихкода

Класс `BarcodeGenerator` создаёт и настраивает изображения штрихкодов. Создайте экземпляр `BarcodeGenerator`, укажите символьный набор (например, Code 39) и данные для кодирования:

```java
// Instantiate barcode object, Set the Code text for the barcode and the
// symbology type to Code39Standard
BarcodeGenerator generator = new BarcodeGenerator(com.aspose.barcode.EncodeTypes.CODE_39_STANDARD,
        "1234567890");
```

Вы можете заменить `EncodeTypes.CODE_39_STANDARD` на любой другой поддерживаемый символьный набор, например `EncodeTypes.QR` или `EncodeTypes.DATA_MATRIX`.

## Шаг 3: отключить автоматический размер

Выключите автоматическое масштабирование, чтобы применить свои собственные размеры:

```java
// Set auto size false
generator.getParameters().setAutoSizeMode(AutoSizeMode.NEAREST);
```

Режим `NEAREST` отключает авто‑размер, но сохраняет читаемость штрихкода.

## Шаг 4: задать высоту

Укажите желаемую высоту в миллиметрах. Здесь мы задаём **50 mm**:

```java
// Set height
generator.getParameters().getImageHeight().setMillimeters(50);
```

## Шаг 5: задать ширину

Определите ширину в миллиметрах – в этом примере **120 mm**:

```java
// Set width
generator.getParameters().getImageWidth().setMillimeters(120);
```

> **Почему миллиметры?** Использование физических единиц гарантирует, что штрихкод будет напечатан точно нужного размера независимо от DPI экрана.

## Шаг 6: сохранить изображение

Наконец, сгенерируйте и сохраните изображение штрихкода в ранее определённый каталог:

```java
// Save the image
generator.save(dataDir + "barcode-custom-size.jpg");
```

Метод `save` автоматически создаёт высококачественный JPEG (можно также выбрать PNG, BMP и т.д.).

### Что происходит «под капотом»?

Когда вы вызываете `save`, Aspose.BarCode рендерит штрихкод на основе заданных размеров, кодирует данные и записывает файл изображения. Поскольку авто‑размер отключён, библиотека использует точно указанные ширину и высоту, создавая штрихкод, идеально вписывающийся в ваш макет.

## Распространённые проблемы и решения

| Проблема | Причина | Решение |
|----------|----------|----------|
| Штрихкод выглядит растянутым | Несоответствие соотношения ширины/высоты выбранному символьному набору | Сохраняйте рекомендованное соотношение сторон для выбранного символьного набора (см. документацию Aspose). |
| Сканер не считывает штрихкод | Размеры слишком малы | Убедитесь, что соблюдены минимальные размеры согласно спецификации штрихкода (например, высота 15 mm для Code 39). |
| Изображение не сохраняется | Неправильный путь `dataDir` | Вызовите `new File(dataDir).mkdirs();` перед сохранением или укажите абсолютный путь. |

## Часто задаваемые вопросы

**В: Можно ли изменить тип символьного набора для моего штрихкода?**  
О: Да, Aspose.BarCode for Java поддерживает широкий спектр символьных наборов. Замените `EncodeTypes.CODE_39_STANDARD` на нужный тип, например `EncodeTypes.QR` или `EncodeTypes.DATA_MATRIX`.

**В: Есть ли пробная версия?**  
О: Да, вы можете ознакомиться с возможностями Aspose.BarCode, получив бесплатную пробную версию **[со страницы релизов Aspose](https://releases.aspose.com/)**.

**В: Где найти подробную документацию?**  
О: Обратитесь к полной документации **[Aspose.BarCode Java reference](https://reference.aspose.com/barcode/java/)** для получения детальной информации о Aspose.BarCode for Java.

**В: Как получить поддержку по возникающим вопросам?**  
О: Посетите форум Aspose.BarCode **[Aspose.BarCode community forum](https://forum.aspose.com/c/barcode/13)**, чтобы задать вопросы и пообщаться с сообществом.

**В: Есть ли вариант временной лицензии?**  
О: Да, вы можете оформить временную лицензию **[на странице временных лицензий](https://purchase.aspose.com/temporary-license/)** для тестовых целей.

**В: Можно ли генерировать изображение штрихкода java в формате PNG вместо JPEG?**  
О: Конечно. Используйте `generator.save(dataDir + "barcode.png", com.aspose.barcode.BarCodeImageFormat.PNG);` для вывода PNG.

**В: Что делать, если позже нужно встроить штрихкод в PDF?**  
О: После генерации изображения вы можете загрузить его в любую PDF‑библиотеку (например, Aspose.PDF) и разместить на странице с помощью API вставки изображений этой библиотеки.

## Заключение

Следуя этим семи простым шагам, вы сможете контролировать точную ширину и высоту любого штрихкода, созданного с помощью Aspose.BarCode for Java. Такой уровень точности помогает соответствовать стандартам печати, поддерживать аккуратный UI‑макет и соблюдать отраслевые регуляции — без потери надёжности считывания.

---

**Последнее обновление:** 2026-09-13  
**Тестировано с:** Aspose.BarCode for Java 24.11  
**Автор:** Aspose

## Связанные руководства

- [Create Barcode with Aspose - Set X & Y Dimensions in Java](/barcode/java/barcode-configuration/managing-x-y-dimension-barcode/)
- [How to Generate Barcode in Java: Creating and Setting Size for Whole Picture](/barcode/java/barcode-basics/creating-setting-size-whole-picture-barcode/)
- [How to create small barcode labels in Java with Aspose.BarCode](/barcode/java/advanced-settings-and-optimization/getting-minimum-barcode-size/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}