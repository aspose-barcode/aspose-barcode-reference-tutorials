---
category: general
date: 2026-07-15
description: Как считывать штрих‑код PDF417 в C# и читать несколько штрих‑кодов с
  изображения. Узнайте, как читать изображение штрих‑кода в C# с подробным кодом и
  советами.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to read pdf417
- read multiple barcodes
- read barcode image c#
- Aspose.BarCode PDF417
- C# barcode decoding
language: ru
lastmod: 2026-07-15
og_description: Как быстро считывать штрих‑код PDF417 в C#. Это руководство покажет,
  как считывать несколько штрих‑кодов с одного изображения и декодировать каждое свойство.
og_image_alt: Screenshot of C# console output displaying PDF417 barcode details
og_title: Как читать PDF417 в C# – полный пример кода и объяснение
schemas:
- author: Aspose
  dateModified: '2026-07-15'
  description: How to read PDF417 barcode in C# and read multiple barcodes from an
    image. Learn to read barcode image C# with detailed code and tips.
  headline: How to Read PDF417 in C# – Complete Step‑by‑Step Guide
  type: TechArticle
- description: How to read PDF417 barcode in C# and read multiple barcodes from an
    image. Learn to read barcode image C# with detailed code and tips.
  name: How to Read PDF417 in C# – Complete Step‑by‑Step Guide
  steps:
  - name: Why This Code Works
    text: '* **`BarCodeReader`** is the core class that streams the image, detects
      barcodes, and returns a collection of `BarCodeResult` objects. * Passing **`DecodeType.MacroPdf417`**
      tells the library to treat Macro‑PDF417 specially; it still returns plain PDF417
      symbols, which satisfies the **read multiple '
  - name: What if the image has both Macro‑PDF417 and regular PDF417 symbols?
    text: The same `BarCodeReader` call will return both. You can differentiate them
      by checking `result.CodeType` (`MacroPdf417` vs `Pdf417`). The extended properties
      will be `null` for a plain PDF417, so the `if (macro != null)` guard prevents
      a `NullReferenceException`.
  - name: My barcode is rotated or skewed—will the reader still work?
    text: Aspose.BarCode includes built‑in rotation and distortion compensation. As
      long as the barcode is at least 30 % of the image width, the decoder will usually
      succeed. For extreme cases you can enable `reader.Options.AllowInvertedBarcodes
      = true;` before calling `ReadBarCodes()`.
  - name: How do I handle large batches of images?
    text: Wrap the reading logic in a `foreach (var file in Directory.GetFiles(folder,
      "*.png"))` loop. The `using` pattern ensures each image’s native resources are
      freed before the next iteration, keeping memory usage low.
  type: HowTo
tags:
- C#
- barcode
- PDF417
- Aspose
title: Как считывать PDF417 в C# — полное пошаговое руководство
url: /ru/net/compact-pdf417-encoding/how-to-read-pdf417-in-c-complete-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Как считывать PDF417 в C# – Полное пошаговое руководство

Когда‑нибудь задумывались **как считывать PDF417** с изображения с помощью C#? Вы не одиноки. Большинство разработчиков сталкиваются с проблемой, когда нужно извлечь расширенные поля Macro‑PDF417 из отсканированного документа. Хорошая новость? Всего несколькими строками кода можно декодировать PDF417, считать несколько штрихкодов на одной картинке и получить каждое скрытое свойство, которое описывает спецификация.

В этом руководстве мы пройдем реальный пример, показывающий **как считывать PDF417**, как **считывать несколько штрихкодов** из одного файла и почему код **read barcode image C#** выглядит именно так. К концу вы получите готовое консольное приложение, которое выводит всю необходимую информацию — ID файла, ID сегмента, контрольную сумму, метки времени и т.д.

## Требования

Прежде чем начать, убедитесь, что у вас есть:

* .NET 6.0 SDK или новее (код работает и с .NET Core, и с .NET Framework).  
* Visual Studio 2022 (или любой другой предпочитаемый редактор).  
* NuGet‑пакет **Aspose.BarCode for .NET** — это библиотека, которая действительно парсит PDF417.  
* Пример изображения, содержащего штрихкод Macro‑PDF417 (например `ExtPDF417Meta.png`).  

Дополнительная конфигурация не требуется; библиотека поставляется со всеми необходимыми декодерами.

## Шаг 1: Установить Aspose.BarCode

Откройте папку проекта в терминале и выполните:

```bash
dotnet add package Aspose.BarCode
```

Эта команда загрузит последнюю стабильную версию (на июль 2026 это 23.12). Если вы предпочитаете Package Manager Console в Visual Studio, используйте:

```powershell
Install-Package Aspose.BarCode
```

