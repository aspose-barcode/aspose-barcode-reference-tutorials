---
category: general
date: 2026-10-24
description: Узнайте, как считывать штрих‑код PDF417 в C# с помощью Aspose.BarCode.
  В этом руководстве рассматривается чтение изображения штрих‑кода, извлечение полей
  Macro PDF417 и обработка типичных сценариев.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to read pdf417 barcode
- read barcode image c#
- read barcode with aspose
language: ru
lastmod: 2026-10-24
og_description: Как считывать штрих‑код PDF417 в C# с помощью Aspose.BarCode. Следуйте
  этому полному руководству, чтобы декодировать изображения, получать метаданные Macro
  PDF417 и избегать распространённых ошибок.
og_image_alt: Screenshot showing how to read PDF417 barcode results in a C# console
  application
og_title: Как считать штрих‑код PDF417 в C# с помощью Aspose – полное руководство
schemas:
- author: Aspose
  dateModified: '2026-10-24'
  description: Learn how to read PDF417 barcode in C# using Aspose.BarCode. This tutorial
    covers reading a barcode image, extracting Macro PDF417 fields, and handling common
    scenarios.
  headline: How to read PDF417 barcode in C# with Aspose – step‑by‑step guide
  type: TechArticle
- description: Learn how to read PDF417 barcode in C# using Aspose.BarCode. This tutorial
    covers reading a barcode image, extracting Macro PDF417 fields, and handling common
    scenarios.
  name: How to read PDF417 barcode in C# with Aspose – step‑by‑step guide
  steps:
  - name: Why use `DecodeType.MacroPdf417`?
    text: '* **Macro PDF417** stores additional fields (file ID, segment count, timestamps,
      etc.) that are not present in standard PDF417. * The `Extended` property of
      `BarCodeResult` is populated only when you request the macro type, saving you
      a separate parsing step.'
  - name: What each property means
    text: '| Property | Description | |----------|-------------| | **MacroPdf417FileID**
      | Unique identifier for the whole multi‑segment document. | | **MacroPdf417SegmentID**
      | Index of the current segment (starting at 0). | | **MacroPdf417SegmentsCount**
      | Total number of segments that belong to the file. | '
  - name: Missing macro fields
    text: 'Sometimes a PDF417 barcode is generated without the optional macro fields.
      Accessing a missing property returns `null` or `0`. Guard against this if you
      plan to store the values:'
  - name: Corrupted or low‑quality images
    text: 'If the image is blurry, you can improve detection by enabling the `BarCodeReader`
      quality options:'
  - name: Multiple barcode formats in one image
    text: 'If you suspect other barcode types might be present, use `DecodeType.AllSupported`
      and filter results:'
  type: HowTo
- questions:
  - answer: Yes. Change `DecodeType.MacroPdf417` to `DecodeType.Pdf417`. The `Extended`
      property will be empty, but `CodeText` and `CodeTypeName` remain available.
    question: Can I read a standard PDF417 (non‑macro) with the same code?
  - answer: Absolutely. Use the overload `new BarCodeReader(Stream, DecodeType)` and
      pass a `FileStream` or `MemoryStream`. This is useful when the image comes from
      a web API.
    question: Does Aspose.BarCode support reading from a stream instead of a file
      path?
  - answer: 'The `MacroPdf417Checksum` field contains the raw CRC‑16 value. You can
      recompute the checksum on the reconstructed file and compare it to ensure data
      integrity. ## Next steps and related topics * **Write PDF417 barcodes** – explore
      `BarCodeGenerator` to create macro barcodes for testing. * **Combine'
    question: How do I validate the checksum?
  type: FAQPage
tags:
- barcode
- Aspose.BarCode
- C#
title: Как считать штрих‑код PDF417 в C# с помощью Aspose – пошаговое руководство
url: /ru/net/compact-pdf417-encoding/how-to-read-pdf417-barcode-in-c-with-aspose-step-by-step-gui/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Как считать штрих‑код PDF417 в C# с помощью Aspose – пошаговое руководство

