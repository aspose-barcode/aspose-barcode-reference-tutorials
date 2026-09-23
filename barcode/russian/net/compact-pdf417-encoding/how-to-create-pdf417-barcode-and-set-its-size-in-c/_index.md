---
category: general
date: 2026-09-22
description: Узнайте, как создать штрих‑код PDF417 в C#, установить размер штрих‑кода
  и сгенерировать файлы изображений штрих‑кода с понятными пошаговыми примерами кода.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create PDF417 barcode
- how to create PDF417
- set barcode size
- create barcode image c#
language: ru
lastmod: 2026-09-22
og_description: Создайте штрих‑код PDF417 на C# быстро. Этот учебник показывает, как
  задать размер штрих‑кода, включить компактный режим и выводить PNG‑изображения для
  любого проекта .NET.
og_image_alt: Screenshot of a generated PDF417 barcode image created with C# code
og_title: Создание штрихкода PDF417 на C# – пошаговое руководство
schemas:
- author: Aspose
  dateModified: '2026-09-22'
  description: Learn how to create PDF417 barcode in C#, set barcode size, and generate
    barcode image files with clear step‑by‑step code examples.
  headline: How to create PDF417 barcode and set its size in C#
  type: TechArticle
tags:
- PDF417
- C#
- Barcode
- Imaging
title: Как создать штрих‑код PDF417 и задать его размер в C#
url: /ru/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-and-set-its-size-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Как создать штрих‑код PDF417 и задать его размер в C#

Если вам нужно **создать штрих‑код PDF417** в C#, это руководство покажет, как сгенерировать код, управлять его размерами и сохранить результат в виде изображения. Независимо от того, разрабатываете ли вы систему билетов, этикетку для логистики или защищённые учётные данные, освоение формата PDF417 позволяет кодировать большие объёмы данных в компактной визуальной форме.

В этом уроке вы научитесь:

* **Создавать штрих‑код PDF417** с помощью библиотеки Aspose.BarCode (или любой совместимой).  
* **Задавать размер штрих‑кода** путём настройки X‑dimension и количества колонок.  
* Генерировать **изображение штрих‑кода в C#** в форматах PNG, JPEG или BMP.  

Пример использует бесплатную Community‑edition библиотеки Aspose.BarCode для .NET, но те же принципы применимы к другим библиотекам, предоставляющим аналогичные свойства.

## Предварительные требования

Прежде чем начать, убедитесь, что у вас есть:

* .NET 6.0 SDK или более новая версия.  
* IDE для C# (Visual Studio, Visual Studio Code, Rider и т.д.).  
* NuGet‑пакет `Aspose.BarCode` (`dotnet add package Aspose.BarCode`).  

Дополнительная настройка не требуется; библиотека работает в Windows, Linux и macOS.

## Шаг 1: Создать базовый штрих‑код PDF417 и задать его размер

Первым шагом создаём объект `BarcodeGenerator` с перечислением `EncodeTypes.Pdf417` и передаём текст для кодирования. Затем настраиваем **X‑dimension** (ширина модуля) и количество **columns**, чтобы контролировать общий размер.

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;

// Define the text that the barcode will represent.
string data = "Sample text for PDF417 barcode";

// Create a basic PDF417 barcode generator.
var basicPdf417 = new BarcodeGenerator(EncodeTypes.Pdf417, data);

// Set the module width to 2 pixels (controls bar thickness).
basicPdf417.Parameters.Barcode.XDimension.Pixels = 2;

// Set the column count; 3 columns yields a compact visual but still readable.
basicPdf417.Parameters.Barcode.Pdf417.Columns = 3;

