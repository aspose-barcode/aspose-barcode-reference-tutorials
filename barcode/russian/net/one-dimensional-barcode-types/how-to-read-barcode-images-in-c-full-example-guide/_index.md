---
category: general
date: 2026-10-15
description: Как быстро считывать изображения штрихкодов в C# с помощью BarCodeReader.
  Узнайте, как считывать несколько штрихкодов, и посмотрите пример считывателя штрихкодов
  на C#, работающего с Macro‑PDF417.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to read barcode
- read multiple barcodes
- c# barcode reader example
- Macro‑PDF417 decoding
- barcode metadata extraction
language: ru
lastmod: 2026-10-15
og_description: Как считывать штрих‑код в C# с помощью BarCodeReader. Этот учебник
  показывает полный пример считывателя штрих‑кодов на C#, который обрабатывает несколько
  штрих‑кодов и извлекает метаданные Macro‑PDF417.
og_image_alt: Screenshot showing how to read barcode with C# BarCodeReader
og_title: Как считать штрих‑код в C# – пошаговый пример
schemas:
- author: Aspose
  dateModified: '2026-10-15'
  description: How to read barcode images in C# quickly using BarCodeReader. Learn
    to read multiple barcodes and see a c# barcode reader example that works with
    Macro‑PDF417.
  headline: How to read barcode images in C# – full example guide
  type: TechArticle
