---
category: general
date: 2026-11-14
description: Узнайте, как считывать штрихкоды с изображения в C# с полным учебником
  по чтению штрихкодов на C#. Включает настройку, полный код и обработку полей Macro
  PDF417.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- read barcodes from image
- barcode reader tutorial c#
language: ru
lastmod: 2026-11-14
og_description: Считывайте штрихкоды с изображения в C# с помощью этого учебника по
  считывателю штрихкодов C#. Получите полностью рабочий пример и научитесь извлекать
  данные Macro PDF417.
og_image_alt: C# code screenshot that reads barcodes from image using BarCodeReader
og_title: Чтение штрихкодов с изображения в C# – полный учебник
schemas:
- author: Aspose
  dateModified: '2026-11-14'
  description: Learn how to read barcodes from image in C# with a complete barcode
    reader tutorial c#. Includes setup, full code, and handling Macro PDF417 fields.
  headline: How to read barcodes from image using C# – step‑by‑step guide
  type: TechArticle
- description: Learn how to read barcodes from image in C# with a complete barcode
    reader tutorial c#. Includes setup, full code, and handling Macro PDF417 fields.
  name: How to read barcodes from image using C# – step‑by‑step guide
  steps:
  - name: Prerequisites
    text: '- .NET 8 SDK (or .NET 6+ if you prefer) installed. - Basic familiarity
      with C# console applications. - An image file that contains a Macro PDF417 barcode
      (e.g., `MacroPdf417.png`).'
  - name: Explanation of each step
    text: '| Step | Why it matters | |------|----------------| | **1️⃣ Define image
      path** | The reader works with a file path or stream. Using a relative path
      makes the example easy to copy‑paste. | | **2️⃣ Create BarCodeReader** | Passing
      `DecodeType.MacroPdf417` restricts the scan to that symbology, which i'
  - name: Reading other symbologies
    text: 'If you need to **read barcodes from image** that are not Macro PDF417,
      replace `DecodeType.MacroPdf417` with a comma‑separated list, e.g.:'
  - name: Handling large images
    text: 'Large PNG or JPEG files can increase memory usage. To keep the process
      lightweight, you can downscale the image before passing it to `BarCodeReader`:'
  - name: Working with streams instead of file paths
    text: 'When the image comes from a database or a web request, pass a `Stream`:'
  type: HowTo
tags:
- C#
- barcode
- image processing
title: Как считывать штрихкоды с изображения с помощью C# – пошаговое руководство
url: /ru/net/one-dimensional-barcode-types/how-to-read-barcodes-from-image-using-c-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Как считывать штрихкоды с изображения с помощью C# – пошаговое руководство

Если вам нужно **считывать штрихкоды с изображения** в приложении .NET, это руководство покажет, как это сделать. К концу урока у вас будет полностью готовая, исполняемая программа, которая извлекает как базовые данные штрихкода, так и поля, специфичные для Macro PDF417.

В этом **barcode reader tutorial c#** мы рассмотрим настройку проекта, необходимый пакет NuGet и полный пример кода, работающий с последним .NET 8 SDK. Внешние сервисы не требуются — всё работает локально.

## Чего вы научитесь

- Как добавить библиотеку Aspose.BarCode (или аналогичную) в проект C#.  
- Как создать `BarCodeReader`, который работает с конкретным файлом изображения.  
- Как перебрать все обнаруженные штрихкоды и вывести их тип, текст и метаданные Macro PDF417.  
- Советы по работе с изображениями, содержащими несколько штрихкодов или различные типы декодирования.

### Требования

- Установлен .NET 8 SDK (или .NET 6+, если предпочитаете).  
- Базовые знания консольных приложений C#.  
- Файл изображения, содержащий штрихкод Macro PDF417 (например, `MacroPdf417.png`).  

---

## Шаг 1: Создать новый консольный проект

Откройте терминал и выполните:

```bash
dotnet new console -n BarcodeReaderDemo
cd BarcodeReaderDemo
```

## Шаг 2: Установить библиотеку для считывания штрихкодов

Для этого руководства мы используем библиотеку **Aspose.BarCode for .NET**, так как она поддерживает Macro PDF417 из коробки. Установите её через NuGet:

