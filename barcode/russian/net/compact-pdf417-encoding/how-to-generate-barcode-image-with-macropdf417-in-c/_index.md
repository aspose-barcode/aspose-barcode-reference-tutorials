---
category: general
date: 2026-11-23
description: Узнайте, как генерировать изображение штрихкода с помощью Aspose.BarCode
  для .NET с метаданными MacroPdf417 на C#. Следуйте полному пошаговому руководству.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to generate barcode image
- MacroPdf417 barcode
- Aspose.BarCode for .NET
- set barcode metadata
- barcode image format
- C# barcode generation
language: ru
lastmod: 2026-11-23
og_description: Как сгенерировать изображение штрихкода с помощью Aspose.BarCode для
  .NET. Этот учебник демонстрирует настройку метаданных MacroPdf417 и генерацию штрихкода
  на C#.
og_image_alt: Barcode image generated with MacroPdf417 using C#
og_title: Как сгенерировать изображение штрихкода с помощью MacroPdf417 в C#
schemas:
- author: Aspose
  dateModified: '2026-11-23'
  description: Learn how to generate barcode image using Aspose.BarCode for .NET with
    MacroPdf417 metadata in C#. Follow the complete step‑by‑step guide.
  headline: How to generate barcode image with MacroPdf417 in C#
  type: TechArticle
- description: Learn how to generate barcode image using Aspose.BarCode for .NET with
    MacroPdf417 metadata in C#. Follow the complete step‑by‑step guide.
  name: How to generate barcode image with MacroPdf417 in C#
  steps:
  - name: Open a terminal or the Package Manager Console in Visual Studio.
    text: Open a terminal or the Package Manager Console in Visual Studio.
  - name: 'Run the following command:'
    text: 'Run the following command:'
  - name: '**Visual inspection** – The barcode should display a series of stacked
      columns with a quiet zone (white margin) around it.'
    text: '**Visual inspection** – The barcode should display a series of stacked
      columns with a quiet zone (white margin) around it.'
  - name: '**Decoding test** – Use a barcode scanner app or the Aspose.BarCode `BarCodeReader`
      class to read the image back and confirm that all metadata fields are correctly
      embedded.'
    text: '**Decoding test** – Use a barcode scanner app or the Aspose.BarCode `BarCodeReader`
      class to read the image back and confirm that all metadata fields are correctly
      embedded.'
  type: HowTo
tags:
- barcode
- C#
- Aspose
- PDF417
title: Как сгенерировать изображение штрихкода с помощью MacroPdf417 в C#
url: /ru/net/compact-pdf417-encoding/how-to-generate-barcode-image-with-macropdf417-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Как сгенерировать изображение штрих‑кода MacroPdf417 на C#

Если вам нужно **создать изображение штрих‑кода** в приложении .NET, это руководство покажет, как сделать это с помощью **Aspose.BarCode for .NET**. Мы пройдем процесс создания **штрих‑кода MacroPdf417**, настройки его метаданных и сохранения результата в файл PNG.

В этом учебнике рассматривается всё: от установки библиотеки до написания полностью работающей консольной программы. К концу вы получите готовый пример кода, генерирующий высококачественное изображение штрих‑кода, а также поймёте, как **устанавливать метаданные штрих‑кода**, выбирать **формат изображения штрих‑кода** и устранять распространённые проблемы. Предыдущий опыт работы с Aspose не требуется — достаточно базовых знаний C#.

## Установить Aspose.BarCode for .NET

Прежде чем **создавать изображение штрих‑кода**, необходимо установить пакет Aspose.BarCode через NuGet.

1. Откройте терминал или консоль диспетчера пакетов в Visual Studio.  
2. Выполните следующую команду:

```bash
dotnet add package Aspose.BarCode
```

Пакет добавляет пространство имён `Aspose.BarCode.Generation`, в котором находится класс `BarcodeGenerator`, используемый для **генерации штрих‑кода на C#**.

> **Pro tip:** Используйте последнюю стабильную версию (на ноябрь 2026 текущая версия — 24.11), чтобы получить новейшие функции и исправления ошибок.

## Создать экземпляр BarcodeGenerator

Первый шаг кода создаёт `BarcodeGenerator`, настроенный для типа **штрих‑кода MacroPdf417**, и передаёт строку данных, которую нужно закодировать.

```csharp
using System;
using Aspose.BarCode.Generation;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // Step 1: Create a BarcodeGenerator for MacroPdf417 with the desired text
            using (BarcodeGenerator barcodeGenerator =
                   new BarcodeGenerator(EncodeTypes.MacroPdf417, "Åspóse.Barcóde©"))
            {
                // Subsequent configuration goes here...
```

Блок `using` гарантирует корректное освобождение генератора и всех неуправляемых ресурсов.

## Настроить базовый внешний вид

Читаемый штрих‑код начинается с разумных размеров. Здесь мы задаём ширину пикселя каждого модуля (`XDimension`) и количество столбцов для матрицы PDF417.

