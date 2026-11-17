---
category: general
date: 2026-11-17
description: Создайте PNG‑изображение штрих‑кода на C# быстро — пошаговое руководство,
  показывающее, как сгенерировать штрих‑код Planet, настроить его размер и сохранить
  изображение.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode png
- how to create barcode
- barcode generator example
- generate planet barcode
- customize barcode size
language: ru
lastmod: 2026-11-17
og_description: Создайте PNG‑изображение штрих‑кода в C# с помощью Aspose.Barcode.
  Узнайте, как сгенерировать штрих‑код Planet, настроить его размер и сохранить PNG‑изображение
  высокого качества.
og_image_alt: C# code snippet that creates a barcode PNG file
og_title: Создание PNG‑штрихкода в C# — полное руководство
schemas:
- author: Aspose
  dateModified: '2026-11-17'
  description: Create barcode PNG in C# quickly – a step‑by‑step guide that shows
    how to generate a Planet barcode, customize its size, and save the image.
  headline: How to create barcode PNG in C# using Aspose.Barcode
  type: TechArticle
- description: Create barcode PNG in C# quickly – a step‑by‑step guide that shows
    how to generate a Planet barcode, customize its size, and save the image.
  name: How to create barcode PNG in C# using Aspose.Barcode
  steps:
  - name: '**Instantiate** the generator with the desired symbology and data.'
    text: '**Instantiate** the generator with the desired symbology and data.'
  - name: '**Adjust parameters** such as size and bar style.'
    text: '**Adjust parameters** such as size and bar style.'
  - name: '**Save** the image in the format you need.'
    text: '**Save** the image in the format you need.'
  type: HowTo
tags:
- barcode
- C#
- Aspose.Barcode
title: Как создать PNG штрихкода в C# с помощью Aspose.Barcode
url: /ru/python-java/general/how-to-create-barcode-png-in-c-using-aspose-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Как создать PNG штрихкода в C# с использованием Aspose.Barcode

Если вам нужно **создавать PNG штрихкода** из кода C#, это руководство покажет, как это сделать. Независимо от того, создаёте ли вы систему почтовых этикеток или приложение точка‑продажи, вы изучите полный **пример генератора штрихкода**, который генерирует штрихкод Planet, позволяет **настраивать размер штрихкода** и сохраняет результат в виде PNG‑изображения.

Вы завершите руководство готовой к запуску программой, которую можно добавить в любой проект .NET. Внешние сервисы не требуются — только библиотека Aspose.Barcode и несколько строк кода.

## Необходимые условия

| Требование | Причина |
|-------------|--------|
| .NET 6.0 SDK or later | Обеспечивает среду выполнения для консольного приложения C# |
| Visual Studio 2022 (or any IDE) | Позволяет компилировать и отлаживать код |
| Aspose.Barcode for .NET NuGet package | Содержит класс `BarcodeGenerator`, используемый в примере |

Установите пакет NuGet из командной строки:

```bash
dotnet add package Aspose.Barcode
```

> **Совет:** Если вы предпочитаете консоль диспетчера пакетов в Visual Studio, выполните `Install-Package Aspose.Barcode`.

## Шаг 1: Создать новый консольный проект

Откройте терминал и выполните:

```bash
dotnet new console -n BarcodePngDemo
cd BarcodePngDemo
```

Это создаст минимальное консольное приложение C# с именем **BarcodePngDemo**.

## Шаг 2: Создать PNG штрихкода в C# (ядро решения)

Сердцем руководства является объект `BarcodeGenerator`. На этом шаге мы **создаём PNG штрихкода**, создавая генератор с символьностью *Planet* и данными, которые нужно закодировать.

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Step 2.1: Initialize the generator for the Planet barcode type
        // "123456" is the data that will be encoded.
        BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Planet, "123456");

        // Step 2.2: Set the module (X‑dimension) size – 4 pixels per bar gives a clear image.
        generator.Parameters.Barcode.XDimension.Pixels = 4;

        // Step 2.3: Choose the empty‑bars style (unfilled bars) for a postal‑friendly look.
        generator.Parameters.Barcode.FilledBars = false;

        // Step 2.4: Save the generated barcode as a PNG file.
        // Adjust the path as needed for your environment.
        generator.Save("postal_planet_empty_bars.png", BarCodeImageFormat.Png);

        System.Console.WriteLine("Barcode PNG created successfully.");
    }
}
```

### Почему эти настройки важны

* **EncodeTypes.Planet** – Символика *Planet* предназначена для почтовых приложений; она эффективно кодирует числовые данные.  
* **XDimension.Pixels = 4** – Эта настройка **customize barcode size** контролирует ширину каждой полосы. Значение 4 пикселя обеспечивает баланс читаемости и размера файла для большинства принтеров.  
* **FilledBars = false** – Стиль пустых полос создаёт изображение белый‑на‑чёрном, которое хорошо сканируется на контрастной бумаге, что часто требуется для почтовых этикеток.  
* **BarCodeImageFormat.Png** – PNG сохраняет резкие края без потери качества, обеспечивая сканируемость штрихкода.

## Шаг 3: Как создать штрихкод – краткое резюме настройки

Если вы новичок в генерации штрихкодов, три строки выше охватывают весь процесс **how to create barcode**.

1. **Instantiate** генератор с нужной символьностью и данными.  
2. **Adjust parameters** такие как размер и стиль полос.  
3. **Save** изображение в требуемом формате.

Вы можете заменить `EncodeTypes.Planet` на любой другой поддерживаемый тип (например, `EncodeTypes.Code128`), не меняя остальной код.

## Шаг 4: Пример генератора штрихкода – добавление дополнительных настроек

Помимо размера и пустых полос, Aspose.Barcode позволяет настраивать цвета, отступы и текст. Ниже представлено быстрое расширение, которое добавляет красный передний план и белый фон, а затем сохраняет тот же штрихкод под другим именем.

```csharp
// Change colors (optional)
generator.Parameters.Barcode.BarColor = System.Drawing.Color.Red;
generator.Parameters.Barcode.BackColor = System.Drawing.Color.White;

