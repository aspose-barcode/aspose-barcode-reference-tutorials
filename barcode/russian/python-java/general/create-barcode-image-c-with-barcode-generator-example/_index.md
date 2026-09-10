---
category: general
date: 2026-09-10
description: Быстро создайте изображение штрихкода на C# с помощью примера генератора
  штрихкодов, показывающего, как задать размеры и сохранить PNG‑файлы.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode image c#
- barcode generator example c#
language: ru
lastmod: 2026-09-10
og_description: Создайте изображение штрихкода на C# с помощью лаконичного примера
  генератора штрихкодов C#. Научитесь настраивать размер, высоту и экспортировать
  PNG‑файлы за считанные минуты.
og_image_alt: Screenshot of a barcode image created with C# code
og_title: Создание изображения штрих‑кода C# – пошаговый пример генератора
schemas:
- author: Aspose
  dateModified: '2026-09-10'
  description: Create barcode image C# quickly using a barcode generator example C#
    that shows how to set dimensions and save PNG files.
  headline: Create barcode image C# with barcode generator example
  type: TechArticle
tags:
- barcode
- C#
- image generation
title: Создать изображение штрихкода C# с примером генератора штрихкода
url: /ru/python-java/general/create-barcode-image-c-with-barcode-generator-example/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Создание изображения штрих‑кода C# с примером генератора штрих‑кодов

Если вам нужно **create barcode image C#** для маркировки продукции, учёта запасов или мобильного сканирования, это руководство показывает полное решение. Вы увидите **barcode generator example C#**, который настраивает ширину модуля, высоту штрихов и сохраняет PNG‑файлы всего в несколько строк кода.

В этом учебнике рассматривается всё: от установки необходимой библиотеки до запуска готовой к компиляции консольной программы. По завершении у вас будет два PNG‑файла штрих‑кода — один с высотой штриха 30 пикселей, другой — 60 пикселей, готовые к использованию в любом приложении .NET.

## Prerequisites

Прежде чем начать, убедитесь, что у вас есть:

* .NET 6.0 SDK или более поздняя версия  
* Среда разработки, например Visual Studio 2022 или VS Code  
* Пакет NuGet **Aspose.BarCode** (в коде используется `BarcodeGenerator` из этой библиотеки)  

Вы можете добавить пакет с помощью следующей команды CLI:

```bash
dotnet add package Aspose.BarCode
```

## Step 1: Set up the console project

Создайте новый консольный проект и подключите библиотеку штрих‑кодов.

```bash
dotnet new console -n BarcodeDemo
cd BarcodeDemo
dotnet add package Aspose.BarCode
```

Эта команда создаёт файл `Program.cs`, в который вы поместите код **barcode generator example C#**.

## Step 2: Write the full barcode generation program

