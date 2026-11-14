---
category: general
date: 2026-11-14
description: Узнайте, как создать изображение штрих‑кода в C# с помощью Aspose.BarCode.
  Это пошаговое руководство охватывает настройку генератора штрих‑кодов в C#, форматирование
  GS1 и экспорт в PNG.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode image
- how to generate barcode
- barcode generator c#
- create gs1 barcode
- barcode image from data
language: ru
lastmod: 2026-11-14
og_description: Быстро создавайте изображение штрихкода в C#. Следуйте этому руководству,
  чтобы узнать, как генерировать штрихкоды, использовать генератор штрихкодов на C#
  и экспортировать PNG‑файл GS1 MicroPDF417.
og_image_alt: Screenshot of a GS1 MicroPDF417 barcode generated in C#
og_title: Создание изображения штрихкода в C# – полное руководство по GS1 MicroPDF417
schemas:
- author: Aspose
  dateModified: '2026-11-14'
  description: Learn how to create barcode image in C# using Aspose.BarCode. This
    step‑by‑step guide covers barcode generator c# setup, GS1 formatting and PNG export.
  headline: How to create barcode image in C# with GS1 MicroPDF417
  type: TechArticle
tags:
- barcode
- C#
- Aspose
title: Как создать изображение штрихкода в C# с GS1 MicroPDF417
url: /ru/net/gs1-barcode-encoding/how-to-create-barcode-image-in-c-with-gs1-micropdf417/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Как создать изображение штрихкода в C# с GS1 MicroPDF417

Если вам нужно **создать изображение штрихкода** в C#, это руководство покажет вам полное, готовое к запуску решение. Вы увидите **как сгенерировать штрихкод** данные, соответствующие стандарту GS1, настроите генератор и экспортируете PNG‑файл высокого качества.

В руководстве рассматривается всё — от установки необходимой библиотеки до обработки распространённых проблем формата данных. К концу вы сможете создать **изображение штрихкода из данных** всего несколькими строками кода и поймёте, почему каждое параметр имеет значение.

## Предварительные требования

* .NET 6.0 или более поздней версии установлен (код также работает с .NET Framework 4.7+).
* IDE, например Visual Studio 2022 или Visual Studio Code.
* Пакет NuGet **Aspose.BarCode for .NET**. Установите его с помощью:

```bash
dotnet add package Aspose.BarCode
```

* Базовое знакомство с синтаксисом C# и форматом идентификаторов приложений GS1 (AI).

> **Совет:** Держите версию библиотеки в актуальном состоянии; последняя версия добавляет поддержку новых символогий штрихкодов и улучшения производительности.

## Создание изображения штрихкода с BarcodeGenerator

Этот раздел содержит основную реализацию. Код создаёт экземпляр **barcode generator c#**, настраивает X‑dimension для читаемости и сохраняет результат в PNG‑файл.

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

// Step 1: Initialise the generator with the GS1 MicroPDF417 symbology
// The data string follows the GS1 syntax: (01)GTIN(21)SerialNumber
BarcodeGenerator generator = new BarcodeGenerator(
    EncodeTypes.MicroPdf417,
    "(01)12345678901234(21)ABC123");

// Step 2: Adjust the module width (X‑dimension) to improve scan reliability
// A value of 2 pixels works well for most screen‑displayed barcodes.
generator.Parameters.Barcode.XDimension.Pixels = 2;

// Step 3: Export the barcode as a PNG image
string outputPath = Path.Combine(
    Environment.GetFolderPath(Environment.SpecialFolder.Desktop),
    "GS1MicroPdf417.png");
generator.Save(outputPath, BarCodeImageFormat.Png);
```

### Почему каждая строка важна

* **EncodeTypes.MicroPdf417** сообщает библиотеке использовать символогию GS1 MicroPDF417, которая компактна и идеальна для мобильного сканирования.
* Строка **data string** должна начинаться с GS1 AI `(01)` для Global Trade Item Number (GTIN), за которым следует `(21)` для серийного номера. Если формат неверен, генератор бросает исключение.
* **XDimension.Pixels** контролирует ширину самого маленького штриха. Большое значение повышает читаемость на дисплеях с низким разрешением, а меньшее значение уменьшает размер изображения.
* **BarCodeImageFormat.Png** создаёт без потерь изображение, сохраняющее резкие края, необходимые для надёжного сканирования.

Запуск программы создаёт `GS1MicroPdf417.png` на рабочем столе. Открытие файла показывает плотный чёрно‑белый штрихкод, кодирующий GTIN `12345678901234` и серийный номер `ABC123`.

## Как сгенерировать штрихкод с помощью GS1 MicroPDF417

Если вы новичок в форматировании GS1, вот основные правила:

| GS1 AI | Значение                     | Пример               |
|--------|-----------------------------|-----------------------|
| (01)   | Глобальный номер торговой единицы | 12345678901234        |
| (21)   | Серийный номер (необязательно)    | ABC123                |

Когда вы объединяете AI с их значениями, оборачиваете каждый AI в скобки и размещаете значения сразу после. Полученную строку можно передать **barcode generator c#** без дополнительного кодирования.

### Распространённые подводные камни

* **Missing parentheses** – Генератор рассматривает строку как необработанные данные и не применит проверки GS1.
* **Exceeding length limits** – MicroPDF417 поддерживает до 155 символов. Удалите лишние пробелы.
* **Invalid characters** – Для GTIN допускаются только цифры; серийный номер может включать заглавные буквы и цифры.

## Настройка изображения штрихкода из данных

Помимо базового X‑dimension, Aspose.BarCode предлагает множество визуальных настроек. Ниже представлены несколько корректировок, которые вы можете применить в зависимости от требований проекта.

```csharp
// Set background to transparent (useful for overlaying on UI)
generator.Parameters.ImageBackgroundColor = Color.Transparent;

