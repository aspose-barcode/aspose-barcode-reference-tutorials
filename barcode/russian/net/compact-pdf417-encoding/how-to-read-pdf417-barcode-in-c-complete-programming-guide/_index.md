---
category: general
date: 2026-11-27
description: как считать штрих‑код PDF417 в C# из изображения с помощью Aspose.BarCode
  – пошаговое руководство с полным примером кода и советами по устранению неполадок.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to read pdf417 barcode
- read barcode from image c#
- C# barcode decoding
- BarCodeReader class
- DecodeType.MacroPdf417
- BarCodeResult properties
language: ru
lastmod: 2026-11-27
og_description: как быстро считывать штрих‑код PDF417 в C#. Узнайте, как декодировать
  штрих‑коды PDF417 с изображений с помощью Aspose.BarCode, полный код и лучшие практики.
og_image_alt: Console output showing how to read PDF417 barcode in C#
og_title: Как считать штрих‑код PDF417 в C# – пошаговое руководство
schemas:
- author: Aspose
  dateModified: '2026-11-27'
  description: how to read pdf417 barcode in C# from an image using Aspose.BarCode
    – step‑by‑step guide with full code example and troubleshooting tips.
  headline: How to read PDF417 barcode in C# – complete programming guide
  type: TechArticle
- description: how to read pdf417 barcode in C# from an image using Aspose.BarCode
    – step‑by‑step guide with full code example and troubleshooting tips.
  name: How to read PDF417 barcode in C# – complete programming guide
  steps:
  - name: Create a new console project
    text: 'Open a terminal (or PowerShell) and run:'
  - name: Install the Aspose.BarCode NuGet package
    text: 'Aspose.BarCode provides the `BarCodeReader` class used in the example.
      Install it with:'
  - name: Add the code shown above
    text: Replace the content of `Program.cs` with the full snippet from the previous
      section. The code demonstrates **C# barcode decoding** and shows how to access
      **BarCodeResult properties** such as `CodeTypeName`, `CodeText`, and the macro‑specific
      `MacroPdf417FileID`.
  - name: Run the application
    text: '```bash dotnet run ```'
  - name: Handle multiple barcodes and error cases
    text: 'Real‑world images may hold more than one barcode or none at all. Wrap the
      reading logic in a `try`/`catch` block to surface parsing errors, and check
      `reader.HasBarcodes` before iterating:'
  - name: Optional – Decode other barcode types from the same image
    text: 'If you later need to **read barcode from image c#** for other symbologies,
      simply change the `DecodeType` argument:'
  type: HowTo
tags:
- barcode
- C#
- Aspose.BarCode
title: Как читать штрих‑код PDF417 в C# – полное руководство по программированию
url: /ru/net/compact-pdf417-encoding/how-to-read-pdf417-barcode-in-c-complete-programming-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Как читать PDF417 штрих‑код в C# – полное руководство по программированию

Если вам нужно **how to read pdf417 barcode** из изображения, это руководство покажет вам точные шаги. С помощью Aspose.BarCode для .NET вы можете декодировать PDF417 штрих‑код одним вызовом метода, а руководство проведет вас через каждую необходимую строку кода.

Чтение штрих‑кода с изображения — распространённая задача при создании сканеров инвентаря, систем проверки билетов или конвейеров обработки документов. В этом учебнике вы узнаете, как настроить окружение, установить необходимый пакет и написать надёжное C#‑приложение, которое считывает PDF417 штрих‑код и извлекает его расширенные поля данных. Внешние сервисы не требуются; всё работает локально.

> **Prerequisites**  
> • .NET 6.0 SDK или более поздняя версия, установленная  
> • Базовые знания C# и консольных приложений  
> • Доступ к файлу изображения, содержащему PDF417 (или Macro PDF417) штрих‑код  

Мы также рассмотрим альтернативы **read barcode from image c#**, объясним самые полезные свойства объекта `BarCodeResult` и дадим советы по обработке нескольких штрих‑кодов на одном изображении.

