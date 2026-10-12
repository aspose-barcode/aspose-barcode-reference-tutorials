---
category: general
date: 2026-10-02
description: Штрих‑код со специальными символами в C# – узнайте, как генерировать
  штрих‑код со специальными символами с помощью Aspose.BarCode.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- barcode with special characters
- how to generate barcode c#
language: ru
lastmod: 2026-10-02
og_description: Штрих‑код со специальными символами в C# – этот учебник показывает,
  как сгенерировать штрих‑код в C#, включающий символы с диакритическими знаками и
  торговые знаки, с полным кодом и объяснениями.
og_image_alt: barcode with special characters example output
og_title: Создание штрих‑кода со специальными символами в C# — пошаговое руководство
schemas:
- author: Aspose
  dateModified: '2026-10-02'
  description: barcode with special characters in C# – learn how to generate a barcode
    with special characters using Aspose.BarCode.
  headline: How to generate a barcode with special characters in C#
  type: TechArticle
- description: barcode with special characters in C# – learn how to generate a barcode
    with special characters using Aspose.BarCode.
  name: How to generate a barcode with special characters in C#
  steps:
  - name: Why this works
    text: '* **Unicode support** – `BarcodeGenerator` accepts a `string` containing
      any Unicode glyph, so characters like **Å**, **ó**, and **©** are encoded without
      extra steps. * **MacroPdf417** – This format allows you to attach file‑level
      metadata (file ID, segment ID, checksum, etc.) that many enterprise '
  - name: Pro tip
    text: If you target a high‑density label printer, increase `XDimension.Pixels`
      to `3` or `4` to avoid pixel‑level distortion.
  - name: Edge case handling
    text: '* **Large file IDs** – The `FileID` property accepts a 32‑bit integer.
      If your system uses GUIDs, hash the GUID into a 32‑bit value before assignment.
      * **Timestamp precision** – The property stores a `DateTime`. If you need sub‑second
      precision, include it in the filename instead, as the standard d'
  - name: Expected output
    text: '* A PNG file approximately 300 × 150 pixels (size varies with column count).
      * When scanned with a PDF417‑compatible reader, the decoded text displays exactly
      **Åspóse.Barcóde©** and the scanner can reconstruct the original file using
      the macro fields.'
  type: HowTo
tags:
- barcode
- C#
- Aspose.BarCode
title: Как сгенерировать штрих‑код со специальными символами в C#
url: /ru/net/one-dimensional-barcode-types/how-to-generate-a-barcode-with-special-characters-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Как сгенерировать штрих‑код со специальными символами в C#

Если вам нужно сгенерировать штрих‑код со специальными символами в C#, это руководство предоставляет полное готовое к запуску решение. Независимо от того, кодируете ли вы буквы с диакритическими знаками, такие как **Å**, или символы, например **©**, приведённые ниже шаги позволят создать штрих‑код MacroPdf417, который сохраняет каждый символ точно так, как вы его ввели.

Вы узнаете, как генерировать barcode c# с помощью библиотеки Aspose.BarCode, настроить специфичные для MacroPdf417 метаданные и сохранить результат в виде PNG‑изображения. Внешние инструменты не требуются — только среда разработки .NET и пакет NuGet Aspose.BarCode.

## Требования

