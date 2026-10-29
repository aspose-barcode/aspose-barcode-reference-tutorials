---
category: general
date: 2026-10-28
description: Как сгенерировать штрих‑код с пользовательским текстом с помощью Aspose.BarCode
  – пошаговое руководство для .NET‑разработчиков по созданию изображений штрих‑кодов
  Aspose.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to generate barcode
- generate barcode custom text
- create barcode aspose
language: ru
lastmod: 2026-10-28
og_description: Как сгенерировать штрих‑код с пользовательским текстом в .NET с помощью
  Aspose.BarCode. Следуйте этому полному руководству, чтобы создать и сохранить макро‑PDF417
  штрих‑код.
og_image_alt: how to generate barcode example PNG image showing a Macro PDF417 barcode
og_title: Как сгенерировать штрих‑код с пользовательским текстом – учебник Aspose.BarCode
schemas:
- author: Aspose
  dateModified: '2026-10-28'
  description: How to generate barcode with custom text using Aspose.BarCode – step‑by‑step
    guide for .NET developers to create barcode Aspose images.
  headline: How to generate barcode with custom text using Aspose.BarCode for .NET
  type: TechArticle
- description: How to generate barcode with custom text using Aspose.BarCode – step‑by‑step
    guide for .NET developers to create barcode Aspose images.
  name: How to generate barcode with custom text using Aspose.BarCode for .NET
  steps:
  - name: Why each line matters
    text: '* **EncodeTypes.MacroPdf417** – selects the Macro PDF417 symbology, which
      supports segmented data and metadata. * **XDimension.Pixels** – controls the
      size of each module; a value of 2 pixels yields a clear, scannable image. *
      **Pdf417.Columns** – reduces the overall width, making the barcode more c'
  - name: Using a different barcode type
    text: If you need to **generate barcode custom text** for a QR code instead of
      Macro PDF417, replace `EncodeTypes.MacroPdf417` with `EncodeTypes.QR`. The rest
      of the parameter structure stays the same, but QR codes do not support Macro
      metadata fields.
  - name: Handling Unicode characters
    text: The example already includes Unicode characters (`Å`, `ó`, `©`). Aspose.BarCode
      handles UTF‑8 input out of the box, but you should ensure the source file is
      saved with UTF‑8 encoding to avoid compile‑time warnings.
  - name: Saving to other image formats
    text: 'Aspose.BarCode supports BMP, JPEG, TIFF, and SVG in addition to PNG. Change
      the `BarCodeImageFormat` enum value accordingly:'
  - name: Large data sets
    text: Macro PDF417 can split data across multiple segments. When the text exceeds
      the capacity of a single segment, increment `MacroPdf417SegmentID` and keep
      `MacroPdf417SegmentsCount` consistent across all generated parts. This approach
      is essential for **create barcode aspose** scenarios where the paylo
  - name: Error handling
    text: 'Wrap the generation logic in a try‑catch block to surface runtime issues
      such as invalid file paths or unsupported characters:'
  type: HowTo
tags:
- barcode
- Aspose.BarCode
- .NET
title: Как сгенерировать штрих‑код с пользовательским текстом, используя Aspose.BarCode
  для .NET
url: /ru/net/one-dimensional-barcode-types/how-to-generate-barcode-with-custom-text-using-aspose-barcod/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Как сгенерировать штрих‑код с пользовательским текстом с помощью Aspose.BarCode для .NET

Генерация штрих‑кода с пользовательским текстом часто требуется, когда необходимо встроить идентификаторы, метки времени или другие метаданные непосредственно в визуальный код. В этом руководстве показано, как создать штрих‑код Macro PDF417, содержащий пользовательский текст и полный набор метаданных, используя библиотеку **Aspose.BarCode** для .NET.

Вы узнаете, как настроить генератор, применить пользовательский текст, задать специфические поля Macro PDF417 и сохранить результат в виде PNG‑изображения. Внешние инструменты не требуются — только пакет NuGet Aspose.BarCode и среда разработки .NET.

## Предварительные требования

