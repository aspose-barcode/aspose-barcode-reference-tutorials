---
category: general
date: 2026-09-23
description: Учебник по генерации штрихкодов на C# показывает, как создавать изображения
  штрихкодов с пользовательскими соотношениями сторон, используя библиотеку Aspose.BarCode.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- c# barcode generator
- how to generate barcode
- DataBar barcode C#
- barcode aspect ratio
- Aspose.BarCode C#
- barcode image export
language: ru
lastmod: 2026-09-23
og_description: Руководство по генератору штрихкодов на C# покажет вам, как создавать
  изображения штрихкодов, регулировать соотношения сторон и экспортировать PNG‑файлы
  с помощью Aspose.BarCode.
og_image_alt: Screenshot of a barcode created with a C# barcode generator
og_title: Создавайте высококачественные штрихкоды с помощью генератора штрихкодов
  на C#
schemas:
- author: Aspose
  dateModified: '2026-09-23'
  description: c# barcode generator tutorial shows how to generate barcode images
    with custom aspect ratios using the Aspose.BarCode library.
  headline: How to use a C# barcode generator for DataBar codes
  type: TechArticle
- description: c# barcode generator tutorial shows how to generate barcode images
    with custom aspect ratios using the Aspose.BarCode library.
  name: How to use a C# barcode generator for DataBar codes
  steps:
  - name: Switching to another barcode type
    text: 'If you need a QR code, Code 128, or PDF417, replace the enum value in the
      constructor:'
  - name: Handling unsupported characters
    text: 'The `BarcodeGenerator` validates the input string against the selected
      symbology. Supplying an illegal character throws an `ArgumentException`. Wrap
      the creation in a try‑catch block to provide a friendly error message:'
  - name: Exporting to other image formats
    text: 'Aspose.BarCode supports BMP, JPEG, TIFF, and SVG. Change the second argument
      of `Save` accordingly:'
  - name: High‑resolution output for printing
    text: 'When printing on high‑DPI printers, increase the X‑dimension and optionally
      set the `Resolution` property:'
  type: HowTo
tags:
- barcode
- c#
- Aspose
title: Как использовать генератор штрихкодов на C# для кодов DataBar
url: /ru/python-java/general/how-to-use-a-c-barcode-generator-for-databar-codes/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Как использовать генератор штрих‑кодов C# для кодов DataBar

Если вам нужен **c# barcode generator**, который может создавать DataBar stacked Omni‑Directional символы, это руководство предоставляет полное готовое решение. Вы увидите, как генерировать изображения штрих‑кодов, управлять X‑dimension и менять aspect ratio, не выходя из IDE.

Создание штрих‑кодов — распространённая потребность для систем учёта, транспортных этикеток и приложений точек продаж. К концу этого руководства вы сможете создавать PNG‑файлы с любым выбранным соотношением сторон и поймёте, как адаптировать код для других типов штрих‑кодов.

## Требования

