---
date: 2026-08-12
description: Узнайте, как повысить читаемость штрих‑кода, настроив соотношение ширина‑узкая
  в CODE_128 на Java с помощью Aspose.BarCode, и эффективно генерировать PNG‑изображения.
  Следуйте нашему пошаговому руководству по генерации штрих‑кодов на Java.
keywords:
- improve barcode readability
- customize code128 barcode
- barcode generation tutorial java
- step by step barcode
lastmod: 2026-08-12
linktitle: Настройка соотношения ширина‑узкая
og_description: Узнайте, как повысить читаемость штрих‑кода, настроив соотношение
  ширина‑узкая в CODE_128 на Java с помощью Aspose.BarCode. Это пошаговое руководство
  показывает, как быстро генерировать PNG‑штрих‑коды.
og_image_alt: Guide to creating CODE_128 barcode with custom wide‑narrow ratio in
  Java
og_title: Повышение читаемости штрих‑кода с помощью соотношения ширина‑узкая в CODE_128
  (58 chars)
schemas:
- author: Aspose
  dateModified: '2026-08-12'
  description: Learn how to improve barcode readability by customizing the CODE_128
    wide‑narrow ratio in Java using Aspose.BarCode, and generate PNG images efficiently.
    Follow our step‑by‑step barcode generation tutorial Java.
  headline: Improve barcode readability with CODE_128 wide‑narrow ratio
  type: TechArticle
- description: Learn how to improve barcode readability by customizing the CODE_128
    wide‑narrow ratio in Java using Aspose.BarCode, and generate PNG images efficiently.
    Follow our step‑by‑step barcode generation tutorial Java.
  name: Improve barcode readability with CODE_128 wide‑narrow ratio
  steps:
  - name: set document directory
    text: Make sure the directory exists and you have write permissions; this is where
      the **saved barcode image** file will be placed.
  - name: instantiate barcode object
    text: The `BarcodeGenerator` class creates barcode images based on the specified
      symbology and encoding options. Here we **create a CODE_128 barcode** by passing
      `EncodeTypes.CODE_128` to the constructor.
  - name: set wide‑narrow ratio
    text: '`setWideNarrowRatio` sets the proportion between wide and narrow bars for
      the generated barcode. The `setWideNarrowRatio` method lets you fine‑tune the
      visual spacing. A value of `3.0f` means the wide bar is three times the width
      of a narrow bar, which falls within the optimal 2.0‑3.0 range for most'
  - name: save image to disk
    text: Calling `save` will **generate a barcode image** and store it as a PNG file,
      completing the **save barcode image** step.
  type: HowTo
