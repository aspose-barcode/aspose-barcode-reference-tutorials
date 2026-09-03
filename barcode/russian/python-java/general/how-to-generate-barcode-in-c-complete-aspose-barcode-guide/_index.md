---
category: general
date: 2026-07-21
description: Как быстро генерировать штрих‑код с помощью Aspose.BarCode для C#. Узнайте,
  как создавать штрих‑коды в Aspose, настраивать соотношения сторон и сохранять PNG
  за считанные минуты.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to generate barcode
- create barcode with aspose
- Aspose.BarCode example
- DataBar stacked omnidirectional
- barcode aspect ratio C#
language: ru
lastmod: 2026-07-21
og_description: Как генерировать штрих‑код с помощью Aspose.BarCode для C#. Это пошаговое
  руководство покажет, как создать штрих‑код с Aspose, настроить параметры и экспортировать
  изображения.
og_image_alt: Screenshot of generated DataBar barcode showing different aspect ratios
og_title: Как сгенерировать штрих‑код в C# – быстрый учебник Aspose.BarCode
schemas:
- author: Aspose
  dateModified: '2026-07-21'
  description: How to generate barcode quickly using Aspose.BarCode for C#. Learn
    to create barcode with Aspose, adjust aspect ratios, and save PNGs in minutes.
  headline: How to Generate Barcode in C# – Complete Aspose.BarCode Guide
  type: TechArticle
tags:
- barcode
- Aspose
- C#
- DataBar
title: Как генерировать штрих‑код в C# – Полное руководство по Aspose.BarCode
url: /ru/python-java/general/how-to-generate-barcode-in-c-complete-aspose-barcode-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Как генерировать штрих‑коды в C# – Полное руководство Aspose.BarCode

Когда‑то задумывались **как генерировать штрих‑коды** в .NET‑приложении, не вдаваясь в низкоуровневый код изображений? Вы не одиноки. Во многих корпоративных проектах нам нужно **создавать штрих‑коды с Aspose** для счетов‑фактур, транспортных этикеток или учёта запасов, и библиотека делает это удивительно просто.

В этом руководстве мы пройдём реальный пример, который создаёт штрих‑код DataBar Stacked Omnidirectional, изменяет его соотношение сторон и сохраняет два PNG‑файла. К концу вы получите готовую к запуску консольную программу и чёткое представление о ключевых свойствах, которыми можно управлять.

## Что вы узнаете

- Как настроить Aspose.BarCode в проекте C# (NuGet, основы лицензирования)
- Инициализировать генератор **DataBar stacked omnidirectional**
- Регулировать X‑размер (pixel size) и соотношение сторон
- Сохранять штрих‑код в виде PNG‑изображений
- Расширять пример для других типов штрих‑кодов или форматов вывода

Предыдущий опыт работы с Aspose не требуется — достаточно работающего .NET 6 (или новее) SDK и любимой IDE.

## Требования

| Требование | Причина |
|------------|---------|
| .NET 6 SDK или новее | Современные возможности языка и простое создание проекта |
| Visual Studio 2022 (или VS Code) | IDE для сборки и отладки |
| Aspose.BarCode for .NET NuGet‑пакет | Основная библиотека, выполняющая всю тяжёлую работу |
| Действительная лицензия Aspose (или оценочная) | Убирает водяной знак оценки и открывает полный набор функций |

Если вы ещё не установили NuGet‑пакет, выполните:

```bash
dotnet add package Aspose.BarCode
```

Теперь, когда всё готово, приступим к коду.

## Шаг 1: Создайте новый консольный проект

Сначала создайте свежий консольный апп. Откройте терминал и введите:

```bash
dotnet new console -n BarcodeDemo
cd BarcodeDemo
```

Это создаст `Program.cs` и файл `.csproj`. Откройте проект в редакторе и добавьте ссылку на Aspose, как показано выше.

## Шаг 2: Инициализируйте BarcodeGenerator

Сердце процесса — класс `BarcodeGenerator`. Мы запросим симбологию **DataBar stacked omnidirectional** и передадим ей пример строки GS1‑128.

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;
using System;