- description: How to read barcode images in C# quickly using BarCodeReader. Learn
    to read multiple barcodes and see a c# barcode reader example that works with
    Macro‑PDF417.
  name: How to read barcode images in C# – full example guide
  steps:
  - name: Initialise the `BarCodeReader`
    text: '```csharp using Aspose.BarCode; using Aspose.BarCode.BarCodeRecognition;'
  - name: Read all barcodes present in the image
    text: '```csharp // Step 2: Read all barcodes in the image BarCodeResult[] results
      = reader.ReadBarCodes(); ```'
  - name: Display basic barcode details
    text: '```csharp foreach (BarCodeResult result in results) { Console.WriteLine($"CodeType:
      {result.CodeTypeName}"); Console.WriteLine($"CodeText: {result.CodeText}");
      ```'
  - name: Retrieve and show Macro‑PDF417 specific metadata
    text: '```csharp // Macro‑PDF417 extended data Console.WriteLine($"FileID: {result.Extended.Pdf417.MacroPdf417FileID}");
      Console.WriteLine($"Segment: {result.Extended.Pdf417.MacroPdf417SegmentID}");
      Console.WriteLine($"Count: {result.Extended.Pdf417.MacroPdf417SegmentsCount}");
      Console.WriteLine($"FileName'
  - name: Full runnable program
    text: Below is a self‑contained console application that puts all four steps together.
      Copy the code into a new `.cs` file, adjust the `imagePath`, and run `dotnet
      run`.
  type: HowTo
tags:
- barcode
- C#
- Aspose.BarCode
title: Как читать изображения штрихкодов в C# – полное руководство с примером
url: /ru/net/one-dimensional-barcode-types/how-to-read-barcode-images-in-c-full-example-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Как считывать изображения штрихкодов в C# – полное руководство с примером

Если вам нужно **как считывать штрихкод** из изображения в приложении .NET, это руководство предоставит готовое к запуску решение. Вы увидите полный **пример считывателя штрихкодов c#**, который работает с символами Macro‑PDF417 и может **считывать несколько штрихкодов** с одной картинки.

Считывание штрихкодов — распространённая задача для систем учёта, проверки билетов и обработки документов. К концу этого руководства вы сможете:

* Инициализировать `BarCodeReader` для любого поддерживаемого формата.  
* Извлечь базовую информацию, такую как тип кода и декодированный текст.  
* Получить специфичные для Macro‑PDF417 метаданные (ID файла, сегмент, контрольная сумма, …).  
* Обрабатывать изображения, содержащие несколько штрихкодов, без дополнительного кода.

## Требования

Перед началом убедитесь, что у вас есть:

* .NET 6.0 SDK или более поздняя версия, установленная.  
* Среда разработки (Visual Studio 2022, VS Code или Rider).  
* Пакет NuGet **Aspose.BarCode for .NET** (`Aspose.BarCode`) — он предоставляет класс `BarCodeReader`, используемый в примере.  
* Файл изображения, содержащий штрихкод Macro‑PDF417 (например, `MacroPdf417.png`).  

Вы можете установить пакет NuGet с помощью следующей команды:

```bash
dotnet add package Aspose.BarCode
```

## Как считывать штрихкоды с помощью BarCodeReader в C#

Ядро решения состоит из четырёх лаконичных шагов. Каждый шаг обёрнут в блок `using`, чтобы гарантировать своевременное освобождение неуправляемых ресурсов.

### Шаг 1: Инициализация `BarCodeReader`

```csharp
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

// Path to the image that contains the Macro‑PDF417 barcode(s)
string imagePath = @"YOUR_DIRECTORY\MacroPdf417.png";

// Initialise the reader for the specific DecodeType
using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
{
    // The remaining steps are inside this block
}
```

**Почему это важно:**  
`BarCodeReader` принимает путь к файлу и `DecodeType`. Указание `DecodeType.MacroPdf417` сообщает библиотеке искать только символы Macro‑PDF417, что ускоряет обнаружение и уменьшает количество ложных срабатываний.

### Шаг 2: Считать все штрихкоды, присутствующие на изображении

```csharp
    // Step 2: Read all barcodes in the image
    BarCodeResult[] results = reader.ReadBarCodes();
```

**Почему это важно:**  
Метод `ReadBarCodes()` возвращает массив, который может содержать один или несколько объектов `BarCodeResult`. Здесь проявляется возможность **считывать несколько штрихкодов** — отдельный цикл для каждого потенциального штрихкода не требуется.

### Шаг 3: Отобразить базовые детали штрихкода

```csharp
    foreach (BarCodeResult result in results)
    {
        Console.WriteLine($"CodeType: {result.CodeTypeName}");
        Console.WriteLine($"CodeText: {result.CodeText}");
```

**Почему это важно:**  
`CodeTypeName` сообщает, какая символьная система была обнаружена (например, “MacroPDF417”), а `CodeText` содержит декодированную полезную нагрузку. Эти два поля используются чаще всего в последующей логике.

### Шаг 4: Получить и отобразить специфичные для Macro‑PDF417 метаданные

```csharp
        // Macro‑PDF417 extended data
        Console.WriteLine($"FileID:    {result.Extended.Pdf417.MacroPdf417FileID}");
        Console.WriteLine($"Segment:   {result.Extended.Pdf417.MacroPdf417SegmentID}");
        Console.WriteLine($"Count:     {result.Extended.Pdf417.MacroPdf417SegmentsCount}");
        Console.WriteLine($"FileName:  {result.Extended.Pdf417.MacroPdf417FileName}");
        Console.WriteLine($"Checksum:  {result.Extended.Pdf417.MacroPdf417Checksum}");
        Console.WriteLine($"FileSize:  {result.Extended.Pdf417.MacroPdf417FileSize}");
        Console.WriteLine($"Time:      {result.Extended.Pdf417.MacroPdf417TimeStamp}");
        Console.WriteLine($"Addressee: {result.Extended.Pdf417.MacroPdf417Addressee}");
        Console.WriteLine($"Sender:    {result.Extended.Pdf417.MacroPdf417Sender}");
        Console.WriteLine($"Terminator:{result.Extended.Pdf417.MacroPdf417Terminator}");
        Console.WriteLine(new string('-', 40));
    }
}
```

**Почему это важно:**  
Macro‑PDF417 расширяет обычный формат PDF417 метаданными уровня документа. Доступ к свойству `Extended.Pdf417` даёт всё необходимое для восстановления оригинального файла, проверки целостности или маршрутизации данных получателю.

### Полностью исполняемая программа

Ниже представлено автономное консольное приложение, объединяющее все четыре шага. Скопируйте код в новый файл `.cs`, скорректируйте `imagePath` и запустите `dotnet run`.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // ------------------------------------------------------------
            // 1️⃣ Initialise the BarCodeReader for Macro‑PDF417 images
            // ------------------------------------------------------------
            string imagePath = @"YOUR_DIRECTORY\MacroPdf417.png";

            using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
            {
                // ------------------------------------------------------------
                // 2️⃣ Read all barcodes present in the image
                // ------------------------------------------------------------
                BarCodeResult[] results = reader.ReadBarCodes();

                if (results.Length == 0)
                {
                    Console.WriteLine("No barcodes were detected.");
                    return;
                }

                // ------------------------------------------------------------
                // 3️⃣ Iterate over each result – this is where we **read multiple barcodes**
                // ------------------------------------------------------------
                foreach (BarCodeResult result in results)
                {
                    Console.WriteLine($"CodeType: {result.CodeTypeName}");
                    Console.WriteLine($"CodeText: {result.CodeText}");

                    // ------------------------------------------------------------
                    // 4️⃣ Extract Macro‑PDF417 metadata (c# barcode reader example)
                    // ------------------------------------------------------------
                    Console.WriteLine($"FileID:    {result.Extended.Pdf417.MacroPdf417FileID}");
                    Console.WriteLine($"Segment:   {result.Extended.Pdf417.MacroPdf417SegmentID}");
                    Console.WriteLine($"Count:     {result.Extended.Pdf417.MacroPdf417SegmentsCount}");
                    Console.WriteLine($"FileName:  {result.Extended.Pdf417.MacroPdf417FileName}");
                    Console.WriteLine($"Checksum:  {result.Extended.Pdf417.MacroPdf417Checksum}");
                    Console.WriteLine($"FileSize:  {result.Extended.Pdf417.MacroPdf417FileSize}");
                    Console.WriteLine($"Time:      {result.Extended.Pdf417.MacroPdf417TimeStamp}");
                    Console.WriteLine($"Addressee: {result.Extended.Pdf417.MacroPdf417Addressee}");
                    Console.WriteLine($"Sender:    {result.Extended.Pdf417.MacroPdf417Sender}");
                    Console.WriteLine($"Terminator:{result.Extended.Pdf417.MacroPdf417Terminator}");
                    Console.WriteLine(new string('-', 40));
                }
            }
        }
    }
}
```

#### Ожидаемый вывод в консоль

```
CodeType: MacroPDF417
CodeText: https://example.com/document
FileID:    12
Segment:   3
Count:     5
FileName:  report.pdf
Checksum:  0x1A2B3C4D
FileSize:  1048576
Time:      2024-08-15T14:23:00Z
Addressee: John Doe
Sender:    Acme Corp.
Terminator:END
----------------------------------------
```

Если изображение содержит более одного символа Macro‑PDF417, программа выводит отдельный блок для каждого штрихкода, демонстрируя возможность **считывать несколько штрихкодов** без дополнительного кода.

## Обработка распространённых граничных случаев

| Ситуация | Что делать | Причина |
|-----------|------------|--------|
| **Файл не найден** | Оберните создание `BarCodeReader` в блок `try/catch (FileNotFoundException)` и отобразите дружелюбное сообщение. | Предотвращает падение приложения и информирует пользователя о недостающем ресурсе. |
| **Штрихкод не обнаружен** | Проверьте `results.Length == 0` (как показано в полной программе) и обработайте ситуацию корректно. | Предоставляет ясную обратную связь, когда изображение не содержит поддерживаемой символьной системы. |
| **Другой тип штрихкода** | Измените `DecodeType.MacroPdf417` на `DecodeType.AllSupportedTypes` или другое конкретное значение перечисления. | Позволяет использовать один и тот же код с QR, Code128, DataMatrix и т.д., при этом сохраняет возможность **считывать несколько штрихкодов**. |
| **Большие изображения** | Установите `reader.AutoSize = true` или уменьшите масштаб изображения перед передачей его в считыватель. | Повышает производительность и снижает нагрузку на память CLR. |
| **Потокобезопасное использование** | Создавайте отдельный экземпляр `BarCodeReader` для каждого потока; класс не является потокобезопасным. | Избегает состояний гонки в многопоточных сканерах или веб‑службах. |

## Профессиональные советы для production‑кода

* **Раннее освобождение:** Оператор `using` гарантирует, что нативные ресурсы (например, буферы изображений) освобождаются сразу. В длительно работающих сервисах освобождайте считыватель, как только закончите обработку каждого изображения.  
* **Пакетная обработка**

## Что изучить дальше?

Следующие руководства охватывают тесно связанные темы, построенные на техниках, продемонстрированных в этом руководстве. Каждый ресурс включает полностью работающие примеры кода с пошаговыми объяснениями, чтобы помочь вам освоить дополнительные возможности API и исследовать альтернативные подходы к реализации в собственных проектах.

- [Считывание штрихкода из изображения C# – полное руководство с Macro PDF417](/barcode/english/net/compact-pdf417-encoding/read-barcode-from-image-c-complete-guide-with-macro-pdf417/)
- [Как создать macro PDF417 штрихкод в C# с использованием Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/how-to-create-macro-pdf417-barcode-in-c-using-aspose-barcode/)
- [Как считать PDF417 в C# – полный пример считывателя штрихкодов](/barcode/english/net/compact-pdf417-encoding/how-to-read-pdf417-in-c-complete-barcode-reader-example/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}