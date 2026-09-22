---
category: general
date: 2026-07-27
description: Как быстро считывать штрих‑код PDF417 в C#. Узнайте, как считывать несколько
  штрих‑кодов, декодировать изображения и получать метаданные Macro PDF417 в полном
  примере штрих‑кода на C#.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to read pdf417
- read multiple barcodes
- c# barcode example
- read barcode image c#
language: ru
lastmod: 2026-07-27
og_description: Как считывать штрих‑код PDF417 в C# с помощью пошагового руководства.
  Декодировать изображения, работать с несколькими штрих‑кодами и извлекать метаданные
  Macro PDF417 в готовом к запуску примере.
og_image_alt: Screenshot showing how to read PDF417 barcode using C# code
og_title: Как считывать PDF417 в C# – Полный пример штрихкода
schemas:
- author: Aspose
  dateModified: '2026-07-27'
  description: How to read PDF417 barcode in C# quickly. Learn to read multiple barcodes,
    decode images, and get Macro PDF417 metadata in a full C# barcode example.
  headline: How to Read PDF417 in C# – Complete Barcode Example
  type: TechArticle
- description: How to read PDF417 barcode in C# quickly. Learn to read multiple barcodes,
    decode images, and get Macro PDF417 metadata in a full C# barcode example.
  name: How to Read PDF417 in C# – Complete Barcode Example
  steps:
  - name: Loads a barcode image from disk.
    text: Loads a barcode image from disk.
  - name: Decodes **PDF417** (including Macro PDF417) barcodes.
    text: Decodes **PDF417** (including Macro PDF417) barcodes.
  - name: Prints basic information such as code type and text.
    text: Prints basic information such as code type and text.
  - name: Outputs the full set of Macro PDF417 fields (file ID, segment ID, checksum,
      etc.).
    text: Outputs the full set of Macro PDF417 fields (file ID, segment ID, checksum,
      etc.).
  type: HowTo
tags:
- barcode
- C#
- PDF417
- image-processing
- Aspose
title: Как читать PDF417 в C# – полный пример штрихкода
url: /ru/net/compact-pdf417-encoding/how-to-read-pdf417-in-c-complete-barcode-example/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Как считывать PDF417 в C# – Полный пример работы со штрих‑кодом

Когда‑то задавались вопросом **как считывать PDF417** штрих‑код в приложении C# без потери волос? Вы не одиноки. Будь то сканер для логистики, проверка билетов или необходимость извлечь данные из PDF417‑закодированного удостоверения, процесс может показаться загадочным в начале.  

В этом руководстве мы пройдём через **c# barcode example**, который читает изображение PDF417, обрабатывает **read multiple barcodes**, если их несколько, и извлекает все полезные метаданные Macro PDF417, которые могут понадобиться.

## Что вы построите

К концу этого руководства у вас будет небольшая консольная программа, которая:

1. Загружает изображение штрих‑кода с диска.  
2. Декодирует **PDF417** (включая Macro PDF417) штрих‑коды.  
3. Выводит базовую информацию, такую как тип кода и текст.  
4. Выводит полный набор полей Macro PDF417 (file ID, segment ID, checksum и т.д.).  

Никаких внешних сервисов, только один NuGet‑пакет и несколько строк C#.

## Предварительные требования – Что нужно перед началом

- **.NET 6.0** или новее (код также работает на .NET Framework 4.6+).  
- Последняя версия библиотеки **Aspose.BarCode for .NET** – установите её через NuGet (`Install-Package Aspose.BarCode`).  
- Файл изображения, содержащий PDF417 штрих‑код (в демо‑примере используется `ExtPDF417Meta.png`).  
- Базовое понимание консольных приложений C# (если вы писали “Hello World”, вам достаточно).  

> **Pro tip:** Если у вас нет готового образца PDF417, сгенерируйте его на сайте демо‑версии Aspose или используйте приложение для смартфона, которое может создавать PDF417‑теги.

## Шаг 1: Создание проекта и установка библиотеки

Сначала создайте новый консольный проект:

```bash
dotnet new console -n Pdf417ReaderDemo
cd Pdf417ReaderDemo
dotnet add package Aspose.BarCode
```

Это подтянет зависимости **c# barcode example**, которые нам нужны. Откройте `Program.cs` и замените стандартный код скелетом ниже:

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