// Save the barcode as a PNG image.
string basicPath = Path.Combine("YOUR_DIRECTORY", "Pdf417Basic.png");
basicPdf417.Save(basicPath, BarCodeImageFormat.Png);
```

**Почему эти настройки важны**

* `XDimension.Pixels` определяет минимальную ширину полосы. Меньшие значения делают штрих‑код плотнее, большие – повышают читаемость на сканерах с низким разрешением.  
* `Pdf417.Columns` влияет на соотношение сторон кода. Меньшее количество колонок делает штрих‑код выше; больше колонок – шире. Регулировка колонок – основной способ **задать размер штрих‑кода** без изменения закодированных данных.

После выполнения кода вы найдёте файл `Pdf417Basic.png` в указанной папке. Изображение выглядит примерно так:

<img src="images/pdf417-basic.png" alt="create PDF417 barcode example showing basic barcode layout">

## Шаг 2: Создать компактный штрих‑код PDF417 (режим truncate) того же размера

Иногда требуется более короткий код для ограниченного пространства. PDF417 поддерживает режим *truncate* (компактный), который убирает стоп‑шаблон и уменьшает общую высоту. Свойство `Truncate` переключает это поведение.

```csharp
// Reuse the same data string.
var compactPdf417 = new BarcodeGenerator(EncodeTypes.Pdf417, data);

// Keep the same module width and column count for a fair size comparison.
compactPdf417.Parameters.Barcode.XDimension.Pixels = 2;
compactPdf417.Parameters.Barcode.Pdf417.Columns = 3;

// Enable compact (truncate) mode – this removes the stop pattern.
compactPdf417.Parameters.Barcode.Pdf417.Truncate = true;

// Save the compact version.
string compactPath = Path.Combine("YOUR_DIRECTORY", "CompactPdf417.png");
compactPdf417.Save(compactPath, BarCodeImageFormat.Png);
```

**Что меняется при `Truncate = true`?**

* Штрих‑код становится примерно на 15‑20 % короче по вертикали, что удобно для небольших этикеток или мобильных экранов.  
* Данные остаются полностью восстанавливаемыми; большинство современных сканеров автоматически распознают режим truncate.

Полученный файл `CompactPdf417.png` выглядит как более тонкая версия базового штрих‑кода.

## Шаг 3: Создать Micro PDF417, настроить колонки и сохранить его

Micro PDF417 – более новая, высокоплотная версия, предназначенная для очень маленьких областей (например, удостоверений личности). Поддерживает только 1‑4 колонки, а библиотека использует тот же параметр `XDimension` для управления размером.

```csharp
// Create a Micro PDF417 generator.
var microPdf417 = new BarcodeGenerator(EncodeTypes.MicroPdf417, data);

// Set module width – 2 pixels works well for most printers.
microPdf417.Parameters.Barcode.XDimension.Pixels = 2;

// Micro PDF417 allows only 1 to 4 columns; choose 4 for a more square shape.
microPdf417.Parameters.Barcode.Pdf417.Columns = 4;

