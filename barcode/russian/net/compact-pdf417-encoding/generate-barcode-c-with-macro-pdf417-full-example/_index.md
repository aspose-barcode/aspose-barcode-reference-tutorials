---
category: general
date: 2026-08-19
description: Генерировать штрих‑код на C# с помощью Aspose.BarCode, создавая Macro
  PDF417 с пользовательским текстом и сохраняя его в виде файла изображения.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate barcode C#
- how to generate pdf417
- create barcode custom text
- generate barcode image file
language: ru
lastmod: 2026-08-19
og_description: Создавайте штрихкоды на C# с помощью Aspose.BarCode, изучайте, как
  генерировать PDF417, добавляйте пользовательский текст и сохраняйте изображение
  штрихкода.
og_image_alt: Screenshot of a Macro PDF417 barcode generated with C#
og_title: Создание штрихкода C# – руководство по Macro PDF417
schemas:
- author: Aspose
  dateModified: '2026-08-19'
  description: Generate barcode C# using Aspose.BarCode to create a Macro PDF417 with
    custom text and save as an image file.
  headline: Generate barcode C# with Macro PDF417 – full example
  type: TechArticle
- questions:
  - answer: Yes. Replace `BarCodeImageFormat.Png` with `Jpeg`, `Bmp`, or `Gif` as
      needed.
    question: Can I generate a different image format?
  - answer: Macro PDF417 is designed for segmentation. Adjust `MacroPdf417SegmentsCount`
      and `MacroPdf417SegmentID` for each part, then concatenate the scanned results.
    question: What if my data exceeds a single barcode?
  - answer: Aspose.BarCode fully supports Unicode. Ensure your source file is saved
      with UTF‑8 encoding to avoid character corruption.
    question: Is Unicode support guaranteed?
  - answer: A licensed version removes the evaluation watermark and provides full
      functionality. The trial works for testing and learning.
    question: Do I need a license for production?
  type: FAQPage
tags:
- barcode
- C#
- Aspose
title: Создание штрихкода C# с Macro PDF417 – полный пример
url: /ru/net/compact-pdf417-encoding/generate-barcode-c-with-macro-pdf417-full-example/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Генерация штрих‑кода C# с Macro PDF417 – полный пример

Если вам нужно **generate barcode C#** для формата Macro PDF417, это руководство покажет готовое решение, готовое к запуску. Вы увидите, как **how to generate pdf417**, добавить пользовательский текст и **generate barcode image file** в одной автономной программе.

В руководстве рассматривается всё: от установки библиотеки Aspose.BarCode до настройки метаданных Macro PDF417, так что вы можете скопировать код прямо в свой проект и сразу увидеть результат.

## Prerequisites

Перед началом убедитесь, что у вас есть:

