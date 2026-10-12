---
category: general
date: 2026-09-26
description: Узнайте, как декодировать PDF417 в C# с пошаговым примером считывателя
  штрихкода. Это руководство показывает, как считывать изображение штрихкода в C#
  с использованием Aspose.BarCode.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to decode pdf417
- read barcode image c#
- c# barcode reader example
language: ru
lastmod: 2026-09-26
og_description: Как быстро декодировать PDF417 в C#. Следуйте этому примеру считывателя
  штрихкода, чтобы прочитать изображение штрихкода в C# с помощью Aspose.BarCode и
  извлечь детали макроса.
og_image_alt: Screenshot showing how to decode PDF417 in C# using Aspose.BarCode
og_title: Как декодировать PDF417 в C# – полное руководство по считыванию штрихкодов
schemas:
- author: Aspose
  dateModified: '2026-09-26'
  description: Learn how to decode PDF417 in C# with a step‑by‑step barcode reader
    example. This guide shows you how to read barcode image C# using Aspose.BarCode.
  headline: How to decode PDF417 in C# – barcode reader example
  type: TechArticle
tags:
- barcode
- pdf417
- csharp
title: Как декодировать PDF417 в C# – пример считывателя штрихкода
url: /ru/net/compact-pdf417-encoding/how-to-decode-pdf417-in-c-barcode-reader-example/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Как декодировать PDF417 в C# – пример считывателя штрихкода

Если вам нужно **как декодировать PDF417** в приложении .NET, этот учебник предоставляет полное, готовое к запуску решение. Вы увидите, как считывать изображение штрихкода в C# с помощью библиотеки Aspose.BarCode, получить расширенную информацию макроса PDF417 и отобразить каждое соответствующее поле.

Декодирование PDF417 не ограничивается простым текстом; формат может содержать данные сегментации файлов, метки времени и контрольные суммы. Это руководство проведёт вас через каждый шаг, объяснит, почему код построен именно так, и выделит типичные подводные камни, с которыми вы можете столкнуться при реализации примера считывателя штрихкода на C#.

## Предварительные требования

