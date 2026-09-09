---
category: general
date: 2026-07-24
description: Учебник по генератору штрихкодов на C#, показывающий, как создать изображение
  штрихкода, задать столбцы, задать строки и создать Databar‑штрихкод всего за несколько
  строк кода.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- barcode generator c#
- generate barcode image
- how to set columns
- how to set rows
- create databar barcode
language: ru
lastmod: 2026-07-24
og_description: Учебник по генератору штрихкодов на C# пошагово покажет, как создать
  изображение штрихкода, настроить столбцы и строки, а также создать штрихкод Databar
  с понятными примерами кода.
og_image_alt: Screenshot of a DataBar Expanded Stacked barcode generated with C#
og_title: Генератор штрихкодов C# – Быстро создавайте DataBar‑сложенные штрихкоды
schemas:
- author: Aspose
  dateModified: '2026-07-24'
  description: Barcode Generator C# tutorial that shows how to generate barcode image,
    set columns, set rows, and create Databar barcode in just a few lines of code.
  headline: Barcode Generator C# – Create DataBar Expanded Stacked Images
  type: TechArticle
tags:
- barcode
- C#
- Aspose.BarCode
title: Генератор штрихкодов C# – Создание изображений DataBar Expanded Stacked
url: /ru/python-java/general/barcode-generator-c-create-databar-expanded-stacked-images/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Barcode Generator C# – Полное руководство по DataBar Expanded Stacked

Когда‑нибудь задумывались, как использовать **barcode generator c#**, чтобы за считанные секунды получать чёткие, сканируемые изображения? Возможно, вы сидели перед пустым проектом, не зная, где разместить столбцы или строки, и как *generate barcode image* без головной боли. Вы попали в нужное место. В этом руководстве мы создадим небольшое консольное приложение, сгенерируем штрих‑код DataBar Expanded Stacked, настроим его макет и сохраним результат в PNG‑файлы — всё с помощью библиотеки **barcode generator c#**.

Мы охватим всё, что вам нужно знать: установку пакета, настройку столбцов и строк (да, ответим на *how to set columns* и *how to set rows*), а также как **create databar barcode**‑объекты, которые можно вставлять в счета, билеты или любые другие машинно‑читаемые метки. Никакой внешней документации не требуется; просто скопируйте‑вставьте, запустите, и вы увидите два PNG‑файла в своей папке.

## Что вам понадобится