// Save a second version
generator.Save("postal_planet_red.png", BarCodeImageFormat.Png);
```

> **Осторожно:** Использование цветов с низким контрастом может сделать штрихкод нечитаемым для некоторых сканеров. Всегда тестируйте на целевом оборудовании.

## Шаг 5: Сгенерировать штрихкод Planet с пустыми полосами (полный пример)

Объединив всё вместе, представляем полный код, который можно скопировать и вставить в `Program.cs`:

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace BarcodePngDemo
{
    class Program
    {
        static void Main()
        {
            // Create the generator for a Planet barcode.
            BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Planet, "123456");

            // Customize size – 4 pixels per module.
            generator.Parameters.Barcode.XDimension.Pixels = 4;

            // Use empty‑bars style for postal friendliness.
            generator.Parameters.Barcode.FilledBars = false;

            // Save the primary PNG.
            generator.Save("postal_planet_empty_bars.png", BarCodeImageFormat.Png);

            // Optional: change colors and save a second version.
            generator.Parameters.Barcode.BarColor = System.Drawing.Color.Red;
            generator.Parameters.Barcode.BackColor = System.Drawing.Color.White;
            generator.Save("postal_planet_red.png", BarCodeImageFormat.Png);

            Console.WriteLine("Both barcode PNG files have been generated.");
        }
    }
}
```

Run the program:

```bash
dotnet run
```

Вы должны увидеть два PNG‑файла в папке проекта:

* `postal_planet_empty_bars.png` – классический черно‑белый штрихкод с пустыми полосами.  
* `postal_planet_red.png` – цветной вариант, демонстрирующий дополнительные опции **customize barcode size**.

Откройте любой из файлов в просмотрщике изображений; вы увидите чистый, сканируемый штрихкод, готовый к печати.

## Распространённые проблемы и их устранение

| Симптом | Вероятная причина | Решение |
|---------|-------------------|---------|
| Штрихкод выглядит размытым | X‑dimension слишком низкое (например, 1 пиксель) | Увеличьте `XDimension.Pixels` минимум до 3‑4 пикселей. |
| Сканер не может прочитать изображение | Цвета имеют недостаточный контраст | Используйте темный цвет полос на светлом фоне или вернитесь к стандартной черно‑белой схеме. |
| `Save` throws `ArgumentException` | Неверный путь к файлу или отсутствие прав записи | Убедитесь, что каталог существует и у приложения есть права записи. |
| Выведена неправильная символьность | Неправильное значение перечисления `EncodeTypes` | Проверьте, что выбрали `EncodeTypes.Planet` (или нужный тип). |

## Лучшие практики для продакшн

* **Validate input data** перед передачей в `BarcodeGenerator`. Штрихкоды Planet принимают только числовые строки определённой длины.  
* **Cache the generator** если нужно создать много штрихкодов с одинаковыми настройками; повторное использование объекта повышает производительность.  
* **Use PNG for on‑screen rendering** и **PDF or TIFF for high‑resolution printing** — оба формата поддерживаются Aspose.Barcode.  
* **Test with the actual scanner** который вы планируете использовать. Разные устройства имеют различную толерантность к ширине полос и контрасту.

## Заключение

Теперь вы знаете, как **создавать PNG штрихкода** файлы в C# с помощью лаконичного **примера генератора штрихкода**. Руководство охватывало:

* Создание экземпляра `BarcodeGenerator` для символьности **Planet**.  
* **Customize barcode size** с использованием свойства X‑dimension.  
* Применение стиля пустых полос для почтового вывода.  
* Сохранение результата в виде PNG‑изображения и, при необходимости, настройка цветов.

Отсюда вы можете изучать другие символьности, добавлять читаемый человеком текст или интегрировать код в веб‑API, который по запросу возвращает PNG штрихкоды. Приятного кодинга, и пусть ваши сканы всегда будут точными!

## Что изучать дальше?

Следующие руководства охватывают тесно связанные темы, построенные на техниках, продемонстрированных в этом руководстве. Каждый ресурс включает полностью работающие примеры кода с пошаговыми объяснениями, чтобы помочь вам освоить дополнительные возможности API и исследовать альтернативные подходы к реализации в ваших проектах.

- [Как создать PNG штрихкода в C# – пошаговое руководство](/barcode/english/net/compact-pdf417-encoding/how-to-create-barcode-png-in-c-step-by-step-guide/)
- [Как создать PNG штрихкода с пользовательским соотношением сторон в C#](/barcode/english/python-java/general/how-to-create-barcode-png-with-a-custom-aspect-ratio-in-c/)
- [Как использовать генератор штрихкода C# для создания штрихкода Planet](/barcode/english/python-java/general/how-to-use-a-c-barcode-generator-to-create-a-planet-barcode/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}