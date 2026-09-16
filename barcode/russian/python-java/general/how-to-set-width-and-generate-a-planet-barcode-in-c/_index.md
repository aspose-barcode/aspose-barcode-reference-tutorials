---
category: general
date: 2026-09-16
description: Узнайте, как установить ширину, как создавать пустые полосы и как заполнять
  полосы при генерации штрих‑кода Planet с помощью Aspose.BarCode.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to set width
- how to make empty
- how to fill bars
- generate planet barcode
language: ru
lastmod: 2026-09-16
og_description: Как задать ширину, создать пустые полосы и заполнить полосы при генерации
  штрих‑кода Planet с помощью Aspose.BarCode — полное пошаговое руководство.
og_image_alt: Screenshot showing how to set width for a Planet barcode in C#
og_title: Как задать ширину и сгенерировать штрих‑код Planet в C#
schemas:
- author: Aspose
  dateModified: '2026-09-16'
  description: Learn how to set width, how to make empty bars, and how to fill bars
    when you generate Planet barcode using Aspose.BarCode.
  headline: How to set width and generate a Planet barcode in C#
  type: TechArticle
tags:
- barcode
- C#
- Aspose.BarCode
title: Как задать ширину и сгенерировать штрих‑код Planet в C#
url: /ru/python-java/general/how-to-set-width-and-generate-a-planet-barcode-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Как установить ширину и сгенерировать штрих‑код Planet в C#

Если вам нужно **how to set width** для штрих‑кода Planet, это руководство показывает полный процесс. Вы также увидите, как **how to make empty** полосы, **how to fill bars**, и точные шаги для **generate Planet barcode** с Aspose.BarCode для .NET.

Создание почтового штрих‑кода Planet обычно требуется при разработке приложений для почтовых этикеток или интеграций с почтовыми службами. К концу этого руководства у вас будет готовая к запуску консольная программа, которая создает как изображение с заполненными полосами, так и изображение с пустыми полосами, используя одну и ту же строку данных.

## Требования

- .NET 6.0 SDK или новее (код также работает с .NET Framework 4.7+)
- Visual Studio 2022 или любой совместимый с C# IDE
- NuGet‑пакет Aspose.BarCode для .NET (`Aspose.BarCode`)  
  Установить с помощью:

```bash
dotnet add package Aspose.BarCode
```

Дополнительная конфигурация не требуется; библиотека обрабатывает кодирование изображения внутри.

## Шаг 1: Создать консольный проект и добавить библиотеку

Откройте терминал и выполните:

```bash
dotnet new console -n PlanetBarcodeDemo
cd PlanetBarcodeDemo
dotnet add package Aspose.BarCode
```

Это создаст файл `Program.cs`, в котором мы напишем логику штрих‑кода.

## Шаг 2: Написать код – how to set width и generate Planet barcode

