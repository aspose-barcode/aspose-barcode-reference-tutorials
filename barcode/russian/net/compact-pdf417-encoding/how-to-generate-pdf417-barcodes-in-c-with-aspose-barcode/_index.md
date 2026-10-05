---
category: general
date: 2026-09-10
description: Как генерировать штрихкоды PDF417 в C# с помощью Aspose.BarCode. Следуйте
  пошаговому руководству, чтобы создать Macro PDF417, настроить параметры и экспортировать
  в PNG.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to generate pdf417
- macro pdf417 barcode
- aspose.barcode for .net
- c# barcode generator
- pdf417 barcode parameters
- barcode image export
language: ru
lastmod: 2026-09-10
og_description: Как генерировать штрихкоды PDF417 в C# с помощью Aspose.BarCode. Узнайте
  полный процесс от настройки до сохранения изображения Macro PDF417 в формате PNG.
og_image_alt: Screenshot of a generated Macro PDF417 barcode saved as a PNG file
og_title: Как генерировать штрихкоды PDF417 в C# – полное руководство Aspose.BarCode
schemas:
- author: Aspose
  dateModified: '2026-09-10'
  description: How to generate PDF417 barcodes in C# using Aspose.BarCode. Follow
    a step‑by‑step guide to create Macro PDF417, adjust parameters, and export as
    PNG.
  headline: How to generate PDF417 barcodes in C# with Aspose.BarCode
  type: TechArticle
- description: How to generate PDF417 barcodes in C# using Aspose.BarCode. Follow
    a step‑by‑step guide to create Macro PDF417, adjust parameters, and export as
    PNG.
  name: How to generate PDF417 barcodes in C# with Aspose.BarCode
  steps:
  - name: '**Create a Macro PDF417 generator** – `EncodeTypes.MacroPdf417` tells Aspose.BarCode
      to use the macro version of PDF417, which supports splitting a large payload
      across multiple symbols.'
    text: '**Create a Macro PDF417 generator** – `EncodeTypes.MacroPdf417` tells Aspose.BarCode
      to use the macro version of PDF417, which supports splitting a large payload
      across multiple symbols.'
  - name: '**Adjust basic appearance** – `XDimension` controls the module (dot) width;
      `Columns` defines how many columns each symbol will contain, influencing both
      size and readability.'
    text: '**Adjust basic appearance** – `XDimension` controls the module (dot) width;
      `Columns` defines how many columns each symbol will contain, influencing both
      size and readability.'
  - name: '**Set macro‑specific fields** – These properties (`MacroPdf417FileID`,
      `MacroPdf417SegmentID`, etc.) are required by the PDF417 macro specification
      to re‑assemble the original data on the scanner side.'
    text: '**Set macro‑specific fields** – These properties (`MacroPdf417FileID`,
      `MacroPdf417SegmentID`, etc.) are required by the PDF417 macro specification
      to re‑assemble the original data on the scanner side.'
  - name: '**Export the image** – `BarCodeImageFormat.Png` provides a lossless image
      that works well for web, print, and mobile scenarios.'
    text: '**Export the image** – `BarCodeImageFormat.Png` provides a lossless image
      that works well for web, print, and mobile scenarios.'
  - name: '**Visual verification** – Open `MacroPdf417.png` in any image viewer. You
      should see a stacked set of vertical bars with a small text caption (the encoded
      data).'
    text: '**Visual verification** – Open `MacroPdf417.png` in any image viewer. You
      should see a stacked set of vertical bars with a small text caption (the encoded
      data).'
  - name: '**Scanner test** – Use a mobile barcode scanner app that supports PDF417.
      Scan the image; the app should return the original “Sample text” plus macro
      metadata (file ID, segment ID, etc.).'
    text: '**Scanner test** – Use a mobile barcode scanner app that supports PDF417.
      Scan the image; the app should return the original “Sample text” plus macro
      metadata (file ID, segment ID, etc.).'
  - name: '**Error handling** – If the scanner reports “checksum error,” double‑check
      `MacroPdf417Checksum` and ensure the `MacroPdf417Terminator` is set correctly
      on the last segment.'
    text: '**Error handling** – If the scanner reports “checksum error,” double‑check
      `MacroPdf417Checksum` and ensure the `MacroPdf417Terminator` is set correctly
      on the last segment.'
  - name: '**Performance** – Generating many segments in a loop can be CPU‑intensive.
      Re‑use a single `BarcodeGenerator` instance and only update the macro fields
      between saves to improve throughput.'
    text: '**Performance** – Generating many segments in a loop can be CPU‑intensive.
      Re‑use a single `BarcodeGenerator` instance and only update the macro fields
      between saves to improve throughput.'
  type: HowTo
