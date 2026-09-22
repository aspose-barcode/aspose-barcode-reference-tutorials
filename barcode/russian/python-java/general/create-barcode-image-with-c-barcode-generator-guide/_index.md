---
category: general
date: 2026-08-09
description: Создайте изображение штрихкода с помощью генератора штрихкодов на C#
  и научитесь генерировать несколько штрихкодов с пользовательскими соотношениями
  сторон за считанные минуты.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode image
- c# barcode generator
- generate multiple barcodes
- barcode aspect ratio
- barcode image format
language: ru
lastmod: 2026-08-09
og_description: Создайте изображение штрихкода с помощью генератора штрихкодов на
  C#. Этот учебник показывает, как генерировать несколько штрихкодов, регулировать
  соотношения сторон и эффективно сохранять файлы PNG.
og_image_alt: Example of create barcode image output with aspect ratios 15 and 30
  using C# barcode generator
og_title: Создайте изображение штрихкода с помощью генератора штрихкодов на C# – краткое
  руководство
schemas:
- author: Aspose
  dateModified: '2026-08-09'
  description: Create barcode image with a C# barcode generator and learn to generate
    multiple barcodes with custom aspect ratios in minutes.
  headline: Create barcode image with C# barcode generator – guide
  type: TechArticle
tags:
- barcode
- C#
- image generation
title: Создание изображения штрихкода с помощью генератора штрихкодов на C# – руководство
url: /ru/python-java/general/create-barcode-image-with-c-barcode-generator-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Создание изображения штрихкода с помощью C# barcode generator – руководство

Если вам нужно **create barcode image** быстро, это руководство покажет, как сделать это с помощью C# barcode generator. Вы научитесь генерировать несколько штрихкодов, менять соотношение сторон и сохранять каждое изображение в файл PNG.

Генерация изображений штрихкодов — распространённая задача при построении систем учёта, точек продаж или этикеток для отправки. К концу этого руководства у вас будет два готовых PNG‑файла, демонстрирующих разные соотношения сторон, и вы поймёте, как расширить подход для любого количества штрихкодов.

## Prerequisites

Перед началом убедитесь, что у вас есть:

* .NET 6.0 SDK или более поздняя версия  
* Visual Studio 2022 (или любая IDE, поддерживающая C#)  
* Ссылка на библиотеку штрихкодов, поддерживающую DataBar Stacked Omnidirectional (например, **Aspose.BarCode for .NET**). В примерах используется API Aspose, но концепции применимы к любой библиотеке с аналогичными свойствами.

Отдельную базу данных или веб‑сервер не требуется — это обычное консольное приложение.

## Step 1: Set up the console project

Создайте новый консольный проект и добавьте библиотеку штрихкодов через NuGet.

```bash
dotnet new console -n BarcodeDemo
cd BarcodeDemo
dotnet add package Aspose.BarCode
```

Команда `dotnet add package` загружает последнюю стабильную версию **Aspose.BarCode**, которая предоставляет класс `BarcodeGenerator`, используемый далее.

## Step 2: Write the full program

Откройте *Program.cs* и замените его содержимое полным примером ниже. Программа создаёт **barcode image**, меняет соотношение сторон и сохраняет два PNG‑файла.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // -----------------------------------------------------------------
            // 1️⃣ Create a DataBar Stacked Omnidirectional generator with sample data
            // -----------------------------------------------------------------
            // The EncodeTypes enum tells the generator which barcode symbology to use.
            // Here we use DataBar Stacked Omnidirectional (GS1 DataBar) and encode
            // a sample GTIN (01) followed by a 14‑digit numeric string.
            var generator = new BarcodeGenerator(
                EncodeTypes.DatabarStackedOmniDirectional,
                "(01)12345678901231");

            // -----------------------------------------------------------------
            // 2️⃣ Configure common parameters (pixel size and X‑dimension)
            // -----------------------------------------------------------------
            // XDimension.Pixels controls the width of the smallest bar in the image.
            // A value of 2 gives a clear, high‑resolution output without increasing file size.
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // -----------------------------------------------------------------
            // 3️⃣ Set the first aspect ratio (15) and save the image
            // -----------------------------------------------------------------
            // AspectRatio influences the height of the barcode relative to its width.
            // An aspect ratio of 15 is typical for compact labels.
            generator.Parameters.Barcode.DataBar.AspectRatio = 15;

            string outputFolder = "BarcodeOutputs/";
            System.IO.Directory.CreateDirectory(outputFolder); // Ensure folder exists

            string file15 = $"{outputFolder}DatabarAspectRatio15.png";
            generator.Save(file15, BarCodeImageFormat.Png);
            Console.WriteLine($"Saved barcode with aspect ratio 15 → {file15}");

            // -----------------------------------------------------------------
            // 4️⃣ Change the aspect ratio to 30 and save a second image
            // -----------------------------------------------------------------
            // A larger aspect ratio (e.g., 30) produces a taller barcode, useful for
            // scanning devices that expect more vertical space.
            generator.Parameters.Barcode.DataBar.AspectRatio = 30;

            string file30 = $"{outputFolder}DatabarAspectRatio30.png";
            generator.Save(file30, BarCodeImageFormat.Png);
            Console.WriteLine($"Saved barcode with aspect ratio 30 → {file30}");

            // -----------------------------------------------------------------
            // 5️⃣ Verify that both files exist
            // -----------------------------------------------------------------
            Console.WriteLine("\nVerification:");
            Console.WriteLine($"File 15 exists: {System.IO.File.Exists(file15)}");
            Console.WriteLine($"File 30 exists: {System.IO.File.Exists(file30)}");
        }
    }
}
```

### Why each part matters

* **Create barcode image** – Конструктор `BarcodeGenerator` инициализирует объект с нужной символьностью и данными.  
* **c# barcode generator** – Свойство `Parameters` даёт полный контроль над параметрами рендеринга; установка `XDimension.Pixels` гарантирует чёткость каждой полосы на экране.  
* **generate multiple barcodes** – Изменяя `DataBar.AspectRatio` между сохранениями, один экземпляр генератора создаёт два разных изображения без повторного создания объекта, что более эффективно.

## Step 3: Run the program and view the results

Запустите приложение:

```bash
dotnet run
```

Вы должны увидеть вывод в консоли, похожий на:

```
Saved barcode with aspect ratio 15 → BarcodeOutputs/DatabarAspectRatio15.png
Saved barcode with aspect ratio 30 → BarcodeOutputs/DatabarAspectRatio30.png

