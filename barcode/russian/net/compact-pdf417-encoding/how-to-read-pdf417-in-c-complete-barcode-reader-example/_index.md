---
category: general
date: 2026-07-21
description: Как считать штрих‑код PDF417 в C# с помощью лаконичного примера считывателя
  штрих‑кодов. Быстро научитесь считывать штрих‑код с изображения с пошаговым кодом.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to read pdf417
- read barcode from image
- c# barcode reader example
language: ru
lastmod: 2026-07-21
og_description: Как считывать штрих‑код PDF417 в C# с практическим примером. Узнайте,
  как считывать штрих‑код с изображения и мгновенно интегрировать пример считывателя
  штрих‑кодов на C#.
og_image_alt: Screenshot of a C# console app printing PDF417 barcode details
og_title: Как читать PDF417 в C# – Полное руководство по чтению штрихкода
schemas:
- author: Aspose
  dateModified: '2026-07-21'
  description: How to read PDF417 barcode in C# using a concise barcode reader example.
    Quickly learn how to read barcode from image with step‑by‑step code.
  headline: How to Read PDF417 in C# – Complete Barcode Reader Example
  type: TechArticle
- description: How to read PDF417 barcode in C# using a concise barcode reader example.
    Quickly learn how to read barcode from image with step‑by‑step code.
  name: How to Read PDF417 in C# – Complete Barcode Reader Example
  steps:
  - name: Why This Works
    text: '- **`DecodeType.MacroPdf417`** tells the reader to expect the extended
      Macro PDF417 format, which carries extra metadata (file ID, segment count, timestamps,
      etc.). - The **`Extended.Pdf417`** object is only populated for Macro PDF417
      barcodes, so accessing those properties is safe after the `ReadBa'
  - name: Multiple Barcodes in One Image
    text: Sometimes a single scan contains more than one PDF417 segment (think of
      a multi‑page document encoded across several symbols). The `foreach` loop already
      enumerates *all* detected barcodes, so you don’t need extra logic—just collect
      the segments and reassemble them later if required.
  - name: Missing Extended Data
    text: 'Not every PDF417 carries macro information. In that scenario `result.Extended.Pdf417`
      will be instantiated but its fields will be default values (zero, empty string,
      or `false`). You can guard against it like this:'
  - name: Performance Tips
    text: '- **Batch processing:** If you have a folder of images, wrap the `BarCodeReader`
      creation inside a loop that reuses the same instance with `barcodeReader.SetImage(imagePath)`.
      This reduces allocation overhead. - **Parallelism:** For large workloads, consider
      `Parallel.ForEach` on the file list, but '
  type: HowTo
tags:
- barcode
- pdf417
- csharp
title: Как читать PDF417 в C# – полный пример считывателя штрихкода
url: /ru/net/compact-pdf417-encoding/how-to-read-pdf417-in-c-complete-barcode-reader-example/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Как считать PDF417 в C# – Полный пример считывателя штрихкодов

Когда‑то задавались вопросом **как считать PDF417** в проекте .NET без бесконечного поиска по документации? Вы не одиноки. Будь то сканирование водительских удостоверений, посадочных талонов или пользовательских меток инвентаря, надёжное извлечение этих данных — реальная потребность.  

В этом руководстве мы пройдём через **c# barcode reader example**, который извлекает все метаданные Macro PDF417 из одного файла изображения. К концу вы получите готовое консольное приложение, которое **reads barcode from image** и выводит все расширенные поля, которые могут понадобиться.

## Что вам понадобится

- .NET 6.0 SDK или новее (можно также целиться в .NET Framework 4.7+ – код работает одинаково)
- Visual Studio 2022, VS Code или любой другой редактор C#
- NuGet‑пакет **Aspose.BarCode for .NET** (класс `BarCodeReader` берётся из этой библиотеки)
- Файл изображения, содержащий штрихкод Macro PDF417 (для демонстрации используем `ExtPDF417Meta.png`)

> **Совет:** Если у вас нет образца PDF417, Aspose предоставляет несколько тестовых изображений в своём репозитории GitHub – просто скачайте одно и поместите в папку проекта.

## Шаг 1: Установите библиотеку штрихкодов

Откройте терминал в папке проекта и выполните:

```bash
dotnet add package Aspose.BarCode
```

Пакет добавляет `BarCodeReader`, `DecodeType` и свойство `Extended`, которое понадобится позже. Дополнительная конфигурация не требуется; библиотека работает «из коробки» для большинства форматов изображений (PNG, JPEG, BMP и т.д.).

## Шаг 2: Создайте минимальное консольное приложение

Создайте новый консольный проект, если ещё не сделали этого:

```bash
dotnet new console -n Pdf417ReaderDemo
cd Pdf417ReaderDemo
```

Замените сгенерированный `Program.cs` кодом ниже. Обратите внимание, что каждый раздел прокомментирован, чтобы вы могли следовать логике, даже если только начинаете работать со штрихкодами.

```csharp
using System;
using Aspose.BarCode;               // Core barcode classes
using Aspose.BarCode.BarCodeRecognition; // DecodeType enum

