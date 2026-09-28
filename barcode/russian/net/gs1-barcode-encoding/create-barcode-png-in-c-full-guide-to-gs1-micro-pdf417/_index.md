---
category: general
date: 2026-08-12
description: Создавайте PNG‑изображения штрихкодов на C# быстро с Aspose.BarCode.
  Узнайте, как генерировать штрихкод PDF417 на C# и освоить использование генератора
  штрихкодов в одном учебнике.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode PNG
- generate PDF417 barcode C#
- barcode generator usage
- GS1 Micro PDF417 example
- Aspose.BarCode C#
language: ru
lastmod: 2026-08-12
og_description: Создайте PNG‑изображение штрих‑кода в C# с помощью Aspose.BarCode.
  Этот учебник покажет, как генерировать штрих‑код PDF417 в C# и эффективно использовать
  генератор штрих‑кодов.
og_image_alt: create barcode PNG example showing a GS1 Micro PDF417 code
og_title: Создание PNG‑штрихкода в C# – пошаговое руководство
schemas:
- author: Aspose
  dateModified: '2026-08-12'
  description: Create barcode PNG in C# quickly with Aspose.BarCode. Learn how to
    generate PDF417 barcode C# and master barcode generator usage in a single tutorial.
  headline: Create barcode PNG in C# – full guide to GS1 Micro PDF417
  type: TechArticle
- description: Create barcode PNG in C# quickly with Aspose.BarCode. Learn how to
    generate PDF417 barcode C# and master barcode generator usage in a single tutorial.
  name: Create barcode PNG in C# – full guide to GS1 Micro PDF417
  steps:
  - name: Why each line matters
    text: '| Line | Reason | |------|--------| | `EncodeTypes.Gs1MicroPdf417` | Selects
      the specific PDF417 variant required for GS1 applications. | | Data string `"(01)12345678901231(10)ABC123"`
      | Demonstrates the GS1 AI syntax for a GTIN (01) and a lot number (10). | |
      `XDimension.Pixels = 2` | Controls the '
  - name: Expected visual result
    text: The PNG contains a rectangular barcode with evenly spaced black modules.
      Scanning it with a GS1‑compatible scanner returns the string `(01)12345678901231(10)ABC123`,
      confirming that **generate PDF417 barcode C#** succeeded.
  - name: Changing the symbology
    text: 'If you need a regular PDF417 instead of the micro version, replace the
      encode type:'
  - name: Adjusting image format
    text: 'Aspose.BarCode supports many formats. To create a JPEG instead:'
  - name: Saving to a stream (useful for web APIs)
    text: '```csharp using (var ms = new MemoryStream()) { generator.Save(ms, BarCodeImageFormat.Png);
      // ms.ToArray() now contains the PNG bytes – return them from an API endpoint.
      } ```'
  - name: What’s next?
    text: '* Explore **barcode reader integration** to verify generated images automatically.
      * Experiment with **custom colors** and **logo embedding** for brand‑aware barcodes.
      * Review the Aspose.BarCode documentation for advanced error‑correction settings
      and multi‑page PDF417 generation.'
  type: HowTo
tags:
- barcode
- C#
- image generation
title: Создание PNG‑штрихкода в C# – полное руководство по GS1 Micro PDF417
url: /ru/net/gs1-barcode-encoding/create-barcode-png-in-c-full-guide-to-gs1-micro-pdf417/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Создание PNG штрих‑кода в C# – полное руководство по GS1 Micro PDF417

Если вам нужно **создать PNG штрих‑кода** в приложении .NET, это руководство покажет, как это сделать. Вы научитесь генерировать штрих‑код PDF417 в C# и увидите шаблоны **использования генератора штрих‑кодов**, применимые в продакшене.

Создание изображения штрих‑кода — распространённая задача для систем учёта, транспортных этикеток и платформ билетирования. К концу этого урока у вас будет автономная консольная программа, которая сохраняет PNG‑файл с штрих‑кодом GS1 Micro PDF417, готовый к дальнейшей обработке.

## Требования

Прежде чем начать, убедитесь, что у вас есть:

* .NET 6.0 SDK или более новая версия (код также работает с .NET Framework 4.7.2+).
* Последняя версия NuGet‑пакета **Aspose.BarCode for .NET**. Установите его командой  
  `dotnet add package Aspose.BarCode`.
* Базовые знания о проектах консольных приложений C#.
* Права записи в папку, куда будет сохраняться PNG.

Эти требования делают пример лёгким, но при этом отражают реальную настройку.

## Шаг 1: Создание проекта C#

Создайте новый консольный проект и добавьте ссылку на Aspose.BarCode:

```bash
dotnet new console -n BarcodePngDemo
cd BarcodePngDemo
dotnet add package Aspose.BarCode
```

CLI `dotnet` создаёт файл `Program.cs` и восстанавливает NuGet‑пакет. Этот шаг необходим для **использования генератора штрих‑кодов**, поскольку библиотека содержит класс `BarcodeGenerator`, которым мы будем пользоваться.

## Шаг 2: Написание полного кода генерации штрих‑кода

Замените содержимое `Program.cs` следующим кодом. Он включает каждую строку, необходимую для **создания PNG штрих‑кода** от начала до конца.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace BarcodePngDemo
{
    class Program
    {
        static void Main(string[] args)
        {
            // -------------------------------------------------
            // 1️⃣ Create a BarcodeGenerator for GS1 Micro PDF417
            // -------------------------------------------------
            // EncodeTypes.Gs1MicroPdf417 tells Aspose.BarCode to use the
            // GS1 Micro PDF417 symbology. The data string follows the
            // Application Identifier (AI) format required by GS1.
            var generator = new BarcodeGenerator(
                EncodeTypes.Gs1MicroPdf417,
                "(01)12345678901231(10)ABC123");

            // -------------------------------------------------
            // 2️⃣ Adjust the X‑dimension (module width)
            // -------------------------------------------------
            // XDimension controls the physical size of each barcode module.
            // Lower values produce a smaller image; higher values increase
            // readability on low‑resolution scanners.
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // -------------------------------------------------
            // 3️⃣ (Optional) Set image resolution and background
            // -------------------------------------------------
            // Higher DPI yields a sharper PNG, useful when the image
            // will be printed. BackgroundColor can be set to Transparent.
            generator.Parameters.ImageResolution = 300;      // DPI
            generator.Parameters.Barcode.BackgroundColor = System.Drawing.Color.Transparent;

            // -------------------------------------------------
            // 4️⃣ Save the barcode as a PNG file
            // -------------------------------------------------
            // The Save method writes the image to disk. You can also
            // choose other formats such as Jpeg, Bmp, or Gif.
            string outputPath = "output.png";
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"✅ Barcode PNG created at: {outputPath}");
        }
    }
}
```

