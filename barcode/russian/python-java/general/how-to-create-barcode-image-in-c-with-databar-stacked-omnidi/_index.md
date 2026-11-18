---
category: general
date: 2026-11-17
description: Создайте изображение штрих‑кода в C# с использованием библиотеки Barcode
  Generator. Следуйте этому руководству, чтобы пошагово узнать, как генерировать коды
  DataBar stacked omnidirectional.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode image
- barcode generator c#
- how to generate databar
language: ru
lastmod: 2026-11-17
og_description: Создайте изображение штрихкода в C# с кратким примером. Узнайте, как
  генерировать многослойные всенаправленные штрихкоды DataBar с помощью библиотеки
  Barcode Generator.
og_image_alt: Screenshot showing a generated barcode image created with C# code
og_title: Создайте изображение штрихкода в C# — полное руководство по кодам DataBar
schemas:
- author: Aspose
  dateModified: '2026-11-17'
  description: Create barcode image in C# using the Barcode Generator library. Follow
    this guide to learn how to generate DataBar stacked omnidirectional codes step‑by‑step.
  headline: How to create barcode image in C# with DataBar stacked omnidirectional
  type: TechArticle
tags:
- barcode
- C#
- Aspose.BarCode
title: Как создать изображение штрихкода в C# с DataBar stacked omnidirectional
url: /ru/python-java/general/how-to-create-barcode-image-in-c-with-databar-stacked-omnidi/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Как создать изображение штрих‑кода в C# с DataBar stacked omnidirectional

Если вам нужно **создать изображение штрих‑кода** в приложении .NET, этот учебник покажет вам полное, готовое к запуску решение. Вы увидите, как использовать API **Barcode Generator C#** для создания stacked omnidirectional DataBar, который является форматом, рассматриваемым в запросе *how to generate databar*.

Руководство проходит через каждый необходимый шаг — от установки библиотеки до точной настройки соотношения сторон — чтобы вы могли скопировать код, запустить его и сразу получить PNG‑файл. Обращение к внешней документации не требуется.

## Предварительные требования

* .NET 6.0 SDK или более поздняя версия (пример также работает с .NET Framework 4.7+)
* Среда разработки, например Visual Studio 2022 или VS Code
* NuGet‑пакет **Aspose.BarCode for .NET** (библиотека, предоставляющая `BarcodeGenerator`)

Вы можете добавить пакет следующей командой:

```bash
dotnet add package Aspose.BarCode
```

> **Pro tip:** Используйте флаг `--version`, чтобы зафиксировать пакет на последней стабильной версии, например `dotnet add package Aspose.BarCode --version 23.9`.

## Шаг 1: Настройка проекта и импорт пространств имён

Создайте новый консольный проект и подключите необходимые пространства имён. Этот шаг подготавливает окружение для кода **barcode generator c#**, который следует далее.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // All barcode generation logic lives here
```

Пространство имён `Aspose.BarCode.Generation` содержит класс `BarcodeGenerator`, который является ядром рабочего процесса **создание изображения штрих‑кода**.

## Шаг 2: Инициализация BarcodeGenerator для stacked omnidirectional DataBar

Генератору нужны две части информации: тип штрих‑кода и данные для кодирования. Значение перечисления `EncodeTypes.DatabarStackedOmniDirectional` выбирает точный вариант DataBar, требуемый в сценариях *how to generate databar*.

```csharp
            // Step 2: Create a barcode generator for a stacked omnidirectional DataBar
            BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
                EncodeTypes.DatabarStackedOmniDirectional,
                "(01)12345678901231"); // Example GTIN-14 payload
```

*Почему это важно:* Выбор правильного значения `EncodeTypes` гарантирует, что полученное изображение соответствует отраслевым спецификациям для розничного сканирования.

## Шаг 3: Определение размера модуля (X‑dimension) в пикселях

Плотность визуального представления штрих‑кода контролируется X‑dimension. Установка разумного пиксельного значения гарантирует читаемость изображения как на экране, так и при печати.

```csharp
            // Step 3: Define the module size (X‑dimension) in pixels
            barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

Если нужен более крупный штрих‑код для печати с низким разрешением, увеличьте значение пикселей соответственно.

## Шаг 4: Регулировка соотношения сторон DataBar для увеличения высоты строк

Stacked omnidirectional DataBar состоит из двух строк. Изменение `AspectRatio` позволяет управлять высотой каждой строки, что может быть полезно, когда стандартный размер выглядит слишком сжатым.

```csharp
            // Step 4: Adjust the DataBar aspect ratio to make rows taller
            barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 15;
```

