---
category: general
date: 2026-10-02
description: Узнайте, как создать микро‑PDF417 штрих‑код в C# и быстро сгенерировать
  PNG‑изображение штрих‑кода. Включает пошаговый код и лучшие практики.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create micro pdf417 barcode
- how to generate barcode png
- create barcode image c#
- barcode generation C#
- MicroPdf417 settings
- C# image export
language: ru
lastmod: 2026-10-02
og_description: Создайте микробаркод PDF417 в C# и сгенерируйте PNG‑изображение штрихкода.
  Следуйте этому полному руководству, чтобы получить файлы штрихкода высокого качества.
og_image_alt: C# code generating a MicroPdf417 barcode saved as PNG
og_title: Создайте микробаркод PDF417 в C# — полное руководство по генерации PNG
schemas:
- author: Aspose
  dateModified: '2026-10-02'
  description: Learn how to create micro pdf417 barcode in C# and generate a barcode
    PNG image quickly. Includes step‑by‑step code and best practices.
  headline: How to create micro pdf417 barcode in C# and save it as PNG
  type: TechArticle
tags:
- barcode
- C#
- image generation
title: Как создать микро‑PDF417 штрих‑код в C# и сохранить его в PNG
url: /ru/net/compact-pdf417-encoding/how-to-create-micro-pdf417-barcode-in-c-and-save-it-as-png/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Как создать микробарcode Micro PDF417 в C# и сохранить его как PNG

Если вам нужно **создать микробарcode Micro PDF417** для этикетки, билета или мобильного сканирования, это руководство покажет, как сделать это в C#. Вы также узнаете, **как генерировать PNG‑файлы штрих‑кода**, которые можно внедрять в веб‑страницы или печатать напрямую из вашего приложения.

Мы пройдем все необходимые настройки, от инициализации генератора до выбора правильного X‑размера и количества колонок. К концу урока у вас будет готовый фрагмент кода C#, который создает четкое PNG‑изображение штрих‑кода MicroPdf417.

## Требования

Прежде чем начать, убедитесь, что у вас есть:

* .NET 6.0 SDK или новее (код также работает с .NET Core 3.1+)
* Visual Studio 2022 или любой IDE, поддерживающий C#
* NuGet‑пакет **Aspose.BarCode for .NET** (или любая библиотека, поддерживающая `EncodeTypes.MicroPdf417`). Установите его с помощью:

```bash
dotnet add package Aspose.BarCode
```

* Права записи в папку, куда вы планируете сохранять PNG‑файл.

Дополнительная конфигурация не требуется; библиотека обрабатывает всю низкоуровневую работу с изображениями.

## Шаг 1: Инициализировать генератор для штрих‑кода MicroPdf417

Первая строка создает экземпляр `BarcodeGenerator`, который знает, что нужно кодировать символ MicroPdf417. Текст, который вы передаете, может содержать Unicode‑символы, которые библиотека кодирует автоматически.

```csharp
using Aspose.BarCode.Generation;

// Initialize the generator with the desired text
var generator = new BarcodeGenerator(
    EncodeTypes.MicroPdf417,          // MicroPdf417 barcode type
    "Åspóse.Barcóde©");               // Sample data containing special characters
```

*Почему это важно*: Выбор `EncodeTypes.MicroPdf417` заставляет движок использовать компактную спецификацию MicroPdf417, что идеально подходит для небольших этикеток, одновременно поддерживая коррекцию ошибок.

## Шаг 2: Задать X‑размер (размер модуля) в пикселях

X‑размер определяет ширину самого маленького штриха («модуля»). Значение `2` пикселя дает плотный, но все еще читаемый штрих‑код.

```csharp
// Set the module size (pixel width of the smallest bar)
generator.Parameters.Barcode.XDimension.Pixels = 2;
```

*Подсказка*: Большие X‑размеры увеличивают общий размер изображения, что может быть полезно для принтеров с низким разрешением. Оставляйте значение 2–4 px для большинства сценариев отображения на экране.

## Шаг 3: Установить количество колонок (максимум 4 для MicroPdf417)

MicroPdf417 допускает до четырех колонок. Большее количество колонок уменьшает высоту штрих‑кода, но делает изображение шире.

```csharp
// Configure the number of columns (max 4 for MicroPdf417)
generator.Parameters.Barcode.Pdf417.Columns = 4;
```

*Зачем это может понадобиться*: Если ширина вашей этикетки ограничена, уменьшите количество колонок. И наоборот, увеличьте количество колонок, чтобы сократить высоту штрих‑кода, когда ограничение по высоте.

## Шаг 4: Сохранить сгенерированный штрих‑код как PNG‑изображение

Наконец, экспортируйте штрих‑код в PNG‑файл. PNG сохраняет точные пиксельные данные без артефактов сжатия, что делает его идеальным для четкого отображения штрих‑кода.

```csharp
using Aspose.BarCode;

// Define the output path (ensure the directory exists)
string outputPath = Path.Combine(
    Environment.CurrentDirectory, "MicroPdf417.png");

// Save as PNG
generator.Save(outputPath, BarCodeImageFormat.Png);

Console.WriteLine($"Barcode saved to: {outputPath}");
```

