---
category: general
date: 2026-09-29
description: Как декодировать штрихкоды PDF417 в C# с использованием Aspose.BarCode.
  Изучите пример считывателя штрихкодов, показывающий, как читать изображения штрихкодов
  и извлекать макроданные.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to decode pdf417
- how to read barcode
- barcode reader example
- read pdf417 barcode
- read barcode image c#
language: ru
lastmod: 2026-09-29
og_description: Как декодировать штрихкоды PDF417 в C# с помощью Aspose.BarCode. Это
  руководство показывает готовый к запуску пример считывателя штрихкодов для чтения
  изображений штрихкодов.
og_image_alt: Screenshot of C# code decoding a PDF417 macro barcode and printing its
  fields
og_title: Как декодировать штрихкоды PDF417 в C# – полный пример считывателя штрихкодов
schemas:
- author: Aspose
  dateModified: '2026-09-29'
  description: How to decode PDF417 barcodes in C# using Aspose.BarCode. Learn a barcode
    reader example that shows how to read barcode images and extract macro data.
  headline: How to decode PDF417 barcodes in C# – step‑by‑step guide
  type: TechArticle
- description: How to decode PDF417 barcodes in C# using Aspose.BarCode. Learn a barcode
    reader example that shows how to read barcode images and extract macro data.
  name: How to decode PDF417 barcodes in C# – step‑by‑step guide
  steps:
  - name: Expected console output
    text: '``` Pdf417MacroFileID: 12345 Pdf417MacroSegmentID: 1 Pdf417MacroFileName:
      Invoice_2026_09_29.pdf ```'
  - name: No barcode detected
    text: '```csharp var results = reader.ReadBarCodes().ToList(); if (!results.Any())
      { Console.WriteLine("No PDF417 barcode found in the image."); return; } ```'
  - name: Unsupported image format
    text: Aspose.BarCode supports PNG, JPEG, BMP, TIFF, and GIF. Attempting to read
      a RAW or WebP file throws `ArgumentException`. Convert the image to a supported
      format before feeding it to the reader.
  - name: Large macro files
    text: Macro‑PDF417 can span many segments. To reconstruct the original file you
      must collect all segments (ordered by `MacroPdf417SegmentID`) and concatenate
      their payloads. The example above only prints individual segment metadata; a
      production implementation would store each segment in a dictionary, the
  - name: Performance tip
    text: If you process thousands of images, reuse a single `BarCodeReader` instance
      with the `SetImage` method instead of creating a new object for each file. This
      reduces memory allocations and speeds up decoding.
  type: HowTo
tags:
- barcode
- pdf417
- csharp
- Aspose.BarCode
title: Как декодировать штрихкоды PDF417 в C# – пошаговое руководство
url: /ru/net/compact-pdf417-encoding/how-to-decode-pdf417-barcodes-in-c-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Как декодировать штрихкоды PDF417 в C# – пошаговое руководство

Если вам нужно **how to decode PDF417** штрихкоды в C#, этот учебник предоставляет полное, готовое к запуску решение. Вы увидите **barcode reader example**, который демонстрирует **how to read barcode** изображения, извлекает макроинформацию и выводит результаты в консоль.

Декодирование PDF417 часто используется при обработке транспортных этикеток, билетов или государственных удостоверений. К концу этого руководства вы сможете считывать изображение штрихкода PDF417, получать доступ к его макрополям и обрабатывать типичные граничные случаи. Внешняя документация не требуется — всё необходимое включено.

## Что вы узнаете

- Установить библиотеку Aspose.BarCode для .NET  
- Создать `BarCodeReader`, который **read PDF417 barcode** данные из PNG или JPEG файла  
- Итерировать объекты `BarCodeResult` и получать свойства macro‑PDF417  
- Устранить распространённые проблемы, такие как неподдерживаемые форматы изображений или отсутствие макроданных  

## Предварительные требования

| Требование | Причина |
|-------------|--------|
| .NET 6.0 SDK or later | Provides the runtime for C# projects |
| Visual Studio 2022 (or any IDE that supports .NET) | Enables easy project creation and debugging |
| NuGet package **Aspose.BarCode** | Supplies the `BarCodeReader` class used in the example |
| A PDF417 macro image (e.g., `ExtPDF417Meta.png`) | The source file the reader will decode |

> **Pro tip:** Если у вас нет изображения PDF417, вы можете сгенерировать его с помощью бесплатного онлайн‑демо Aspose.BarCode или отсканировать реальную этикетку.

## Шаг 1: Установить Aspose.BarCode через NuGet

Откройте терминал в папке вашего решения и выполните:

```bash
dotnet add package Aspose.BarCode
```

Эта команда добавит последнюю стабильную версию Aspose.BarCode в ваш проект и обновит файл `.csproj`. Эта библиотека реализует функциональность **read barcode image C#** для десятков символогий, включая PDF417.

## Шаг 2: Создать BarCodeReader для **how to decode PDF417**

Ядром процесса **how to read barcode** является `BarCodeReader`. Вы должны указать читателю как путь к файлу, так и ожидаемую символогию (`DecodeType.MacroPdf417`). Указание правильного `DecodeType` повышает скорость и точность обнаружения.

```csharp
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

