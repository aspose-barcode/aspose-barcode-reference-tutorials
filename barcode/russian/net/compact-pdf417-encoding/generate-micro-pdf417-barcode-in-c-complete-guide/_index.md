---
category: general
date: 2026-07-18
description: Генерация микроштрихкода micro PDF417 с помощью Aspose.BarCode для .NET —
  пошаговое руководство, охватывающее столбцы, строки и вывод в PNG.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate micro pdf417 barcode
- Aspose.BarCode for .NET
- MicroPdf417 columns
- MicroPdf417 rows
- C# barcode generation
language: ru
lastmod: 2026-07-18
og_description: Создавайте микробар‑код micro PDF417 мгновенно с помощью Aspose.BarCode
  для .NET. Узнайте, как управлять столбцами, строками и сохранять в PNG за считанные
  минуты.
og_image_alt: Screenshot of a generated Micro PDF417 barcode saved as PNG
og_title: Создание микробаркода PDF417 – Полный учебник C#
schemas:
- author: Aspose
  dateModified: '2026-07-18'
  description: Generate micro pdf417 barcode with Aspose.BarCode for .NET – step‑by‑step
    guide covering columns, rows, and PNG output.
  headline: Generate Micro PDF417 Barcode in C# – Complete Guide
  type: TechArticle
