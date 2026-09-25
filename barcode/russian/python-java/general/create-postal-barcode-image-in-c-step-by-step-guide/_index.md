---
category: general
date: 2026-08-03
description: Создайте изображение почтового штрихкода на C# быстро. Узнайте, как генерировать
  почтовый штрихкод, задавать размеры штрихкода и создавать штрихкод Planet.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create postal barcode image
- how to generate postal barcode
- generate planet barcode
- how to set barcode dimensions
language: ru
lastmod: 2026-08-03
og_description: Создайте изображение почтового штрихкода на C# с помощью этого полного
  руководства; узнайте, как задавать размеры штрихкода, генерировать штрихкод Planet
  и создавать штрихкоды RM4SCC.
og_image_alt: Generated postal barcode image saved as PNG using C# BarcodeGenerator
og_title: Создание изображения почтового штрихкода в C# – полное руководство по программированию
schemas:
- author: Aspose
  dateModified: '2026-08-03'
  description: Create postal barcode image in C# quickly. Learn how to generate postal
    barcode, set barcode dimensions, and generate a Planet barcode.
  headline: Create postal barcode image in C# – step‑by‑step guide
  type: TechArticle
tags:
- barcode
- C#
- postal barcode
title: Создание изображения почтового штрихкода в C# – пошаговое руководство
url: /ru/python-java/general/create-postal-barcode-image-in-c-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Создание изображения почтового штрих‑кода в C# – пошаговое руководство

Если вам нужно **создать изображение почтового штрих‑кода** в C#, это руководство покажет, как это сделать. Мы рассмотрим **как генерировать почтовый штрих‑код**, **как задать размеры штрих‑кода** и как **создать штрих‑код Planet** для распространённых почтовых стандартов.

В конце вы получите два готовых PNG‑файла — один штрих‑код Planet и один штрих‑код RM4SCC — каждый высотой 100 px. Дополнительные инструменты не требуются, кроме библиотеки Aspose.BarCode для .NET.

## Требования

* .NET 6 SDK или новее (код также работает с .NET Framework 4.7+)
* Visual Studio 2022 или любой IDE для C#
* NuGet‑пакет **Aspose.BarCode** (библиотека, предоставляющая `BarcodeGenerator`)

## Шаг 1: Установить библиотеку штрих‑кодов

Откройте терминал в папке проекта и выполните:

```bash
dotnet add package Aspose.BarCode
```

Пакет добавляет пространство имён `Aspose.BarCode`, которое содержит `BarcodeGenerator` и перечисление `EncodeTypes`, необходимое для почтовых штрих‑кодов.

## Шаг 2: Определить папку вывода

Создание надёжного пути вывода предотвращает ошибки выполнения, когда папка не существует.

```csharp
using System;
using System.IO;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class PostalBarcodeDemo
{
    static void Main()
    {
        // Ensure the directory exists
        string outputFolder = Path.Combine(Directory.GetCurrentDirectory(), "Barcodes");
        Directory.CreateDirectory(outputFolder);
```

*Почему это важно*: `Directory.CreateDirectory` идемпотентен — он создаёт папку только если её ещё нет, избегая исключений при последующих запусках.

## Шаг 3: Настроить общие размеры штрих‑кода

Установка X‑размера (ширины отдельного бара) и общей высоты бара позволяет контролировать визуальный размер генерируемого изображения.

```csharp
        // Common dimension settings
        const int xDimensionPixels = 4;   // Width of a single bar
        const int barHeightPixels = 100; // Desired barcode height
```

**Как задать размеры штрих‑кода**: свойство `Parameters.Barcode.XDimension.Pixels` определяет ширину узкого бара, а `Parameters.Barcode.BarHeight.Pixels` — полную высоту. Отрегулируйте эти значения в соответствии со спецификациями вашей почтовой службы.

## Шаг 4: Сгенерировать штрих‑код Planet

Planet — широко используемый почтовый штрих‑код в Великобритании. Ниже приведён код, который создаёт штрих‑код Planet высотой 100 px и сохраняет его как PNG.

```csharp
        // Step 4: Generate Planet barcode
        BarcodeGenerator planetGenerator = new BarcodeGenerator(EncodeTypes.Planet, "123456");
        planetGenerator.Parameters.Barcode.XDimension.Pixels = xDimensionPixels;
        planetGenerator.Parameters.Barcode.BarHeight.Pixels = barHeightPixels;

        string planetPath = Path.Combine(outputFolder, "PostalPlanetBarHeight100Pixels.png");
        planetGenerator.Save(planetPath, BarCodeImageFormat.Png);
```

**Почему это работает**: `EncodeTypes.Planet` указывает генератору использовать симбологию Planet. Метод `Save` записывает PNG‑файл по указанному пути, сохраняя ранее заданные размеры.

## Шаг 5: Сгенерировать штрих‑код RM4SCC

RM4SCC — нидерландский стандарт почтовых штрих‑кодов. Приведённый ниже код повторяет пример с Planet, демонстрируя **как генерировать почтовый штрих‑код** другого типа с теми же размерами.

