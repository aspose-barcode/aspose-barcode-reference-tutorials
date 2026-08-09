---
category: general
date: 2026-08-09
description: Как считывать PDF417 в C# с помощью BarCodeReader. Узнайте, как читать
  PNG‑файлы штрихкодов, обрабатывать несколько штрихкодов и извлекать расширенные
  метаданные.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to read pdf417
- c# barcode reader
- read multiple barcodes
- read barcode png
- read barcode extended
language: ru
lastmod: 2026-08-09
og_description: Как считывать PDF417 в C# с помощью Aspose.BarCode. Этот учебник показывает,
  как читать PNG‑файлы штрихкодов, обрабатывать несколько штрихкодов на одном изображении
  и получать расширенные метаданные PDF417.
og_image_alt: Screenshot of C# BarCodeReader console output displaying PDF417 metadata
og_title: Как читать PDF417 в C# – руководство по считыванию штрихкода
schemas:
- author: Aspose
  dateModified: '2026-08-09'
  description: How to read PDF417 in C# using the BarCodeReader. Learn to read barcode
    PNG files, handle multiple barcodes, and extract extended metadata.
  headline: How to read PDF417 in C# – complete barcode reader guide
  type: TechArticle
- description: How to read PDF417 in C# using the BarCodeReader. Learn to read barcode
    PNG files, handle multiple barcodes, and extract extended metadata.
  name: How to read PDF417 in C# – complete barcode reader guide
  steps:
  - name: Verify the file exists before creating the reader.
    text: Verify the file exists before creating the reader.
  - name: Use `Image.FromFile` only when you need to pre‑process (rotate, crop). The
      `BarCodeReader` can open the file directly, which avoids extra memory allocation.
    text: Use `Image.FromFile` only when you need to pre‑process (rotate, crop). The
      `BarCodeReader` can open the file directly, which avoids extra memory allocation.
  - name: If the PNG contains transparency, the reader still works because the barcode
      is rendered on opaque pixels.
    text: If the PNG contains transparency, the reader still works because the barcode
      is rendered on opaque pixels.
  type: HowTo
tags:
- barcode
- C#
- PDF417
title: Как считывать PDF417 в C# – полное руководство по чтению штрихкодов
url: /ru/net/compact-pdf417-encoding/how-to-read-pdf417-in-c-complete-barcode-reader-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Как читать PDF417 в C# – полное руководство по считыванию штрихкодов

Если вам нужно **как читать PDF417** в приложении .NET, это руководство предоставляет готовое к запуску решение. Вы увидите, как считывать PNG‑изображение со штрихкодом, обрабатывать несколько штрихкодов на одном изображении и извлекать расширенные поля PDF417, которые скрывают многие сканеры.

Считывание штрихкодов PDF417 широко используется в логистике, билетных системах и управлении документами. К концу этого урока вы сможете декодировать изображение Macro PDF417, отобразить каждый результат и использовать дополнительную информацию (ID файла, количество сегментов, метки времени и т.д.) в своей бизнес‑логике.

## Prerequisites

- .NET 6.0 или новее (код также работает с .NET Framework 4.7+)
- Visual Studio 2022 или любой IDE для C#
- **Aspose.BarCode for .NET** (бесплатная пробная версия или лицензированный пакет NuGet)
- PNG‑изображение, содержащее штрихкод Macro PDF417 (пример файла называется `ExtPDF417Meta.png`)

> **Совет:** Установите библиотеку через консоль NuGet:  
> `dotnet add package Aspose.BarCode`

## Как читать PDF417 с помощью BarCodeReader в C#

Ядром решения является класс `BarCodeReader`. Он принимает путь к изображению и перечисление `DecodeType`, которое указывает движку, какую символьную систему искать.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.ReadEngine;