// Adjust the path to point at your PDF417 macro image
string imagePath = @"YOUR_DIRECTORY/ExtPDF417Meta.png";

// The reader is disposable; wrap it in a using block to release resources automatically.
using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
{
    // Step 3 is inside this block.
}
```

**Why this matters:**  
- `DecodeType.MacroPdf417` сообщает движку искать поля macro‑PDF417 (file ID, segment ID и т.д.).  
- Использование `using` гарантирует закрытие базового потока изображения, предотвращая проблемы с блокировкой файлов в Windows.

## Шаг 3: Итерировать обнаруженные штрихкоды

Одно изображение может содержать несколько штрихкодов. Метод `ReadBarCodes()` возвращает `IEnumerable<BarCodeResult>`, по которому можно выполнять цикл.

```csharp
foreach (BarCodeResult result in reader.ReadBarCodes())
{
    // Inside the loop we will extract macro data.
}
```

Если изображение не содержит символов PDF417, тело цикла никогда не выполнится, и вы можете обработать этот случай после цикла (см. раздел «Обработка ошибок»).

## Шаг 4: Доступ к полям PDF417 macro

Каждый `BarCodeResult` раскрывает свойство `Extended` с под‑объектом `Pdf417`. Наиболее часто используемые макрополя:

| Свойство | Значение |
|----------|---------|
| `MacroPdf417FileID` | Identifier of the whole macro PDF417 file |
| `MacroPdf417SegmentID` | Sequence number of the current segment |
| `MacroPdf417FileName` | Optional file name stored in the macro |

Ниже полный код, который выводит эти значения:

```csharp
foreach (BarCodeResult result in reader.ReadBarCodes())
{
    // Macro fields are nullable; use the null‑conditional operator to avoid exceptions.
    Console.WriteLine($"Pdf417MacroFileID:   {result.Extended?.Pdf417?.MacroPdf417FileID}");
    Console.WriteLine($"Pdf417MacroSegmentID:{result.Extended?.Pdf417?.MacroPdf417SegmentID}");
    Console.WriteLine($"Pdf417MacroFileName: {result.Extended?.Pdf417?.MacroPdf417FileName}");

    // You can also read other macro properties, such as:
    // result.Extended.Pdf417.MacroPdf417Addressee
    // result.Extended.Pdf417.MacroPdf417Sender
}
```

### Ожидаемый вывод в консоль

```
Pdf417MacroFileID:    12345
Pdf417MacroSegmentID: 1
Pdf417MacroFileName:  Invoice_2026_09_29.pdf
```

Если макрополя отсутствуют, вывод будет содержать пустые строки, так как свойства равны `null`. Это нормально для PDF417 без макросов.

## Шаг 5: Обработка распространённых подводных камней (обработка ошибок и граничные случаи)

### Штрихкод не обнаружен

```csharp
var results = reader.ReadBarCodes().ToList();
if (!results.Any())
{
    Console.WriteLine("No PDF417 barcode found in the image.");
    return;
}
```

### Неподдерживаемый формат изображения

Aspose.BarCode поддерживает PNG, JPEG, BMP, TIFF и GIF. Попытка прочитать файл RAW или WebP вызывает `ArgumentException`. Преобразуйте изображение в поддерживаемый формат перед передачей его читателю.

### Большие макрофайлы

Macro‑PDF417 может состоять из множества сегментов. Чтобы восстановить оригинальный файл, необходимо собрать все сегменты (упорядоченные по `MacroPdf417SegmentID`) и конкатенировать их полезные нагрузки. Приведённый выше пример только выводит метаданные отдельных сегментов; в продакшн‑реализации каждый сегмент следует сохранять в словарь, а затем собрать их после чтения всех сегментов.

### Совет по производительности

Если вы обрабатываете тысячи изображений, переиспользуйте один экземпляр `BarCodeReader` с методом `SetImage` вместо создания нового объекта для каждого файла. Это уменьшает выделения памяти и ускоряет декодирование.

```csharp
using (BarCodeReader reader = new BarCodeReader(null, DecodeType.MacroPdf417))
{
    foreach (string file in Directory.GetFiles(@"YOUR_DIRECTORY", "*.png"))
    {
        reader.SetImage(file);
        // read barcodes as shown earlier
    }
}
```

## Полный рабочий пример

Скопируйте следующую программу в новый проект Console App (`dotnet new console`). Он включает все шаги, обработку ошибок и комментарии.

```csharp
// Program.cs
using System;
using System.IO;
using System.Linq;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