- questions:
  - answer: Yes, Aspose.BarCode works seamlessly with Spring, Java EE, Android, and
      other Java environments.
    question: Can I use Aspose.BarCode with other Java frameworks?
  - answer: Change the symbology type in the `BarcodeGenerator` constructor, for example
      `EncodeTypes.QR` for QR codes.
    question: How can I generate barcodes with different symbologies?
  - answer: Yes, you can access the free trial version on the [Aspose.BarCode free
      trial page](https://releases.aspose.com/).
    question: Is there a trial version available for Aspose.BarCode?
  - answer: Refer to the documentation on the [Aspose.BarCode Java API documentation](https://reference.aspose.com/barcode/java/).
    question: Where can I find detailed documentation for Aspose.BarCode?
  - answer: Visit the Aspose.BarCode community forum at [Aspose.BarCode community
      forum](https://forum.aspose.com/c/barcode/13) for support and community discussions.
    question: How to get support for Aspose.BarCode?
  type: FAQPage
second_title: Aspose.BarCode Java API
tags:
- barcode readability
- Aspose.BarCode
- Java barcode tutorial
title: Повышение читаемости штрих‑кода с помощью соотношения ширина‑узкая в CODE_128
url: /ru/java/barcode-configuration/configuring-wide-narrow-ratio/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Повышение читаемости штрих‑кода с помощью широтно‑узкого отношения CODE_128

## Введение

Если вам нужно **повысить читаемость штрих‑кода** для этикеток инвентаря, транспортных ярлыков или любого приложения, использующего CODE_128, настройка широтно‑узкого отношения является наиболее эффективной техникой. В этом руководстве мы пошагово пройдем процесс **создания штрих‑кода** с использованием Aspose.BarCode для Java, покажем, как настроить отношение, **создавать PNG‑изображения штрих‑кода** и **сохранять изображение штрих‑кода** на диск. Вы также увидите, почему отношение важно для производительности сканера и как точно настроить его под вашу конкретную печатную среду.

## Краткие ответы
- **What is the wide‑narrow ratio?** Что такое широтно‑узкое отношение? Оно контролирует относительную ширину широких полос по сравнению с узкими полосами в штрих‑коде.  
- **Which symbology supports ratio adjustment?** Какая символьная система поддерживает настройку отношения? Большинство 1‑D символьных систем, включая CODE_128, позволяют установить пользовательское отношение.  
- **Do I need a license?** Нужна ли мне лицензия? Доступна бесплатная пробная версия, но для использования в продакшене требуется коммерческая лицензия.  
- **Can I generate a barcode image in PNG format?** Могу ли я создать изображение штрих‑кода в формате PNG? Да — используйте `generator.save(...)` для создания PNG‑изображений штрих‑кода.  
- **Is the code compatible with Java 8+?** Совместим ли код с Java 8+? Абсолютно; Aspose.BarCode работает со всеми современными версиями Java.

## Требования

Прежде чем погрузиться в код, убедитесь, что у вас есть следующее:

- Установленный Java Development Kit (JDK) на вашем компьютере.  
- Библиотека Aspose.BarCode для Java. Скачайте её по [ссылка для скачивания](https://releases.aspose.com/barcode/java/).

## Импорт пакетов

Для начала импортируйте основной класс Aspose.BarCode в ваш проект.  
`BarcodeGenerator` — это основной класс, используемый для создания изображений штрих‑кода с указанной символьной системой и параметрами.  

```java
// Import Aspose.BarCode library
import com.aspose.barcode.generation.BarcodeGenerator;
```

## Что такое широтно‑узкое отношение и почему его следует настраивать?

Широтно‑узкое отношение определяет, во сколько раз широкая полоса шире узкой полосы. Настройка этого отношения улучшает совместимость со сканерами (большинство сканеров читают лучше при отношениях от 2.0 до 3.0), компенсирует ограничения DPI принтера и позволяет подобрать визуальный стиль бренда без потери надёжности.

## Как повысить читаемость штрих‑кода, создав CODE_128 с широтно‑узким отношением в Java

Начните с добавления библиотеки Aspose.BarCode в ваш Java‑проект, затем создайте экземпляр `BarcodeGenerator`, указывая `EncodeTypes.CODE_128`. Настройте генератор с желаемым широтно‑узким отношением с помощью `setWideNarrowRatio`, при необходимости измените другие визуальные параметры и в конце вызовите `save`, чтобы записать штрих‑код в файл PNG. Этот лаконичный процесс гарантирует постоянное качество штрих‑кода и повышает уровень считывания сканерами на различных устройствах.

### Шаг 1: установить каталог документа

```java
// The path to the resource directory.
String dataDir = "Your Document Directory";
```

Убедитесь, что каталог существует и у вас есть права на запись; здесь будет размещён файл **сохранённого изображения штрих‑кода**.

### Шаг 2: создать объект штрих‑кода

Класс `BarcodeGenerator` создает изображения штрих‑кода на основе указанной символьной системы и параметров кодирования.  
```java
// Instantiate barcode object
// Create an instance of BarcodeGenerator, specify codetext and symbology in the constructor
BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.CODE_128, "12345678");
```

Здесь мы **создаём штрих‑код CODE_128**, передавая `EncodeTypes.CODE_128` в конструктор.

### Шаг 3: установить широтно‑узкое отношение

`setWideNarrowRatio` задаёт пропорцию между широкими и узкими полосами генерируемого штрих‑кода.  
```java
// Set the wide to narrow ratio for the barcode
generator.getParameters().getBarcode().setWideNarrowRatio(3.0f);
```

Метод `setWideNarrowRatio` позволяет точно настроить визуальное расстояние. Значение `3.0f` означает, что широкая полоса в три раза шире узкой, что находится в оптимальном диапазоне 2.0‑3.0 для большинства сканеров.

### Шаг 4: сохранить изображение на диск

```java
// Save the image to disk in PNG format
generator.save(dataDir + "wideNarrowRatio.png");
```

Вызов `save` **создаст изображение штрих‑кода** и сохранит его в файл PNG, завершая шаг **сохранения изображения штрих‑кода**.

## Зачем настраивать широтно‑узкое отношение?

Настройка широтно‑узкого отношения улучшает совместимость со сканерами, поскольку большинство промышленных сканеров читают лучше, когда отношение находится в диапазоне от 2.0 до 3.0. Это также повышает качество печати, компенсируя разрешения принтеров 150–300 dpi, уменьшая искажение полос. Кроме того, отношение позволяет компаниям согласовать внешний вид штрих‑кода с фирменными рекомендациями, сохраняя надёжную производительность сканирования.

## Распространённые проблемы и решения

| Проблема | Причина | Решение |
|----------|---------|---------|
| Изображение штрих‑кода искажено | Отношение слишком высоко/низко для принтера | Отрегулируйте значение, передаваемое в `setWideNarrowRatio` (например, 2.0‑2.5). |
| Файл не создан | Недействительный путь `dataDir` или недостаточные права | Проверьте путь к каталогу и убедитесь, что приложение имеет права на запись. |
| Сканер не может считать штрих‑код | Отношение выходит за пределы рекомендованного диапазона для символьной системы | Используйте стандартные отношения (2.0‑3.0) или протестируйте с целевым сканером. |

## Часто задаваемые вопросы

**Q: Can I use Aspose.BarCode with other Java frameworks?**  
A: Да, Aspose.BarCode работает без проблем со Spring, Java EE, Android и другими Java‑окружениями.

**Q: How can I generate barcodes with different symbologies?**  
A: Измените тип символьной системы в конструкторе `BarcodeGenerator`, например `EncodeTypes.QR` для QR‑кодов.

**Q: Is there a trial version available for Aspose.BarCode?**  
A: Да, вы можете получить бесплатную пробную версию на странице [страница бесплатной пробной версии Aspose.BarCode](https://releases.aspose.com/).

**Q: Where can I find detailed documentation for Aspose.BarCode?**  
A: Обратитесь к документации на странице [документация Aspose.BarCode Java API](https://reference.aspose.com/barcode/java/).

**Q: How to get support for Aspose.BarCode?**  
A: Посетите форум сообщества Aspose.BarCode по адресу [форум сообщества Aspose.BarCode](https://forum.aspose.com/c/barcode/13) для получения поддержки и обсуждения в сообществе.

---

**Последнее обновление:** 2026-08-12  
**Тестировано с:** Aspose.BarCode for Java 24.11 (latest at time of writing)  
**Автор:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Связанные руководства

- [Создание штрих‑кода Java – Установка разрешения изображения с Aspose.BarCode](/barcode/java/advanced-settings-and-optimization/setting-image-resolution-barcode/)
- [Определение ориентации штрих‑кода в Java с Aspose.BarCode](/barcode/java/advanced-settings-and-optimization/configuring-barcode-orientation/)
- [Как создать изображения штрих‑кода code128 в Java с Aspose.BarCode](/barcode/java/advanced-settings-and-optimization/saving-barcode-images-different-formats/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}