---
category: general
date: 2026-08-15
description: Изображение штрихкода PNG в C# – узнайте, как генерировать почтовые штрихкоды,
  создавать штрихкод Planet и изменять высоту штрихкода с помощью простого генератора.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- barcode image png
- barcode generator c#
- generate postal barcode
- create planet barcode
- change barcode height
language: ru
lastmod: 2026-08-15
og_description: Учебник по созданию PNG‑изображения штрихкода в C# показывает, как
  генерировать почтовые штрихкоды, создавать штрихкод Planet и изменять высоту штрихкода
  с помощью API BarcodeGenerator.
og_image_alt: Screenshot of generated PNG barcode with custom height using C# BarcodeGenerator
og_title: PNG‑изображение штрихкода в C# – генерировать и настраивать штрихкоды
schemas:
- author: Aspose
  dateModified: '2026-08-15'
  description: Barcode image PNG in C# – learn how to generate postal barcodes, create
    a Planet barcode, and change barcode height with a simple generator.
  headline: Barcode image PNG in C# generate barcodes, change height
  type: TechArticle
tags:
- barcode
- C#
- PNG
- postal
- generator
title: Изображение штрихкода PNG в C# — генерация штрихкодов, изменение высоты
url: /ru/python-java/general/barcode-image-png-in-c-generate-barcodes-change-height/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Изображение штрихкода PNG в C# – генерация штрихкодов, изменение высоты

Если вам нужен **barcode image PNG** в C#, это руководство проведёт вас через весь процесс. Вы узнаете, как генерировать почтовые штрихкоды, создавать штрихкод Planet и менять высоту штрихкода, не покидая IDE.

Генерация надёжных PNG‑штрихкодов — частая потребность для транспортных этикеток, систем учёта запасов и автоматизированных почтовых решений. К концу этого урока у вас будет переиспользуемый фрагмент кода, который создаёт PNG‑файлы высокого качества для форматов Planet и RM4SCC, а также вы поймёте, как регулировать высоту полосы в соответствии с почтовыми требованиями.

## Что понадобится

- .NET 6+ или .NET Framework 4.7.2 (API BarcodeGenerator работает с любой современной средой .NET)  
- Ссылка на пакет **Aspose.BarCode for .NET** в NuGet (или любую совместимую библиотеку, предоставляющую `BarcodeGenerator`, `EncodeTypes` и `BarCodeImageFormat`)  
- Базовое знакомство с синтаксисом C# и файловым вводом‑выводом  

Дополнительные инструменты не требуются; код работает в Visual Studio, Rider или через `dotnet` CLI.

## Изображение штрихкода PNG – базовая генерация

Первый шаг — создать **barcode image PNG** с параметрами по умолчанию. Это базовый файл, который позже можно будет настроить.

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

// Define the output folder (replace with your own path)
string outputFolder = @"C:\Barcodes";

// Ensure the folder exists
Directory.CreateDirectory(outputFolder);

// 1️⃣ Create a Planet barcode generator with default height
BarcodeGenerator planetGenerator = new BarcodeGenerator(EncodeTypes.Planet, "123456");

// Set the module width (X‑dimension) to 4 pixels – this defines the thin bar size
planetGenerator.Parameters.Barcode.XDimension.Pixels = 4;

// Save the image as PNG; this is the first **barcode image PNG** you’ll produce
planetGenerator.Save(Path.Combine(outputFolder, "PlanetBarHeightDefault.png"),
                     BarCodeImageFormat.Png);
```

**Почему это работает:**  
- `EncodeTypes.Planet` указывает генератору использовать символьную систему Planet, требуемую многими почтовыми службами.  
- `XDimension.Pixels` задаёт ширину самой тонкой полосы; значение 4 px обеспечивает читаемость штрихкода при типичных размерах этикетки.  
- Метод `Save` записывает **barcode image PNG** файл на диск, сохраняя всю векторную информацию в виде растровых пикселей.

## Изменение высоты штрихкода – настройка визуального веса

Почтовые стандарты часто требуют определённую высоту полосы. Ниже показан фрагмент кода, который задаёт пользовательскую высоту 100 пикселей для того же штрихкода Planet.

```csharp
// 2️⃣ Apply a custom 100‑pixel bar height
planetGenerator.Parameters.Barcode.BarHeight.Pixels = 100;

