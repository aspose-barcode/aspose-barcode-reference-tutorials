---
category: general
date: 2026-08-09
description: Генерировать штрих‑код из текста в C# с помощью Aspose.BarCode. Узнайте,
  как создавать штрих‑коды, обрабатывать специальные символы и быстро создавать PDF417‑штрих‑коды
  в C#.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate barcode from text
- how to generate barcode
- barcode with special characters
- barcode encode types
- create pdf417 barcode c#
language: ru
lastmod: 2026-08-09
og_description: Генерировать штрих‑код из текста в C# с использованием Aspose.BarCode.
  Этот учебник показывает, как генерировать штрих‑код, поддерживать специальные символы
  и создавать PDF417‑штрих‑код в C# с полным кодом.
og_image_alt: Screenshot of a generated MicroPdf417 barcode saved as PNG
og_title: Создание штрих‑кода из текста в C# – быстрый пошаговый гид
schemas:
- author: Aspose
  dateModified: '2026-08-09'
  description: Generate barcode from text in C# with Aspose.BarCode. Learn how to
    generate barcode, handle special characters, and create PDF417 barcode C# quickly.
  headline: Generate barcode from text in C# – complete step‑by‑step guide
  type: TechArticle
tags:
- barcode
- C#
- PDF417
- Aspose
- encoding
title: Генерация штрих‑кода из текста в C# – полное пошаговое руководство
url: /ru/net/compact-pdf417-encoding/generate-barcode-from-text-in-c-complete-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Создание штрихкода из текста в C# – полное пошаговое руководство

Если вам нужно **generate barcode from text** в приложении .NET, это руководство проведёт вас через весь процесс. Вы увидите, как generate barcode, управлять специальными символами и создать реализацию PDF417 barcode C# , которая работает сразу из коробки.

Создание штрихкода из текста является распространённой задачей для систем учёта, платформ продажи билетов и документооборотов. К концу этого руководства у вас будет исполняемое консольное приложение C#, которое генерирует PNG‑изображение MicroPdf417 с помощью Aspose.BarCode. Внешние сервисы не требуются, а код обрабатывает Unicode‑символы, такие как “Å”, “©” и “é”.

## Требования

