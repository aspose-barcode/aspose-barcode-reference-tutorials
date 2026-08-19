---
category: general
date: 2026-08-19
description: Учебник по генератору штрих‑кодов на C# показывает, как создавать штрих‑коды
  DataBar Expanded Stacked, настраивать размер штрих‑кода и конфигурировать строки
  и столбцы.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- c# barcode generator
- how to generate barcode
- create databar barcode
- customize barcode size
- configure databar parameters
language: ru
lastmod: 2026-08-19
og_description: Учебник по генератору штрихкодов на C# показывает, как генерировать
  штрихкоды DataBar, настраивать их размер и задавать количество строк и столбцов
  для точного вывода.
og_image_alt: Screenshot of a DataBar Expanded Stacked barcode generated with C#
og_title: Генератор штрих‑кодов на C# – пошаговое руководство по созданию пользовательских
  DataBar штрих‑кодов
schemas:
- author: Aspose
  dateModified: '2026-08-19'
  description: C# barcode generator tutorial shows how to generate DataBar Expanded
    Stacked barcodes, customize barcode size, and configure rows and columns.
  headline: 'C# barcode generator: create custom DataBar barcodes'
  type: TechArticle
- description: C# barcode generator tutorial shows how to generate DataBar Expanded
    Stacked barcodes, customize barcode size, and configure rows and columns.
  name: 'C# barcode generator: create custom DataBar barcodes'
  steps:
  - name: Initialise the barcode generator with sample text
    text: '```csharp using Aspose.BarCode.Generation;'
  - name: Set the number of columns (default rows are used)
    text: '```csharp // Configure the DataBar to use four columns. barcodeGenerator.Parameters.Barcode.DataBar.Columns
      = 4; ```'
  - name: Save the barcode image that uses four columns
    text: '```csharp // Save the barcode as a PNG file. barcodeGenerator.Save("YOUR_DIRECTORY/DatabarCols4.png",
      BarCodeImageFormat.Png); ```'
  - name: Re‑initialise the generator for a new configuration
    text: '```csharp // Create a new generator instance for the same symbology and
      text. barcodeGenerator = new BarcodeGenerator( EncodeTypes.DatabarExpandedStacked,
      "Databar Expanded Stacked long"); ```'
  - name: Set the number of rows (default columns are used)
    text: '```csharp // Configure the DataBar to use three rows. barcodeGenerator.Parameters.Barcode.DataBar.Rows
      = 3; ```'
  - name: Save the barcode image that uses three rows
    text: '```csharp // Save the barcode with three rows. barcodeGenerator.Save("YOUR_DIRECTORY/DatabarRows3.png",
      BarCodeImageFormat.Png); ```'
  type: HowTo
tags:
- barcode
- csharp
- databar
title: 'Генератор штрихкодов C#: создание пользовательских штрихкодов DataBar'
url: /ru/python-java/general/c-barcode-generator-create-custom-databar-barcodes/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# C# генератор штрих‑кодов: создание пользовательских DataBar штрих‑кодов

Если вам нужен **c# barcode generator**, который может создавать символы DataBar Expanded Stacked, это руководство покажет, как точно генерировать изображения штрих‑кодов с пользовательскими строками и столбцами. Вы узнаете, как настроить параметры databar, изменить размер штрих‑кода и сохранить результат в виде PNG‑файлов.

Программная генерация штрих‑кодов устраняет ручные этапы дизайна и гарантирует согласованный вывод на разных платформах. В этом учебнике вы:

* Установите и подключите библиотеку Aspose.BarCode for .NET (или любой совместимый пакет).
* Создадите генератор штрих‑кода для символьного набора DataBar Expanded Stacked.
* **Как генерировать изображения штрих‑кода** с конкретными настройками столбцов и строк.
* **Настроите размер штрих‑кода** путем управления строками и столбцами DataBar.
* **Настроите параметры databar** такие как текст, формат и качество изображения.

## Prerequisites

* .NET 6.0 SDK или более поздняя версия.
* Среда разработки C# (Visual Studio, VS Code, Rider и т.д.).
* NuGet‑пакет `Aspose.BarCode` (или эквивалентная библиотека, предоставляющая `BarcodeGenerator`, `EncodeTypes` и `BarCodeImageFormat`).

Добавьте пакет с помощью .NET CLI:

```bash
dotnet add package Aspose.BarCode
```

## Using the C# barcode generator to create DataBar barcodes

Следующие разделы проведут вас через каждый шаг. Основное внимание уделяется **c# barcode generator** API, но тот же шаблон применим к другим библиотекам штрих‑кодов, которые предоставляют аналогичные свойства.

### Step 1: Initialise the barcode generator with sample text

```csharp
using Aspose.BarCode.Generation;

