---
category: general
date: 2026-08-09
description: Создайте изображение штрихкода в C# с этим пошаговым руководством. Узнайте,
  как генерировать штрихкод, регулировать высоту штрихкода в пикселях и эффективно
  создавать несколько штрихкодов.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode image
- how to generate barcode
- barcode generator c#
- create multiple barcodes
- barcode height pixels
language: ru
lastmod: 2026-08-09
og_description: Создайте изображение штрихкода в C# быстро. Следуйте этому руководству,
  чтобы узнать, как генерировать штрихкод, задавать высоту штрихкода в пикселях и
  создавать несколько штрихкодов.
og_image_alt: Screenshot of barcode images generated with C# code showing different
  heights
og_title: Создание изображения штрих‑кода в C# – полное руководство для разработчиков
schemas:
- author: Aspose
  dateModified: '2026-08-09'
  description: Create barcode image in C# with this step-by-step guide. Learn how
    to generate barcode, adjust barcode height pixels, and create multiple barcodes
    efficiently.
  headline: Create barcode image in C# – complete programming guide
  type: TechArticle
- description: Create barcode image in C# with this step-by-step guide. Learn how
    to generate barcode, adjust barcode height pixels, and create multiple barcodes
    efficiently.
  name: Create barcode image in C# – complete programming guide
  steps:
  - name: Define the output folder
    text: Choose a folder where the generated PNG files will be stored. Using an absolute
      path avoids permission surprises.
  - name: Instantiate the barcode generator
    text: For a DataBar Omnidirectional barcode, pass `EncodeTypes.DatabarOmniDirectional`
      and the GS1‑128 data string.
  - name: Set common barcode parameters
    text: The most common visual tweaks are the X‑dimension (module width) and the
      bar height. Both are expressed in pixels.
  - name: Save the first barcode image
    text: '```csharp // Step 4: Save the barcode image with a 30 px height string
      file30 = Path.Combine(outputFolder, "DatabarBarHeight30Pixels.png"); barcode.Save(file30,
      BarCodeImageFormat.Png); ```'
  - name: Adjust the barcode height pixels
    text: Changing the height does not require a new `BarcodeGenerator` instance—just
      modify the parameter.
  - name: Save the second barcode image
    text: '```csharp // Step 6: Save the barcode image with the new 60 px height string
      file60 = Path.Combine(outputFolder, "DatabarBarHeight60Pixels.png"); barcode.Save(file60,
      BarCodeImageFormat.Png); ```'
  - name: Expected output
    text: 'After running the full sample, the `Barcodes` folder contains:'
  type: HowTo
tags:
- barcode
- C#
- image generation
title: Создание изображения штрих‑кода в C# — полное руководство по программированию
url: /ru/python-java/general/create-barcode-image-in-c-complete-programming-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Создание изображения штрих‑кода в C# – полное руководство по программированию

Если вам нужно **создать изображение штрих‑кода** в приложении .NET, это руководство покажет вам точно **как генерировать штрих‑код** с использованием библиотеки Aspose.BarCode. Вы увидите, как управлять **пикселями высоты штрих‑кода**, сохранять изображение и создавать **несколько штрих‑кодов** без дублирования кода.

В руководстве рассматривается всё — от установки пакета до настройки размеров, так что вы можете скопировать‑вставить готовый пример, готовый к запуску, в свой проект уже сегодня.

## Предварительные требования

* .NET 6.0 SDK или более поздняя версия, установленная  
* Visual Studio 2022 (или любой IDE для C#)  
* Пакет NuGet `Aspose.BarCode` – установить с помощью  

```bash
dotnet add package Aspose.BarCode
```

Дополнительные зависимости не требуются.

## Как сгенерировать изображение штрих‑кода с помощью BarcodeGenerator C#

Основным классом для создания изображения штрих‑кода является `BarcodeGenerator`. Он инкапсулирует тип кодирования, строку данных и все параметры рендеринга.

### Шаг 1: Определите папку вывода

Выберите папку, в которой будут сохраняться сгенерированные PNG‑файлы. Использование абсолютного пути избавляет от неожиданностей с правами доступа.

```csharp
// Step 1: Define the output folder
string outputFolder = Path.Combine(Environment.CurrentDirectory, "Barcodes");
Directory.CreateDirectory(outputFolder);
```

> **Почему?** Программное создание папки гарантирует, что последующие вызовы `Save` будут успешными даже на чистой машине.

### Шаг 2: Создайте экземпляр генератора штрих‑кода

Для штрих‑кода DataBar Omnidirectional передайте `EncodeTypes.DatabarOmniDirectional` и строку данных GS1‑128.

```csharp
// Step 2: Create a DataBar Omnidirectional barcode generator with the data to encode
var barcode = new BarcodeGenerator(
    EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");
```

> **Примечание:** Объект `BarcodeGenerator` можно переиспользовать; вы можете менять его параметры между сохранениями, чтобы **создавать несколько штрих‑кодов** из одних и тех же данных.

### Шаг 3: Установите общие параметры штрих‑кода

Самыми распространёнными визуальными настройками являются X‑размер (ширина модуля) и высота штриха. Оба параметра задаются в пикселях.

```csharp
// Step 3: Set common barcode parameters (X‑dimension and initial height)
barcode.Parameters.Barcode.XDimension.Pixels = 2;   // thin modules for sharper output
barcode.Parameters.Barcode.BarHeight.Pixels = 30;  // initial height – 30 px
```

> **Зачем задавать X‑размер?** Меньший X‑размер дает более высокое разрешение, что важно, когда изображение будет печататься или отображаться на экранах с высоким DPI.

### Шаг 4: Сохраните первое изображение штрих‑кода

```csharp
// Step 4: Save the barcode image with a 30 px height
string file30 = Path.Combine(outputFolder, "DatabarBarHeight30Pixels.png");
barcode.Save(file30, BarCodeImageFormat.Png);
```

Файл `DatabarBarHeight30Pixels.png` теперь содержит DataBar Omnidirectional штрих‑код высотой 30 пикселей.

### Шаг 5: Измените высоту штрих‑кода в пикселях

Изменение высоты не требует создания нового экземпляра `BarcodeGenerator` — достаточно изменить параметр.

```csharp
// Step 5: Change the bar height to 60 px for the same barcode
barcode.Parameters.Barcode.BarHeight.Pixels = 60;
```

### Шаг 6: Сохраните второе изображение штрих‑кода

```csharp
// Step 6: Save the barcode image with the new 60 px height
string file60 = Path.Combine(outputFolder, "DatabarBarHeight60Pixels.png");
barcode.Save(file60, BarCodeImageFormat.Png);
```

Теперь у вас есть два PNG‑файла с разными **пикселями высоты штрих‑кода**, демонстрирующие, насколько просто создавать варианты **изображения штрих‑кода**.

## Динамическая установка высоты штрих‑кода в пикселях

Часто требуется серия штрих‑кодов с высотой, соответствующей элементам UI или печатным этикеткам. Ниже приведён вспомогательный метод, абстрагирующий изменение высоты:

```csharp
/// <summary>
/// Saves a barcode image with a custom height.
/// </summary>
/// <param name="generator">Configured BarcodeGenerator instance.</param>
/// <param name="heightPx">Desired bar height in pixels.</param>
/// <param name="fileName">Target file name (including path).</param>
void SaveBarcodeWithHeight(BarcodeGenerator generator, int heightPx, string fileName)
{
    generator.Parameters.Barcode.BarHeight.Pixels = heightPx;
    generator.Save(fileName, BarCodeImageFormat.Png);
}
```

Теперь вы можете вызвать `SaveBarcodeWithHeight(barcode, 45, "BarHeight45.png");`, чтобы **создать изображение штрих‑кода** высотой 45 пикселей одной строкой.

## Создание нескольких штрих‑кодов в цикле

Когда у вас есть коллекция идентификаторов продуктов, цикл `foreach` устраняет повторяющийся код. Этот пример показывает, как **создавать несколько штрих‑кодов** из массива GTIN.

```csharp
string[] gtins = { "01234567890123", "09876543210987", "12345098765432" };
int[] heights = { 30, 45, 60 }; // different heights for visual variety

for (int i = 0; i < gtins.Length; i++)
{
    // Encode each GTIN as a DataBar Omnidirectional barcode
    var gen = new BarcodeGenerator(EncodeTypes.DatabarOmniDirectional,
                                   $"(01){gtins[i]}");

    // Reuse the X‑dimension setting for consistency
    gen.Parameters.Barcode.XDimension.Pixels = 2;

    // Choose a height from the heights array (or calculate dynamically)
    int height = heights[i % heights.Length];
    string filePath = Path.Combine(outputFolder,
        $"Databar_{gtins[i]}_Height{height}px.png");

    SaveBarcodeWithHeight(gen, height, filePath);
}
```

Цикл создаёт три PNG‑файла, каждый с отдельным значением **пикселей высоты штрих‑кода**. Поскольку вспомогательный метод `SaveBarcodeWithHeight` инкапсулирует изменение высоты, основной цикл остаётся чистым и сосредоточенным на данных.

### Ожидаемый результат

После выполнения полного примера в папке `Barcodes` будет:

```
DatabarBarHeight30Pixels.png
DatabarBarHeight60Pixels.png
Databar_01234567890123_Height30px.png
Databar_09876543210987_Height45px.png
Databar_12345098765432_Height60px.png
```

Открытие любого PNG‑файла покажет чёткий DataBar Omnidirectional штрих‑код, который может быть считан стандартными мобильными приложениями.

## Распространённые ошибки и профессиональные советы

| Проблема | Почему происходит | Как избежать |
|----------|-------------------|--------------|
| **Неправильные EncodeTypes** | Использование 1D‑типа для DataBar приводит к нечитаемому изображению. | Всегда выбирайте `EncodeTypes.DatabarOmniDirectional` (или другую вариацию DataBar) для полезных данных GS1‑128. |
| **Недостаточный X‑dimension** | Очень маленький X‑dimension может привести к исчезновению тонких штрихов на мониторах с низким разрешением. | Держите `XDimension.Pixels` ≥ 2 для отображения на экране; увеличьте до 3‑4 для печати. |
| **Ошибки пути к файлу** | Относительные пути могут разрешаться в неожиданные каталоги. | Используйте `Path.Combine` и `Environment.CurrentDirectory` для построения абсолютных путей. |
| **Перезапись изображений** | Повторное использование одного и того же имени файла в цикле перезаписывает предыдущие результаты. | Включайте уникальные идентификаторы (например, GTIN или метку времени) в имя файла. |
| **Отсутствующий пакет NuGet** | Код компилируется, но во время выполнения бросает `FileNotFoundException`. | Убедитесь, что `Aspose.BarCode` установлен и проект ссылается на него. |

## Полный рабочий пример

Ниже представлен полный код программы, который вы можете скопировать в консольное приложение. Он включает все шаги, вспомогательные методы и обработку ошибок.

```csharp
using System;
using System.IO;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Prepare output folder
        string outputFolder = Path.Combine(Environment.CurrentDirectory, "Barcodes");
        Directory.CreateDirectory(outputFolder);

        // ---------- Single barcode with two heights ----------
        var barcode = new BarcodeGenerator(
            EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");

        barcode.Parameters.Barcode.XDimension.Pixels = 2;
        barcode.Parameters.Barcode.BarHeight.Pixels = 30;
        barcode.Save(Path.Combine(outputFolder, "DatabarBarHeight30Pixels.png"),
                     BarCodeImageFormat.Png);

        barcode.Parameters.Barcode.BarHeight.Pixels = 60;
        barcode.Save(Path.Combine(outputFolder, "DatabarBarHeight60Pixels.png"),
                     BarCodeImageFormat.Png);

        // ---------- Helper for dynamic heights ----------
        void SaveBarcodeWithHeight(BarcodeGenerator gen, int heightPx, string fileName)
        {
            gen.Parameters.Barcode.BarHeight.Pixels = heightPx;
            gen.Save(fileName, BarCodeImageFormat.Png);
        }

        // ---------- Multiple barcodes ----------
        string[] gtins = { "01234567890123", "09876543210987", "12345098765432" };
        int[] heights = { 30, 45, 60 };

        for (int i = 0; i < gtins.Length; i++)
        {
            var gen = new BarcodeGenerator(EncodeTypes.DatabarOmniDirectional,
                                           $"(01){gtins[i]}");
            gen.Parameters.Barcode.XDimension.Pixels = 2;

            int height = heights[i % heights.Length];
            string filePath = Path.Combine(outputFolder,
                $"Databar_{gtins[i]}_Height{height}px.png");

            SaveBarcodeWithHeight(gen, height, filePath);
        }

        Console.WriteLine($"Barcode images created in: {outputFolder}");
    }
}
```

Запуск этой программы

## Что изучать дальше?

Следующие руководства охватывают тесно связанные темы, опирающиеся на техники, продемонстрированные в этом руководстве. Каждый ресурс включает полностью работающие примеры кода с пошаговыми объяснениями, чтобы помочь вам освоить дополнительные возможности API и изучить альтернативные подходы к реализации в собственных проектах.

- [Создать штрих‑код с пользовательской высотой – Одномерные штрих‑коды](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-barcode-height-adjustment/)
- [Создать изображение штрих‑кода C# – Пример GS1 DataMatrix](/barcode/english/net/gs1-barcode-encoding/gs1-datamatrix-example/)
- [Создать изображение штрих‑кода DotCode – строки и столбцы (Aspose.BarCode)](/barcode/english/net/dotcode-barcode-configuration/dotcode-rows-columns-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}