- .NET 6.0 SDK или новее (код также работает с .NET Core 3.1 и .NET Framework 4.7+)
- Visual Studio 2022 (или любой IDE, поддерживающий C#)
- **Aspose.BarCode for .NET** NuGet package  
  ```bash
  dotnet add package Aspose.BarCode
  ```
- Базовые знания синтаксиса C#

## Создание штрихкода из текста – настройка генератора

Первый шаг — создать экземпляр `BarcodeGenerator`, который знает, какой **barcode encode type** вам нужен. В этом руководстве мы используем `EncodeTypes.MicroPdf417`, который является компактным вариантом PDF417, подходящим для коротких строк данных.

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Step 1: Create a barcode generator for MicroPdf417 with the desired text
        // This demonstrates "generate barcode from text" with Unicode characters.
        BarcodeGenerator generator = new BarcodeGenerator(
            EncodeTypes.MicroPdf417,
            "Åspóse.Barcóde©"
        );

        // Continue with configuration (see next sections)
        ConfigureGenerator(generator);
        SaveBarcode(generator);
    }

    // Configuration is split into its own method for clarity.
    static void ConfigureGenerator(BarcodeGenerator generator)
    {
        // Step 2: Define the X dimension of the barcode modules (in pixels)
        // XDimension controls the width of the smallest bar; 2 px gives a clear image.
        generator.Parameters.Barcode.XDimension.Pixels = 2;

        // Step 3: Set the number of columns for the PDF417 layout.
        // Fewer columns produce a taller barcode; 4 columns works well for short strings.
        generator.Parameters.Barcode.Pdf417.Columns = 4;
    }

    static void SaveBarcode(BarcodeGenerator generator)
    {
        // Step 4: Save the generated barcode as a PNG image.
        // You can change BarCodeImageFormat to Jpeg, Gif, etc., if needed.
        string outputPath = Path.Combine(
            Environment.CurrentDirectory,
            "MicroPdf417.png"
        );
        generator.Save(outputPath, BarCodeImageFormat.Png);
        Console.WriteLine($"Barcode saved to: {outputPath}");
    }
}
```

**Почему это работает:**  
- `EncodeTypes.MicroPdf417` указывает библиотеке использовать семью PDF417, удовлетворяя требование **create pdf417 barcode c#**.  
- Конструктор получает исходный текст, что является сутью **generate barcode from text**.  
- Поддержка Unicode встроена, поэтому символы вроде “Å” и “©” кодируются правильно, решая задачу **barcode with special characters**.

## Как generate barcode со специальными символами

Когда ваши данные содержат символы, не входящие в ASCII, необходимо убедиться, что генератор использует кодировку UTF‑8. Aspose.BarCode автоматически определяет Unicode, но при возникновении проблем вы можете явно задать кодировку текста:

```csharp
generator.Parameters.Barcode.TextEncoding = Encoding.UTF8;
```

Добавление этой строки перед `ConfigureGenerator` гарантирует, что **barcode with special characters** отрисовывается корректно на любой платформе.

### Практический совет
Если вывод выглядит искажённым, проверьте, поддерживает ли шрифт, используемый рендерером штрихкода, необходимые глифы. Вы можете встроить пользовательский TrueType‑шрифт с помощью:

```csharp
generator.Parameters.Barcode.Font.FontFamily = "Arial Unicode MS";
```

## Типы кодирования штрихкода, которые вы можете выбрать

Aspose.BarCode поддерживает десятки **barcode encode types**, каждый из которых подходит для различных сценариев:

| Encode type                | Типичный сценарий использования                     |
|----------------------------|--------------------------------------|
| `EncodeTypes.Code128`      | Транспортные этикетки, учёт           |
| `EncodeTypes.QR`           | Мобильные платежи, URL-адреса                |
| `EncodeTypes.Pdf417`       | Водительские удостоверения, посадочные талоны   |
| `EncodeTypes.MicroPdf417`  | Небольшие объёмы данных, ограниченное пространство   |
| `EncodeTypes.DataMatrix`   | Маленькие предметы, высокая плотность данных        |

Изменить тип кодирования так же просто, как заменить значение enum в конструкторе:

```csharp
BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.QR, "https://example.com");
```

Эта гибкость позволяет отвечать на вопросы о **barcode encode types** не выходя из IDE.

## Создание PDF417 barcode C# – финальные шаги и проверка

После настройки генератора последняя часть **create pdf417 barcode c#** — сохранение изображения и подтверждение результата.

```csharp
// Save as PNG (lossless, ideal for further processing)
generator.Save("MicroPdf417.png", BarCodeImageFormat.Png);
```

Запустите программу (`dotnet run`), и вы должны увидеть сообщение в консоли, похожее на:

```
Barcode saved to: C:\YourProject\bin\Debug\net6.0\MicroPdf417.png
```

Откройте PNG‑файл; вы увидите чёткий MicroPdf417 barcode, который кодирует строку “Åspóse.Barcóde©”. Сканирование его мобильным сканером штрихкодов (например, ZXing) возвращает исходный текст, доказывая, что **generate barcode from text** работает даже со специальными символами.

### Пограничный случай: очень длинный текст

MicroPdf417 имеет максимальную ёмкость данных 1 KB. Если ваш ввод превышает этот предел, библиотека бросает `ArgumentException`. Чтобы обработать это корректно:

```csharp
try
{
    generator.Save("MicroPdf417.png", BarCodeImageFormat.Png);
}
catch (ArgumentException ex)
{
    Console.Error.WriteLine($"Data too long for MicroPdf417: {ex.Message}");
}
```

Для больших объёмов данных переключитесь на полный `EncodeTypes.Pdf417` или `EncodeTypes.DataMatrix`.

## Распространённые подводные камни и как их избежать

| Issue                               | Cause                                   | Fix |
|-------------------------------------|-----------------------------------------|-----|
| Штрихкод выглядит размытым              | XDimension слишком низкое (например, 1 px)         | Увеличьте `XDimension.Pixels` до 2‑3 px |
| Unicode‑символы становятся `?`      | Кодировка текста по умолчанию — ASCII          | Установите `TextEncoding = Encoding.UTF8` |
| Файл изображения не создан               | Каталог вывода не существует         | Вызовите `Directory.CreateDirectory` перед `Save` |
| Сканер не может прочитать штрихкод      | Слишком много столбцов для коротких данных          | Уменьшите `Pdf417.Columns` (например, 3‑4) |

## Полный исходный код (готов к копированию)

```csharp
using System;
using System.IO;
using System.Text;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Create the generator – this is the core of "generate barcode from text"
        BarcodeGenerator generator = new BarcodeGenerator(
            EncodeTypes.MicroPdf417,
            "Åspóse.Barcóde©"
        );

        // Ensure Unicode characters are handled correctly
        generator.Parameters.Barcode.TextEncoding = Encoding.UTF8;

        // Optional: set a font that contains the required glyphs
        generator.Parameters.Barcode.Font.FontFamily = "Arial Unicode MS";

        // Configure visual appearance
        generator.Parameters.Barcode.XDimension.Pixels = 2;
        generator.Parameters.Barcode.Pdf417.Columns = 4;

        // Prepare output directory
        string outputDir = Path.Combine(Environment.CurrentDirectory, "output");
        Directory.CreateDirectory(outputDir);
        string outputPath = Path.Combine(outputDir, "MicroPdf417.png");

        // Save the barcode image
        try
        {
            generator.Save(outputPath, BarCodeImageFormat.Png);
            Console.WriteLine($"Barcode saved to: {outputPath}");
        }
        catch (ArgumentException ex)
        {
            Console.Error.WriteLine($"Failed to generate barcode: {ex.Message}");
        }
    }
}
```

**Ожидаемый результат:** файл с именем `MicroPdf417.png`, расположенный в папке `output`, содержащий чёткий MicroPdf417 barcode, который кодирует исходную строку со специальными символами.

## Заключение

Теперь вы знаете, как **generate barcode from text** в C# с помощью Aspose.BarCode, как работать с **barcode with special characters**, и как **create pdf417 barcode c#** с полным контролем над параметрами кодирования. Регулируя **barcode encode types**, вы можете создавать QR‑коды, Code128, DataMatrix или любой другой поддерживаемый формат.

Далее изучите следующие темы, чтобы углубить свои знания о штрихкодах:

- **How to generate barcode** пакетно для тысяч записей (используйте `Parallel.ForEach` для ускорения)
- Настройка цветов и добавление логотипов внутрь штрихкода
- Интеграция генерации штрихкода в ASP.NET Core API для мгновенной доставки изображений
- Использование других библиотек, таких как ZXing.Net или IronBarcode, в качестве открытых альтернатив

Не стесняйтесь экспериментировать с различными размерами, настройками столбцов и типами кодирования. Приятного кодирования, и пусть ваши приложения сканируют безупречно!

## Что изучать дальше?

Следующие руководства охватывают тесно связанные темы, основанные на техниках, продемонстрированных в этом руководстве. Каждый ресурс включает полностью работающие примеры кода с пошаговыми объяснениями, чтобы помочь вам освоить дополнительные возможности API и изучить альтернативные подходы к реализации в ваших проектах.

- [Как создать штрихкод – компактный PDF417 с Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [Как сгенерировать штрихкод – конфигурация Code 39 с Aspose.BarCode](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-code-39-configuration/)
- [Как сгенерировать штрихкод – односторонние типы штрихкодов](/barcode/english/net/one-dimensional-barcode-types/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}