```bash
dotnet add package Aspose.BarCode --version 23.12
```

> **Почему эта библиотека?** Она предоставляет один класс `BarCodeReader`, поддерживает десятки символогий и раскрывает свойство `Extended`, содержащее поля Macro PDF417.

## Шаг 3: Написать код считывателя штрихкодов (barcode reader tutorial c#)

Замените содержимое `Program.cs` следующим полным примером. Он демонстрирует **как считывать штрихкоды с изображения** и выводит как общую информацию, так и специфичную для Macro PDF417.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Recognition;

namespace BarcodeReaderDemo
{
    class Program
    {
        static void Main(string[] args)
        {
            // -------------------------------------------------------------
            // 1️⃣  Define the path to the image that contains the barcode.
            // -------------------------------------------------------------
            string imagePath = "YOUR_DIRECTORY/MacroPdf417.png";

            // -------------------------------------------------------------
            // 2️⃣  Create a BarCodeReader for the Macro PDF417 symbology.
            // -------------------------------------------------------------
            // DecodeType.MacroPdf417 tells the reader to look for the
            // Macro PDF417 variant and to populate the Extended.Pdf417
            // fields when they are present.
            using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
            {
                // ---------------------------------------------------------
                // 3️⃣  Iterate through every barcode found in the image.
                // ---------------------------------------------------------
                foreach (BarCodeResult result in reader.ReadBarCodes())
                {
                    // -----------------------------------------------------
                    // 4️⃣  Output generic barcode information.
                    // -----------------------------------------------------
                    Console.WriteLine($"CodeType: {result.CodeTypeName}");
                    Console.WriteLine($"CodeText: {result.CodeText}");

                    // -----------------------------------------------------
                    // 5️⃣  Output Macro PDF417 specific fields (if any).
                    // -----------------------------------------------------
                    // The Extended property is only populated for
                    // symbologies that expose extra data, such as Macro PDF417.
                    Console.WriteLine($"Pdf417MacroFileID: {result.Extended.Pdf417.MacroPdf417FileID}");
                    Console.WriteLine($"Pdf417MacroSegmentID: {result.Extended.Pdf417.MacroPdf417SegmentID}");
                    Console.WriteLine($"Pdf417MacroSegmentsCount: {result.Extended.Pdf417.MacroPdf417SegmentsCount}");

                    // -----------------------------------------------------
                    // 6️⃣  (Optional) Add more macro fields here as needed.
                    // -----------------------------------------------------
                    Console.WriteLine(new string('-', 40));
                }
            }

            // -------------------------------------------------------------
            // 7️⃣  Keep the console window open when debugging.
            // -------------------------------------------------------------
            Console.WriteLine("Finished reading barcodes. Press any key to exit.");
            Console.ReadKey();
        }
    }
}
```

### Пояснение к каждому шагу

| Шаг | Почему это важно |
|------|----------------|
| **1️⃣ Определить путь к изображению** | Считыватель работает с путем к файлу или потоком. Использование относительного пути упрощает копирование‑вставку примера. |
| **2️⃣ Создать BarCodeReader** | Передача `DecodeType.MacroPdf417` ограничивает сканирование этой символогией, что повышает скорость и гарантирует заполнение полей `Extended`. |
| **3️⃣ Перебрать результаты** | Изображение может содержать несколько штрихкодов; цикл `foreach` гарантирует, что мы захватим их все. |
| **4️⃣ Общий вывод** | `CodeTypeName` и `CodeText` — самые часто используемые сведения, необходимые разработчикам. |
| **5️⃣ Поля Macro PDF417** | Macro PDF417 содержит дополнительные данные (ID файла, ID сегмента, количество сегментов). Доступ к `result.Extended.Pdf417` предоставляет эти значения без дополнительного парсинга. |
| **6️⃣ Дополнительные необязательные поля** | Библиотека раскрывает другие макрополя (например, `MacroPdf417FileName`). Вы можете расширить вывод в соответствии с вашими требованиями. |
| **7️⃣ Держать консоль открытой** | Полезно при запуске из Visual Studio или `dotnet run`, чтобы увидеть вывод до закрытия окна. |

## Шаг 4: Запустить программу и проверить вывод

Поместите ваш файл `MacroPdf417.png` в папку, на которую ссылается `imagePath`. Затем выполните:

```bash
dotnet run
```

Типичный вывод консоли выглядит так:

```
CodeType: MacroPdf417
CodeText: https://example.com/document.pdf
Pdf417MacroFileID: 12
Pdf417MacroSegmentID: 3
Pdf417MacroSegmentsCount: 5
----------------------------------------
Finished reading barcodes. Press any key to exit.
```

Если изображение содержит несколько символов Macro PDF417, программа перечислит каждый набор значений последовательно.

## Общие варианты и граничные случаи

### Чтение других символогий

Если вам нужно **считывать штрихкоды с изображения**, которые не являются Macro PDF417, замените `DecodeType.MacroPdf417` на список, разделённый запятыми, например:

```csharp
using (BarCodeReader reader = new BarCodeReader(imagePath,
    DecodeType.QR | DecodeType.Code128 | DecodeType.DataMatrix))
