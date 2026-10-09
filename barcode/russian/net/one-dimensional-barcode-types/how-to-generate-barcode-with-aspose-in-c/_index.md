---
category: general
date: 2026-09-19
description: Как генерировать штрих‑код с помощью Aspose в C# — пошаговое руководство
  по быстрому и надёжному созданию штрих‑кода с Aspose.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to generate barcode
- create barcode with aspose
language: ru
lastmod: 2026-09-19
og_description: Как создать штрих‑код с помощью Aspose в C#. Следуйте этому руководству,
  чтобы создать штрих‑код с Aspose, настроить MacroPdf417 и сохранить его в формате
  PNG.
og_image_alt: Screenshot showing a MacroPdf417 barcode generated with Aspose in C#
og_title: Как сгенерировать штрих‑код с помощью Aspose – полное руководство по C#
schemas:
- author: Aspose
  dateModified: '2026-09-19'
  description: How to generate barcode using Aspose in C# – a step‑by‑step guide to
    create barcode with Aspose quickly and reliably.
  headline: How to generate barcode with Aspose in C#
  type: TechArticle
- description: How to generate barcode using Aspose in C# – a step‑by‑step guide to
    create barcode with Aspose quickly and reliably.
  name: How to generate barcode with Aspose in C#
  steps:
  - name: What if I need a different image format?
    text: Aspose supports `BarCodeImageFormat.Jpeg`, `Bmp`, `Tiff`, `Svg`, and `Pdf`.
      Just replace `BarCodeImageFormat.Png` with the desired enum value.
  - name: How do I generate multiple segments automatically?
    text: You can place the code above inside a loop, incrementing `MacroPdf417SegmentID`
      on each iteration and updating the data string. Remember to keep `MacroPdf417SegmentsCount`
      constant across all segments.
  - name: What if the data exceeds the capacity of a single MacroPdf417 symbol?
    text: MacroPdf417 is designed for large payloads, but every barcode has a theoretical
      maximum (≈ 1.1 KB per segment). Split the source file into chunks that fit this
      limit, then encode each chunk as a separate segment.
  - name: Does the checksum need to be calculated manually?
    text: Aspose can generate the CCITT‑16 checksum automatically if you set `MacroPdf417Checksum`
      to `0`. In the example we supplied a hard‑coded value for illustration; in production
      code you’d typically let the library compute it.
  - name: How can I change the barcode’s foreground/background colors?
    text: 'Use the `BarColor` and `BackColor` properties:'
  type: HowTo
tags:
- barcode
- Aspose
- C#
- .NET
title: Как сгенерировать штрих‑код с помощью Aspose в C#
url: /ru/net/one-dimensional-barcode-types/how-to-generate-barcode-with-aspose-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Как создать штрих‑код с помощью Aspose в C#

Создание штрих‑кода в C# простое, когда вы используете библиотеку Aspose.BarCode. В этом руководстве показано, как **создать штрих‑код с Aspose** шаг за шагом, охватывая формат MacroPdf417, общие настройки внешнего вида и сохранение результата в виде PNG‑изображения.

Вы узнаете, как:

* Установить и добавить ссылку на Aspose.BarCode для .NET  
* Настроить свойства, специфичные для MacroPdf417, такие как идентификатор файла, идентификатор сегмента и контрольная сумма  
* Регулировать визуальные параметры, такие как X‑dimension и количество колонок  
* Экспортировать штрих‑код в файл изображения  

Предыдущий опыт работы с Aspose не требуется — достаточно базовых знаний C# и Visual Studio.

## Предварительные требования

Перед началом убедитесь, что у вас есть:

| Требование | Подробности |
|-------------|-------------|
| .NET runtime | .NET 6.0 или новее (код также работает с .NET Framework 4.7+) |
| IDE | Visual Studio 2022, Rider или любой редактор, поддерживающий C# |
| Aspose.BarCode | NuGet‑пакет `Aspose.BarCode` (бесплатная пробная версия или лицензия) |
| Базовые знания C# | Знакомство с инструкциями `using` и инициализацией объектов |

Вы можете добавить Aspose.BarCode в ваш проект через NuGet Package Manager:

```bash
dotnet add package Aspose.BarCode
```

## Как создать штрих‑код в C# – общий процесс

Процесс состоит из четырёх логических шагов:

1. **Создать экземпляр `BarcodeGenerator`** с нужным типом кодирования (MacroPdf417) и текстом, который нужно закодировать.  
2. **Установить общие параметры внешнего вида** такие как X‑dimension и количество колонок.  
3. **Настроить свойства, специфичные для MacroPdf417**, например идентификатор файла, идентификатор сегмента и метку времени.  
4. **Сохранить штрих‑код** в выбранном формате файла (в примере — PNG).

Каждый шаг подробно описан ниже.

## Шаг 1: Создать генератор штрих‑кода для MacroPdf417

Класс `BarcodeGenerator` является точкой входа для всех задач создания штрих‑кодов. При его создании вы передаёте два аргумента:

* `EncodeTypes.MacroPdf417` — указывает Aspose использовать симбологию MacroPdf417.  
* Строка данных — текст, который будет закодирован внутри штрих‑кода.

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;
using System;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // Step 1 – instantiate the generator with MacroPdf417 and sample data
            using (BarcodeGenerator generator = new BarcodeGenerator(
                       EncodeTypes.MacroPdf417, "Sample"))
            {
                // Subsequent steps go here
            }
        }
    }
}
```

> **Почему это важно:** MacroPdf417 — двумерный штрих‑код, способный хранить большие объёмы данных и поддерживающий макро‑функции, такие как сегментация файлов, что полезно при передаче больших файлов по частям.

## Шаг 2: Установить общие параметры внешнего вида штрих‑кода

Хотя MacroPdf417 имеет множество специализированных настроек, вам всё равно нужно контролировать визуальную плотность и расположение. Наиболее часто используемые параметры:

* **X‑dimension** — ширина самого маленького модуля (пикселя). Меньшие значения дают более плотное изображение.  
* **Columns** — количество колонок данных в строке; большее число уменьшает высоту штрих‑кода.

```csharp
// Step 2 – adjust appearance
generator.Parameters.Barcode.XDimension.Pixels = 2;   // 2‑pixel modules
generator.Parameters.Barcode.Pdf417.Columns = 5;    // 5 columns per row
```

> **Совет:** Держите `XDimension` в диапазоне от 2 до 4 пикселей для большинства сценариев отображения на экране. Большие значения повышают читаемость на принтерах с низким разрешением, но увеличивают общий размер изображения.

## Шаг 3: Настроить свойства, специфичные для MacroPdf417

MacroPdf417 добавляет набор полей метаданных, позволяющих разбить большой файл на несколько сегментов штрих‑кода. Ниже перечислены свойства, которые обычно требуются:

| Свойство | Назначение |
|----------|------------|
| `MacroPdf417FileID` | Уникальный идентификатор всего файла (максимум 8 цифр). |
| `MacroPdf417SegmentID` | Индекс текущего сегмента (начинается с 0). |
| `MacroPdf417SegmentsCount` | Общее количество сегментов в файле. |
| `MacroPdf417FileName` | Читаемое человеком имя исходного файла. |
| `MacroPdf417Checksum` | Необязательная контрольная сумма CCITT‑16 для обнаружения ошибок. |
| `MacroPdf417FileSize` | Размер исходного файла в байтах. |
| `MacroPdf417TimeStamp` | Метка времени создания файла. |
| `MacroPdf417Addressee` / `MacroPdf417Sender` | Необязательные строки для идентификации получателя/отправителя. |
| `MacroPdf417Terminator` | Определяет, является ли штрих‑код последним сегментом (`Set`) или промежуточным (`Unset`). |

```csharp
// Step 3 – set macro‑specific data
generator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;
generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;
generator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";
generator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234; // CCITT‑16 example
generator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000; // in bytes
generator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2019, 11, 1);
generator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
generator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
generator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;
```

> **Почему эти поля полезны:**  
> *Когда необходимо передать большой документ по каналу с низкой пропускной способностью, его можно разбить на несколько штрих‑кодов MacroPdf417. Получатель восстанавливает оригинальный файл, читая метаданные каждого сегмента.*

## Шаг 4: Сохранить сгенерированный штрих‑код как изображение

Aspose поддерживает множество форматов вывода: PNG, JPEG, BMP, TIFF, SVG и PDF. PNG — без потерь, идеален для веба или UI‑отображения.

```csharp
// Step 4 – export the barcode
string outputPath = @"C:\Barcodes\MacroPdf417.png";
generator.Save(outputPath, BarCodeImageFormat.Png);
Console.WriteLine($"Barcode saved to {outputPath}");
```

При запуске программы вы найдете PNG‑файл, похожий на иллюстрацию ниже.

![Штрих‑код MacroPdf417, сгенерированный Aspose в C#](placeholder-image.png){.img-fluid alt="как создать штрих‑код с Aspose в C#"}

> **Ожидаемый результат:** PNG‑изображение размером 300 × 150 пикселей, показывающее штрих‑код MacroPdf417, который кодирует текст «Sample» вместе с указанными макро‑метаданными.

## Полный, исполняемый пример

Объединив всё вместе, получаем полную программу, которую можно скопировать, вставить и запустить:

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;
using System;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // Create the generator for MacroPdf417
            using (BarcodeGenerator generator = new BarcodeGenerator(
                       EncodeTypes.MacroPdf417, "Sample"))
            {
                // Appearance settings
                generator.Parameters.Barcode.XDimension.Pixels = 2;
                generator.Parameters.Barcode.Pdf417.Columns = 5;

                // MacroPdf417 specific data
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
                generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;
                generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";
                generator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234;
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000;
                generator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2019, 11, 1);
                generator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
                generator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
                generator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;

                // Save as PNG
                string outputPath = @"C:\Barcodes\MacroPdf417.png";
                generator.Save(outputPath, BarCodeImageFormat.Png);
                Console.WriteLine($"Barcode saved to {outputPath}");
            }
        }
    }
}
```