- .NET 6.0 SDK или новее (код работает на .NET Core, .NET Framework и .NET 5+)
- Новый консольный проект (`dotnet new console`) – при желании можно использовать Visual Studio.
- NuGet‑пакет Aspose.BarCode for .NET (библиотека, лежащая в основе **barcode generator c#**). Установите его командой:

```bash
dotnet add package Aspose.BarCode
```

Вот и всё. После восстановления пакета вы готовы к работе.

## Barcode Generator C# – Настройка проекта

Сначала подключим необходимые пространства имён и создадим вспомогательный метод, который сделает основной код более чистым.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        // Folder where PNG files will be saved
        string outputFolder = Environment.CurrentDirectory;

        // Build the first barcode with custom columns
        GenerateDatabarWithColumns(outputFolder, columns: 4);

        // Build the second barcode with custom rows
        GenerateDatabarWithRows(outputFolder, rows: 3);
    }

    // -----------------------------------------------------------------
    // Helper: creates a DataBar Expanded Stacked barcode and sets columns
    // -----------------------------------------------------------------
    static void GenerateDatabarWithColumns(string folder, int columns)
    {
        // Step 1: Create a DataBar Expanded Stacked barcode generator with the desired text
        var barcodeGenerator = new BarcodeGenerator(
            EncodeTypes.DatabarExpandedStacked, "Databar Expanded Stacked long");

        // Step 2: Configure the barcode to use the supplied number of columns
        // This answers the “how to set columns” question.
        barcodeGenerator.Parameters.Barcode.DataBar.Columns = columns;

        // Step 3: Save the barcode image as PNG – this is the “generate barcode image” part.
        string filePath = System.IO.Path.Combine(folder, $"DatabarCols{columns}.png");
        barcodeGenerator.Save(filePath, BarCodeImageFormat.Png);

        Console.WriteLine($"✅ Created barcode with {columns} columns: {filePath}");
    }

    // -----------------------------------------------------------------
    // Helper: creates a DataBar Expanded Stacked barcode and sets rows
    // -----------------------------------------------------------------
    static void GenerateDatabarWithRows(string folder, int rows)
    {
        // Step 4: Create another generator for the same barcode type and text
        var barcodeGenerator = new BarcodeGenerator(
            EncodeTypes.DatabarExpandedStacked, "Databar Expanded Stacked long");

        // Step 5: Configure the barcode to use the supplied number of rows
        // This answers the “how to set rows” query.
        barcodeGenerator.Parameters.Barcode.DataBar.Rows = rows;

        // Step 6: Save the second barcode image as PNG
        string filePath = System.IO.Path.Combine(folder, $"DatabarRows{rows}.png");
        barcodeGenerator.Save(filePath, BarCodeImageFormat.Png);

        Console.WriteLine($"✅ Created barcode with {rows} rows: {filePath}");
    }
}
```

### Почему такая структура работает

- **Разделение ответственности** – каждый вспомогательный метод отвечает за одну настройку (столбцы vs строки). Это упрощает чтение и повторное использование кода.
- **Явные параметры** – мы передаём `columns` или `rows` как аргументы, поэтому один и тот же метод можно вызвать с любым значением без изменения тела.
- **Мгновенная обратная связь** – `Console.WriteLine` сообщает, куда именно был сохранён файл, что удобно при запуске программы из терминала.

## Как задать столбцы для DataBar Expanded Stacked

Свойство `DataBar.Columns` определяет, сколько вертикальных срезов будет у штрих‑кода. По умолчанию — `4`, но вам могут понадобиться `2` или `6` в зависимости от объёма кодируемых данных или требований сканера. Ниже короткий фрагмент, изолирующий логику установки столбцов:

```csharp
var generator = new BarcodeGenerator(EncodeTypes.DatabarExpandedStacked, "Sample Text");
generator.Parameters.Barcode.DataBar.Columns = 5;   // ← change this number as needed
generator.Save("databar_columns5.png", BarCodeImageFormat.Png);
```

**Pro tip:** При увеличении количества столбцов общая ширина штрих‑кода растёт пропорционально. Если вы планируете вставлять изображение в PDF или веб‑страницу, убедитесь, что контейнер способен вместить дополнительную ширину, иначе сканер может считать его неверно.

## Как задать строки для DataBar Expanded Stacked

Строки работают аналогично, но влияют на высоту штрих‑кода. По умолчанию количество строк — `3`. Если у вашей этикетки ограничено вертикальное пространство, можно уменьшить значение до `2`. И наоборот, больше строк может улучшить читаемость на принтерах с низким разрешением.

```csharp
var generator = new BarcodeGenerator(EncodeTypes.DatabarExpandedStacked, "Sample Text");
generator.Parameters.Barcode.DataBar.Rows = 2;   // ← adjust rows here
generator.Save("databar_rows2.png", BarCodeImageFormat.Png);
```

**Watch out:** Установка количества строк ниже минимально необходимого для кодируемых данных вызовет исключение во время выполнения. Библиотека бросает `ArgumentException` с понятным сообщением, так что вы сразу узнаете, что конфигурация неверна.

## Генерация изображения штрих‑кода – сохранение в PNG

Оба вспомогательных метода заканчиваются вызовом `Save`. Перечисление `BarCodeImageFormat.Png` указывает Aspose.BarCode вывести без потерь PNG‑файл, что идеально для большинства сценариев сканирования, поскольку сохраняет резкие края. Если нужен другой формат (JPEG для веба, BMP для устаревших систем), просто замените значение перечисления — других изменений кода не требуется.

```csharp
generator.Save("mybarcode.jpeg", BarCodeImageFormat.Jpeg);
```

Сгенерированные PNG‑файлы выглядят так (представьте изображение; ниже описан альтернативный текст):

> **Alt text for the generated images:** *DataBar Expanded Stacked barcode with 4 columns (left) and 3 rows (right), rendered in high‑contrast black on a transparent background.*

## Создание DataBar Barcode – полностью рабочий пример

Объединив всё вместе, получаем компактную версию, которую можно сразу вставить в `Program.cs`. Она демонстрирует настройку как столбцов, так и строк, а также быструю проверку наличия файлов после сохранения.

```csharp
using System;
using System.IO;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Demo
{
    static void Main()
    {
        string outDir = Directory.GetCurrentDirectory();

        // ---------- Create barcode with custom columns ----------
        var colGen = new BarcodeGenerator(EncodeTypes.DatabarExpandedStacked,
                                          "Databar Expanded Stacked long");
        colGen.Parameters.Barcode.DataBar.Columns = 4;   // how to set columns
        string colPath = Path.Combine(outDir, "DatabarCols4.png");
        colGen.Save(colPath, BarCodeImageFormat.Png);
        Console.WriteLine($"Saved column barcode → {colPath}");

        // ---------- Create barcode with custom rows ----------
        var rowGen = new BarcodeGenerator(EncodeTypes.DatabarExpandedStacked,
                                          "Databar Expanded Stacked long");
        rowGen.Parameters.Barcode.DataBar.Rows = 3;      // how to set rows
        string rowPath = Path.Combine(outDir, "DatabarRows3.png");
        rowGen.Save(rowPath, BarCodeImageFormat.Png);
        Console.WriteLine($"Saved row barcode → {rowPath}");

        // ---------- Verify files exist ----------
        Console.WriteLine(File.Exists(colPath)
            ? "✅ Column image generated successfully."
            : "❌ Column image missing.");
        Console.WriteLine(File.Exists(rowPath)
            ? "✅ Row image generated successfully."
            : "❌ Row image missing.");
    }
}
```

### Ожидаемый вывод

При запуске программы (`dotnet run`) вы увидите строки в консоли, похожие на:

```
Saved column barcode → C:\MyProject\DatabarCols4.png
Saved row barcode → C:\MyProject\DatabarRows3.png
✅ Column image generated successfully.
✅ Row image generated successfully.
```

Откройте два PNG‑файла в любом просмотрщике изображений; вы заметите, что левый файл имеет четыре вертикальных модуля (столбца), а правый — три модуля по высоте (строки). Оба файла полностью сканируемы любым стандартным считывателем DataBar.

## Распространённые ошибки и как их избежать

| Symptom | Likely Cause | Fix |
|---------|--------------|-----|
| `ArgumentException: Columns value is out of range` | Columns set to 0 or > 8 (the library caps at 8). | Stick to values between **1** and **8**. |
| Barcode appears blurry in PDF | PNG saved at default DPI (96) and then scaled. | Use `generator.Parameters.ImageResolution = 300;` before saving. |
| Scanner fails on rows‑only configuration | Rows changed but columns left at default that don’t match data length. | Adjust both rows **and** columns together, or let the library auto‑size by omitting manual settings. |

## Последующие шаги

Теперь, когда вы знаете, как **generate barcode image**, **set columns**, **set rows** и **create databar barcode** с помощью **barcode generator c#**, вы можете:

- Встраивать PNG‑файлы в PDF с помощью `Aspose.PDF` или `iTextSharp`.
- Переключиться на `EncodeTypes.DatabarLimited`, если нужен более компактный вариант.
- Экспериментировать с цветами (`generator.Parameters.Barcode.ForeColor = Color.Blue`).
- Добавлять QR‑коды или другие символьные системы в тот же проект — Aspose.BarCode поддерживает более 150 типов.

Если возникнут проблемы, оставляйте комментарий ниже или смотрите официальную документацию Aspose.BarCode (API‑reference охватывает всё и содержит десятки живых примеров кода). Приятного кодинга, и пусть ваши сканеры никогда не пропустят метку!

## Что изучать дальше?

Следующие руководства охватывают смежные темы, построенные на техниках, продемонстрированных в этом гиде. Каждый ресурс включает полностью рабочие примеры кода с пошаговыми объяснениями, чтобы помочь вам освоить дополнительные возможности API и исследовать альтернативные подходы в своих проектах.

- [Create DotCode barcode image – rows & columns (Aspose.BarCode)](/barcode/english/net/dotcode-barcode-configuration/dotcode-rows-columns-configuration/)
- [Create barcode image c# – Configure Codablock F Rows & Columns](/barcode/english/net/codablock-f-encoding/codablock-f-row-column-configuration/)
- [Generate barcode image – GS1 Coupon UPC-A Databar](/barcode/english/net/gs1-barcode-encoding/gs1-coupon-upc-a-databar-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}