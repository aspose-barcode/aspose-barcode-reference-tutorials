---
category: general
date: 2026-09-22
description: Узнайте, как считывать штрихкоды PDF417 в C# с полным примером считывателя
  штрихкодов. Этот учебник покажет, как быстро и надёжно считывать изображение штрихкода
  в C#.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to read pdf417
- read barcode image c#
- c# barcode reader example
language: ru
lastmod: 2026-09-22
og_description: Как считывать штрихкоды PDF417 в C# с помощью краткого примера считывателя
  штрихкодов. Следуйте руководству, чтобы декодировать изображения Macro PDF417 и
  извлекать метаданные.
og_image_alt: Screenshot of C# code that reads a PDF417 barcode and prints its metadata
og_title: Как читать штрихкоды PDF417 в C# – полный пример считывателя штрихкодов
schemas:
- author: Aspose
  dateModified: '2026-09-22'
  description: Learn how to read PDF417 barcodes in C# with a full barcode reader
    example. This tutorial shows you how to read barcode image C# quickly and reliably.
  headline: How to read PDF417 barcodes in C# – complete step‑by‑step guide
  type: TechArticle
- description: Learn how to read PDF417 barcodes in C# with a full barcode reader
    example. This tutorial shows you how to read barcode image C# quickly and reliably.
  name: How to read PDF417 barcodes in C# – complete step‑by‑step guide
  steps:
  - name: Why each step matters
    text: '1. **Creating the reader with `DecodeType.MacroPdf417`** – Macro PDF417
      is a special variant that can carry file‑level metadata. Specifying the decode
      type ensures the SDK parses those extra fields instead of treating the code
      as a plain PDF417. 2. **Iterating over `ReadBarCodes()`** – An image can '
  - name: Reading a non‑macro PDF417 barcode
    text: If your source images contain regular PDF417 codes (no macro metadata),
      replace `DecodeType.MacroPdf417` with `DecodeType.Pdf417`. The rest of the code
      stays identical, but the `Extended.Pdf417` block will be empty because those
      fields simply don’t exist.
  - name: Handling multi‑segment PDFs
    text: 'Macro PDF417 can split a large document across several barcode segments.
      To reassemble the original file you must:'
  - name: Dealing with corrupted images
    text: '- **Low contrast** – Increase image preprocessing (e.g., histogram equalization)
      before passing it to `BarCodeReader`. - **Rotation** – Use `barcodeReader.SetRotateAngle(90)`
      or enable auto‑rotate if the SDK supports it. - **Partial scans** – Ensure the
      image resolution is at least 300 dpi; otherwis'
  - name: Next steps
    text: '- Explore **read barcode image C#** techniques for other symbologies (QR,
      DataMatrix) using the same `BarCodeReader` API. - Integrate the barcode decoder
      into an ASP.NET Core service to process uploads on the fly. - Experiment with
      image preprocessing libraries (e.g., `OpenCvSharp`) to boost success'
  type: HowTo
tags:
- barcode
- pdf417
- c#
title: Как считывать штрихкоды PDF417 в C# – полное пошаговое руководство
url: /ru/net/compact-pdf417-encoding/how-to-read-pdf417-barcodes-in-c-complete-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Как читать штрихкоды PDF417 в C# – полное пошаговое руководство

Если вам нужно **how to read pdf417** в приложении .NET, это руководство покажет точный код и логику, которые вам нужны. К концу первых двух предложений вы узнаете, как читать изображение штрихкода C# с помощью популярного класса `BarCodeReader`, и у вас будет готовый к запуску пример, извлекающий каждый элемент метаданных Macro PDF417.

Чтение штрихкодов PDF417 является распространённым требованием при обработке транспортных этикеток, посадочных талонов или защищённых документов. Этот учебник охватывает всё — от настройки считывателя до обработки крайних случаев, чтобы вы могли интегрировать сканирование штрихкодов с уверенностью.

## Что вы достигнете

- Декодировать изображение Macro PDF417.
- Вывести базовую информацию о штрихкоде (тип и текст).
- Получить доступ ко всем расширенным полям Macro PDF417, таким как ID файла, количество сегментов и метка времени.
- Понять распространённые подводные камни при работе с многосегментными PDF417 кодами.

**Требования**

- .NET 6.0 или новее (код также работает с .NET Framework 4.7+).
- Ссылка на SDK штрихкодов, предоставляющий `BarCodeReader`, `DecodeType` и `BarCodeResult` (например, Aspose.BarCode, Dynamsoft или любую библиотеку с тем же API).
- Файл изображения (`ExtPDF417Meta.png`), содержащий штрихкод Macro PDF417.

> **Pro tip:** Поместите изображение в папку, относительную к корню проекта, и установите для него свойство **Copy to Output Directory** в значение *Copy if newer*, чтобы путь работал во время отладки.

