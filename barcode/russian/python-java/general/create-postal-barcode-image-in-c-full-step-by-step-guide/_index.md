---
category: general
date: 2026-07-27
description: Создайте изображение почтового штрихкода на C# быстро — узнайте, как
  генерировать почтовый штрихкод, штрихкод Planet и как задать высоту штрихкода.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create postal barcode image
- how to generate postal barcode
- generate planet barcode
- how to set barcode height
language: ru
lastmod: 2026-07-27
og_description: Создайте изображение почтового штрихкода на C# и освоите, как генерировать
  почтовый штрихкод, генерировать штрихкод Planet и как задать высоту штрихкода для
  идеальных результатов.
og_image_alt: Sample PNG showing Planet and RM4SCC postal barcodes generated with
  Aspose.BarCode
og_title: Создание изображения почтового штрихкода в C# – Полный программный обзор
schemas:
- author: Aspose
  dateModified: '2026-07-27'
  description: Create postal barcode image in C# quickly—learn how to generate postal
    barcode, generate planet barcode, and how to set barcode height.
  headline: Create Postal Barcode Image in C# – Full Step‑by‑Step Guide
  type: TechArticle
- description: Create postal barcode image in C# quickly—learn how to generate postal
    barcode, generate planet barcode, and how to set barcode height.
  name: Create Postal Barcode Image in C# – Full Step‑by‑Step Guide
  steps:
  - name: Why set `XDimension`?
    text: '`XDimension` is the pixel width of the smallest bar. If you leave it at
      the library’s default (usually 1 px), the barcode can look cramped on high‑resolution
      screens. Setting it to **4 px** gives a nicely spaced image that prints cleanly
      on most printers.'
  - name: What does `BarHeight.Pixels` actually do?
    text: When you **set barcode height**, you override the library’s automatic calculation.
      By default Aspose.BarCode chooses a height that keeps the barcode square‑ish,
      which is fine for many use‑cases. However, postal standards sometimes demand
      a minimum bar height (e.g., 100 px for high‑resolution printin
  - name: Edge Cases & Common Pitfalls
    text: '- **Zero or negative height** – the library throws `ArgumentException`.
      Always validate user input. - **Non‑integer pixel values** – the property is
      an `int`, so fractions are rounded down automatically. - **Changing DPI after
      setting height** – the visual size changes, but the pixel count stays the'
  - name: Expected Output
    text: 'When you open the generated PNG files you’ll see:'
  type: HowTo
tags:
- barcode
- C#
- Aspose
- postal
title: Создание изображения почтового штрихкода в C# – полное пошаговое руководство
url: /ru/python-java/general/create-postal-barcode-image-in-c-full-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Создание изображения почтового штрихкода в C# – Полное пошаговое руководство

Когда‑нибудь вам нужно было **создать изображение почтового штрихкода** в C#, но вы не знали, какие свойства настраивать? Вы не одиноки. Независимо от того, создаёте ли вы систему почтовых ярлыков или просто экспериментируете с почтовыми символьными системами, освоение правильных вызовов API делает всё это простым как раз.

В этом руководстве мы пройдёмся по **как генерировать почтовый штрихкод** изображения для форматов Planet и RM4SCC, и покажем вам **как задать высоту штрихкода**, чтобы полосы выглядели точно так, как вы ожидаете. К концу у вас будет готовое к запуску консольное приложение, которое создаст четыре PNG‑файла — два с высотой по умолчанию и два с явно заданной высотой полосы 100 px.

## Что вам понадобится

- **.NET 6.0** или новее (код также компилируется на .NET Framework 4.6+)  
- **Aspose.BarCode for .NET** – пакет NuGet, который предоставляет `BarcodeGenerator`  
- Папка на диске, куда можно сохранять PNG‑файлы (замените `YOUR_DIRECTORY` в примере)  

Если вы ещё не использовали Aspose.BarCode, получите его из NuGet:

```bash
dotnet add package Aspose.BarCode
```

Вот и всё — никаких дополнительных DLL, никаких нативных зависимостей. Погрузимся.

## Создание изображения почтового штрихкода — инициализация генератора

Первое, что вы делаете, — создаёте экземпляр `BarcodeGenerator`. Этот объект является точкой входа для *любого* штрихкода, который вы хотите отобразить. Вы передаёте два аргумента конструктору:

1. **Тип кодирования** (`EncodeTypes.Planet` или `EncodeTypes.RM4SCC`)  
2. **Строка данных** (числовой почтовый индекс, например `"123456"`)

```csharp
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Folder where PNG files will be saved
        const string outputFolder = @"C:\Temp\Barcodes";

        // Ensure the folder exists
        System.IO.Directory.CreateDirectory(outputFolder);

        // ---------- Planet barcode with default height ----------
        var planetGenerator = new BarcodeGenerator(EncodeTypes.Planet, "123456");
        // X‑dimension controls the width of the narrowest bar (in pixels)
        planetGenerator.Parameters.Barcode.XDimension.Pixels = 4;
        string planetDefaultPath = System.IO.Path.Combine(outputFolder, "PlanetDefault.png");
        planetDefaultPath = System.IO.Path.ChangeExtension(planetDefaultPath, "png");
        planetGenerator.Save(planetDefaultPath, BarCodeImageFormat.Png);

        // ---------- RM4SCC barcode with default height ----------
        var rm4sccGenerator = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");
        rm4sccGenerator.Parameters.Barcode.XDimension.Pixels = 4;
        string rm4sccDefaultPath = System.IO.Path.Combine(outputFolder, "RM4SCCDefault.png");
        rm4sccGenerator.Save(rm4sccDefaultPath, BarCodeImageFormat.Png);
```

### Зачем задавать `XDimension`?

`XDimension` — это ширина в пикселях самой маленькой полосы. Если оставить значение по умолчанию библиотеки (обычно 1 px), штрихкод может выглядеть сжато на экранах с высоким разрешением. Установка значения **4 px** даёт хорошо распределённое изображение, которое чисто печатается на большинстве принтеров.

## Как генерировать почтовый штрихкод — типы Planet и RM4SCC

Теперь, когда у нас есть генератор, давайте поговорим о *двух* самых распространённых почтовых символьных системах: **Planet** (используется в Великобритании) и **RM4SCC** (используется в США). Единственное различие в коде — значение перечисления `EncodeTypes`. Всё остальное — сохранение, DPI или формат PNG — остаётся тем же.

```csharp
        // ---------- Planet barcode with explicit 100 px height ----------
        var planetHeightGenerator = new BarcodeGenerator(EncodeTypes.Planet, "123456");
        planetHeightGenerator.Parameters.Barcode.XDimension.Pixels = 4;
        // Here we answer the “how to set barcode height” question.
        planetHeightGenerator.Parameters.Barcode.BarHeight.Pixels = 100;
        string planetHeightPath = System.IO.Path.Combine(outputFolder, "PlanetHeight100.png");
        planetHeightGenerator.Save(planetHeightPath, BarCodeImageFormat.Png);

        // ---------- RM4SCC barcode with explicit 100 px height ----------
        var rm4sccHeightGenerator = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");
        rm4sccHeightGenerator.Parameters.Barcode.XDimension.Pixels = 4;
        rm4sccHeightGenerator.Parameters.Barcode.BarHeight.Pixels = 100;
        string rm4sccHeightPath = System.IO.Path.Combine(outputFolder, "RM4SCCHeight100.png");
        rm4sccHeightGenerator.Save(rm4sccHeightPath, BarCodeImageFormat.Png);
    }
}
```

### Что на самом деле делает `BarHeight.Pixels`?

Когда вы **задаёте высоту штрихкода**, вы переопределяете автоматический расчёт библиотеки. По умолчанию Aspose.BarCode выбирает высоту, которая делает штрихкод почти квадратным, что подходит для многих случаев. Однако почтовые стандарты иногда требуют минимальную высоту полосы (например, 100 px для печати с высоким разрешением). Свойство `BarHeight.Pixels` позволяет точно соответствовать этим требованиям.

## Как задать высоту штрихкода — управление высотой полосы для почтовых стандартов

Если вы задаётесь вопросом **как задать высоту штрихкода** для конкретного DPI принтера, вы можете комбинировать `BarHeight.Pixels` с настройками `Resolution`:

```csharp
        // Example: 300 DPI, 1 inch tall => 300 px
        planetHeightGenerator.Parameters.ImageResolution = 300;
        planetHeightGenerator.Parameters.Barcode.BarHeight.Pixels = 300; // 1‑inch bar at 300 DPI
```

> **Совет:** Всегда тестируйте несколько разных высот на целевом принтере. Слишком высокая, и штрихкод может выйти за пределы печатной области ярлыка; слишком низкая, и сканеры могут не обнаружить зону тишины.

### Пограничные случаи и распространённые подводные камни

- **Нулевая или отрицательная высота** — библиотека бросает `ArgumentException`. Всегда проверяйте ввод пользователя.  
- **Нецелочисленные значения пикселей** — свойство имеет тип `int`, поэтому дроби автоматически округляются вниз.  
- **Изменение DPI после установки высоты** — визуальный размер меняется, но количество пикселей остаётся тем же. Если нужна физическая величина (например, 1 cm), вычисляйте `pixels = DPI * cm / 2.54`.

## Полный рабочий пример — все шаги вместе

Ниже приведена полная готовая к копированию программа. Она включает обработку ошибок, создание папки и комментарии, объясняющие каждую строку. Запустите её из консольного проекта, и вы получите четыре PNG‑файла в `C:\Temp\Barcodes`.

```csharp
using System;
using System.IO;
using Aspose.BarCode.Generation;

namespace PostalBarcodeDemo
{
    class Program
    {
        static void Main()
        {
            const string outputFolder = @"C:\Temp\Barcodes";
            Directory.CreateDirectory(outputFolder);

            try
            {
                // 1️⃣ Planet barcode – default (automatic) height
                var planetDefault = new BarcodeGenerator(EncodeTypes.Planet, "123456");
                planetDefault.Parameters.Barcode.XDimension.Pixels = 4;
                string planetDefaultPath = Path.Combine(outputFolder, "PlanetDefault.png");
                planetDefault.Save(planetDefaultPath, BarCodeImageFormat.Png);
                Console.WriteLine($"Saved: {planetDefaultPath}");

                // 2️⃣ RM4SCC barcode – default (automatic) height
                var rm4sccDefault = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");
                rm4sccDefault.Parameters.Barcode.XDimension.Pixels = 4;
                string rm4sccDefaultPath = Path.Combine(outputFolder, "RM4SCCDefault.png");
                rm4sccDefault.Save(rm4sccDefaultPath, BarCodeImageFormat.Png);
                Console.WriteLine($"Saved: {rm4sccDefaultPath}");

                // 3️⃣ Planet barcode – explicit 100 px height
                var planetHeight = new BarcodeGenerator(EncodeTypes.Planet, "123456");
                planetHeight.Parameters.Barcode.XDimension.Pixels = 4;
                planetHeight.Parameters.Barcode.BarHeight.Pixels = 100;
                string planetHeightPath = Path.Combine(outputFolder, "PlanetHeight100.png");
                planetHeight.Save(planetHeightPath, BarCodeImageFormat.Png);
                Console.WriteLine($"Saved: {planetHeightPath}");

                // 4️⃣ RM4SCC barcode – explicit 100 px height
                var rm4sccHeight = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");
                rm4sccHeight.Parameters.Barcode.XDimension.Pixels = 4;
                rm4sccHeight.Parameters.Barcode.BarHeight.Pixels = 100;
                string rm4sccHeightPath = Path.Combine(outputFolder, "RM4SCCHeight100.png");
                rm4sccHeight.Save(rm4sccHeightPath, BarCodeImageFormat.Png);
                Console.WriteLine($"Saved: {rm4sccHeightPath}");
            }
            catch (Exception ex)
            {
                Console.Error.WriteLine($"Something went wrong: {ex.Message}");
            }
        }
    }
}
```

### Ожидаемый результат

Когда вы откроете сгенерированные PNG‑файлы, вы увидите:

| Файл | Символика | Высота | Визуальные заметки |
|------|-----------|--------|--------------------|
| `PlanetDefault.png` | Planet | Automatic (≈ 50 px) | Тонкая |

## Что стоит изучить дальше?

Следующие руководства охватывают тесно связанные темы, которые развивают техники, продемонстрированные в этом руководстве. Каждый ресурс включает полные рабочие примеры кода с пошаговыми объяснениями, чтобы помочь вам освоить дополнительные возможности API и исследовать альтернативные подходы к реализации в ваших проектах.

- [Как генерировать штрихкоды — одноразмерные типы штрихкодов](/barcode/english/net/one-dimensional-barcode-types/)
- [Как генерировать штрихкоды — конфигурация Code 39 с Aspose.BarCode](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-code-39-configuration/)
- [Как генерировать DataMatrix штрихкоды (ECC 200) с Aspose.BarCode для .NET](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-ecc-200-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}