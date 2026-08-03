---
category: general
date: 2026-08-03
description: Считайте штрих‑код PDF417 с изображения с помощью C# BarCodeReader —
  полный пример считывателя штрих‑кодов, который также показывает, как считывать несколько
  штрих‑кодов.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- read PDF417 barcode
- barcode reader example
- read multiple barcodes
- read barcodes image
language: ru
lastmod: 2026-08-03
og_description: Быстро считайте штрих‑код PDF417 с помощью примера BarCodeReader на
  C#. Следуйте этому пошаговому руководству, чтобы декодировать macro PDF417 и считывать
  несколько штрих‑кодов с изображения.
og_image_alt: Console output of a read PDF417 barcode example in C#
og_title: Чтение штрихкода PDF417 на C# – полный пример считывателя штрихкода
schemas:
- author: Aspose
  dateModified: '2026-08-03'
  description: Read PDF417 barcode from an image using C# BarCodeReader – a complete
    barcode reader example that also shows how to read multiple barcodes.
  headline: Read PDF417 barcode in C# – barcode reader example
  type: TechArticle
- description: Read PDF417 barcode from an image using C# BarCodeReader – a complete
    barcode reader example that also shows how to read multiple barcodes.
  name: Read PDF417 barcode in C# – barcode reader example
  steps:
  - name: '**Create a new console project**'
    text: '**Create a new console project**'
  - name: '**Add the barcode library**'
    text: '**Add the barcode library**'
  - name: '**Copy the barcode image**'
    text: '**Copy the barcode image**'
  type: HowTo
tags:
- barcode
- PDF417
- C#
- .NET
title: Считывание штрихкода PDF417 в C# – пример считывателя штрихкода
url: /ru/net/compact-pdf417-encoding/read-pdf417-barcode-in-c-barcode-reader-example/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Чтение штрихкода PDF417 в C# – пример считывателя штрихкодов

Если вам нужно считать данные штрихкода PDF417 из изображения, это руководство покажет, как сделать это с помощью класса **BarCodeReader** в C#. Вы узнаете пример считывателя штрихкода, который также обрабатывает макро‑PDF417 и может читать несколько штрихкодов на одном изображении.

Работа со штрихкодами часто подразумевает работу с разными источниками изображений, различными условиями освещения и иногда составными данными, такими как сегменты макро‑PDF417. В этом учебнике рассматривается всё, что необходимо для декодирования штрихкода PDF417, извлечения его расширенных полей и обработки нескольких штрихкодов с одной картинки. К концу вы получите готовую консольную программу, которая читает штрихкоды из файла изображения и выводит подробную информацию в консоль.

## Что понадобится

Перед началом убедитесь, что у вас есть:

* .NET 6.0 SDK или более поздняя версия  
* Последняя версия NuGet‑пакета **Aspose.BarCode for .NET** (или любая совместимая библиотека, предоставляющая `BarCodeReader` и `DecodeType.MacroPdf417`)  
* Файл изображения, содержащий штрихкод PDF417 или макро‑PDF417 (в примере используется `ExtPDF417Meta.png`)  
* Редактор кода или IDE, например Visual Studio 2022  

Дополнительные сервисы или внешние API не требуются.

## Настройка проекта для чтения штрихкодов

1. **Создайте новый консольный проект**  

   ```bash
   dotnet new console -n Pdf417ReaderDemo
   cd Pdf417ReaderDemo
   ```

2. **Добавьте библиотеку штрихкодов**  

   ```bash
   dotnet add package Aspose.BarCode --version 23.12
   ```

3. **Скопируйте изображение штрихкода**  

   Поместите `ExtPDF417Meta.png` (или любое изображение, содержащее штрихкод PDF417) в папку проекта.  
   Для этого учебника предполагается, что файл находится по пути `YOUR_DIRECTORY/ExtPDF417Meta.png`.

Проект готов к компиляции и запуску примера считывателя штрихкодов.

## Как читать штрихкод PDF417 с помощью BarCodeReader

Суть решения — блок `using`, который создаёт экземпляр `BarCodeReader`, указывает `DecodeType.MacroPdf417` и перебирает каждый найденный штрихкод. Ниже приведён полностью самодостаточный код, который можно вставить в `Program.cs`.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

