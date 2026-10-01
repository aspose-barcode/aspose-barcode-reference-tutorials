---
category: general
date: 2026-09-13
description: Быстро создайте штрих‑код Databar Stacked в C# с помощью Aspose.Barcode
  — узнайте, как задать столбцы, строки и сохранить изображения.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create databar stacked barcode
- Databar Expanded Stacked
- barcode columns
- barcode rows
- Aspose.Barcode for .NET
- C# barcode generator
language: ru
lastmod: 2026-09-13
og_description: Создайте штрих‑код Databar Stacked в C# с использованием Aspose.Barcode.
  Это руководство показывает, как настроить столбцы, строки и экспортировать изображения
  PNG.
og_image_alt: Screenshot of a generated Databar stacked barcode saved as PNG
og_title: Создайте Databar Stacked штрих‑код в C# – Полное пошаговое руководство
schemas:
- author: Aspose
  dateModified: '2026-09-13'
  description: Create databar stacked barcode in C# quickly using Aspose.Barcode –
    learn to set columns, rows, and save images.
  headline: How to create databar stacked barcode in C# with Aspose.Barcode
  type: TechArticle
- description: Create databar stacked barcode in C# quickly using Aspose.Barcode –
    learn to set columns, rows, and save images.
  name: How to create databar stacked barcode in C# with Aspose.Barcode
  steps:
  - name: 'Create a new Console App project:'
    text: 'Create a new Console App project:'
  - name: 'Add the Aspose.Barcode package:'
    text: 'Add the Aspose.Barcode package:'
  - name: 'Open **Program.cs** and add the required `using` statements:'
    text: 'Open **Program.cs** and add the required `using` statements:'
  type: HowTo
tags:
- barcode
- C#
- Aspose
- Databar
title: Как создать штрих‑код Databar Stacked в C# с помощью Aspose.Barcode
url: /ru/python-java/general/how-to-create-databar-stacked-barcode-in-c-with-aspose-barco/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Как создать Databar Stacked штрих‑код в C# с Aspose.Barcode

Если вам нужно **создать Databar Stacked штрих‑код** в приложении .NET, это руководство предоставляет готовое решение, которое можно сразу запустить. Вы увидите, как настроить количество столбцов, изменить количество строк и сохранить результат в файл PNG — всё с помощью библиотеки Aspose.Barcode for .NET.

Создание **Databar Expanded Stacked** штрих‑кода перестаёт быть загадкой, как только вы поймёте трёхшаговый процесс: создать генератор, задать нужные размеры и записать изображение на диск. В следующих разделах мы подробно разберём каждый шаг, объясним, почему настройки важны, и покажем конечный результат, который можно сразу проверить.

## Требования

Прежде чем начать, убедитесь, что у вас есть:

