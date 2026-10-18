---
category: general
date: 2026-10-18
description: Узнайте, как считывать штрих‑код с изображения в C# с помощью Aspose.BarCode,
  включая извлечение метаданных Macro PDF417 и полный пример кода.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to read barcode from image
- C# barcode reader
- Macro PDF417 metadata
- BarCodeReader class
- DecodeType.MacroPdf417
- barcode metadata extraction
language: ru
lastmod: 2026-10-18
og_description: Как считать штрих‑код с изображения с помощью C# Aspose.BarCode. Следуйте
  этому пошаговому руководству, чтобы извлечь метаданные Macro PDF417 и решить распространённые
  задачи.
og_image_alt: Screenshot showing output of how to read barcode from image with C#
  Aspose.BarCode
og_title: Как считать штрих‑код с изображения в C# — полное руководство Aspose.BarCode
schemas:
- author: Aspose
  dateModified: '2026-10-18'
  description: Learn how to read barcode from image in C# with Aspose.BarCode, covering
    Macro PDF417 metadata extraction and complete sample code.
  headline: How to read barcode from image in C# using Aspose.BarCode
  type: TechArticle
- description: Learn how to read barcode from image in C# with Aspose.BarCode, covering
    Macro PDF417 metadata extraction and complete sample code.
  name: How to read barcode from image in C# using Aspose.BarCode
  steps:
  - name: Expected console output
    text: '``` CodeType: MacroPdf417 CodeText: https://example.com/document.pdf MacroFileID:
      12345 MacroSegmentID: 1 MacroSegmentsCount: 3 MacroFileName: document.pdf MacroChecksum:
      0x1A2B3C4D MacroFileSize: 204800 MacroTimeStamp: 2023-07-15T10:23:45Z MacroAddressee:
      Acme Corp MacroSender: Warehouse 7 MacroTer'
  - name: Large images
    text: 'Reading very large images can consume significant memory. Use the `BarcodeReader`
      overload that accepts `ReaderParameters` to limit the maximum image size:'
  - name: Missing or corrupted metadata
    text: If any of the Macro fields are missing, the corresponding property returns
      `null` or `0`. Log these cases and decide whether to treat the barcode as incomplete.
  - name: Multiple barcode types in one image
    text: 'If an image may contain other barcode formats, you can pass an array of
      `DecodeType` values:'
  type: HowTo
tags:
- barcode
- C#
- Aspose.BarCode
title: Как считать штрих‑код с изображения в C# с помощью Aspose.BarCode
url: /ru/net/one-dimensional-barcode-types/how-to-read-barcode-from-image-in-c-using-aspose-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Как считать штрих‑код с изображения в C# с использованием Aspose.BarCode

Если вам нужно **как считать штрих‑код с изображения** в приложении .NET, это руководство показывает точные шаги с Aspose.BarCode. Независимо от того, обрабатываете ли вы отсканированные документы, чеки или бирки инвентаря, вы увидите, как считать штрих‑код, извлечь метаданные Macro PDF417 и обработать типичные граничные случаи.

Считывание штрих‑кода с изображения — рутинная задача, но извлечение расширенных полей Macro PDF417 добавляет уровень сложности. Этот учебник охватывает полный рабочий процесс, от настройки проекта до полностью готового примера, чтобы вы могли скопировать‑вставить код и увидеть мгновенный результат.

## Что вы узнаете

- Как настроить Aspose.BarCode для проектов C#.  
- Правильный способ создания **C# barcode reader** для изображения Macro PDF417.  
- Как перебрать каждый обнаруженный штрих‑код и вывести базовую информацию.  
- Как получить доступ к **Macro PDF417 metadata** таким как file ID, segment ID и checksum.  
- Советы по обработке отсутствующих метаданных, больших изображений и распространённых ошибок декодирования.  

**Prerequisites**

- .NET 6.0 (или новее) установлен.  
- Базовое знакомство с C# и Visual Studio (подойдёт любой IDE).  
- Файл изображения, содержащий штрих‑код Macro PDF417 (например, `ExtPDF417Meta.png`).  

## Шаг 1: Установите Aspose.BarCode

Откройте терминал в папке проекта и выполните:

```bash
dotnet add package Aspose.BarCode
```

Пакет включает класс **BarCodeReader**, который реализует функциональность **C# barcode reader**, необходимую для этого руководства.

## Шаг 2: Настройте среду разработки

Создайте новое консольное приложение, если у вас его ещё нет:

```bash
dotnet new console -n BarcodeDemo
cd BarcodeDemo
```