class Program
{
    static void Main()
    {
        // Path to the PDF417 macro image – update to your actual location.
        string imagePath = @"YOUR_DIRECTORY/ExtPDF417Meta.png";

        // Verify the file exists before attempting to read.
        if (!File.Exists(imagePath))
        {
            Console.WriteLine($"File not found: {imagePath}");
            return;
        }

        // Initialize the reader for Macro PDF417.
        using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
        {
            var results = reader.ReadBarCodes().ToList();

            if (!results.Any())
            {
                Console.WriteLine("No PDF417 barcode detected in the image.");
                return;
            }

            foreach (BarCodeResult result in results)
            {
                // Print macro information safely.
                Console.WriteLine($"Pdf417MacroFileID:   {result.Extended?.Pdf417?.MacroPdf417FileID}");
                Console.WriteLine($"Pdf417MacroSegmentID:{result.Extended?.Pdf417?.MacroPdf417SegmentID}");
                Console.WriteLine($"Pdf417MacroFileName: {result.Extended?.Pdf417?.MacroPdf417FileName}");
                Console.WriteLine(); // blank line for readability
            }
        }
    }
}
```

**Запуск программы**

```bash
dotnet run
```

Вы должны увидеть вывод макрополей в консоль, соответствующий ожидаемому выводу, показанному ранее.

## Заключение

В этом учебнике вы узнали **how to decode PDF417** штрихкоды в C# с помощью лаконичного **barcode reader example**. Установив Aspose.BarCode, создав `BarCodeReader` для `MacroPdf417`, итерируя результаты и получая свойства макро `Extended.Pdf417`, вы сможете надёжно **read PDF417 barcode** данные из любого поддерживаемого изображения.

Далее вы можете:
- Реализовать агрегацию сегментов для восстановления многосегментных макрофайлов.  
- Исследовать другие символогии (QR, Code128), используя тот же шаблон `BarCodeReader`.  
- Интегрировать декодер в веб‑API, обрабатывающее загруженные изображения (`read barcode image C#` в контексте сервиса).  

Не стесняйтесь экспериментировать с различными источниками изображений, стратегиями обработки ошибок и оптимизациями производительности. Приятного кодинга!

## Что вам стоит изучить дальше?

Следующие учебники охватывают тесно связанные темы, основанные на техниках, продемонстрированных в этом руководстве. Каждый ресурс включает полностью работающие примеры кода с пошаговыми объяснениями, помогающими освоить дополнительные возможности API и исследовать альтернативные подходы к реализации в ваших проектах.

- [Как считывать PDF417 в C# – полное руководство по чтению штрихкодов](/barcode/english/net/compact-pdf417-encoding/how-to-read-pdf417-in-c-complete-barcode-reader-guide/)
- [Как генерировать штрихкод PDF417 с Aspose – полное руководство](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-with-aspose-complete-guide/)
- [Как создать штрихкод PDF417 с Aspose – полное пошаговое руководство](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-with-aspose-complete-step-by-st/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}