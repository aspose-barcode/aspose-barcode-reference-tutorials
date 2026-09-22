---
category: general
date: 2026-08-03
description: Создайте штрих‑код PDF417 на C# быстро. Узнайте, как генерировать штрих‑код
  PDF417 и как сохранять изображение штрих‑кода в формате PNG с помощью Aspose.Barcode.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create pdf417 barcode
- how to generate pdf417 barcode
- how to save barcode image
language: ru
lastmod: 2026-08-03
og_description: Создайте штрих‑код PDF417 на C# с помощью Aspose.Barcode. Следуйте
  этому руководству, чтобы сгенерировать штрих‑код PDF417 и узнать, как эффективно
  сохранять изображение штрих‑кода.
og_image_alt: Screenshot of a generated compact PDF417 barcode saved as PNG
og_title: Создание штрихкода PDF417 в C# – полный учебный курс по программированию
schemas:
- author: Aspose
  dateModified: '2026-08-03'
  description: Create PDF417 barcode in C# quickly. Learn how to generate PDF417 barcode
    and how to save barcode image as PNG with Aspose.Barcode.
  headline: Create PDF417 barcode in C# – step‑by‑step guide
  type: TechArticle
- description: Create PDF417 barcode in C# quickly. Learn how to generate PDF417 barcode
    and how to save barcode image as PNG with Aspose.Barcode.
  name: Create PDF417 barcode in C# – step‑by‑step guide
  steps:
  - name: Why this matters
    text: '* **EncodeTypes.Pdf417** tells the library to use the PDF417 standard,
      which supports large data payloads and error correction. * Providing Unicode
      characters proves the generator handles non‑ASCII input without extra configuration.'
  - name: Practical tip
    text: If you need a taller barcode for limited horizontal space, increase `Columns`.
      Setting `Truncate` to `true` reduces the overall height by removing quiet zones,
      which is ideal for mobile screens.
  - name: Expected result
    text: Running the program creates `CompactPdf417.png` in the project folder. Opening
      the file shows a compact PDF417 barcode that encodes the string *Åspóse.Barcóde©*.
      The image can be embedded in HTML, PDF reports, or printed on labels.
  - name: Verifying the output
    text: 'After the program finishes, you can verify the file exists with a quick
      command:'
  type: HowTo
tags:
- barcode
- C#
- PDF417
- image generation
title: Создание штрих‑кода PDF417 на C# – пошаговое руководство
url: /ru/net/compact-pdf417-encoding/create-pdf417-barcode-in-c-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Создание штрих‑кода PDF417 в C# – пошаговое руководство

Если вам нужно **создать штрих‑код PDF417** в приложении .NET, это руководство покажет, как именно сгенерировать штрих‑код PDF417 и сохранить его изображение. В результате вы получите PNG‑файл, который можно использовать в отчетах, билетах или мобильных сканирующих приложениях.

В учебнике рассматривается всё: от настройки проекта до получения готового PNG‑файла. Внешняя документация не требуется; просто следуйте шагам и запустите код.

## Что понадобится

Прежде чем начать, убедитесь, что у вас есть:

* .NET 6.0 SDK или новее (код также работает с .NET Framework 4.7+)
* Visual Studio 2022 или любой IDE, поддерживающий C#
* Доступ в Интернет для установки пакета NuGet **Aspose.Barcode for .NET**

Эти предварительные требования гарантируют, что код соберётся без дополнительной конфигурации.

## Создание штрих‑кода PDF417 – настройка проекта

1. Откройте командную строку и создайте новый консольный проект:

   ```bash
   dotnet new console -n Pdf417Demo
   cd Pdf417Demo
   ```

2. Добавьте библиотеку Aspose.Barcode:

   ```bash
   dotnet add package Aspose.Barcode
   ```

3. Откройте сгенерированный файл `Program.cs`. Операторы `using` в начале дают доступ к классам штрих‑кодов:

   ```csharp
   using System;
   using Aspose.Barcode.Generation;
   using Aspose.Barcode;
   ```

Проект готов к **созданию штрих‑кода PDF417**.

## Как сгенерировать штрих‑код PDF417 с помощью Aspose.Barcode

Основная часть создания штрих‑кода находится в классе `BarcodeGenerator`. Вы указываете символьный набор (`EncodeTypes.Pdf417`) и данные, которые нужно закодировать.

```csharp
// Step 1: Initialise the generator with PDF417 symbology and sample text.
// The text includes Unicode characters to demonstrate full‑range support.
BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Åspóse.Barcóde©");
```

### Почему это важно

* **EncodeTypes.Pdf417** указывает библиотеке использовать стандарт PDF417, поддерживающий большие объёмы данных и коррекцию ошибок.
* Использование Unicode‑символов демонстрирует, что генератор обрабатывает ввод не‑ASCII без дополнительной настройки.

## Как настроить внешний вид штрих‑кода

