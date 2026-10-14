---
category: general
date: 2026-10-05
description: Aspose Barcode Generator C# позволяет легко добавлять макроданные и генерировать
  штрихкоды PDF417. Узнайте пошагово, как добавить макрометаданные и создать изображение
  PDF417.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- aspose barcode generator c#
- how to add macro
- how to generate pdf417
language: ru
lastmod: 2026-10-05
og_description: Aspose Barcode Generator C# показывает, как добавить макро‑метаданные
  и сгенерировать штрих‑код PDF417 за несколько строк кода.
og_image_alt: Screenshot of a MacroPdf417 barcode created with Aspose Barcode Generator
  C#
og_title: Aspose Barcode Generator C# – добавить макрос и сгенерировать штрих‑код
  PDF417
schemas:
- author: Aspose
  dateModified: '2026-10-05'
  description: Aspose Barcode Generator C# lets you add macro data and generate PDF417
    barcodes effortlessly. Learn step‑by‑step how to add macro metadata and create
    a PDF417 image.
  headline: How to use Aspose Barcode Generator C# for a MacroPdf417 barcode
  type: TechArticle
tags:
- barcode
- csharp
- aspose
title: Как использовать Aspose Barcode Generator C# для штрихкода MacroPdf417
url: /ru/net/compact-pdf417-encoding/how-to-use-aspose-barcode-generator-c-for-a-macropdf417-barc/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Как использовать Aspose Barcode Generator C# для штрихкода MacroPdf417

Если вам нужно создать штрихкод MacroPdf417 на C#, **Aspose Barcode Generator C#** предоставляет лаконичное API, которое обрабатывает как изображение штрихкода, так и необходимые макро‑метаданные. В этом руководстве показано, как добавить макро‑информацию и сгенерировать изображение PDF417 всего за несколько шагов.

Вы узнаете, как настроить визуальные параметры, внедрить макро‑поля, такие как идентификатор файла и метка времени, и сохранить результат в формате PNG. Внешние инструменты не требуются — только библиотека Aspose.BarCode и среда разработки .NET.

## Предварительные требования

Перед началом убедитесь, что у вас есть:

* .NET 6.0 или новее установленный  
* Visual Studio 2022 (или любой IDE для C#)  
* Лицензионная или оценочная копия **Aspose.BarCode for .NET**  

Код работает на Windows, Linux и macOS, поскольку библиотека не зависит от платформы.

## Шаг 1: Установите пакет Aspose.BarCode NuGet

Откройте ваш проект в Visual Studio, затем выполните следующую команду в **Package Manager Console**:

```powershell
Install-Package Aspose.BarCode
```

Это добавит сборку `Aspose.BarCode` и её зависимости в ваш проект.

## Шаг 2: Создайте экземпляр генератора штрихкода

Первая строка создаёт объект `BarcodeGenerator` для символьного набора **MacroPdf417** и задаёт текст, который нужно закодировать.

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode.BarCodeImageFormat;

// Step 2: Initialise the generator with MacroPdf417 and the payload text
using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MacroPdf417, "Åspóse.Barcóde©"))
{
    // subsequent configuration goes here
}
```

*Почему это важно*: Значение `EncodeTypes.MacroPdf417` сообщает библиотеке, что следует ожидать макро‑связанных полей, которые вы зададите на следующем шаге.

## Шаг 3: Определите визуальное оформление

Вы можете управлять размером каждого модуля (самого маленького чёрного или белого квадрата) и количеством столбцов в матрице PDF417. Настройка `XDimension` влияет на общую разрешающую способность изображения.

```csharp
    // Step 3: Visual settings
    generator.Parameters.Barcode.XDimension.Pixels = 2;          // width of a single module
    generator.Parameters.Barcode.Pdf417.Columns = 5;           // number of columns in the symbol
```

Увеличение `Columns` уменьшает высоту штрихкода, а больший `XDimension` делает изображение чётче на экранах с высоким DPI.

## Шаг 4: Добавьте макро‑метаданные (как добавить macro)

MacroPdf417 требует нескольких дополнительных полей, описывающих исходный файл и его сегментацию. Следующие свойства напрямую соответствуют спецификациям макро‑PDF417:

```csharp
    // Step 4: Macro fields – how to add macro data
    generator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;               // unique file identifier
    generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;                  // current segment number
    generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;              // total number of segments
    generator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";             // optional file name
    generator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234;                // CCITT‑16 placeholder
    generator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000;              // size in bytes
    generator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = 
        new DateTime(2019, 11, 1);                                                   // creation timestamp
    generator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";            // recipient identifier
    generator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";               // sender identifier
    generator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = 
        Pdf417MacroTerminator.Set;                                                   // marks the last segment
