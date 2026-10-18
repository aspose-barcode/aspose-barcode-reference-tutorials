---
category: general
date: 2026-10-18
description: Узнайте, как создавать штрих‑код PDF417 в C# с помощью Aspose.BarCode.
  Этот учебник охватывает базовое, компактное, макро‑ и микроварианты PDF417 с полным
  кодом.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create pdf417 barcode
- how to create pdf417
language: ru
lastmod: 2026-10-18
og_description: Создайте штрих‑код PDF417 на C# с помощью Aspose.BarCode. Следуйте
  этому руководству, чтобы пошагово генерировать базовые, компактные, макро‑ и микроштрих‑коды
  PDF417.
og_image_alt: Screenshot showing a generated PDF417 barcode saved as an image file
og_title: Создание штрихкода PDF417 на C# – полный учебник Aspose.BarCode
schemas:
- author: Aspose
  dateModified: '2026-10-18'
  description: Learn how to create PDF417 barcode in C# with Aspose.BarCode. This
    tutorial covers basic, compact, macro and micro PDF417 generation with full code.
  headline: Create PDF417 barcode in C# using Aspose.BarCode – step‑by‑step guide
  type: TechArticle
tags:
- barcode
- pdf417
- csharp
- aspose
title: Создание штрих‑кода PDF417 в C# с использованием Aspose.BarCode — пошаговое
  руководство
url: /ru/net/compact-pdf417-encoding/create-pdf417-barcode-in-c-using-aspose-barcode-step-by-step/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Создание штрих‑кода PDF417 в C# с помощью Aspose.BarCode – пошаговое руководство

Если вам нужно **создать штрих‑код PDF417** в приложении .NET, это руководство проведёт вас через весь процесс. Вы увидите, как сгенерировать базовый штрих‑код, включить компактный режим, добавить макро‑метаданные и создать микровариант — всё с понятными объяснениями и исполняемым кодом.

Генерация штрих‑кодов PDF417 широко используется в логистике, билетных системах и управлении документами. К концу этого руководства вы сможете интегрировать создание штрих‑кода в любой проект C# без внешних инструментов.

## Prerequisites

Before you start, make sure you have:

* .NET 6.0 или новее (код также работает с .NET Framework 4.7+)
* Visual Studio 2022 или любой C# IDE
* **Aspose.BarCode for .NET** NuGet пакет  
  ```bash
  dotnet add package Aspose.BarCode
  ```
* Разрешение на запись в папку, где будут сохраняться сгенерированные PNG‑файлы

Дополнительная конфигурация не требуется; библиотека обрабатывает все детали низкоуровневого кодирования.

## Шаг 1: Создание базового штрих‑кода PDF417

The first step establishes a regular PDF417 barcode with custom size and column count.

```csharp
using Aspose.BarCode.Generation;

// Initialize the generator for a standard PDF417 barcode
BarcodeGenerator basicGen = new BarcodeGenerator(EncodeTypes.Pdf417, "Åspóse.Barcóde©");

// Adjust the X‑dimension (module width) to 2 pixels for higher resolution
basicGen.Parameters.Barcode.XDimension.Pixels = 2;

// Set the number of columns – three columns keep the barcode compact yet readable
basicGen.Parameters.Barcode.Pdf417.Columns = 3;

// Save the barcode as a PNG image
basicGen.Save(@"YOUR_DIRECTORY\Pdf417Basic.png", BarCodeImageFormat.Png);
```

**Почему эти настройки важны**

* `XDimension.Pixels` контролирует физический размер каждого элемента штрих‑кода. Значение 2 даёт чёткое изображение на большинстве экранов и принтеров.
* `Pdf417.Columns` определяет количество столбцов данных в штрих‑коде. Меньшее количество столбцов уменьшает ширину; большее — увеличивает ёмкость данных.

Запуск кода создаёт `Pdf417Basic.png`, который выглядит как типичный символ PDF417 с тремя столбцами данных и полным столбцом метаданных справа.

## Шаг 2: Включение компактного (усечённого) режима

Compact mode removes the right‑hand metadata column, making the barcode narrower. This is useful when space is limited but the data can be reconstructed from the remaining rows.

```csharp
// Turn on truncated mode to omit the metadata column
basicGen.Parameters.Barcode.Pdf417.Truncate = true;

// Save the compact version
basicGen.Save(@"YOUR_DIRECTORY\CompactPdf417.png", BarCodeImageFormat.Png);
```

**Почему усекать?**  
When `Truncate` is `true`, the generator omits the optional right‑hand column that stores error‑correction and file‑level metadata. The resulting barcode occupies fewer columns while still being scannable by most PDF417 readers.

## Шаг 3: Создание Macro PDF417 штрих‑кода с метаданными уровня файла

Macro PDF417 extends the standard format with segment identifiers, allowing a large document to be split into multiple barcodes. This is handy for encoding long strings or multi‑page files.

```csharp
// Initialize a generator for Macro PDF417
BarcodeGenerator macroGen = new BarcodeGenerator(EncodeTypes.MacroPdf417, "sample text");

// Set column count for better readability
macroGen.Parameters.Barcode.Pdf417.Columns = 5;

// Assign macro-specific identifiers
macroGen.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;   // Unique file identifier
macroGen.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 1;      // Current segment number
macroGen.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 10; // Total segments

// Save the macro barcode
macroGen.Save(@"YOUR_DIRECTORY\MacroPdf417.png", BarCodeImageFormat.Png);
```

**Объяснение полей Macro**

| Свойство | Назначение |
|----------|------------|
| `MacroPdf417FileID` | Уникальный идентификатор всего файла; все сегменты используют это значение. |
| `MacroPdf417SegmentID` | Индекс текущего сегмента (начинается с 1). |
| `MacroPdf417SegmentsCount` | Общее количество сегментов, составляющих полный набор данных. |

