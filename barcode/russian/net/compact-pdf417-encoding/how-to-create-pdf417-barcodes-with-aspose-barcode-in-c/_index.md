---
category: general
date: 2026-11-17
description: Как создать штрихкоды PDF417 с помощью Aspose.BarCode — пошаговое руководство,
  в котором также показано, как создать штрихкод Aspose на C#.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to create pdf417
- create barcode aspose
language: ru
lastmod: 2026-11-17
og_description: Как создавать штрихкоды PDF417 с помощью Aspose.BarCode. Этот учебник
  пошагово покажет, как создать штрихкод Aspose, настроить метаданные Macro PDF417
  и сохранить изображение.
og_image_alt: Screenshot of a PDF417 barcode generated with Aspose.BarCode in C#
og_title: Как создать штрихкоды PDF417 с помощью Aspose.BarCode – полное руководство
  на C#
schemas:
- author: Aspose
  dateModified: '2026-11-17'
  description: How to create PDF417 barcodes using Aspose.BarCode – step‑by‑step guide
    that also shows how to create barcode aspose in C#.
  headline: How to create PDF417 barcodes with Aspose.BarCode in C#
  type: TechArticle
- description: How to create PDF417 barcodes using Aspose.BarCode – step‑by‑step guide
    that also shows how to create barcode aspose in C#.
  name: How to create PDF417 barcodes with Aspose.BarCode in C#
  steps:
  - name: Set up the project and import Aspose.BarCode
    text: 'Create a new console project and add the Aspose.BarCode NuGet package:'
  - name: Initialise the `BarcodeGenerator` for Macro PDF417
    text: The `BarcodeGenerator` constructor takes the barcode type and the text you
      want to encode. For Macro PDF417 you use `EncodeTypes.MacroPdf417`.
  - name: Configure appearance and Macro PDF417 metadata
    text: Configure appearance and Macro PDF417 metadata
  - name: Save the barcode image
    text: '```csharp // Choose the output folder (ensure it exists) and save as PNG.
      string outputPath = "MacroPdf417.png"; generator.Save(outputPath, BarCodeImageFormat.Png);
      Console.WriteLine($"PDF417 barcode saved to {outputPath}"); } ```'
  - name: Full, runnable example
    text: 'Putting everything together, here’s the complete program you can compile
      and run immediately:'
  type: HowTo
tags:
- barcode
- pdf417
- aspose
- csharp
title: Как создать штрихкоды PDF417 с помощью Aspose.BarCode на C#
url: /ru/net/compact-pdf417-encoding/how-to-create-pdf417-barcodes-with-aspose-barcode-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Как создавать штрих‑коды PDF417 с помощью Aspose.BarCode в C#

Если вам нужно **создавать штрих‑коды PDF417** для инвентаризации, доставки или отслеживания документов, это руководство покажет точные шаги с Aspose.BarCode. Вы увидите, как создать штрих‑код, настроить поля Macro PDF417 и экспортировать результат в виде PNG‑изображения — всё в одной исполняемой программе на C#.

Создание штрих‑кода PDF417 часто требуется, когда необходимо закодировать большие объёмы данных в компактном, машинно‑читаемом формате. Aspose.BarCode упрощает процесс, позволяя точно настроить размеры, количество столбцов и полный набор метаданных Macro PDF417. К концу этого урока у вас будет полностью готовый, автономный пример, который можно добавить в любой проект .NET.

## Предварительные требования

Прежде чем начать, убедитесь, что у вас есть:

* .NET 6.0 SDK или новее (код также работает с .NET Framework 4.7+).
* Действующая лицензия Aspose.BarCode для .NET (бесплатная оценочная версия подходит для тестов).
* Visual Studio 2022, VS Code или любой IDE, поддерживающий C#.
* Базовые знания синтаксиса C# и оператора `using`.

> **Совет:** Если запустить пример без лицензии, Aspose добавит небольшую водяную метку к сгенерированному изображению.

## Как создавать штрих‑коды PDF417 с Aspose.BarCode

Ниже реализации разбиты на четыре чётких шага. Каждый шаг содержит фрагмент кода, объяснение **почему** он нужен и практические рекомендации, которые вы сможете применить в своих проектах.

### Шаг 1: Настройка проекта и импорт Aspose.BarCode

Создайте новый консольный проект и добавьте пакет Aspose.BarCode через NuGet:

```bash
dotnet new console -n Pdf417Demo
cd Pdf417Demo
dotnet add package Aspose.BarCode
```

Затем откройте `Program.cs` и добавьте необходимые пространства имён:

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;
```

*Почему это важно:* Импорт `Aspose.BarCode.Generation` даёт доступ к `BarcodeGenerator` и перечислению `EncodeTypes`, которые являются основными классами для создания штрих‑кодов.

### Шаг 2: Инициализация `BarcodeGenerator` для Macro PDF417

Конструктор `BarcodeGenerator` принимает тип штрих‑кода и текст, который нужно закодировать. Для Macro PDF417 используется `EncodeTypes.MacroPdf417`.

```csharp
// Initialise a Macro PDF417 generator with the data you want to encode.
using (BarcodeGenerator generator = 
       new BarcodeGenerator(EncodeTypes.MacroPdf417, "Sample text for PDF417"))
{
    // The generator instance will be disposed automatically at the end of the block.
```