* .NET 6.0 SDK или более поздняя версия, установленная  
* Visual Studio 2022 (или любой предпочитаемый вами редактор C#)  
* Ссылка NuGet на **Aspose.BarCode** — библиотека, реализующая класс `BarcodeGenerator`

Отдельная графическая библиотека не требуется; Aspose.BarCode обрабатывает кодирование изображений внутри.

## Шаг 1: Установите пакет NuGet Aspose.BarCode

Откройте терминал в папке проекта и выполните:

```bash
dotnet add package Aspose.BarCode
```

Эта команда добавит последнюю стабильную версию библиотеки в ваш файл проекта, делая класс `BarcodeGenerator` доступным для использования.

## Шаг 2: Определите папку вывода

Выберите папку, в которой будут сохраняться сгенерированные PNG‑файлы. Использование абсолютного или относительного пути работает одинаково, но относительный путь делает проект более переносимым.

```csharp
// Define the output folder (relative to the project root)
string outputFolder = "GeneratedBarcodes/";
Directory.CreateDirectory(outputFolder); // Ensure the folder exists
```

Создание каталога программно предотвращает ошибки выполнения, если папка отсутствует.

## Шаг 3: Создайте экземпляр генератора штрих‑кодов C# с примерными данными

Конструктор `BarcodeGenerator` требует два аргумента: тип штрих‑кода и строку данных. Для символа DataBar stacked Omni‑Directional используйте `EncodeTypes.DatabarStackedOmniDirectional`.

```csharp
// Create a barcode generator for a DataBar stacked Omni‑Directional code
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarStackedOmniDirectional,
    "(01)12345678901231");
```

Строка данных следует формату идентификатора приложения GS1. Перечисление `EncodeTypes` содержит более 150 стандартов штрих‑кодов; вы можете переключиться на другой тип, изменив значение перечисления.

## Шаг 4: Установите X‑dimension (размер в пикселях) для штрих‑кода

X‑dimension управляет шириной самого узкого штриха. Значение в 2 пикселя дает чёткое, высоко‑разрешающее изображение, подходящее для большинства экранов.

```csharp
// Set the X‑dimension to 2 pixels
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

Настройка X‑dimension необязательна, но предоставляет точный контроль над визуальной плотностью штрих‑кода.

## Шаг 5: Сгенерируйте штрих‑код с aspect ratio 15 и сохраните его как PNG

Свойство `AspectRatio` относится к под‑объекту `DataBar`. Изменение этого значения растягивает или сжимает штрих‑код по вертикали, сохраняя закодированные данные.

```csharp
// Set aspect ratio to 15 and save the image
barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 15;
barcodeGenerator.Save($"{outputFolder}DatabarAspectRatio15.png", BarCodeImageFormat.Png);
```

Метод `Save` записывает штрих‑код по указанному пути файла. Перечисление `BarCodeImageFormat.Png` обеспечивает сжатие без потерь.

![пример вывода генератора штрих‑кодов c#](generated_barcode_example.png)

*Изображение: штрих‑код, сгенерированный с aspect ratio 15.*

## Шаг 6: Измените aspect ratio на 30 и сгенерируйте второе изображение

Повторное использование того же экземпляра `BarcodeGenerator` избавляет от необходимости создавать новый объект. Просто обновите `AspectRatio` и снова вызовите `Save`.

```csharp
// Update aspect ratio to 30 and save a second image
barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 30;
barcodeGenerator.Save($"{outputFolder}DatabarAspectRatio30.png", BarCodeImageFormat.Png);
```

Теперь у вас есть два PNG‑файла, различающиеся только вертикальным масштабированием. Эта техника полезна, когда требуется отобразить одни и те же данные для этикеток разных размеров.

## Распространённые варианты и граничные случаи

### Переход к другому типу штрих‑кода

Если вам нужен QR‑code, Code 128 или PDF417, замените значение перечисления в конструкторе:

```csharp
BarcodeGenerator qrGenerator = new BarcodeGenerator(
    EncodeTypes.QR, "https://example.com");
```

Все остальные шаги настройки (X‑dimension, сохранение) остаются одинаковыми.

### Обработка неподдерживаемых символов

`BarcodeGenerator` проверяет входную строку в соответствии с выбранной символьной системой. Передача недопустимого символа вызывает `ArgumentException`. Оберните создание в блок try‑catch, чтобы предоставить понятное сообщение об ошибке:

```csharp
try
{
    var generator = new BarcodeGenerator(EncodeTypes.DatabarStackedOmniDirectional, data);
}
catch (ArgumentException ex)
{
    Console.WriteLine($"Invalid data for the selected barcode type: {ex.Message}");
}
```

### Экспорт в другие форматы изображений

Aspose.BarCode поддерживает BMP, JPEG, TIFF и SVG. Соответственно измените второй аргумент метода `Save`:

```csharp
barcodeGenerator.Save($"{outputFolder}Databar.svg", BarCodeImageFormat.Svg);
```

### Вывод высокого разрешения для печати

При печати на принтерах с высоким DPI увеличьте X‑dimension и при необходимости задайте свойство `Resolution`:

```csharp
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 4;
barcodeGenerator.Parameters.ImageResolution.Dpi = 300;
```

Эти настройки создают более крупные файлы, но сохраняют чёткие границы на физическом носителе.

## Ожидаемый результат

Запуск полной программы создаёт следующие файлы в папке `GeneratedBarcodes/`:

* `DatabarAspectRatio15.png` – DataBar‑код стандартной высоты  
* `DatabarAspectRatio30.png` – вертикально растянутый вариант  

Оба изображения содержат одинаковые закодированные данные GS1, и их можно проверить с помощью любого приложения‑сканера штрих‑кодов.

## Полный исходный код

Скопируйте код ниже в новый консольный проект (`dotnet new console`) и запустите его. Программа выводит сообщения о статусе в консоль и записывает PNG‑файлы на диск.

```csharp
using System;
using System.IO;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Step 2: Define the output folder
        string outputFolder = "GeneratedBarcodes/";
        Directory.CreateDirectory(outputFolder);

        // Step 3: Create a C# barcode generator with sample data
        BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
            EncodeTypes.DatabarStackedOmniDirectional,
            "(01)12345678901231");

        // Step 4: Set common barcode properties (pixel size of X‑dimension)
        barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;

        // Step 5: Generate a barcode with aspect ratio 15 and save it as PNG
        barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 15;
        string file15 = Path.Combine(outputFolder, "DatabarAspectRatio15.png");
        barcodeGenerator.Save(file15, BarCodeImageFormat.Png);
        Console.WriteLine($"Saved barcode with aspect ratio 15 to {file15}");

        // Step 6: Change the aspect ratio to 30 and save the new image
        barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 30;
        string file30 = Path.Combine(outputFolder, "DatabarAspectRatio30.png");
        barcodeGenerator.Save(file30, BarCodeImageFormat.Png);
        Console.WriteLine($"Saved barcode with aspect ratio 30 to {file30}");
    }
}
```

Запуск программы выводит в консоль сообщения, похожие на:

```
Saved barcode with aspect ratio 15 to GeneratedBarcodes/DatabarAspectRatio15.png
Saved barcode with aspect ratio 30 to GeneratedBarcodes/DatabarAspectRatio30.png
```

## Заключение

Теперь у вас есть **c# barcode generator**, который может создавать DataBar stacked Omni‑Directional символы, настраивать X‑dimension и экспортировать PNG‑файлы с пользовательскими aspect ratio. Та же схема работает для любой другой символьной системы штрих‑кодов, поддерживаемой Aspose.BarCode, что упрощает интеграцию создания штрих‑кодов в системы учёта, доставки или точек продаж.

Если вы хотите продолжить изучение, попробуйте:

* Генерацию QR‑code или символов PDF417 (`how to generate barcode` для мобильных приложений)  
* Экспорт в SVG для масштабируемой веб‑графики  
* Встраивание сгенерированных изображений непосредственно в PDF‑счета с помощью Aspose.PDF  

Экспериментируйте с различными значениями `AspectRatio`, размерами X‑dimension и форматами вывода, чтобы точно соответствовать

## Что изучать дальше?

Следующие руководства охватывают тесно связанные темы, построенные на техниках, продемонстрированных в этом руководстве. Каждый ресурс включает полные работающие примеры кода с пошаговыми объяснениями, чтобы помочь вам освоить дополнительные возможности API и исследовать альтернативные подходы к реализации в ваших проектах.

- [Как генерировать Aztec‑barcode с пользовательским aspect ratio с помощью Aspose.BarCode для .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)
- [Как настроить размер штрих‑кода – aspect ratio Codablock F с Aspose.BarCode для .NET](/barcode/english/net/codablock-f-encoding/codablock-f-aspect-ratio-customization/)
- [Как генерировать и настраивать высоту штрих‑кода One‑Dimensional Databar с помощью Aspose.BarCode для .NET](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-barcode-height-adjustment/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}