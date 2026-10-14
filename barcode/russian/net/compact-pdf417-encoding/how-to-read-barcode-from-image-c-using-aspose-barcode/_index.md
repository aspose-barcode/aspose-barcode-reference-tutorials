---
category: general
date: 2026-10-02
description: Узнайте, как считывать штрих‑код с изображения в C# с полным примером,
  показывающим, как декодировать штрих‑код PDF417 с помощью Aspose.BarCode.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- read barcode from image c#
- how to decode pdf417 barcode
language: ru
lastmod: 2026-10-02
og_description: Считайте штрих‑код с изображения на C# с помощью Aspose.BarCode. Этот
  учебник объясняет, как декодировать штрих‑код PDF417 и извлечь расширенные метаданные.
og_image_alt: Screenshot showing how to read barcode from image c# in Visual Studio
og_title: Считывание штрихкода с изображения в C# – пошаговое руководство
schemas:
- author: Aspose
  dateModified: '2026-10-02'
  description: Learn how to read barcode from image c# with a complete example that
    shows how to decode PDF417 barcode using Aspose.BarCode.
  headline: How to read barcode from image c# using Aspose.BarCode
  type: TechArticle
- description: Learn how to read barcode from image c# with a complete example that
    shows how to decode PDF417 barcode using Aspose.BarCode.
  name: How to read barcode from image c# using Aspose.BarCode
  steps:
  - name: Create a `BarCodeReader` for a PDF417 image
    text: '```csharp using System; using Aspose.BarCode; using Aspose.BarCode.BarCodeRecognition;'
  - name: Iterate over all detected barcodes
    text: '```csharp // Step 2: Read every barcode found in the image foreach (BarCodeResult
      barcodeResult in barcodeReader.ReadBarCodes()) { // At this point you have successfully
      read barcode from image c#. ```'
  - name: Access the extended PDF417 macro metadata
    text: '```csharp // Step 3: Grab the macro‑PDF417 extended information var macro
      = barcodeResult.Extended.Pdf417;'
  - name: Output the barcode text and macro details
    text: '```csharp // Step 4: Print the basic barcode information Console.WriteLine($"Type:
      {barcodeResult.CodeTypeName}, Text: {barcodeResult.CodeText}");'
  - name: Handle errors and clean up resources
    text: 'The `using` statement automatically disposes the `BarCodeReader`. However,
      you should still catch exceptions that may arise from missing files or unsupported
      formats:'
  type: HowTo
tags:
- barcode
- C#
- Aspose.BarCode
title: Как прочитать штрих‑код из изображения C# с помощью Aspose.BarCode
url: /ru/net/compact-pdf417-encoding/how-to-read-barcode-from-image-c-using-aspose-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Как считать штрих‑код с изображения C# с использованием Aspose.BarCode

Если вам нужно **считать штрих‑код с изображения C#**, это руководство проведёт вас через полное, готовое к запуску решение. Вы узнаете, как декодировать штрих‑код PDF417, получить его расширенные макро‑данные и вывести результаты в консоль.

Считывание штрих‑кодов с изображений — распространённая задача для систем учёта, проверки билетов и обработки документов. Этот учебник охватывает всё необходимое: требуемые пакеты, объяснение кода, обработку граничных случаев и ожидаемый вывод. Внешняя документация не требуется; пример работает сразу с Aspose.BarCode .NET.

## Требования

Перед началом убедитесь, что у вас есть:

* .NET 6.0 SDK или более поздняя версия, установленная  
* Visual Studio 2022 (или любая IDE для C#)  
* Ссылка NuGet на **Aspose.BarCode** (версия 23.10 или новее)  
* Файл изображения, содержащий штрих‑код PDF417 – например `ExtPDF417Meta.png`

Если какой‑либо из этих пунктов отсутствует, установите .NET SDK, добавьте пакет NuGet с помощью `dotnet add package Aspose.BarCode` и поместите изображение в папку, к которой ваш проект может обращаться.

## Как считать штрих‑код с изображения C# – пошагово

Следующие разделы разбивают реализацию на логические шаги. Каждый шаг включает фрагмент кода, объяснение **почему** шаг важен и совет, который можно применить в реальных проектах.

### Шаг 1: Создать `BarCodeReader` для изображения PDF417

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

class Program
{
    static void Main()
    {
        // Step 1: Initialise the reader for a Macro PDF417 image
        const string imagePath = @"YOUR_DIRECTORY/ExtPDF417Meta.png";

        // The DecodeType enum tells the library which symbology to look for.
        // Using DecodeType.MacroPdf417 restricts the scan to PDF417 macro symbols.
        using (BarCodeReader barcodeReader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
        {
            // The reader is now ready to read barcode from image c# efficiently.
```

**Почему это важно** – Конструктор `BarCodeReader` принимает путь к изображению и ожидаемый тип штрих‑кода. Указание `MacroPdf417` сужает поиск, что повышает производительность и уменьшает количество ложных срабатываний, когда изображение содержит несколько символогий.

**Pro tip:** Если вы не уверены в типе штрих‑кода, используйте `DecodeType.AllSupportedTypes` и отфильтруйте результаты позже.

### Шаг 2: Перебрать все обнаруженные штрих‑коды

```csharp
            // Step 2: Read every barcode found in the image
            foreach (BarCodeResult barcodeResult in barcodeReader.ReadBarCodes())
            {
                // At this point you have successfully read barcode from image c#.
```

**Почему это важно** – Изображение PDF417 macro может содержать несколько сегментов. Метод `ReadBarCodes()` возвращает коллекцию, позволяя обрабатывать каждый сегмент отдельно.

**Edge case:** Если изображение не содержит никаких символов PDF417, коллекция будет пустой и тело цикла никогда не выполнится. Рассмотрите возможность добавить проверку после цикла, чтобы информировать пользователя.

### Шаг 3: Доступ к расширенным метаданным PDF417 macro

```csharp
                // Step 3: Grab the macro‑PDF417 extended information
                var macro = barcodeResult.Extended.Pdf417;

                // The macro object holds file‑level data that PDF417 uses for
                // multi‑segment documents such as shipping manifests.
```

**Почему это важно** – Свойство `Extended.Pdf417` раскрывает поля, определённые спецификацией PDF417, такие как ID файла, ID сегмента и имя файла. Эти данные необходимы, когда нужно восстановить многостраничный документ из отдельных сканов штрих‑кодов.

**Pro tip:** Всегда проверяйте, что `barcodeResult.Extended` не равно null перед доступом к `Pdf417`. Библиотека возвращает `null` для символогий, не поддерживающих расширенные данные.

### Шаг 4: Вывести текст штрих‑кода и детали macro

```csharp
                // Step 4: Print the basic barcode information
                Console.WriteLine($"Type: {barcodeResult.CodeTypeName}, Text: {barcodeResult.CodeText}");

                // Print macro‑specific fields
                Console.WriteLine($"Macro File ID: {macro.MacroPdf417FileID}, Segment ID: {macro.MacroPdf417SegmentID}");
                Console.WriteLine($"Segments Count: {macro.MacroPdf417SegmentsCount}, File Name: {macro.MacroPdf417FileName}");
            }
        }
    }
}
```

**Почему это важно** – Вывод в консоль даёт мгновенную видимость как декодированного текста, так и макро‑метаданных. Это полезно для отладки и последующей обработки, например, сохранения информации в базе данных.

**Expected output** (при условии, что образец изображения содержит один макросегмент):

```
Type: MacroPdf417, Text: https://example.com/document.pdf
Macro File ID: 12, Segment ID: 1
Segments Count: 3, File Name: shipment_manifest.pdf
```

Если изображение содержит три сегмента, цикл выведет три блока, каждый с разным `Segment ID`.

### Шаг 5: Обработать ошибки и освободить ресурсы

`using`‑оператор автоматически освобождает `BarCodeReader`. Тем не менее, следует перехватывать исключения, которые могут возникнуть из‑за отсутствующих файлов или неподдерживаемых форматов:

```csharp
        try
        {
            // Place the entire reader block here (Steps 1‑4)
        }
        catch (Exception ex)
        {
            Console.Error.WriteLine($"Error while trying to read barcode from image c#: {ex.Message}");
        }
```

**Почему это важно** – Надёжные приложения не падают из‑за отсутствующего файла или повреждённого изображения. Чёткое сообщение об ошибке помогает вам или вашей службе поддержки быстро диагностировать проблему.

## Как декодировать штрих‑код PDF417 с помощью Aspose.BarCode

В этом разделе естественно появляется вторичное ключевое слово **how to decode pdf417 barcode**. Декодирование штрих‑кода PDF417 следует той же схеме, что показана выше, но вы можете опустить флаг `MacroPdf417`, если вам нужен только обычный текст:

```csharp
using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.Pdf417))
{
    foreach (BarCodeResult result in reader.ReadBarCodes())
    {
        Console.WriteLine($"Decoded text: {result.CodeText}");
    }
}
```

**Why you might choose this variant** – Когда штрих‑код не содержит макро‑информации, использование `DecodeType.Pdf417` уменьшает нагрузку на процессор и упрощает обработку результата.

**Common question:** *What if the barcode is rotated?*  
Aspose.BarCode автоматически определяет вращение и корректирует его, так что дополнительный код предобработки изображения не требуется.

## Полный, готовый к запуску пример

Скопируйте всю программу ниже в новый консольный проект (`dotnet new console`) и замените `YOUR_DIRECTORY/ExtPDF417Meta.png` реальным путём к вашему изображению.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

class Program
{
    static void Main()
    {
        const string imagePath = @"YOUR_DIRECTORY/ExtPDF417Meta.png";

        try
        {
            using (BarCodeReader barcodeReader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
            {
                foreach (BarCodeResult barcodeResult in barcodeReader.ReadBarCodes())
                {
                    var macro = barcodeResult.Extended?.Pdf417;

                    Console.WriteLine($"Type: {barcodeResult.CodeTypeName}, Text: {barcodeResult.CodeText}");

                    if (macro != null)
                    {
                        Console.WriteLine($"Macro File ID: {macro.MacroPdf417FileID}, Segment ID: {macro.MacroPdf417SegmentID}");
                        Console.WriteLine($"Segments Count: {macro.MacroPdf417SegmentsCount}, File Name: {macro.MacroPdf417FileName}");
                    }
                    else
                    {
                        Console.WriteLine("No macro PDF417 metadata available.");
                    }
                }
            }
        }
        catch (Exception ex)
        {
            Console.Error.WriteLine($"Error while trying to read barcode from image c#: {ex.Message}");
        }
    }
}
```

Запуск программы выводит тип штрих‑кода, декодированный текст и любые макро‑метаданные. Если изображение не содержит PDF417 macro, программа корректно информирует об этом.

## Заключение

Теперь вы знаете, как **считать штрих‑код с изображения C#** с помощью Aspose.BarCode, как **декодировать штрих‑код PDF417** и как извлекать расширенные поля macro‑PDF417. Решение охватывает инициализацию, итерацию, доступ к метаданным, обработку ошибок и вариант для обычного декодирования PDF417.

Отсюда вы можете:

* Сохранить извлечённые данные в базе данных SQL для последующего доступа.  
* Объединить несколько сегментов для восстановления оригинального документа.  
* Исследовать другие символогии, поддерживаемые Aspose.BarCode, такие

## Что следует изучить дальше?

Следующие учебники охватывают тесно связанные темы, которые развивают техники, продемонстрированные в этом руководстве. Каждый ресурс включает полностью работающие примеры кода с пошаговыми объяснениями, чтобы помочь вам освоить дополнительные возможности API и исследовать альтернативные подходы к реализации в собственных проектах.

- [Как считать PDF417 в C# – Полный пример штрих‑кода](/barcode/english/net/compact-pdf417-encoding/how-to-read-pdf417-in-c-complete-barcode-example/)
- [Как считать PDF417 в C# – Полный пример считывателя штрих‑кода](/barcode/english/net/compact-pdf417-encoding/how-to-read-pdf417-in-c-complete-barcode-reader-example/)
- [Как сгенерировать изображение штрих‑кода PDF417 в C# с помощью Aspose](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-image-in-c-with-aspose/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}