* .NET 6.0 SDK или более поздняя версия, установленная  
* Visual Studio 2022 (или любая IDE, поддерживающая C#)  
* Aspose.BarCode for .NET, добавленный в ваш проект (`dotnet add package Aspose.BarCode`)  

Эти требования гарантируют, что код компилируется без дополнительных зависимостей.

## Сгенерировать штрих‑код со специальными символами в C#

Суть решения заключается в создании экземпляра `BarcodeGenerator`, использующего формат `EncodeTypes.MacroPdf417`. Генератор принимает любую строку Unicode, поэтому специальные символы можно включать напрямую.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Step 1: Create a barcode generator for MacroPdf417 with special characters
        using (BarcodeGenerator barcodeGenerator =
               new BarcodeGenerator(EncodeTypes.MacroPdf417, "Åspóse.Barcóde©"))
        {
            // Step 2: Set basic barcode appearance
            barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
            barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 5;

            // Step 3: Configure MacroPdf417 specific metadata
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234; // CCITT‑16 checksum
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400000;
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2019, 11, 1);
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;

            // Step 4: Save the generated barcode as a PNG image
            barcodeGenerator.Save("ExtPDF417Meta.png", BarCodeImageFormat.Png);
        }

        Console.WriteLine("Barcode with special characters generated successfully.");
    }
}
```

### Почему это работает

* **Unicode support** – `BarcodeGenerator` принимает `string`, содержащий любые глифы Unicode, поэтому такие символы, как **Å**, **ó** и **©**, кодируются без дополнительных шагов.  
* **MacroPdf417** – Этот формат позволяет прикреплять метаданные уровня файла (ID файла, ID сегмента, контрольная сумма и т.д.), которые ожидают многие корпоративные системы сканирования.  
* **Pixel‑level control** – Установка `XDimension.Pixels` контролирует ширину модуля, что влияет на читаемость на принтерах с низким разрешением.

## Установить базовый внешний вид штрих‑кода

Настройка `XDimension` и количества колонок влияет как на визуальный размер, так и на объём данных, помещающихся в одну строку. Значение `2` пикселя обеспечивает компактный, но считываемый штрих‑код, тогда как `Columns = 5` делает символ достаточно узким для большинства этикеток.

### Совет профессионала

Если вы используете принтер этикеток с высокой плотностью, увеличьте `XDimension.Pixels` до `3` или `4`, чтобы избежать искажений на уровне пикселей.

## Настроить метаданные MacroPdf417

MacroPdf417 расширяет стандартную спецификацию PDF417 полями, описывающими, как должен быть восстановлен много‑сегментный файл. Свойства, указанные в примере, соответствуют типичному сценарию использования:

| Property | Purpose |
|----------|---------|
| `MacroPdf417FileID` | Уникальный идентификатор всего файла |
| `MacroPdf417SegmentID` | Индекс текущего сегмента (начинается с 1) |
| `MacroPdf417SegmentsCount` | Общее количество сегментов в файле |
| `MacroPdf417FileName` | Логическое имя файла (используется некоторыми сканерами) |
| `MacroPdf417Checksum` | Контрольная сумма CCITT‑16 для целостности данных |
| `MacroPdf417FileSize` | Ожидаемый размер в байтах – помогает сканерам проверять полноту |
| `MacroPdf417TimeStamp` | Временная метка создания для аудита |
| `MacroPdf417Addressee` / `MacroPdf417Sender` | Опциональная информация о получателе/отправителе |
| `MacroPdf417Terminator` | Указывает, является ли это последним сегментом (`Set`) или промежуточным (`Unset`) |

### Обработка граничных случаев

* **Large file IDs** – Свойство `FileID` принимает 32‑битное целое число. Если ваша система использует GUID, преобразуйте GUID в 32‑битное значение с помощью хеширования перед присвоением.  
* **Timestamp precision** – Свойство хранит `DateTime`. Если требуется точность менее секунды, включите её в имя файла, так как стандарт не поддерживает миллисекунды.  

## Сохранить изображение штрих‑кода

Метод `Save` записывает отрисованный штрих‑код в файловую систему. Вы можете выбрать другие форматы (`Jpeg`, `Bmp`, `Svg`), заменив `BarCodeImageFormat.Png`. PNG — без потерь, что делает его идеальным для дальнейшей обработки или встраивания в PDF.

```csharp
barcodeGenerator.Save("ExtPDF417Meta.png", BarCodeImageFormat.Png);
```

После запуска программы вы найдете `ExtPDF417Meta.png` в каталоге вывода. Открытие изображения показывает плотный, многострочный штрих‑код, содержащий текст **Åspóse.Barcóde©** вместе с настроенными макро‑метаданными.

### Ожидаемый результат

* PNG‑файл приблизительно 300 × 150 пикселей (размер зависит от количества колонок).  
* При сканировании совместимым считывателем PDF417 декодированный текст будет точно **Åspóse.Barcóde©**, а сканер сможет восстановить оригинальный файл, используя макро‑поля.

## Как сгенерировать barcode c# – распространённые подводные камни

Несмотря на простоту кода, разработчики часто сталкиваются со следующими проблемами:

1. **Missing NuGet package** – Забвение установки `Aspose.BarCode` приводит к ошибкам компиляции. Проверьте ссылку на пакет в вашем `.csproj`.  
2. **Invalid characters for the chosen symbology** – Некоторые типы штрих‑кодов (например, Code 128) отклоняют определённые диапазоны Unicode. MacroPdf417 принимает полный набор Unicode, что делает его самым безопасным выбором для специальных символов.  
3. **Incorrect file path** – Использование относительного пути без соответствующих прав может вызвать исключение времени выполнения `UnauthorizedAccessException`. Укажите абсолютный путь или убедитесь, что приложение имеет права записи в целевую папку.  

Устранение этих моментов гарантирует, что процесс генерации barcode c# будет проходить без проблем.

## Полный рабочий пример

Скопируйте полную программу ниже в новый консольный проект и запустите её. Дополнительная настройка не требуется, кроме пакета NuGet.



## Что вам стоит изучить дальше?

Следующие руководства охватывают тесно связанные темы, построенные на техниках, продемонстрированных в этом руководстве. Каждый ресурс включает полные работающие примеры кода с пошаговыми объяснениями, чтобы помочь вам освоить дополнительные возможности API и исследовать альтернативные подходы к реализации в ваших проектах.

- [Barcode with Special Characters – Complete Guide to Generating PDF417 Using](/barcode/english/net/compact-pdf417-encoding/barcode-with-special-characters-complete-guide-to-generating/)
- [How to generate barcode image with Aspose.BarCode in C#](/barcode/english/python-java/general/how-to-generate-barcode-image-with-aspose-barcode-in-c/)
- [How to Generate PDF417 Barcode Image in C# with Aspose](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-image-in-c-with-aspose/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}