// Create a generator for DataBar Expanded Stacked with sample text.
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked,
    "Databar Expanded Stacked long");
```

*Почему этот шаг?*  
`BarcodeGenerator` — точка входа для всех задач создания штрих‑кодов. Передача перечисления `EncodeTypes.DatabarExpandedStacked` сообщает библиотеке, какой символьный набор использовать, а аргумент текста становится читаемым значением, закодированным в символе.

### Step 2: Set the number of columns (default rows are used)

```csharp
// Configure the DataBar to use four columns.
barcodeGenerator.Parameters.Barcode.DataBar.Columns = 4;
```

*Почему этот шаг?*  
Символы DataBar Expanded Stacked состоят из наложенных линейных элементов. Изменение свойства `Columns` меняет горизонтальную плотность, позволяя разместить более длинные строки данных без увеличения общей высоты. Это напрямую **настраивает размер штрих‑кода**.

### Step 3: Save the barcode image that uses four columns

```csharp
// Save the barcode as a PNG file.
barcodeGenerator.Save("YOUR_DIRECTORY/DatabarCols4.png", BarCodeImageFormat.Png);
```

*Что вы видите:*  
Сохранённое изображение `DatabarCols4.png` отображает DataBar штрих‑код, шире стандартного, потому что содержит четыре столбца. Вы можете открыть файл в любом просмотрщике изображений, чтобы проверить результат.

### Step 4: Re‑initialise the generator for a new configuration

```csharp
// Create a new generator instance for the same symbology and text.
barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked,
    "Databar Expanded Stacked long");