Если вам нужно **как считать PDF417 штрих‑код** в приложении .NET, это руководство покажет, как именно считывать PDF417 штрих‑код в C# с использованием библиотеки Aspose.BarCode. Независимо от того, обрабатываете ли вы отсканированные документы, мобильные захваты или пакетно импортированные изображения, приведённый ниже код декодирует штрих‑код и извлекает каждое свойство Macro PDF417, которое может вам понадобиться.

Чтение изображения штрих‑кода в C# может показаться сложным, особенно когда штрих‑код содержит расширенные метаданные. Этот учебник устраняет догадки, предоставляя полностью готовый к запуску пример, объясняя каждую строку и охватывая крайние случаи, такие как отсутствие макросегментов или повреждённые изображения. К концу вы сможете уверенно интегрировать декодирование PDF417 в любой проект на C#.

## Требования

Прежде чем начать, убедитесь, что у вас есть:

* .NET 6.0 SDK или более поздняя версия  
* Visual Studio 2022 (или любая IDE, поддерживающая .NET)  
* Лицензия или бесплатная оценочная версия **Aspose.BarCode for .NET** – временный ключ можно получить на сайте Aspose  
* Файл изображения, содержащий Macro PDF417 штрих‑код (например, `ExtPDF417Meta.png`)

> **Pro tip:** Если вам нужно лишь поэкспериментировать, Aspose предлагает 30‑дневную пробную версию с полным набором функций для чтения штрих‑кодов.

## Шаг 1: Установите NuGet‑пакет Aspose.BarCode

Откройте папку проекта в терминале и выполните:

```bash
dotnet add package Aspose.BarCode
```

Пакет добавляет пространство имён `Aspose.BarCode.ReadRecognition`, в котором находится класс `BarCodeReader`, используемый для декодирования изображений.

## Шаг 2: Создайте BarCodeReader для изображения PDF417

Конструктор `BarCodeReader` принимает два аргумента: путь к файлу изображения и `DecodeType`, который вы хотите использовать. Указание `DecodeType.MacroPdf417` сообщает Aspose искать символы Macro PDF417 и автоматически заполнять расширенные свойства.

```csharp
using Aspose.BarCode.ReadRecognition;

// Replace with the actual path to your barcode image
string imagePath = @"C:\Barcodes\ExtPDF417Meta.png";

using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
{
    // The reader is now ready to scan the image
```

### Почему использовать `DecodeType.MacroPdf417`?

* **Macro PDF417** хранит дополнительные поля (идентификатор файла, количество сегментов, метки времени и т.д.), которых нет в обычном PDF417.  
* Свойство `Extended` объекта `BarCodeResult` заполняется только при запросе макро‑типа, избавляя вас от отдельного шага парсинга.

## Шаг 3: Переберите все найденные штрих‑коды

Одно изображение может содержать несколько символов PDF417 (например, когда документ разбит на несколько страниц). Метод `ReadBarCodes()` возвращает `IEnumerable<BarCodeResult>`, по которому можно пройти в цикле.

```csharp
    foreach (BarCodeResult result in reader.ReadBarCodes())
    {
        // Basic information
        Console.WriteLine($"CodeType: {result.CodeTypeName}");
        Console.WriteLine($"CodeText: {result.CodeText}");
```

Если изображение не содержит штрих‑кода, цикл просто не выполнится, и программа завершится корректно. Такое поведение делает код безопасным для пакетной обработки, где некоторые файлы могут быть без штрих‑кода.

## Шаг 4: Выведите расширенные свойства Macro PDF417

Свойство `Extended.Pdf417` группирует все макроспецифичные поля. Каждое поле напрямую соответствует спецификации PDF417, поэтому вы можете сохранять их в базе данных, вести журнал или использовать для дальнейшей валидации.

```csharp
        // Macro PDF417 extended properties
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
    }
}
```

### Что означает каждое свойство

