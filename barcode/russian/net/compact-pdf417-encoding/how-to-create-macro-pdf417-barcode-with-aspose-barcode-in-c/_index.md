---
category: general
date: 2026-11-20
description: Узнайте, как создать макро‑PDF417 штрих‑код в C# с помощью Aspose.BarCode.
  Это руководство охватывает метаданные, параметры и сохранение изображения.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create macro PDF417 barcode
- macro PDF417 metadata
- Aspose.BarCode C#
- PDF417 macro parameters
- barcode generator example
language: ru
lastmod: 2026-11-20
og_description: Создайте макро‑штрихкод PDF417 в C# с помощью Aspose.BarCode. Следуйте
  этому полному руководству, чтобы задать метаданные, настроить параметры и экспортировать
  PNG.
og_image_alt: Screenshot of a generated macro PDF417 barcode image
og_title: Создание макро‑штрихкода PDF417 в C# – пошаговое руководство
schemas:
- author: Aspose
  dateModified: '2026-11-20'
  description: Learn how to create macro PDF417 barcode in C# using Aspose.BarCode.
    This guide covers metadata, parameters, and saving the image.
  headline: How to create macro PDF417 barcode with Aspose.BarCode in C#
  type: TechArticle
- description: Learn how to create macro PDF417 barcode in C# using Aspose.BarCode.
    This guide covers metadata, parameters, and saving the image.
  name: How to create macro PDF417 barcode with Aspose.BarCode in C#
  steps:
  - name: Expected output
    text: 'Running the program prints a confirmation line similar to:'
  - name: What if I need more than 20 segments?
    text: The `MacroPdf417SegmentsCount` property can be set up to `255`. Ensure the
      receiving system can handle the larger segment count, and consider splitting
      the data into a manageable number of symbols.
  - name: How does the checksum affect scanning?
    text: The CCITT‑16 checksum (`MacroPdf417Checksum`) provides an additional error‑checking
      layer. If a scanner detects a mismatch, it will reject the barcode. You can
      omit the checksum if your workflow does not require it.
  - name: Can I generate a PDF417 macro barcode without Aspose?
    text: Yes, other libraries (e.g., ZXing.Net, Dynamsoft) support PDF417, but macro‑specific
      fields are often missing. Aspose.BarCode offers the most complete implementation
      for macro metadata.
  - name: What image formats are supported for saving?
    text: The `Save` method accepts any format defined in `BarCodeImageFormat`, such
      as `Png`, `Jpeg`, `Gif`, `Bmp`, and `Tiff`. Choose a format that matches your
      downstream processing pipeline.
  type: HowTo
tags:
- barcode
- PDF417
- C#
- Aspose
title: Как создать макро‑PDF417 штрих‑код с помощью Aspose.BarCode в C#
url: /ru/net/compact-pdf417-encoding/how-to-create-macro-pdf417-barcode-with-aspose-barcode-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Как создать макро PDF417 штрих‑код с помощью Aspose.BarCode в C#

Если вам нужно **создать макро PDF417 штрих‑код** в .NET‑приложении, этот учебник покажет точные шаги. Вы увидите, как настроить специфичные для макро метаданные, отрегулировать визуальные параметры и сохранить результат в файл PNG.

Создание макро PDF417 штрих‑кода полезно, когда необходимо разбить большой набор данных на несколько символов, сохранив при этом идентификатор всего файла. В примере ниже мы используем библиотеку Aspose.BarCode, которая предоставляет удобный API для всех функций PDF417.

К концу этого руководства у вас будет готовая к запуску консольная программа, генерирующая изображение штрих‑кода, содержащего полную макро‑информацию.

## Требования