*Почему это важно:* Оператор `using` гарантирует своевременное освобождение неуправляемых ресурсов (например, дескрипторов GDI+), что предотвращает утечки памяти в длительно работающих сервисах.

### Шаг 3: Настройка внешнего вида и метаданных Macro PDF417

#### 3.1 Регулировка визуальных параметров

```csharp
    // Set the module (X) dimension – 2 pixels gives a reasonably dense barcode.
    generator.Parameters.Barcode.XDimension.Pixels = 2;

    // Define the number of columns; fewer columns make the barcode taller.
    generator.Parameters.Barcode.Pdf417.Columns = 5;
```

#### 3.2 Заполнение полей Macro PDF417

Macro PDF417 позволяет разбить большой документ на несколько сегментов штрих‑кода. Ниже перечислены поля, которые являются необязательными, но часто требуются в системах логистики или управления документами.

```csharp
    // Unique identifier for the whole file (must be the same across all segments).
    generator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;

    // Segment index (starting at 1). Here we generate the 12th segment.
    generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;

    // Total number of segments that will be produced.
    generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;

    // Human‑readable file name, useful for audits.
    generator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";

    // CCITT‑16 checksum – helps receivers verify data integrity.
    generator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234;

    // Approximate file size in bytes; some scanners use this for validation.
    generator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000;

    // Timestamp of the original file creation.
    generator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = 
        new DateTime(2024, 5, 1);

    // Optional address fields that can be read by advanced scanners.
    generator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
    generator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";

    // Terminator tells the scanner that this is the last segment.
    generator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = 
        Pdf417MacroTerminator.Set;
```

*Почему эти поля полезны:*  
* **FileID** связывает все сегменты вместе, позволяя их восстановление.  
* **SegmentID** и **SegmentsCount** сообщают сканеру порядок и завершённость серии.  
* **Checksum** и **FileSize** обеспечивают быструю проверку целостности без необходимости декодировать весь полезный груз.

> **Внимание:** `MacroPdf417FileID` должен быть уникальным для каждого логического документа. Повторное использование одного и того же идентификатора для разных файлов может привести к ошибкам восстановления.

### Шаг 4: Сохранение изображения штрих‑кода

```csharp
    // Choose the output folder (ensure it exists) and save as PNG.
    string outputPath = "MacroPdf417.png";
    generator.Save(outputPath, BarCodeImageFormat.Png);
    Console.WriteLine($"PDF417 barcode saved to {outputPath}");
}
```

*Почему PNG?* PNG сохраняет точные пиксельные данные без артефактов сжатия, что идеально для сканеров штрих‑кодов, которым нужны чёткие границы.

### Полный, готовый к запуску пример

Объединив всё вместе, получаем полную программу, которую можно сразу скомпилировать и запустить:

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace Pdf417Demo
{
    class Program
    {
        static void Main()
        {
            // Step 1‑4: generate a Macro PDF417 barcode and save it as PNG
            using (BarcodeGenerator generator = 
                   new BarcodeGenerator(EncodeTypes.MacroPdf417, "Sample text for PDF417"))
            {
                // Appearance
                generator.Parameters.Barcode.XDimension.Pixels = 2;
                generator.Parameters.Barcode.Pdf417.Columns = 5;

                // Macro PDF417 metadata
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
                generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;
                generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";
                generator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234;
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000;
                generator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = 
                    new DateTime(2024, 5, 1);
                generator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
                generator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
                generator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = 
                    Pdf417MacroTerminator.Set;

                // Save
                string outputPath = "MacroPdf417.png";
                generator.Save(outputPath, BarCodeImageFormat.Png);
                Console.WriteLine($"PDF417 barcode saved to {outputPath}");
            }
        }
    }
}
```

**Ожидаемый результат:** После выполнения программы в папке проекта появится файл `MacroPdf417.png`. Открыв изображение, вы увидите плотный, контрастный штрих‑код PDF417, который кодирует строку «Sample text for PDF417» вместе с указанными макро‑метаданными.

## Часто задаваемые вопросы и обработка граничных случаев

| Вопрос | Ответ |
|----------|--------|
| *Могу ли я генерировать несколько сегментов в цикле?* | Да. Инкрементируйте `MacroPdf417SegmentID` на каждой итерации, оставляйте `MacroPdf417FileID` постоянным и обновляйте `MacroPdf417SegmentsCount` только после того, как узнаете общее количество сегментов. |
| *Что делать, если данные превышают один символ PDF417?* | Macro |

## Что изучать дальше?

Следующие руководства охватывают тесно связанные темы, расширяющие техники, продемонстрированные в этом руководстве. Каждый ресурс содержит полностью работающие примеры кода с пошаговыми объяснениями, чтобы помочь вам освоить дополнительные возможности API и исследовать альтернативные подходы в собственных проектах.

- [How to create macro PDF417 barcode in C# using Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/how-to-create-macro-pdf417-barcode-in-c-using-aspose-barcode/)
- [How to create a micro PDF417 barcode in C# using Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/how-to-create-micro-pdf417-barcode-in-c/)
- [How to Create Barcode – Compact PDF417 with Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}