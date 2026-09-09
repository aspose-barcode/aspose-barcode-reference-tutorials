---
category: general
date: 2026-07-21
description: Создайте штрих‑код PDF417 с помощью Aspose на C#. Узнайте, как сгенерировать
  штрих‑код PDF417 с метаданными за несколько простых шагов.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create pdf417 barcode
- how to generate pdf417 barcode
- create barcode with aspose
language: ru
lastmod: 2026-07-21
og_description: Создайте штрих‑код PDF417 быстро с помощью Aspose. Это руководство
  покажет, как сгенерировать штрих‑код PDF417, установить макро‑метаданные и сохранить
  изображение.
og_image_alt: Screenshot showing a generated PDF417 barcode created with Aspose
og_title: Создание штрих‑кода PDF417 с помощью Aspose – пошаговое руководство
schemas:
- author: Aspose
  dateModified: '2026-07-21'
  description: Create PDF417 barcode using Aspose in C#. Learn how to generate PDF417
    barcode with metadata in just a few steps.
  headline: Create PDF417 Barcode with Aspose – Complete Guide
  type: TechArticle
tags:
- barcode
- Aspose
- PDF417
title: Создание штрих‑кода PDF417 с помощью Aspose – Полное руководство
url: /ru/net/compact-pdf417-encoding/create-pdf417-barcode-with-aspose-complete-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Создание штрих‑кода PDF417 с помощью Aspose – Полное руководство

Когда‑то вам нужно **создать штрих‑код PDF417**, но вы не знали, какая библиотека справится с макро‑метаданными без проблем? Вы не одиноки. В этом руководстве мы покажем, **как сгенерировать штрих‑код PDF417** с помощью библиотеки Aspose.BarCode, установить все макро‑поля и сохранить результат в PNG — всё это в нескольких строках C#.

Мы пройдем весь процесс, от установки Aspose.BarCode до настройки внешнего вида штрих‑кода, чтобы вы могли вставить код в любой .NET‑проект и увидеть результат мгновенно. К концу вы будете уверенно создавать штрих‑коды с Aspose и настраивать макро‑параметры для реальных сценариев сканирования.

## Требования

Прежде чем начать, убедитесь, что у вас есть:

- .NET 6.0 или новее (код также работает на .NET Framework 4.7+)
- Действующая лицензия Aspose.BarCode for .NET (бесплатная trial‑версия подходит для оценки)
- Visual Studio 2022 или ваша любимая IDE
- Базовые знания C# — ничего сложного, только обычные `using`‑директивы

Если чего‑то не хватает, установите NuGet‑пакет сейчас:

```bash
dotnet add package Aspose.BarCode
```

Вот и всё — дополнительных зависимостей не требуется.

## Шаг 1: Инициализация генератора штрих‑кода (Primary Keyword Appears Here)

Первым делом создайте экземпляр `BarcodeGenerator`, который будет использовать симбологию **PDF417**. Aspose называет её `EncodeTypes.Pdf417`, но для штрих‑кодов с поддержкой макросов используйте `EncodeTypes.MacroPdf417`.

```csharp
using Aspose.BarCode.Generation;
using System;

class Program
{
    static void Main()
    {
        // Create a PDF417 barcode generator with the text you want to encode
        using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MacroPdf417, "Åspóse.Barcóde©"))
        {
            // The rest of the steps are inside this using block
        }
    }
}
```

*Почему это важно*: оператор `using` гарантирует корректное освобождение ресурсов генератора, включая нативные. Кроме того, выбор `MacroPdf417` открывает возможность встраивать метаданные уровня файла — удобная функция для больших документооборотных процессов.

## Шаг 2: Определение базового внешнего вида (Secondary Keyword – how to generate pdf417 barcode)

Штрих‑код, который слишком мал или сжат, будет нечитаем. Aspose предоставляет тонкую настройку размера модуля, количества колонок и прочего.

```csharp
// Set the module (X) dimension – each bar will be 2 pixels wide
generator.Parameters.Barcode.XDimension.Pixels = 2;

// Choose a reasonable column count for readability
generator.Parameters.Barcode.Pdf417.Columns = 5;

// Optional: tweak error correction level if you need higher resilience
generator.Parameters.Barcode.Pdf417.ErrorCorrectionLevel = 5; // 0‑8 range
```

Эти три строки — ядро **how to generate PDF417 barcode**, которое будет надёжно сканироваться на большинстве устройств. Регулируйте `Columns` и `ErrorCorrectionLevel` в зависимости от объёма данных и условий сканирования.

## Шаг 3: Добавление макро‑метаданных PDF417 (Primary Keyword – create pdf417 barcode)

Macro PDF417 позволяет встраивать информацию уровня документа непосредственно в штрих‑код. Здесь вы действительно *создаёте штрих‑код PDF417*, который несёт больше, чем простую строку.

```csharp
// File identifier – must be unique across all segments
generator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;

// Segment identifier – this is segment 12 of the whole file
generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;

// Total number of segments in the file
generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;

// Human‑readable file name (optional but nice for debugging)
generator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";

// Optional CCITT‑16 checksum for extra integrity checking
generator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234;

// Approximate file size in bytes – helpful for large PDFs
generator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000;

// Timestamp when the file was generated
generator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2019, 11, 1);

// Add address fields – these are free‑form strings
generator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
generator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";

// Define the macro terminator (whether this is the last segment)
generator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;
```