* .NET 6.0 SDK или более поздняя версия, установленная.
* Visual Studio 2022 (или любая IDE, поддерживающая C#).
* Пакет NuGet **Aspose.BarCode for .NET** (`Aspose.BarCode`).

Вы можете добавить пакет с помощью следующей команды:

```bash
dotnet add package Aspose.BarCode
```

## Шаг 1: Инициализация генератора штрих‑кода для macro PDF417

Первый шаг — создать экземпляр `BarcodeGenerator` с значением перечисления `EncodeTypes.MacroPdf417`. Это указывает библиотеке рассматривать штрих‑код как символ macro PDF417.

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

using (BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
           EncodeTypes.MacroPdf417, "Åspóse.Barcóde©"))
{
    // The generator is now ready for further configuration.
```

*Почему это важно*: Выбор `MacroPdf417` включает все свойства, связанные с макро, в объекте параметров `Pdf417`.

## Шаг 2: Установка базового визуального вида

Читаемый штрих‑код начинается с подходящего размера модуля и количества столбцов. Свойство `XDimension.Pixels` задает ширину одного модуля, а `Pdf417.Columns` определяет, сколько столбцов данных содержит каждая строка.

```csharp
    // Set module width to 2 pixels.
    barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;

    // Use 5 columns per row – a compact layout for this example.
    barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 5;
```

Настройка этих значений влияет как на надежность сканера, так и на размер изображения.

## Шаг 3: Определение деталей идентификации макро‑файла

Macro PDF417 требует идентификатор файла, идентификатор сегмента и общее количество сегментов. Эти три поля позволяют сканеру восстановить исходный набор данных.

```csharp
    // Unique file identifier for the whole macro file.
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;

    // Identifier of the current segment (starting at 0 or 1 based on your protocol).
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;

    // Total number of segments that compose the complete file.
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;

    // Optional human‑readable file name.
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";
```

Эти **параметры macro PDF417** являются ядром макро‑функциональности. Без них сканер не сможет связать символы вместе.

## Шаг 4: Добавление необязательных макро‑метаданных

Помимо обязательных идентификаторов, формат macro поддерживает дополнительные поля, такие как контрольная сумма, размер файла, метка времени, получатель, отправитель и флаг завершения. Предоставление этих данных улучшает обнаружение ошибок и дает контекст для последующих систем.

```csharp
    // CCITT‑16 checksum example.
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234;

    // Approximate file size in bytes (helps the receiver allocate buffers).
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000;

    // Timestamp of when the macro file was generated.
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2019, 11, 1);

    // Optional address fields.
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";

    // Terminator indicates that this is the final segment.
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;
```

*Полезный совет*: Если ваш процесс не требует конкретного поля, вы можете оставить его со значением по умолчанию. Библиотека опустит соответствующий элемент данных в штрих‑коде.

## Шаг 5: Сохранение изображения штрих‑кода

После настройки всех параметров вызовите `Save` для экспорта штрих‑кода. В примере PNG‑файл сохраняется в указанный пользователем каталог.

```csharp
    // Replace with a valid folder on your machine.
    string outputPath = "YOUR_DIRECTORY/ExtPDF417Meta.png";

    // Save as PNG – other formats (Jpeg, Gif, etc.) are also supported.
    barcodeGenerator.Save(outputPath, BarCodeImageFormat.Png);
}
```

Когда программа завершится, `ExtPDF417Meta.png` будет содержать macro PDF417 штрих‑код, кодирующий текст `"Åspóse.Barcóde©"` вместе со всеми макро‑метаданными.

## Полный исходный код

Ниже представлен полный, автономный пример программы. Скопируйте его в новый консольный проект и запустите после установки пакета NuGet Aspose.BarCode.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace MacroPdf417Demo
{
    class Program
    {
        static void Main()
        {
            // Step 1: Create a macro PDF417 barcode generator.
            using (BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
                       EncodeTypes.MacroPdf417, "Åspóse.Barcóde©"))
            {
                // Step 2: Visual appearance.
                barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
                barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 5;

                // Step 3: Core macro identifiers.
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";

                // Step 4: Optional macro metadata.
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2019, 11, 1);
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;

                // Step 5: Export the image.
                string outputPath = "YOUR_DIRECTORY/ExtPDF417Meta.png";
                barcodeGenerator.Save(outputPath, BarCodeImageFormat.Png);
                Console.WriteLine($"Macro PDF417 barcode saved to {outputPath}");
            }
        }
    }
}
```

### Ожидаемый вывод

Запуск программы выводит строку подтверждения, похожую на:

```
Macro PDF417 barcode saved to YOUR_DIRECTORY/ExtPDF417Meta.png
```

Открытие PNG‑файла показывает плотный, высококонтрастный штрих‑код. Сканирование его совместимым со сканером PDF417 возвращает исходный текст плюс все макро‑поля.

## Часто задаваемые вопросы и особые случаи

### Что делать, если нужно более 20 сегментов?

Свойство `MacroPdf417SegmentsCount` можно установить до `255`. Убедитесь, что принимающая система может обработать большее количество сегментов, и рассмотрите возможность разбивки данных на управляемое число символов.

### Как контрольная сумма влияет на сканирование?

Контрольная сумма CCITT‑16 (`MacroPdf417Checksum`) добавляет дополнительный уровень проверки ошибок. Если сканер обнаружит несоответствие, он отклонит штрих‑код. Вы можете опустить контрольную сумму, если ваш процесс её не требует.

### Можно ли сгенерировать macro PDF417 штрих‑код без Aspose?

Да, другие библиотеки (например, ZXing.Net, Dynamsoft) поддерживают PDF417, но часто отсутствуют поля, специфичные для macro. Aspose.BarCode предлагает наиболее полную реализацию макро‑метаданных.

### Какие форматы изображений поддерживаются для сохранения?

Метод `Save` принимает любой формат, определённый в `BarCodeImageFormat`, например `Png`, `Jpeg`, `Gif`, `Bmp` и `Tiff`. Выберите формат, соответствующий вашему конвейеру последующей обработки.

## Заключение

Теперь вы знаете, как **создать macro PDF417 штрих‑код** в C# с помощью Aspose.BarCode. В учебнике рассмотрены инициализация генератора, визуальные настройки, идентификаторы макро‑файла, необязательные метаданные и экспорт изображения. С этой базой вы можете внедрять macro PDF в системы учёта, отслеживания документов или любые сценарии, требующие сегментированной передачи данных.

Следующие шаги включают эксперименты с различными значениями `XDimension` для более высокого разрешения, настройку уровня коррекции ошибок или интеграцию штрих‑кода в веб‑API, который напрямую возвращает поток PNG. Для смежных тем см. учебники по **barcode generator example**, **PDF417 macro parameters** и обработке **macro PDF417 metadata**.

Удачной разработки!

## Что изучать дальше?

Следующие учебники охватывают тесно связанные темы, основанные на техниках, продемонстрированных в этом руководстве. Каждый ресурс включает полные работающие примеры кода с пошаговыми объяснениями, чтобы помочь вам освоить дополнительные возможности API и исследовать альтернативные подходы к реализации в ваших проектах.

- [Как создать изображение PDF417 штрих‑кода в C# с опциями Macro PDF417](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-image-in-c-with-macro-pdf417-op/)
- [Считывание штрих‑кода с изображения C# – полное руководство с Macro PDF417](/barcode/english/net/compact-pdf417-encoding/read-barcode-from-image-c-complete-guide-with-macro-pdf417/)
- [Как создать PDF417 штрих‑код с Aspose – полное пошаговое руководство](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-with-aspose-complete-step-by-st/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}