class Program
{
    static void Main()
    {
        // Step 2.1: Choose the barcode type and data
        var generator = new BarcodeGenerator(
            EncodeTypes.DatabarStackedOmniDirectional,
            "(01)12345678901231"); // GS1-128 example

        // Step 2.2: Set the X‑dimension (pixel size) – controls overall size
        generator.Parameters.Barcode.XDimension.Pixels = 2;

        // Continue with aspect ratio adjustments...
        GenerateBarcodes(generator);
    }

    static void GenerateBarcodes(BarcodeGenerator generator)
    {
        // Placeholder for the rest of the steps
    }
}
```

**Почему это важно:** `EncodeTypes.DatabarStackedOmniDirectional` генерирует компактный, высокоплотный штрих‑код, идеальный для небольших этикеток. Строка данных следует идентификатору приложения GS1 `(01)` для значения GTIN‑14, которое ожидают многие системы цепочки поставок.

## Шаг 3: Настройте соотношение сторон и сохраните изображения

Aspose.BarCode позволяет менять **соотношение сторон** символов DataBar через `Parameters.Barcode.DataBar.AspectRatio`. Изменение этого значения меняет визуальное соотношение ширины к высоте, что может быть критично при размещении штрих‑кода на этикетке фиксированного размера.

```csharp
static void GenerateBarcodes(BarcodeGenerator generator)
{
    string outputPath = "GeneratedBarcodes/"; // Ensure this folder exists
    System.IO.Directory.CreateDirectory(outputPath);

    // ---------- First image: Aspect Ratio 15 ----------
    generator.Parameters.Barcode.DataBar.AspectRatio = 15;
    string file15 = $"{outputPath}DatabarAspectRatio15.png";
    generator.Save(file15, BarCodeImageFormat.Png);
    Console.WriteLine($"Saved barcode with aspect ratio 15 to {file15}");

    // ---------- Second image: Aspect Ratio 30 ----------
    generator.Parameters.Barcode.DataBar.AspectRatio = 30;
    string file30 = $"{outputPath}DatabarAspectRatio30.png";
    generator.Save(file30, BarCodeImageFormat.Png);
    Console.WriteLine($"Saved barcode with aspect ratio 30 to {file30}");
}
```

**Пояснение каждой строки**

- `outputPath` указывает папку, куда будут сохраняться PNG‑файлы. `Directory.CreateDirectory` гарантирует, что папка существует даже на чистой машине.
- `AspectRatio = 15` даёт относительно высокий штрих‑код; `AspectRatio = 30` растягивает его по горизонтали.
- `generator.Save(...)` записывает изображение на диск. Перечисление `BarCodeImageFormat.Png` обеспечивает безпотерьное качество.
- `Console.WriteLine` выводит мгновенную обратную связь при запуске программы.

### Ожидаемый вывод

При выполнении `dotnet run` вы увидите примерно следующее:

```
Saved barcode with aspect ratio 15 to GeneratedBarcodes/DatabarAspectRatio15.png
Saved barcode with aspect ratio 30 to GeneratedBarcodes/DatabarAspectRatio30.png
```

Откройте оба PNG‑файла рядом; вы заметите, что второе изображение заметно шире, при этом высота остаётся той же. Оба изображения сканируются стандартными считывателями штрих‑кодов.

## Шаг 4: Запустите полный пример

Ниже представлен **полный, готовый к запуску исходный код** в одном блоке для удобного копирования:

```csharp
// Program.cs
using Aspose.BarCode.Generation;
using Aspose.BarCode;
using System;
using System.IO;

class Program
{
    static void Main()
    {
        // Initialise generator with DataBar stacked omnidirectional symbology
        var generator = new BarcodeGenerator(
            EncodeTypes.DatabarStackedOmniDirectional,
            "(01)12345678901231");

        // Set pixel size of the X‑dimension (controls overall size)
        generator.Parameters.Barcode.XDimension.Pixels = 2;

        // Generate two barcodes with different aspect ratios
        GenerateBarcodes(generator);
    }