// Save the micro barcode.
string microPath = Path.Combine("YOUR_DIRECTORY", "MicroPdf417.png");
microPdf417.Save(microPath, BarCodeImageFormat.Png);
```

**Ключевые моменты для Micro PDF417**

* Перечисление `EncodeTypes.MicroPdf417` автоматически выбирает микровариант.  
* Поскольку символ более плотный, может потребоваться принтер с более высоким DPI (300 dpi и выше), чтобы штрих‑код оставался читаемым.  
* Регулировка количества колонок – единственный доступный «регулятор» размера; библиотека по‑прежнему учитывает `XDimension`.

## Как задать размер штрих‑кода для разных форматов вывода

В примерах выше используется PNG, но тот же метод `Save` работает с JPEG, BMP или TIFF. Если нужен конкретный размер изображения (например, 300 × 150 px), комбинируйте `XDimension` с `ResolutionX`/ `ResolutionY`:

```csharp
basicPdf417.Parameters.ImageResolution = 300; // DPI
basicPdf417.Parameters.Barcode.XDimension.Pixels = 3; // larger modules for higher DPI
basicPdf417.Save("Pdf417HighRes.jpg", BarCodeImageFormat.Jpeg);
```

Увеличение `ImageResolution` при масштабировании `XDimension` сохраняет визуальное качество при печати с высоким разрешением.

## Распространённые подводные камни и профессиональные советы

| Проблема | Почему возникает | Решение |
|----------|------------------|---------|
| Штрих‑код выглядит размытым на экране | Низкое DPI в сочетании с маленьким `XDimension` | Увеличьте `ImageResolution` и/или `XDimension.Pixels` |
| Сканер не читает режим truncate | Устаревшее прошивка сканера не поддерживает его | Используйте полный (не усечённый) режим для старого оборудования |
| Micro PDF417 нечитаем | Печать при < 300 dpi или недостаточный контраст | Печатайте на матовой бумаге при 300 dpi и выше, обеспечьте темный фон |
| Файл вывода повреждён | Нет прав записи в целевую папку | Проверьте, что `YOUR_DIRECTORY` существует и доступен для записи |

**Совет профессионала:** При необходимости без потерь качества сохраняйте штрих‑код в PNG, особенно если планируется дальнейшая обработка (например, встраивание в PDF). PNG сохраняет точные пиксельные значения, тогда как JPEG вводит артефакты сжатия, которые могут ухудшить читаемость кода.

## Полный, готовый к запуску пример

Ниже представлено полное консольное приложение, демонстрирующее все три типа штрих‑кодов за один запуск. Скопируйте код в новый .NET‑проект консоли и выполните его.

```csharp
using System;
using System.IO;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // The text to encode – change this to whatever data you need.
        const string data = "Sample text for PDF417 barcode";

        // Directory where images will be saved.
        string outputDir = Path.Combine(Environment.CurrentDirectory, "Barcodes");
        Directory.CreateDirectory(outputDir);

        // ---------- Basic PDF417 ----------
        var basicPdf417 = new BarcodeGenerator(EncodeTypes.Pdf417, data);
        basicPdf417.Parameters.Barcode.XDimension.Pixels = 2;
        basicPdf417.Parameters.Barcode.Pdf417.Columns = 3;
        string basicPath = Path.Combine(outputDir, "Pdf417Basic.png");
        basicPdf417.Save(basicPath, BarCodeImageFormat.Png);
        Console.WriteLine($"Basic PDF417 saved to {basicPath}");

        // ---------- Compact (Truncate) PDF417 ----------
        var compactPdf417 = new BarcodeGenerator(EncodeTypes.Pdf417, data);
        compactPdf417.Parameters.Barcode.XDimension.Pixels = 2;
        compactPdf417.Parameters.Barcode.Pdf417.Columns = 3;
        compactPdf417.Parameters.Barcode.Pdf417.Truncate = true;
        string compactPath = Path.Combine(outputDir, "CompactPdf417.png");
        compactPdf417.Save(compactPath, BarCodeImageFormat.Png);
        Console.WriteLine($"Compact PDF417 saved to {compactPath}");

        // ---------- Micro PDF417 ----------
        var microPdf417 = new BarcodeGenerator(EncodeTypes.MicroPdf417, data);
        microPdf417.Parameters.Barcode.XDimension.Pixels = 2;
        microPdf417.Parameters.Barcode.Pdf417.Columns = 4; // 1‑4 allowed
        string microPath = Path.Combine(outputDir, "MicroPdf417.png");
        microPdf417.Save(microPath, BarCodeImageFormat.Png);
        Console.WriteLine($"Micro PDF417 saved to {microPath}");
    }
}
```

**Ожидаемый результат**

Запуск программы создаст три PNG‑файла в папке `Barcodes`:

* `Pdf417Basic.png` – стандартный штрих‑код PDF417 с тремя колонками.  
* `CompactPdf417.png` – те же данные в режиме truncate (компактный), немного короче.  
* `MicroPdf417.png` – высокоплотный вариант Micro PDF417 с четырьмя колонками.

Откройте любое изображение в просмотрщике; вы увидите характерный «слоистый» вид.

## Что изучать дальше?

Следующие руководства охватывают близкие темы, расширяющие техники, продемонстрированные в этом руководстве. Каждый ресурс содержит полностью рабочие примеры кода с пошаговыми объяснениями, помогающими освоить дополнительные возможности API и исследовать альтернативные подходы в ваших проектах.

- [Как создать штрих‑код – Compact PDF417 с Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [Как задать уровень ошибки в штрих‑коде PDF417 – Полное руководство](/barcode/english/net/compact-pdf417-encoding/how-to-set-error-level-in-pdf417-barcode-complete-guide/)
- [Создание метаданных штрих‑кода PDF417 в C# – Полное пошаговое руководство](/barcode/english/net/compact-pdf417-encoding/create-pdf417-barcode-metadata-in-c-complete-step-by-step-gu/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}