tags:
- barcode
- pdf417
- csharp
- aspose
title: Как генерировать штрихкоды PDF417 в C# с помощью Aspose.BarCode
url: /ru/net/compact-pdf417-encoding/how-to-generate-pdf417-barcodes-in-c-with-aspose-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Как генерировать штрихкоды PDF417 в C# с помощью Aspose.BarCode

Если вам нужно **как генерировать pdf417** в проекте .NET, этот учебник показывает полный рабочий процесс. Вы увидите, как создать штрихкод **Macro PDF417**, точно настроить его параметры и экспортировать результат в виде PNG‑изображения — всё с помощью Aspose.BarCode для .NET.

Генерация штрихкодов PDF417 широко используется в логистике, билетных системах и рабочих процессах с защищёнными документами. К концу этого руководства у вас будет готовый к использованию генератор штрихкодов C#, который можно внедрить в любое приложение.

## Что вам понадобится

- **Visual Studio 2022** (или любой IDE для C#)  
- **.NET 6.0** или новее  
- **Aspose.BarCode for .NET** пакет NuGet (`Install-Package Aspose.BarCode`)  
- Базовое знакомство с синтаксисом C#  

> **Pro tip:** Используйте последнюю версию Aspose.BarCode, чтобы получить новейшие функции Macro PDF417 и исправления ошибок.

---

## Как генерировать штрихкоды PDF417 в C#  

Ниже приведён полностью исполняемый пример, который создаёт штрихкод **Macro PDF417**, настраивает его макрос‑специфические поля и сохраняет изображение.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // STEP 1 – create a Macro PDF417 generator with the desired text
        using (BarcodeGenerator generator =
               new BarcodeGenerator(EncodeTypes.MacroPdf417, "Sample text"))
        {
            // STEP 2 – adjust basic barcode appearance
            generator.Parameters.Barcode.XDimension.Pixels = 2;   // module width
            generator.Parameters.Barcode.Pdf417.Columns = 5;     // number of columns

            // STEP 3 – configure Macro PDF417 specific fields
            generator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
            generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;
            generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;
            generator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";
            generator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234; // CCITT‑16
            generator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000;
            generator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp =
                new DateTime(2023, 11, 1);
            generator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
            generator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
            generator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;

            // STEP 4 – save the generated barcode as a PNG image
            generator.Save("MacroPdf417.png", BarCodeImageFormat.Png);
        }

        Console.WriteLine("Macro PDF417 barcode generated: MacroPdf417.png");
    }
}
```

### Почему каждый шаг важен

1. **Create a Macro PDF417 generator** – `EncodeTypes.MacroPdf417` сообщает Aspose.BarCode использовать макроверсию PDF417, которая поддерживает разделение большого объёма данных на несколько символов.  
2. **Adjust basic appearance** – `XDimension` управляет шириной модуля (точки); `Columns` определяет количество столбцов в каждом символе, влияя как на размер, так и на читаемость.  
3. **Set macro‑specific fields** – Эти свойства (`MacroPdf417FileID`, `MacroPdf417SegmentID` и др.) требуются спецификацией Macro PDF417 для восстановления исходных данных на стороне сканера.  
4. **Export the image** – `BarCodeImageFormat.Png` обеспечивает безпотерьное изображение, которое хорошо подходит для веба, печати и мобильных сценариев.  

---

## Настройка Aspose.BarCode для .NET (генератор штрихкодов C#)

Прежде чем запустить приведённый выше код, необходимо добавить библиотеку Aspose.BarCode в ваш проект:

```bash
dotnet add package Aspose.BarCode
```

*Пакет NuGet включает все зависимости, поэтому дополнительные DLL не требуются.*  
Если вы нацелены на .NET Framework, та же команда `Install-Package Aspose.BarCode` работает из консоли диспетчера пакетов.

### Распространённые подводные камни

- **Missing license** – По умолчанию Aspose работает в режиме оценки, добавляя водяной знак к штрихкоду. Зарегистрируйте файл лицензии (`License license = new License(); license.SetLicense("Aspose.BarCode.lic");`), чтобы убрать его.  
- **Incorrect `EncodeTypes`** – Использование `EncodeTypes.Pdf417` вместо `EncodeTypes.MacroPdf417` игнорирует все макрос‑поля, нарушая реконструкцию многосегментных данных.  

---

## Настройка параметров штрихкода Macro PDF417

Макрос‑поля позволяют разбить большой документ на несколько символов PDF417. Ниже быстрый справочник:

| Свойство | Назначение | Типичный диапазон |
|----------|------------|-------------------|
| `MacroPdf417FileID` | Уникальный идентификатор полного файла | 0‑2³¹‑1 |
| `MacroPdf417SegmentID` | Индекс текущего сегмента (начинается с 0) | 0‑254 |
| `MacroPdf417SegmentsCount` | Общее количество сегментов в файле | 1‑255 |
| `MacroPdf417FileName` | Необязательное читаемое имя | 0‑255 символов |
| `MacroPdf417Checksum` | Контрольная сумма CCITT‑16 для обнаружения ошибок | 0‑65535 |
| `MacroPdf417FileSize` | Исходный размер файла в байтах | 0‑2³¹‑1 |
| `MacroPdf417TimeStamp` | Метка времени создания (необязательно) | `DateTime` значение |
| `MacroPdf417Addressee` / `MacroPdf417Sender` | Необязательные метаданные для маршрутизации | Любая строка |
| `MacroPdf417Terminator` | Указывает последний сегмент (`Set` или `Unset`) | `Pdf417MacroTerminator` enum |

Настройте эти значения в соответствии с кодируемыми данными. Например, если вы разбиваете файл размером 2 МБ на 20 сегментов, задайте `MacroPdf417FileSize` = `2_000_000` и `MacroPdf417SegmentsCount` = `20`.

---

## Экспорт штрихкода в виде PNG‑изображения (экспорт изображения штрихкода)

Сохранение штрихкода в PNG — самый распространённый формат экспорта, поскольку он сохраняет резкие края и поддерживает прозрачность. Aspose.BarCode также поддерживает JPEG, BMP, GIF и TIFF — выбирайте тот, который подходит вашему последующему процессу.

```csharp
generator.Save("MacroPdf417.png", BarCodeImageFormat.Png);
```

**Советы для получения изображения высокого качества**

- Увеличьте `XDimension.Pixels` для более крупных модулей при печати на высокоразрешающих носителях.  
- Используйте `BarCodeImageFormat.Tiff` с компрессией CCITT Group 4 для PDF‑файлов, совместимых с факсом.  
- Установите `generator.Parameters.ImageOptions.Resolution`, если требуется конкретное DPI (например, 300 dpi для печати).  

---

## Тестирование и устранение неполадок вашего штрихкода PDF417

1. **Visual verification** – Откройте `MacroPdf417.png` в любом просмотрщике изображений. Вы должны увидеть набор вертикальных полос с небольшим текстовым подписью (закодированные данные).  
2. **Scanner test** – Используйте мобильное приложение‑сканер, поддерживающее PDF417. Сканируйте изображение; приложение должно вернуть исходный «Sample text» плюс макрос‑метаданные (file ID, segment ID и т.д.).  
3. **Error handling** – Если сканер сообщает «checksum error», дважды проверьте `MacroPdf417Checksum` и убедитесь, что `MacroPdf417Terminator` правильно установлен в последнем сегменте.  
4. **Performance** – Генерация большого количества сегментов в цикле может быть ресурсоёмкой. Переиспользуйте один экземпляр `BarcodeGenerator` и обновляйте только макрос‑поля между сохранениями, чтобы повысить пропускную способность.  

---

## Заключение

Теперь вы знаете **как генерировать PDF417** штрихкоды в C# с помощью Aspose.BarCode, от установки библиотеки до настройки полей Macro PDF417 и экспорта чистого PNG‑изображения. Полное решение демонстрирует:

- Настройку **генератора штрихкодов C#** с типом Macro PDF417  
- Кастомизацию **параметров штрихкода PDF417** для многосегментных данных  
- Выполнение **экспорта изображения штрихкода** для дальнейшего использования  

Отсюда вы можете изучать продвинутые темы, такие как внедрение штрихкода в PDF‑документы, создание сопутствующих QR‑кодов или автоматизацию пакетной обработки больших файлов.

**Следующие шаги**

- Попробуйте разные значения `BarCodeImageFormat` (например, `Tiff` для печати высокого разрешения).  
- Скомбинируйте Macro PDF417 с другими символогиями в том же документе, используя `generator.Parameters.Barcode.Symbology`.  
- Ознакомьтесь с [Aspose.BarCode documentation](https://docs.aspose.com/barcode/net/) для более глубокой настройки, такой как уровень коррекции ошибок и режимы кодирования.  

Счастливого кодинга!

## Что вам следует изучить дальше?

Следующие учебники охватывают тесно связанные темы, которые развивают техники, продемонстрированные в этом руководстве. Каждый ресурс включает полностью работающие примеры кода с пошаговыми объяснениями, помогающими освоить дополнительные возможности API и исследовать альтернативные подходы в ваших проектах.

- [Создать штрихкод с текстом – Полное руководство по PDF417 Macro](/barcode/english/net/compact-pdf417-encoding/generate-barcode-with-text-full-pdf417-macro-guide/)
- [регулировка размера штрихкода – Руководство C# по генерации штрихкодов PDF417](/barcode/english/net/compact-pdf417-encoding/adjust-barcode-size-c-guide-to-generate-pdf417-barcodes/)
- [Как сгенерировать штрихкод PDF417 – Полное программное руководство](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-complete-programming-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}