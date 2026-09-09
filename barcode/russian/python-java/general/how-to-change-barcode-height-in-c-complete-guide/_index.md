---
category: general
date: 2026-07-24
description: Как быстро изменить высоту штрихкода в C#. Узнайте, как использовать
  генератор штрихкодов C#, сохранять изображение штрихкода в PNG и пошагово регулировать
  высоту полос.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to change barcode
- barcode generator c#
- barcode image png
- how to generate barcode
- adjust barcode height
language: ru
lastmod: 2026-07-24
og_description: Как изменить высоту штрихкода в C#? Это руководство показывает, как
  сгенерировать штрихкод, настроить его размер и сохранить его как PNG‑изображение
  с помощью генератора штрихкодов C#.
og_image_alt: Screenshot illustrating how to change barcode height in C# with a barcode
  generator
og_title: Как изменить высоту штрих‑кода в C# – быстрый учебник
schemas:
- author: Aspose
  dateModified: '2026-07-24'
  description: How to change barcode height in C# quickly. Learn barcode generator
    C# usage, save barcode image PNG, and adjust bar height step‑by‑step.
  headline: How to Change Barcode Height in C# – Complete Guide
  type: TechArticle
- description: How to change barcode height in C# quickly. Learn barcode generator
    C# usage, save barcode image PNG, and adjust bar height step‑by‑step.
  name: How to Change Barcode Height in C# – Complete Guide
  steps:
  - name: Generates a **DataBar Omni‑directional** barcode using the `BarcodeGenerator`
      class.
    text: Generates a **DataBar Omni‑directional** barcode using the `BarcodeGenerator`
      class.
  - name: Changes the bar height from 30 pixels to 60 pixels (or any value you need).
    text: Changes the bar height from 30 pixels to 60 pixels (or any value you need).
  - name: Saves both versions as **barcode image PNG** files on disk.
    text: Saves both versions as **barcode image PNG** files on disk.
  type: HowTo
tags:
- barcode
- c#
- png
- image-processing
title: Как изменить высоту штрихкода в C# – Полное руководство
url: /ru/python-java/general/how-to-change-barcode-height-in-c-complete-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Как изменить высоту штрих‑кода в C# – Полное руководство

Как изменить высоту штрих‑кода в C# — распространённая проблема, когда нужен штрих‑код, подходящий к конкретной этикетке или дизайну упаковки. В этом руководстве мы пройдем процесс генерации штрих‑кода, настройки высоты его полос и сохранения его в виде PNG‑изображения — всё с помощью библиотеки **barcode generator C#**.

Представьте, что вы создаёте систему печати транспортных этикеток, и высота полос по умолчанию выглядит слишком маленькой для ваших этикеток размером 4 × 6 дюймов. Вы могли бы растянуть всё изображение, но это исказит полосы и нарушит работу сканеров. Вместо этого вы узнаете чистый способ **adjust barcode height** непосредственно в генераторе, обеспечивая чёткий и читаемый результат каждый раз.

## Что вы создадите

К концу этого руководства у вас будет небольшое консольное приложение, которое:

1. Генерирует штрих‑код **DataBar Omni‑directional** с помощью класса `BarcodeGenerator`.  
2. Меняет высоту полос с 30 пикселей на 60 пикселей (или любое нужное вам значение).  
3. Сохраняет обе версии как файлы **barcode image PNG** на диск.

## Предварительные требования

- .NET 6.0 SDK или новее (можно также нацелиться на .NET Framework 4.8, если предпочитаете).  
- Visual Studio 2022, VS Code или любой другой IDE по вашему выбору.  
- Пакет NuGet Aspose.BarCode for .NET (или любая совместимая библиотека штрих‑кодов). Установите его с помощью:

```bash
dotnet add package Aspose.BarCode
```

Вот и всё — никаких дополнительных DLL, никаких файлов конфигурации.

## Шаг 1: Настройка проекта Barcode Generator C#  