| Property | Description |
|----------|-------------|
| **MacroPdf417FileID** | Уникальный идентификатор всего много‑сегментного документа. |
| **MacroPdf417SegmentID** | Индекс текущего сегмента (начинается с 0). |
| **MacroPdf417SegmentsCount** | Общее количество сегментов, принадлежащих файлу. |
| **MacroPdf417FileName** | Необязательное имя файла, встроенное в штрих‑код. |
| **MacroPdf417Checksum** | CRC‑16 контрольная сумма блока макро‑данных. |
| **MacroPdf417FileSize** | Исходный размер файла в байтах. |
| **MacroPdf417TimeStamp** | Метка времени, когда был сгенерирован макро‑штрих‑код. |
| **MacroPdf417Addressee** | Предназначенный получатель документа. |
| **MacroPdf417Sender** | Отправитель документа. |
| **MacroPdf417Terminator** | Флаг‑терминатор, указывающий конец макро‑последовательности. |

Эти поля особенно полезны при восстановлении большого PDF или изображения, разбитого на несколько символов PDF417 для печати на низкокачественных носителях.

## Шаг 5: Обработка распространённых краевых случаев

### Отсутствующие макро‑поля

Иногда PDF417 штрих‑код генерируется без необязательных макро‑полей. Доступ к отсутствующему свойству возвращает `null` или `0`. Защитите свой код, если планируете сохранять значения:

```csharp
string fileName = result.Extended.Pdf417.MacroPdf417FileName ?? "Unnamed";
long fileSize = result.Extended.Pdf417.MacroPdf417FileSize;
```

### Повреждённые или низкокачественные изображения

Если изображение размыто, можно улучшить обнаружение, включив параметры качества `BarCodeReader`:

```csharp
reader.BarcodeSettings.ImageQuality = 90; // value between 0‑100
reader.BarcodeSettings.PureBarcode = false; // allow detection in noisy backgrounds
```

Эти настройки необязательны, но могут значительно повысить вероятность успешного чтения отсканированных документов.

### Несколько форматов штрих‑кодов на одном изображении

Если вы подозреваете наличие других типов штрих‑кодов, используйте `DecodeType.AllSupported` и отфильтруйте результаты:

```csharp
using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.AllSupported))
{
    foreach (BarCodeResult result in reader.ReadBarCodes())
    {
        if (result.CodeType == DecodeType.MacroPdf417)
        {
            // Process macro PDF417 as shown above
        }
    }
}
```

## Полный рабочий пример

Скопируйте следующую программу в новый консольный проект (`dotnet new console`) и запустите её. Замените переменную `imagePath` на путь к вашему собственному изображению Macro PDF417.

```csharp
using System;
using Aspose.BarCode.ReadRecognition;

class Program
{
    static void Main()
    {
        // Path to the barcode image
        string imagePath = @"C:\Barcodes\ExtPDF417Meta.png";

        // Initialize the reader for Macro PDF417
        using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
        {
            // Optional: improve detection on low‑quality scans
            reader.BarcodeSettings.ImageQuality = 90;
            reader.BarcodeSettings.PureBarcode = false;

            // Iterate through every barcode found in the image
            foreach (BarCodeResult result in reader.ReadBarCodes())
            {
                Console.WriteLine($"CodeType: {result.CodeTypeName}");
                Console.WriteLine($"CodeText: {result.CodeText}");

                // Output extended Macro PDF417 fields
                Console.WriteLine($"Pdf417MacroFileID: {result.Extended.Pdf417.MacroPdf417FileID}");
                Console.WriteLine($"Pdf417MacroSegmentID: {result.Extended.Pdf417.MacroPdf417SegmentID}");
                Console.WriteLine($"Pdf417MacroSegmentsCount: {result.Extended.Pdf417.MacroPdf417SegmentsCount}");
                Console.WriteLine($"Pdf417MacroFileName: {result.Extended.Pdf417.MacroPdf417FileName ?? \"N/A\"}");
                Console.WriteLine($"Pdf417MacroChecksum: {result.Extended.Pdf417.MacroPdf417Checksum}");
                Console.WriteLine($"Pdf417MacroFileSize: {result.Extended.Pdf417.MacroPdf417FileSize}");
                Console.WriteLine($"Pdf417MacroTimeStamp: {result.Extended.Pdf417.MacroPdf417TimeStamp}");
                Console.WriteLine($"Pdf417MacroAddressee: {result.Extended.Pdf417.MacroPdf417Addressee ?? \"N/A\"}");
                Console.WriteLine($"Pdf417MacroSender: {result.Extended.Pdf417.MacroPdf417Sender ?? \"N/A\"}");
                Console.WriteLine($"MacroPdf417Terminator: {result.Extended.Pdf417.MacroPdf417Terminator}");
                Console.WriteLine(new string('-', 40));
            }
        }
    }
}
```

