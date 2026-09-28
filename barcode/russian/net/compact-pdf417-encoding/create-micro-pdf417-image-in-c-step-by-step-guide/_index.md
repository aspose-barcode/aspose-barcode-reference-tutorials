---
category: general
date: 2026-08-12
description: Создайте изображение micro PDF417 в C# быстро. Узнайте, как генерировать
  штрих‑код PDF417 в C# с полным кодом, параметрами и советами по устранению неполадок.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create micro PDF417 image
- how to generate PDF417 barcode C#
- barcode generator C#
- PDF417 column settings
- barcode image format PNG
language: ru
lastmod: 2026-08-12
og_description: Создайте изображение micro PDF417 на C# с помощью этого подробного
  руководства. Следуйте шагам, чтобы сгенерировать штрих‑код PDF417 на C# и настроить
  вывод.
og_image_alt: Screenshot of a generated micro PDF417 barcode saved as a PNG file
og_title: Создание микроснимка PDF417 в C# — полное руководство по программированию
schemas:
- author: Aspose
  dateModified: '2026-08-12'
  description: Create micro PDF417 image in C# quickly. Learn how to generate PDF417
    barcode C# with full code, options, and troubleshooting tips.
  headline: Create micro PDF417 image in C# – step‑by‑step guide
  type: TechArticle
tags:
- barcode
- PDF417
- C#
- imaging
title: Создание микро PDF417 изображения в C# — пошаговое руководство
url: /ru/net/compact-pdf417-encoding/create-micro-pdf417-image-in-c-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Создание изображения micro PDF417 в C# – пошаговое руководство

Если вам нужно **создать изображение micro PDF417** в .NET‑приложении, этот учебник покажет, как сделать это несколькими строками C#. Вы увидите точный код для генерации штрих‑кода PDF417 в C# и как настроить размер, количество столбцов и формат файла.

Руководство охватывает всё: от установки необходимой библиотеки до работы с Unicode‑символами и сохранения результата в файл PNG. К концу вы получите переиспользуемый метод, который генерирует высококачественные штрих‑коды micro PDF417 для биркок инвентаря, билетов или мобильных сканирующих решений.

## Предварительные требования

Перед началом убедитесь, что у вас есть:

* .NET 6.0 SDK или новее (код также работает с .NET Core и .NET Framework)
* Visual Studio 2022 или любой IDE, поддерживающий C#
* Пакет NuGet **Aspose.BarCode** (или любая совместимая библиотека штрих‑кодов, поддерживающая `EncodeTypes.MicroPdf417`)

Вы можете добавить пакет с помощью .NET CLI:

```bash
dotnet add package Aspose.BarCode
```

> **Совет:** Используйте последнюю стабильную версию библиотеки, чтобы получить исправления ошибок и новые возможности кодирования.

## Шаг 1: Создание экземпляра генератора штрих‑кода

Первый шаг – создать объект `BarcodeGenerator` с типом кодирования `MicroPdf417` и данными, которые нужно закодировать. Библиотека автоматически обрабатывает UTF‑8 символы, поэтому вы можете включать буквы с диакритическими знаками или специальные символы.

```csharp
using Aspose.BarCode.Generation;

// Data to encode – Unicode characters are supported out of the box
string data = "Åspóse.Barcóde©";

// Create a MicroPdf417 barcode generator
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.MicroPdf417, data);
```

**Почему это важно:** `EncodeTypes.MicroPdf417` создаёт компактный 2‑D штрих‑код, который помещается на небольших этикетках, сохраняя возможности коррекции ошибок. Передача данных при конструировании гарантирует раннюю проверку содержимого генератором.

## Шаг 2: Настройка X‑размера (ширина модуля)

X‑размер определяет, насколько широким будет каждый модуль штрих‑кода (пиксель). Меньшее значение даёт более плотное изображение, но может стать нечитаемым на сканерах с низким разрешением. Хорошей отправной точкой является 2 пикселя.

```csharp
// Set module width to 2 pixels (adjustable per printer DPI)
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

**Пограничный случай:** Если вы нацелены на принтер с высоким разрешением (≥300 dpi), можно увеличить значение пикселя до 3‑4, чтобы улучшить читаемость без увеличения общего размера изображения.

## Шаг 3: Выбор количества столбцов

Micro PDF417 позволяет задать количество столбцов в матрице (1‑4). Больше столбцов делает штрих‑код шире, но короче, что может быть полезно при ограниченном вертикальном пространстве.

```csharp
// Use 4 columns to keep the barcode compact vertically
barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 4;
```

**Когда менять:**  
* Используйте **1‑2 столбца** для узких этикеток (например, браслетных меток).  
* Используйте **3‑4 столбца**, когда есть больше горизонтального пространства и нужен более короткий штрих‑код.

## Шаг 4: Установка пути к файлу вывода

Определите, куда будет сохранено сгенерированное изображение. Используйте `Path.Combine` для построения платформенно‑независимого пути.

```csharp
using System.IO;