* .NET 6.0 SDK или более поздняя версия, установленная  
* Visual Studio 2022 (или любая IDE, поддерживающая .NET)  
* NuGet‑пакет **Aspose.BarCode for .NET** (`Install-Package Aspose.BarCode`)  

Эти требования гарантируют, что код компилируется и работает без дополнительной настройки.

## Шаг 1: Установите пакет Aspose.BarCode

Откройте терминал в папке проекта и выполните:

```bash
dotnet add package Aspose.BarCode
```

Эта команда добавит последнюю стабильную версию Aspose.BarCode в ваш проект, предоставив доступ к классу `BarcodeGenerator` и всем связанным параметрам.

## Шаг 2: Создайте новое консольное приложение

Создайте минимальное консольное приложение, которое будет содержать логику генерации штрих‑кода:

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

namespace BarcodeDemo
{
    internal class Program
    {
        private static void Main()
        {
            // The full barcode generation flow is encapsulated in a separate method
            GenerateMacroPdf417Barcode();
        }

        /// <summary>
        /// Generates a Macro PDF417 barcode with custom text and metadata, then saves it as PNG.
        /// </summary>
        private static void GenerateMacroPdf417Barcode()
        {
            // Step 1: Instantiate the generator with the desired encode type and data
            using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MacroPdf417, "Åspóse.Barcóde©"))
            {
                // Step 2: Define the visual appearance of the barcode
                generator.Parameters.Barcode.XDimension.Pixels = 2;          // Size of a single module
                generator.Parameters.Barcode.Pdf417.Columns = 5;            // Number of columns in the symbol

                // Step 3: Populate Macro PDF417 specific metadata fields
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
                generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;
                generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";
                generator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234; // CCITT‑16 example value
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000;
                generator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2019, 11, 1);
                generator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
                generator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
                generator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;