- description: Generate micro pdf417 barcode with Aspose.BarCode for .NET – step‑by‑step
    guide covering columns, rows, and PNG output.
  name: Generate Micro PDF417 Barcode in C# – Complete Guide
  steps:
  - name: 4.1 Two Columns, Auto‑Calculated Rows
    text: '```csharp // Force 2 columns, let rows auto‑adjust generator.Parameters.Barcode.Pdf417.Columns
      = 2; generator.Parameters.Barcode.Pdf417.Rows = 0; // 0 = auto generator.Save("MicroPdf417Columns2.png",
      BarCodeImageFormat.Png); Console.WriteLine("Saved: MicroPdf417Columns2.png");
      ```'
  - name: 4.2 Six Rows, Auto‑Calculated Columns
    text: '```csharp // Switch to 6 rows, columns auto‑determined generator.Parameters.Barcode.Pdf417.Columns
      = 0; // auto columns generator.Parameters.Barcode.Pdf417.Rows = 6; generator.Save("MicroPdf417Rows6.png",
      BarCodeImageFormat.Png); Console.WriteLine("Saved: MicroPdf417Rows6.png"); ```'
  - name: 4.3 Four Columns × Eight Rows (Fully Specified)
    text: '```csharp // Explicitly set both columns and rows generator.Parameters.Barcode.Pdf417.Columns
      = 4; generator.Parameters.Barcode.Pdf417.Rows = 8; generator.Save("MicroPdf417Rows8Columns4.png",
      BarCodeImageFormat.Png); Console.WriteLine("Saved: MicroPdf417Rows8Columns4.png");
      ```'
  - name: Expected Output
    text: 'Running the program produces three PNG files:'
  type: HowTo
- questions:
  - answer: Call `Directory.CreateDirectory(path)` before the first `Save` to avoid
      a `DirectoryNotFoundException`.
    question: What if the output folder doesn’t exist?
  - answer: Absolutely. Replace `BarCodeImageFormat.Png` with `Jpeg`, `Bmp`, or `Gif`
      as needed.
    question: Can I change the image format?
  - answer: MicroPdf417 can encode up to 1 KB of data, but practical limits depend
      on the chosen rows/columns. If you hit an error, increase rows or columns.
    question: Is there a limit to the text length?
  - answer: Use Aspose.Pdf to insert the generated PNG, or switch to `BarCodeImageFormat.Pdf`
      for a direct PDF output.
    question: How do I embed the barcode in a PDF?
  type: FAQPage
tags:
- barcode
- C#
- Aspose
title: Генерация микроштрихкода PDF417 в C# — Полное руководство
url: /ru/net/compact-pdf417-encoding/generate-micro-pdf417-barcode-in-c-complete-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Генерация микробарcode Micro PDF417 в C# – Полное руководство

Когда‑нибудь задумывались, как **generate micro pdf417 barcode** напрямую из вашего C# приложения? Вы не одиноки. Независимо от того, маркируете ли вы инвентарь, кодируете короткие URL‑адреса или создаёте собственное решение для сканирования, освоение этого крошечного, но мощного 2‑D кода может сэкономить вам массу хлопот.

В этом руководстве мы пройдем реальный пример с использованием **Aspose.BarCode for .NET**, покажем, как настроить столбцы, строки и размер модуля, а затем сохранить результат в PNG‑файл. К концу у вас будет готовое консольное приложение, которое генерирует три разных изображения штрих‑кода — без загадок.

## Что понадобится

- .NET 6 или новее (код также работает на .NET Framework 4.7+)
- Visual Studio 2022 (или любая другая IDE для C#)
- NuGet‑пакет **Aspose.BarCode** (`Aspose.BarCode`)
- Папка с правом записи на диске для выходных PNG‑файлов

Если всё уже есть — отлично, приступаем.

## Шаг 1: Создание проекта и установка Aspose.BarCode

Сначала создайте новый консольный проект:

```bash
dotnet new console -n MicroPdf417Demo
cd MicroPdf417Demo
dotnet add package Aspose.BarCode
```

> **Pro tip:** После добавления пакета выполните `dotnet restore`, чтобы убедиться, что все зависимости разрешены.

Теперь откройте `Program.cs`. Начнём с подключения необходимых пространств имён:

```csharp
using System;
using Aspose.BarCode.Generation;
```

Эти два оператора `using` дают доступ к `BarcodeGenerator`, `EncodeTypes` и перечислению форматов изображений, которое понадобится позже.

## Шаг 2: Инициализация генератора MicroPdf417

Сердцем операции является объект `BarcodeGenerator`. Мы передаём ему тип кодирования **MicroPdf417** и текст, который хотим закодировать — в нашем случае слово «ASPOSE».

```csharp
// Initialise generator with MicroPdf417 and sample text
var generator = new BarcodeGenerator(EncodeTypes.MicroPdf417, "ASPOSE");
```

Почему `MicroPdf417`? По сравнению с полноразмерным PDF417, микровариант упаковывает больше данных в меньший размер, что идеально для этикеток с ограниченным пространством.

## Шаг 3: Настройка размера модуля (X‑Dimension)

Размер модуля определяет, сколько пикселей занимает каждый крошечный квадрат штрих‑кода. Значение **2 пикселя** даёт чёткое, читаемое изображение без увеличения размера файла.

```csharp
// Set X‑dimension to 2 pixels per module
generator.Parameters.Barcode.XDimension.Pixels = 2;
```

> **Note:** Если нужен более крупный штрих‑код для сканирования с расстояния, увеличьте это значение до 3 или 4.

## Шаг 4: Генерация штрих‑кодов с разными конфигурациями столбцов/строк

### 4.1 Два столбца, авторасчёт строк

```csharp
// Force 2 columns, let rows auto‑adjust
generator.Parameters.Barcode.Pdf417.Columns = 2;
generator.Parameters.Barcode.Pdf417.Rows = 0; // 0 = auto
generator.Save("MicroPdf417Columns2.png", BarCodeImageFormat.Png);
Console.WriteLine("Saved: MicroPdf417Columns2.png");
```

### 4.2 Шесть строк, авторасчёт столбцов

```csharp
// Switch to 6 rows, columns auto‑determined
generator.Parameters.Barcode.Pdf417.Columns = 0; // auto columns
generator.Parameters.Barcode.Pdf417.Rows = 6;
generator.Save("MicroPdf417Rows6.png", BarCodeImageFormat.Png);
Console.WriteLine("Saved: MicroPdf417Rows6.png");
```

### 4.3 Четыре столбца × восемь строк (полностью задано)

```csharp
// Explicitly set both columns and rows
generator.Parameters.Barcode.Pdf417.Columns = 4;
generator.Parameters.Barcode.Pdf417.Rows = 8;
generator.Save("MicroPdf417Rows8Columns4.png", BarCodeImageFormat.Png);
Console.WriteLine("Saved: MicroPdf417Rows8Columns4.png");
```

Каждый вызов `Save` записывает PNG‑файл в рабочий каталог проекта. При желании измените путь (`"YOUR_DIRECTORY/..."`) на что‑то вроде `Path.Combine(Environment.CurrentDirectory, "output")`, если предпочитаете отдельную папку.

## Шаг 5: Полный рабочий пример

Объединив всё вместе, получаем готовую к копированию и вставке программу:

```csharp
using System;
using Aspose.BarCode.Generation;

