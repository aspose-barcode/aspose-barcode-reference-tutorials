---
category: general
date: 2026-10-21
description: Создайте изображение штрих‑кода Databar Expanded Stacked в C# с помощью
  BarcodeGenerator. Следуйте этому пошаговому руководству, чтобы создавать изображения
  штрих‑кодов, настраивать строки и столбцы и экспортировать файлы PNG.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- databar expanded stacked
- generate barcode image
- barcode generator c#
- how to generate databar
- create databar barcode
language: ru
lastmod: 2026-10-21
og_description: Создайте расширенный многослойный штрихкод Databar в C# с помощью
  этого руководства. Узнайте, как использовать BarcodeGenerator, задавать строки и
  столбцы и сохранять изображения в формате PNG.
og_image_alt: Sample databar expanded stacked barcode image generated with C#
og_title: Создайте расширенный многослойный штрих‑код Databar в C# – полное руководство
schemas:
- author: Aspose
  dateModified: '2026-10-21'
  description: Generate a databar expanded stacked barcode image in C# using BarcodeGenerator.
    Follow this step‑by‑step guide to create barcode images, customize rows and columns,
    and export PNG files.
  headline: How to generate a databar expanded stacked barcode in C#
  type: TechArticle
- description: Generate a databar expanded stacked barcode image in C# using BarcodeGenerator.
    Follow this step‑by‑step guide to create barcode images, customize rows and columns,
    and export PNG files.
  name: How to generate a databar expanded stacked barcode in C#
  steps:
  - name: Basic barcode generation
    text: The simplest way to generate a **databar expanded stacked** image is to
      instantiate `BarcodeGenerator` with the desired `EncodeTypes` value and a plain
      text payload.
  - name: Customizing columns – create databar barcode with 4 columns
    text: You can control the number of columns using the `Parameters.Barcode.DataBar.Columns`
      property. The following example creates a barcode with **4 columns** while keeping
      the default row count.
  - name: Customizing rows – create databar barcode with 3 rows
    text: Similarly, you can adjust the row count via `Parameters.Barcode.DataBar.Rows`.
      The code below generates a barcode with **3 rows** and the default column count
      (4).
  - name: Exporting to other formats
    text: 'If you need a different image type (e.g., JPEG, BMP, or SVG), replace `BarCodeImageFormat.Png`
      with the appropriate enum value:'
  - name: Saving to a memory stream
    text: 'Sometimes you want to embed the barcode directly into a web response or
      a PDF without touching the file system. Use a `MemoryStream`:'
  - name: Handling invalid input
    text: 'The `BarcodeGenerator` validates the payload against the chosen symbology.
      If the data contains prohibited characters, an `ArgumentException` is thrown.
      Wrap the generation code in a try‑catch block to provide a friendly error message:'
  - name: Scaling the barcode image
    text: 'You can change the image size without altering the encoded data by setting
      `Parameters.Image.Width` and `Parameters.Image.Height`:'
  type: HowTo
tags:
- barcode
- C#
- Aspose.BarCode
title: Как сгенерировать расширенный штабелированный штрих‑код Databar в C#
url: /ru/python-java/general/how-to-generate-a-databar-expanded-stacked-barcode-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Как сгенерировать штрих‑код Databar Expanded Stacked на C#

Если вам нужно создать **databar expanded stacked** штрих‑код на C#, это руководство покажет, как это сделать. Символика databar expanded stacked идеальна для кодирования большого объёма данных в компактной форме, и вы можете создать изображение всего в несколько строк кода. Вы также узнаете, как **генерировать файлы изображений штрих‑кода** в разных форматах и настраивать количество строк или колонок под вашу среду сканирования.

В этом учебнике рассматривается всё, что необходимо для начала создания штрих‑кодов databar: установка требуемой библиотеки, подготовка выходной папки, создание штрих‑кода с пользовательскими строками или колонками и сохранение результата в файл PNG. К концу вы сможете **создавать изображения штрих‑кода databar** программно и адаптировать код для других форматов изображений или сценариев выполнения.

## Требования

Прежде чем начать, убедитесь, что у вас есть:

* .NET 6.0 SDK или новее (код также работает с .NET Core 3.1 и .NET Framework 4.7+)
* Среда разработки, например Visual Studio 2022, Visual Studio Code или Rider
* Доступ в Интернет для установки пакета **Barcode Generator C#** NuGet (Aspose.BarCode for .NET)