Можно задать размер каждого модуля, количество колонок и использовать компактный (усечённый) режим. Эти параметры влияют как на читаемость, так и на размер файла.

```csharp
// Step 2: Set the module (X) dimension – each barcode element will be 2 pixels wide.
generator.Parameters.Barcode.XDimension.Pixels = 2;

// Step 3: Configure PDF417‑specific options.
generator.Parameters.Barcode.Pdf417.Columns = 3;      // Number of columns (affects height)
generator.Parameters.Barcode.Pdf417.Truncate = true; // Enable compact mode
```

### Практический совет

Если требуется более высокий штрих‑код при ограниченном горизонтальном пространстве, увеличьте `Columns`. Установка `Truncate` в `true` уменьшает общую высоту, удаляя зоны тишины, что идеально для мобильных экранов.

## Как сохранить изображение штрих‑кода в PNG

После настройки генератора вызовите `Save`, указав путь к файлу и желаемый формат изображения. Метод сразу записывает изображение на диск.

```csharp
// Step 4: Save the generated barcode as a PNG image.
string outputPath = @"./CompactPdf417.png";
generator.Save(outputPath, BarCodeImageFormat.Png);
Console.WriteLine($"Barcode saved to {outputPath}");
```

### Ожидаемый результат

Запуск программы создаёт файл `CompactPdf417.png` в папке проекта. При открытии файла вы увидите компактный штрих‑код PDF417, который кодирует строку *Åspóse.Barcóde©*. Изображение можно встроить в HTML, PDF‑отчёты или напечатать на этикетках.

## Полный исходный код

Ниже представлен полностью готовый к запуску пример. Скопируйте его в `Program.cs` и выполните `dotnet run`.

```csharp
using System;
using Aspose.Barcode.Generation;
using Aspose.Barcode;

namespace Pdf417Demo
{
    class Program
    {
        static void Main()
        {
            // Initialise the generator with PDF417 symbology and sample text.
            BarcodeGenerator generator = new BarcodeGenerator(
                EncodeTypes.Pdf417,
                "Åspóse.Barcóde©");

            // Set the module width to 2 pixels.
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // Configure PDF417‑specific options.
            generator.Parameters.Barcode.Pdf417.Columns = 3;
            generator.Parameters.Barcode.Pdf417.Truncate = true;

            // Define the output file path.
            string outputPath = @"./CompactPdf417.png";

            // Save the barcode as a PNG image.
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"Barcode saved to {outputPath}");
        }
    }
}
```

### Проверка результата

После завершения программы вы можете быстро проверить наличие файла следующей командой:

```bash
dotnet run && ls -l CompactPdf417.png
```

Если файл появился, процесс **создания штрих‑кода PDF417** завершён успешно.

## Распространённые варианты и граничные случаи

| Ситуация | Корректировка |
|-----------|------------|
| **Более длинная строка данных** | Увеличьте `Columns` или задайте `Rows` для размещения большего количества кодовых слов. |
| **Другой формат изображения** | Замените `BarCodeImageFormat.Png` на `Jpeg`, `Bmp` или `Gif`. |
| **Более высокое разрешение** | Установите `generator.Parameters.ImageResolution` перед вызовом `Save`. |
| **Цвет фона** | Используйте `generator.Parameters.Barcode.ImageBackgroundColor = Color.White;` |
| **Обработка исключений** | Оберните `generator.Save` в блок `try/catch`, чтобы отлавливать ошибки ввода‑вывода. |

Эти варианты позволяют адаптировать штрих‑код под конкретные устройства или требования брендинга.

## Заключение

Теперь вы знаете, как **создать штрих‑код PDF417** в C# с помощью Aspose.Barcode, настроить его внешний вид и **сохранить изображение штрих‑кода** в формате PNG. Полный пример демонстрирует каждый необходимый шаг, от настройки проекта до проверки, что позволяет интегрировать генерацию штрих‑кодов в любое .NET‑решение.

Далее можете изучить связанные темы, такие как **генерация QR‑кодов**, **встраивание штрих‑кодов в PDF‑документы** или **кастомизация цветов штрих‑кода**. Все они используют тот же API генератора, позволяя расширять возможности сканирования вашего приложения с минимальными усилиями. Приятного кодинга!

## Что стоит изучить дальше?

Следующие учебники охватывают тесно связанные темы, построенные на техниках, продемонстрированных в этом руководстве. Каждый ресурс содержит полностью рабочие примеры кода с пошаговыми объяснениями, помогающими освоить дополнительные возможности API и исследовать альтернативные подходы в ваших проектах.

- [How to Create Barcode – Compact PDF417 with Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [How to Generate DataMatrix Barcodes (ECC 200) with Aspose.BarCode for .NET](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-ecc-200-configuration/)
- [How to generate Aztec barcode with custom aspect ratio using Aspose.BarCode for .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}