string outputDirectory = @"C:\Barcodes";
Directory.CreateDirectory(outputDirectory); // Ensure the folder exists
string outputPath = Path.Combine(outputDirectory, "MicroPdf417.png");
```

**Подсказка:** Храните штрих‑коды в отдельной папке, чтобы проект оставался упорядоченным и упростить последующую пакетную обработку.

## Шаг 5: Сохранение штрих‑кода в файл PNG

Наконец, запишите штрих‑код на диск. PNG сохраняет без потерь, что важно для надёжного сканирования.

```csharp
// Save the barcode image in PNG format
barcodeGenerator.Save(outputPath, BarCodeImageFormat.Png);
```

Если нужен другой формат (например, JPEG для веб‑доставки), замените `BarCodeImageFormat.Png` на `BarCodeImageFormat.Jpeg`.

### Ожидаемый результат

После выполнения кода вы найдёте `MicroPdf417.png` в `C:\Barcodes`. Открытие файла покажет чёткий прямоугольный штрих‑код, кодирующий строку **Åspóse.Barcóde©**. Сканирование изображения считывателем PDF417 вернёт исходный текст, подтверждая успешность процесса **создания изображения micro PDF417**.

## Полный переиспользуемый метод

Ниже представлен один метод, который можно вставить в любой класс C#. Он инкапсулирует описанные выше шаги и позволяет передавать пользовательские данные, количество столбцов и место сохранения.

```csharp
using Aspose.BarCode.Generation;
using System.IO;

public static class BarcodeHelper
{
    /// <summary>
    /// Generates a micro PDF417 barcode image.
    /// </summary>
    /// <param name="data">Text to encode (Unicode supported).</param>
    /// <param name="columns">Number of columns (1‑4). Default is 4.</param>
    /// <param name="pixelWidth">Module width in pixels. Default is 2.</param>
    /// <param name="outputPath">Full file path, including file name and extension.</param>
    public static void CreateMicroPdf417Image(
        string data,
        int columns = 4,
        int pixelWidth = 2,
        string outputPath = "MicroPdf417.png")
    {
        // Validate column range
        if (columns < 1 || columns > 4)
            throw new ArgumentOutOfRangeException(nameof(columns), "Columns must be between 1 and 4.");

        // Initialize generator
        BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MicroPdf417, data);

        // Apply settings
        generator.Parameters.Barcode.XDimension.Pixels = pixelWidth;
        generator.Parameters.Barcode.Pdf417.Columns = columns;

        // Ensure directory exists
        string directory = Path.GetDirectoryName(outputPath);
        if (!string.IsNullOrEmpty(directory))
            Directory.CreateDirectory(directory);

        // Save as PNG (change format if needed)
        generator.Save(outputPath, BarCodeImageFormat.Png);
    }
}
```

**Как использовать метод:**

```csharp
BarcodeHelper.CreateMicroPdf417Image(
    data: "Åspóse.Barcóde©",
    columns: 4,
    pixelWidth: 2,
    outputPath: @"C:\Barcodes\MyMicroPdf417.png");
```

Эта инкапсулированная версия упрощает **генерацию PDF417 штрих‑кода в C#** в разных проектах.

## Распространённые проблемы и их решение

| Проблема | Причина | Решение |
|----------|---------|----------|
| Штрих‑код нечитаем сканером | X‑размер слишком мал для DPI принтера | Увеличьте `XDimension.Pixels` до 3‑4 для принтеров с высоким разрешением |
| Текст обрезан | Ввод превышает ёмкость Micro PDF417 (≈ 150 символов) | Используйте обычный PDF417 (`EncodeTypes.Pdf417`) для больших объёмов данных |
| Unicode‑символы отображаются как � | Версия библиотеки не поддерживает UTF‑8 | Обновите до последней версии пакета Aspose.BarCode |
| Файл не создан | Отсутствует каталог вывода или нет прав | Вызовите `Directory.CreateDirectory` перед сохранением и убедитесь в наличии прав записи |

## Расширение примера

* **Изменить формат изображения:** Замените `BarCodeImageFormat.Png` на `BarCodeImageFormat.Jpeg` или `BarCodeImageFormat.Bmp`.
* **Добавить отступ:** `generator.Parameters.Barcode.Margins.All = 5;` добавляет 5‑пиксельную белую границу.
* **Применить цвет:** `generator.Parameters.Barcode.ForeColor = System.Drawing.Color.Blue;` меняет цвет переднего плана штрих‑кода.

Эти расширения позволяют точно настроить процесс **создания изображения micro PDF417** под брендинг или специфические условия сканирования.

## Заключение

Теперь вы знаете, как **создать изображение micro PDF417** в C# от начала до конца, включая кодирование данных, ширину модуля, выбор столбцов и вывод в файл. Переиспользуемый метод демонстрирует лучшую практику для **генерации PDF417 штрих‑кода в C#**, учитывая пограничные случаи и предлагая точки настройки для реальных проектов.

Далее изучайте связанные темы, такие как **генерация стандартных штрих‑кодов PDF417**, **встраивание штрих‑кодов в PDF‑отчёты** или **оптимизация читаемости штрих‑кода для мобильных камер**. Экспериментируйте с разным количеством столбцов и шириной пикселей, чтобы найти идеальный баланс для размера этикетки и возможностей сканера. Приятного кодинга!

## Что изучать дальше?

Следующие учебники охватывают тесно связанные темы, построенные на техниках, продемонстрированных в этом руководстве. Каждый ресурс включает полностью работающие примеры кода с пошаговыми объяснениями, помогающими освоить дополнительные возможности API и исследовать альтернативные подходы к реализации в ваших проектах.

- [Как создать штрих‑код – Compact PDF417 с Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [Как генерировать штрих‑коды PDF417 – Compact PDF417 Encoding](/barcode/english/net/compact-pdf417-encoding/)
- [Создание изображения штрих‑кода C# – пример GS1 DataMatrix](/barcode/english/net/gs1-barcode-encoding/gs1-datamatrix-example/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}