**Ожидаемый вывод** (значения будут отличаться в зависимости от вашего изображения):

```
CodeType: MacroPdf417
CodeText: 1234567890ABCDEFGHIJ
Pdf417MacroFileID: 42
Pdf417MacroSegmentID: 0
Pdf417MacroSegmentsCount: 3
Pdf417MacroFileName: Invoice_2026_10.pdf
Pdf417MacroChecksum: 32768
Pdf417MacroFileSize: 245760
Pdf417MacroTimeStamp: 2026-10-24T14:32:10Z
Pdf417MacroAddressee: AccountingDept
Pdf417MacroSender: SalesTeam
MacroPdf417Terminator: True
----------------------------------------
```

Если изображение не содержит символов Macro PDF417, программа ничего не выводит и завершается тихо — идеально для пакетных задач, обрабатывающих множество файлов.

## Часто задаваемые вопросы

**Q: Можно ли считать обычный PDF417 (не‑macro) тем же кодом?**  
A: Да. Замените `DecodeType.MacroPdf417` на `DecodeType.Pdf417`. Свойство `Extended` будет пустым, но `CodeText` и `CodeTypeName` останутся доступными.

**Q: Поддерживает ли Aspose.BarCode чтение из потока вместо пути к файлу?**  
A: Абсолютно. Используйте перегрузку `new BarCodeReader(Stream, DecodeType)` и передайте `FileStream` или `MemoryStream`. Это удобно, когда изображение поступает из веб‑API.

**Q: Как проверить контрольную сумму?**  
A: Поле `MacroPdf417Checksum` содержит необработанное значение CRC‑16. Вы можете пересчитать контрольную сумму для восстановленного файла и сравнить её, чтобы убедиться в целостности данных.

## Следующие шаги и смежные темы

* **Создание PDF417 штрих‑кодов** – изучите `BarCodeGenerator` для генерации макро‑штрих‑кодов в целях тестирования.  
* **Объединение нескольких сегментов** – после чтения всех сегментов упорядочьте их по `MacroPdf417SegmentID` и соедините `CodeText` для восстановления исходного полезного нагрузки.  
* **Тонкая настройка производительности** – для сценариев с высокой пропускной способностью переиспользуйте один экземпляр `BarCodeReader` для множества изображений и

## Что изучать дальше?

Следующие учебники охватывают тесно связанные темы, построенные на техниках, продемонстрированных в этом руководстве. Каждый ресурс включает полностью работающие примеры кода с пошаговыми объяснениями, чтобы помочь вам освоить дополнительные возможности API и исследовать альтернативные подходы в собственных проектах.

- [How to Read PDF417 in C# – Complete Barcode Example](/barcode/english/net/compact-pdf417-encoding/how-to-read-pdf417-in-c-complete-barcode-example/)
- [How to create macro PDF417 barcode in C# using Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/how-to-create-macro-pdf417-barcode-in-c-using-aspose-barcode/)
- [Read barcode from image C# – complete guide with Macro PDF417](/barcode/english/net/compact-pdf417-encoding/read-barcode-from-image-c-complete-guide-with-macro-pdf417/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}