Добавьте директивы `using` в начало `Program.cs`:

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;
```

Эти пространства имён предоставляют класс **BarCodeReader** и перечисление `DecodeType`, требуемые для декодирования Macro PDF417.

## Шаг 3: Инициализируйте BarCodeReader для Macro PDF417

Суть **как считать штрих‑код с изображения** — создать экземпляр `BarCodeReader`, указывающий конкретный `DecodeType`. Для Macro PDF417 необходимо передать `DecodeType.MacroPdf417`:

```csharp
// Step 3: Create a barcode reader for a Macro PDF417 image
using (BarCodeReader reader = new BarCodeReader(
           "YOUR_DIRECTORY/ExtPDF417Meta.png", DecodeType.MacroPdf417))
{
    // The reader is now ready to scan the image.
}
```

**Почему это важно:**  
Выбор `DecodeType.MacroPdf417` сообщает библиотеке искать расширенный формат Macro PDF417, который содержит дополнительные поля помимо базовых данных штрих‑кода. Если использовать общий `DecodeType.Pdf417`, эти дополнительные поля будут проигнорированы.

## Шаг 4: Переберите обнаруженные штрих‑коды

Одно изображение может содержать несколько штрих‑кодов. Метод `ReadBarCodes()` возвращает перечисляемую коллекцию объектов `BarCodeResult`. Пройдитесь по ней, чтобы вывести базовую информацию о каждом штрих‑коде:

```csharp
foreach (BarCodeResult result in reader.ReadBarCodes())
{
    Console.WriteLine($"CodeType: {result.CodeTypeName}");
    Console.WriteLine($"CodeText: {result.CodeText}");
}
```

Свойство `CodeTypeName` сообщает точную символьную систему штрих‑кода (например, “MacroPdf417”), а `CodeText` содержит декодированную строку.

## Шаг 5: Извлеките и отобразите метаданные Macro PDF417

Когда штрих‑код является Macro PDF417, свойство `Extended.Pdf417` предоставляет набор полей метаданных. Доступ к ним осуществляется напрямую, как показано ниже:

```csharp
Console.WriteLine($"MacroFileID: {result.Extended.Pdf417.MacroPdf417FileID}");
Console.WriteLine($"MacroSegmentID: {result.Extended.Pdf417.MacroPdf417SegmentID}");
Console.WriteLine($"MacroSegmentsCount: {result.Extended.Pdf417.MacroPdf417SegmentsCount}");
Console.WriteLine($"MacroFileName: {result.Extended.Pdf417.MacroPdf417FileName}");
Console.WriteLine($"MacroChecksum: {result.Extended.Pdf417.MacroPdf417Checksum}");
Console.WriteLine($"MacroFileSize: {result.Extended.Pdf417.MacroPdf417FileSize}");
Console.WriteLine($"MacroTimeStamp: {result.Extended.Pdf417.MacroPdf417TimeStamp}");
Console.WriteLine($"MacroAddressee: {result.Extended.Pdf417.MacroPdf417Addressee}");
Console.WriteLine($"MacroSender: {result.Extended.Pdf417.MacroPdf417Sender}");
Console.WriteLine($"MacroTerminator: {result.Extended.Pdf417.MacroPdf417Terminator}");
```

Эти поля дают всё необходимое для восстановления оригинального много‑сегментного файла, проверки целостности и связывания штрих‑кода с конкретным документом или отправителем.

### Ожидаемый вывод в консоль

```
CodeType: MacroPdf417
CodeText: https://example.com/document.pdf
MacroFileID: 12345
MacroSegmentID: 1
MacroSegmentsCount: 3
MacroFileName: document.pdf
MacroChecksum: 0x1A2B3C4D
MacroFileSize: 204800
MacroTimeStamp: 2023-07-15T10:23:45Z
MacroAddressee: Acme Corp
MacroSender: Warehouse 7
MacroTerminator: END
```

Если изображение не содержит штрих‑код Macro PDF417, объект `Extended.Pdf417` будет `null`. Защищайте код от этого, чтобы избежать `NullReferenceException`:

```csharp
if (result.Extended?.Pdf417 != null)
{
    // Safe to read metadata
}
else
{
    Console.WriteLine("No Macro PDF417 metadata found.");
}
```

## Шаг 6: Обработка распространённых ошибок и граничных случаев

### Большие изображения

Считывание очень больших изображений может потреблять значительный объём памяти. Используйте перегрузку `BarcodeReader`, принимающую `ReaderParameters`, чтобы ограничить максимальный размер изображения:

```csharp
ReaderParameters parameters = new ReaderParameters
{
    MaxImageSize = 4096 // pixels
};