// Overwrite or save as a new file to keep both versions
planetGenerator.Save(Path.Combine(outputFolder, "PlanetBarHeight100.png"),
                     BarCodeImageFormat.Png);
```

**Почему меняют высоту:**  
Более высокая полоса повышает надёжность сканирования на принтерах с низким разрешением, тогда как более низкая полоса экономит место на этикетке. Свойство `BarHeight.Pixels` позволяет точно настроить этот параметр, не затрагивая X‑размер.

## Генерация почтового штрихкода – пример RM4SCC

Формат RM4SCC — ещё один распространённый почтовый штрихкод, используемый в Соединённом Королевстве. Шаги генерации аналогичны примеру с Planet, укрепляя шаблон **barcode generator c#**.

```csharp
// 3️⃣ Create an RM4SCC barcode generator with default height
BarcodeGenerator rm4sccGenerator = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");

// Keep the same module width for consistency
rm4sccGenerator.Parameters.Barcode.XDimension.Pixels = 4;

// Save the default‑height PNG
rm4sccGenerator.Save(Path.Combine(outputFolder, "RM4SCCBarHeightDefault.png"),
                     BarCodeImageFormat.Png);
```

## Изменение высоты штрихкода – вариант RM4SCC

Точно так же, как и для штрихкода Planet, можно отрегулировать высоту полосы RM4SCC. Ниже код, задающий высоту 100 px и создающий второй **barcode image PNG** для той же строки данных.

```csharp
// 4️⃣ Set a custom 100‑pixel bar height for RM4SCC
rm4sccGenerator.Parameters.Barcode.BarHeight.Pixels = 100;

// Save the customized PNG
rm4sccGenerator.Save(Path.Combine(outputFolder, "RM4SCCBarHeight100.png"),
                     BarCodeImageFormat.Png);
```

## Полный, исполняемый пример

Объединяя все шаги, получаем единый, самодостаточный проект, создающий четыре PNG‑файла:

```csharp
using System;
using System.IO;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        string outputFolder = @"C:\Barcodes";
        Directory.CreateDirectory(outputFolder);

        // Planet barcode – default height
        var planet = new BarcodeGenerator(EncodeTypes.Planet, "123456");
        planet.Parameters.Barcode.XDimension.Pixels = 4;
        planet.Save(Path.Combine(outputFolder, "PlanetBarHeightDefault.png"),
                    BarCodeImageFormat.Png);

        // Planet barcode – custom 100‑pixel height
        planet.Parameters.Barcode.BarHeight.Pixels = 100;
        planet.Save(Path.Combine(outputFolder, "PlanetBarHeight100.png"),
                    BarCodeImageFormat.Png);

        // RM4SCC barcode – default height
        var rm4scc = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");
        rm4scc.Parameters.Barcode.XDimension.Pixels = 4;
        rm4scc.Save(Path.Combine(outputFolder, "RM4SCCBarHeightDefault.png"),
                    BarCodeImageFormat.Png);

        // RM4SCC barcode – custom 100‑pixel height
        rm4scc.Parameters.Barcode.BarHeight.Pixels = 100;
        rm4scc.Save(Path.Combine(outputFolder, "RM4SCCBarHeight100.png"),
                    BarCodeImageFormat.Png);

        Console.WriteLine("All barcode PNG files have been generated in " +


## Что следует изучить дальше?


Следующие руководства охватывают тесно связанные темы, расширяющие техники, продемонстрированные в этом руководстве. Каждый ресурс включает полностью работающие примеры кода с пошаговыми объяснениями, чтобы помочь вам освоить дополнительные возможности API и исследовать альтернативные подходы реализации в собственных проектах.

- [Create Barcode Custom Height – One-Dimensional Barcodes](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-barcode-height-adjustment/)
- [Create Barcode PNG – DataMatrix Aspect Ratio – Aspose.BarCode](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-aspect-ratio-customization/)
- [Create barcode image C# – GS1 DataMatrix Example](/barcode/english/net/gs1-barcode-encoding/gs1-datamatrix-example/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}