> **Pro tip:** Если вы используете конвейер CI/CD, добавьте ссылку на пакет NuGet в файл проекта, чтобы сборки были воспроизводимыми.

## Установите библиотеку Barcode Generator C#

В примере используется библиотека Aspose.BarCode, которая предоставляет класс `BarcodeGenerator` и перечисление `EncodeTypes.DatabarExpandedStacked`.

```bash
dotnet add package Aspose.BarCode
```

Эта команда добавит последнюю стабильную версию в ваш проект. После установки вы можете импортировать пространство имён в файлах C#:

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;
```

## Подготовьте выходную папку

Надёжный путь к файлу предотвращает ошибки во время выполнения, когда библиотека пытается записать изображение. Следующий код создаёт каталог, если он не существует:

```csharp
using System;
using System.IO;

// Define the folder where barcode images will be saved
string outputFolder = Path.Combine(Environment.CurrentDirectory, "Barcodes");

// Ensure the folder exists
Directory.CreateDirectory(outputFolder);
```

> **Почему это важно:** Попытка сохранить в несуществующий каталог вызывает `IOException`. Предварительное создание папки делает код надёжным как для локальной разработки, так и для продакшн‑окружения.

## Генерация изображения штрих‑кода databar expanded stacked

### Базовая генерация штрих‑кода

Самый простой способ создать изображение **databar expanded stacked** — создать экземпляр `BarcodeGenerator` с нужным значением `EncodeTypes` и простым текстовым payload.

```csharp
// Create a barcode that encodes a long numeric string
var basicGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked,
    "01234567890123456789");

// Save the barcode as PNG
basicGenerator.Save(Path.Combine(outputFolder, "DatabarBasic.png"),
    BarCodeImageFormat.Png);
```

Запуск этого фрагмента создаёт файл `DatabarBasic.png` в папке *Barcodes*. На изображении находится стандартный символ databar expanded stacked с макетом по умолчанию (4 колонки × 4 строки).

### Настройка колонок — создать штрих‑код databar с 4 колонками

Количество колонок можно задать через свойство `Parameters.Barcode.DataBar.Columns`. В следующем примере создаётся штрих‑код с **4 колонками**, при этом количество строк остаётся по умолчанию.

```csharp
// Step 1: Define a generator with custom column count
var columnGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked,
    "Databar Expanded Stacked long");

// Set the column count to 4 (default rows = 4)
columnGenerator.Parameters.Barcode.DataBar.Columns = 4;

// Save the image
columnGenerator.Save(Path.Combine(outputFolder, "DatabarCols4.png"),
    BarCodeImageFormat.Png);
```

Полученный файл **DatabarCols4.png** выглядит так:

![Databar expanded stacked barcode с 4 колонками](databar_cols4.png "Databar expanded stacked barcode с 4 колонками – сгенерировано на C#")

*Текст alt изображения (og_image_alt):* **Пример изображения штрих‑кода databar expanded stacked, сгенерированного на C#** – это удовлетворяет требованиям SEO для alt‑текста изображения.

### Настройка строк — создать штрих‑код databar с 3 строками

Аналогично, количество строк можно изменить через `Parameters.Barcode.DataBar.Rows`. Код ниже генерирует штрих‑код с **3 строками** и количеством колонок по умолчанию (4).

```csharp
// Step 2: Define a generator with custom row count
var rowGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked,
    "Databar Expanded Stacked long");

// Set the row count to 3 (default columns = 4)
rowGenerator.Parameters.Barcode.DataBar.Rows = 3;

// Save the image
rowGenerator.Save(Path.Combine(outputFolder, "DatabarRows3.png"),
    BarCodeImageFormat.Png);
```

Файл **DatabarRows3.png** содержит символ databar expanded stacked, который немного короче по вертикали, что может быть полезно для этикеток с ограниченным пространством.

### Экспорт в другие форматы

Если нужен другой тип изображения (например, JPEG, BMP или SVG), замените `BarCodeImageFormat.Png` на соответствующее значение перечисления:

```csharp
columnGenerator.Save(Path.Combine(outputFolder, "DatabarCols4.jpg"),
    BarCodeImageFormat.Jpeg);
```

Библиотека также поддерживает векторные форматы, такие как SVG, которые идеальны для печати высокого разрешения.

## Расширенные сценарии

### Сохранение в поток памяти

Иногда требуется встроить штрих‑код непосредственно в веб‑ответ или PDF без обращения к файловой системе. Используйте `MemoryStream`:

```csharp
using System.IO;

