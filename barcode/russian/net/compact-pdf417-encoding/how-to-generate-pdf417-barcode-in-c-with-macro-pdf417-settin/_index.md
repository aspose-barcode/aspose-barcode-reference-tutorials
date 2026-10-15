---
category: general
date: 2026-10-15
description: Узнайте, как генерировать штрих‑код PDF417 в C# с использованием параметров
  Macro‑PDF417, задавать размеры штрих‑кода и сохранять его в PNG. Включён полный
  пример кода.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to generate pdf417 barcode
- C# PDF417 barcode
- Macro PDF417 parameters
- set barcode dimensions
- barcode image format
- barcode checksum
language: ru
lastmod: 2026-10-15
og_description: Как сгенерировать штрих‑код PDF417 в C# с полной конфигурацией Macro‑PDF417,
  управлением размерами и выводом в PNG. Следуйте полному примеру.
og_image_alt: Screenshot of a generated PDF417 barcode image created with C# code
og_title: Как сгенерировать штрих‑код PDF417 в C# – пошаговое руководство
schemas:
- author: Aspose
  dateModified: '2026-10-15'
  description: Learn how to generate PDF417 barcode in C# using Macro‑PDF417 parameters,
    set barcode dimensions, and save as PNG. Complete code example included.
  headline: How to generate PDF417 barcode in C# with Macro‑PDF417 settings
  type: TechArticle
tags:
- barcode
- PDF417
- C#
- Aspose.Barcode
title: Как сгенерировать штрих‑код PDF417 в C# с настройками Macro‑PDF417
url: /ru/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-with-macro-pdf417-settin/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Как сгенерировать штрих‑код PDF417 в C# с настройками Macro‑PDF417

Если вам нужно **как сгенерировать PDF417 штрих‑код** для документооборота, это руководство покажет точные шаги. Вы увидите, как настроить параметры Macro‑PDF417, задать размеры штрих‑кода и экспортировать результат в виде PNG‑изображения — всё в одной исполняемой программе на C#.

Генерация PDF417 штрих‑кода не требует множества библиотек или сложной пост‑обработки. С помощью Aspose.Barcode for .NET вы можете контролировать каждый аспект штрих‑кода, от ширины модуля до контрольной суммы, и получать изображение высокого качества, готовое к печати или сканированию.

## Требования

Прежде чем начать, убедитесь, что у вас есть:

* .NET 6.0 (или более поздний) SDK установлен  
* Visual Studio 2022 или любая другая C# IDE по вашему выбору  
* NuGet‑пакет Aspose.Barcode for .NET (`Install-Package Aspose.Barcode`)  

Эти требования гарантируют, что код соберётся без дополнительной настройки.

## Шаг 1: Создать генератор штрих‑кода для Macro‑PDF417

Первая операция создаёт экземпляр `BarcodeGenerator`, нацеленный на формат `EncodeTypes.MacroPdf417`. Конструктор получает данные, которые вы хотите закодировать — в данном случае строку `"Sample text"`.

```csharp
using Aspose.Barcode;
using Aspose.Barcode.Generation;

// Step 1: Initialize the generator with Macro‑PDF417 and data to encode
using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MacroPdf417, "Sample text"))
{
    // Subsequent steps configure the barcode
```

Создание генератора инициализирует внутренний объект `Parameters`, который вы будете использовать для настройки свойств **C# PDF417 штрих‑кода**.

## Шаг 2: Задать базовый внешний вид штрих‑кода – установить размеры

Контроль визуального размера штрих‑кода повышает надёжность сканирования. Свойство `XDimension.Pixels` определяет ширину модуля (точки), а `Pdf417.Columns` задаёт количество колонок в штрих‑коде.

```csharp
    // Step 2: Define module width and column count
    generator.Parameters.Barcode.XDimension.Pixels = 2;   // module width in pixels
    generator.Parameters.Barcode.Pdf417.Columns = 5;    // number of columns
```

Установка этих размеров гарантирует, что штрих‑код поместится в типичные размеры этикеток и удовлетворит спецификации сканеров.

## Шаг 3: Указать идентификацию файла Macro‑PDF417

Macro‑PDF417 расширяет стандартный PDF417 метаданными уровня файла. Необходимо задать уникальный идентификатор файла, идентификатор сегмента, общее количество сегментов и человекочитаемое имя файла.

```csharp
    // Step 3: Assign macro file identification
    generator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
    generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 1;
    generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 10;
    generator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "myFile.pdf";
```

Эти **параметры Macro PDF417** позволяют downstream‑системам восстановить оригинальный файл из нескольких сегментов штрих‑кода.

## Шаг 4: Добавить дополнительную макро‑метадату – включить контрольную сумму штрих‑кода

Помимо идентификации, Macro‑PDF417 может хранить контрольную сумму, размер файла, метку времени, получателя, отправителя и флаг завершения. Предоставление контрольной суммы улучшает проверку целостности данных при декодировании.

```csharp
    // Step 4: Populate extra macro metadata
    generator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 0x1A2B;               // CCITT‑16 checksum
    generator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 850_000;             // file size in bytes
    generator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = DateTime.UtcNow;   // UTC timestamp
    generator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "Acme Corp";
    generator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "John Doe";
    generator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;
```

Включение **контрольной суммы штрих‑кода** и другой метадаты делает штрих‑код самодокументируемым, что ценно для автоматических конвейеров обработки документов.