Соотношение сторон `15` часто используется для розничных этикеток; вы можете экспериментировать со значениями от `10` до `20`, чтобы удовлетворить конкретные требования к макету.

## Шаг 5: Сохранение сгенерированного штрих‑кода в виде PNG‑изображения

Наконец, запишите изображение на диск. PNG — без потерь, что делает его идеальным для последующей обработки или встраивания в PDF‑файлы.

```csharp
            // Step 5: Save the generated barcode as a PNG image
            string outputPath = "DatabarAspectRatio15.png";
            barcodeGenerator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"Barcode image saved to {outputPath}");
        }
    }
}
```

Запуск программы создаёт файл **DatabarAspectRatio15.png** в выходном каталоге проекта. Открытие файла показывает чистый, контрастный штрих‑код, готовый к сканированию.

### Ожидаемый результат

Сохранённое изображение выглядит аналогично иллюстрации ниже (само изображение опущено для краткости).

*Alt text for the example image:* **create barcode image** – PNG‑файл, отображающий stacked omnidirectional DataBar с соотношением сторон 15.

## Общие варианты и граничные случаи

| Ситуация | Корректировка |
|-----------|------------|
| **Different payload length** | Замените строку GTIN любой действительной DataBar‑информацией (например, `(01)01234567890123`). |
| **Higher resolution for large prints** | Увеличьте `XDimension.Pixels` до 4 или 5 и при необходимости задайте `Resolution` в `Parameters.Image`. |
| **Other DataBar formats** | Используйте `EncodeTypes.DatabarStacked` для двухстрочного stacked‑варианта без возможности omnidirectional. |
| **Saving as JPEG** | Замените `BarCodeImageFormat.Png` на `BarCodeImageFormat.Jpeg` и при необходимости задайте `Quality`. |

Эти варианты отвечают на более широкий вопрос *how to generate databar*, показывая, что один и тот же генератор можно перенастроить для разных семейств DataBar.

## Полный перечень исходного кода

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // Create a barcode generator for a stacked omnidirectional DataBar
            BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
                EncodeTypes.DatabarStackedOmniDirectional,
                "(01)12345678901231");

            // Define the module size (X‑dimension) in pixels
            barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;

            // Adjust the DataBar aspect ratio to make rows taller
            barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 15;

            // Save the generated barcode as a PNG image
            string outputPath = "DatabarAspectRatio15.png";
            barcodeGenerator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"Barcode image saved to {outputPath}");
        }
    }
}
```

Скопируйте код в `Program.cs`, восстановите пакеты NuGet и выполните `dotnet run`. Консоль подтвердит расположение изображения, и вы сможете открыть PNG, чтобы проверить результат **создать изображение штрих‑кода**.

## Заключение

Теперь вы знаете, как **создать изображение штрих‑кода** в C# с помощью библиотеки Barcode Generator и как **generate DataBar** коды с точным контролем размера и соотношения сторон. Полный пример демонстрирует все необходимые настройки — от инициализации `BarcodeGenerator` до экспорта PNG‑файла — чтобы вы могли интегрировать создание штрих‑кодов в любое .NET‑приложение без дополнительного исследования.

### Что дальше?

* Изучите другие символьные наборы штрих‑кодов с помощью `EncodeTypes` (например, QR, Code128) — естественное расширение рабочего процесса **barcode generator c#**.
* Объедините сгенерированное изображение с PDF‑ или Excel‑отчётами, используя Aspose.PDF или Aspose.Cells.
* Настройте цвет, добавьте отступы или внедрите штрих‑код в веб‑API для генерации по запросу.

Не стесняйтесь экспериментировать с параметрами, и пусть код служит надёжной основой для всех будущих проектов, связанных со штрих‑кодами. Приятного кодирования!

## Что вам следует изучить дальше?

Следующие учебники охватывают тесно связанные темы, построенные на техниках, продемонстрированных в этом руководстве. Каждый ресурс включает полностью работающие примеры кода с пошаговыми объяснениями, чтобы помочь вам освоить дополнительные возможности API и исследовать альтернативные подходы к реализации в собственных проектах.

- [Как использовать генератор штрих‑кодов C# для создания DataBar штрих‑кодов](/barcode/english/python-java/general/how-to-use-a-barcode-generator-c-to-create-databar-barcodes/)
- [Как использовать генератор штрих‑кодов C# для создания DataBar Omni‑directional штрих‑кодов](/barcode/english/python-java/general/how-to-use-a-barcode-generator-c-to-create-databar-omni-dire/)
- [Как создать stacked DataBar штрих‑код в C# – пошаговое руководство](/barcode/english/python-java/general/how-to-create-databar-stacked-barcode-in-c-step-by-step-guid/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}