> **Pro tip:** зафиксируйте версию (`23.12.0`) в вашем `.csproj`, чтобы избежать случайных несовместимых изменений в будущем.

## Шаг 2: Создать каркас консольного приложения

Создайте новый консольный проект, если у вас его ещё нет:

```bash
dotnet new console -n Pdf417ReaderDemo
cd Pdf417ReaderDemo
```

Замените автоматически сгенерированный `Program.cs` кодом ниже. Мы разберём каждый блок в следующих разделах.

## Шаг 3: Написать полный код «Как считывать PDF417»

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
            // -----------------------------------------------------------------
            // 1️⃣  Set the path to the image that contains one or more PDF417 codes
            // -----------------------------------------------------------------
            string imagePath = @"YOUR_DIRECTORY/ExtPDF417Meta.png";

            // -----------------------------------------------------------------
            // 2️⃣  Initialise the BarCodeReader for MacroPdf417 decoding
            // -----------------------------------------------------------------
            // The DecodeType flag tells Aspose to look specifically for Macro‑PDF417,
            // but it will also pick up plain PDF417 symbols that happen to be in the
            // same image – perfect for the “read multiple barcodes” scenario.
            using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
            {
                // -----------------------------------------------------------------
                // 3️⃣  Iterate over every barcode found in the image
                // -----------------------------------------------------------------
                foreach (BarCodeResult result in reader.ReadBarCodes())
                {
                    // -------------------------------------------------------------
                    // 4️⃣  Basic barcode information – works for any barcode type
                    // -------------------------------------------------------------
                    Console.WriteLine($"Code Type : {result.CodeTypeName}");
                    Console.WriteLine($"Code Text : {result.CodeText}");

                    // -------------------------------------------------------------
                    // 5️⃣  Macro‑PDF417 extended properties (the real reason you’re here)
                    // -------------------------------------------------------------
                    var macro = result.Extended?.Pdf417?.MacroPdf417;
                    if (macro != null)
                    {
                        Console.WriteLine($"File ID          : {macro.FileID}");
                        Console.WriteLine($"Segment ID       : {macro.SegmentID}");
                        Console.WriteLine($"Segments Count   : {macro.SegmentsCount}");
                        Console.WriteLine($"File Name        : {macro.FileName}");
                        Console.WriteLine($"Checksum         : {macro.Checksum}");
                        Console.WriteLine($"File Size        : {macro.FileSize}");
                        Console.WriteLine($"Time Stamp       : {macro.TimeStamp}");
                        Console.WriteLine($"Addressee        : {macro.Addressee}");
                        Console.WriteLine($"Sender           : {macro.Sender}");
                        Console.WriteLine($"Terminator       : {macro.Terminator}");
                    }
                    else
                    {
                        Console.WriteLine("No Macro‑PDF417 extended data found for this barcode.");
                    }

                    Console.WriteLine(new string('-', 40)); // visual separator
                }
            }

            // -----------------------------------------------------------------
            // 6️⃣  Keep the console window open when running from VS
            // -----------------------------------------------------------------
            Console.WriteLine("Done. Press any key to exit...");
            Console.ReadKey();
        }
    }
}
```

### Почему этот код работает

* **`BarCodeReader`** — основной класс, который читает изображение, обнаруживает штрихкоды и возвращает коллекцию объектов `BarCodeResult`.  
* Передача **`DecodeType.MacroPdf417`** сообщает библиотеке обрабатывать Macro‑PDF417 особым образом; при этом она всё равно возвращает обычные символы PDF417, что удовлетворяет требованию **read multiple barcodes**.  
* Объект **`Extended.Pdf417.MacroPdf417`** содержит все необязательные поля, определённые стандартом ISO/IEC 15438 — здесь вы получаете `FileID`, `SegmentID`, `Checksum` и т.д.  
* Блок `using` гарантирует освобождение нативных ресурсов, предотвращая утечки памяти в длительно работающих сервисах.

## Шаг 4: Запустить приложение и проверить вывод

В терминале:

```bash
dotnet run
```

Вы должны увидеть что‑то вроде:

```
Code Type : MacroPdf417
Code Text : 1234567890...
File ID          : 12
Segment ID       : 1
Segments Count   : 3
File Name        : invoice2024.pdf
Checksum         : 9A3F
File Size        : 245760
Time Stamp       : 2024-11-02T14:23:00Z
Addressee        : Acme Corp
Sender           : Logistics Dept
Terminator       : 1
----------------------------------------
Done. Press any key to exit...
```

Если изображение содержит более одного штрихкода, цикл выведет разделительную строку (`----------------------------------------`) и продолжит с следующим результатом — именно так выглядит **read multiple barcodes** на практике.

## Часто задаваемые вопросы и особые случаи

### Что делать, если изображение содержит как Macro‑PDF417, так и обычные PDF417 символы?

Тот же вызов `BarCodeReader` вернёт оба типа. Их можно различать, проверяя `result.CodeType` (`MacroPdf417` vs `Pdf417`). Расширенные свойства будут `null` для обычного PDF417, поэтому условие `if (macro != null)` предотвращает `NullReferenceException`.

### Мой штрихкод повернут или искажен — будет ли работать считыватель?

Aspose.BarCode включает встроенную компенсацию вращения и искажений. Пока штрихкод занимает минимум 30 % ширины изображения, декодер обычно справляется. Для экстремальных случаев можно включить `reader.Options.AllowInvertedBarcodes = true;` перед вызовом `ReadBarCodes()`.

### Как обрабатывать большие партии изображений?

Обёрните логику чтения в цикл `foreach (var file in Directory.GetFiles(folder, "*.png"))`. Паттерн `using` гарантирует освобождение нативных ресурсов каждого изображения перед следующей итерацией, поддерживая низкое потребление памяти.

## Полный листинг исходного кода (готов к копированию)

Ниже представлен весь код программы в одном блоке для быстрого копирования. Нет скрытых зависимостей — только NuGet‑пакет Aspose.BarCode.

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
            string imagePath = @"YOUR_DIRECTORY/ExtPDF417Meta.png";

            using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
            {
                foreach (BarCodeResult result in reader.ReadBarCodes())
                {
                    Console.WriteLine($"Code Type : {result.CodeTypeName}");
                    Console.WriteLine($"Code Text : {result.CodeText}");

                    var macro = result.Extended?.Pdf417?.MacroPdf417;
                    if (macro != null)
                    {
                        Console.WriteLine($"File ID          : {macro.FileID}");
                        Console.WriteLine($"Segment ID       : {macro.SegmentID}");
                        Console.WriteLine($"Segments Count   : {macro.SegmentsCount}");
                        Console.WriteLine($"File Name        : {macro.FileName}");
                        Console.WriteLine($"Checksum         : {macro.Checksum}");
                        Console.WriteLine($"File Size        : {macro.FileSize}");
                        Console.WriteLine($"Time Stamp       : {macro.TimeStamp}");
                        Console.WriteLine($"Addressee        : {macro.Addressee}");
                        Console.WriteLine($"Sender           : {macro.Sender}");
                        Console.WriteLine($"Terminator       : {macro.Terminator}");
                    }
                    else
                    {
                        Console.WriteLine("No Macro‑PDF417 extended data found for this barcode.");
                    }

                    Console.WriteLine(new string('-', 40));
                }
            }

            Console.WriteLine("Done. Press any key to exit...");
            Console.ReadKey();
        }
    }
}
```