Откройте `Program.cs` и замените его содержимое следующим полным примером:

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Data to encode – the same value is used for both images
        const string data = "123456";

        // -----------------------------------------------------------------
        // Part A: Filled‑bars version (default style)
        // -----------------------------------------------------------------
        // Step 2.1: Create a Planet barcode generator
        var filledGenerator = new BarcodeGenerator(EncodeTypes.Planet, data);

        // Step 2.2: How to set width – define the width of a single bar in pixels
        // The XDimension controls bar width; 4 pixels yields a clear, printable image
        filledGenerator.Parameters.Barcode.XDimension.Pixels = 4;

        // Step 2.3: Save the filled‑bars image (default is FilledBars = true)
        string filledPath = "PostalPlanetFilledBars.png";
        filledGenerator.Save(filledPath, BarCodeImageFormat.Png);
        Console.WriteLine($"Filled‑bars barcode saved to {filledPath}");

        // -----------------------------------------------------------------
        // Part B: Empty‑bars version (unfilled style)
        // -----------------------------------------------------------------
        // Step 3.1: Re‑instantiate the generator for the same data
        var emptyGenerator = new BarcodeGenerator(EncodeTypes.Planet, data);

        // Step 3.2: How to set width again – required after re‑instantiation
        emptyGenerator.Parameters.Barcode.XDimension.Pixels = 4;

        // Step 3.3: How to make empty – disable the filled‑bars flag
        emptyGenerator.Parameters.Barcode.FilledBars = false;

        // Step 3.4: Save the empty‑bars image
        string emptyPath = "PostalPlanetEmptyBars.png";
        emptyGenerator.Save(emptyPath, BarCodeImageFormat.Png);
        Console.WriteLine($"Empty‑bars barcode saved to {emptyPath}");

        // -----------------------------------------------------------------
        // Verification output
        // -----------------------------------------------------------------
        Console.WriteLine("Both barcodes generated successfully.");
    }
}
```

### Почему каждый шаг важен

- **How to set width**: Свойство `XDimension.Pixels` напрямую влияет на физический размер каждой полосы. Выбор значения от 2 до 6 пикселей обеспечивает баланс читаемости на экране и качества печати.
- **How to make empty**: Установка `FilledBars = false` заставляет генератор рисовать только контуры полос. Этот стиль полезен для печати «свет‑на‑тёмном» или когда нужно, чтобы сквозила текстура бумаги.
- **How to fill bars**: Значение по умолчанию `FilledBars = true` создаёт сплошные чёрные полосы, что является стандартом для большинства почтовых сканеров.
- **Generate Planet barcode**: Использование `EncodeTypes.Planet` выбирает специфическое кодирование, требуемое United States Postal Service (USPS) для штрих‑кодов Planet.

## Шаг 3: Скомпилировать и запустить программу

Выполните из папки проекта:

```bash
dotnet run
```

Вы должны увидеть вывод консоли, похожий на:

```
Filled‑bars barcode saved to PostalPlanetFilledBars.png
Empty‑bars barcode saved to PostalPlanetEmptyBars.png
Both barcodes generated successfully.
```

В каталоге проекта появятся два PNG‑файла:

- `PostalPlanetFilledBars.png` – сплошные чёрные полосы (стиль по умолчанию)
- `PostalPlanetEmptyBars.png` – контурные полосы (пустой стиль)

Откройте их в любом просмотрщике изображений, чтобы убедиться, что ширина полосы соответствует настройке в 4 пикселя, а пустая версия отображает незаполненные полосы.

## Часто задаваемые вопросы и особые случаи

| Вопрос | Ответ |
|----------|--------|
| *Can I use a different image format?* | Да. Замените `BarCodeImageFormat.Png` на `Jpeg`, `Bmp` или `Gif` при необходимости. |
| *What if the barcode becomes too wide for my label?* | Уменьшите `XDimension.Pixels` (например, до `2`) или увеличьте ширину модуля принтера этикеток. |
| *Do I need to set `Height` manually?* | Библиотека автоматически рассчитывает высоту на основе кодирования. При необходимости можно переопределить `Parameters.Barcode.BarHeight`. |
| *Is the empty‑bars style supported on all printers?* | Большинство современных термопринтеров поддерживают как заполненные, так и пустые стили, но проверьте на тестовой печати, если используете устаревшее устройство. |
| *How to add a human‑readable caption under the barcode?* | Используйте `Parameters.Caption` для включения и стилизации подписи; установите `CaptionAbove` в `false`, чтобы разместить её снизу. |

## Профессиональные советы

- **Reuse the same generator** только когда все параметры остаются одинаковыми. Изменение `FilledBars` после сохранения не влияет на уже сохранённое изображение, поэтому повторное создание экземпляра (как показано) гарантирует чистый старт.
- **Batch generation**: Оберните код в цикл и меняйте `data` на каждой итерации, чтобы создать серию штрих‑кодов Planet для массовой рассылки.
- **Performance**: Для тысяч штрих‑кодов создайте один экземпляр `BarcodeGenerator`, при необходимости изменяйте `XDimension` и `FilledBars` и переиспользуйте объект, чтобы снизить выделения памяти.

## Заключение

Теперь вы знаете **how to set width**, **how to make empty**, **how to fill bars** и точные шаги для **generate Planet barcode** с Aspose.BarCode в C#. Полный, исполняемый пример создаёт как PNG‑файлы со сплошными, так и с пустыми полосами, готовые к интеграции в любой процесс создания почтовых этикеток.

Далее изучайте связанные темы, такие как **how to add QR codes to the same label**, **customizing barcode colors** или **embedding the barcode into a PDF document**. Каждая из них опирается на те же основы, рассмотренные здесь. Приятного кодирования!

## Что следует изучить дальше?

Следующие руководства охватывают тесно связанные темы, которые развивают техники, продемонстрированные в этом руководстве. Каждый ресурс включает полные работающие примеры кода с пошаговыми объяснениями, чтобы помочь вам освоить дополнительные возможности API и исследовать альтернативные подходы к реализации в ваших проектах.

- [Создать изображение штрих‑кода Planet в C# – Как сгенерировать почтовый штрих‑код](/barcode/english/python-java/general/create-planet-barcode-image-in-c-how-to-generate-postal-barc/)
- [Как создать штрих‑код Code128 с пустыми полосами в Java](/barcode/english/java/image-manipulation/generating-barcode-empty-bars/)
- [Как сгенерировать изображение штрих‑кода в Java с Aspose.BarCode](/barcode/english/java/barcode-rendering-techniques/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}