---
category: general
date: 2026-07-15
description: Создайте штрих‑код из текста с помощью Aspose.BarCode в C#. Узнайте,
  как изменить количество столбцов, сохранить изображение штрих‑кода и быстро создавать
  решения Aspose для штрих‑кодов.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate barcode from text
- how to generate barcode
- how to change column count
- save barcode image
- create barcode aspose
language: ru
lastmod: 2026-07-15
og_description: Создайте штрих‑код из текста с помощью Aspose.BarCode. Это руководство
  показывает, как изменить количество столбцов, сохранить изображение штрих‑кода и
  создать штрих‑код Aspose в несколько строк кода.
og_image_alt: Generate barcode from text example – MicroPdf417 PNG output
og_title: Генерация штрихкода из текста с Aspose.BarCode – Быстрый обзор C#
schemas:
- author: Aspose
  dateModified: '2026-07-15'
  description: Generate barcode from text using Aspose.BarCode in C#. Learn how to
    change column count, save barcode image, and create barcode Aspose solutions fast.
  headline: Generate barcode from text using Aspose.BarCode – C# Guide
  type: TechArticle
- description: Generate barcode from text using Aspose.BarCode in C#. Learn how to
    change column count, save barcode image, and create barcode Aspose solutions fast.
  name: Generate barcode from text using Aspose.BarCode – C# Guide
  steps:
  - name: What if my text is longer than the default capacity?
    text: MicroPdf417 automatically switches to a multi‑row layout when the data exceeds
      the maximum per row. You can still control the column count, but the library
      may add extra rows behind the scenes. No extra code needed—just keep an eye
      on the resulting image dimensions.
  - name: How do I change the image format to JPEG or BMP?
    text: Replace `BarCodeImageFormat.Png` with `BarCodeImageFormat.Jpeg` (or `Bmp`).
      Remember that JPEG introduces compression artifacts, which can affect scanning
      reliability. PNG is the safest default.
  - name: I’m seeing a watermark in the output—what’s wrong?
    text: That’s the evaluation version of Aspose.BarCode. To **create barcode Aspose**
      without watermarks, load a valid license file as shown in the commented line
      of Step 2.
  - name: Can I generate other symbologies (QR, Code128, etc.)?
    text: Absolutely. Just swap `EncodeTypes.MicroPdf417` with any other value from
      the `EncodeTypes` enum, e.g., `EncodeTypes.QR` or `EncodeTypes.Code128`. The
      rest of the code stays the same, which makes the approach highly reusable.
  type: HowTo
tags:
- barcode
- Aspose
- C#
- image-processing
title: Генерация штрихкода из текста с использованием Aspose.BarCode – руководство
  по C#
url: /ru/net/one-dimensional-barcode-types/generate-barcode-from-text-using-aspose-barcode-c-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Генерация штрихкода из текста с помощью Aspose.BarCode – Руководство C#

Генерация штрихкода из текста с помощью Aspose.BarCode удивительно проста. В этом руководстве мы пройдёмся по **созданию штрихкода**, настроим расположение колонок и, наконец, **сохраним изображение штрихкода** в файл PNG. Независимо от того, создаёте ли вы систему билетов, принтер этикеток для склада или просто экспериментируете с QR‑подобными кодами, нижеописанные шаги быстро приведут вас к результату.

## Чему вы научитесь

- Создать штрихкод из любой Unicode‑строки (да, даже «Åspóse.Barcóde©» работает).
- Настроить **количество колонок** для MicroPdf417, чтобы подогнать под узкие или широкие этикетки.
- Сохранить результат на диск в нужном формате изображения.
- Советы по работе со специальными символами и типичные подводные камни при **создании штрихкода Aspose**.

Никаких внешних инструментов, без командных строк — только чистый C# и библиотека Aspose.BarCode.

## Предварительные требования

Прежде чем приступить, убедитесь, что у вас есть:

