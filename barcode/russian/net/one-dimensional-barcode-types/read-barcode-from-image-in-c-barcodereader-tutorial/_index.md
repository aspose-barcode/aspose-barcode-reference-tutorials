---
category: general
date: 2026-08-15
description: Считайте штрих‑код с изображения в C# с помощью BarCodeReader. Узнайте,
  как считывать несколько штрих‑кодов в C#, как считывать штрих‑код PDF417, и посмотрите
  полный пример BarCodeReader на C#.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- read barcode from image
- read multiple barcodes c#
- how to read pdf417 barcode
- c# barcodereader example
language: ru
lastmod: 2026-08-15
og_description: Считайте штрих‑код с изображения в C# с пошаговым руководством. Узнайте,
  как считывать несколько штрих‑кодов в C#, декодировать символы PDF417 и запустить
  полноценный пример C# BarCodeReader.
og_image_alt: Screenshot of C# code that reads barcode from image using BarCodeReader
og_title: Чтение штрихкода с изображения в C# – руководство BarCodeReader
schemas:
- author: Aspose
  dateModified: '2026-08-15'
  description: Read barcode from image in C# using BarCodeReader. Learn how to read
    multiple barcodes C#, read PDF417 barcode, and see a full C# BarCodeReader example.
  headline: Read barcode from image in C# – BarCodeReader tutorial
  type: TechArticle
tags:
- barcode
- C#
- .NET
- image processing
title: Считывание штрихкода с изображения в C# – учебник BarCodeReader
url: /ru/net/one-dimensional-barcode-types/read-barcode-from-image-in-c-barcodereader-tutorial/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Считывание штрихкода с изображения в C# – руководство BarCodeReader

Если вам нужно **считать штрихкод с изображения** в приложении .NET, это руководство покажет, как сделать это с помощью класса `BarCodeReader`. Вы также узнаете, как **считать несколько штрихкодов C#**, декодировать символ PDF417 и получите полный **пример C# BarCodeReader**, который можно скопировать в свой проект.

В руководстве рассматривается каждый шаг — от добавления необходимого пакета NuGet до вывода расширенных полей PDF417 — чтобы в итоге получить готовую к запуску консольную программу. Внешняя документация не требуется; весь код и пояснения включены.

## Что понадобится

Прежде чем начать, убедитесь, что у вас есть:

* .NET 6.0 SDK или новее (код работает с .NET Core и .NET Framework)
* Visual Studio 2022 или любой редактор, поддерживающий C#
* Пакет NuGet `Aspose.BarCode` (или эквивалентная библиотека, предоставляющая `BarCodeReader`)
* Файл изображения, содержащий штрихкод Macro PDF417 (например, `ExtPDF417Meta.png`)

Наличие этих предварительных условий гарантирует, что пример скомпилируется без дополнительной настройки.

## Считывание штрихкода с изображения с помощью BarCodeReader

Первый шаг — создать экземпляр `BarCodeReader`, указывающий на файл изображения и сообщающий библиотеке, какой тип штрихкода искать.

```csharp
using System;
using Aspose.BarCode;               // Namespace for BarCodeReader
using Aspose.BarCode.BarCodeRecognition; // DecodeType enum

class Program
{
    static void Main()
    {
        // Path to the image that holds the Macro PDF417 barcode
        const string imagePath = @"YOUR_DIRECTORY/ExtPDF417Meta.png";

        // Initialize the reader for Macro PDF417 barcodes only
        using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
        {
            // Read all barcodes present in the image
            foreach (BarCodeResult result in reader.ReadBarCodes())
            {
                // Basic barcode information
                Console.WriteLine($"Code Type : {result.CodeTypeName}");
                Console.WriteLine($"Code Text : {result.CodeText}");

                // Extended Macro PDF417 fields (available only for this type)
                Console.WriteLine($"File ID          : {result.Extended.Pdf417.MacroPdf417FileID}");
                Console.WriteLine($"Segment ID       : {result.Extended.Pdf417.MacroPdf417SegmentID}");
                Console.WriteLine($"Segments Count   : {result.Extended.Pdf417.MacroPdf417SegmentsCount}");
                Console.WriteLine($"File Name        : {result.Extended.Pdf417.MacroPdf417FileName}");
                Console.WriteLine($"Checksum         : {result.Extended.Pdf417.MacroPdf417Checksum}");
                Console.WriteLine($"File Size        : {result.Extended.Pdf417.MacroPdf417FileSize}");
                Console.WriteLine($"Time Stamp       : {result.Extended.Pdf417.MacroPdf417TimeStamp}");
                Console.WriteLine($"Addressee        : {result.Extended.Pdf417.MacroPdf417Addressee}");
                Console.WriteLine($"Sender           : {result.Extended.Pdf417.MacroPdf417Sender}");
                Console.WriteLine($"Terminator Flag  : {result.Extended.Pdf417.MacroPdf417Terminator}");
                Console.WriteLine(new string('-', 40));
            }
        }
    }
}
```

**Почему это работает:**  
`BarCodeReader` открывает изображение, сканирует его в поисках указанного `DecodeType` и возвращает коллекцию объектов `BarCodeResult`. Каждый результат содержит общие данные штрихкода (`CodeTypeName`, `CodeText`) и, для Macro PDF417, объект `Extended.Pdf417`, который раскрывает все дополнительные поля, определённые стандартом.

## Считывание нескольких штрихкодов C# на одном изображении

Иногда изображение содержит более одного штрихкода (например, QR‑код рядом с PDF417). Чтобы обработать такой случай, просто опустите явное указание `DecodeType` или передайте `DecodeType.AllSupported` и пройдитесь по результатам в цикле.

