---
category: general
date: 2026-09-26
description: Руководство по генератору штрих‑кодов на C# показывает, как задавать
  строки и столбцы при создании штрих‑кодов Databar Expanded Stacked в C#.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- barcode generator c#
- how to set rows
- how to set columns
- Databar Expanded Stacked barcode
- C# barcode library
language: ru
lastmod: 2026-09-26
og_description: Учебник по генератору штрихкодов на C# объясняет, как задавать строки
  и столбцы для штрихкодов Databar Expanded Stacked, с полным кодом и советами.
og_image_alt: Barcode generator C# example showing rows and columns settings
og_title: Генератор штрихкодов C# – задаём строки и столбцы пошагово
schemas:
- author: Aspose
  dateModified: '2026-09-26'
  description: barcode generator C# guide shows how to set rows and how to set columns
    when creating Databar Expanded Stacked barcodes in C#.
  headline: How to use barcode generator C# for rows and columns
  type: TechArticle
- description: barcode generator C# guide shows how to set rows and how to set columns
    when creating Databar Expanded Stacked barcodes in C#.
  name: How to use barcode generator C# for rows and columns
  steps:
  - name: Create a generator for a Databar Expanded Stacked barcode
    text: '```csharp // Create a generator for a Databar Expanded Stacked barcode
      with sample text BarcodeGenerator barcodeGenerator = new BarcodeGenerator( EncodeTypes.DatabarExpandedStacked,
      "Databar Expanded Stacked long"); ```'
  - name: How to set columns – configure the barcode to use 4 columns
    text: '```csharp // How to set columns: set the Columns property to 4 barcodeGenerator.Parameters.Barcode.DataBar.Columns
      = 4; ```'
  - name: Save the barcode image with the column setting
    text: '```csharp // Save the PNG image that reflects the column configuration
      barcodeGenerator.Save("YOUR_DIRECTORY/DatabarCols4.png", BarCodeImageFormat.Png);
      ```'
  - name: Re‑initialize the generator for a different layout
    text: When you need a separate barcode with a different visual arrangement, create
      a new instance rather than re‑using the previous one. This guarantees that previous
      settings (like columns) do not bleed into the new configuration.
  - name: How to set rows – configure the barcode to use 3 rows
    text: '```csharp // How to set rows: assign the Rows property to 3 barcodeGenerator.Parameters.Barcode.DataBar.Rows
      = 3; ```'
  - name: Save the barcode image that includes the row setting
    text: '```csharp // Save the PNG image that reflects the row configuration barcodeGenerator.Save("YOUR_DIRECTORY/DatabarRows3.png",
      BarCodeImageFormat.Png); ```'
  - name: Expected output
    text: 'Running the program produces two PNG files:'
  - name: Pro tip
    text: 'If you need to generate many barcodes with varying rows and columns, wrap
      the configuration logic in a helper method:'
  type: HowTo
tags:
- barcode
- C#
- code example
title: Как использовать генератор штрихкодов C# для строк и столбцов
url: /ru/python-java/general/how-to-use-barcode-generator-c-for-rows-and-columns/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Как использовать генератор штрих‑кодов C# для строк и столбцов

Если вам нужен **barcode generator C#**, позволяющий управлять визуальным расположением штрих‑кода Databar Expanded Stacked, этот учебник предоставит полностью готовое решение. Вы узнаете, **как задать строки** и **как задать столбцы**, чтобы полученное изображение точно соответствовало требуемому дизайну.

Программная генерация штрих‑кодов часто напоминает угадывание, какое свойство за что отвечает. К концу этого руководства вы разберётесь в API, избежите распространённых ошибок и получите готовый пример кода, который можно сразу скопировать в свой проект.

## Prerequisites

Прежде чем начать, убедитесь, что у вас есть:

* .NET 6.0 или более новая версия (код также работает с .NET Core и .NET Framework)
* Ссылка на библиотеку генерации штрих‑кодов, предоставляющую `BarcodeGenerator` и `EncodeTypes` (например, Aspose.BarCode, Dynamsoft или любой совместимый SDK)
* IDE, например Visual Studio или VS Code
* Права записи в папку, куда будут сохраняться PNG‑файлы

Дополнительные пакеты NuGet не требуются, кроме самого SDK для штрих‑кодов.

## Barcode generator C# – setting rows and columns

Ниже представлены пошаговые инструкции по настройке. Фрагменты кода полные и могут быть вставлены напрямую в метод `Main` консольного приложения.

### Step 1: Create a generator for a Databar Expanded Stacked barcode

```csharp
// Create a generator for a Databar Expanded Stacked barcode with sample text
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked, "Databar Expanded Stacked long");
```

*Why this matters:* Создание экземпляра `BarcodeGenerator` — первое действие в любом рабочем процессе **barcode generator C#**. Конструктор принимает тип кодирования и строку данных, которые будут закодированы.

### Step 2: How to set columns – configure the barcode to use 4 columns

```csharp
// How to set columns: set the Columns property to 4
barcodeGenerator.Parameters.Barcode.DataBar.Columns = 4;
```

Установка свойства `Columns` меняет количество вертикальных модулей, используемых DataBar. Значение `4` создаёт более плотный, компактный штрих‑код, что полезно при ограниченном горизонтальном пространстве.

### Step 3: Save the barcode image with the column setting

```csharp
// Save the PNG image that reflects the column configuration
barcodeGenerator.Save("YOUR_DIRECTORY/DatabarCols4.png", BarCodeImageFormat.Png);
```

Метод `Save` записывает сгенерированное изображение на **disk**. Проверьте полученный файл, чтобы убедиться, что макет из четырёх столбцов выглядит как ожидается.

![Barcode generator C# example showing rows and columns settings](./images/barcode-rows-columns.png)

*Изображение выше иллюстрирует результат настройки столбцов.*

### Step 4: Re‑initialize the generator for a different layout

Когда вам нужен отдельный штрих‑код с иной визуальной компоновкой, создайте новый экземпляр, а не переиспользуйте предыдущий. Это гарантирует, что прежние настройки (например, столбцы) не перейдут в новую конфигурацию.

```csharp
// Re‑initialize to start a fresh configuration
barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked, "Databar Expanded Stacked long");
```

### Step 5: How to set rows – configure the barcode to use 3 rows

```csharp
// How to set rows: assign the Rows property to 3
barcodeGenerator.Parameters.Barcode.DataBar.Rows = 3;
```

Свойство `Rows` управляет вертикальным расположением модулей DataBar. Макет из трёх строк является стандартным для многих сканеров, но при необходимости можно увеличить его для большей плотности данных.

### Step 6: Save the barcode image that includes the row setting

```csharp
// Save the PNG image that reflects the row configuration
barcodeGenerator.Save("YOUR_DIRECTORY/DatabarRows3.png", BarCodeImageFormat.Png);
```

Откройте `DatabarRows3.png`, чтобы увидеть расположение в три строки. Если штрих‑код не сканируется, дважды проверьте значения rows/columns относительно спецификаций вашего сканера.

## Full source code – ready to copy

Ниже приведена полная программа, объединяющая все шаги. Замените `YOUR_DIRECTORY` на абсолютный или относительный путь, существующий на вашем компьютере.

```csharp
using System;
using YourBarcodeSdkNamespace;   // Replace with the actual namespace of your SDK

