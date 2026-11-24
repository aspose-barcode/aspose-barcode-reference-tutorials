---
category: general
date: 2026-11-23
description: Узнайте, как использовать BarCodeReader в C# для чтения штрихкодов с
  изображения, включая декодирование Macro PDF417, с полным примером кода и понятными
  объяснениями.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to use barcodereader
- read barcodes from image c#
language: ru
lastmod: 2026-11-23
og_description: Как использовать BarCodeReader в C# для чтения штрихкодов с изображения.
  Следуйте этому пошаговому руководству, чтобы декодировать Macro PDF417 и другие
  форматы с готовым к запуску кодом.
og_image_alt: Screenshot of BarCodeReader console output showing decoded Macro PDF417
  data
og_title: Как использовать BarCodeReader в C# – быстро считывать штрихкоды с изображений
schemas:
- author: Aspose
  dateModified: '2026-11-23'
  description: Learn how to use BarCodeReader in C# to read barcodes from an image,
    including Macro PDF417 decoding, with a complete code example and clear explanations.
  headline: How to use BarCodeReader in C# to read barcodes from images
  type: TechArticle
- description: Learn how to use BarCodeReader in C# to read barcodes from an image,
    including Macro PDF417 decoding, with a complete code example and clear explanations.
  name: How to use BarCodeReader in C# to read barcodes from images
  steps:
  - name: 1. Decoding multiple barcode formats
    text: 'If you need to detect more than one format, pass a combined `DecodeType`
      flag:'
  - name: 2. Managing large images
    text: 'Large images can cause high memory usage. Downscale the image before passing
      it to the reader:'
  - name: 3. Error handling
    text: 'Wrap the reading logic in a try‑catch block to surface decoding failures:'
  type: HowTo
tags:
- barcode
- C#
- image-processing
title: Как использовать BarCodeReader в C# для чтения штрихкодов из изображений
url: /ru/net/compact-pdf417-encoding/how-to-use-barcodereader-in-c-to-read-barcodes-from-images/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Как использовать BarCodeReader в C# для чтения штрихкодов с изображений

Если вам нужно **как использовать BarCodeReader** для быстрой проверки штрихкода, это руководство покажет именно это. Независимо от того, создаёте ли вы систему точек продаж или автоматизируете приём документов, вы узнаете, как считывать штрихкоды из изображений в проектах C# всего в несколько строк кода.

В этом учебнике вы увидите полностью готовый, исполняемый пример, который декодирует штрихкод Macro PDF417, извлекает его расширенные свойства и выводит полезную информацию в консоль. Внешняя документация не требуется — всё, что нужно, находится здесь.

## Prerequisites

Перед тем как начать, убедитесь, что у вас есть:

* .NET 6.0 (или новее) — код ориентирован на последнюю LTS‑версию.
* Ссылка на пакет **Aspose.BarCode** (или любой совместимый) NuGet, предоставляющий `BarCodeReader`.
* Файл изображения, содержащий штрихкод Macro PDF417 (в примере используется `ExtPDF417Meta.png`).

> **Pro tip:** Если вы используете Visual Studio, добавьте пакет через `dotnet add package Aspose.BarCode` или через UI NuGet Package Manager.

## Step 1: Create a BarCodeReader instance

Первое, что делаете при работе с библиотекой штрихкодов, — создаёте объект‑чтения, указывающий исходное изображение и тип(ы) штрихкодов, которые нужно искать.

```csharp
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

// Step 1: Initialise BarCodeReader for a Macro PDF417 image
using (BarCodeReader barcodeReader = new BarCodeReader(
           "YOUR_DIRECTORY/ExtPDF417Meta.png",
           DecodeType.MacroPdf417))
{
    // The using block guarantees proper disposal of native resources.
```

*Почему это важно:*  
`BarCodeReader` открывает изображение, выделяет нативную память и подготавливает алгоритмы декодирования для указанного `DecodeType`. Ограничив тип до `MacroPdf417`, вы снижаете нагрузку на CPU и повышаете точность обнаружения.

## Step 2: Read all barcodes found in the image

Одно изображение может содержать несколько штрихкодов, особенно когда речь идёт о макро‑закодированных данных. Метод `ReadBarCodes` возвращает перечисление объектов `BarCodeResult`, каждый из которых представляет один найденный код.

```csharp
    // Step 2: Iterate over every barcode found
    foreach (BarCodeResult barcodeResult in barcodeReader.ReadBarCodes())
    {
```

*Почему это важно:*  
Итерация по коллекции гарантирует, что вы захватите каждый экземпляр, что критично для сценариев пакетной обработки или когда документ содержит несколько кодов.

## Step 3: Access the extended Macro PDF417 properties

Macro PDF417 хранит дополнительную метаинформацию, такую как идентификаторы файлов, номера сегментов и общее количество сегментов. Эти значения доступны через свойство `Extended.Pdf417` объекта `BarCodeResult`.

```csharp
        // Step 3: Pull extended Macro PDF417 information
        var macroInfo = barcodeResult.Extended.Pdf417;
```

*Почему это важно:*  
Расширенные поля позволяют восстановить много‑сегментные документы или проверить, что все части принадлежат одному источнику. Пропуск этого шага оставит вас только с «сырой» строкой текста, лишая важного контекста.

## Step 4: Output the most useful information

