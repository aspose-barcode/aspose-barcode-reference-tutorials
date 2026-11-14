---
category: general
date: 2026-11-14
description: Узнайте, как быстро создать штрих‑код PDF417 на C#. Это руководство также
  показывает, как генерировать PDF417 и как настраивать параметры PDF417 для точного
  контроля.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create pdf417 barcode
- how to generate pdf417
- how to customize pdf417
language: ru
lastmod: 2026-11-14
og_description: Создайте штрих‑код PDF417 на C# с пошаговыми инструкциями. Узнайте,
  как генерировать PDF417 и как настраивать параметры PDF417 для точных результатов.
og_image_alt: Screenshot showing a generated PDF417 barcode created with C# code
og_title: Создание штрихкода PDF417 в C# — полное руководство с пользовательским макетом
schemas:
- author: Aspose
  dateModified: '2026-11-14'
  description: Learn how to create PDF417 barcode in C# quickly. This guide also shows
    how to generate PDF417 and how to customize PDF417 settings for precise control.
  headline: How to create PDF417 barcode with custom layout in C#
  type: TechArticle
- description: Learn how to create PDF417 barcode in C# quickly. This guide also shows
    how to generate PDF417 and how to customize PDF417 settings for precise control.
  name: How to create PDF417 barcode with custom layout in C#
  steps:
  - name: '**Check dimensions:** Ensure columns/rows stay within the allowed range.'
    text: '**Check dimensions:** Ensure columns/rows stay within the allowed range.'
  - name: '**Adjust error level:** Increase `ErrorLevel` for damaged media.'
    text: '**Adjust error level:** Increase `ErrorLevel` for damaged media.'
  - name: '**Review image quality:** Save with a higher DPI (`generator.Save(outputPath,
      BarCodeImageFormat.Png, 300)`) if you plan to print.'
    text: '**Review image quality:** Save with a higher DPI (`generator.Save(outputPath,
      BarCodeImageFormat.Png, 300)`) if you plan to print.'
  type: HowTo
tags:
- barcode
- pdf417
- C#
title: Как создать штрих‑код PDF417 с пользовательским макетом в C#
url: /ru/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-with-custom-layout-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Как создать штрих‑код PDF417 с пользовательским макетом на C#

Если вам нужно **создать pdf417 barcode** для системы билетов, бирки инвентаря или сканирования в мобильном приложении, этот учебник покажет полный процесс. Вы увидите, как быстро сгенерировать PDF417 и как настроить параметры PDF417, такие как столбцы и строки, чтобы штрих‑код соответствовал ограничениям вашего дизайна.

Генерация штрих‑кода не требует сложной графической библиотеки — достаточно Aspose.BarCode for .NET (или любого совместимого API). К концу этого руководства у вас будет готовый PNG‑файл, который можно вставлять в PDF, веб‑страницы или печатать напрямую из приложения.

## Требования

- .NET 6.0 или новее (код также работает с .NET Framework 4.7+)
- Aspose.BarCode for .NET (пакет NuGet `Aspose.BarCode`)
- Базовые знания C# и Visual Studio (или любой IDE)

> **Совет профессионала:** Если вы используете конвейер CI/CD, добавьте ссылку на пакет NuGet в файл проекта, чтобы сборки оставались воспроизводимыми.

## Шаг 1: Установить библиотеку штрих‑кодов

Откройте папку проекта в терминале и выполните:

```bash
dotnet add package Aspose.BarCode
```

Пакет содержит класс `BarcodeGenerator`, используемый во всём этом учебнике. Дополнительные нативные зависимости не требуются.

## Шаг 2: Создать базовый штрих‑код PDF417

Первая цель — **create pdf417 barcode** с настройками по умолчанию. Ниже представлена программа, которая настраивает генератор, кодирует пример строки и сохраняет результат как PNG‑изображение.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Pdf417Demo
{
    static void Main()
    {
        // Step 2.1: Initialise the generator for PDF417 with the desired text
        BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Sample text for PDF417");

        // Step 2.2: Save the barcode as PNG
        string outputPath = "Pdf417Default.png";
        generator.Save(outputPath, BarCodeImageFormat.Png);

        Console.WriteLine($"Barcode saved to {outputPath}");
    }
}
```