```csharp
                // Step 2: Set basic barcode appearance
                barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;   // pixel width of a module
                barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 5;    // number of columns
```

*Почему именно такие значения?*  
- **XDimension** определяет толщину каждой полосы; 2 пикселя хорошо подходят для просмотра на экране и большинства принтеров.  
- **Columns** влияют на общую ширину; небольшое количество столбцов делает штрих‑код компактным, сохраняя при этом ёмкость коррекции ошибок.

## Установить метаданные штрих‑кода (специфично для MacroPdf417)

MacroPdf417 позволяет встраивать информацию уровня файла непосредственно в штрих‑код. Здесь вы **устанавливаете метаданные штрих‑кода**, такие как идентификатор файла, идентификатор сегмента и временные метки.

```csharp
                // Step 3: Configure MacroPdf417 specific metadata
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234; // CCITT‑16 example
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400000;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2019, 11, 1);
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;
```

### Что означает каждое свойство

| Свойство | Назначение |
|----------|------------|
| **MacroPdf417FileID** | Уникальный идентификатор логического файла, к которому относится штрих‑код. |
| **MacroPdf417SegmentID** | Индекс текущего сегмента (нумерация с нуля). |
| **MacroPdf417SegmentsCount** | Общее количество сегментов, составляющих весь файл. |
| **MacroPdf417FileName** | Человекочитаемое имя исходного файла. |
| **MacroPdf417Checksum** | Необязательная контрольная сумма CCITT‑16 для проверки целостности данных. |
| **MacroPdf417FileSize** | Ожидаемый размер оригинального файла в байтах. |
| **MacroPdf417TimeStamp** | Дата и время генерации штрих‑кода — полезно для отслеживания версий. |
| **MacroPdf417Addressee / Sender** | Пользовательские строки, которые могут содержать информацию о маршрутизации. |
| **MacroPdf417Terminator** | Указывает, является ли этот сегмент последним (`Set`) или нет (`Unset`). |

> **Edge case:** Если вы планируете разбивать большой документ на множество сегментов, сохраняйте одинаковое значение `SegmentsCount` во всех сгенерированных штрих‑кодах. Несоответствие количества приведёт к ошибкам декодирования.

## Выбрать формат изображения штрих‑кода и сохранить

Aspose поддерживает множество **форматов изображений штрих‑кода** (PNG, JPEG, BMP, TIFF и др.). PNG — без потерь и хорошо подходит для большинства веб‑ и печатных сценариев.

```csharp
                // Step 4: Save the generated barcode image
                string outputPath = @"YOUR_DIRECTORY/ExtPDF417Meta.png";
                barcodeGenerator.Save(outputPath, BarCodeImageFormat.Png);
                Console.WriteLine($"Barcode image saved to: {outputPath}");
            } // end using
        }
    }
}
```

Замените `YOUR_DIRECTORY` на абсолютный или относительный путь к папке, в которую приложение имеет право записи.

При запуске программы вы увидите сообщение в консоли, подтверждающее расположение файла. Откройте PNG‑файл в любом просмотрщике изображений — вы увидите чёткий **штрих‑код MacroPdf417**, который кодирует переданный текст и заданные метаданные.

### Ожидаемый вывод

```
Barcode image saved to: C:\Projects\BarcodeDemo\ExtPDF417Meta.png
```

Размер файла изображения будет примерно 30‑40 KB, в зависимости от выбранных `XDimension` и количества столбцов.

## Проверить штрих‑код и устранить проблемы

1. **Визуальная проверка** — Штрих‑код должен отображать серию вертикальных столбцов с тихой зоной (белым полем) вокруг него.  
2. **Тест декодирования** — Используйте приложение‑сканер штрих‑кодов или класс `BarCodeReader` из Aspose.BarCode, чтобы прочитать изображение и убедиться, что все поля метаданных корректно внедрены.  



## Что вам следует изучить дальше?

Следующие учебники охватывают тесно связанные темы, расширяющие техники, продемонстрированные в этом руководстве. Каждый ресурс содержит полностью рабочие примеры кода с пошаговыми объяснениями, чтобы помочь вам освоить дополнительные возможности API и исследовать альтернативные подходы в собственных проектах.

- [Создать изображение штрих‑кода PDF417 с Aspose.BarCode в C# – пошаговое руководство](/barcode/english/net/compact-pdf417-encoding/how-to-create-barcode-image-with-pdf417-in-c-step-by-step-gu/)
- [Как сгенерировать штрих‑код с пользовательским текстом, используя Aspose.BarCode for .NET](/barcode/english/net/one-dimensional-barcode-types/how-to-generate-barcode-with-custom-text-using-aspose-barcod/)
- [Как считывать штрих‑коды из изображения на C# с Aspose.BarCode – пошаговое руководство](/barcode/english/net/one-dimensional-barcode-types/how-to-read-barcodes-from-image-using-c-step-by-step-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}