// Change foreground color to dark blue for branding
generator.Parameters.Barcode.BarColor = Color.FromArgb(0, 0, 139);

// Increase image resolution to 300 dpi for print‑ready output
generator.Parameters.ImageResolution = 300;
```

Каждая настройка необязательна; значения по умолчанию уже дают чистое, сканируемое **barcode image**. Экспериментируйте с цветами и разрешением только после подтверждения, что сканеры всё ещё могут считывать код.

## Сохранение штрихкода в других форматах

Хотя PNG является самым распространённым форматом для веба и мобильных устройств, вам могут потребоваться JPEG, BMP или SVG. Метод `Save` принимает любое значение `BarCodeImageFormat`.

```csharp
generator.Save("barcode.jpg", BarCodeImageFormat.Jpeg);
generator.Save("barcode.svg", BarCodeImageFormat.Svg);
```

* JPEG уменьшает размер файла, но вводит артефакты сжатия, которые могут влиять на читаемость.
* SVG сохраняет векторное качество и идеален для адаптивных веб‑дизайнов.

## Проверка сгенерированного штрихкода

Быстрый способ убедиться, что шаг **create barcode image** выполнен успешно, — использовать мобильное приложение‑сканер, поддерживающее GS1 MicroPDF417. Сканируйте сохранённый PNG; приложение должно отобразить:

```
GTIN: 12345678901234
Serial: ABC123
```

Если сканер сообщает об ошибке, дважды проверьте форматирование AI и значение X‑dimension.

## Полный пример — автономная консольная программа

Ниже приведена полная программа, которую вы можете скопировать, вставить и запустить без изменений (за исключением шага установки NuGet).

```csharp
using System;
using System.IO;
using System.Drawing;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // Initialise the generator with GS1 MicroPDF417 and sample data
            BarcodeGenerator generator = new BarcodeGenerator(
                EncodeTypes.MicroPdf417,
                "(01)12345678901234(21)ABC123");

            // Improve readability by setting module width
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // Optional visual customisation
            generator.Parameters.ImageBackgroundColor = Color.Transparent;
            generator.Parameters.Barcode.BarColor = Color.FromArgb(0, 0, 139);
            generator.Parameters.ImageResolution = 300;

            // Define output path (Desktop folder)
            string outputPath = Path.Combine(
                Environment.GetFolderPath(Environment.SpecialFolder.Desktop),
                "GS1MicroPdf417.png");

            // Save the barcode as PNG
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"Barcode image saved to: {outputPath}");
        }
    }
}
```

При запуске программы консоль выводит полный путь к файлу, а PNG появляется на рабочем столе. Этот пример демонстрирует **how to generate barcode** данные, настройку внешнего вида и экспорт **barcode image from data** в едином, согласованном процессе.

## Часто задаваемые вопросы

| Вопрос | Ответ |
|----------|--------|
| *Могу ли я генерировать другие символогии GS1?* | Да. Замените `EncodeTypes.MicroPdf417` на `EncodeTypes.Pdf417`, `EncodeTypes.DataMatrix` и т.д., и соответственно скорректируйте строку данных. |
| *Что делать, если мои данные превышают ёмкость MicroPDF417?* | Переключитесь на обычную символогию PDF417, которая поддерживает более длинные полезные нагрузки. |
| *Нужна ли лицензия для Aspose.BarCode?* | Бесплатная оценочная лицензия подходит для разработки. Для продакшна приобретите лицензию, чтобы убрать водяной знак оценки. |
| *Подходит ли PNG для печати на этикетках?* | Увеличьте `ImageResolution` до 300 dpi или выше и рассмотрите сохранение в формате TIFF для промышленных принтеров. |

## Заключение

Теперь вы знаете, как **create barcode image** в C# с использованием подхода **barcode generator c#**, форматировать данные для сценария **create gs1 barcode**, и экспортировать результат в PNG или другой тип изображения. Полный пример демонстрирует каждый шаг — от подготовки данных до визуальной настройки — чтобы вы могли интегрировать создание штрихкодов в любое приложение .NET.

Далее изучайте связанные темы, такие как **barcode image from data** для QR‑кодов, добавление нескольких штрихкодов в один PDF или автоматизация пакетной генерации для систем учёта. Экспериментируйте с различными значениями X‑dimension и форматами изображений, чтобы найти оптимальное решение для вашей среды сканирования.

Удачной разработки, и пусть ваши приложения начнут **creating barcode images**, которые надёжно работают в реальном мире!

## Что стоит изучить дальше?

Следующие руководства охватывают тесно связанные темы, которые развивают техники, продемонстрированные в этом руководстве. Каждый ресурс включает полные рабочие примеры кода с пошаговыми объяснениями, чтобы помочь вам освоить дополнительные возможности API и исследовать альтернативные подходы к реализации в ваших проектах.

- [Как создать изображение штрихкода с Aspose.Barcode в C#](/barcode/english/python-java/general/how-to-create-barcode-image-with-aspose-barcode-in-c/)
- [Как создать почтовый штрихкод в C# с использованием Aspose.BarCode](/barcode/english/python-java/general/how-to-create-postal-barcode-image-in-c-using-aspose-barcode/)
- [Как создать изображение штрихкода PDF417 в C# — полное руководство](/barcode/english/net/compact-pdf417-encoding/generate-pdf417-barcode-in-c-complete-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}