```

*Почему переинициализировать?*  
Изменение свойства `Rows` при сохранённом предыдущем значении `Columns` может привести к неожиданной комбинации. Создание нового экземпляра гарантирует, что только желаемый параметр (`Rows`) повлияет на следующее изображение.

### Step 5: Set the number of rows (default columns are used)

```csharp
// Configure the DataBar to use three rows.
barcodeGenerator.Parameters.Barcode.DataBar.Rows = 3;
```

*Почему этот шаг?*  
Свойство `Rows` управляет вертикальным наложением. Увеличение количества строк делает штрих‑код выше, что полезно, когда горизонтальное пространство ограничено, а вертикальное — обильное. Это ещё один способ **настроить размер штрих‑кода**.

### Step 6: Save the barcode image that uses three rows

```csharp
// Save the barcode with three rows.
barcodeGenerator.Save("YOUR_DIRECTORY/DatabarRows3.png", BarCodeImageFormat.Png);
```

*Результат:*  
`DatabarRows3.png` показывает более высокий штрих‑код с тремя наложенными строками, демонстрируя, как **configure databar parameters** влияет на визуальное представление.

## Full runnable example

Ниже приведена полная программа, которую можно скопировать, вставить и запустить. В ней включены все импорты, обработка ошибок и комментарии для ясности.

```csharp
using System;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Define output folder (adjust as needed).
        string outputFolder = @"C:\Barcodes";

        // -----------------------------------------------------------------
        // Create barcode with custom column count.
        // -----------------------------------------------------------------
        BarcodeGenerator generator = new BarcodeGenerator(
            EncodeTypes.DatabarExpandedStacked,
            "Databar Expanded Stacked long");

        // Set 4 columns – this widens the symbol.
        generator.Parameters.Barcode.DataBar.Columns = 4;

        // Save the first image.
        string colsPath = System.IO.Path.Combine(outputFolder, "DatabarCols4.png");
        generator.Save(colsPath, BarCodeImageFormat.Png);
        Console.WriteLine($"Saved barcode with 4 columns to: {colsPath}");

        // -----------------------------------------------------------------
        // Create barcode with custom row count.
        // -----------------------------------------------------------------
        generator = new BarcodeGenerator(
            EncodeTypes.DatabarExpandedStacked,
            "Databar Expanded Stacked long");

        // Set 3 rows – this makes the symbol taller.
        generator.Parameters.Barcode.DataBar.Rows = 3;

        // Save the second image.
        string rowsPath = System.IO.Path.Combine(outputFolder, "DatabarRows3.png");
        generator.Save(rowsPath, BarCodeImageFormat.Png);
        Console.WriteLine($"Saved barcode with 3 rows to: {rowsPath}");
    }
}
```

**Ожидаемый вывод**

Запуск программы создаёт два PNG‑файла:

* `DatabarCols4.png` — широкий DataBar штрих‑код с четырьмя столбцами.
* `DatabarRows3.png` — высокий DataBar штрих‑код с тремя строками.

Откройте изображения, чтобы убедиться, что размеры штрих‑кода соответствуют заданным параметрам.

## Common questions and edge‑case handling

| Question | Answer |
|----------|--------|
| *What if I need both custom rows **and** columns?* | Set `Rows` **and** `Columns` on the same `BarcodeGenerator` instance before calling `Save`. The library combines both values to produce a grid of the requested size. |
| *Can I change the image format?* | Yes. Replace `BarCodeImageFormat.Png` with `Jpeg`, `Bmp`, or `Gif` to suit your workflow. |
| *What happens when the text is longer than the symbol can hold?* | The generator throws an `ArgumentException`. Shorten the text or increase `Columns`/`Rows` to provide more capacity. |
| *Is there a way to set DPI or image resolution?* | Use `generator.Parameters.ImageResolution` to specify the desired DPI before saving. This further **customizes barcode size** for high‑resolution printing. |
| *Does the library support other DataBar variants?* | Yes. Replace `EncodeTypes.DatabarExpandedStacked` with `DatabarExpanded`, `DatabarLimited`, etc., while keeping the same parameter structure. |

## Tips for reliable barcode generation

* **Pro tip:** Always verify the generated image with a scanner or a mobile app before deploying it to production.  
* **Watch out for:** Null or empty output directories—`Save` will throw an exception if the path does not exist. Create the folder programmatically if needed.  
* **Performance note:** Re‑using a single `BarcodeGenerator` instance and only changing `Rows` or `Columns` can reduce object‑creation overhead when generating many barcodes in a loop.

## Conclusion

Теперь вы знаете, как использовать **c# barcode generator** для **создания databar штрих‑кодов**, **настройки размера штрих‑кода** и **конфигурации параметров databar** таких как строки и столбцы. Регулируя эти настройки, вы сможете вписать штрих‑коды в любой макет, сохраняя их надёжность при сканировании.

Далее изучайте связанные темы, такие как **как генерировать PDF‑файлы со штрих‑кодами**, встраивание штрих‑кодов в отчёты или переход к другим символьным наборам (QR, Code‑128 и т.д.). Экспериментируйте с различными `Rows`, `Columns` и разрешениями изображений, чтобы найти оптимальную конфигурацию для вашего конкретного случая.

---


## What Should You Learn Next?


The following tutorials cover closely related topics that build on the techniques demonstrated in this guide. Each resource includes complete working code examples with step-by-step explanations to help you master additional API features and explore alternative implementation approaches in your own projects.

- [How to Generate and Adjust Barcode Height for One-Dimensional Databar using Aspose.BarCode for .NET](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-barcode-height-adjustment/)
- [Generate One-Dimensional Databar 2D Barcodes Using Aspose.BarCode .NET API](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-2d-component-configuration/)
- [Generate Aspose.BarCode Databar barcode using .NET API – Row & Column Configuration](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-row-column-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}