namespace MicroPdf417Demo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Initialise generator with MicroPdf417 and sample text
            var generator = new BarcodeGenerator(EncodeTypes.MicroPdf417, "ASPOSE");

            // 2️⃣ Set module size – 2 pixels per module for a sharp image
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // 3️⃣ Create three variants with different column/row settings

            // Variant A – 2 columns, rows auto‑adjust
            generator.Parameters.Barcode.Pdf417.Columns = 2;
            generator.Parameters.Barcode.Pdf417.Rows = 0; // auto rows
            generator.Save("MicroPdf417Columns2.png", BarCodeImageFormat.Png);
            Console.WriteLine("Saved: MicroPdf417Columns2.png");

            // Variant B – 6 rows, columns auto‑determine
            generator.Parameters.Barcode.Pdf417.Columns = 0; // auto columns
            generator.Parameters.Barcode.Pdf417.Rows = 6;
            generator.Save("MicroPdf417Rows6.png", BarCodeImageFormat.Png);
            Console.WriteLine("Saved: MicroPdf417Rows6.png");

            // Variant C – 4 columns × 8 rows (full control)
            generator.Parameters.Barcode.Pdf417.Columns = 4;
            generator.Parameters.Barcode.Pdf417.Rows = 8;
            generator.Save("MicroPdf417Rows8Columns4.png", BarCodeImageFormat.Png);
            Console.WriteLine("Saved: MicroPdf417Rows8Columns4.png");

            Console.WriteLine("All barcodes generated successfully!");
        }
    }
}
```

### Ожидаемый результат

Запуск программы создаёт три PNG‑файла:

| Имя файла | Примерные размеры (px) | Визуальная подсказка |
|-----------|------------------------|----------------------|
| `MicroPdf417Columns2.png` | 180 × 120 | Узкий, более высокий штрих‑код |
| `MicroPdf417Rows6.png` | 120 × 180 | Широкий, более короткий штрих‑код |
| `MicroPdf417Rows8Columns4.png` | 160 × 160 | Почти квадратный, сбалансированный макет |

Откройте любой из них в просмотрщике изображений — вы увидите чёткий **Micro PDF417** штрих‑код, готовый к сканированию.

## Часто задаваемые вопросы и особые случаи

- **Что делать, если папка вывода не существует?**  
  Вызовите `Directory.CreateDirectory(path)` перед первым `Save`, чтобы избежать `DirectoryNotFoundException`.

- **Можно ли изменить формат изображения?**  
  Конечно. Замените `BarCodeImageFormat.Png` на `Jpeg`, `Bmp` или `Gif` по необходимости.

- **Есть ли ограничение на длину текста?**  
  MicroPdf417 может закодировать до 1 KB данных, но практические ограничения зависят от выбранных строк/столбцов. Если возникнет ошибка, увеличьте количество строк или столбцов.

- **Как встроить штрих‑код в PDF?**  
  Используйте Aspose.Pdf для вставки сгенерированного PNG, либо переключитесь на `BarCodeImageFormat.Pdf` для прямого вывода в PDF.

## Pro Tips для генерации штрих‑кодов в C#

1. **Кешируйте генератор**, когда нужно создавать много штрих‑кодов с одинаковыми настройками — меняется только текст, что экономит процессорные ресурсы.  
2. **Точно настраивайте уровень коррекции ошибок** через `generator.Parameters.Barcode.Pdf417.ErrorLevel`, если среда сканирования шумная.  
3. **Тестируйте на реальных сканерах** как можно раньше. Некоторые портативные устройства плохо читают очень плотные микроштрих‑коды; регулировка `XDimension` может существенно помочь.

## Заключение

Теперь вы знаете, как **generate micro pdf417 barcode** с помощью **Aspose.BarCode for .NET**, управлять **MicroPdf417 columns** и **MicroPdf417 rows**, а также сохранять результат в PNG‑файлы — всё из одного компактного C# консольного приложения. Экспериментируйте с различными размерами модуля, уровнями коррекции ошибок или даже цветным выводом, чтобы подобрать оптимальное решение для вашего проекта.

Далее вы можете изучить **C# barcode generation** для других символогий, таких как QR, Code128 или DataMatrix, либо напрямую внедрять изображения в PDF с помощью Aspose.Pdf. Возможности безграничны, когда базовые навыки под контролем.

Счастливого кодинга, и пусть ваши сканирования всегда проходят без ошибок!

## Что изучать дальше?

Следующие руководства охватывают тесно связанные темы, расширяющие техники, продемонстрированные в этом пособии. Каждый ресурс содержит полностью рабочие примеры кода с пошаговыми объяснениями, помогающими освоить дополнительные возможности API и исследовать альтернативные подходы в ваших проектах.

- [How to Create Barcode – Compact PDF417 with Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [Create DotCode barcode image – rows & columns (Aspose.BarCode)](/barcode/english/net/dotcode-barcode-configuration/dotcode-rows-columns-configuration/)
- [Generate DataMatrix Barcode – Pro Guide with Aspose.BarCode](/barcode/english/net/datamatrix-barcode-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}