## Итоги – Что мы рассмотрели

* **Как считывать PDF417** с помощью Aspose.BarCode в C#.  
* Точные шаги для **read multiple barcodes** из одного изображения.  
* Как **read barcode image C#** и извлечь каждое поле Macro‑PDF417.  
* Советы по работе с вращением, пакетной обработкой и отсутствующими расширенными данными.

## Следующие шаги и смежные темы

* **Encode PDF417** — генерируйте свои собственные Macro‑PDF417 штрихкоды с помощью `BarCodeBuilder`.  
* **Read other 2‑D symbologies** — QR, DataMatrix, Aztec — используя тот же класс `BarCodeReader`.  
* **Integrate with ASP.NET Core** — создайте веб‑конечную точку, принимающую загруженное изображение и возвращающую JSON с декодированными полями.  

Экспериментируйте: меняйте путь к изображению, бросайте обычный PDF417 в ту же папку или меняйте флаги `DecodeType`, чтобы увидеть, как библиотека реагирует. Чем больше вы играете, тем увереннее будете себя чувствовать в сценариях **read barcode image C#**.

Есть сложное изображение, которое отказывается декодироваться? Оставьте комментарий ниже или откройте issue в репозитории GitHub примера проекта. Приятного кодинга!

## Что изучать дальше?

Следующие руководства охватывают тесно связанные темы, построенные на техниках, продемонстрированных в этом гиде. Каждый ресурс включает полностью работающие примеры кода с пошаговыми объяснениями, помогающими освоить дополнительные возможности API и исследовать альтернативные подходы в ваших проектах.

- [How to Read DataMatrix Barcodes with Aspose.BarCode for .NET](/barcode/english/net/datamatrix-barcode-reading/)
- [How to Create Barcode – Compact PDF417 with Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [Read DataMatrix barcode C# – Generate DataMatrix Mode (Auto)](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-auto/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}