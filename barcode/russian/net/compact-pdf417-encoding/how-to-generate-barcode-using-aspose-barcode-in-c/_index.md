---
category: general
date: 2026-11-20
description: Узнайте, как генерировать штрих‑код с помощью Aspose.Barcode на C#. Это
  руководство проведёт вас через процесс создания штрих‑кода MicroPdf417 и сохранения
  его в виде PNG‑изображения.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to generate barcode
- create barcode with aspose
language: ru
lastmod: 2026-11-20
og_description: Как сгенерировать штрих‑код с помощью Aspose.Barcode в C#. Следуйте
  этому полному руководству, чтобы создать штрих‑код MicroPdf417 и экспортировать
  его в PNG.
og_image_alt: 'How to generate barcode: sample MicroPdf417 image produced by Aspose.Barcode'
og_title: Как сгенерировать штрих‑код с помощью Aspose.Barcode – пошаговое руководство
  на C#
schemas:
- author: Aspose
  dateModified: '2026-11-20'
  description: Learn how to generate barcode with Aspose.Barcode in C#. This guide
    walks you through creating a MicroPdf417 barcode and saving it as a PNG image.
  headline: How to generate barcode using Aspose.Barcode in C#
  type: TechArticle
- description: Learn how to generate barcode with Aspose.Barcode in C#. This guide
    walks you through creating a MicroPdf417 barcode and saving it as a PNG image.
  name: How to generate barcode using Aspose.Barcode in C#
  steps:
  - name: Install the Aspose.Barcode NuGet package
    text: 'Open a terminal in your project folder and run:'
  - name: Create a `BarcodeGenerator` instance for MicroPdf417
    text: '```csharp using Aspose.Barcode.Generation;'
  - name: Adjust the X‑dimension (module width)
    text: '```csharp // Step 3: Set the module width in pixels – 2 px yields a clear,
      print‑ready image generator.Parameters.Barcode.XDimension.Pixels = 2; ```'
  - name: Choose the number of columns for the PDF417 component
    text: '```csharp // Step 4: Define how many columns the PDF417 component should
      use (1‑4 allowed) generator.Parameters.Barcode.Pdf417.Columns = 4; ```'
  - name: Save the barcode image
    text: '```csharp using System.IO;'
  - name: Full source code
    text: 'Putting all steps together yields a complete, self‑contained console application:'
  - name: Generating other symbologies
    text: 'If you want to **create barcode with Aspose** for QR codes, Code128, or
      UPC, replace `EncodeTypes.MicroPdf417` with the appropriate enum value, e.g.:'
  - name: Changing image format
    text: 'Aspose.Barcode supports multiple raster formats. To export as JPEG with
      90 % quality:'
  - name: Handling large data payloads
    text: MicroPdf417 can store up to 1 KB of data. For larger payloads switch to
      full `EncodeTypes.Pdf417` and adjust `Rows` and `Columns` accordingly.
  - name: Unicode and special characters
    text: The library automatically encodes Unicode strings. However, some legacy
      scanners only recognize ASCII. If you target such devices, limit the input to
      the ASCII range or use a different symbology that guarantees compatibility.
  type: HowTo
tags:
- barcode generation
- Aspose.Barcode
- C#
- MicroPdf417
title: Как сгенерировать штрих‑код с помощью Aspose.Barcode в C#
url: /ru/net/compact-pdf417-encoding/how-to-generate-barcode-using-aspose-barcode-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Как генерировать штрих‑коды с помощью Aspose.Barcode в C#

Если вам нужно **как генерировать штрих‑коды** для настольного или веб‑приложения, Aspose.Barcode предоставляет простой API. В этом руководстве показано, как именно сгенерировать штрих‑код MicroPdf417, настроить его размеры и сохранить результат в виде PNG‑файла. Вы также увидите, как **создать штрих‑код с Aspose** для других форматов, не покидая IDE.

Генерация штрих‑кода — распространённая задача для систем учёта, платформ билетирования и защищённых документооборотных процессов. К концу этого руководства у вас будет готовая к запуску программа, создающая высококачественное изображение штрих‑кода, готовое к печати или встраиванию.

## Что понадобится

Прежде чем начать, убедитесь, что у вас есть:

* .NET 6.0 SDK или новее (код также работает с .NET Framework 4.7+)
* Visual Studio 2022 (или любой редактор C#)
* Действующая лицензия Aspose.Barcode для .NET – бесплатная пробная версия подходит для разработки и тестирования
* Базовое знакомство с синтаксисом C#

Дополнительные пакеты NuGet не требуются, кроме `Aspose.Barcode`.

## Как генерировать штрих‑код с Aspose.Barcode

Следующие разделы разбивают процесс на отдельные шаги. Каждый шаг объясняет **почему** код необходим, а не только **что** он делает.

### Шаг 1: Установить пакет Aspose.Barcode NuGet

Откройте терминал в папке проекта и выполните:

```bash
dotnet add package Aspose.Barcode
```

Эта команда добавит последнюю стабильную версию Aspose.Barcode в ваш файл проекта, обеспечивая доступность класса `BarcodeGenerator` во время компиляции.

**Почему это важно:** Пакет содержит ядро движка рендеринга и набор предопределённых `EncodeTypes`. Без него компилятор не сможет разрешить `BarcodeGenerator` или `EncodeTypes`.

### Шаг 2: Создать экземпляр `BarcodeGenerator` для MicroPdf417

```csharp
using Aspose.Barcode.Generation;

// Step 2: Initialize the generator with the desired symbology and data
BarcodeGenerator generator = new BarcodeGenerator(
    EncodeTypes.MicroPdf417,          // MicroPdf417 is a compact 2‑D barcode
    "Åspóse.Barcóde©");               // Sample text – Unicode characters are supported
```

**Почему это важно:** Конструктор связывает символьность (`EncodeTypes.MicroPdf417`) с исходными данными, которые вы хотите закодировать. MicroPdf417 идеален, когда нужен меньший размер по сравнению с полным PDF417, но при этом требуется поддержка буквенно‑цифровых данных.

### Шаг 3: Настроить X‑размер (ширину модуля)

```csharp
// Step 3: Set the module width in pixels – 2 px yields a clear, print‑ready image
generator.Parameters.Barcode.XDimension.Pixels = 2;
```

**Почему это важно:** X‑размер определяет размер каждой ячейки штрих‑кода. Слишком маленькое значение приводит к размытию изображения; слишком большое делает штрих‑код неоправданно крупным. Два пикселя — сбалансированное значение по умолчанию для большинства экранных и печатных сценариев.

### Шаг 4: Выбрать количество колонок для компонента PDF417

```csharp
// Step 4: Define how many columns the PDF417 component should use (1‑4 allowed)
generator.Parameters.Barcode.Pdf417.Columns = 4;
```

**Почему это важно:** Внутри MicroPdf417 используется компонент PDF417. Регулировка количества колонок влияет на соотношение сторон штрих‑кода и его ёмкость. Четыре колонки дают компактную форму при сохранении читаемости.

### Шаг 5: Сохранить изображение штрих‑кода

```csharp
using System.IO;

// Step 5: Export the barcode as a PNG file
string outputPath = Path.Combine(
    Environment.GetFolderPath(Environment.SpecialFolder.Desktop),
    "MicroPdf417.png");

generator.Save(outputPath, BarCodeImageFormat.Png);
```

**Почему это важно:** `Save` записывает отрендеренный штрих‑код на диск. PNG — без потерь, что сохраняет резкие края, необходимые сканерам. При необходимости можно заменить `BarCodeImageFormat.Png` на `Jpeg`, `Bmp` или `Gif`.

### Полный исходный код

Объединив все шаги, получаем полностью автономное консольное приложение:

```csharp
using System;
using System.IO;
using Aspose.Barcode.Generation;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // Initialize generator with MicroPdf417 symbology and sample data
            BarcodeGenerator generator = new BarcodeGenerator(
                EncodeTypes.MicroPdf417,
                "Åspóse.Barcóde©");

            // Configure visual appearance
            generator.Parameters.Barcode.XDimension.Pixels = 2;
            generator.Parameters.Barcode.Pdf417.Columns = 4;

            // Determine output location (Desktop for easy access)
            string outputPath = Path.Combine(
                Environment.GetFolderPath(Environment.SpecialFolder.Desktop),
                "MicroPdf417.png");

            // Save the barcode image as PNG
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"Barcode saved to: {outputPath}");
        }
    }
}
```

Запустите программу (`dotnet run`), и вы найдёте `MicroPdf417.png` на рабочем столе. Открытие файла покажет чёткий штрих‑код MicroPdf417, кодирующий текст `"Åspóse.Barcóde©"`.

## Проверка штрих‑кода

Чтобы убедиться, что штрих‑код сгенерирован корректно:

1. Откройте PNG в любом просмотрщике изображений.
2. Используйте мобильное приложение‑сканер, поддерживающее PDF417 или MicroPdf417.
3. Сканируйте изображение; приложение должно отобразить исходный текст, включая специальные символы.

Если сканирование не удалось, проверьте следующее:

* **X‑размер:** Значения ниже 1 px могут вызывать артефакты рендеринга.
* **Количество колонок:** Значения вне диапазона 1‑4 вызывают исключение.
* **Набор символов:** Aspose.Barcode поддерживает UTF‑8; убедитесь, что исходный файл сохранён в кодировке UTF‑8.

## Распространённые варианты и граничные случаи

### Генерация других символьностей

Если вы хотите **создать штрих‑код с Aspose** для QR‑кодов, Code128 или UPC, замените `EncodeTypes.MicroPdf417` на соответствующее значение перечисления, например:

```csharp
BarcodeGenerator qrGenerator = new BarcodeGenerator(EncodeTypes.QR, "https://example.com");
```

Все остальные шаги настройки (X‑размер, сохранение) остаются без изменений.

### Смена формата изображения

Aspose.Barcode поддерживает несколько растровых форматов. Чтобы экспортировать в JPEG с качеством 90 %:

```csharp
generator.Save(outputPath, BarCodeImageFormat.Jpeg, 90);
```

### Обработка больших объёмов данных

MicroPdf417 может хранить до 1 KB данных. Для более крупных полезных нагрузок переключитесь на полный `EncodeTypes.Pdf417` и соответственно настройте `Rows` и `Columns`.

### Юникод и специальные символы

Библиотека автоматически кодирует строки Unicode. Однако некоторые устаревшие сканеры распознают только ASCII. Если вы нацелены на такие устройства, ограничьте ввод диапазоном ASCII или используйте другую символьность, гарантирующую совместимость.

## Профессиональные советы для продакшн‑использования

* **Кешировать генератор** при массовой генерации штрих‑кодов с одинаковыми настройками – это снижает накладные расходы на создание объектов.
* **Установить `Resolution`** (`generator.Parameters.ImageResolution`) в 300 dpi для печати высокого качества.
* **Включить коррекцию ошибок** для 2‑D штрих‑кодов (`generator.Parameters.Barcode.Pdf417.ErrorCorrectionLevel`) для повышения надёжности сканирования повреждённых носителей.
* **Обернуть логику сохранения** в блок `try / catch` для обработки I/O‑исключений, особенно при записи на сетевые ресурсы.

## Заключение

Теперь вы знаете **как генерировать штрих‑коды** с помощью Aspose.Barcode в C#. В руководстве рассмотрены установка NuGet‑пакета, создание `BarcodeGenerator`, настройка размеров и колонок, а также сохранение результата в PNG. На этой основе вы можете **создать штрих‑код с Aspose** для любой поддерживаемой символьности, регулировать визуальные параметры и интегрировать генерацию штрих‑кодов в более крупные .NET‑решения.

Готовы исследовать дальше? Попробуйте генерировать QR‑коды для сокращения URL, встраивать штрих‑коды в PDF‑отчёты с помощью Aspose.PDF или автоматизировать пакетную генерацию штрих‑кодов для управления запасами. Каждый новый сценарий опирается на те же базовые концепции, продемонстрированные здесь. Приятного кодинга!

## Что изучать дальше?

Следующие руководства охватывают тесно связанные темы, построенные на техниках, продемонстрированных в этом руководстве. Каждый ресурс включает полностью рабочие примеры кода с пошаговыми объяснениями, помогающими освоить дополнительные возможности API и исследовать альтернативные подходы реализации в ваших проектах.

- [How to Generate PDF417 Barcode with Aspose – Complete Guide](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-with-aspose-complete-guide/)
- [How to Generate DataMatrix Barcodes Using Aspose.BarCode for .NET – Step‑by‑Step Guide](/barcode/english/net/datamatrix-barcode-configuration/)
- [How to generate barcode image with Aspose.BarCode in C#](/barcode/english/python-java/general/how-to-generate-barcode-image-with-aspose-barcode-in-c/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}