```

Свойство `Extended` будет `null` для символогий, не предоставляющих дополнительные данные, поэтому всегда проверяйте на `null` перед доступом.

### Обработка больших изображений

Большие PNG или JPEG файлы могут увеличить использование памяти. Чтобы процесс был лёгким, вы можете уменьшить масштаб изображения перед передачей его в `BarCodeReader`:

```csharp
using (System.Drawing.Bitmap bmp = new System.Drawing.Bitmap(imagePath))
{
    var resized = new System.Drawing.Bitmap(bmp, new System.Drawing.Size(bmp.Width / 2, bmp.Height / 2));
    using (BarCodeReader reader = new BarCodeReader(resized, DecodeType.MacroPdf417))
    {
        // read as before...
    }
}
```

### Работа с потоками вместо путей к файлам

Когда изображение поступает из базы данных или веб‑запроса, передайте `Stream`:

```csharp
using (FileStream fs = File.OpenRead(imagePath))
using (BarCodeReader reader = new BarCodeReader(fs, DecodeType.MacroPdf417))
{
    // read as before...
}
```

## Профессиональные советы для плавной работы считывателя штрихкодов

- **Pro tip:** Всегда задавайте `DecodeType` самым узким набором символогий, которые вы ожидаете. Это уменьшает количество ложных срабатываний и ускоряет обработку.  
- **Watch out for:** Изображения с низким контрастом или сильным сжатием могут приводить к пропуску считываний. Предобрабатывайте изображение (регулируйте яркость/контраст), если замечаете низкую эффективность обнаружения.  
- **Tip:** Класс `BarCodeReader` реализует `IDisposable`; использование блока `using` гарантирует своевременное освобождение нативных ресурсов.  

---

## Заключение

Теперь вы знаете, как **считывать штрихкоды с изображения** в C# и извлекать как стандартную, так и специфичную для Macro PDF417 информацию. Этот **barcode reader tutorial c#** предоставляет полное, автономное решение, которое можно внедрить в любой проект .NET.

Отсюда вы можете:

- Исследовать другие типы декодирования (QR, DataMatrix, Code128).  
- Интегрировать считыватель в API ASP.NET Core для обработки загрузок в реальном времени.  
- Сохранить извлечённые макрополя в базе данных для последующей агрегации.

Удачной разработки, и не стесняйтесь экспериментировать с различными источниками изображений и форматами штрихкодов!

## Что стоит изучить дальше?

Следующие руководства охватывают тесно связанные темы, которые опираются на техники, продемонстрированные в этом руководстве. Каждый ресурс включает полностью работающие примеры кода с пошаговыми объяснениями, чтобы помочь вам освоить дополнительные возможности API и исследовать альтернативные подходы к реализации в ваших проектах.

- [Как декодировать штрихкоды PDF417 в C# и считывать изображение штрихкода C#](/barcode/english/net/compact-pdf417-encoding/how-to-decode-pdf417-barcodes-in-c-and-read-barcode-image-c/)
- [Как считывать штрихкод с изображения c# с использованием Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/how-to-read-barcode-from-image-c-using-aspose-barcode/)
- [Считывание штрихкода с изображения C# – полное руководство с Macro PDF417](/barcode/english/net/compact-pdf417-encoding/read-barcode-from-image-c-complete-guide-with-macro-pdf417/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}