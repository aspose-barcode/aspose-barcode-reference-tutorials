---
category: general
date: 2026-07-27
description: Создайте штрих‑код с данными в C# быстро. Узнайте, как создать PDF417‑штрих‑код
  в C# с помощью Aspose.BarCode, задать размеры и сохранить в PNG.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode with data
- create pdf417 barcode c#
language: ru
lastmod: 2026-07-27
og_description: Создайте штрих‑код с данными в C# с использованием Aspose.BarCode.
  Это руководство показывает, как создать штрих‑код PDF417 на C# с пользовательскими
  настройками и сохранить его в формате PNG.
og_image_alt: Screenshot of a barcode created with data in a C# application
og_title: Создание штрихкода с данными в C# — Полный пошаговый разбор
schemas:
- author: Aspose
  dateModified: '2026-07-27'
  description: Create barcode with data in C# quickly. Learn how to create PDF417
    barcode c# using Aspose.BarCode, set dimensions, and save as PNG.
  headline: Create barcode with data in C# – Step‑by‑Step Guide
  type: TechArticle
- description: Create barcode with data in C# quickly. Learn how to create PDF417
    barcode c# using Aspose.BarCode, set dimensions, and save as PNG.
  name: Create barcode with data in C# – Step‑by‑Step Guide
  steps:
  - name: Initialising `BarcodeGenerator` with MicroPdf417 and a Unicode string.
    text: Initialising `BarcodeGenerator` with MicroPdf417 and a Unicode string.
  - name: Tweaking the X‑dimension for finer resolution.
    text: Tweaking the X‑dimension for finer resolution.
  - name: Limiting columns to keep the barcode compact.
    text: Limiting columns to keep the barcode compact.
  - name: Saving the result as a PNG file.
    text: Saving the result as a PNG file.
  type: HowTo
tags:
- barcode
- C#
- Aspose
title: Создание штрих‑кода с данными в C# — пошаговое руководство
url: /ru/net/compact-pdf417-encoding/create-barcode-with-data-in-c-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Создание штрих‑кода с данными в C# – Полный пошаговый пример

Когда‑нибудь нужно было **создать штрих‑код с данными** в .NET‑приложении, но не было уверенности, какие вызовы API использовать? Вы не одиноки. Будь то маркировка инвентаря, печать билетов или встраивание информации в мобильный сканер, умение создавать штрих‑коды – полезный навык для любого разработчика C#.

В этом руководстве мы пройдём практический пример, показывающий, как **create PDF417 barcode c#** с помощью библиотеки Aspose.BarCode, настроить ширину модуля, ограничить количество столбцов и, наконец, сохранить результат в PNG‑файл. К концу вы получите полностью готовую консольную программу, которую можно сразу добавить в любой проект.

## Prerequisites — Что понадобится

- **.NET 6.0** или новее (код также работает с .NET Framework 4.7+)  
- **Aspose.BarCode for .NET** NuGet‑пакет (`Install-Package Aspose.BarCode`)  
- Редактор кода или IDE (Visual Studio, VS Code, Rider – выбирайте свой)  
- Права записи в папку, куда будет сохраняться PNG  

Дополнительные файлы конфигурации не требуются; библиотека самодостаточна.

## Шаг 1: Создание проекта и импорт пространств имён

Сначала создайте новый консольный проект (или откройте существующий) и добавьте ссылку на Aspose.BarCode.

```csharp
// Program.cs – entry point
using System;
using Aspose.BarCode.Generation;   // Core generator classes
using Aspose.BarCode;               // For BarCodeImageFormat enum

namespace BarcodeDemo
{
    class Program
    {
        static void Main(string[] args)
        {
            // We'll place the barcode generation logic here.
        }
    }
}
```

> **Почему это важно:** Импорт нужных пространств имён даёт доступ к `BarcodeGenerator` и связанным настройкам без необходимости полностью квалифицировать каждый тип. Это также делает код чище для будущего обслуживания.

## Шаг 2: Инициализация генератора штрих‑кода с вашими данными

Теперь мы действительно **create barcode with data**. Конструктор `BarcodeGenerator` принимает два аргумента: тип символьности (`EncodeTypes.MicroPdf417`) и строку, которую нужно закодировать.

```csharp
// Inside Main()
string dataToEncode = "Åspóse.Barcóde©";   // Example containing Unicode characters
var generator = new BarcodeGenerator(EncodeTypes.MicroPdf417, dataToEncode);
```

> **Подсказка:** Символьность MicroPdf417 – это компактная версия PDF417, идеальная, когда нужен меньший размер изображения, но при этом высокая ёмкость данных. Библиотека поддерживает Unicode «из коробки», так что символы вроде “Å” и “©” работают без проблем.

## Шаг 3: Точная настройка X‑размера (ширина модуля)

Если требуется более чёткое, высокоразрешённое изображение, можно уменьшить ширину модуля. Установка **2 пикселей** даёт более тонкую сетку без значительного роста размера файла.

```csharp
// Adjust the module (X‑dimension) to 2 pixels
generator.Parameters.Barcode.XDimension.Pixels = 2;
```

> **Зачем менять X‑размер?** Меньший X‑размер делает каждую полосу уже, что улучшает читаемость на сканерах высокого разрешения, сохраняя общий размер штрих‑кода приемлемым.

## Шаг 4: Ограничение количества столбцов PDF417 (необязательно, но часто)

