---
category: general
date: 2026-08-22
description: Узнайте, как генерировать почтовый штрих‑код в C# и управлять высотой
  штриха, размером X и форматом изображения с помощью библиотеки генератора штрих‑кодов
  C#.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate postal barcode
- barcode generator c#
- barcode x dimension
- barcode image format
- change barcode width
language: ru
lastmod: 2026-08-22
og_description: Создайте почтовый штрих‑код на C# с полным контролем высоты штриха,
  X‑размера и формата изображения. Следуйте этому пошаговому руководству, чтобы создать
  идеальные почтовые символы.
og_image_alt: Example of a generated postal barcode with custom bar height in C#
og_title: Создание почтового штрихкода в C# – полное руководство с пользовательским
  размером
schemas:
- author: Aspose
  dateModified: '2026-08-22'
  description: Learn how to generate postal barcode in C# and control bar height,
    X dimension, and image format using the barcode generator C# library.
  headline: How to generate postal barcode in C# with custom dimensions
  type: TechArticle
tags:
- barcode
- C#
- image processing
title: Как сгенерировать почтовый штрих‑код в C# с пользовательскими размерами
url: /ru/python-java/general/how-to-generate-postal-barcode-in-c-with-custom-dimensions/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Как генерировать почтовый штрих‑код в C# с пользовательскими размерами

Если вам нужно генерировать почтовый штрих‑код в C#, это руководство покажет вам полный процесс. Вы увидите, как управлять высотой полос, регулировать X‑размер штрих‑кода и выбирать подходящий формат изображения штрих‑кода.

Почтовые штрих‑коды используются почтовыми службами по всему миру, и надёжная реализация должна обеспечивать одинаковые размеры для разных символогий. В этом уроке вы научитесь использовать класс **BarcodeGenerator**, изменять ширину штрих‑кода и сохранять результат в формате PNG, JPEG или других поддерживаемых форматах.

## Предварительные требования