- **Visual Studio 2022** (или любой IDE для C#) с установленным .NET 6+.
- NuGet‑пакет **Aspose.Barcode for .NET** (`Install-Package Aspose.Barcode`).
- Права записи в папку, куда будут сохраняться PNG‑файлы.

Дополнительные зависимости не требуются.

## Шаг 1: Создание проекта и добавление Aspose.Barcode

1. Создайте новый проект Console App:

   ```bash
   dotnet new console -n DatabarStackedDemo
   cd DatabarStackedDemo
   ```

2. Добавьте пакет Aspose.Barcode:

   ```bash
   dotnet add package Aspose.Barcode
   ```

3. Откройте **Program.cs** и добавьте необходимые `using`‑директивы:

   ```csharp
   using Aspose.BarCode;
   using Aspose.BarCode.Generation;
   using System;
   ```

Эти шаги обеспечивают доступ к классам **C# barcode generator** в вашем коде.

## Шаг 2: Создание генератора для Databar Stacked штрих‑кода

Первый объект, который вам нужен, — это `BarcodeGenerator`, настроенный для символьности **Databar Expanded Stacked**. Этот объект является точкой входа для всех операций, связанных со штрих‑кодами.

```csharp
// Step 2: Initialize a generator for Databar Expanded Stacked
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked, // Symbology
    "Databar Expanded Stacked long");   // Human‑readable text (optional)
```

**Почему это важно:**  
`EncodeTypes.DatabarExpandedStacked` указывает Aspose.Barcode использовать стековую версию семейства DataBar, что идеально подходит для ограниченных по высоте областей, например, чеков. Второй аргумент задаёт данные, кодируемые в штрих‑коде; вы можете заменить его любой числовой или буквенно‑цифровой строкой, соответствующей стандарту DataBar.

## Шаг 3: Настройка столбцов штрих‑кода и сохранение изображения

Stacked DataBar может отображаться с различным числом **столбцов**. По умолчанию их три, но для более длинных строк данных может потребоваться четыре столбца. Установите свойство `Columns` перед сохранением.

```csharp
// Step 3: Set the barcode to use 4 columns (default rows) and save the image
barcodeGenerator.Parameters.Barcode.DataBar.Columns = 4;

// Choose an output folder that exists on your machine
string outputPathCols = @"YOUR_DIRECTORY\DatabarCols4.png";
barcodeGenerator.Save(outputPathCols, BarCodeImageFormat.Png);

Console.WriteLine($"Barcode with 4 columns saved to {outputPathCols}");
```

**Пояснение:**  
- `Parameters.Barcode.DataBar.Columns` напрямую влияет на горизонтальное сегментирование штрих‑кода. Большее количество столбцов делает изображение шире, но высота остаётся той же.
- `Save` записывает штрих‑код в файл PNG. Другие форматы (JPEG, BMP, SVG) также поддерживаются через передачу другого значения `BarCodeImageFormat`.

## Шаг 4: Создание другого генератора и настройка строк штрих‑кода

Иногда сканирующей среде требуется более высокий штрих‑код, чего можно достичь, увеличив количество **строк**. Ниже приведён фрагмент, создающий второй экземпляр генератора, задающий три строки и сохраняющий результат.

```csharp
// Step 4: Create a new generator for the same data but with 3 rows
BarcodeGenerator barcodeGeneratorRows = new BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked,
    "Databar Expanded Stacked long");

// Set the barcode to use 3 rows (default columns)
barcodeGeneratorRows.Parameters.Barcode.DataBar.Rows = 3;

// Save the image with rows configured
string outputPathRows = @"YOUR_DIRECTORY\DatabarRows3.png";
barcodeGeneratorRows.Save(outputPathRows, BarCodeImageFormat.Png);

Console.WriteLine($"Barcode with 3 rows saved to {outputPathRows}");
```

**Зачем отдельный экземпляр?**  
Изменение `Rows` в том же `BarcodeGenerator` после вызова `Save` тоже работает, но создание нового экземпляра изолирует каждую конфигурацию и делает код более читаемым — особенно когда вы позже расширяете руководство, добавляя другие варианты (например, разные строки данных или уровни коррекции ошибок).

## Шаг 5: Проверка сгенерированных штрих‑кодов

Откройте два только что созданных PNG‑файла. Вы должны увидеть:

- **DatabarCols4.png** — более широкий штрих‑код, состоящий из четырёх вертикальных столбцов.
- **DatabarRows3.png** — более высокий штрих‑код, состоящий из трёх горизонтальных строк.

Оба изображения кодируют один и тот же текст (`"Databar Expanded Stacked long"`), но их визуальная структура различается. Сканируйте их любым стандартным сканером DataBar или мобильным приложением, поддерживающим DataBar, чтобы убедиться, что они декодируются корректно.

## Распространённые ошибки и профессиональные советы

| Проблема | Почему происходит | Как избежать |
|----------|-------------------|--------------|
| **Неправильный путь к папке** | `Save` бросает `DirectoryNotFoundException`, если каталог не существует. | Перед вызовом `Save` используйте `Directory.CreateDirectory(Path.GetDirectoryName(outputPath))`. |
| **Слишком много столбцов/строк** | Спецификации DataBar ограничивают количество столбцов до 4 и строк до 3. | Оставайтесь в допустимом диапазоне; иначе Aspose.Barcode выдаст `ArgumentOutOfRangeException`. |
| **Не читаемый штрих‑код** | Низкое разрешение изображения делает штрих‑код размытым. | Увеличьте DPI через `barcodeGenerator.Parameters.ImageResolution`, если нужна более высокая чёткость (например, 300 dpi). |
| **Неправильный формат данных** | DataBar принимает только числовые строки до 13 цифр в некоторых режимах. | Проверьте строку ввода перед передачей её в генератор. |

## Расширение примера

Теперь, когда вы умеете **создавать Databar Stacked штрих‑код** с пользовательскими столбцами и строками, вы можете исследовать:

- **Изменение цветов переднего/фонового плана** (`barcodeGenerator.Parameters.Barcode.Color = Color.Blue;`).
- **Добавление зоны тишины** (`barcodeGenerator.Parameters.Barcode.Qz = 2;`).
- **Экспорт в SVG** для независимого от разрешения рендеринга (`BarCodeImageFormat.Svg`).

Все эти параметры задокументированы в [справочнике API Aspose.Barcode for .NET](https://docs.aspose.com/barcode/net/).

## Полный исходный код

Ниже приведена полностью готовая к запуску программа, включающая каждый описанный выше шаг. Скопируйте её в ваш `Program.cs`, замените `YOUR_DIRECTORY` реальным путём и выполните `dotnet run`.

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;
using System;
using System.IO;

class Program
{
    static void Main()
    {
        // Ensure the output directory exists
        string outputDir = @"YOUR_DIRECTORY";
        Directory.CreateDirectory(outputDir);

        // -------------------------------------------------
        // Step 1: Generator for 4‑column stacked barcode
        // -------------------------------------------------
        BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
            EncodeTypes.DatabarExpandedStacked,
            "Databar Expanded Stacked long");

        // Set 4 columns (default rows = 2)
        barcodeGenerator.Parameters.Barcode.DataBar.Columns = 4;

        string colsPath = Path.Combine(outputDir, "DatabarCols4.png");
        barcodeGenerator.Save(colsPath, BarCodeImageFormat.Png);
        Console.WriteLine($"Saved 4‑column barcode to {colsPath}");

        // -------------------------------------------------
        // Step 2: Generator for 3‑row stacked barcode
        // -------------------------------------------------
        BarcodeGenerator barcodeGeneratorRows = new BarcodeGenerator(
            EncodeTypes.DatabarExpandedStacked,
            "Databar Expanded Stacked long");

        // Set 3 rows (default columns = 2)
        barcodeGeneratorRows.Parameters.Barcode.DataBar.Rows = 3;

        string rowsPath = Path.Combine(outputDir, "DatabarRows3.png");
        barcodeGeneratorRows.Save(rowsPath, BarCodeImageFormat.Png);
        Console.WriteLine($"Saved 3‑row barcode to {rowsPath}");
    }
}
```

Запуск программы создаст два PNG‑файла, демонстрирующие, как **столбцы штрих‑кода** и **строки штрих‑кода** влияют на визуальное расположение символа **Databar Expanded Stacked**.

## Заключение

Теперь вы знаете, как **создать Databar Stacked штрих‑код** в C# с помощью Aspose.Barcode for .NET. Регулируя свойства `Columns` и `Rows`, можно генерировать штрих‑коды, подходящие под самые разные ограничения по пространству, при этом сохраняется целостность данных. Пример охватывает всё: от настройки проекта до устранения неполадок, предоставляя прочную основу для более сложных сценариев работы со штрих‑кодами.

**Следующие шаги:**  
- Поэкспериментируйте с разными строками данных и посмотрите, как ограничения столбцов/строк влияют на читаемость.  
- Объедините этот код с веб‑API для генерации штрих‑кодов «по запросу».  
- Исследуйте другие символьности (например, QR, Code128), используя тот же шаблон `BarcodeGenerator`.

Удачной разработки, и пусть ваши сканирования всегда проходят успешно!


## Что изучать дальше?


В следующих руководствах рассматриваются тесно связанные темы, которые развивают техники, продемонстрированные в этом пособии. Каждый ресурс содержит полностью работающие примеры кода с пошаговыми объяснениями, помогающими освоить дополнительные возможности API и исследовать альтернативные подходы в ваших проектах.

- [Barcode Generator C# – Create DataBar Expanded Stacked Images](/barcode/english/python-java/general/barcode-generator-c-create-databar-expanded-stacked-images/)
- [databar expanded stacked barcode guide – how to generate and size it in C#](/barcode/english/python-java/general/databar-expanded-stacked-barcode-guide-how-to-generate-and-s/)
- [Generate Aspose.BarCode Databar barcode using .NET API – Row & Column Configuration](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-row-column-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}