namespace Pdf417ReaderDemo
{
    class Program
    {
        static void Main(string[] args)
        {
            // We'll fill this in in the next steps.
        }
    }
}
```

## Шаг 2: Инициализация считывателя штрих‑кодов для PDF417

Сердце решения – класс `BarCodeReader`. Мы указываем, какой файл сканировать и какой тип штрих‑кода нас интересует — в данном случае `DecodeType.Pdf417` или макровариант `DecodeType.MacroPdf417`. Использование макро‑типа гарантирует захват расширенных полей.

```csharp
// Step 2: Create the reader, targeting Macro PDF417 barcodes
string imagePath = "YOUR_DIRECTORY/ExtPDF417Meta.png";

using (BarCodeReader reader = new BarCodeReader(
           imagePath, DecodeType.MacroPdf417))
{
    // The rest of the logic lives inside this block.
}
```

Почему использовать `MacroPdf417`, а не обычный `Pdf417`? Macro PDF417 несёт дополнительную мета‑информацию (file ID, количество сегментов, метки времени и т.д.), от которой зависят многие реальные приложения — представьте себе грузовые манифесты, разбитые на несколько страниц.

## Шаг 3: Чтение всех штрих‑кодов, найденных на изображении

Одно изображение может содержать **read multiple barcodes** — возможно, QR‑код рядом с PDF417. Метод `ReadBarCodes()` возвращает `IEnumerable<BarCodeResult>`, по которому можно итерировать.

```csharp
// Step 3: Iterate through every barcode detected
foreach (BarCodeResult result in reader.ReadBarCodes())
{
    // Inside we’ll output both generic and macro‑specific data.
}
```

Если на изображении только один PDF417, цикл всё равно выполнится один раз, что делает код гибким для будущих сценариев, когда понадобится **read multiple barcodes** из одного сканирования.

## Шаг 4: Вывод базовой информации о штрих‑коде

Прежде чем погружаться в макро‑поля, полезно показать тип штрих‑кода и декодированный текст. Это поможет убедиться, что считыватель действительно распознал PDF417, а не другую символьную систему.

```csharp
Console.WriteLine($"CodeType : {result.CodeTypeName}");
Console.WriteLine($"CodeText : {result.CodeText}");
```

Свойство `CodeTypeName` вернёт *MacroPdf417* (или *Pdf417*, если флаг макро не установлен), а `CodeText` содержит необработанные данные, закодированные в штрих‑коде.

## Шаг 5: Извлечение метаданных Macro PDF417

Свойство `Extended` даёт глубокий доступ к структуре, специфичной для PDF417. Каждый выводимый ниже параметр напрямую соответствует спецификации макро‑PDF417.

```csharp
// Step 5: Macro PDF417 metadata – all optional, but very handy
Console.WriteLine($"Pdf417MacroFileID          : {result.Extended.Pdf417.MacroPdf417FileID}");
Console.WriteLine($"Pdf417MacroSegmentID       : {result.Extended.Pdf417.MacroPdf417SegmentID}");
Console.WriteLine($"Pdf417MacroSegmentsCount   : {result.Extended.Pdf417.MacroPdf417SegmentsCount}");
Console.WriteLine($"Pdf417MacroFileName        : {result.Extended.Pdf417.MacroPdf417FileName}");
Console.WriteLine($"Pdf417MacroChecksum        : {result.Extended.Pdf417.MacroPdf417Checksum}");
Console.WriteLine($"Pdf417MacroFileSize        : {result.Extended.Pdf417.MacroPdf417FileSize}");
Console.WriteLine($"Pdf417MacroTimeStamp       : {result.Extended.Pdf417.MacroPdf417TimeStamp}");
Console.WriteLine($"Pdf417MacroAddressee       : {result.Extended.Pdf417.MacroPdf417Addressee}");
Console.WriteLine($"Pdf417MacroSender          : {result.Extended.Pdf417.MacroPdf417Sender}");
Console.WriteLine($"MacroPdf417Terminator      : {result.Extended.Pdf417.MacroPdf417Terminator}");
```

Каждая строка извлекает отдельный элемент макро‑полезной нагрузки:

- **FileID** – уникальный идентификатор всего набора документов.  
- **SegmentID** – номер текущего сегмента в многосегментном файле.  
- **SegmentsCount** – общее ожидаемое количество сегментов.  
- **FileName, Checksum, FileSize** – полезно для проверки целостности передаваемого файла.  
- **TimeStamp, Addressee, Sender** – необязательные поля, которые многие логистические системы включают.  

Если какое‑то из этих полей отсутствует в исходном штрих‑коде, библиотека вернёт `null` или `0`, и вы сможете обработать это по своему усмотрению.

## Шаг 6: Запуск полного примера

Объединив всё вместе, получаем полностью готовую к запуску программу:

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

namespace Pdf417ReaderDemo
{
    class Program
    {
        static void Main(string[] args)
        {
            // Path to the image containing a Macro PDF417 barcode
            string imagePath = "YOUR_DIRECTORY/ExtPDF417Meta.png";

            // Initialize the reader for Macro PDF417 (covers both standard and macro)
            using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
            {
                // Loop through every barcode detected – handles read multiple barcodes gracefully
                foreach (BarCodeResult result in reader.ReadBarCodes())
                {
                    // Basic info
                    Console.WriteLine($"CodeType : {result.CodeTypeName}");
                    Console.WriteLine($"CodeText : {result.CodeText}");

                    // Macro PDF417 specific metadata
                    Console.WriteLine($"Pdf417MacroFileID          : {result.Extended.Pdf417.MacroPdf417FileID}");
                    Console.WriteLine($"Pdf417MacroSegmentID       : {result.Extended.Pdf417.MacroPdf417SegmentID}");
                    Console.WriteLine($"Pdf417MacroSegmentsCount   : {result.Extended.Pdf417.MacroPdf417SegmentsCount}");
                    Console.WriteLine($"Pdf417MacroFileName        : {result.Extended.Pdf417.MacroPdf417FileName}");
                    Console.WriteLine($"Pdf417MacroChecksum        : {result.Extended.Pdf417.MacroPdf417Checksum}");
                    Console.WriteLine($"Pdf417MacroFileSize        : {result.Extended.Pdf417.MacroPdf417FileSize}");
                    Console.WriteLine($"Pdf417MacroTimeStamp       : {result.Extended.Pdf417.MacroPdf417TimeStamp}");
                    Console.WriteLine($"Pdf417MacroAddressee       : {result.Extended.Pdf417.MacroPdf417Addressee}");
                    Console.WriteLine($"Pdf417MacroSender          : {result.Extended.Pdf417.MacroPdf417Sender}");
                    Console.WriteLine($"MacroPdf417Terminator      : {result.Extended.Pdf417.MacroPdf417Terminator}");
                    Console.WriteLine(new string('-', 40));
                }
            }

            Console.WriteLine("Decoding complete. Press any key to exit.");
            Console.ReadKey();
        }
    }
}
```