class Program
{
    static void Main()
    {
        // ---------- Columns configuration ----------
        // 1. Create generator
        BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
            EncodeTypes.DatabarExpandedStacked, "Databar Expanded Stacked long");

        // 2. Set columns (how to set columns)
        barcodeGenerator.Parameters.Barcode.DataBar.Columns = 4;

        // 3. Save image with column setting
        barcodeGenerator.Save("YOUR_DIRECTORY/DatabarCols4.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved barcode with 4 columns to DatabarCols4.png");

        // ---------- Rows configuration ----------
        // 4. Re‑initialize generator for a fresh instance
        barcodeGenerator = new BarcodeGenerator(
            EncodeTypes.DatabarExpandedStacked, "Databar Expanded Stacked long");

        // 5. Set rows (how to set rows)
        barcodeGenerator.Parameters.Barcode.DataBar.Rows = 3;

        // 6. Save image with row setting
        barcodeGenerator.Save("YOUR_DIRECTORY/DatabarRows3.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved barcode with 3 rows to DatabarRows3.png");
    }
}
```

### Expected output

Запуск программы создаёт два PNG‑файла:

| File name            | Layout description                         |
|----------------------|--------------------------------------------|
| `DatabarCols4.png`   | Databar Expanded Stacked with **4 columns** |
| `DatabarRows3.png`   | Databar Expanded Stacked with **3 rows**    |

Оба изображения должны быть читаемы стандартными сканерами, поддерживающими символьную систему Databar Expanded Stacked.

## Common pitfalls and pro tips

| Pitfall                              | Why it happens                               | Fix / Tip |
|--------------------------------------|----------------------------------------------|-----------|
| Using the same `BarcodeGenerator` instance for both rows and columns | The SDK keeps the previous configuration, so setting rows after columns may produce an unexpected mix | Re‑initialize the generator (as shown in Step 4) before changing the other dimension |
| Forgetting to set `EncodeTypes` correctly | The SDK defaults to a different symbology, leading to an invalid barcode | Always pass `EncodeTypes.DatabarExpandedStacked` when you need this specific format |
| Saving to a non‑existent folder      | `Save` throws an exception if the path is invalid | Ensure `YOUR_DIRECTORY` exists or use `Directory.CreateDirectory` before calling `Save` |
| Using values outside the allowed range (e.g., 0 columns) | The SDK validates the range and throws `ArgumentOutOfRangeException` | Valid column values are 1‑4; valid row values are 1‑3 for this symbology |

### Pro tip

Если нужно генерировать множество штрих‑кодов с разными строками и столбцами, вынесите логику настройки в вспомогательный метод:

```csharp
static void GenerateDatabar(string text, int? rows, int? columns, string outputPath)
{
    var generator = new BarcodeGenerator(EncodeTypes.DatabarExpandedStacked, text);
    if (rows.HasValue)    generator.Parameters.Barcode.DataBar.Rows = rows.Value;
    if (columns.HasValue) generator.Parameters.Barcode.DataBar.Columns = columns.Value;
    generator.Save(outputPath, BarCodeImageFormat.Png);
}
```

Такой подход уменьшает дублирование кода и упрощает его поддержку.

## Conclusion

Теперь у вас есть чёткий, сквозной пример использования **barcode generator C#** для управления как количеством строк, так и количеством столбцов в штрих‑коде Databar Expanded Stacked. Следуя указанным шагам, вы сможете создавать точные изображения штрих‑кодов, соответствующие требованиям вашего сканирующего оборудования.

Дальше вы можете изучить:

* Настройку других свойств `DataBar`, таких как **AspectRatio** или **BarHeight**
* Генерацию других символьных систем (например, QR, Code128) с тем же классом `BarcodeGenerator`
* Встраивание сгенерированных PNG в PDF или прямую печать из C#

Экспериментируйте с различными комбинациями строк/столбцов и делитесь результатами в комментариях. Happy coding!

## What Should You Learn Next?

Следующие учебники охватывают смежные темы, расширяющие техники, продемонстрированные в этом руководстве. Каждый ресурс содержит полностью рабочие примеры кода с пошаговыми объяснениями, помогающими освоить дополнительные возможности API и исследовать альтернативные подходы в ваших проектах.

- [How to set columns for a Databar Expanded Stacked barcode – complete C# guide](/barcode/english/python-java/general/how-to-set-columns-for-a-databar-expanded-stacked-barcode-co/)
- [databar expanded stacked barcode guide – how to generate and size it in C#](/barcode/english/python-java/general/databar-expanded-stacked-barcode-guide-how-to-generate-and-s/)
- [Barcode Generator Example in C# – Set Columns, Rows & Export Image](/barcode/english/python-java/general/barcode-generator-example-in-c-set-columns-rows-export-image/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}