### Почему важна каждая строка

| Строка | Причина |
|------|--------|
| `EncodeTypes.Gs1MicroPdf417` | Выбирает конкретный вариант PDF417, требуемый для GS1‑приложений. |
| Строка данных `"(01)12345678901231(10)ABC123"` | Демонстрирует синтаксис GS1 AI для GTIN (01) и номера партии (10). |
| `XDimension.Pixels = 2` | Управляет физическим размером штрих‑кода; обычное значение по умолчанию для экранного отображения. |
| `ImageResolution = 300` | Увеличивает DPI, обеспечивая чёткость PNG при печати. |
| `BackgroundColor = Transparent` | Делает PNG пригодным для наложения в пользовательском интерфейсе. |
| `Save(..., BarCodeImageFormat.Png)` | Сохраняет штрих‑код в формате PNG, что соответствует цели **создать PNG штрих‑кода**. |

## Шаг 3: Запуск программы и проверка результата

Запустите консольное приложение:

```bash
dotnet run
```

Вы увидите сообщение‑подтверждение и найдёте файл `output.png` в папке проекта. Открыв его, вы увидите штрих‑код GS1 Micro PDF417, кодирующий примерные данные.

![create barcode PNG example](barcode-example.png)

*Alt text: пример создания PNG штрих‑кода, показывающий код GS1 Micro PDF417.*

### Ожидаемый визуальный результат

PNG содержит прямоугольный штрих‑код с равномерно расположенными чёрными модулями. Сканирование его совместимым с GS1 сканером возвращает строку `(01)12345678901231(10)ABC123`, подтверждая, что **генерация PDF417 штрих‑кода C#** прошла успешно.

## Шаг 4: Исследование распространённых вариантов

### Смена символьного набора

Если нужен обычный PDF417 вместо микроварианта, замените тип кодирования:

```csharp
var generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Your data here");
```

### Изменение формата изображения

Aspose.BarCode поддерживает множество форматов. Чтобы создать JPEG, используйте:

```csharp
generator.Save("output.jpg", BarCodeImageFormat.Jpeg);
```

### Сохранение в поток (полезно для веб‑API)

```csharp
using (var ms = new MemoryStream())
{
    generator.Save(ms, BarCodeImageFormat.Png);
    // ms.ToArray() now contains the PNG bytes – return them from an API endpoint.
}
```

Эти фрагменты показывают гибкое **использование генератора штрих‑кодов** за пределами простого сохранения в файл.

## Полезные советы и подводные камни

* **Проверяйте длину данных** – у GS1 Micro PDF417 есть максимальная ёмкость; превышение приводит к исключению. Используйте `generator.Parameters.Barcode.IsValidData(data)` для предварительной проверки.
* **Не используйте слишком маленькие значения XDimension** – значения ниже 1 пикселя могут сделать штрих‑код нечитаемым на устройствах с низким разрешением.
* **Устанавливайте `QuietZone`**, если встраиваете PNG в более крупную графику; стандартная зона тишины гарантирует, что сканеры найдут стартовые/концевые шаблоны.
* **Потокобезопасность** – экземпляры `BarcodeGenerator` не являются потокобезопасными. Создавайте новый генератор для каждого запроса в веб‑службе.

## Заключение

Теперь вы знаете, как **создавать PNG штрих‑коды** в C# с помощью Aspose.BarCode, как **генерировать PDF417 штрих‑код C#** с вариантом GS1 Micro и какие шаблоны необходимы для эффективного **использования генератора штрих‑кодов**. Полный, готовый к запуску пример можно добавить в любой .NET‑проект, а затем расширять другими символьными наборами, форматами изображений или потоковыми выводами.

### Что дальше?

* Изучите **интеграцию считывателя штрих‑кодов** для автоматической проверки сгенерированных изображений.  
* Поэкспериментируйте с **пользовательскими цветами** и **встраиванием логотипа** для брендированных штрих‑кодов.  
* Ознакомьтесь с документацией Aspose.BarCode для продвинутых настроек коррекции ошибок и генерации многостраничных PDF417.

Счастливого кодинга, и пусть ваши приложения «говорят» на языке машин с чёткими, надёжными PNG штрих‑кодами!

## Что стоит изучить дальше?

Следующие руководства охватывают тесно связанные темы, расширяющие техники, продемонстрированные в этом руководстве. Каждый ресурс содержит полностью работающие примеры кода с пошаговыми объяснениями, помогающими освоить дополнительные возможности API и исследовать альтернативные подходы в ваших проектах.

- [How to Create Barcode – Compact PDF417 with Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [How to Save PNG using DataMatrix C40 with Aspose.BarCode](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-c40/)
- [How to Generate Barcode – Code 39 Configuration with Aspose.BarCode](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-code-39-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}