class Program
{
    static void Main()
    {
        // Path to the image that contains one or more PDF417 barcodes
        const string imagePath = "YOUR_DIRECTORY/ExtPDF417Meta.png";

        // Step 1: Create a BarCodeReader for a macro PDF417 image
        using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
        {
            // Step 2: Read all barcodes from the image
            foreach (BarCodeResult result in reader.ReadBarCodes())
            {
                // Step 3: Output basic barcode information
                Console.WriteLine($"CodeType: {result.CodeTypeName}");
                Console.WriteLine($"CodeText: {result.CodeText}");

                // Step 4: Output macro PDF417 specific fields
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

            // Pro tip: If no barcodes are found, ReadBarCodes() returns an empty collection.
            // You can check reader.HasBarcodes for a quick boolean test.
            if (!reader.HasBarcodes)
            {
                Console.WriteLine("No barcodes detected in the provided image.");
            }
        }
    }
}
```

**Почему это работает**:  

* `DecodeType.MacroPdf417` указывает считывателю искать макро‑расширение PDF417, которое содержит дополнительную мета‑информацию, такую как ID файла, количество сегментов и метки времени.  
* Оператор `using` гарантирует своевременное освобождение неуправляемых ресурсов (дескрипторы файлов, нативные буферы декодирования).  
* Цикл `foreach` автоматически обрабатывает **все** штрихкоды, присутствующие на изображении, удовлетворяя требование *чтения нескольких штрихкодов*.  

При запуске программы (`dotnet run`) вы должны увидеть вывод, похожий на следующий:

```
CodeType: MacroPdf417
CodeText: https://example.com/document.pdf
Pdf417MacroFileID: 12345
Pdf417MacroSegmentID: 1
Pdf417MacroSegmentsCount: 3
Pdf417MacroFileName: document.pdf
Pdf417MacroChecksum: 0x1A2B
Pdf417MacroFileSize: 204800
Pdf417MacroTimeStamp: 2024-07-15T10:25:00Z
Pdf417MacroAddressee: John Doe
Pdf417MacroSender: Acme Corp
MacroPdf417Terminator: True
----------------------------------------
```

Если изображение содержит более одного штрихкода PDF417, цикл выводит отдельный блок для каждого штрихкода, демонстрируя, как **читать несколько штрихкодов** с одной картинки.

## Чтение нескольких штрихкодов с одного изображения

Тот же экземпляр `BarCodeReader` может декодировать сразу несколько типов штрихкодов. Чтобы расширить область от только макро‑PDF417 к любому PDF417 (или даже QR, Code128 и т.д.), измените флаг `DecodeType`:

```csharp
using (BarCodeReader reader = new BarCodeReader(imagePath,
       DecodeType.Pdf417 | DecodeType.MacroPdf417 | DecodeType.QR | DecodeType.Code128))
{
    // The rest of the code stays unchanged.
}
```

*`DecodeType`* — это битовая маска, поэтому вы можете комбинировать любое количество поддерживаемых форматов. Такая гибкость делает фрагмент **примером считывателя штрихкодов**, работающим в широком спектре сценариев, например сканирование этикеток товаров, билетов или удостоверений личности.

## Безопасный доступ к полям макро‑PDF417

Макро‑PDF417 добавляет богатый набор расширенных свойств. Однако не каждый штрихкод содержит все поля. Попытка доступа к отсутствующему свойству может вызвать `NullReferenceException`. Самый безопасный подход — проверять каждое свойство перед выводом:

```csharp
var macro = result.Extended?.Pdf417;
if (macro != null)
{
    Console.WriteLine($"Pdf417MacroFileID: {macro.MacroPdf417FileID ?? "N/A"}");
    // Repeat for other fields...
}
```

*Почему это важно*: В реальных проектах вы можете получать обычные штрихкоды PDF417 без макро‑данных. Защитная проверка гарантирует, что приложение продолжит работу без сбоев.

## Распространённые ошибки и лучшие практики

| Проблема | Почему происходит | Рекомендуемое решение |
|----------|-------------------|------------------------|
| Неправильный путь к изображению | `BarCodeReader` бросает исключение «файл не найден» до начала декодирования | Используйте `Path.Combine` и проверяйте наличие файла с помощью `File.Exists` |
| Низкое разрешение изображения | Декодер не может обнаружить границы штрихкода, результат — ноль обнаружений | Обеспечьте минимум 300 dpi для надёжных результатов |
| Штрихкод повернут более 45° | Многие библиотеки предполагают вертикальное расположение | Включите `reader.RecognitionOptions.RotateImage = true`, если изображение может быть повернутым |

## Что изучать дальше?

Следующие учебники охватывают тесно связанные темы, расширяющие техники, продемонстрированные в этом руководстве. Каждый ресурс включает полностью рабочие примеры кода с пошаговыми объяснениями, чтобы помочь вам освоить дополнительные возможности API и исследовать альтернативные подходы в собственных проектах.

- [How to Read DataMatrix Barcodes with Aspose.BarCode for .NET](/barcode/english/net/datamatrix-barcode-reading/)
- [Read DataMatrix barcode C# – Generate DataMatrix Mode (Auto)](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-auto/)
- [Read Barcode from Image – Mastering Barcode Region Extraction in Java with Aspose.BarCode](/barcode/english/java/advanced-settings-and-optimization/extracting-barcode-region-information/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}