class Pdf417Demo
{
    static void Main()
    {
        // Step 1: Create a BarCodeReader for a Macro PDF417 image
        using (BarCodeReader reader = new BarCodeReader(
            "YOUR_DIRECTORY/ExtPDF417Meta.png",
            DecodeType.MacroPdf417))
        {
            // Step 2: Read all barcodes from the image
            foreach (BarCodeResult result in reader.ReadBarCodes())
            {
                // Step 3: Output basic barcode information
                Console.WriteLine($"CodeType: {result.CodeTypeName}");
                Console.WriteLine($"CodeText: {result.CodeText}");

                // Step 4: Display Macro PDF417 extended metadata
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
}
```

### Почему это работает

- **`DecodeType.MacroPdf417`** указывает считывателю искать вариант Macro PDF417, который хранит дополнительные поля, показанные на шаге 4.
- Блок `using` автоматически освобождает читатель, закрывая файловые дескрипторы.
- `ReadBarCodes()` возвращает **все** штрихкоды, соответствующие запрошенному типу, что удовлетворяет требованию *чтения нескольких штрихкодов*, даже если изображение содержит только один.

Запуск программы выводит результат, похожий на:

```
CodeType: MacroPdf417
CodeText: 1234567890
Pdf417MacroFileID: 1
Pdf417MacroSegmentID: 0
Pdf417MacroSegmentsCount: 3
Pdf417MacroFileName: invoice_2023.pdf
Pdf417MacroChecksum: 0x1A2B
Pdf417MacroFileSize: 254321
Pdf417MacroTimeStamp: 2023-03-15T10:45:00Z
Pdf417MacroAddressee: ACME Corp.
Pdf417MacroSender: Warehouse 7
MacroPdf417Terminator: True
----------------------------------------
```

## Использование считывателя штрихкодов C# для чтения нескольких штрихкодов

Если изображение содержит несколько символов Macro PDF417 (например, отсканированную страницу с набором билетов), тот же цикл `foreach` обрабатывает каждый из них. Дополнительный код не нужен; считыватель агрегирует результаты внутри.

```csharp
// Example: processing a batch image
using (BarCodeReader batchReader = new BarCodeReader(
    "batch.png", DecodeType.MacroPdf417))
{
    int index = 0;
    foreach (BarCodeResult item in batchReader.ReadBarCodes())
    {
        Console.WriteLine($"--- Barcode #{++index} ---");
        Console.WriteLine($"Text: {item.CodeText}");
        // extended fields are accessed the same way
    }
}
```

### Распространённые подводные камни

- **Формат изображения:** Считыватель поддерживает PNG, JPEG, BMP и TIFF. Если попытаться использовать неподдерживаемый формат, вы получите пустую коллекцию. Поэтому в руководстве подчеркивается *чтение штрихкода PNG*.
- **Разрешение:** Изображения с низким разрешением (< 300 dpi) могут приводить к пропуску сегментов. При возможности увеличьте масштаб или запросите скан более высокого качества.
- **Флаг Macro:** Если забыть указать `DecodeType.MacroPdf417`, движок будет работать только с обычным PDF417 и отбросит расширенные данные. Всегда указывайте тип macro, когда нужны *расширенные поля штрихкода*.

## Чтение PNG‑файлов со штрихкодами – лучшие практики

Работа с PNG‑файлами проста, так как формат сохраняет пиксельные данные без потерь. Ниже краткий чек‑лист:

1. Убедитесь, что файл существует перед созданием считывателя.  
   ```csharp
   if (!File.Exists(path))
       throw new FileNotFoundException($"File not found: {path}");
   ```
2. Используйте `Image.FromFile` только при необходимости предварительной обработки (поворот, обрезка). `BarCodeReader` может открыть файл напрямую, что экономит дополнительную память.
3. Если PNG содержит прозрачность, считыватель всё равно работает, поскольку штрихкод отображается на непрозрачных пикселях.

## Доступ к расширенным метаданным PDF417

Объект `Extended.Pdf417` раскрывает все необязательные поля, определённые спецификацией PDF417. Вы можете сопоставить эти поля с доменной моделью, сохранить их в базе данных или использовать для валидации.

```csharp
public class Pdf417Metadata
{
    public int FileID { get; set; }
    public int SegmentID { get; set; }
    public int SegmentsCount { get; set; }
    public string FileName { get; set; }
    public string Checksum { get; set; }
    public long FileSize { get; set; }
    public DateTime TimeStamp { get; set; }
    public string Addressee { get; set; }
    public string Sender { get; set; }
    public bool Terminator { get; set; }
}
```

Populate the model:



## Что изучать дальше?

Следующие руководства охватывают тесно связанные темы, построенные на техниках, продемонстрированных в этом руководстве. Каждый ресурс включает полностью работающие примеры кода с пошаговыми объяснениями, чтобы помочь вам освоить дополнительные возможности API и изучить альтернативные подходы к реализации в своих проектах.

- [Как читать DataMatrix штрихкоды с помощью Aspose.BarCode for .NET](/barcode/english/net/datamatrix-barcode-reading/)
- [Как создать штрихкод – Compact PDF417 с Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [Чтение DataMatrix штрихкода C# – Генерация режима DataMatrix (Auto)](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-auto/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}