    static void GenerateBarcodes(BarcodeGenerator generator)
    {
        string outputPath = "GeneratedBarcodes/";
        Directory.CreateDirectory(outputPath);

        // Aspect Ratio 15
        generator.Parameters.Barcode.DataBar.AspectRatio = 15;
        string file15 = Path.Combine(outputPath, "DatabarAspectRatio15.png");
        generator.Save(file15, BarCodeImageFormat.Png);
        Console.WriteLine($"Saved barcode with aspect ratio 15 to {file15}");

        // Aspect Ratio 30
        generator.Parameters.Barcode.DataBar.AspectRatio = 30;
        string file30 = Path.Combine(outputPath, "DatabarAspectRatio30.png");
        generator.Save(file30, BarCodeImageFormat.Png);
        Console.WriteLine($"Saved barcode with aspect ratio 30 to {file30}");
    }
}
```

Скомпилируйте и запустите:

```bash
dotnet run
```

Вуаля — два идеально отрисованных PNG‑штрих‑кода появятся в `GeneratedBarcodes/`.

## Шаг 5: Расширение примера (по желанию)

Теперь, когда вы **знаете, как генерировать штрих‑коды** с Aspose, возможно, возникнет вопрос: *Что ещё можно настроить?* Вот несколько быстрых идей:

| Свойство | Что делает | Типичный сценарий |
|----------|------------|-------------------|
| `generator.Parameters.Barcode.CodeTextParameters.Font.Size` | Меняет размер читаемого человеком текста | Больший шрифт для ручных сканеров |
| `generator.Parameters.Barcode.ImageFormat` | Глобальный формат вывода (PNG, JPEG, BMP и др.) | JPEG для веб‑дружественного размера |
| `generator.Parameters.Barcode.Color` | Устанавливает цвет переднего плана | Цветовое кодирование категорий |
| `generator.Save(..., BarCodeImageFormat.Svg)` | Векторный вывод для бесконечного масштабирования | PDF‑готовый к печати |

Чтобы поэкспериментировать, просто добавьте соответствующие строки перед каждым вызовом `Save`.

## Частые ошибки и профессиональные советы

- **Размещение лицензии:** Если вы используете платную лицензию, вызовите `License license = new License(); license.SetLicense("Aspose.BarCode.lic");` до создания генератора. Пропуск этого шага оставит водяной знак на изображении.
- **Неверная строка данных:** Символы DataBar ожидают числовые GS1‑данные. Передача буквенных символов вызовет `ArgumentException`.
- **Потокобезопасность:** Экземпляры `BarcodeGenerator` **не** являются потокобезопасными. Создавайте новый объект для каждого потока, если генерируете штрих‑коды параллельно.
- **Размер изображения vs. возможности сканера:** Очень высокий `XDimension.Pixels` может создать огромное изображение, которое некоторые сканеры не смогут прочитать. Тестируйте с целевым оборудованием.

## Заключение

Мы рассмотрели **как генерировать штрих‑коды** в C# с помощью Aspose.BarCode, от настройки проекта до сохранения двух изображений с разными соотношениями сторон. Ключевые шаги — инициализация генератора, настройка X‑размера и соотношения сторон, вызов `Save` — образуют повторяемый шаблон, применимый к любому типу штрих‑кода, поддерживаемому Aspose.

Теперь вы можете **создавать штрих‑коды с Aspose** для счетов‑фактур, транспортных этикеток или инвентарных меток, а также имеете прочную основу для изучения более продвинутых функций, таких как цвет, пользовательские шрифты или вывод в SVG. Не стесняйтесь менять код, экспериментировать с другими `EncodeTypes` и интегрировать генератор в свои сервисы.

Есть вопросы или хотите увидеть конкретный стиль штрих‑кода? Оставьте комментарий ниже, и удачной разработки!

## Что изучать дальше?

Следующие руководства охватывают тесно связанные темы, расширяющие техники, продемонстрированные в этом руководстве. Каждый ресурс содержит полностью работающие примеры кода с пошаговыми объяснениями, помогающими освоить дополнительные возможности API и исследовать альтернативные подходы в ваших проектах.

- [How to generate Aztec barcode with custom aspect ratio using Aspose.BarCode for .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)
- [How to Customize Barcode - Codablock F Aspect Ratio with Aspose.BarCode for .NET](/barcode/english/net/codablock-f-encoding/codablock-f-aspect-ratio-customization/)
- [How to Generate DataMatrix Barcodes (ECC 200) with Aspose.BarCode for .NET](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-ecc-200-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}