### Ожидаемый вывод

При запуске программы с корректным файлом `ExtPDF417Meta.png` вы должны увидеть нечто похожее на:

```
CodeType : MacroPdf417
CodeText : https://example.com/track?order=12345
Pdf417MacroFileID          : 101
Pdf417MacroSegmentID       : 1
Pdf417MacroSegmentsCount   : 3
Pdf417MacroFileName        : order_manifest.pdf
Pdf417MacroChecksum        : 0x1A2B3C4D
Pdf417MacroFileSize        : 45296
Pdf417MacroTimeStamp       : 2024-03-15T10:27:00Z
Pdf417MacroAddressee       : LogisticsDept
Pdf417MacroSender          : WarehouseA
MacroPdf417Terminator      : true
----------------------------------------
Decoding complete. Press any key to exit.
```

Если изображение содержит более одного штрих‑кода,


## Что изучать дальше?


Следующие руководства охватывают тесно связанные темы, которые развивают техники, продемонстрированные в этом руководстве. Каждый ресурс включает полностью работающие примеры кода с пошаговыми объяснениями, чтобы помочь вам освоить дополнительные возможности API и исследовать альтернативные подходы реализации в собственных проектах.

- [How to Generate PDF417 Barcodes – Compact PDF417 Encoding](/barcode/english/net/compact-pdf417-encoding/)
- [How to Create Barcode – Compact PDF417 with Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [How to Read DataMatrix Barcodes with Aspose.BarCode for .NET](/barcode/english/net/datamatrix-barcode-reading/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}