```csharp
using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.AllSupported))
{
    foreach (BarCodeResult result in reader.ReadBarCodes())
    {
        Console.WriteLine($"Found {result.CodeTypeName}: {result.CodeText}");
    }
}
```

**Зачем это нужно:**  
Указание `AllSupported` заставляет движок попытаться распознать каждый известный ему формат штрихкода, что гарантирует захват всех символов на изображении. Этот подход рекомендуется, когда типы штрихкодов заранее неизвестны.

## Как считать штрихкод PDF417 с помощью C#

Если вам нужен только классический PDF417 (не‑macro), измените `DecodeType` на `Pdf417`. Остальная часть кода остаётся той же, за исключением того, что расширенные поля недоступны.

```csharp
using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.Pdf417))
{
    foreach (BarCodeResult result in reader.ReadBarCodes())
    {
        Console.WriteLine($"PDF417 text: {result.CodeText}");
    }
}
```

**Почему это важно:**  
Классический PDF417 не раскрывает свойства, специфичные для macro, поэтому блок `Extended.Pdf417` не нужен. Точное указание `DecodeType` также ускоряет сканирование, поскольку библиотека пропускает неподдерживаемые алгоритмы.

## Полный пример C# BarCodeReader, который можно скопировать

Ниже представлена полная программа, объединяющая три сценария в одном простом консольном приложении. Замените `YOUR_DIRECTORY/ExtPDF417Meta.png` реальным путём к вашему изображению.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

class Program
{
    static void Main()
    {
        const string imagePath = @"YOUR_DIRECTORY/ExtPDF417Meta.png";

        // 1️⃣ Read Macro PDF417 and show extended fields
        Console.WriteLine("=== Macro PDF417 ===");
        ReadMacroPdf417(imagePath);

        // 2️⃣ Read any barcode type present (multiple barcodes)
        Console.WriteLine("\n=== All supported barcodes ===");
        ReadAllBarcodes(imagePath);

        // 3️⃣ Read classic PDF417 only
        Console.WriteLine("\n=== Classic PDF417 ===");
        ReadClassicPdf417(imagePath);
    }

    static void ReadMacroPdf417(string path)
    {
        using (BarCodeReader reader = new BarCodeReader(path, DecodeType.MacroPdf417))
        {
            foreach (BarCodeResult result in reader.ReadBarCodes())
            {
                Console.WriteLine($"Code Type : {result.CodeTypeName}");
                Console.WriteLine($"Code Text : {result.CodeText}");
                Console.WriteLine($"File ID   : {result.Extended.Pdf417.MacroPdf417FileID}");
                // ... other extended fields omitted for brevity
                Console.WriteLine(new string('-', 30));
            }
        }
    }

    static void ReadAllBarcodes(string path)
    {
        using (BarCodeReader reader = new BarCodeReader(path, DecodeType.AllSupported))
        {
            foreach (BarCodeResult result in reader.ReadBarCodes())
            {
                Console.WriteLine($"{result.CodeTypeName}: {result.CodeText}");
            }
        }
    }

    static void ReadClassicPdf417(string path)
    {
        using (BarCodeReader reader = new BarCodeReader(path, DecodeType.Pdf417))
        {
            foreach (BarCodeResult result in reader.ReadBarCodes())
            {
                Console.WriteLine($"PDF417 text: {result.CodeText}");
            }
        }
    }
}
```

### Ожидаемый вывод

Если образец изображения содержит штрихкод Macro PDF417, консоль выведет что‑то вроде:

```
=== Macro PDF417 ===
Code Type : MacroPdf417
Code Text : 1234567890
File ID   : 5
Segment ID       : 2
Segments Count   : 3
File Name        : report.pdf
Checksum         : 0x1A2B
File Size        : 84212
Time Stamp       : 2024-03-15T10:22:31Z
Addressee        : John Doe
Sender           : Acme Corp
Terminator Flag  : True
------------------------------

=== All supported barcodes ===
MacroPdf417: 1234567890
QrCode: https://example.com

=== Classic PDF417 ===
PDF417 text: 0987654321
```

Если изображение содержит только обычный PDF417, раздел «Macro PDF417» будет пустым, а раздел «Classic PDF417» покажет декодированный текст.

## Заключение

Теперь вы знаете, как **считать штрихкод с изображения** в C# с помощью `BarCodeReader`, как **считать несколько штрихкодов C#** в одном файле и какие шаги нужны для **считывания штрихкода PDF417** — как макро, так и классической версии. Полный **пример C# BarCodeReader** готов к вставке в любой .NET‑проект, и вы можете расширять его для поддержки других форматов или интегрировать в более крупный конвейер обработки изображений.

**Следующие шаги**

* Изучите шаблоны обработки ошибок, такие как `try / catch`, вокруг блока чтения.  
* Поэкспериментируйте с объектом `ReaderParameters` для настройки скорости и точности обнаружения.  
* Объедините чтение штрихкодов с библиотеками предварительной обработки изображений (

## Что следует изучить дальше?


Следующие руководства охватывают тесно связанные темы, построенные на техниках, продемонстрированных в этом руководстве. Каждый ресурс включает полностью работающие примеры кода с пошаговыми объяснениями, чтобы помочь вам освоить дополнительные возможности API и исследовать альтернативные подходы реализации в своих проектах.

- [Как считывать DataMatrix штрихкоды с Aspose.BarCode для .NET](/barcode/english/net/datamatrix-barcode-reading/)
- [Считывание DataMatrix штрихкода C# – режим генерации DataMatrix (Auto)](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-auto/)
- [Считывание штрихкода с изображения – мастерство извлечения области штрихкода в Java с Aspose.BarCode](/barcode/english/java/advanced-settings-and-optimization/extracting-barcode-region-information/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}