Сначала создайте новый консольный проект и подключите библиотеку штрих‑кодов.

```bash
dotnet new console -n BarcodeHeightDemo
cd BarcodeHeightDemo
dotnet add package Aspose.BarCode
```

Теперь откройте `Program.cs`. Мы добавим необходимые директивы `using` в начале:

```csharp
using System;
using Aspose.BarCode.Generation;   // Core barcode generator classes
using Aspose.BarCode;               // For image format enums
```

Эти пространства имён дают доступ к `BarcodeGenerator`, `EncodeTypes` и `BarCodeImageFormat`.

## Шаг 2: Генерация начального изображения штрих‑кода PNG  

Внутри `Main` создайте экземпляр генератора с типом **DataBar Omni‑directional** и примером полезной нагрузки GS1‑128. Параметр `XDimension` задаёт пиксельную ширину каждой узкой полосы; для демонстрации оставим его равным 2 пикселям.

```csharp
static void Main(string[] args)
{
    // Step 2.1: Create a DataBar Omni‑directional barcode generator
    var barcodeGen = new BarcodeGenerator(
        EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");

    // Step 2.2: Set the X‑dimension (width of the thinnest bar)
    barcodeGen.Parameters.Barcode.XDimension.Pixels = 2;

    // Step 2.3: Define the initial bar height (30 pixels)
    barcodeGen.Parameters.Barcode.BarHeight.Pixels = 30;

    // Step 2.4: Save the first image as PNG
    barcodeGen.Save("DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);
    Console.WriteLine("Saved 30‑pixel barcode as PNG.");
```

Запуск программы сейчас создаст файл `DatabarBarHeight30Pixels.png` в папке проекта. Откройте его — вы увидите компактный штрих‑код с умеренной высотой полос.

## Шаг 3: Настройка высоты штрих‑кода для изображения Barcode Image PNG  

Изменить высоту так же просто, как присвоить новое значение свойству `BarHeight.Pixels`. Нет необходимости воссоздавать генератор; объект изменяемый.

```csharp
    // Step 3.1: Increase the bar height to 60 pixels
    barcodeGen.Parameters.Barcode.BarHeight.Pixels = 60;

    // Step 3.2: Save the larger version
    barcodeGen.Save("DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);
    Console.WriteLine("Saved 60‑pixel barcode as PNG.");
}
```

Это и есть суть **how to change barcode** размеров в C#. Вы можете задать любое целое значение — 30, 45, 120 — в зависимости от размера этикетки. Библиотека автоматически пересчитает расположение модулей, сохраняя совместимость со сканерами.

## Шаг 4: Проверка результата  

После второго вызова `Save` у вас должно быть два PNG‑файла:

| Имя файла                     | Высота полос (пикселей) |
|-------------------------------|--------------------------|
| `DatabarBarHeight30Pixels.png`| 30                       |
| `DatabarBarHeight60Pixels.png`| 60                       |

Откройте каждое изображение в любимом просмотрщике. Версия с 60 пикселями должна выглядеть выше, но сохранять ту же ширину и кодировку. Если измерить полосы экранной линейкой, вы увидите удвоенную высоту — именно то, что мы запросили.

## Распространённые подводные камни при изменении высоты штрих‑кода  

| Проблема                              | Почему происходит                              | Решение |
|---------------------------------------|-----------------------------------------------|---------|
| **Изображение обрезается**            | Путь к папке вывода неверный или только для чтения. | Используйте абсолютный путь или убедитесь, что есть права на запись. |
| **Сканер не считывает**              | Слишком экстремальная высота (например, > 200 px) нарушает соотношение сторон. | Держите высоту в диапазоне 20–150 px для большинства сканеров; протестируйте на реальном устройстве. |
| **X‑dimension выглядит некорректно** | Изменение высоты без корректировки X‑dimension может сделать полосы слишком тонкими. | Отрегулируйте `XDimension.Pixels` вместе с `BarHeight.Pixels` для сбалансированного вида. |
| **Неправильный EncodeTypes**          | Использование линейного типа штрих‑кода для настроек DataBar. | Убедитесь, что используете `EncodeTypes.DatabarOmniDirectional` для полезной нагрузки GS1‑128. |