- .NET 6.0 SDK или новее (код также работает с .NET Framework 4.7+)
- Visual Studio 2022 (или любой IDE, поддерживающий C#)
- Лицензия Aspose.BarCode for .NET (бесплатная trial‑версия подходит для оценки)
- Базовое знакомство с синтаксисом C#

> **Pro tip:** Установите пакет NuGet через CLI, чтобы избежать конфликтов версий:  
> `dotnet add package Aspose.BarCode`

## Step 1: Set up the project and import the library

Создайте новое консольное приложение и добавьте необходимые директивы `using`.

```csharp
using Aspose.BarCode.Generation;
using System;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // The full barcode generation logic starts in the next step.
        }
    }
}
```

**Почему этот шаг важен:**  
Пространство имён `Aspose.BarCode.Generation` предоставляет класс `BarcodeGenerator`, который является точкой входа для создания любого типа штрих‑кода, включая Macro PDF417. Импорт `System` даёт доступ к `DateTime` для метаданных временной метки.

## Step 2: Create a Macro PDF417 generator with custom text

Замените комментарий‑заполнитель инициализацией генератора. Это демонстрирует **create barcode custom text**, одновременно выбирая правильный тип кодирования.

```csharp
// Step 2: Initialize a barcode generator for Macro PDF417 with custom text.
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.MacroPdf417,          // Choose Macro PDF417 as the symbology
    "Åspóse.Barcóde©");               // Custom text can contain Unicode characters
```

**Объяснение:**  
- `EncodeTypes.MacroPdf417` указывает Aspose генерировать PDF417‑штрих‑код с поддержкой макро‑функций (разделение файла, контрольная сумма и т.д.).  
- Текст `"Åspóse.Barcóde©"` показывает, что Unicode‑символы полностью поддерживаются, что часто требуется для международных приложений.

## Step 3: Configure appearance and Macro PDF417 metadata

Тонко настройте размеры штрих‑кода и задайте макро‑специфичные поля, необходимые для обработки сегментированных файлов.

```csharp
// Appearance: set the narrow bar width to 2 pixels.
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;

// PDF417 specific settings
barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 5;                     // Number of columns per row
barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;    // Unique file identifier
barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;       // Current segment number
barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;  // Total number of segments
barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01"; // Logical file name
barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234;     // CCITT‑16 CRC checksum
barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000;   // Approximate file size in bytes
barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2019, 11, 1);
barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;
```

**Почему эти настройки важны:**

| Параметр | Назначение |
|----------|------------|
| `XDimension.Pixels` | Управляет визуальной плотностью; 2 px дают чёткое, сканируемое изображение. |
| `Columns` | Определяет количество столбцов данных в строке, влияя на размер штрих‑кода. |
| `MacroPdf417FileID` | Уникально идентифицирует логический файл во всех сегментах. |
| `MacroPdf417SegmentID` / `SegmentsCount` | Позволяют восстановить исходный файл из нескольких штрих‑кодов. |
| `MacroPdf417FileName` | Человекочитаемое имя, хранящееся внутри штрих‑кода для последующей обработки. |
| `MacroPdf417Checksum` | Обеспечивает обнаружение ошибок с помощью алгоритма CCITT‑16 CRC. |
| `MacroPdf417FileSize` | Помогает декодеру понять, когда получен весь файл. |
| `MacroPdf417TimeStamp` | Записывает время генерации штрих‑кода, полезно для аудита. |
| `MacroPdf417Addressee` / `MacroPdf417Sender` | Необязательные поля, которые могут использоваться в бизнес‑процессах. |
| `MacroPdf417Terminator` | Указывает, что данный сегмент является последним (`Set`). |

## Step 4: Save the barcode as an image file

Наконец, сохраните штрих‑код в файл PNG, чтобы его можно было просмотреть или встроить в другое место.

```csharp
// Step 4: Save the generated barcode image to a file.
string outputPath = @"C:\Barcodes\ExtPDF417Meta.png";   // Adjust the folder as needed
barcodeGenerator.Save(outputPath, BarCodeImageFormat.Png);

Console.WriteLine($"Barcode saved to {outputPath}");
```

**Что вы увидите:**  
Изображение PNG с именем `ExtPDF417Meta.png`, содержащее Macro PDF417‑штрих‑код, который кодирует пользовательский текст и все указанные метаданные. Изображение можно открыть любой стандартной программой‑просмотрщиком или вставить в PDF, отчёты или веб‑страницы.

## Full source code (copy‑paste ready)

```csharp
using Aspose.BarCode.Generation;
using System;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // Initialize generator with custom Unicode text.
            BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
                EncodeTypes.MacroPdf417,
                "Åspóse.Barcóde©");

            // Appearance settings.
            barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
            barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 5;

            // Macro PDF417 metadata.
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234;
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000;
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2019, 11, 1);
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;

            // Save the barcode image.
            string outputPath = @"C:\Barcodes\ExtPDF417Meta.png";
            barcodeGenerator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"Barcode saved to {outputPath}");
        }
    }
}
```

### Expected output

Запуск программы выводит:

```
Barcode saved to C:\Barcodes\ExtPDF417Meta.png
```

Открытие `ExtPDF417Meta.png` показывает чистый Macro PDF417‑штрих‑код, который корректно сканируется любым PDF417‑ридером, сохраняя пользовательский текст `"Åspóse.Barcóde©"` и заданные макро‑метаданные.

## Common questions and edge cases

- **Можно ли генерировать другой формат изображения?**  
  Да. Замените `BarCodeImageFormat.Png` на `Jpeg`, `Bmp` или `Gif` по необходимости.

- **Что делать, если мои данные превышают один штрих‑код?**  
  Macro PDF417 предназначен для сегментации. Настройте `MacroPdf417SegmentsCount` и `MacroPdf417SegmentID` для каждой части, затем объедините результаты сканирования.

- **Гарантирована ли поддержка Unicode?**  
  Aspose.BarCode полностью поддерживает Unicode. Убедитесь, что ваш исходный файл сохранён в кодировке UTF‑8, чтобы избежать искажения символов.

- **Нужна ли лицензия для продакшн‑использования?**  
  Лицензированная версия убирает водяной знак оценки и предоставляет полный набор функций. Триальная версия подходит для тестирования и обучения.

## Conclusion

Теперь вы знаете, как **generate barcode C#** для Macro PDF417, **how to generate pdf417** с богатыми метаданными, **create barcode custom text** и **generate barcode image file** с помощью Aspose.BarCode. Полный, готовый к запуску пример демонстрирует каждый необходимый шаг — от настройки проекта до сохранения финального PNG‑изображения.

### Next steps

- Поэкспериментируйте с другими параметрами PDF417, такими как `ErrorCorrectionLevel` и `CompactPdf417`, для получения более компактных символов.  
- Интегрируйте сгенерированный штрих‑код в PDF‑отчёт с помощью Aspose.PDF.  
- Изучите пакетную генерацию: пройдитесь по коллекции файлов и создайте серию сегментированных Macro PDF417‑штрих‑кодов.

Применяйте код в своём рабочем процессе, и генерация штрих‑кодов станет бесшовной частью ваших C#‑приложений. Приятного кодинга!

## What Should You Learn Next?

Следующие руководства охватывают тесно связанные темы, расширяющие техники, продемонстрированные в этом руководстве. Каждый ресурс включает полностью рабочие примеры кода с пошаговыми объяснениями, чтобы помочь вам освоить дополнительные возможности API и исследовать альтернативные подходы в собственных проектах.

- [How to generate Aztec barcode with custom aspect ratio using Aspose.BarCode for .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)
- [Generate barcode image – Code 93 with Aspose.BarCode](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-code-93-configuration/)
- [How to Generate and Adjust Barcode Height for One-Dimensional Databar using Aspose.BarCode for .NET](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-barcode-height-adjustment/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}