PDF417 позволяет задавать число столбцов. Для MicroPdf417 максимум – **4**, что делает штрих‑код коротким и широким.

```csharp
// Set the column count to the maximum allowed (4)
generator.Parameters.Barcode.Pdf417.Columns = 4;
```

> **Особый случай:** Если задать количество столбцов выше допустимого максимума, Aspose автоматически ограничит его, но рекомендуется придерживаться документированного диапазона, чтобы избежать неожиданного масштабирования.

## Шаг 5: Сохранение штрих‑кода в PNG‑изображение

Наконец, запишем сгенерированное изображение на диск. Метод `Save` принимает полный путь и желаемый формат изображения.

```csharp
// Define output path – adjust as needed
string outputPath = @"C:\Temp\MicroPdf417.png";

// Save as PNG (lossless, widely supported)
generator.Save(outputPath, BarCodeImageFormat.Png);

Console.WriteLine($"Barcode saved to {outputPath}");
```

> **Профессиональный совет:** PNG сохраняет точные пиксельные данные, что критично для штрих‑кодов. Если нужен векторный формат для масштабирования, замените `BarCodeImageFormat.Png` на `BarCodeImageFormat.Svg`.

### Полный рабочий пример

Собрав всё вместе, получаем готовую к копированию и вставке программу:

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

namespace BarcodeDemo
{
    class Program
    {
        static void Main(string[] args)
        {
            // 1️⃣ Data we want to encode – includes special characters
            string dataToEncode = "Åspóse.Barcóde©";

            // 2️⃣ Initialise generator with MicroPdf417 symbology
            var generator = new BarcodeGenerator(EncodeTypes.MicroPdf417, dataToEncode);

            // 3️⃣ Fine‑tune resolution – 2‑pixel modules
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // 4️⃣ Use the maximum of 4 columns for a compact barcode
            generator.Parameters.Barcode.Pdf417.Columns = 4;

            // 5️⃣ Save the image
            string outputPath = @"C:\Temp\MicroPdf417.png";
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"✅ Barcode created successfully! Saved at: {outputPath}");
        }
    }
}
```

Запуск этой программы создаёт PNG‑файл, выглядящий примерно так:

![Barcode created with data in C#](barcode-sample.png "Screenshot of a barcode created with data in a C# application")

*Изображение выше – лишь пример; ваш реальный штрих‑код будет содержать точную строку “Åspóse.Barcóde©”.*

## Часто задаваемые вопросы и особые случаи

| Question | Answer |
|----------|--------|
| *What if my data exceeds MicroPdf417 capacity?* | Switch to `EncodeTypes.Pdf417` (regular PDF417) which supports up to 1 800 characters. |
| *Can I change the image format to JPEG?* | Yes—replace `BarCodeImageFormat.Png` with `BarCodeImageFormat.Jpeg`. Remember JPEG is lossy; it may affect scanner reliability. |
| *Do I need to handle Unicode manually?* | No. Aspose.BarCode automatically encodes Unicode characters, but ensure your source file is saved with UTF‑8 encoding. |
| *What if I need a transparent background?* | Set `generator.Parameters.Barcode.BackgroundColor = System.Drawing.Color.Transparent;` before saving. |
| *Is there a way to generate the barcode in memory?* | Call `generator.GenerateBarCodeImage()` to get a `System.Drawing.Image` object you can stream directly. |

## Итоги – Что мы изучили

Мы продемонстрировали, как **create barcode with data** в C#:

1. Инициализировали `BarcodeGenerator` с MicroPdf417 и строкой Unicode.  
2. Настроили X‑размер для более высокой детализации.  
3. Ограничили количество столбцов, чтобы штрих‑код оставался компактным.  
4. Сохранили результат в PNG‑файл.

Все эти шаги отвечают на основной запрос «how to **create PDF417 barcode c#**», одновременно показывая, как настраивать часто используемые параметры.

## Следующие шаги и смежные темы

- **Add human‑readable text** below the barcode using `generator.Parameters.Barcode.CodeTextParameters`.  
- **Embed the PNG in a PDF** with `Aspose.Pdf` for printable reports.  
- **Generate other symbologies** (QR, Code128, DataMatrix) by swapping `EncodeTypes`.  
- **Batch processing** – loop over a CSV of product IDs and output a folder of barcodes.

Экспериментируйте с количеством столбцов, уровнем коррекции ошибок и цветовыми схемами. Как только почувствуете уверенность, сможете создавать полноценные решения маркировки, которые без проблем интегрируются с системами учёта или билетными сервисами.

Счастливого кодинга, и пусть ваши сканирования всегда проходят без ошибок!

## Что изучать дальше?

Следующие руководства охватывают тесно связанные темы, расширяющие техники, продемонстрированные в этом пособии. Каждый ресурс содержит полностью работающие примеры кода с пошаговыми объяснениями, помогающими освоить дополнительные возможности API и исследовать альтернативные подходы в ваших проектах.

- [Как создать штрих‑код – компактный PDF417 с Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [Создание изображения штрих‑кода DotCode – строки и столбцы (Aspose.BarCode)](/barcode/english/net/dotcode-barcode-configuration/dotcode-rows-columns-configuration/)
- [Создание PNG‑штрих‑кода – соотношение сторон DataMatrix – Aspose.BarCode](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-aspect-ratio-customization/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}