* .NET 6.0 (или новее) SDK установлен  
* Visual Studio 2022 (или любой IDE, совместимый с C#)  
* **Aspose.BarCode for .NET** пакет NuGet (`Aspose.BarCode`)  
* Пример изображения Macro PDF417 (например, `ExtPDF417Meta.png`)

Эти требования гарантируют, что код компилируется и работает без дополнительной настройки.

## Шаг 1: Установите пакет NuGet Aspose.BarCode

Первый шаг в любом проекте **чтения изображения штрихкода C#** — добавить библиотеку штрихкода. Откройте терминал в папке решения и выполните:

```bash
dotnet add package Aspose.BarCode
```

Пакет предоставляет `BarCodeReader`, `DecodeType` и свойство `Extended`, используемое для доступа к макроданным. Установив его один раз, вы делаете классы доступными во всём проекте.

## Шаг 2: Создайте считыватель штрихкода для изображения Macro PDF417

Теперь вы можете создать экземпляр `BarCodeReader`, указав путь к изображению и задав `DecodeType.MacroPdf417`. Это сообщает библиотеке искать расширенный формат PDF417, содержащий макроинформацию.

```csharp
using Aspose.BarCode.BarCodeRecognition;

// Path to the Macro PDF417 image
string imagePath = @"YOUR_DIRECTORY/ExtPDF417Meta.png";

// Initialize the reader for Macro PDF417 decoding
using (BarCodeReader barcodeReader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
{
    // The reader is ready – next we will extract barcodes.
}
```

**Почему это важно:**  
`DecodeType.MacroPdf417` активирует парсер, специфичный для макросов. Если его опустить, считыватель вернёт только обычный текстовый полезный груз и проигнорирует макрополя, которые, вероятно, нужны для восстановления файла.

## Шаг 3: Прочитайте все штрихкоды, найденные на изображении

Одно изображение может содержать несколько символов PDF417, особенно когда данные разбиты на сегменты. Перебор `ReadBarCodes()` гарантирует, что вы захватите каждый сегмент.

```csharp
// Step 3: Iterate over each detected barcode
foreach (BarCodeResult barcodeResult in barcodeReader.ReadBarCodes())
{
    // Inside the loop we will access both basic and macro data.
}
```

**Почему нужен цикл:**  
Макроданные PDF417 часто появляются в нескольких сегментах. Обработка каждого `BarCodeResult` обеспечивает сбор полного набора макрополей, таких как `MacroPdf417FileID` и `MacroPdf417SegmentsCount`.

## Шаг 4: Получите и отобразите базовые данные штрихкода

Объект `BarCodeResult` содержит тип и декодированный текст. Вывод этих значений помогает убедиться, что считыватель правильно идентифицировал символ, прежде чем переходить к деталям макроса.

```csharp
Console.WriteLine($"CodeType: {barcodeResult.CodeTypeName}");
Console.WriteLine($"CodeText: {barcodeResult.CodeText}");
```

**Подсказка:** Если `CodeText` пустой, изображение может быть повреждено или выбран неверный режим декодирования. Дважды проверьте `DecodeType`, использованный при инициализации.

## Шаг 5: Извлеките расширенную информацию макроса PDF417

Макроданные находятся в `barcodeResult.Extended.Pdf417`. Каждое свойство соответствует полю, определённому в спецификации PDF417.

```csharp
// Step 5: Access macro-specific fields
var macroInfo = barcodeResult.Extended.Pdf417;

Console.WriteLine($"Pdf417MacroFileID: {macroInfo.MacroPdf417FileID}");
Console.WriteLine($"Pdf417MacroSegmentID: {macroInfo.MacroPdf417SegmentID}");
Console.WriteLine($"Pdf417MacroSegmentsCount: {macroInfo.MacroPdf417SegmentsCount}");
Console.WriteLine($"Pdf417MacroFileName: {macroInfo.MacroPdf417FileName}");
Console.WriteLine($"Pdf417MacroChecksum: {macroInfo.MacroPdf417Checksum}");
Console.WriteLine($"Pdf417MacroFileSize: {macroInfo.MacroPdf417FileSize}");
Console.WriteLine($"Pdf417MacroTimeStamp: {macroInfo.MacroPdf417TimeStamp}");
Console.WriteLine($"Pdf417MacroAddressee: {macroInfo.MacroPdf417Addressee}");
Console.WriteLine($"Pdf417MacroSender: {macroInfo.MacroPdf417Sender}");
Console.WriteLine($"MacroPdf417Terminator: {macroInfo.MacroPdf417Terminator}");
```

**Что означает каждое поле**

| Property | Description |
|----------|-------------|
| `MacroPdf417FileID` | Идентификатор, группирующий все сегменты, принадлежащие одному логическому файлу. |
| `MacroPdf417SegmentID` | Номер текущего сегмента (начинается с 1). |
| `MacroPdf417SegmentsCount` | Общее количество сегментов, необходимых для восстановления оригинального файла. |
| `MacroPdf417FileName` | Необязательное имя файла, встроенное в макрос. |
| `MacroPdf417Checksum` | CRC‑16 контрольная сумма для проверки целостности. |
| `MacroPdf417FileSize` | Ожидаемый размер восстанавливаемого файла (в байтах). |
| `MacroPdf417TimeStamp` | Дата и время генерации макроса. |
| `MacroPdf417Addressee` | Необязательный идентификатор получателя. |
| `MacroPdf417Sender` | Необязательный идентификатор отправителя. |
| `MacroPdf417Terminator` | Флаг завершения; должен быть `true` в последнем сегменте. |

Понимание этих полей позволяет воссоздать оригинальный файл, проверить целостность данных и реализовать пользовательскую бизнес‑логику (например, отклонять устаревшие документы).

## Шаг 6: Обработайте несколько сегментов и восстановите оригинальный файл (расширенно)

Когда `MacroPdf417SegmentsCount` больше 1, необходимо собрать каждый сегмент, упорядочить их по `MacroPdf417SegmentID` и конкатенировать значения `CodeText`. Ниже представлена лаконичная реализация:

```csharp
// Collect segments in a dictionary keyed by SegmentID
var segments = new SortedDictionary<int, string>();

foreach (BarCodeResult result in barcodeReader.ReadBarCodes())
{
    var macro = result.Extended.Pdf417;
    segments[macro.MacroPdf417SegmentID] = result.CodeText;
}

// Verify that we received all expected segments
int expectedCount = segments.First().Value != null
    ? barcodeReader.ReadBarCodes().First().Extended.Pdf417.MacroPdf417SegmentsCount
    : 0;

if (segments.Count == expectedCount)
{
    // Reconstruct the full payload
    string fullPayload = string.Concat(segments.Values);
    Console.WriteLine($"Reconstructed payload ({fullPayload.Length} chars):");
    Console.WriteLine(fullPayload);
}
else
{
    Console.WriteLine($"Warning: Expected {expectedCount} segments but received {segments.Count}.");
}
```

**Почему это важно:**  
Без упорядочивания и конкатенации декодированные данные будут неполными или искажёнными. Фрагмент кода также демонстрирует защитное программирование, проверяя количество сегментов.

## Шаг 7: Завершите с обработкой ошибок и лучшими практиками

Готовый к продакшну **c# barcode reader example** должен предусматривать ошибки ввода‑вывода, неподдерживаемые форматы и повреждённые изображения.

```csharp
try
{
    // Existing barcode reading code goes here
}
catch (FileNotFoundException ex)
{
    Console.Error.WriteLine($"Image file not found: {ex.Message}");
}
catch (BarCodeException ex)
{
    Console.Error.WriteLine($"Barcode processing error: {ex.Message}");
}
catch (Exception ex)
{
    Console.Error.WriteLine($"Unexpected error: {ex.Message}");
}
```

**Контрольный список лучших практик**

* Проверяйте путь к изображению перед созданием `BarCodeReader`.  
* Используйте конструкции `using` для гарантированного освобождения неуправляемых ресурсов.  
* Логируйте макрополя для аудита — особенно `MacroPdf417Checksum` и `MacroPdf417TimeStamp`.  
* При работе с большими файлами рассматривайте возможность потоковой записи объединённого полезного груза на диск вместо полного удержания в памяти.

## Ожидаемый вывод

Запуск полной программы против корректного `ExtPDF417Meta.png` выдаёт вывод, похожий на следующий:

```
CodeType: MacroPdf417
CodeText: <base64‑encoded segment data>
Pdf417MacroFileID: 42
Pdf417MacroSegmentID: 1
Pdf417MacroSegmentsCount: 3
Pdf417MacroFileName: document.pdf
Pdf417MacroChecksum: 0x1A2B
Pdf417MacroFileSize: 254312
Pdf417MacroTimeStamp: 2024-03-15T10:23:45Z
Pdf417MacroAddressee: Acme Corp
Pdf417MacroSender: Warehouse 7
MacroPdf417Terminator: False
...
```

Если присутствуют все три сегмента, блок восстановления выводит полный полезный груз после сообщения о проверке.

## Заключение

Теперь вы знаете **как декодировать PDF417** в C# с помощью надёжного примера считывателя штрихкода. В руководстве рассмотрены установка Aspose.BarCode, инициализация `BarCodeReader` для Macro PDF417, перебор нескольких штрихкодов, извлечение макрополей, сборка сегментированных данных и обработка ошибок.  

Далее вы можете:

* Интегрировать считыватель в веб‑API, принимающее загруженные изображения.  
* Сохранять метаданные макроса в базе данных для целей аудита.  
* Расширить решение на другие 2‑D символьные системы, заменив `DecodeType` (e

## Что следует изучить дальше?

Следующие учебники охватывают тесно связанные темы, построенные на техниках, продемонстрированных в этом руководстве. Каждый ресурс включает полностью рабочие примеры кода с пошаговыми объяснениями, помогающими освоить дополнительные возможности API и исследовать альтернативные подходы в ваших проектах.

- [How to Read PDF417 in C# – Complete Barcode Reader Example](/barcode/english/net/compact-pdf417-encoding/how-to-read-pdf417-in-c-complete-barcode-reader-example/)
- [How to Create PDF417 Barcode with Aspose – Complete Step‑by‑Step Guide](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-with-aspose-complete-step-by-st/)
- [Read PDF417 barcode in C# – barcode reader example](/barcode/english/net/compact-pdf417-encoding/read-pdf417-barcode-in-c-barcode-reader-example/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}