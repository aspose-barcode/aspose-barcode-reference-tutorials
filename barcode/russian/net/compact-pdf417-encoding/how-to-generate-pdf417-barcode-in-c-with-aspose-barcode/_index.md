---
category: general
date: 2026-11-27
description: Узнайте, как генерировать штрих‑код PDF417 на C# с помощью Aspose.BarCode.
  Регулируйте размеры, задавайте количество колонок и сохраняйте в PNG за несколько
  строк кода.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate PDF417 barcode
- Aspose.BarCode C#
- PDF417 barcode dimensions
- barcode image PNG
- BarcodeGenerator usage
language: ru
lastmod: 2026-11-27
og_description: Сгенерируйте штрих‑код PDF417 на C# мгновенно. Этот учебник показывает,
  как настроить размеры, количество столбцов и сохранить результат в виде PNG‑изображения.
og_image_alt: Screenshot showing a generated PDF417 barcode saved as a PNG file
og_title: Создание штрихкода PDF417 в C# – быстрое руководство с Aspose.BarCode
schemas:
- author: Aspose
  dateModified: '2026-11-27'
  description: Learn how to generate PDF417 barcode in C# using Aspose.BarCode. Adjust
    dimensions, set column count, and save as PNG in a few lines of code.
  headline: How to generate PDF417 barcode in C# with Aspose.BarCode
  type: TechArticle
- description: Learn how to generate PDF417 barcode in C# using Aspose.BarCode. Adjust
    dimensions, set column count, and save as PNG in a few lines of code.
  name: How to generate PDF417 barcode in C# with Aspose.BarCode
  steps:
  - name: Why each line matters
    text: '* **BarcodeGenerator** – the core class that creates a barcode image. Passing
      `EncodeTypes.Pdf417` selects the PDF417 symbology. * **XDimension.Pixels** –
      determines the smallest bar width. Smaller values shrink the image; larger values
      improve readability on low‑resolution scanners. * **Pdf417.Colu'
  - name: Changing the encoded data
    text: 'Replace the second argument of `BarcodeGenerator` with any UTF‑8 string,
      e.g.:'
  - name: Adjusting image size without losing quality
    text: 'If you need a larger image for printing, increase `XDimension.Pixels`:'
  - name: Handling very long inputs
    text: 'PDF417 can encode up to 1 850 characters. For extremely long strings, you
      may want to increase the column count:'
  - name: Saving in other formats
    text: 'Aspose.BarCode supports BMP, JPEG, TIFF, and SVG. Change the format like
      this:'
  type: HowTo
tags:
- barcode
- PDF417
- C#
- Aspose
title: Как сгенерировать штрих‑код PDF417 в C# с помощью Aspose.BarCode
url: /ru/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-with-aspose-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Как сгенерировать штрих‑код PDF417 в C# с помощью Aspose.BarCode

Если вам нужно **сгенерировать штрих‑код PDF417** в .NET‑приложении, это руководство покажет вам краткое решение от начала до конца. Вы увидите, как создать штрих‑код, точно настроить его размер и записать результат в файл PNG — всё с помощью библиотеки Aspose.BarCode.

Создание штрих‑кода PDF417 часто требуется, когда нужно закодировать большие объёмы данных для сканирования на мобильных устройствах, посадочных талонах или бирках инвентаря. К концу этого руководства у вас будет готовая к запуску консольная программа, генерирующая высококачественное изображение PNG.

## Требования

* .NET 6.0 SDK или более поздняя версия, установленная  
* Последняя версия **Aspose.BarCode for .NET** (пакет NuGet `Aspose.BarCode`)  
* IDE или редактор (Visual Studio, VS Code, Rider и т.д.)  

Код работает в Windows, Linux и macOS, поскольку Aspose.BarCode кросс‑платформенный.

## Шаг 1: Создать новый консольный проект

Откройте терминал и выполните:

```bash
dotnet new console -n Pdf417Demo
cd Pdf417Demo
dotnet add package Aspose.BarCode
```

Это создаёт минимальный C#‑проект с именем **Pdf417Demo** и добавляет зависимость `Aspose.BarCode`.

## Шаг 2: Написать код генерации штрих‑кода