                // Step 4: Save the barcode image to disk
                string outputPath = @"ExtPDF417Meta.png";
                generator.Save(outputPath, BarCodeImageFormat.Png);
                Console.WriteLine($"Barcode saved to {outputPath}");
            }
        }
    }
}
```

### Почему каждая строка важна

* **EncodeTypes.MacroPdf417** – выбирает символьную схему Macro PDF417, поддерживающую сегментированные данные и метаданные.  
* **XDimension.Pixels** – управляет размером каждого модуля; значение 2 пикселя дает чёткое, сканируемое изображение.  
* **Pdf417.Columns** – уменьшает общую ширину, делая штрих‑код более компактным для печатных этикеток.  
* **MacroPdf417* properties** – встраивают информацию уровня файла (ID, количество сегментов, метки времени и т.д.) непосредственно в штрих‑код. Эта возможность уникальна для Macro PDF417 и часто используется в логистике или системах управления документами.  
* **Save(..., BarCodeImageFormat.Png)** – сохраняет без потерь в формате PNG, сохраняет резкие края штрих‑кода для надёжного сканирования.

## Шаг 3: Запустите программу и проверьте результат

Соберите и запустите консольное приложение:

```bash
dotnet run
```

Программа создаёт `ExtPDF417Meta.png` в рабочем каталоге проекта. При открытии файла отображается штрих‑код Macro PDF417, который кодирует текст **«Åspóse.Barcóde©»** вместе с предоставленными вами метаданными.

**Ожидаемый результат** – PNG‑изображение, похожее на приведённое ниже:

![пример вывода генерации штрих‑кода PNG‑изображение, показывающее штрих‑код Macro PDF417](ExtPDF417Meta.png)

*Текст alt изображения («пример вывода генерации штрих‑кода PNG изображение») усиливает основной ключевой запрос для доступности и SEO.*

## Распространённые варианты и граничные случаи

### Использование другого типа штрих‑кода

Если вам нужно **сгенерировать штрих‑код с пользовательским текстом** для QR‑кода вместо Macro PDF417, замените `EncodeTypes.MacroPdf417` на `EncodeTypes.QR`. Остальная структура параметров остаётся той же, однако QR‑коды не поддерживают поля метаданных Macro.

### Обработка Unicode‑символов

В примере уже используются Unicode‑символы (`Å`, `ó`, `©`). Aspose.BarCode из коробки поддерживает ввод в UTF‑8, однако следует убедиться, что исходный файл сохранён в кодировке UTF‑8, чтобы избежать предупреждений компиляции.

### Сохранение в другие форматы изображений

Aspose.BarCode поддерживает BMP, JPEG, TIFF и SVG помимо PNG. Измените значение перечисления `BarCodeImageFormat` соответственно:

```csharp
generator.Save("barcode.svg", BarCodeImageFormat.Svg);
```

### Большие наборы данных

Macro PDF417 может разбивать данные на несколько сегментов. Когда текст превышает ёмкость одного сегмента, увеличьте `MacroPdf417SegmentID` и поддерживайте согласованность `MacroPdf417SegmentsCount` во всех сгенерированных частях. Такой подход необходим для сценариев **create barcode aspose**, когда полезная нагрузка превышает возможности одного штрих‑кода.

### Обработка ошибок

Обёрните логику генерации в блок try‑catch, чтобы отлавливать ошибки выполнения, такие как неверные пути к файлам или неподдерживаемые символы:

```csharp
try
{
    GenerateMacroPdf417Barcode();
}
catch (Exception ex)
{
    Console.Error.WriteLine($"Barcode generation failed: {ex.Message}");
}
```

## Профессиональные советы для надёжной генерации штрих‑кодов

* **Validate the barcode** после создания с помощью `BarCodeReader`. Этот дополнительный шаг подтверждает, что закодированные данные соответствуют вашим ожиданиям.

  ```csharp
  using (BarCodeReader reader = new BarCodeReader("ExtPDF417Meta.png", DecodeType.MacroPdf417))
  {
      if (reader.Read())
          Console.WriteLine($"Decoded text: {reader.GetCodeText()}");
  }
  ```

* **Keep X‑dimension between 2 – 4 pixels** для большинства сканеров. Меньшие значения могут приводить к нечитаемым изображениям на устройствах с низким разрешением.

* **Avoid very long file names** в `MacroPdf417FileName`. Спецификация ограничивает поле 32 символами.

* **Use consistent timestamps** (UTC) при генерации нескольких сегментов, чтобы упростить последующую обработку.

## Заключение

Теперь вы знаете **how to generate barcode** с пользовательским текстом с помощью Aspose.BarCode для .NET, как настроить метаданные Macro PDF417 и как сохранить результат в виде PNG‑изображения. Полный, исполняемый пример демонстрирует каждый необходимый шаг — от установки пакета NuGet до обработки Unicode‑символов и сохранения вывода.

Отсюда вы можете:

* **Generate barcode custom text** для других символьных схем (QR, DataMatrix и т.д.)  
* **Create barcode Aspose** рабочие процессы, которые пакетно обрабатывают тысячи изображений  
* Интегрировать код генерации штрих‑кода в сервисы ASP.NET Core, Windows services или Azure Functions  

Экспериментируйте с различными параметрами, изучайте дополнительные поля метаданных и внедряйте штрих‑код в ваши конвейеры автоматизации документов. Приятного кодирования!

## Что изучать дальше?

Следующие руководства охватывают близко связанные темы, которые опираются на техники, продемонстрированные в этом руководстве. Каждый ресурс содержит полностью рабочие примеры кода с пошаговыми объяснениями, помогающими освоить дополнительные возможности API и исследовать альтернативные подходы к реализации в ваших проектах.

- [Как создать PDF417 штрих‑код с Aspose – Полное пошаговое руководство](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-with-aspose-complete-step-by-st/)
- [Генерация штрих‑кода из текста с помощью Aspose.BarCode – Руководство C#](/barcode/english/net/one-dimensional-barcode-types/generate-barcode-from-text-using-aspose-barcode-c-guide/)
- [Как использовать Aspose.BarCode для создания текста DataMatrix кода в .NET](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-extended-code-text-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}