Наконец, выведите данные в консоль (или любой логгер), чтобы убедиться в корректности операции чтения. Пример выводит тип кода, декодированный текст и несколько макро‑полей.

```csharp
        // Step 4: Display key details
        Console.WriteLine($"Code Type: {barcodeResult.CodeTypeName}");
        Console.WriteLine($"Code Text: {barcodeResult.CodeText}");
        Console.WriteLine($"Macro PDF417 File ID: {macroInfo.MacroPdf417FileID}");
        // Additional macro fields are available:
        // macroInfo.MacroPdf417SegmentID
        // macroInfo.MacroPdf417SegmentsCount
    }
}
```

**Expected console output**

```
Code Type: MacroPdf417
Code Text: 1234567890
Macro PDF417 File ID: 42
```

> **Note:** Если изображение не содержит штрихкод Macro PDF417, `ReadBarCodes()` вернёт пустую коллекцию и тело цикла никогда не выполнится. Всегда проверяйте результат на пустоту в продакшн‑коде.

## Read barcodes from image in C# – handling common scenarios

### 1. Decoding multiple barcode formats

Если нужно обнаружить более одного формата, передайте комбинированный флаг `DecodeType`:

```csharp
using (BarCodeReader reader = new BarCodeReader(
           "sample.png",
           DecodeType.Pdf417 | DecodeType.QR | DecodeType.DataMatrix))
{
    // Same iteration logic as before
}
```

### 2. Managing large images

Большие изображения могут вызвать высокий расход памяти. Уменьшите масштаб изображения перед передачей его в reader:

```csharp
using (Bitmap original = new Bitmap("large.png"))
using (Bitmap resized = new Bitmap(original, new Size(1024, 768)))
{
    // Save resized image to a temporary stream and feed it to BarCodeReader
}
```

### 3. Error handling

Обёрните логику чтения в блок try‑catch, чтобы отлавливать ошибки декодирования:

```csharp
try
{
    // reading code from previous steps
}
catch (BarCodeException ex)
{
    Console.Error.WriteLine($"Barcode decoding failed: {ex.Message}");
}
```

## Full working example

Ниже представлен полный код программы, который можно скопировать, вставить и запустить. Он включает все шаги, необходимые директивы `using` и простую схему обработки ошибок.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

class Program
{
    static void Main()
    {
        const string imagePath = "YOUR_DIRECTORY/ExtPDF417Meta.png";

        try
        {
            using (BarCodeReader barcodeReader = new BarCodeReader(
                       imagePath,
                       DecodeType.MacroPdf417))
            {
                bool anyFound = false;

                foreach (BarCodeResult barcodeResult in barcodeReader.ReadBarCodes())
                {
                    anyFound = true;
                    var macroInfo = barcodeResult.Extended.Pdf417;

                    Console.WriteLine($"Code Type: {barcodeResult.CodeTypeName}");
                    Console.WriteLine($"Code Text: {barcodeResult.CodeText}");
                    Console.WriteLine($"Macro PDF417 File ID: {macroInfo.MacroPdf417FileID}");
                    Console.WriteLine($"Segment ID: {macroInfo.MacroPdf417SegmentID}");
                    Console.WriteLine($"Segments Count: {macroInfo.MacroPdf417SegmentsCount}");
                    Console.WriteLine(new string('-', 40));
                }

                if (!anyFound)
                {
                    Console.WriteLine("No barcodes were detected in the image.");
                }
            }
        }
        catch (BarCodeException ex)
        {
            Console.Error.WriteLine($"Error reading barcode: {ex.Message}");
        }
    }
}
```

**Running the program** выводит каждый найденный штрихкод Macro PDF417 и его расширенные поля, либо сообщает, что штрихкоды не найдены.

## Conclusion

Теперь вы знаете **как использовать BarCodeReader** для чтения штрихкодов из изображений в C#‑приложениях, включая извлечение метаданных Macro PDF417. Решение охватывает инициализацию, итерацию, доступ к расширенным свойствам и практические советы по работе с несколькими форматами, большими изображениями и ошибками.

Дальше вы можете изучить:

* **Reading QR codes** – замените `DecodeType.MacroPdf417` на `DecodeType.QR`.
* **Saving decoded data** в базу данных или JSON‑файл для дальнейшей обработки.
* **Integrating with ASP.NET Core** для приёма загруженных изображений через веб‑API.

Экспериментируйте с различными типами штрихкодов и источниками изображений. Приятного кодинга!


## What Should You Learn Next?


Следующие учебники охватывают тесно связанные темы, которые развивают техники, продемонстрированные в этом руководстве. Каждый ресурс содержит полностью рабочие примеры кода с пошаговыми объяснениями, помогающими освоить дополнительные возможности API и исследовать альтернативные подходы в ваших проектах.

- [c# barcode reader tutorial – read Macro PDF417 barcodes step by step using GroupDocs.Barcode](/barcode/english/net/compact-pdf417-encoding/c-barcode-reader-tutorial-read-macro-pdf417-barcodes-step-by/)
- [How to use a barcode generator C# for Macro PDF417](/barcode/english/net/compact-pdf417-encoding/how-to-use-a-barcode-generator-c-for-macro-pdf417/)
- [Read barcode from image C# – complete guide with Macro PDF417](/barcode/english/net/compact-pdf417-encoding/read-barcode-from-image-c-complete-guide-with-macro-pdf417/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}