Откройте **Program.cs** и замените его содержимое следующим кодом:

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace Pdf417Demo
{
    class Program
    {
        static void Main(string[] args)
        {
            // 1️⃣ Create a PDF417 barcode generator with the desired text
            // EncodeTypes.Pdf417 tells Aspose.BarCode which symbology to use.
            BarcodeGenerator generator = new BarcodeGenerator(
                EncodeTypes.Pdf417, "Sample text for PDF417 barcode");

            // 2️⃣ Adjust barcode dimensions and column count
            // XDimension controls the width of a single module (pixel size).
            // Setting it to 2 pixels yields a compact yet readable barcode.
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // Columns define how many data columns the barcode will have.
            // A value of 3 works well for short strings; increase for longer data.
            generator.Parameters.Barcode.Pdf417.Columns = 3;

            // Optional: increase error correction level for more robust scanning.
            generator.Parameters.Barcode.Pdf417.ErrorCorrectionLevel = 2;

            // 3️⃣ Save the generated barcode as a PNG file
            // The output path can be absolute or relative to the project folder.
            string outputPath = "Pdf417Basic.png";
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"PDF417 barcode saved to '{outputPath}'.");
        }
    }
}
```

### Почему каждая строка важна

* **BarcodeGenerator** – основной класс, создающий изображение штрих‑кода. Передача `EncodeTypes.Pdf417` выбирает символьную схему PDF417.  
* **XDimension.Pixels** – определяет минимальную ширину полосы. Меньшие значения уменьшают изображение; большие значения повышают читаемость на сканерах с низким разрешением.  
* **Pdf417.Columns** – управляет количеством столбцов данных. Большее количество столбцов даёт более короткий, но более высокий штрих‑код; меньше столбцов делает его шире.  
* **ErrorCorrectionLevel** – более высокий уровень добавляет избыточные данные, делая штрих‑код устойчивым к повреждениям, но увеличивая размер.  
* **Save(..., BarCodeImageFormat.Png)** – сохраняет изображение на диск в формате PNG, без потерь, что идеально подходит для дальнейшей обработки или встраивания в документы.

## Шаг 3: Скомпилировать и запустить программу

В терминале выполните:

```bash
dotnet run
```

Вы должны увидеть:

```
PDF417 barcode saved to 'Pdf417Basic.png'.
```

В папке проекта появится файл **Pdf417Basic.png**. При открытии вы увидите чёткий штрих‑код PDF417, который кодирует текст *«Sample text for PDF417 barcode»*.

![Сгенерированный штрих‑код PDF417, сохранённый в файл PNG](pdf417-barcode-example.png "Сгенерированный штрих‑код PDF417 в формате PNG")

*Текст alt изображения: скриншот сгенерированного штрих‑кода PDF417, сохранённого в файл PNG, демонстрирующий результат руководства по генерации штрих‑кода PDF417.*

## Шаг 4: Общие варианты и граничные случаи

### Изменение кодируемых данных

Замените второй аргумент `BarcodeGenerator` любой строкой UTF‑8, например:

```csharp
new BarcodeGenerator(EncodeTypes.Pdf417, "https://example.com/checkout?order=12345")
```

Генератор автоматически разбивает данные по строкам и столбцам.

### Регулировка размера изображения без потери качества

Если требуется более крупное изображение для печати, увеличьте `XDimension.Pixels`:

```csharp
generator.Parameters.Barcode.XDimension.Pixels = 4; // double the module width
```

### Обработка очень длинных входных данных

PDF417 может кодировать до 1 850 символов. Для чрезвычайно длинных строк вы можете увеличить количество столбцов:

```csharp
generator.Parameters.Barcode.Pdf417.Columns = 5; // more columns, less height
```

Если содержимое превышает максимальную ёмкость, Aspose.BarCode генерирует `ArgumentException`. Оберните код генерации в блок try‑catch, чтобы вывести понятное сообщение об ошибке.

### Сохранение в других форматах

Aspose.BarCode поддерживает BMP, JPEG, TIFF и SVG. Измените формат следующим образом:

```csharp
generator.Save("Pdf417Vector.svg", BarCodeImageFormat.Svg);
```

## Шаг 5: Проверка штрих‑кода

Вы можете убедиться в корректности штрих‑кода, отсканировав его любой программой‑чтением PDF417 (например, приложениями камеры смартфона, поддерживающими сканирование штрих‑кодов). Декодированный текст должен совпадать со строкой, переданной генератору.

Если сканирование не удалось:

* Убедитесь, что изображение не сжато (используйте PNG или без потерь SVG).  
* Проверьте, что `ErrorCorrectionLevel` достаточно высок для предполагаемой среды.  
* Убедитесь, что размеры штрих‑кода соответствуют разрешению сканера.

## Заключение

Теперь вы знаете, как **сгенерировать штрих‑код PDF417** в C# с помощью Aspose.BarCode, настроить его размеры, задать количество столбцов и экспортировать результат в виде изображения PNG. Этот подход подходит для широкого спектра сценариев, от мобильных билетов до управления инвентарём.

Далее вы можете изучить:

* **Чтение** штрих‑кода PDF417 с помощью `BarCodeReader`.  
* Генерацию других символьных схем, таких как QR Code или DataMatrix.  
* Встраивание PNG в PDF‑файлы, отчёты или веб‑страницы.  

Не стесняйтесь экспериментировать с различными уровнями коррекции ошибок, форматами изображений и объёмом данных, чтобы подобрать оптимальное решение для вашего проекта. Приятного кодирования!

## Что изучать дальше?

Следующие руководства охватывают тесно связанные темы, опирающиеся на техники, продемонстрированные в этом руководстве. Каждый ресурс содержит полностью работающие примеры кода с пошаговыми объяснениями, помогающими освоить дополнительные возможности API и исследовать альтернативные подходы к реализации в ваших проектах.

- [Как сгенерировать штрих‑код PDF417 в C# с помощью Aspose.BarCode BarcodeGenerator](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-with-barcodegenerator/)
- [Как сгенерировать штрих‑код PDF417 и отобразить его как PNG](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-and-render-it-as-png/)
- [Как сгенерировать штрих‑код PDF417 в C# и задать размер штрих‑кода](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-and-set-barcode-size/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}