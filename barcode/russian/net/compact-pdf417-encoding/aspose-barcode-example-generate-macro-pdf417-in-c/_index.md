---
category: general
date: 2026-10-09
description: Узнайте, как создать штрих‑код PDF417 в C# с использованием Aspose.BarCode
  — генерировать Macro PDF417 с полной поддержкой метаданных.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create pdf417 barcode c#
- macro pdf417 c#
- aspose barcode c#
- barcode generator c#
lastmod: 2026-10-09
og_description: Узнайте, как создать штрих‑код PDF417 в C# с использованием Aspose.BarCode
  — генерировать Macro PDF417 с полной поддержкой метаданных, включая file ID, segment
  data, timestamp и другие параметры.
og_image_alt: Screenshot of a Macro PDF417 barcode generated with Aspose.BarCode in
  C#
og_title: Как создать штрих‑код PDF417 в C# с помощью Aspose.BarCode
schemas:
- author: Aspose
  dateModified: '2026-10-09'
  description: Aspose barcode example showing how to use a barcode generator C# to
    create a Macro PDF417 with full metadata support.
  headline: 'Aspose barcode example: generate Macro PDF417 in C#'
  type: TechArticle
tags:
- aspose barcode
- pdf417 barcode
- c# barcode generation
- macro pdf417
title: Как создать штрих‑код PDF417 в C# с помощью Aspose.BarCode
url: /ru/net/compact-pdf417-encoding/aspose-barcode-example-generate-macro-pdf417-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Как создать PDF417 штрих‑код на C# с помощью Aspose.BarCode

Если вам нужно **создать PDF417 штрих‑код C#** быстро и надёжно, этот учебник проведёт вас через весь процесс с использованием Aspose.BarCode. Вы увидите все необходимые настройки, от базовых размеров до полного набора полей метаданных Macro PDF417, и завершите работу PNG‑изображением, готовым для последующей обработки.

## Быстрые ответы
- **Какая библиотека генерирует PDF417 штрих‑коды?** Aspose.BarCode for .NET.
- **В каком формате выводит пример?** A loss‑less PNG image.
- **Нужна ли лицензия?** A free trial works for the sample; a commercial license is required for production.
- **Какая версия .NET поддерживается?** .NET 6.0 or later.
- **Можно ли добавить метаданные к штрих‑коду?** Yes – Macro PDF417 supports file ID, segment count, timestamps, and more.

## Что такое штрих‑код PDF417?
PDF417 штрих‑код — это многослойная линейная символьная система, способная кодировать до примерно 1 KB данных на символ и поддерживающая необязательные макро‑метаданные для многосегментных файлов. Он состоит из нескольких рядов наложенных линейных паттернов, что обеспечивает большую ёмкость данных при сохранении читаемости стандартными 2‑D сканерами. Формат также включает уровни коррекции ошибок для повышения надёжности, а необязательная макро‑функция позволяет разбивать большие файлы на несколько штрих‑кодов с метаданными, помогающими их собрать обратно.

## Почему использовать Aspose.BarCode для PDF417?
Aspose.BarCode поддерживает **over 50 barcode symbologies** и может генерировать Macro PDF417 штрих‑коды с до **2 000 columns**, обрабатывая файлы более **10 MB** без загрузки всей нагрузки в память. Эта измеримая возможность гарантирует плавную работу сценариев с высоким пропуском в корпоративных средах и предоставляет широкие возможности настройки.

## Предварительные требования

- .NET 6.0 (or later) installed  
- Visual Studio 2022 or any C#‑compatible IDE  
- A valid license for **Aspose.BarCode for .NET** (the free trial works for this example)  

Add the Aspose.BarCode NuGet package to your project:

```bash
dotnet add package Aspose.BarCode
```

## Как создать PDF417 штрих‑код на C#?

`BarcodeGenerator` is the main class for creating barcode images.  
`EncodeTypes.MacroPdf417` selects the Macro PDF417 symbology for barcode generation.  
`Save` writes the generated barcode to an image file.

Load the `BarcodeGenerator` with the `EncodeTypes.MacroPdf417` enum and your target text, then call `Save` – that’s the complete creation flow in three lines. The generator handles Unicode automatically, and the `using` statement guarantees that unmanaged resources are released after the image is saved.

