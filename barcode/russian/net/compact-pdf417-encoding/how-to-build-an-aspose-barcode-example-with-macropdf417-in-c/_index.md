---
category: general
date: 2026-10-12
description: Узнайте, как создать пример штрихкода Aspose на C#, генерирующий штрихкод
  MacroPdf417 с полными метаданными, и как считать его обратно с помощью BarCodeReader.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- aspose barcode example
- macroPdf417 barcode
- barcode metadata
- c# barcode generation
- BarCodeReader
language: ru
lastmod: 2026-10-12
og_description: Пример Aspose Barcode на C#, показывающий, как создать штрих‑код MacroPdf417
  с встроенными метаданными и считать его обратно с помощью BarCodeReader.
og_image_alt: Screenshot of an Aspose barcode example displaying a MacroPdf417 barcode
  with metadata
og_title: Создайте пример штрихкода Aspose с MacroPdf417 на C#
schemas:
- author: Aspose
  dateModified: '2026-10-12'
  description: Learn how to create an Aspose barcode example in C# that generates
    a MacroPdf417 barcode with full metadata and reads it back using BarCodeReader.
  headline: How to build an Aspose barcode example with MacroPdf417 in C#
  type: TechArticle
tags:
- Aspose.BarCode
- C#
- Barcode
title: Как создать пример штрихкода Aspose с MacroPdf417 на C#
url: /ru/net/compact-pdf417-encoding/how-to-build-an-aspose-barcode-example-with-macropdf417-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Как создать пример Aspose barcode с MacroPdf417 на C#

Если вам нужен **aspose barcode example**, который создает штрих‑код MacroPdf417 и считывает встроенные метаданные, это руководство покажет полный рабочий процесс. Вы увидите, как настроить генератор, внедрить информацию уровня файла, сохранить изображение и затем декодировать те же данные с помощью `BarCodeReader`.

В учебнике рассматривается всё, что необходимо знать для **C# barcode generation** с Aspose.BarCode, включая распространённые подводные камни и советы по работе с большими идентификаторами файлов или пользовательскими метками времени.

## Что вам понадобится

Перед началом убедитесь, что у вас есть:

* .NET 6.0 SDK или новее (код работает с .NET Core и .NET Framework)
* Visual Studio 2022 или любая IDE, поддерживающая C#
* Действующая лицензия Aspose.BarCode (бесплатная пробная версия подходит для разработки)
* Пакет NuGet `Aspose.BarCode`, установленный в вашем проекте

Эти предварительные условия гарантируют, что пример запустится без дополнительной настройки.

## Шаг 1: Настройте проект примера Aspose barcode

Создайте новое консольное приложение и добавьте библиотеку Aspose.BarCode:

```bash
dotnet new console -n AsposeMacroPdf417Demo
cd AsposeMacroPdf417Demo
dotnet add package Aspose.BarCode
```

Пакет `Aspose.BarCode` предоставляет `BarcodeGenerator`, `BarCodeReader` и все типы, необходимые для работы с MacroPdf417.

### Зачем нужен этот шаг
Добавление пакета NuGet решает проблемы с перечислениями `EncodeTypes`, `DecodeType` и `BarCodeImageFormat`, используемыми позже. Без пакета компилятор не распознает эти символы, и пример не соберётся.

## Шаг 2: Создайте генератор штрих‑кода MacroPdf417

Откройте **Program.cs** и замените шаблонный код следующим блоком. Этот блок создаёт `BarcodeGenerator`, настроенный для символьного набора MacroPdf417, и задаёт базовые параметры отображения.

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Enums;
using System;

