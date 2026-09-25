---
category: general
date: 2026-08-22
description: Как считывать штрихкоды PDF417 в C# с пошаговым руководством, охватывающим
  чтение нескольких штрихкодов с изображения и извлечение деталей MacroPdf417.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to read pdf417
- read multiple barcodes
- read barcodes image c#
language: ru
lastmod: 2026-08-22
og_description: Как быстро считывать штрихкоды PDF417 в C#. Этот учебник покажет,
  как считывать несколько штрихкодов с изображения и получать расширенную информацию
  MacroPdf417.
og_image_alt: Developer console displaying MacroPdf417 barcode details extracted by
  C# code
og_title: Как читать штрихкоды PDF417 в C# – полное пошаговое руководство
schemas:
- author: Aspose
  dateModified: '2026-08-22'
  description: How to read PDF417 barcodes in C# with a step‑by‑step guide, covering
    how to read multiple barcodes from an image and extract MacroPdf417 details.
  headline: How to read PDF417 barcodes in C# – complete guide
  type: TechArticle
tags:
- barcode
- C#
- Aspose.BarCode
title: Как считывать штрихкоды PDF417 в C# — полное руководство
url: /ru/net/compact-pdf417-encoding/how-to-read-pdf417-barcodes-in-c-complete-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Как читать штрихкоды PDF417 в C# – полное руководство

Если вам нужно **как читать PDF417** штрихкоды в приложении .NET, этот учебник предоставляет готовое решение. Вы узнаете, как считывать несколько штрихкодов с одного изображения, извлекать полный набор данных MacroPdf417 и выводить их в консоль. Подход работает с библиотекой Aspose.BarCode for .NET и требует всего несколько строк кода.

Считывание штрихкодов с изображения — распространённая задача в системах учёта, проверке билетов и управлении документами. К концу этого руководства вы сможете декодировать любой штрихкод PDF417 или MacroPdf417, обрабатывать несколько кодов на одной картинке и понимать расширенные поля, которые предоставляет MacroPdf417.

## Предварительные требования

- .NET 6.0 SDK или новее (код также компилируется с .NET Framework 4.7+)
- Visual Studio 2022 или любой другой редактор C#
- NuGet‑пакет Aspose.BarCode for .NET (`Install-Package Aspose.BarCode`)
- Пример изображения, содержащего штрихкод MacroPdf417 (например, `MacroPdf417.png`)

Дополнительная настройка не требуется; библиотека самостоятельно загружает изображение и выполняет декодирование.

## Как читать штрихкоды PDF417 с изображения в C#

Ядром решения является класс `BarCodeReader`. Он открывает изображение, обнаруживает все штрихкоды указанного типа и возвращает коллекцию объектов `BarCodeResult`. Ниже показан полный консольный пример.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