Verification:
File 15 exists: True
File 30 exists: True
```

Откройте папку `BarcodeOutputs`. Вы найдёте два PNG‑файла:

* **DatabarAspectRatio15.png** – компактный штрихкод, подходящий для этикеток с ограниченной высотой.  
* **DatabarAspectRatio30.png** – более высокий штрихкод, который многие сканеры читают надёжнее с расстояния.

Оба изображения готовы к внедрению в PDF, печати на чеках или отправке в мобильное приложение.

## Step 4: Extend the solution to generate any number of barcodes

Показанный выше шаблон легко масштабируется:

```csharp
int[] ratios = { 10, 15, 20, 30, 40 };
foreach (int ratio in ratios)
{
    generator.Parameters.Barcode.DataBar.AspectRatio = ratio;
    string path = $"{outputFolder}DatabarAspectRatio{ratio}.png";
    generator.Save(path, BarCodeImageFormat.Png);
    Console.WriteLine($"Saved aspect ratio {ratio} → {path}");
}
```

* **generate multiple barcodes** – Цикл проходит по массиву соотношений сторон, создавая отдельное **barcode image** для каждого значения.  
* Измените `EncodeTypes` или строку для кодирования, чтобы получать QR‑коды, Code 128 или другие символьности без изменения основной логики.

## Practical tips and common pitfalls

| Tip | Explanation |
|-----|-------------|
| **Reuse the same generator** | Повторная инициализация `BarcodeGenerator` для каждого изображения добавляет лишние затраты. Изменение параметров между вызовами `Save` быстрее и требует меньше памяти. |
| **Validate the output folder** | Всегда вызывайте `Directory.CreateDirectory` перед сохранением; иначе `Save` бросит `DirectoryNotFoundException`. |
| **Choose an appropriate X‑dimension** | Очень низкие пиксельные значения (например, 1) могут сделать штрихкод нечитаемым на экранах с низким разрешением. Значения 2–3 хорошо работают для большинства принтеров. |
| **Mind the encoding** | GS1 DataBar ожидает ведущий `(01)` для GTIN. Если опустить скобки, библиотека может сгенерировать недействительный штрихкод. |
| **Test with a real scanner** | Визуальная проверка недостаточна. Тестируйте PNG‑файлы на реальном сканере, который планируете использовать. |

## Expected output (visual description)

*Оба PNG‑файла показывают темный на светлом DataBar Stacked Omnidirectional штрихкод. Версия с соотношением 15 короче, а версия с соотношением 30 примерно вдвое выше.*  

Если вы вставите изображения в документ, они отобразятся чётко, потому что мы задали `XDimension.Pixels = 2`.

## Conclusion

Теперь вы знаете, как **create barcode image** файлы с помощью **C# barcode generator**, и как **generate multiple barcodes**, меняя соотношение сторон или любой другой параметр. Полный, готовый к запуску пример демонстрирует лучшие практики, такие как повторное использование экземпляра генератора, обработка каталогов вывода и проверка создания файлов.

Далее вы можете изучить:

* Добавление пользовательских цветов через `generator.Parameters.Barcode.Color` (вторичное ключевое слово: **c# barcode generator**)  
* Экспорт в другие форматы, такие как JPEG или SVG (`BarCodeImageFormat.Jpeg`, `BarCodeImageFormat.Svg`)  
* Интеграцию логики создания штрихкода в Web API для обслуживания изображений по запросу (вторичное ключевое слово

## What Should You Learn Next?

Следующие руководства охватывают тесно связанные темы, которые развивают техники, продемонстрированные в этом руководстве. Каждый ресурс включает полностью рабочие примеры кода с пошаговыми объяснениями, помогающими освоить дополнительные возможности API и исследовать альтернативные подходы в ваших проектах.

- [Create Barcode PNG – DataMatrix Aspect Ratio – Aspose.BarCode](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-aspect-ratio-customization/)
- [barcode generator tutorial c# – Customize Code 16K Barcode Aspect Ratios with Aspose.BarCode for .NET](/barcode/english/net/code-16k-encoding/code-16k-aspect-ratio-customization/)
- [How to generate Aztec barcode with custom aspect ratio using Aspose.BarCode for .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}