```

*Почему эти поля*:  
* `MacroPdf417FileID` связывает все сегменты вместе, обеспечивая возможность сканеру собрать оригинальный документ.  
* `MacroPdf417SegmentID` и `MacroPdf417SegmentsCount` позволяют декодеру знать порядок и общее количество частей.  
* `MacroPdf417FileSize` и `MacroPdf417Checksum` предоставляют контроль целостности, что ценно при передаче больших объёмов данных.

## Шаг 5: Сохраните изображение штрихкода (как сгенерировать pdf417)

Наконец, запишите штрихкод на диск. Метод `Save` принимает путь к файлу и формат изображения. PNG сохраняет чёткие границы штрихкода без артефактов сжатия.

```csharp
    // Step 5: Save the generated barcode – how to generate pdf417 image
    generator.Save("ExtPDF417Meta.png", BarCodeImageFormat.Png);
}
```

После выполнения программы вы найдёте **ExtPDF417Meta.png** в папке вывода. Открытие изображения покажет чистый MacroPdf417 штрихкод, готовый к печати или встраиванию в PDF.

### Ожидаемый результат

| Имя файла          | Формат | Размеры (примерно) |
|--------------------|--------|----------------------|
| ExtPDF417Meta.png  | PNG    | 300 × 150 px (зависит от `XDimension`) |

Сканирование изображения совместимым считывателем PDF417 (например, ZXing, Aspose.BarCode for .NET) возвращает исходный текст **“Åspóse.Barcóde©”** вместе со всеми макро‑полями.

## Распространённые ошибки и как их избежать

| Проблема | Почему происходит | Решение |
|----------|-------------------|---------|
| **Incorrect `EncodeTypes`** | Использование `EncodeTypes.Pdf417` вместо `EncodeTypes.MacroPdf417` отключает макро‑поля. | Всегда создавайте генератор с `EncodeTypes.MacroPdf417`. |
| **Missing macro fields** | Некоторые сканеры игнорируют штрихкод, если обязательные макро‑поля отсутствуют. | Заполните как минимум `FileID`, `SegmentID`, `SegmentsCount` и `Terminator`. |
| **Too small `XDimension`** | Значение меньше 1 пикселя может привести к нечитаемому штрихкоду на дисплеях с низким разрешением. | Держите `XDimension` ≥ 2 пикселя для большинства сценариев отображения и печати. |
| **File path errors** | Указание относительного пути, который не существует, вызывает исключение. | Используйте `Path.Combine(Environment.CurrentDirectory, "ExtPDF417Meta.png")` или абсолютный путь. |

## Полный исходный код

Ниже приведён полностью готовый к запуску пример, который можно скопировать в новый консольный проект.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode.BarCodeImageFormat;

namespace MacroPdf417Demo
{
    class Program
    {
        static void Main()
        {
            // Initialise the generator with MacroPdf417 and the payload text
            using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MacroPdf417, "Åspóse.Barcóde©"))
            {
                // Visual appearance
                generator.Parameters.Barcode.XDimension.Pixels = 2;          // module width
                generator.Parameters.Barcode.Pdf417.Columns = 5;           // number of columns

                // Macro fields – how to add macro
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

                // Save the barcode – how to generate pdf417
                generator.Save("ExtPDF417Meta.png", BarCodeImageFormat.Png);
            }

            Console.WriteLine("MacroPdf417 barcode generated successfully.");
        }
    }
}
```

Запустите программу (`dotnet run`). После выполнения консоль выведет сообщение об успехе, а файл PNG появится в папке вывода проекта.

## Следующие шаги

* **Encode larger data** – Увеличьте `Columns` или скорректируйте `Rows` (через `Pdf417.Rows`), чтобы разместить больше символов.  
* **Embed in PDF** – Используйте Aspose.PDF для вставки сгенерированного PNG в документ.  
* **Scan verification** – Воспользуйтесь `Aspose.BarCode.Reader` для декодирования штрихкода и программной проверки макро‑полей.  

Изучение этих тем углубит ваше понимание **how to generate PDF417** штрихкодов с богатыми макро‑данными и подготовит к реальным сценариям, таким как пакетная обработка документов или безопасный обмен данными.

---

*Счастливого кодинга! Если это руководство оказалось полезным, поделитесь им с коллегами или поставьте звёздочку репозиторию Aspose.BarCode на GitHub.*

## Что изучать дальше?

Следующие руководства охватывают тесно связанные темы, построенные на техниках, продемонстрированных в этом руководстве. Каждый ресурс включает полностью работающие примеры кода с пошаговыми объяснениями, чтобы помочь вам освоить дополнительные возможности API и исследовать альтернативные подходы в своих проектах.

- [Как создать macro PDF417 штрихкод в C# с использованием Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/how-to-create-macro-pdf417-barcode-in-c-using-aspose-barcode/)
- [Как сгенерировать PDF417 штрихкод в C# с помощью Barcode Generator](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-with-barcode-generator/)
- [Пример Aspose barcode: генерация Macro PDF417 в C#](/barcode/english/net/compact-pdf417-encoding/aspose-barcode-example-generate-macro-pdf417-in-c/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}