*Зачем это нужно*: сканеры, поддерживающие Macro PDF417, могут восстанавливать оригинальный файл из нескольких сегментов штрих‑кода, проверять целостность через контрольную сумму и даже отображать информацию отправителя/получателя. Это идеально для логистики, архивирования документов или любых сценариев, где один штрих‑код не вмещает весь полезный груз.

## Шаг 4: Сохранение штрих‑кода как изображения (Secondary Keyword – create barcode with aspose)

Наконец, запишите штрих‑код в PNG‑файл (или любой другой формат, поддерживаемый Aspose). Перечисление `BarCodeImageFormat` делает это тривиальным.

```csharp
// Choose a folder you have write access to
string outputPath = @"C:\Barcodes\ExtPDF417Meta.png";

// Save the barcode – PNG keeps the crisp edges
generator.Save(outputPath, BarCodeImageFormat.Png);
Console.WriteLine($"Barcode saved to {outputPath}");
```

Это весь поток **create barcode with Aspose**. После запуска программы откройте PNG‑файл — вы увидите чистый символ PDF417 с внедрёнными макро‑полями.

![Создание примера штрих‑кода PDF417](image.png "Создание примера штрих‑кода PDF417")

*Подсказка*: если нужен другой формат изображения (JPEG, BMP, SVG), просто замените `BarCodeImageFormat.Png` на нужное значение перечисления.

## Полный рабочий пример

Объединив все части, получаем готовое к запуску консольное приложение:

```csharp
using Aspose.BarCode.Generation;
using System;

class Program
{
    static void Main()
    {
        // Initialise generator for Macro PDF417
        using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MacroPdf417, "Åspóse.Barcóde©"))
        {
            // Basic appearance
            generator.Parameters.Barcode.XDimension.Pixels = 2;
            generator.Parameters.Barcode.Pdf417.Columns = 5;
            generator.Parameters.Barcode.Pdf417.ErrorCorrectionLevel = 5;

            // Macro metadata
            generator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
            generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;
            generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;
            generator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";
            generator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234;
            generator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000;
            generator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2019, 11, 1);
            generator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
            generator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
            generator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;

            // Save as PNG
            string outputPath = @"C:\Barcodes\ExtPDF417Meta.png";
            generator.Save(outputPath, BarCodeImageFormat.Png);
            Console.WriteLine($"Barcode saved to {outputPath}");
        }
    }
}
```

Запустите программу, откройте полученное изображение, и вы увидите идеально сформированный штрих‑код PDF417, готовый к сканированию.

## Часто задаваемые вопросы и особые случаи

**Что делать, если мои данные превышают ёмкость одного символа PDF417?**  
Aspose автоматически разбивает данные на несколько макросегментов, если включён `MacroPdf417`. Просто убедитесь, что `SegmentsCount` отражает общее количество частей.

**Можно ли изменить цвет штрих‑кода?**  
Конечно. Используйте `generator.Parameters.Barcode.BarColor` и `BackgroundColor`, чтобы задать любые цвета.

**Поддерживается ли Unicode?**  
Да — в примере используются символы вроде `Å` и `©`. Aspose обрабатывает кодировку UTF‑8 внутри, так что можно встраивать практически любой язык.

**Какова производительность при генерации тысяч штрих‑кодов?**  
Создание отдельного генератора для каждого штрих‑кода приемлемо при небольших нагрузках. Для массовой обработки лучше переиспользовать один экземпляр `BarcodeGenerator` и менять только свойство `CodeText` между сохранениями.

## Заключение

Теперь вы знаете, **как создать штрих‑код PDF417** с помощью Aspose, задать макро‑уровневые метаданные и экспортировать результат в PNG высокого качества. Этот подход — *create pdf417 barcode* с тонко настроенным внешним видом и встроенной файловой информацией — надёжен и легко интегрируется в существующие .NET‑сервисы.

Готовы к следующему шагу? Попробуйте генерировать серию сегментированных штрих‑кодов для представления многомегабайтного PDF, либо поэкспериментируйте с различными уровнями коррекции ошибок, чтобы увидеть, как меняется надёжность сканирования. А если хотите узнать о других симбологиях, загляните в руководства Aspose по генерации QR‑кодов или DataMatrix.

Счастливого кодинга, и пусть ваши сканы всегда будут без ошибок!

## Что изучать дальше?

Следующие руководства охватывают смежные темы, расширяющие техники, продемонстрированные в этом руководстве. Каждый ресурс содержит полностью рабочие примеры кода с пошаговыми объяснениями, чтобы помочь вам освоить дополнительные возможности API и исследовать альтернативные подходы в собственных проектах.

- [How to Create Barcode – Compact PDF417 with Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [Cómo crear un código de barras – PDF417 compacto con Aspose.BarCode](/barcode/spanish/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [如何使用 Aspose.BarCode 创建紧凑型 PDF417 条码](/barcode/chinese/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}