// Generate barcode into a memory stream
using var ms = new MemoryStream();
columnGenerator.Save(ms, BarCodeImageFormat.Png);

// Reset stream position before reading
ms.Position = 0;

// Example: return the stream as a file download in ASP.NET Core
// return File(ms.ToArray(), "image/png", "databar.png");
```

### Обработка некорректного ввода

`BarcodeGenerator` проверяет payload относительно выбранной символики. Если данные содержат запрещённые символы, генерируется `ArgumentException`. Оберните код генерации в блок try‑catch, чтобы предоставить понятное сообщение об ошибке:

```csharp
try
{
    var gen = new BarcodeGenerator(EncodeTypes.DatabarExpandedStacked, "INVALID*DATA");
    gen.Save(Path.Combine(outputFolder, "Invalid.png"), BarCodeImageFormat.Png);
}
catch (ArgumentException ex)
{
    Console.WriteLine($"Failed to generate barcode: {ex.Message}");
}
```

### Масштабирование изображения штрих‑кода

Размер изображения можно изменить, не меняя закодированные данные, задав `Parameters.Image.Width` и `Parameters.Image.Height`:

```csharp
columnGenerator.Parameters.Image.Width = 300;   // pixels
columnGenerator.Parameters.Image.Height = 150; // pixels
columnGenerator.Save(Path.Combine(outputFolder, "DatabarLarge.png"),
    BarCodeImageFormat.Png);
```

Масштабирование полезно, когда штрих‑код должен соответствовать определённому DPI для сканеров.

## Полный рабочий пример

Ниже представлено полностью готовое консольное приложение, демонстрирующее все описанные шаги:

```csharp
using System;
using System.IO;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace DatabarExpandedStackedDemo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Prepare output folder
            string outputFolder = Path.Combine(
                Environment.CurrentDirectory, "Barcodes");
            Directory.CreateDirectory(outputFolder);

            // 2️⃣ Generate basic barcode
            var basic = new BarcodeGenerator(
                EncodeTypes.DatabarExpandedStacked,
                "01234567890123456789");
            basic.Save(Path.Combine(outputFolder, "DatabarBasic.png"),
                BarCodeImageFormat.Png);

            // 3️⃣ Generate barcode with 4 columns
            var colGen = new BarcodeGenerator(
                EncodeTypes.DatabarExpandedStacked,
                "Databar Expanded Stacked long");
            colGen.Parameters.Barcode.DataBar.Columns = 4;
            colGen.Save(Path.Combine(outputFolder, "DatabarCols4.png"),
                BarCodeImageFormat.Png);

            // 4️⃣ Generate barcode with 3 rows
            var rowGen = new BarcodeGenerator(
                EncodeTypes.DatabarExpandedStacked,
                "Databar Expanded Stacked long");
            rowGen.Parameters.Barcode.DataBar.Rows = 3;
            rowGen.Save(Path.Combine(outputFolder, "DatabarRows3.png"),
                BarCodeImageFormat.Png);

            // 5️⃣ Export to JPEG as an extra format
            colGen.Save(Path.Combine(outputFolder, "DatabarCols4.jpg"),
                BarCodeImageFormat.Jpeg);

            Console.WriteLine("All barcode images have been generated in:");
            Console.WriteLine(outputFolder);
        }
    }
}
```

**Ожидаемый вывод**


## Что изучать дальше?


Следующие учебники охватывают тесно связанные темы, расширяющие техники, продемонстрированные в этом руководстве. Каждый ресурс включает полностью рабочие примеры кода с пошаговыми объяснениями, чтобы помочь вам освоить дополнительные возможности API и исследовать альтернативные подходы реализации в собственных проектах.

- [How to set columns for a Databar Expanded Stacked barcode – complete C# guide](/barcode/english/python-java/general/how-to-set-columns-for-a-databar-expanded-stacked-barcode-co/)
- [How to build a barcode generator example in C# with DataBar Expanded Stacked](/barcode/english/python-java/general/how-to-build-a-barcode-generator-example-in-c-with-databar-e/)
- [databar expanded stacked barcode guide – how to generate and size it in C#](/barcode/english/python-java/general/databar-expanded-stacked-barcode-guide-how-to-generate-and-s/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}