## Шаг 5: Сохранить сгенерированный штрих‑код как PNG‑изображение – выбрать формат изображения штрих‑кода

Последний шаг записывает штрих‑код в файл. Метод `Save` принимает путь к файлу и перечисление `BarCodeImageFormat`. PNG обеспечивает безпотерьную компрессию, сохраняющую резкие края для надёжного сканирования.

```csharp
    // Step 5: Export the barcode to PNG
    generator.Save("C:/Barcodes/MacroPdf417.png", BarCodeImageFormat.Png);
}
```

После выполнения файл `MacroPdf417.png` будет содержать чёткий PDF417 штрих‑код, готовый к встраиванию в PDF, печати на этикетках или отображению на экранах.

## Ожидаемый результат

Открытие `C:/Barcodes/MacroPdf417.png` показывает прямоугольный штрих‑код с закодированным текстом «Sample text». Штрих‑код включает макро‑метаданные, которые вы задали, и их можно проверить любой программой‑сканером PDF417, поддерживающей Macro‑PDF417. Размеры изображения отражают ширину модуля (2 px) и количество колонок (5), получая компактный, но разборчивый штрих‑код.

## Распространённые варианты и граничные случаи

| Ситуация | Корректировка |
|-----------|------------|
| **Разная длина данных** | Замените `"Sample text"` любой строкой UTF‑8; генератор автоматически подстроит размер штрих‑кода. |
| **Более высокое разрешение** | Увеличьте `XDimension.Pixels` до 3 или 4 для больших модулей, полезно для принтеров с низким разрешением. |
| **Больше сегментов** | Измените `MacroPdf417SegmentsCount`, чтобы соответствовать общему количеству частей штрих‑кода, которые планируете генерировать. |
| **Альтернативный формат изображения** | Используйте `BarCodeImageFormat.Jpeg` или `BarCodeImageFormat.Bmp`, если ваша downstream‑система предпочитает эти форматы. |
| **Пользовательская коррекция ошибок** | Измените `generator.Parameters.Barcode.Pdf417.ErrorLevel` (диапазон 0‑8), чтобы сбалансировать плотность данных и устойчивость к ошибкам. |

**Совет:** Всегда проверяйте сгенерированный штрих‑код физическим сканером перед вводом в эксплуатацию. У сканеров могут быть ограничения прошивки на ширину модуля или количество колонок.

## Полный исходный код

```csharp
using System;
using Aspose.Barcode;
using Aspose.Barcode.Generation;

namespace Pdf417MacroDemo
{
    class Program
    {
        static void Main()
        {
            // Initialize the generator for Macro‑PDF417 with sample data
            using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MacroPdf417, "Sample text"))
            {
                // Set visual dimensions
                generator.Parameters.Barcode.XDimension.Pixels = 2;          // module width
                generator.Parameters.Barcode.Pdf417.Columns = 5;           // column count

                // Provide macro file identification
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
                generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 1;
                generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 10;
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "myFile.pdf";

                // Add macro metadata
                generator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 0x1A2B;               // CCITT‑16 checksum
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 850_000;             // file size in bytes
                generator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = DateTime.UtcNow;   // timestamp
                generator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "Acme Corp";
                generator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "John Doe";
                generator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;

                // Export as PNG
                generator.Save("C:/Barcodes/MacroPdf417.png", BarCodeImageFormat.Png);
            }

            Console.WriteLine("PDF417 barcode generated successfully.");
        }
    }
}
```

Запуск этой программы создаст `MacroPdf417.png` в папке `C:/Barcodes`. Консоль подтвердит успешную генерацию.

## Заключение

Теперь вы знаете **как сгенерировать PDF417 штрих‑код** в C# с полным управлением Macro‑PDF417, как **задать размеры штрих‑кода**, как внедрить **контрольную сумму штрих‑кода** и другую макро‑метадату, а также как экспортировать результат, выбрав **формат изображения штрих‑кода**. Полный пример можно скопировать в любой .NET‑проект, изменить под разные полезные нагрузки и интегрировать в более крупные конвейеры автоматизации документов.

### Следующие шаги

* Исследуйте уровни коррекции ошибок **C# PDF417 штрих‑кода**, чтобы повысить надёжность сканирования.  
* Объединяйте несколько сегментов Macro‑PDF417 для кодирования больших файлов, таких как PDF или изображения.  
* Переключите **формат изображения штрих‑кода** на SVG для масштабируемой векторной графики в веб‑приложениях.  

Экспериментируйте с параметрами и делитесь результатами в комментариях или на форумах сообщества. Приятного кодинга!

## Что изучать дальше?

Следующие учебные материалы охватывают тесно связанные темы, построенные на техниках, продемонстрированных в этом руководстве. Каждый ресурс включает полностью работающие примеры кода с пошаговыми объяснениями, помогающими освоить дополнительные возможности API и исследовать альтернативные подходы в ваших проектах.

- [Generate barcode C# with Macro PDF417 – full example](/barcode/english/net/compact-pdf417-encoding/generate-barcode-c-with-macro-pdf417-full-example/)
- [How to Generate PDF417 Barcode – Complete Programming Guide](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-complete-programming-guide/)
- [How to generate PDF417 barcode in C# with custom dimensions](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-with-custom-dimensions/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}