![How to read PDF417 barcode using C#](https://example.com/placeholder-image.png)

## Как читать штрихкод PDF417 в C# – полный код

Ниже представлена автономная программа, которую можно вставить в консольное приложение. Она создаёт считыватель штрихкодов, перебирает каждый декодированный результат и выводит как стандартные, так и расширенные поля Macro PDF417.

```csharp
using System;
using Aspose.BarCode;          // Replace with the namespace of your barcode SDK
using Aspose.BarCode.BarCodeRecognition;

class Program
{
    static void Main()
    {
        // Step 1: Create a barcode reader for a Macro PDF417 image
        // The second argument tells the SDK to look specifically for Macro PDF417 codes.
        using var barcodeReader = new BarCodeReader(
            "YOUR_DIRECTORY/ExtPDF417Meta.png",
            DecodeType.MacroPdf417);

        // Step 2: Decode all barcodes present in the image
        foreach (BarCodeResult result in barcodeReader.ReadBarCodes())
        {
            // Step 3: Display the basic barcode information
            Console.WriteLine($"CodeType: {result.CodeTypeName}");
            Console.WriteLine($"CodeText: {result.CodeText}");

            // Step 4: Output Macro PDF417 specific metadata
            // All properties are available through the Extended.Pdf417 object.
            Console.WriteLine($"Pdf417MacroFileID: {result.Extended.Pdf417.MacroPdf417FileID}");
            Console.WriteLine($"Pdf417MacroSegmentID: {result.Extended.Pdf417.MacroPdf417SegmentID}");
            Console.WriteLine($"Pdf417MacroSegmentsCount: {result.Extended.Pdf417.MacroPdf417SegmentsCount}");
            Console.WriteLine($"Pdf417MacroFileName: {result.Extended.Pdf417.MacroPdf417FileName}");
            Console.WriteLine($"Pdf417MacroChecksum: {result.Extended.Pdf417.MacroPdf417Checksum}");
            Console.WriteLine($"Pdf417MacroFileSize: {result.Extended.Pdf417.MacroPdf417FileSize}");
            Console.WriteLine($"Pdf417MacroTimeStamp: {result.Extended.Pdf417.MacroPdf417TimeStamp}");
            Console.WriteLine($"Pdf417MacroAddressee: {result.Extended.Pdf417.MacroPdf417Addressee}");
            Console.WriteLine($"Pdf417MacroSender: {result.Extended.Pdf417.MacroPdf417Sender}");
            Console.WriteLine($"MacroPdf417Terminator: {result.Extended.Pdf417.MacroPdf417Terminator}");
            Console.WriteLine(new string('-', 40));
        }
    }
}
```

### Почему каждый шаг важен

1. **Создание считывателя с `DecodeType.MacroPdf417`** – Macro PDF417 — специальный вариант, способный переносить метаданные уровня файла. Указание типа декодирования гарантирует, что SDK разберёт эти дополнительные поля, а не будет рассматривать код как обычный PDF417.  
2. **Перебор `ReadBarCodes()`** – На изображении может быть более одного штрихкода (например, QR‑код рядом с PDF417). Цикл гарантирует, что вы захватите каждый результат.  
3. **Вывод `CodeTypeName` и `CodeText`** – Это самые часто используемые свойства; они дают вам название символогии и человекочитаемую полезную нагрузку.  
4. **Доступ к `Extended.Pdf417`** – Объект `Extended` появляется только для типов декодирования, связанных с PDF417. Каждое свойство напрямую соответствует спецификации Macro PDF417, позволяя восстановить оригинальный файл или проверить порядок сегментов.

## Общие варианты и крайние случаи

### Чтение обычного PDF417 штрихкода

Если ваши исходные изображения содержат обычные PDF417 коды (без macro‑метаданных), замените `DecodeType.MacroPdf417` на `DecodeType.Pdf417`. Остальная часть кода остаётся идентичной, но блок `Extended.Pdf417` будет пустым, поскольку такие поля просто не существуют.

### Обработка многосегментных PDF

Macro PDF417 может разбить большой документ на несколько сегментов штрихкода. Чтобы собрать оригинальный файл, необходимо:

1. Собрать `Pdf417MacroSegmentID` каждого сегмента.  
2. Отсортировать сегменты по их ID.  
3. Проверить, что `Pdf417MacroSegmentsCount` соответствует количеству полученных сегментов.  
4. Конкатенировать `CodeText` каждого сегмента в порядке.  
5. При необходимости проверить `Pdf417MacroChecksum`.

Ниже приведён лаконичный фрагмент, демонстрирующий логику сборки:

```csharp
var segments = new SortedDictionary<int, string>();
int expectedCount = 0;

foreach (var result in barcodeReader.ReadBarCodes())
{
    int segId = result.Extended.Pdf417.MacroPdf417SegmentID;
    int segCount = result.Extended.Pdf417.MacroPdf417SegmentsCount;
    expectedCount = segCount;               // will be the same for every segment
    segments[segId] = result.CodeText;       // store payload by segment ID
}

// Verify we have all parts
if (segments.Count == expectedCount)
{
    string fullPayload = string.Concat(segments.Values);
    Console.WriteLine("Reassembled payload:");
    Console.WriteLine(fullPayload);
}
else
{
    Console.WriteLine($"Missing segments: expected {expectedCount}, received {segments.Count}");
}
```

### Работа с повреждёнными изображениями

- **Low contrast** – Увеличьте предобработку изображения (например, выравнивание гистограммы) перед передачей его в `BarCodeReader`.  
- **Rotation** – Используйте `barcodeReader.SetRotateAngle(90)` или включите авто‑поворот, если SDK поддерживает эту функцию.  
- **Partial scans** – Убедитесь, что разрешение изображения не менее 300 dpi; иначе SDK может пропустить небольшие сегменты.

## Пример считывателя штрихкодов c# – лучшие практики

| Практика | Причина |
|----------|--------|
| **Освобождайте читатель с помощью `using`** | Гарантирует своевременное освобождение нативных ресурсов, предотвращая утечки памяти. |
| **Проверяйте, что `result.Extended` не null** | Некоторые SDK возвращают `null` для не‑macro кодов; проверка предотвращает `NullReferenceException`. |
| **Записывайте `Pdf417MacroFileID` в журнал** | Этот идентификатор уникален для каждого файла и полезен для аудита. |
| **Оборачивайте декодирование в try/catch** | Ошибки ввода‑вывода (отсутствующий файл) или неподдерживаемые форматы вызывают исключения, которые следует обрабатывать корректно. |

```csharp
try
{
    // decoding logic here
}
catch (FileNotFoundException ex)
{
    Console.Error.WriteLine($"Image not found: {ex.FileName}");
}
catch (BarCodeException ex)
{
    Console.Error.WriteLine($"Barcode decoding failed: {ex.Message}");
}
```

## Ожидаемый вывод

Запуск полной программы против корректно сформированного `ExtPDF417Meta.png` даёт вывод, похожий на следующий:

```
CodeType: MacroPdf417
CodeText: https://example.com/document.pdf
Pdf417MacroFileID: 12345
Pdf417MacroSegmentID: 1
Pdf417MacroSegmentsCount: 3
Pdf417MacroFileName: document.pdf
Pdf417MacroChecksum: 0x1A2B
Pdf417MacroFileSize: 204800
Pdf417MacroTimeStamp: 2024-08-15T14:32:00Z
Pdf417MacroAddressee: John Doe
Pdf417MacroSender: Acme Corp.
MacroPdf417Terminator: True
----------------------------------------
```

Если изображение содержит несколько сегментов, цикл выведет метаданные каждого сегмента последовательно.

## Заключение

Теперь вы знаете **how to read pdf417** штрихкоды в C# и имеете **c# barcode reader example**, который извлекает каждое поле Macro PDF417. Решение охватывает базовое декодирование, извлечение метаданных, сборку многосегментных файлов и обработку ошибок, предоставляя готовую к продакшену основу для любого рабочего процесса обработки документов.

### Следующие шаги

- Исследуйте техники **read barcode image C#** для других символогий (QR, DataMatrix), используя тот же API `BarCodeReader`.  
- Интегрируйте декодер штрихкодов в сервис ASP.NET Core для обработки загрузок в режиме реального времени.  
- Экспериментируйте с библиотеками предобработки изображений (например, `OpenCvSharp`), чтобы повысить успешность сканирования низкого качества.

Счастливого кодинга, и смело адаптируйте пример под ваш конкретный сценарий!

## Что вам следует изучить дальше?

Следующие учебники охватывают тесно связанные темы, построенные на техниках, продемонстрированных в этом руководстве. Каждый ресурс включает полностью работающие примеры кода с пошаговыми объяснениями, помогая вам освоить дополнительные возможности API и исследовать альтернативные подходы к реализации в собственных проектах.

- [Как сохранить штрихкод в C# – генерировать PDF417 штрихкоды](/barcode/english/net/compact-pdf417-encoding/how-to-save-barcode-in-c-generate-pdf417-barcodes/)
- [Как читать PDF417 в C# – полное пошаговое руководство](/barcode/english/net/compact-pdf417-encoding/how-to-read-pdf417-in-c-complete-step-by-step-guide/)
- [Как установить уровень ошибки в PDF417 штрихкоде – полное руководство](/barcode/english/net/compact-pdf417-encoding/how-to-set-error-level-in-pdf417-barcode-complete-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}