**Почему это работает:**  
`EncodeTypes.Pdf417` указывает библиотеке использовать символьную схему PDF417. Конструктор автоматически создаёт объект `Barcode` с параметрами столбцов/строк по умолчанию, которые гарантируют сканируемость в большинстве сценариев.

Запустите программу (`dotnet run`). Вы найдёте `Pdf417Default.png` в папке проекта. Открытие изображения покажет стандартный штрих‑код PDF417, готовый к сканированию.

![Create PDF417 barcode example](https://example.com/images/pdf417-default.png){:alt="Пример создания штрих‑кода PDF417 с отображением макета по умолчанию"}

## Шаг 3: Как сгенерировать PDF417 с пользовательскими размерами

Иногда фиксированный ярлык или UI‑компонент требуют определённого пространства для штрих‑кода. Здесь и пригодится **how to generate pdf417** с пользовательскими столбцами и строками.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Pdf417CustomDemo
{
    static void Main()
    {
        // Initialise generator with the same text
        BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Custom layout text");

        // ---- Customization begins here ----
        // Set the number of columns (2‑30). Fewer columns make the barcode taller.
        generator.Parameters.Barcode.Pdf417.Columns = 4;

        // Set the number of rows (1‑90). More rows make the barcode wider.
        generator.Parameters.Barcode.Pdf417.Rows = 9;
        // ------------------------------------

        // Save the customized barcode
        string outputPath = "Pdf417CustomLayout.png";
        generator.Save(outputPath, BarCodeImageFormat.Png);

        Console.WriteLine($"Custom barcode saved to {outputPath}");
    }
}
```

**Почему это может понадобиться:**  
- **Ограниченная ширина:** Уменьшение количества столбцов и увеличение строк создаёт более широкий, но более короткий штрих‑код, идеальный для узких этикеток.  
- **Ограниченная высота:** Увеличение столбцов и уменьшение строк даёт более высокий, узкий штрих‑код, полезный, когда есть вертикальное пространство.

И `Columns`, и `Rows` принимают только значения из указанных диапазонов (2‑30 для столбцов, 1‑90 для строк). Передача значения вне диапазона вызывает `ArgumentOutOfRangeException`, поэтому всегда проверяйте ввод пользователя, если предоставляете эти настройки в UI.

## Шаг 4: Как дополнительно настроить PDF417

Помимо столбцов и строк, символьная схема PDF417 предлагает множество дополнительных параметров:

| Свойство | Назначение | Типичные значения |
|----------|------------|-------------------|
| `ErrorLevel` | Управляет способностью к коррекции ошибок | 0‑8 (чем выше, тем надёжнее) |
| `MacroPdf417` | Включает macro PDF417 для многосегментных данных | `true`/`false` |
| `CompactPdf417` | Создаёт более компактный штрих‑код за счёт снижения коррекции ошибок | `true`/`false` |
| `SecurityLevel` | Добавляет проверочный цифр безопасности | 0‑2 |

Ниже быстрый пример, который также устанавливает максимальный уровень ошибок (8) для шумной среды:

```csharp
generator.Parameters.Barcode.Pdf417.ErrorLevel = 8;
generator.Parameters.Barcode.Pdf417.CompactPdf417 = true;
```

**Почему это важно:**  
Более высокий уровень коррекции ошибок позволяет сканерам восстанавливать данные, даже если часть штрих‑кода повреждена. Однако это также увеличивает размер штрих‑кода, поэтому балансируйте настройку в соответствии с вашими ограничениями макета.

## Шаг 5: Проверить работу штрих‑кода

После генерации PNG протестируйте его любой программой‑сканером штрих‑кодов (на большинстве смартфонов есть бесплатные считыватели PDF417). Если сканер возвращает исходный текст (`Custom layout text`), штрих‑код действителен.

Если возникли проблемы со сканированием:

1. **Проверьте размеры:** Убедитесь, что столбцы/строки находятся в допустимом диапазоне.  
2. **Отрегулируйте уровень ошибок:** Увеличьте `ErrorLevel` для повреждённых носителей.  
3. **Проверьте качество изображения:** Сохраните с более высоким DPI (`generator.Save(outputPath, BarCodeImageFormat.Png, 300)`) если планируете печать.

## Полный исходный код переиспользуемого помощника

Ниже компактный, переиспользуемый класс, который можно добавить в любой .NET‑проект. Он инкапсулирует **how to generate pdf417** и **how to customize pdf417** в одном методе.

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

public static class Pdf417Helper
{
    /// <summary>
    /// Creates a PDF417 barcode image with optional layout parameters.
    /// </summary>
    /// <param name="text">The data to encode.</param>
    /// <param name="outputPath">Full file path for the PNG output.</param>
    /// <param name="columns">Number of columns (2‑30). Pass null to use default.</param>
    /// <param name="rows">Number of rows (1‑90). Pass null to use default.</param>
    /// <param name="errorLevel">Error correction level (0‑8). Null = default.</param>
    public static void CreatePdf417(string text, string outputPath,
                                    int? columns = null,
                                    int? rows = null,
                                    int? errorLevel = null)
    {
        var generator = new BarcodeGenerator(EncodeTypes.Pdf417, text);

        // Apply optional customizations
        if (columns.HasValue) generator.Parameters.Barcode.Pdf417.Columns = columns.Value;
        if (rows.HasValue)    generator.Parameters.Barcode.Pdf417.Rows    = rows.Value;
        if (errorLevel.HasValue) generator.Parameters.Barcode.Pdf417.ErrorLevel = errorLevel.Value;

        // Save as high‑resolution PNG (300 DPI) for printing scenarios
        generator.Save(outputPath, BarCodeImageFormat.Png, 300);
    }
}
```

Вы можете вызвать этот помощник так:

```csharp
Pdf417Helper.CreatePdf417(
    text: "Order #12345",
    outputPath: "OrderBarcode.png",
    columns: 5,
    rows: 12,
    errorLevel: 6);
```

Метод скрывает повторяющийся шаблон, позволяя сосредоточиться на бизнес‑логике.

## Распространённые подводные камни и как их избежать

- **Значения вне диапазона:** Всегда проверяйте `columns` и `rows` перед их назначением.  
- **Неправильный формат изображения:** Некоторые старые сканеры принимают только BMP или JPEG. При необходимости используйте `BarCodeImageFormat.Bmp`.  
- **Низкое DPI для печати:** DPI по умолчанию — 96. Для печати высокого качества явно задайте более высокое DPI (например, 300) при вызове `Save`.  
- **Отсутствие поддержки шрифтов:** PDF417 кодирует бинарные данные, поэтому обычно не требуется указывать шрифт. Однако если вы накладываете текст на изображение, убедитесь, что шрифт установлен на целевой машине.

## Заключение

Теперь вы знаете, как **create pdf417 barcode** от начала до конца, как **generate pdf417** с пользовательскими настройками столбцов/строк и как **customize pdf417** для коррекции ошибок и компактности. Следуя шаблону переиспользуемого помощника, вы сможете генерировать штрих‑коды по запросу, адаптировать их под любые ограничения макета и гарантировать надёжное сканирование в продакшн‑среде.

**Следующие шаги**

- Исследуйте другие символьные схемы, такие как QR или Code128, используя тот же класс `BarcodeGenerator`.  
- Объедините вывод PNG с библиотекой генерации PDF (например, iText7), чтобы вставлять штрих‑коды в счета‑фактуры.  
- Поэкспериментируйте с `MacroPdf417` для многосегментной передачи данных — функция, полезная в логистике и транспортных приложениях.

Счастливого кодинга, и пусть ваши штрих‑коды всегда сканируются с первой попытки!

## Что вам следует изучить дальше?

Следующие учебники охватывают тесно связанные темы, которые развивают техники, продемонстрированные в этом руководстве. Каждый ресурс включает полностью работающие примеры кода с пошаговыми объяснениями, чтобы помочь вам освоить дополнительные возможности API и исследовать альтернативные подходы в собственных проектах.

- [How to generate PDF417 barcode in C# – step‑by‑step guide](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-step-by-step-guide/)
- [How to generate barcode and customize PDF417 barcode in C#](/barcode/english/net/compact-pdf417-encoding/how-to-generate-barcode-and-customize-pdf417-barcode-in-c/)
- [How to create PDF417 barcode and export PNG in C#](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-and-export-png-in-c/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}