```csharp
        // Step 5: Generate RM4SCC barcode
        BarcodeGenerator rm4sccGenerator = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");
        rm4sccGenerator.Parameters.Barcode.XDimension.Pixels = xDimensionPixels;
        rm4sccGenerator.Parameters.Barcode.BarHeight.Pixels = barHeightPixels;

        string rm4sccPath = Path.Combine(outputFolder, "PostalRM4SCCBarHeight100Pixels.png");
        rm4sccGenerator.Save(rm4sccPath, BarCodeImageFormat.Png);
```

Оба PNG‑файла теперь находятся в папке `Barcodes`. При открытии вы увидите чистые штрих‑коды высотой 100 px, готовые к печати или встраиванию в документы.

## Полный исходный код

Ниже представлена полная, готовая к запуску программа, которая **создаёт изображения почтовых штрих‑кодов** для стандартов Planet и RM4SCC.

```csharp
using System;
using System.IO;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class PostalBarcodeDemo
{
    static void Main()
    {
        // Ensure output directory exists
        string outputFolder = Path.Combine(Directory.GetCurrentDirectory(), "Barcodes");
        Directory.CreateDirectory(outputFolder);

        // Dimension settings – reusable for all barcodes
        const int xDimensionPixels = 4;   // Width of a single bar
        const int barHeightPixels = 100; // Height of the barcode

        // ---- Generate Planet barcode ----
        BarcodeGenerator planetGenerator = new BarcodeGenerator(EncodeTypes.Planet, "123456");
        planetGenerator.Parameters.Barcode.XDimension.Pixels = xDimensionPixels;
        planetGenerator.Parameters.Barcode.BarHeight.Pixels = barHeightPixels;
        string planetPath = Path.Combine(outputFolder, "PostalPlanetBarHeight100Pixels.png");
        planetGenerator.Save(planetPath, BarCodeImageFormat.Png);

        // ---- Generate RM4SCC barcode ----
        BarcodeGenerator rm4sccGenerator = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");
        rm4sccGenerator.Parameters.Barcode.XDimension.Pixels = xDimensionPixels;
        rm4sccGenerator.Parameters.Barcode.BarHeight.Pixels = barHeightPixels;
        string rm4sccPath = Path.Combine(outputFolder, "PostalRM4SCCBarHeight100Pixels.png");
        rm4sccGenerator.Save(rm4sccPath, BarCodeImageFormat.Png);

        Console.WriteLine("Barcodes generated:");
        Console.WriteLine($"• {planetPath}");
        Console.WriteLine($"• {rm4sccPath}");
    }
}
```

### Ожидаемый вывод

Запуск программы выводит пути к файлам и создаёт два PNG‑файла:

```
Barcodes/
 ├─ PostalPlanetBarHeight100Pixels.png
 └─ PostalRM4SCCBarHeight100Pixels.png
```

Каждое изображение высотой 100 px, ширина узкого бара — 4 пикселя, что соответствует заданным размерам.

## Практические советы и распространённые подводные камни

* **Разрешения папки** — если программа запускается под ограничённой учётной записью, убедитесь, что целевая папка доступна для записи.
* **Другие размеры** — чтобы получить более высокий штрих‑код, увеличьте `barHeightPixels`. Для более высокой детализации уменьшите `xDimensionPixels`, но оставьте значение ≥ 2, чтобы избежать артефактов рендеринга.
* **Другие почтовые симбологии** — Aspose.BarCode также поддерживает `EncodeTypes.Postnet` и `EncodeTypes.AustralianPost`. Поменяйте значение `EncodeTypes`, оставив ту же логику размеров.
* **Формат изображения** — используйте `BarCodeImageFormat.Jpeg` для уменьшения размера файла, если не требуется безупречное качество.

## Заключение

Теперь вы знаете, как **создавать изображения почтовых штрих‑кодов** в C# путем настройки размеров, выбора нужной симбологии и сохранения результата в PNG. В руководстве рассмотрено **как генерировать почтовый штрих‑код**, продемонстрировано **генерирование штрих‑кода Planet** и объяснено **как задать размеры штрих‑кода** для получения согласованного вывода.

Далее изучайте **кастомизацию цветов штрих‑кода**, добавление **читаемого человеком текста** или интеграцию изображений в PDF‑счета. Тот же шаблон применим к любому другому типу штрих‑кода, поддерживаемому Aspose.BarCode, позволяя расширить решение до полной автоматизации почтовых процессов.


## Что изучать дальше?


Следующие руководства охватывают близкие темы, опираясь на техники, продемонстрированные в этом руководстве. Каждый ресурс содержит полностью работающие примеры кода с пошаговыми объяснениями, помогающими освоить дополнительные возможности API и исследовать альтернативные подходы реализации в ваших проектах.

- [How to Generate Barcode - One-Dimensional Barcode Types](/barcode/english/net/one-dimensional-barcode-types/)
- [How to generate Aztec barcode with custom aspect ratio using Aspose.BarCode for .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)
- [How to generate barcode java – Australia Post Barcode with Aspose](/barcode/english/java/barcode-configuration/generating-australia-post-barcode/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}