1. **.NET 6.0** или новее (код также работает на .NET Framework 4.7+).  
2. **Лицензия** на Aspose.BarCode, либо вы можете начать с бесплатной оценочной версии.  
3. Папка, в которую можно записывать файлы — в примерах мы назовём её `YOUR_DIRECTORY`.  

Если чего‑то не хватает, скачайте пакет NuGet прямо сейчас:

```bash
dotnet add package Aspose.BarCode
```

Вот и всё — никаких дополнительных DLL для копирования вручную.

## Шаг 1 – Настройка проекта и импортов

Сначала создайте консольное приложение (или вставьте код в любой C#‑проект). Главное — подключить нужные пространства имён:

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeImageFormat; // for the image format enum
```

Зачем эти using? `BarcodeGenerator` находится в `Aspose.BarCode.Generation`, а перечисление `BarCodeImageFormat` — в `Aspose.BarCode`. Чистый импорт делает последующий код более читаемым, как обычный английский текст.

## Шаг 2 – Создание генератора штрихкода (как генерировать штрихкод)

Теперь мы действительно **генерируем штрихкод из текста**. Перечисление `EncodeTypes` указывает Aspose, какую символьную систему использовать; здесь мы выбираем `MicroPdf417`, потому что он умеет компактно размещать длинные строки.

```csharp
// Step 2: Create a barcode generator for MicroPdf417 with the desired text
var generator = new BarcodeGenerator(EncodeTypes.MicroPdf417, "Åspóse.Barcóde©");

// Optional: If you have a license, load it now to avoid the evaluation watermark
// generator.License = new License(); // generator.License.SetLicense("Aspose.Total.NET.lic");
```

Обратите внимание, строка содержит символы с диакритикой и знак ©. Aspose.BarCode автоматически кодирует Unicode, так что предварительная обработка текста не требуется.

## Шаг 3 – Точная настройка внешнего вида (как изменить количество колонок)

MicroPdf417 позволяет управлять числом колонок, что напрямую влияет на ширину штрихкода. Более плотная раскладка подходит для узких этикеток; более широкая — улучшает читаемость на больших печатных листах.

```csharp
// Step 3: Set the X‑dimension (module width) to 2 pixels for finer resolution
generator.Parameters.Barcode.XDimension.Pixels = 2;

// Step 3b: Define the number of columns for the PDF417 layout (e.g., 4 columns)
generator.Parameters.Barcode.Pdf417.Columns = 4; // <-- how to change column count
```

Почему модули 2 пикселя? Это даёт чёткое изображение без излишнего увеличения размера файла. Экспериментируйте — значения от 1 до 4 обычно работают хорошо. Если понадобится другое количество колонок, просто измените свойство `Columns`; Aspose автоматически пересчитает макет.

## Шаг 4 – Сохранение изображения штрихкода (сохранить изображение штрихкода)

Сгенерировав объект, мы готовы **сохранить изображение штрихкода**. Метод `Save` принимает путь к файлу и перечисление формата изображения. PNG — без потерь, поэтому штрихкод остаётся чётким даже после масштабирования.

```csharp
// Step 4: Save the generated barcode as a PNG image
string outputPath = @"YOUR_DIRECTORY\MicroPdf417.png";
generator.Save(outputPath, BarCodeImageFormat.Png);
Console.WriteLine($"Barcode saved to {outputPath}");
```

Полезный совет: всегда используйте абсолютный путь или убедитесь, что рабочая директория соответствует вашим ожиданиям; иначе файл может оказаться в папке bin, и вы не сможете его найти.

## Полный рабочий пример

Объединив всё вместе, получаем автономную программу, которую можно скопировать в `Program.cs` и запустить:

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Create the generator with Unicode text
            var generator = new BarcodeGenerator(EncodeTypes.MicroPdf417, "Åspóse.Barcóde©");

            // 2️⃣ Adjust visual parameters
            generator.Parameters.Barcode.XDimension.Pixels = 2;   // finer modules
            generator.Parameters.Barcode.Pdf417.Columns = 4;    // how to change column count

            // 3️⃣ Choose output location
            string outputPath = @"C:\Temp\MicroPdf417.png";

            try
            {
                // 4️⃣ Persist the image (save barcode image)
                generator.Save(outputPath, BarCodeImageFormat.Png);
                Console.WriteLine($"✅ Barcode generated and saved to: {outputPath}");
            }
            catch (Exception ex)
            {
                // Pro tip: handle I/O errors gracefully
                Console.Error.WriteLine($"❌ Failed to save barcode: {ex.Message}");
            }
        }
    }
}
```

**Ожидаемый вывод** (консоль):

```
✅ Barcode generated and saved to: C:\Temp\MicroPdf417.png
```

И если открыть `MicroPdf417.png`, вы увидите чёткий штрихкод MicroPdf417, который кодирует исходную строку, включая все специальные символы, которые мы передали.

## Часто задаваемые вопросы и особые случаи

### Что делать, если мой текст длиннее стандартной ёмкости?

MicroPdf417 автоматически переходит в многострочный макет, когда данные превышают максимум на одну строку. Вы всё равно можете управлять количеством колонок, но библиотека может добавить дополнительные строки «за кулисами». Дополнительный код не нужен — просто следите за размерами получаемого изображения.

### Как изменить формат изображения на JPEG или BMP?

Замените `BarCodeImageFormat.Png` на `BarCodeImageFormat.Jpeg` (или `Bmp`). Помните, что JPEG вводит артефакты сжатия, что может повлиять на надёжность сканирования. PNG остаётся самым безопасным вариантом.

```csharp
generator.Save(outputPath, BarCodeImageFormat.Jpeg);
```

### Я вижу водяной знак в результате — в чём проблема?

Это оценочная версия Aspose.BarCode. Чтобы **создать штрихкод Aspose** без водяных знаков, загрузите действительный файл лицензии, как показано в закомментированной строке Шага 2.

### Можно ли генерировать другие символьные системы (QR, Code128 и т.д.)?

Конечно. Просто замените `EncodeTypes.MicroPdf417` на любое другое значение из перечисления `EncodeTypes`, например `EncodeTypes.QR` или `EncodeTypes.Code128`. Остальная часть кода остаётся без изменений, что делает подход очень переиспользуемым.

## Профессиональные советы для готовой к продакшну генерации штрихкодов

- **Кешируйте генератор**, если создаёте много штрихкодов с одинаковыми настройками; это уменьшит накладные расходы на создание объектов.
- **Проверяйте входную строку** на ограничения длины, характерные для выбранной символьной системы (Aspose бросает `ArgumentException`, если строка слишком длинная).
- **Используйте конструкции `using`** или вызывайте `Dispose` у генератора после завершения работы, чтобы своевременно освободить нативные ресурсы.
- **Устанавливайте DPI** через `generator.Parameters.ImageResolution.DpiX/DpiY`, если нужны высокоразрешающие печати для больших этикеток.

## Заключение

Теперь вы точно знаете **как генерировать штрихкод из текста** с помощью Aspose.BarCode, как **изменять количество колонок** и как правильно **сохранять изображение штрихкода** в PNG. Полный, исполняемый пример выше демонстрирует чистый, готовый к продакшну подход.

## Что изучать дальше?

Следующие руководства охватывают тесно связанные темы, расширяющие техники, продемонстрированные в этом руководстве. Каждый ресурс включает полностью работающие примеры кода с пошаговыми объяснениями, чтобы помочь вам освоить дополнительные возможности API и исследовать альтернативные варианты реализации в собственных проектах.

- [How to Generate Barcode – Code 39 Configuration with Aspose.BarCode](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-code-39-configuration/)
- [Generate barcode image – Code 93 with Aspose.BarCode](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-code-93-configuration/)
- [How to Generate DataMatrix Barcodes (ECC 200) with Aspose.BarCode for .NET](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-ecc-200-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}