Сканер, понимающий Macro PDF417, может восстановить исходные данные, прочитав все сегменты и используя эти идентификаторы.

## Шаг 4: Создание Micro PDF417 штрих‑кода для коротких данных

Micro PDF417 is a compact version designed for small payloads (up to 90 characters). It limits the column range to 1‑4, making the barcode suitable for tiny labels or devices with limited display area.

```csharp
// Initialize a generator for Micro PDF417
BarcodeGenerator microGen = new BarcodeGenerator(EncodeTypes.MicroPdf417, "small data");

// Set a fine X‑dimension for crisp rendering
microGen.Parameters.Barcode.XDimension.Pixels = 2;

// Choose a column count within the allowed range (1‑4)
microGen.Parameters.Barcode.Pdf417.Columns = 4;

// Save the micro barcode
microGen.Save(@"YOUR_DIRECTORY\MicroPdf417.png", BarCodeImageFormat.Png);
```

**Когда использовать Micro PDF417**  
Use this variant when the data payload is short and you need the smallest possible barcode. It is ideal for inventory tags, access cards, or any scenario where screen real estate is at a premium.

## Полный рабочий пример

Below is a self‑contained console application that generates all four barcode types in one run. Copy the code into a new C# project, replace `YOUR_DIRECTORY` with an existing folder path, and run it.

```csharp
using System;
using Aspose.BarCode.Generation;

namespace Pdf417Demo
{
    class Program
    {
        static void Main()
        {
            // Adjust this path to a writable folder on your machine
            string outputPath = @"C:\Barcodes";

            // ---------- Basic PDF417 ----------
            var basicGen = new BarcodeGenerator(EncodeTypes.Pdf417, "Åspóse.Barcóde©");
            basicGen.Parameters.Barcode.XDimension.Pixels = 2;
            basicGen.Parameters.Barcode.Pdf417.Columns = 3;
            basicGen.Save($"{outputPath}\\Pdf417Basic.png", BarCodeImageFormat.Png);

            // ---------- Compact PDF417 ----------
            basicGen.Parameters.Barcode.Pdf417.Truncate = true;
            basicGen.Save($"{outputPath}\\CompactPdf417.png", BarCodeImageFormat.Png);

            // ---------- Macro PDF417 ----------
            var macroGen = new BarcodeGenerator(EncodeTypes.MacroPdf417, "sample text");
            macroGen.Parameters.Barcode.Pdf417.Columns = 5;
            macroGen.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
            macroGen.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 1;
            macroGen.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 10;
            macroGen.Save($"{outputPath}\\MacroPdf417.png", BarCodeImageFormat.Png);

            // ---------- Micro PDF417 ----------
            var microGen = new BarcodeGenerator(EncodeTypes.MicroPdf417, "small data");
            microGen.Parameters.Barcode.XDimension.Pixels = 2;
            microGen.Parameters.Barcode.Pdf417.Columns = 4; // valid range: 1‑4
            microGen.Save($"{outputPath}\\MicroPdf417.png", BarCodeImageFormat.Png);

            Console.WriteLine("All PDF417 barcodes have been generated successfully.");
        }
    }
}
```

**Ожидаемый результат**

Running the program creates four PNG files in the specified folder:

* `Pdf417Basic.png` – стандартный штрих‑код с тремя столбцами
* `CompactPdf417.png` – те же данные, усечённый правый столбец
* `MacroPdf417.png` – макро‑штрих‑код, содержащий метаданные сегмента
* `MicroPdf417.png` – компактный микрошрих‑код для коротких строк

Откройте любое изображение в просмотрщике; вы увидите характерные шаблоны PDF417. Сканирование их мобильным сканером штрих‑кодов (например, ZXing, Scandit) возвращает исходные текстовые строки.

## Часто задаваемые вопросы и советы

* **Что делать, если штрих‑код выглядит размытым?**  
  Увеличьте `XDimension.Pixels` до 3 или 4. Большие размеры модулей дают изображение более высокого разрешения, но увеличивают размер файла.

* **Можно ли вывести SVG вместо PNG?**  
  Да. Замените `BarCodeImageFormat.Png` на `BarCodeImageFormat.Svg` в вызовах `Save`.

* **Нужно ли вручную задавать уровень коррекции ошибок?**  
  Aspose.BarCode автоматически выбирает оптимальный уровень. Для специализированных случаев вы можете изменить `Pdf417.ErrorCorrectionLevel`.

* **Как встроить штрих‑код в PDF‑документ?**  
  Используйте `Aspose.Pdf`, чтобы добавить сгенерированный PNG или SVG как элемент изображения на страницу PDF.

* **Является ли библиотека потокобезопасной?**  
  Каждый экземпляр `BarcodeGenerator` независим; вы можете создавать генераторы в нескольких потоках без общего состояния.

## Заключение

Теперь вы знаете, как **создать штрих‑код PDF417** в C# с помощью Aspose.BarCode, охватывая базовый, компактный, макро и микровариант.

## Что изучать дальше?

The following tutorials cover closely related topics that build on the techniques demonstrated in this guide. Each resource includes complete working code examples with step-by-step explanations to help you master additional API features and explore alternative implementation approaches in your own projects.

- [Как создать штрих‑код pdf417 в C# – пошаговое руководство](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-in-c-step-by-step-guide/)
- [Как создать PDF417 штрих‑код в C# с компактным режимом](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-in-c-with-compact-mode/)
- [Как создать macro PDF417 штрих‑код в C# с использованием Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/how-to-create-macro-pdf417-barcode-in-c-using-aspose-barcode/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}