### Шаг 1: создать экземпляр генератора штрих‑кода C# 

The `BarcodeGenerator` class creates and configures barcode images.  

Instantiate `BarcodeGenerator` with the `EncodeTypes.MacroPdf417` enum value and the text you want to encode. The text can contain Unicode characters, which the library handles automatically.

```csharp
using Aspose.BarCode.Generation;
using System;

using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MacroPdf417, "Åspóse.Barcóde©"))
{
    // Subsequent steps are performed inside this using block.
```

*Почему это важно*: `EncodeTypes.MacroPdf417` tells the engine to produce a Macro PDF417 symbol, which supports segmented data and additional file‑level metadata. The `using` statement guarantees that unmanaged resources are released after the image is saved.

### Шаг 2: определить базовый внешний вид штрих‑кода

`XDimension.Pixels` sets the size of each barcode module in pixels.

A Macro PDF417 barcode consists of square modules. Controlling the module size and column count influences both readability and file size.

```csharp
    // Pixel size of a single module (X dimension)
    generator.Parameters.Barcode.XDimension.Pixels = 2;

    // Number of columns in the symbol; fewer columns produce a taller barcode
    generator.Parameters.Barcode.Pdf417.Columns = 5;
```

*Почему это важно*: `XDimension.Pixels` determines the visual density; a value of 2 pixels works well for screen display while keeping the image small. Adjust the column count to fit your layout constraints—more columns create a wider, shorter barcode.

### Шаг 3: установить специфические метаданные Macro PDF417

`MacroPdf417FileID` identifies the file to which all barcode segments belong.

Macro PDF417 extends the standard PDF417 format with fields that enable reconstruction of large files from multiple barcode segments. Each field is optional, but setting them demonstrates the full capabilities of the API.

```csharp
    // Unique identifier for the entire file
    generator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;

    // Identifier of the current segment (zero‑based)
    generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;

    // Total number of segments that compose the file
    generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;

    // Logical name of the source file
    generator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";

    // 16‑bit CCITT checksum for error detection
    generator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234;

    // Approximate size of the original file in bytes
    generator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400000;

    // Timestamp when the file was generated
    generator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2019, 11, 1);

    // Optional address fields for routing information
    generator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
    generator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";

    // Terminator indicates that this is the last segment
    generator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;
```

*Почему это важно*:  
- `MacroPdf417FileID` links all segments belonging to the same logical file.  
- `MacroPdf417SegmentID` and `MacroPdf417SegmentsCount` enable the decoder to reorder fragments correctly.  
- `MacroPdf417Checksum` provides a quick integrity check without decoding the entire payload.  
- `MacroPdf417FileSize` and `MacroPdf417TimeStamp` allow downstream systems to verify that the reconstructed file matches the original.  
- `MacroPdf417Addressee` / `MacroPdf417Sender` are useful in logistics or document‑exchange scenarios.  
- Setting `MacroPdf417Terminator` to `Set` marks this barcode as the final segment, which simplifies the reconstruction algorithm.

### Шаг 4: сохранить сгенерированное изображение штрих‑кода

`Save` writes the barcode image to the specified file path.

Finally, write the barcode to a PNG file. You can choose any supported format (`Png`, `Jpeg`, `Bmp`, `Gif`, `Tiff`).

```csharp
    // Save the barcode image to the specified path
    generator.Save("YOUR_DIRECTORY/ExtPDF417Meta.png", BarCodeImageFormat.Png);
}
```

*Почему это важно*: PNG preserves lossless pixel data, ensuring that scanners read the exact module pattern you configured. Changing the format may affect the visual quality and file size.

#### Ожидаемый результат

Running the complete program creates a file named **ExtPDF417Meta.png**. Opening the image shows a rectangular Macro PDF417 barcode with the text “Åspóse.Barcóde©” encoded, and the visual density matches the 2‑pixel X dimension you set. Scanning the image with a PDF417‑compatible reader returns all metadata fields defined in Step 3.

## Полный рабочий пример