* .NET 6.0 или новее установлен  
* Ссылка на пакет NuGet **Aspose.BarCode** (или любая совместимая библиотека генератора штрих‑кодов для C#)  
* Базовое знакомство с синтаксисом C# и Visual Studio или вашей предпочтительной IDE  

Внешние сервисы не требуются; код полностью выполняется на клиентском компьютере.

## Шаг 1: Настройте проект и импортируйте пространства имён

Создайте новое консольное приложение и добавьте библиотеку штрих‑кодов. Ниже приведённые директивы `using` дают доступ к генератору и перечислениям форматов изображений.

```csharp
using System;
using Aspose.BarCode.Generation;   // Provides BarcodeGenerator, EncodeTypes, etc.
using Aspose.BarCode;               // Contains BarCodeImageFormat
```

Класс `BarcodeGenerator` является ядром API генератора штрих‑кодов на C#. Он создаёт объект, содержащий все параметры рендеринга.

## Шаг 2: Сгенерировать базовый почтовый штрих‑код с размерами по умолчанию

Первый пример создаёт штрих‑код Planet с высотой полос по умолчанию. Это демонстрирует минимальную конфигурацию, необходимую для генерации почтового штрих‑кода.

```csharp
// Create a Planet barcode with the default bar height
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(EncodeTypes.Planet, "123456");

// Set the module width (X dimension) to 4 pixels – this defines the narrow bar size
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 4;

// Save the image as PNG using the default bar height
barcodeGenerator.Save("PostalPlanetDefault.png", BarCodeImageFormat.Png);
```

*Почему это работает*: Когда вы опускаете свойство `BarHeight`, библиотека применяет стандартную высоту, определённую для выбранной символогии. `XDimension` управляет **X‑размером штрих‑кода**, который напрямую влияет на общую ширину символа.

## Шаг 3: Изменить ширину штрих‑кода и увеличить высоту полос

Часто требуется более высокая полоса, чтобы соответствовать определённым почтовым требованиям. Следующий код задаёт пользовательскую высоту полосы 100 пикселей, сохраняя тот же X‑размер.

```csharp
// Re‑use the generator for a custom height
barcodeGenerator = new BarcodeGenerator(EncodeTypes.Planet, "123456");
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 4;

// Increase the bar height to 100 pixels
barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 100;

// Save using the same PNG format
barcodeGenerator.Save("PostalPlanetHeight100.png", BarCodeImageFormat.Png);
```

*Зачем регулировать высоту*: Свойство `BarHeight` управляет вертикальным размером каждой полосы. Для почтовых служб, требующих минимальную высоту, установка этого значения обеспечивает соответствие без влияния на кодирование.

## Шаг 4: Сгенерировать штрих‑код RM4SCC с настройками по умолчанию

RM4SCC — ещё одна распространённая почтовая симвология. Приведённый ниже код повторяет пример с Planet, но меняет перечисление `EncodeTypes`.

```csharp
// Create an RM4SCC barcode with default bar height
barcodeGenerator = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 4;

// Save as PNG; default height is applied automatically
barcodeGenerator.Save("PostalRM4SCCDefault.png", BarCodeImageFormat.Png);
```

Поскольку библиотека автоматически выбирает соответствующую высоту по умолчанию для RM4SCC, вы получаете изображение, соответствующее стандартам, одной строкой кода.

## Шаг 5: Изменить высоту полосы для штрих‑кода RM4SCC

Если почтовая система требует более высокую полосу, вы можете изменить высоту точно так же, как делали это для Planet.

```csharp
// RM4SCC barcode with a custom 100‑pixel bar height
barcodeGenerator = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 4;
barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 100;

// Save the result; you may also choose JPEG, BMP, or TIFF
barcodeGenerator.Save("PostalRM4SCCHeight100.png", BarCodeImageFormat.Png);
```

*Подсказка*: Перечисление **barcode image format** включает `Jpeg`, `Bmp`, `Tiff` и `Gif`. Выберите формат, соответствующий вашему последующему конвейеру обработки.

## Шаг 6: Исследовать другие форматы изображений и точно настроить размеры

Ниже представлен компактный фрагмент, демонстрирующий, как переключать формат вывода и экспериментировать с различными X‑размерами.

```csharp
string[] formats = { "Png", "Jpeg", "Bmp", "Tiff" };
int[] xDims = { 2, 3, 4, 5 };

foreach (var fmt in formats)
{
    foreach (var x in xDims)
    {
        barcodeGenerator = new BarcodeGenerator(EncodeTypes.Planet, "123456");
        barcodeGenerator.Parameters.Barcode.XDimension.Pixels = x;
        barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 80; // consistent height

        // Dynamically choose the format enum
        BarCodeImageFormat imageFormat = (BarCodeImageFormat)Enum.Parse(
            typeof(BarCodeImageFormat), fmt, true);

        string fileName = $"Planet_X{x}_{fmt}.png";
        barcodeGenerator.Save(fileName, imageFormat);
    }
}
```

*Зачем итерация*: Выполнение этого цикла создаёт матрицу изображений, показывающих, как **изменение ширины штрих‑кода** (через X‑размер) влияет на общий вид. Это также демонстрирует, что один и тот же генератор может выводить несколько типов **barcode image format** без дополнительных изменений кода.

## Распространённые подводные камни и как их избежать

| Проблема | Причина | Решение |
|----------|---------|---------|
| Полосы слишком тонкие | X‑размер установлен в 1 пиксель или меньше | Установите `XDimension.Pixels` минимум в 2 для читаемости |
| Изображение размыто | Сохранение в JPEG с высоким уровнем сжатия | Используйте `BarCodeImageFormat.Png` для без потерь |
| Неожиданный размер при печати | DPI не учитывается | Установите `barcodeGenerator.Parameters.ImageResolution.Dpi`, если принтер ожидает определённый DPI |
| Неправильная симвология | Использование `EncodeTypes.Planet` для данных RM4SCC | Выберите правильное значение `EncodeTypes`, соответствующее спецификации почтовой службы |

## Проверка результата

После выполнения кода откройте любой из сгенерированных PNG‑файлов. Вы должны увидеть чёткий прямоугольный штрих‑код с равномерными вертикальными полосами. Высота полос будет соответствовать заданному значению (например, 100 пикселей), а общая ширина отразит **X‑размер штрих‑кода**, который вы настроили.

Если необходимо встроить изображение в веб‑страницу, формат PNG поддерживается браузерами из коробки. Для PDF‑отчётов вы можете преобразовать PNG в массив байтов и вставить его с помощью библиотеки PDF.

## Полный пример — все шаги в одной программе

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        // Directory for output files
        const string outDir = @"C:\Barcodes\";

        // 1. Planet barcode – default height
        GenerateBarcode(outDir, EncodeTypes.Planet, "123456", 4, null, "PlanetDefault.png");

        // 2. Planet barcode – custom height
        GenerateBarcode(outDir, EncodeTypes.Planet, "123456", 4, 100, "PlanetHeight100.png");

        // 3. RM4SCC barcode – default height
        GenerateBarcode(outDir, EncodeTypes.RM4SCC, "123456", 4, null, "RM4SCCDefault.png");

        // 4. RM4SCC barcode – custom height
        GenerateBarcode(outDir, EncodeTypes.RM4SCC, "123456", 4, 100, "RM4SCCHeight100.png");
    }

    /// <summary>
    /// Creates a barcode image with optional custom height.
    /// </summary>
    static void GenerateBarcode(string folder, EncodeTypes type, string data,
                                int xDim, int? barHeight, string fileName)
    {
        var generator = new BarcodeGenerator(type, data);
        generator.Parameters.Barcode.XDimension.Pixels = xDim;

        if (barHeight.HasValue)
            generator.Parameters.Barcode.BarHeight.Pixels = barHeight.Value;

        generator.Save(System.IO.Path.Combine(folder, fileName), BarCodeImageFormat.Png);
    }
}
```

Запуск этой программы создаёт четыре PNG‑файла в `C:\Barcodes\`. Каждый файл демонстрирует различную комбинацию **generate postal barcode**, **barcode X dimension** и **barcode image format**.

## Заключение

Теперь вы знаете, как генерировать почтовый штрих‑код в C# и полностью управлять высотой полос, шириной модуля и форматом вывода. Регулируя **barcode X dimension** и используя соответствующий **barcode image format**, вы сможете удовлетворить любые почтовые требования и интегрировать символы в настольные, веб‑ и мобильные приложения.

Далее изучайте расширенные возможности, такие как добавление читаемого человеком текста, применение цветовых палитр или встраивание штрих‑кода в PDF‑документы. Эти темы используют те же концепции **barcode generator C#**, которые вы только что освоили, поэтому вы можете уверенно расширять эту основу.

## Что изучать дальше?

Следующие руководства охватывают тесно связанные темы, построенные на техниках, продемонстрированных в этом руководстве. Каждый ресурс содержит полностью работающие примеры кода с пошаговыми объяснениями, помогающими освоить дополнительные возможности API и исследовать альтернативные подходы к реализации в ваших проектах.

- [Как генерировать и настраивать высоту штрих‑кода для одностороннего Databar с использованием Aspose.BarCode для .NET](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-barcode-height-adjustment/)
- [Создать изображение штрих‑кода – Code 93 с Aspose.BarCode](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-code-93-configuration/)
- [Как генерировать штрих‑код Aztec с пользовательским соотношением сторон с использованием Aspose.BarCode для .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}