**Ожидаемый результат** – После запуска программы вы найдете `MicroPdf417.png` в папке проекта. Открытие файла покажет ясный штрих‑код MicroPdf417, кодирующий строку `Åspóse.Barcóde©`.

## Как генерировать PNG‑штрих‑код в разных форматах изображений (опционально)

Хотя PNG является самым распространенным форматом для изображений штрих‑кодов, тот же метод `Save` поддерживает JPEG, BMP и TIFF. Чтобы **как генерировать PNG‑штрих‑код** в другом формате, просто измените перечисление `BarCodeImageFormat`:

```csharp
// Save as JPEG instead of PNG
generator.Save(outputPath.Replace(".png", ".jpg"), BarCodeImageFormat.Jpeg);
```

Помните, что JPEG использует сжатие с потерями, которое может размыть тонкие штрихи. Для любых производственных сканирующих приложений используйте PNG.

## Создание изображения штрих‑кода C# – лучшие практики и особые случаи

Ниже несколько практических советов, которые делают ваш **create barcode image c#** процесс более надежным:

| Ситуация | Рекомендация |
|-----------|----------------|
| **Большой объем данных** | Разбейте данные на несколько символов MicroPdf417 и визуально соедините их. |
| **Принтеры с низким разрешением** | Увеличьте `XDimension.Pixels` до 3‑4 px, чтобы избежать пропусков штрихов. |
| **Динамическая папка вывода** | Используйте `Path.GetTempPath()` или папку, выбранную пользователем через `SaveFileDialog`. |
| **Потокобезопасная генерация** | Создавайте новый `BarcodeGenerator` для каждого потока; класс не является потокобезопасным. |
| **Обработка ошибок** | Оберните код генерации в блок `try/catch`, чтобы перехватывать `BarCodeException`. |

```csharp
try
{
    // generation code from steps 1‑4
}
catch (BarCodeException ex)
{
    Console.Error.WriteLine($"Barcode generation failed: {ex.Message}");
}
```

## Полный, готовый к запуску пример

Объединив всё вместе, получаем полное консольное приложение, которое можно скопировать, вставить и запустить:

```csharp
using System;
using System.IO;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // 1. Initialize generator with MicroPdf417 type and sample text
        var generator = new BarcodeGenerator(
            EncodeTypes.MicroPdf417,
            "Åspóse.Barcóde©");

        // 2. Set module size (X‑dimension) to 2 px
        generator.Parameters.Barcode.XDimension.Pixels = 2;

        // 3. Use the maximum of 4 columns for a compact shape
        generator.Parameters.Barcode.Pdf417.Columns = 4;

        // 4. Define output path and save as PNG
        string outputPath = Path.Combine(
            Environment.CurrentDirectory, "MicroPdf417.png");

        // Ensure the directory exists
        Directory.CreateDirectory(Path.GetDirectoryName(outputPath)!);

        // Save the barcode image
        generator.Save(outputPath, BarCodeImageFormat.Png);

        Console.WriteLine($"Barcode successfully created at: {outputPath}");
    }
}
```

Запустите программу командой `dotnet run`. Консоль выведет полный путь, а PNG‑файл появится рядом с исполняемым файлом.

## Заключение

Теперь вы знаете, **как создать микробарcode Micro PDF417** в C# и **как генерировать PNG‑файлы штрих‑кода** для любого проекта .NET. Шаги — инициализация генератора, настройка X‑размера и колонок, экспорт в PNG — охватывают основные параметры для надежного создания штрих‑кодов.

Дальше вы можете исследовать:

* **Create barcode image c#** для других символогий (QR, Code128, DataMatrix), изменив `EncodeTypes`.
* Добавление цвета или фоновых изображений через `generator.Parameters.Barcode.Image`.
* Интеграцию генерации штрих‑кода в конечные точки ASP.NET Core для выдачи изображений по запросу.

Экспериментируйте с настройками, проверяйте результат на реальных сканерах и адаптируйте код под ваш рабочий процесс. Приятного кодинга!

## Что изучать дальше?

Следующие учебники охватывают тесно связанные темы, расширяющие техники, продемонстрированные в этом руководстве. Каждый ресурс включает полностью работающие примеры кода с пошаговыми объяснениями, помогающими освоить дополнительные возможности API и исследовать альтернативные подходы в ваших проектах.

- [Create barcode PNG in C# – full guide to GS1 Micro PDF417](/barcode/english/net/gs1-barcode-encoding/create-barcode-png-in-c-full-guide-to-gs1-micro-pdf417/)
- [How to generate micro pdf417 barcode in C# – step‑by‑step guide](/barcode/english/net/compact-pdf417-encoding/how-to-generate-micro-pdf417-barcode-in-c-step-by-step-guide/)
- [How to create PDF417 barcode image in C# with Macro PDF417 options](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-image-in-c-with-macro-pdf417-op/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}