using (BarCodeReader reader = new BarCodeReader(
           "large_image.png", DecodeType.MacroPdf417, parameters))
{
    // Process as before
}
```

### Отсутствующие или повреждённые метаданные

Если какие‑то поля Macro отсутствуют, соответствующее свойство возвращает `null` или `0`. Записывайте такие случаи в журнал и решайте, считать ли штрих‑код неполным.

### Несколько типов штрих‑кодов на одном изображении

Если изображение может содержать другие форматы штрих‑кодов, можно передать массив значений `DecodeType`:

```csharp
DecodeType[] types = { DecodeType.MacroPdf417, DecodeType.QR, DecodeType.Code128 };
using (BarCodeReader reader = new BarCodeReader("mixed.png", types))
{
    // Iterate as before
}
```

Такой подход сохраняет гибкость логики **как считать штрих‑код с изображения** без потери производительности.

## Шаг 7: Полный исходный код

Ниже приведена полная, готовая к запуску программа. Замените `YOUR_DIRECTORY/ExtPDF417Meta.png` на путь к вашему изображению.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

namespace BarcodeDemo
{
    class Program
    {
        static void Main(string[] args)
        {
            // Path to the image containing a Macro PDF417 barcode
            const string imagePath = "YOUR_DIRECTORY/ExtPDF417Meta.png";

            // Initialize the C# barcode reader for Macro PDF417
            using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
            {
                // Iterate over all detected barcodes
                foreach (BarCodeResult result in reader.ReadBarCodes())
                {
                    Console.WriteLine($"CodeType: {result.CodeTypeName}");
                    Console.WriteLine($"CodeText: {result.CodeText}");

                    // Safely access Macro PDF417 metadata
                    if (result.Extended?.Pdf417 != null)
                    {
                        Console.WriteLine($"MacroFileID: {result.Extended.Pdf417.MacroPdf417FileID}");
                        Console.WriteLine($"MacroSegmentID: {result.Extended.Pdf417.MacroPdf417SegmentID}");
                        Console.WriteLine($"MacroSegmentsCount: {result.Extended.Pdf417.MacroPdf417SegmentsCount}");
                        Console.WriteLine($"MacroFileName: {result.Extended.Pdf417.MacroPdf417FileName}");
                        Console.WriteLine($"MacroChecksum: {result.Extended.Pdf417.MacroPdf417Checksum}");
                        Console.WriteLine($"MacroFileSize: {result.Extended.Pdf417.MacroPdf417FileSize}");
                        Console.WriteLine($"MacroTimeStamp: {result.Extended.Pdf417.MacroPdf417TimeStamp}");
                        Console.WriteLine($"MacroAddressee: {result.Extended.Pdf417.MacroPdf417Addressee}");
                        Console.WriteLine($"MacroSender: {result.Extended.Pdf417.MacroPdf417Sender}");
                        Console.WriteLine($"MacroTerminator: {result.Extended.Pdf417.MacroPdf417Terminator}");
                    }
                    else
                    {
                        Console.WriteLine("No Macro PDF417 metadata found for this barcode.");
                    }

                    Console.WriteLine(new string('-', 40));
                }
            }

            Console.WriteLine("Barcode processing completed.");
        }
    }
}
```

Запустите программу командой:

```bash
dotnet run
```

Вы должны увидеть тип штрих‑кода, декодированный текст и все доступные поля Macro PDF417, выведенные в консоль.

## Заключение

В этом руководстве вы узнали **как считать штрих‑код с изображения** с помощью Aspose.BarCode для C#. Руководство охватило настройку **C# barcode reader**,

## Что изучать дальше?

Следующие учебники охватывают тесно связанные темы, расширяющие техники, продемонстрированные в этом руководстве. Каждый ресурс включает полностью работающие примеры кода с пошаговыми объяснениями, чтобы помочь вам освоить дополнительные возможности API и исследовать альтернативные подходы реализации в собственных проектах.

- [Считать штрих‑код с изображения C# – полное руководство с Macro PDF417](/barcode/english/net/compact-pdf417-encoding/read-barcode-from-image-c-complete-guide-with-macro-pdf417/)
- [Как создать штрих‑код macro PDF417 в C# с использованием Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/how-to-create-macro-pdf417-barcode-in-c-using-aspose-barcode/)
- [Как считать PDF417 штрих‑код в C# – полное пошаговое руководство](/barcode/english/net/compact-pdf417-encoding/how-to-read-pdf417-in-c-complete-step-by-step-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}