class Program
{
    static void Main()
    {
        // 👉 1️⃣  Point the reader at the image that holds the Macro PDF417 barcode.
        //    Replace the path with your own image location if needed.
        string imagePath = "YOUR_DIRECTORY/ExtPDF417Meta.png";

        // The BarCodeReader is disposable – using a using‑statement guarantees resources are freed.
        using (BarCodeReader barcodeReader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
        {
            // 👉 2️⃣  Iterate over every barcode that the reader finds.
            //    Macro PDF417 can embed multiple segments, so we handle them all.
            foreach (BarCodeResult result in barcodeReader.ReadBarCodes())
            {
                // Basic barcode info – always handy for logging.
                Console.WriteLine($"CodeType: {result.CodeTypeName}");
                Console.WriteLine($"CodeText: {result.CodeText}");

                // 👉 3️⃣  Pull out the extended Macro PDF417 fields.
                //    These properties live under result.Extended.Pdf417.
                var macro = result.Extended.Pdf417;

                Console.WriteLine($"Pdf417MacroFileID: {macro.MacroPdf417FileID}");
                Console.WriteLine($"Pdf417MacroSegmentID: {macro.MacroPdf417SegmentID}");
                Console.WriteLine($"Pdf417MacroSegmentsCount: {macro.MacroPdf417SegmentsCount}");
                Console.WriteLine($"Pdf417MacroFileName: {macro.MacroPdf417FileName}");
                Console.WriteLine($"Pdf417MacroChecksum: {macro.MacroPdf417Checksum}");
                Console.WriteLine($"Pdf417MacroFileSize: {macro.MacroPdf417FileSize}");
                Console.WriteLine($"Pdf417MacroTimeStamp: {macro.MacroPdf417TimeStamp}");
                Console.WriteLine($"Pdf417MacroAddressee: {macro.MacroPdf417Addressee}");
                Console.WriteLine($"Pdf417MacroSender: {macro.MacroPdf417Sender}");
                Console.WriteLine($"MacroPdf417Terminator: {macro.MacroPdf417Terminator}");
                Console.WriteLine(new string('-', 40)); // visual separator
            }
        }

        // Keep the console window open when debugging.
        Console.WriteLine("Done. Press any key to exit...");
        Console.ReadKey();
    }
}
```

### Почему это работает

- **`DecodeType.MacroPdf417`** указывает считывателю ожидать расширенный формат Macro PDF417, который содержит дополнительную метаинформацию (ID файла, количество сегментов, метки времени и т.д.).
- Объект **`Extended.Pdf417`** заполняется только для штрихкодов Macro PDF417, поэтому доступ к его свойствам безопасен после вызова `ReadBarCodes()`.
- Блок **`using`** гарантирует освобождение файловых дескрипторов, предотвращая блокировку файлов в Windows.

## Шаг 3: Запустите приложение

Соберите и выполните:

```bash
dotnet run
```

Если изображение содержит действительный штрихкод Macro PDF417, вы увидите вывод, похожий на:

```
CodeType: MacroPdf417
CodeText: 1234567890
Pdf417MacroFileID: 1
Pdf417MacroSegmentID: 0
Pdf417MacroSegmentsCount: 3
Pdf417MacroFileName: SampleDocument.pdf
Pdf417MacroChecksum: 0xABCD
Pdf417MacroFileSize: 102400
Pdf417MacroTimeStamp: 2024-03-15T10:23:45Z
Pdf417MacroAddressee: John Doe
Pdf417MacroSender: Acme Corp
MacroPdf417Terminator: True
----------------------------------------
Done. Press any key to exit...
```

Если ничего не выводится, проверьте правильность пути к изображению и убедитесь, что штрихкод действительно является вариантом Macro PDF417. Обычный PDF417 (без макро‑расширения) тоже будет декодирован, но свойства `Extended` останутся пустыми.

## Обработка граничных случаев

### Несколько штрихкодов на одном изображении

Иногда один скан содержит более одного сегмента PDF417 (например, многостраничный документ, закодированный в нескольких символах). Цикл `foreach` уже перечисляет *все* найденные штрихкоды, так что дополнительная логика не нужна – просто собирайте сегменты и собирайте их позже, если требуется.

### Отсутствие расширенных данных

Не каждый PDF417 несёт макро‑информацию. В таком случае `result.Extended.Pdf417` будет создан, но его поля будут иметь значения по умолчанию (ноль, пустая строка или `false`). Можно защититься так:

```csharp
if (macro.MacroPdf417FileID != 0)
{
    // Process macro data
}
else
{
    Console.WriteLine("No macro information present in this barcode.");
}
```

### Советы по производительности

- **Пакетная обработка:** Если у вас папка с изображениями, оберните создание `BarCodeReader` в цикл, переиспользуя один экземпляр с `barcodeReader.SetImage(imagePath)`. Это уменьшит накладные расходы на выделение памяти.
- **Параллелизм:** Для больших объёмов рассмотрите `Parallel.ForEach` по списку файлов, но помните, что считыватель Aspose потокобезопасен только при использовании отдельного экземпляра `BarCodeReader` в каждом потоке.

## Полный листинг исходного кода (готов к копированию)

Ниже представлен весь код программы ещё раз, готовый для вставки в `Program.cs`. Дополнительные файлы не требуются, кроме изображения.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

class Program
{
    static void Main()
    {
        string imagePath = "YOUR_DIRECTORY/ExtPDF417Meta.png";

        using (BarCodeReader barcodeReader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
        {
            foreach (BarCodeResult result in barcodeReader.ReadBarCodes())
            {
                Console.WriteLine($"CodeType: {result.CodeTypeName}");
                Console.WriteLine($"CodeText: {result.CodeText}");

                var macro = result.Extended.Pdf417;

                Console.WriteLine($"Pdf417MacroFileID: {macro.MacroPdf417FileID}");
                Console.WriteLine($"Pdf417MacroSegmentID: {macro.MacroPdf417SegmentID}");
                Console.WriteLine($"Pdf417MacroSegmentsCount: {macro.MacroPdf417SegmentsCount}");
                Console.WriteLine($"Pdf417MacroFileName: {macro.MacroPdf417FileName}");
                Console.WriteLine($"Pdf417MacroChecksum: {macro.MacroPdf417Checksum}");
                Console.WriteLine($"Pdf417MacroFileSize: {macro.MacroPdf417FileSize}");
                Console.WriteLine($"Pdf417MacroTimeStamp: {macro.MacroPdf417TimeStamp}");
                Console.WriteLine($"Pdf417MacroAddressee: {macro.MacroPdf417Addressee}");
                Console.WriteLine($"Pdf417MacroSender: {macro.MacroPdf417Sender}");
                Console.WriteLine($"MacroPdf417Terminator: {macro.MacroPdf417Terminator}");
                Console.WriteLine(new string('-', 40));
            }
        }

        Console.WriteLine("Done. Press any key to exit...");
        Console.ReadKey();
    }
}
```

## Итоги: Как быстро считать PDF417 в C#

- Установите **Aspose.BarCode** через NuGet.
- Укажите `BarCodeReader` на ваше изображение с `DecodeType.MacroPdf417`.
- Пройдитесь по `ReadBarCodes()` и получите как базовые, так и расширенные поля.
- Корректно обрабатывайте отсутствие макро‑данных и учитывайте оптимизации производительности для массовых сканирований.

## Следующие шаги и связанные темы

- **Read barcode from image** с другими форматами (QR, DataMatrix) – просто замените значение перечисления `DecodeType`.
- **Encode PDF417** с помощью `BarCodeGenerator`, если нужно создавать штрихкоды программно.
- Изучите **уровни коррекции ошибок** и их влияние на надёжность сканирования.
- Интегрируйте эту логику в ASP.NET Core API, чтобы предоставить чтение штрихкодов как веб‑сервис.

Экспериментируйте: меняйте изображение, играйте с флагом `DecodeType` или сохраняйте макро‑данные в базе. Основной шаблон остаётся тем же, и теперь у вас есть надёжный **c# barcode reader example** в арсенале.

Счастливого кодинга, и пусть ваши сканы всегда будут чистыми!


## Что изучать дальше?


Следующие руководства охватывают тесно связанные темы, расширяющие техники, продемонстрированные в этом руководстве. Каждый ресурс включает полностью работающие примеры кода с пошаговыми объяснениями, чтобы помочь вам освоить дополнительные возможности API и исследовать альтернативные подходы в собственных проектах.

- [How to Read DataMatrix Barcodes with Aspose.BarCode for .NET](/barcode/english/net/datamatrix-barcode-reading/)
- [How to Create Barcode – Compact PDF417 with Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [How to create barcode quiet zone for Code 16K using Aspose.BarCode for .NET](/barcode/english/net/code-16k-encoding/code-16k-quiet-zone-settings/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}