Запустите программу командой `dotnet run` (или нажмите **F5** в Visual Studio). После выполнения проверьте, что PNG‑файл существует и открывается без ошибок.

## Часто задаваемые вопросы и обработка граничных случаев

### Что если мне нужен другой формат изображения?
Aspose поддерживает `BarCodeImageFormat.Jpeg`, `Bmp`, `Tiff`, `Svg` и `Pdf`. Просто замените `BarCodeImageFormat.Png` на нужное значение перечисления.

### Как автоматически генерировать несколько сегментов?
Можно поместить приведённый выше код в цикл, увеличивая `MacroPdf417SegmentID` на каждой итерации и обновляя строку данных. Не забудьте оставить `MacroPdf417SegmentsCount` одинаковым для всех сегментов.

### Что если данные превышают ёмкость одного символа MacroPdf417?
MacroPdf417 предназначен для больших полезных нагрузок, но каждый штрих‑код имеет теоретический максимум (≈ 1,1 KB на сегмент). Разбейте исходный файл на части, подходящие под это ограничение, и кодируйте каждую часть как отдельный сегмент.

### Нужно ли вычислять контрольную сумму вручную?
Aspose может автоматически генерировать контрольную сумму CCITT‑16, если установить `MacroPdf417Checksum` в `0`. В примере мы указали фиксированное значение для иллюстрации; в продакшн‑коде обычно позволяют библиотеке вычислять её самостоятельно.

### Как изменить цвета переднего и заднего плана штрих‑кода?
Используйте свойства `BarColor` и `BackColor`:

```csharp
generator.Parameters.Barcode.BarColor = System.Drawing.Color.DarkBlue;
generator.Parameters.Barcode.BackColor = System.Drawing.Color.White;
```

## Заключение

Теперь вы знаете, **как генерировать штрих‑код** в C# с помощью Aspose.BarCode и, конкретно, **как создать штрих‑код с Aspose** для симбологии MacroPdf417. Руководство охватило установку, настройку внешнего вида и макро‑специфических полей.

## Что стоит изучить дальше?

Следующие руководства охватывают близко связанные темы, построенные на техниках, продемонстрированных в этом пособии. Каждый ресурс включает полностью работающие примеры кода с пошаговыми объяснениями, чтобы помочь вам освоить дополнительные возможности API и исследовать альтернативные подходы в собственных проектах.

- [Как генерировать DataMatrix штрих‑коды с помощью Aspose.BarCode для .NET – пошаговое руководство](/barcode/english/net/datamatrix-barcode-configuration/)
- [Как создать изображение штрих‑кода PDF417 в C# с Aspose](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-image-in-c-with-aspose/)
- [Как генерировать Aztec штрих‑код с пользовательским соотношением сторон с помощью Aspose.BarCode для .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}