namespace Pdf417ReaderDemo
{
    class Program
    {
        static void Main()
        {
            // Path to the image that contains one or more MacroPdf417 barcodes
            const string imagePath = @"YOUR_DIRECTORY\MacroPdf417.png";

            // 1️⃣ Initialize the reader for MacroPdf417 barcodes.
            // DecodeType.MacroPdf417 tells the engine to look for the extended PDF417 format.
            using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
            {
                // 2️⃣ Iterate over every barcode found in the image.
                foreach (BarCodeResult result in reader.ReadBarCodes())
                {
                    // 3️⃣ Print basic information.
                    Console.WriteLine($"CodeType: {result.CodeTypeName}");
                    Console.WriteLine($"CodeText: {result.CodeText}");

                    // 4️⃣ Access MacroPdf417 extended fields.
                    // The Extended property contains format‑specific data; for PDF417 it is .Pdf417.
                    var macro = result.Extended.Pdf417;

                    Console.WriteLine($"Pdf417MacroFileID: {macro.MacroPdf417FileID}");
                    Console.WriteLine($"Pdf417MacroSegmentID: {macro.MacroPdf417SegmentID}");
                    Console.WriteLine($"Pdf417MacroSegmentsCount: {macro.MacroPdf417SegmentsCount}");
                    Console.WriteLine($"Pdf417MacroFileName: {macro.MacroPdf417FileName}");
                    Console.WriteLine($"Pdf417MacroChecksum: {macro.MacroPdf417Checksum}");
                    Console.WriteLine($"Pdf417MacroFileSize: {macro.MacroPdf417FileSize}");
                    Console.WriteLine($"Pdf417MacroTimeStamp: {macro.MacroPdf417TimeStamp}");
                    Console.WriteLine($"Pdf417MacroAddressee: {macro.MacroPdf417Addressee}");
                    Console.WriteLine($"Pdf417MacroSender: {macro.MacroPdf417Sender}");
                    Console.WriteLine($"MacroPdf417Terminator: {macro.MacroPdf417Terminator}");

                    Console.WriteLine(new string('-', 40));
                }
            }

            Console.WriteLine("Decoding completed. Press any key to exit.");
            Console.ReadKey();
        }
    }
}
```

### Почему важна каждая строка

| Шаг | Назначение |
|------|------------|
| **1️⃣ Initialize** | Создаёт `BarCodeReader`, привязанный к файлу изображения, и ограничивает обнаружение символьным набором MacroPdf417, что ускоряет обработку. |
| **2️⃣ Iterate** | `ReadBarCodes()` возвращает **все** штрихкоды, соответствующие запрошенному типу, позволяя **читать несколько штрихкодов** без дополнительных циклов. |
| **3️⃣ Basic output** | Выводит общее `CodeTypeName` и читаемый человеком `CodeText`. Это полезно для журналирования или быстрой проверки. |
| **4️⃣ Extended data** | MacroPdf417 содержит дополнительные метаданные (ID файла, количество сегментов, метки времени и т.д.). Объект `Extended.Pdf417` предоставляет каждое поле напрямую, чтобы вы могли сохранить или проверить весь пакет данных. |

Запуск программы с корректным изображением MacroPdf417 выдаёт консольный вывод, похожий на следующий:

```
CodeType: MacroPdf417
CodeText: https://example.com/document.pdf
Pdf417MacroFileID: 12345678
Pdf417MacroSegmentID: 1
Pdf417MacroSegmentsCount: 3
Pdf417MacroFileName: document.pdf
Pdf417MacroChecksum: 0x9A3F
Pdf417MacroFileSize: 245760
Pdf417MacroTimeStamp: 2024-07-15T14:32:00Z
Pdf417MacroAddressee: John Doe
Pdf417MacroSender: Acme Corp.
MacroPdf417Terminator: True
----------------------------------------
```

Вывод подтверждает, что библиотека успешно прочитала штрихкод, извлекла текст и предоставила все поля MacroPdf417.

## Чтение нескольких штрихкодов с одного изображения

Во многих реальных сценариях на одной этикетке размещается несколько символов PDF417 — например, в транспортной накладной могут быть код перевозчика, номер отслеживания и таможенная декларация. Приведённый выше блок кода уже **читает несколько штрихкодов**, потому что `ReadBarCodes()` возвращает перечисление всех совпадений. Дополнительная настройка не требуется; достаточно пройтись по результатам, как показано в примере.

Если нужно ограничить чтение только стандартным PDF417 (не macro), замените `DecodeType.MacroPdf417` на `DecodeType.Pdf417`. Остальная логика остаётся без изменений.

## Понимание расширенных данных MacroPdf417

MacroPdf417 — это расширение обычной спецификации PDF417. Оно разбивает большие полезные нагрузки на несколько сегментов и добавляет небольшой заголовок, описывающий весь файл. Наиболее важные поля:

- **MacroPdf417FileID** – уникальный идентификатор, общий для всех сегментов одного файла.
- **MacroPdf417SegmentID** – порядковый номер текущего сегмента.
- **MacroPdf417SegmentsCount** – общее количество ожидаемых сегментов.
- **MacroPdf417FileName** – необязательное имя файла, передаваемое со штрихкодом.
- **MacroPdf417Checksum** – контрольное значение для полного файла.
- **MacroPdf417FileSize** – размер исходной бинарной полезной нагрузки.
- **MacroPdf417TimeStamp** – метка времени в формате ISO‑8601, когда штрихкод был сгенерирован.
- **MacroPdf417Addressee / Sender** – необязательные текстовые поля для маршрутизации.
- **MacroPdf417Terminator** – указывает, является ли данный сегмент последним.

Получив все сегменты, вы можете восстановить оригинальный файл, упорядочив их по `MacroPdf417SegmentID` и конкатенировав значения `CodeText`. Эта логика проста в реализации, как только поля доступны.

## Распространённые подводные камни и профессиональные советы

- **Качество изображения имеет значение** – изображения с низким разрешением или сильно сжатые PNG/JPEG могут приводить к пропуску обнаружения. Используйте минимум 300 dpi для печатных штрихкодов.
- **Смешанные символьные наборы** – если изображение содержит как MacroPdf417, так и обычный PDF417, создайте два считывателя (по одному для каждого `DecodeType`) или используйте `DecodeType.AllSupported` и отфильтруйте результаты по `result.CodeTypeName`.
- **Использование памяти** – оператор `using` сразу освобождает `BarCodeReader`, предотвращая удерживание больших буферов изображений в памяти.
- **Потокобезопасность** – `BarCodeReader` не является потокобезопасным. Создавайте отдельный экземпляр для каждого потока при параллельной обработке изображений.
- **Обработка ошибок** – оберните вызов `ReadBarCodes()` в блок try/catch, чтобы перехватывать `BarCodeException` для повреждённых изображений.

## Полный рабочий пример в обзоре

Ниже приведена полная программа, которую можно скопировать в новый консольный проект. В ней указаны все директивы `using`, константа пути к изображению и шаблон освобождения ресурсов.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

namespace Pdf417ReaderDemo
{
    class Program
    {
        static void Main()
        {
            const string imagePath = @"YOUR_DIRECTORY\MacroPdf417.png";

            using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
            {
                foreach (BarCodeResult result in reader.ReadBarCodes())
                {
                    Console.WriteLine($"CodeType: {result.CodeTypeName}");
                    Console.WriteLine($"CodeText: {result.CodeText}");

                    var macro = result.Extended.Pdf417;
                    Console.WriteLine($"Pdf417MacroFileID: {macro.MacroPdf417FileID}");
                    Console.WriteLine($"Pdf417MacroSegmentID: {macro.MacroPdf417SegmentID}");
                    Console.WriteLine($"Pdf417MacroSegmentsCount: {macro.MacroPdf417SegmentsCount}");
                    Console.WriteLine($"Pdf417MacroFileName: {macro.MacroPdf417FileName}");
                    Console.WriteLine($"Pdf417MacroChecksum: {macro.MacroPdf417Checksum}");
                    Console.WriteLine($"Pdf417MacroFileSize: {macro.MacroPdf417FileSize}");
                    Console.WriteLine($"Pdf417MacroTimeStamp: {macro.MacroPdf417TimeStamp}");
                    Console.WriteLine($"Pdf417MacroAddressee: {macro.MacroPdf417Addressee}");
                    Console.WriteLine($"Pdf417MacroSender: {macro.MacroPdf417Sender}");
                    Console.WriteLine($"MacroPdf417Terminator: {macro.MacroPdf417Terminator}");
                    Console.WriteLine(new string('-', 40));
                }
            }

            Console.WriteLine("Decoding completed. Press any key to exit.");
            Console.ReadKey();
        }
    }
}
```

Соберите проект командой `dotnet build` и запустите `dotnet run`. Консоль выведет базовые данные каждого штрихкода и полный полезный набор MacroPdf417.

## Следующие шаги

- **Восстановление многосегментных файлов** – собрать все сегменты, отсортировать их по `MacroPdf417SegmentID` и конкатенировать `CodeText` для получения оригинального файла.

## Что изучать дальше?


Следующие учебники охватывают тесно связанные темы, построенные на техниках, продемонстрированных в этом руководстве. Каждый ресурс включает полностью рабочие примеры кода с пошаговыми объяснениями, чтобы помочь вам освоить дополнительные возможности API и исследовать альтернативные подходы в собственных проектах.

- [How to Generate PDF417 Barcode – Compact PDF417 Encoding](/barcode/english/net/compact-pdf417-encoding/)
- [How to Read PDF417 Barcodes with Turkish Characters in Java](/barcode/english/java/multilingual-support/recognizing-pdf417-turkish-characters/)
- [How to Use Aspose for PDF417 Barcode (Chinese) in Java](/barcode/english/java/multilingual-support/recognizing-pdf417-chinese-characters/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}