Эти советы помогут избежать самых частых ошибок при **adjusting barcode height**.

## Профессиональные советы для готовой к продакшену реализации Barcode Generator C#  

- **Cache the generator** если вы генерируете десятки штрих‑кодов с одинаковыми настройками; меняйте только строку данных и высоту полосы при каждой итерации.  
- **Batch save** путем перебора списка высот и вызова `Save` внутри цикла — удобно для создания спрайт‑листа размеров штрих‑кодов.  
- **Compress PNGs** с помощью `System.Drawing` или `ImageSharp`, если нужны более мелкие файлы для веб‑доставки.  
- **Validate the barcode** используя `barcodeGen.Validate()` перед сохранением; он бросает исключение, если данные не соответствуют стандартам GS1.  

## Полный исходный код (готовый к копированию и вставке)

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

namespace BarcodeHeightDemo
{
    class Program
    {
        static void Main(string[] args)
        {
            // Create a DataBar Omni‑directional barcode generator with sample data
            var barcodeGen = new BarcodeGenerator(
                EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");

            // Set common parameters
            barcodeGen.Parameters.Barcode.XDimension.Pixels = 2;   // Width of the thinnest bar
            barcodeGen.Parameters.Barcode.BarHeight.Pixels = 30; // Initial height

            // Save the 30‑pixel version
            barcodeGen.Save("DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);
            Console.WriteLine("Saved 30‑pixel barcode as PNG.");

            // Change the bar height to 60 pixels for a larger barcode
            barcodeGen.Parameters.Barcode.BarHeight.Pixels = 60;

            // Save the 60‑pixel version
            barcodeGen.Save("DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);
            Console.WriteLine("Saved 60‑pixel barcode as PNG.");
        }
    }
}
```

Запустите программу командой `dotnet run`. Появятся два PNG‑файла рядом, демонстрирующие **how to generate barcode** изображения разной высоты.

## Заключение

Мы только что рассмотрели **how to change barcode** высоту в C# от начала до конца. Создав `BarcodeGenerator`, отрегулировав `BarHeight.Pixels` и сохранив результат как **barcode image PNG**, вы получаете полный контроль над визуальным размером ваших штрих‑кодов без потери надёжности сканирования.

Теперь вы можете:

- Генерировать любой тип штрих‑кода, поддерживаемый библиотекой (`how to generate barcode`).  
- Настраивать его размеры (`adjust barcode height`) на лету.  
- Экспортировать чистые PNG‑файлы для печати, веба или мобильных приложений (`barcode image png`).  

Следующие шаги? Попробуйте заменить `EncodeTypes.DatabarOmniDirectional` на QR‑коды, поэкспериментировать с цветами через `barcodeGen.Parameters.Barcode.ForeColor` или интегрировать генератор в API ASP.NET Core, которое возвращает PNG‑потоки по запросу.

Есть вопросы о крайних случаях или альтернативных библиотеках? Оставьте комментарий ниже — приятного кодинга!

## Что стоит изучить дальше?

Следующие руководства охватывают тесно связанные темы, которые развивают техники, продемонстрированные в этом руководстве. Каждый ресурс включает полностью рабочие примеры кода с пошаговыми объяснениями, чтобы помочь вам освоить дополнительные возможности API и исследовать альтернативные подходы к реализации в ваших проектах.

- [Как изменить границу – Генерация типа границы штрих‑кода ITF-14](/barcode/english/net/itf-14-barcode-customization/itf-14-barcode-border-type-generation/)
- [Как генерировать штрих‑код — Одномерные типы штрих‑кодов](/barcode/english/net/one-dimensional-barcode-types/)
- [Как генерировать Aztec‑штрих‑код с пользовательским соотношением сторон с помощью Aspose.BarCode for .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}