Замените содержимое `Program.cs` полным, готовым к запуску примером ниже. Программа демонстрирует, как **create barcode image C#** с пользовательскими размерами и как сохранить результат в виде PNG‑файлов.

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
            // 1️⃣ Create a DataBar Omnidirectional barcode generator with the desired data.
            // The string "(01)12345678901231" follows the GS1 Application Identifier format.
            var generator = new BarcodeGenerator(
                EncodeTypes.DatabarOmniDirectional,
                "(01)12345678901231");

            // 2️⃣ Set the X‑dimension (module width) to 2 pixels.
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // 3️⃣ Configure a 30‑pixel bar height and save the first image.
            generator.Parameters.Barcode.BarHeight.Pixels = 30;
            SaveBarcode(generator, "DatabarBarHeight30Pixels.png");

            // 4️⃣ Change the bar height to 60 pixels and save the second image.
            generator.Parameters.Barcode.BarHeight.Pixels = 60;
            SaveBarcode(generator, "DatabarBarHeight60Pixels.png");

            Console.WriteLine("Barcode images have been saved to the output folder.");
        }

        /// <summary>
        /// Saves the current barcode image as a PNG file.
        /// </summary>
        /// <param name="generator">The configured BarcodeGenerator instance.</param>
        /// <param name="fileName">The file name for the PNG image.</param>
        private static void SaveBarcode(BarcodeGenerator generator, string fileName)
        {
            // Ensure the output directory exists.
            string outputPath = System.IO.Path.Combine(
                AppDomain.CurrentDomain.BaseDirectory, "output");
            System.IO.Directory.CreateDirectory(outputPath);

            // Combine the directory and file name.
            string fullPath = System.IO.Path.Combine(outputPath, fileName);

            // Save the barcode as a PNG image.
            generator.Save(fullPath, BarCodeImageFormat.Png);
        }
    }
}
```

### Why each line matters

* **EncodeTypes.DatabarOmniDirectional** – выбирает символьную схему DataBar Omnidirectional, которая кодирует числовые данные и широко используется в розничной торговле.  
* **XDimension.Pixels = 2** – задаёт ширину модуля; меньшее значение делает штрих‑код более компактным.  
* **BarHeight.Pixels** – управляет визуальной высотой штрихов. Регулируя это значение, вы можете создавать штрих‑коды, подходящие под разные размеры этикеток.  
* **Save method** – записывает штрих‑код в PNG‑файл, формат сохраняет чёткие края и совместим с большинством графических библиотек.

## Step 3: Build and run the program

Выполните следующую команду из папки проекта:

```bash
dotnet run
```

Когда программа завершится, вы увидите два PNG‑файла в подпапке `output`:

* `DatabarBarHeight30Pixels.png` – высота штриха 30 пикселей  
* `DatabarBarHeight60Pixels.png` – высота штриха 60 пикселей  

Оба изображения содержат одинаковые закодированные данные, но различаются визуальной высотой, что демонстрирует, как **barcode generator example C#** можно адаптировать под разные требования к этикеткам.

## Step 4: Verify the generated barcodes

Откройте PNG‑файлы в любом просмотрщике изображений. Вы должны увидеть чёткий, контрастный штрих‑код DataBar. Чтобы убедиться, что штрих‑коды читаются, можно воспользоваться мобильным сканером (например, приложениями на базе ZXing) или настольной библиотекой, такой как **Aspose.BarCode**, в режиме декодирования:

```csharp
var reader = new BarCodeReader(fullPath, DecodeType.DatabarOmniDirectional);
foreach (BarCodeResult result in reader.ReadBarCodes())
{
    Console.WriteLine($"Decoded value: {result.CodeText}");
}
```

Если вывод совпадает с `(01)12345678901231`, генерация прошла успешно.

## Common variations and edge cases

| Situation | Adjustment | Code snippet |
|-----------|------------|--------------|
| **Different symbology** (e.g., QR, Code128) | Change `EncodeTypes` value | `new BarcodeGenerator(EncodeTypes.QR, "Hello World")` |
| **Custom image format** (JPEG, BMP) | Use a different `BarCodeImageFormat` enum | `generator.Save(path, BarCodeImageFormat.Jpeg)` |
| **Dynamic data** (user input) | Replace the hard‑coded string with a variable | `string data = Console.ReadLine(); var generator = new BarcodeGenerator(EncodeTypes.DatabarOmniDirectional, data);` |
| **Invalid data length** | Catch `ArgumentException` thrown by the generator | ```csharp try { ... } catch (ArgumentException ex) { Console.WriteLine(ex.Message); }``` |

Pro tip: всегда проверяйте длину входных данных для выбранной символьной схемы; Aspose.BarCode бросает исключение, если данные не соответствуют спецификации.

## Troubleshooting checklist

* **Directory not found** – вспомогательная функция `SaveBarcode` автоматически создаёт папку `output`, но убедитесь, что приложение имеет права записи.  
* **Unexpected image size** – проверьте, что `XDimension.Pixels` и `BarHeight.Pixels` заданы до вызова `Save`. Изменение этих значений после сохранения не влияет на уже записанные файлы.  
* **Unreadable barcode** – убедитесь, что закодированная строка соответствует формату GS1 при использовании символьных схем DataBar. Отсутствие скобок или неверные идентификаторы приложений приводят к ошибкам декодирования.

## Conclusion

Теперь вы знаете, как **create barcode image C#** с помощью практического **barcode generator example C#**. Полная программа задаёт ширину модуля, регулирует высоту штрихов и сохраняет PNG‑файлы с минимальным объёмом кода. Дальше вы можете исследовать дополнительные возможности, такие как настройка цвета, экспорт в много‑страничный PDF или генерация в реальном времени в веб‑API ASP.NET Core.

**Next steps**

* Поэкспериментировать с другими символьными схемами (`EncodeTypes.Code128`, `EncodeTypes.QR`), чтобы расширить варианты сканирования.  
* Интегрировать генератор в веб‑службу, возвращающую изображения штрих‑кодов по запросу.  
* Объединить штрих‑код с метаданными продукта в PDF‑счете с помощью Aspose.PDF.

Happy coding, and enjoy the flexibility that C# provides for barcode image creation!

## What Should You Learn Next?

The following tutorials cover closely related topics that build on the techniques demonstrated in this guide. Each resource includes complete working code examples with step-by-step explanations to help you master additional API features and explore alternative implementation approaches in your own projects.

- [Barcode Generator Example in C# – Set Columns, Rows & Export Image](/barcode/english/python-java/general/barcode-generator-example-in-c-set-columns-rows-export-image/)
- [Create barcode image C# – GS1 DataMatrix Example](/barcode/english/net/gs1-barcode-encoding/gs1-datamatrix-example/)
- [Barcode Generator Example – Build DataBar Image in C#](/barcode/english/python-java/general/barcode-generator-example-build-databar-image-in-c/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}