class Program
{
    static void Main()
    {
        // Step 2.1: Initialize the generator with source text.
        using (BarcodeGenerator barcodeGenerator =
               new BarcodeGenerator(EncodeTypes.MacroPdf417, "Sample data"))
        {
            // Adjust the module size – 2 pixels per X‑dimension.
            barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;

            // Reduce the number of columns to keep the barcode compact.
            barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 5;

            // Step 2.2: Embed MacroPdf417 metadata.
            // ---------------------------------------------------------
            // The following properties are optional but illustrate
            // how a full‑featured barcode can carry file‑level data.
            // ---------------------------------------------------------
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234; // CCITT‑16
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000;
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp =
                new DateTime(2024, 9, 1);
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Terminator =
                Pdf417MacroTerminator.Set;

            // Step 2.3: Save the barcode image.
            const string outPath = "ExtPDF417Meta.png";
            barcodeGenerator.Save(outPath, BarCodeImageFormat.Png);
            Console.WriteLine($"Barcode saved to {outPath}");
        }
```

#### Объяснение ключевых свойств

| Свойство | Назначение | Типичный диапазон / примечания |
|----------|------------|--------------------------------|
| `MacroPdf417FileID` | Уникальный идентификатор всего файла | Должен быть ≤ 2³¹‑1 |
| `MacroPdf417SegmentID` | Индекс текущего сегмента | Начинается с 0 |
| `MacroPdf417SegmentsCount` | Общее количество сегментов в файле | Должно быть ≥ SegmentID |
| `MacroPdf417FileName` | Человекочитаемое имя файла | До 255 символов |
| `MacroPdf417Checksum` | CCITT‑16 контрольная сумма оригинального файла | Вычисляется внешним инструментом при необходимости |
| `MacroPdf417FileSize` | Размер оригинального файла в байтах | Полезно для проверки |
| `MacroPdf417TimeStamp` | Дата/время создания файла | Используйте UTC для согласованности |
| `MacroPdf417Addressee` / `MacroPdf417Sender` | Дополнительная информация о получателе/отправителе | Любая строка до 255 символов |
| `MacroPdf417Terminator` | Помечает последний сегмент | Установите `Set` для последнего сегмента |

Эти поля составляют **barcode metadata**, которые позже может извлечь считыватель.

## Шаг 3: Декодируйте штрих‑код и отобразите метаданные

После сохранения изображения та же программа продолжает работу, открывая файл с помощью `BarCodeReader`. Добавьте следующий код внутри метода `Main`, после предыдущего блока `using`:

```csharp
        // Step 3: Open the saved image with a MacroPdf417 reader.
        using (BarCodeReader barcodeReader =
               new BarCodeReader("ExtPDF417Meta.png", DecodeType.MacroPdf417))
        {
            // Step 3.1: Iterate through all decoded results.
            foreach (BarCodeResult result in barcodeReader.ReadBarCodes())
            {
                // The Extended property holds the MacroPdf417 specific fields.
                var meta = result.Extended.Pdf417;
                Console.WriteLine($"FileID: {meta.MacroPdf417FileID}");
                Console.WriteLine($"SegmentID: {meta.MacroPdf417SegmentID}");
                Console.WriteLine($"SegmentsCount: {meta.MacroPdf417SegmentsCount}");
                Console.WriteLine($"FileName: {meta.MacroPdf417FileName}");
                Console.WriteLine($"Checksum: {meta.MacroPdf417Checksum}");
                Console.WriteLine($"FileSize: {meta.MacroPdf417FileSize}");
                Console.WriteLine($"Timestamp: {meta.MacroPdf417TimeStamp}");
                Console.WriteLine($"Addressee: {meta.MacroPdf417Addressee}");
                Console.WriteLine($"Sender: {meta.MacroPdf417Sender}");
                Console.WriteLine($"Terminator: {meta.MacroPdf417Terminator}");
            }
        }
    }
}
```

### Зачем важно считывать обратно
`BarCodeReader` проверяет, что внедрённые метаданные корректно закодированы. Если какое‑либо свойство отсутствует или выходит за пределы, считыватель вернёт `null` для этого поля, позволяя обработать ошибку gracefully.

## Шаг 4: Запустите и проверьте вывод

Выполните программу:

```bash
dotnet run
```

Вы должны увидеть вывод в консоли, похожий на:

```
Barcode saved to ExtPDF417Meta.png
FileID: 12345678
SegmentID: 12
SegmentsCount: 20
FileName: file01
Checksum: 1234
FileSize: 400000
Timestamp: 9/1/2024 12:00:00 AM
Addressee: street
Sender: aspose
Terminator: Set
```

Если значения совпадают с теми, которые вы задали в Шаге 2, **aspose barcode example** работает как ожидалось.

## Пограничные случаи и рекомендации по лучшим практикам

| Ситуация | На что обратить внимание | Рекомендованное решение |
|----------|--------------------------|--------------------------|
| **FileID превышает диапазон 32‑бит** | Aspose генерирует `ArgumentOutOfRangeException`. | Сохраняйте ID ≤ 2 147 483 647 или разбейте файл на несколько блоков MacroPdf417. |
| **Метка времени в локальном времени** | Считыватели в другом часовом поясе могут неправильно интерпретировать значение. | Сохраняйте метки времени в UTC (`DateTime.UtcNow`) и при необходимости преобразуйте при отображении. |
| **Большой размер файла** | `MacroPdf417FileSize` имеет тип `int`; значения > 2 GB переполняются. | Используйте пользовательское поле или разбейте файл на более мелкие сегменты. |
| **Отсутствующий сегмент** | Если `SegmentID` не последовательный, восстановление не удаётся. | Проверьте порядок сегментов перед кодированием или используйте настройки коррекции ошибок. |
| **Неподдерживаемый формат изображения** | Сохранение в BMP может значительно увеличить размер. | PNG — хороший вариант по умолчанию; JPEG можно использовать, если допускаете сжатие с потерями. |

**Pro tip:** При генерации большого количества штрих‑кодов пакетно переиспользуйте один экземпляр `BarcodeGenerator` и меняйте только `EncodeTypes` и исходный текст. Это уменьшает выделения памяти и ускоряет обработку.

## Связанные темы, которые стоит изучить дальше

* **Другие макросимвольные наборы** – Aspose также поддерживает MacroPdf417 с уровнями коррекции ошибок.  
* **Встраивание штрих‑кодов в PDF** – Сочетайте `Aspose.PDF` с генератором штрих‑кодов для создания печатных документов.  
* **Интеграция с ASP.NET Core** – Подавайте сгенерированные штрих‑коды напрямую из веб‑API.  
* **Сканирование с мобильных устройств** – Используйте SDK `Aspose.BarCode.Cloud` для кросс‑платформенного декодирования.

Эти темы естественно расширяют **aspose barcode example** и углубляют ваши знания в **C# barcode generation**.

## Заключение

Теперь у вас есть полностью рабочий **aspose barcode example**, который создаёт штрих‑код MacroPdf417, внедряет богатые **barcode metadata**, сохраняет изображение и считывает данные обратно с помощью `BarCodeReader`. Следуя описанным шагам, вы сможете адаптировать код под разные идентификаторы файлов, метки времени или даже другие типы штрих‑кодов, поддерживаемые Aspose.

Не стесняйтесь экспериментировать с дополнительными полями метаданных, менять формат изображения или интегрировать генератор в более крупное приложение. Приятного кодинга!

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}