---

## Как читать PDF417 штрих‑код с изображения в C#

Первый важный шаг — создать `BarCodeReader`, указывающий путь к изображению и сообщающий библиотеке, какой тип штрих‑кода искать. Указав `DecodeType.MacroPdf417`, вы ограничите сканирование вариантами PDF417, что повышает скорость и точность.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

namespace Pdf417ReaderDemo
{
    class Program
    {
        static void Main(string[] args)
        {
            // Path to the image that contains the PDF417 barcode
            string imagePath = @"C:\Barcodes\Pdf417Sample.png";

            // Initialize the reader for Macro PDF417 barcodes
            using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
            {
                // Iterate through all detected barcodes
                foreach (BarCodeResult result in reader.ReadBarCodes())
                {
                    Console.WriteLine($"Code Type : {result.CodeTypeName}");
                    Console.WriteLine($"Code Text : {result.CodeText}");

                    // Macro PDF417 specific extended information
                    if (result.Extended?.Pdf417?.MacroPdf417FileID != null)
                    {
                        Console.WriteLine($"Macro PDF417 File ID : {result.Extended.Pdf417.MacroPdf417FileID}");
                    }

                    // Show confidence and symbology details
                    Console.WriteLine($"Code Confidence : {result.CodeTextConfidence}");
                    Console.WriteLine($"Is Mirror Image : {result.IsMirrored}");
                    Console.WriteLine(new string('-', 40));
                }
            }
        }
    }
}
```

**Why this works** – Конструктор `BarCodeReader` получает путь к изображению и `DecodeType`. `MacroPdf417` сообщает движку искать семейство PDF417, включая макро‑расширение, которое несёт дополнительные метаданные, такие как идентификатор файла. Метод `ReadBarCodes()` возвращает перечисление объектов `BarCodeResult`, каждый из которых представляет обнаруженный штрих‑код.

### Шаг 1: Создать новый консольный проект

Откройте терминал (или PowerShell) и выполните:

```bash
dotnet new console -n Pdf417ReaderDemo
cd Pdf417ReaderDemo
```

Создание нового проекта изолирует демонстрацию и гарантирует, что файл `csproj` будет содержать только те зависимости, которые вы добавите дальше.

### Шаг 2: Установить NuGet‑пакет Aspose.BarCode

Aspose.BarCode предоставляет класс `BarCodeReader`, используемый в примере. Установите его с помощью:

```bash
dotnet add package Aspose.BarCode --version 23.12
```

Пакет включает поддержку всех 1D и 2D символогий, включая PDF417 и его макро‑вариант.

### Шаг 3: Добавить показанный выше код

Замените содержимое `Program.cs` полным фрагментом из предыдущего раздела. Код демонстрирует **C# barcode decoding** и показывает, как получить доступ к **BarCodeResult properties**, таким как `CodeTypeName`, `CodeText` и макроспецифическому `MacroPdf417FileID`.

### Шаг 4: Запустить приложение

```bash
dotnet run
```

Если изображение содержит читаемый PDF417 штрих‑код, консоль выведет что‑то похожее на:

```
Code Type : PDF417
Code Text : https://example.com/invoice/12345
Macro PDF417 File ID : 7
Code Confidence : 98.7
Is Mirror Image : False
----------------------------------------
```

Если на изображении нет PDF417 штрих‑кода, цикл просто завершится без вывода.

### Шаг 5: Обрабатывать несколько штрих‑кодов и ошибки

В реальных изображениях может быть более одного штрих‑кода или их может не быть вовсе. Оберните логику чтения в блок `try`/`catch`, чтобы отлавливать ошибки парсинга, и проверьте `reader.HasBarcodes` перед итерацией:

```csharp
using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
{
    if (!reader.HasBarcodes)
    {
        Console.WriteLine("No PDF417 barcodes detected.");
        return;
    }

    foreach (BarCodeResult result in reader.ReadBarCodes())
    {
        // existing processing code...
    }
}
```

**Pro tip:** При работе с низкокачественными сканами регулируйте свойство `Resolution` у `BarCodeReader` (например, `reader.Resolution = 300;`). Более высокая разрешающая способность улучшает обнаружение, но может увеличить нагрузку на процессор.

### Шаг 6: Необязательно – декодировать другие типы штрих‑кодов с того же изображения

Если позже вам понадобится **read barcode from image c#** для других символогий, просто измените аргумент `DecodeType`:

```csharp
using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.AllSupportedTypes))
{
    // This will detect QR, Code128, DataMatrix, etc.
}
```

Класс `BarCodeResult` одинаково работает для любого типа, поэтому вы можете переиспользовать цикл обработки без изменений.

---

## Понимание ключевых классов

| Class | Назначение | Самые полезные члены |
|-------|------------|----------------------|
| `BarCodeReader` | Открывает изображение и сканирует его на наличие штрих‑кодов | `ReadBarCodes()`, `HasBarcodes`, `Resolution` |
| `BarCodeResult` | Содержит информацию об одном обнаруженном штрих‑коде | `CodeTypeName`, `CodeText`, `CodeTextConfidence`, `Extended` |
| `Extended.Pdf417` | Предоставляет макроспецифичные данные для PDF417 | `MacroPdf417FileID`, `MacroPdf417SegmentCount`, `MacroPdf417SegmentIndex` |

Знание этих членов позволяет извлекать не только человекочитаемый текст, но и структурированные метаданные, которые Macro PDF417 встраивает, что часто требуется для пакетной обработки многостраничных документов.

---

## Распространённые ошибки и как их избежать

* **Incorrect `DecodeType`** – Использование `DecodeType.Pdf417` вместо `MacroPdf417` пропустит макро‑расширения. Выбирайте точный тип, соответствующий вашему штрих‑коду.  
* **Unsupported image format** – Aspose.BarCode читает PNG, JPEG, BMP, TIFF и GIF. Если у вас RAW‑изображение, сначала конвертируйте его.  
* **Low image contrast** – Предобработайте изображение (увеличьте контраст или бинаризуйте) перед передачей в `BarCodeReader`. Библиотека также предлагает `reader.ImageProcessingOptions`.  
* **Large files** – Для сканов с очень высоким разрешением задайте `reader.MaxBarcodesPerPage`, чтобы ограничить потребление памяти.

---

## Заключение

Теперь вы знаете **how to read pdf417 barcode** в C# с помощью Aspose.BarCode, от настройки проекта до обработки макроспецифичных полей. Полный, готовый к запуску пример демонстрирует **C# barcode decoding**, показывает, как получить доступ к **BarCodeResult properties**, и даёт практические советы для надёжного сканирования.  

Далее изучайте связанные темы, такие как **read barcode from image c#** для QR‑кодов, интегрируйте чтение штрих‑кодов в ASP.NET Core API или экспериментируйте с пакетной обработкой множества изображений. Класс `BarCodeReader` работает со всеми поддерживаемыми символогиями, поэтому вы можете расширять это решение под любой штрих‑код, с которым сталкивается ваше приложение.

Удачной разработки, и не стесняйтесь адаптировать пример под ваш рабочий процесс!

## Что изучать дальше?

Следующие учебники охватывают тесно связанные темы, построенные на техниках, продемонстрированных в этом руководстве. Каждый ресурс включает полностью работающие примеры кода с пошаговыми объяснениями, помогающими освоить дополнительные возможности API и исследовать альтернативные подходы к реализации в ваших проектах.

- [How to read macro PDF417 barcode in C# with Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/how-to-read-macro-pdf417-barcode-in-c-with-aspose-barcode/)
- [How to read PDF417 barcode in C# – full barcode reader guide](/barcode/english/net/compact-pdf417-encoding/how-to-read-pdf417-barcode-in-c-full-barcode-reader-guide/)
- [How to Create PDF417 Barcode with Aspose – Complete Step‑by‑Step Guide](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-with-aspose-complete-step-by-st/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}