Copy the code below into a new console project (`dotnet new console`) and replace `YOUR_DIRECTORY` with an absolute or relative path that exists on your machine.

```csharp
using Aspose.BarCode.Generation;
using System;

namespace MacroPdf417Demo
{
    class Program
    {
        static void Main()
        {
            // Step 1: Create a barcode generator for Macro PDF417 with the desired text
            using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MacroPdf417, "Åspóse.Barcóde©"))
            {
                // Step 2: Define the basic barcode appearance
                generator.Parameters.Barcode.XDimension.Pixels = 2;          // pixel size of a single module
                generator.Parameters.Barcode.Pdf417.Columns = 5;           // number of columns in the symbol

                // Step 3: Set Macro PDF417 specific metadata
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
                generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;
                generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";
                generator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234; // CCITT‑16 example
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400000;
                generator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2019, 11, 1);
                generator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
                generator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
                generator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;

                // Step 4: Save the generated barcode image
                generator.Save("YOUR_DIRECTORY/ExtPDF417Meta.png", BarCodeImageFormat.Png);
            }

            Console.WriteLine("Macro PDF417 barcode generated successfully.");
        }
    }
}
```

Run the program (`dotnet run`). After execution, verify that the PNG file appears at the location you specified. Use any barcode‑reading app that supports Macro PDF417 to confirm that the metadata is correctly embedded.

## Распространённые варианты и граничные случаи

- **Different image formats**: Replace `BarCodeImageFormat.Png` with `Jpeg`, `Bmp`, or `Tiff` if your downstream system prefers another format.  
- **Changing module size**: Larger `XDimension.Pixels` values improve scan reliability on low‑resolution scanners but increase image size.  
- **Multiple segments**: To produce a multi‑segment file, generate a series of barcodes, increment `MacroPdf417SegmentID` for each, and keep `MacroPdf417FileID` constant. Only the last segment should have `MacroPdf417Terminator` set.  
- **Unicode support**: The generator automatically encodes Unicode characters; ensure your source string uses UTF‑8 encoding if you read it from an external file.  
- **Error handling**: Wrap the `using` block in a try‑catch to capture `BarCodeException` for invalid parameters (e.g., column count out of range).

## Профессиональные советы

- **Performance**: Reuse a single `BarcodeGenerator` instance when creating many barcodes with the same settings; only change the `CodeText` property between saves.  
- **File size estimation**: The `MacroPdf417FileSize` field should match the byte count of the original payload; mismatches may cause downstream validation failures.  
- **Testing**: Validate generated barcodes with both Aspose’s built‑in decoder (`BarCodeReader`) and a third‑party scanner to ensure interoperability.

## Заключение

This **Aspose.BarCode** example shows you how to **создать PDF417 штрих‑код C#** with full Macro metadata support, giving you a solid foundation for building robust barcode‑based data exchange pipelines.

## Что вам следует изучить дальше?

The following tutorials cover closely related topics that build on the techniques demonstrated in this guide. Each resource includes complete working code examples with step‑by‑step explanations to help you master additional API features and explore alternative implementation approaches in your own projects.

- [Как создать штрих‑код – Compact PDF417 с Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [Как создать тихую зону штрих‑кода для Code 16K с помощью Aspose.BarCode для .NET](/barcode/english/net/code-16k-encoding/code-16k-quiet-zone-settings/)
- [Как создать тихую зону штрих‑кода для ITF-14 с использованием Aspose.BarCode для .NET](/barcode/english/net/itf-14-barcode-customization/itf-14-barcode-quiet-zone-configuration/)

---

**Последнее обновление:** 2026-10-09  
**Тестировано с:** Aspose.BarCode 24.11 for .NET  
**Автор:** Aspose

## Связанные руководства

- [Как сгенерировать изображение штрих‑кода Pdf417 в C с Aspose](/barcode/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-image-in-c-with-aspose/)
- [Как создать штрих‑код – Compact PDF417 с Aspose.BarCode](/barcode/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [Учебник генератора штрих‑кодов: Как сгенерировать штрих‑код Pdf417](/barcode/net/compact-pdf417-encoding/barcode-generator-tutorial-how-to-generate-pdf417-barcode-in/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}