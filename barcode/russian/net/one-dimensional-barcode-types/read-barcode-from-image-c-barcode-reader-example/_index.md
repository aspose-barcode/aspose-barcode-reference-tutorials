---
category: general
date: 2026-07-30
description: Считывание штрихкода с изображения с помощью Aspose.BarCode для .NET –
  полный пример считывателя штрихкодов на C#, показывающий, как декодировать штрихкоды
  Macro PDF417.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- read barcode from image
- c# barcode reader example
- macro pdf417 decoding
- aspose.barcode for .net
- barcode processing c#
language: ru
lastmod: 2026-07-30
og_description: Считайте штрих‑код с изображения с помощью Aspose.BarCode для .NET.
  Этот пошаговый пример считывателя штрих‑кодов на C# показывает, как извлечь все
  метаданные Macro PDF417.
og_image_alt: Screenshot of C# console output displaying decoded Macro PDF417 barcode
  information
og_title: Считывание штрихкода с изображения – полный пример считывателя штрихкода
  на C#
schemas:
- author: Aspose
  dateModified: '2026-07-30'
  description: Read barcode from image using Aspose.BarCode for .NET – a complete
    C# barcode reader example that shows how to decode Macro PDF417 barcodes.
  headline: Read barcode from image – C# barcode reader example
  type: TechArticle
- description: Read barcode from image using Aspose.BarCode for .NET – a complete
    C# barcode reader example that shows how to decode Macro PDF417 barcodes.
  name: Read barcode from image – C# barcode reader example
  steps:
  - name: '**`using` block** – Guarantees the native resources (file handles, native
      decoder memory) are freed immediately after the operation. Skipping this can
      lead to locked files on Windows.'
    text: '**`using` block** – Guarantees the native resources (file handles, native
      decoder memory) are freed immediately after the operation. Skipping this can
      lead to locked files on Windows.'
  - name: '**`DecodeType.MacroPdf417`** – Tells Aspose to look specifically for Macro PDF417
      symbols; other barcode types are ignored, which speeds up scanning.'
    text: '**`DecodeType.MacroPdf417`** – Tells Aspose to look specifically for Macro PDF417
      symbols; other barcode types are ignored, which speeds up scanning.'
  - name: '**`ReadBarCodes()`** – Returns a collection because an image might contain
      multiple Macro PDF417 segments (think of a multi‑page document split across
      several barcodes).'
    text: '**`ReadBarCodes()`** – Returns a collection because an image might contain
      multiple Macro PDF417 segments (think of a multi‑page document split across
      several barcodes).'
  - name: '**`macroResult.Extended?.Pdf417`** – The `Extended` object is nullable;
      the safe‑navigation operator (`?.`) prevents a `NullReferenceException` if the
      barcode lacks extended data.'
    text: '**`macroResult.Extended?.Pdf417`** – The `Extended` object is nullable;
      the safe‑navigation operator (`?.`) prevents a `NullReferenceException` if the
      barcode lacks extended data.'
  - name: '**Printing each field** – Gives you visibility into the file identifier,
      segment ordering, checksum verification, and optional textual fields like sender
      or addressee.'
    text: '**Printing each field** – Gives you visibility into the file identifier,
      segment ordering, checksum verification, and optional textual fields like sender
      or addressee.'
  - name: '**Collect all segments** into a dictionary keyed by `SegmentID`.'
    text: '**Collect all segments** into a dictionary keyed by `SegmentID`.'
  - name: '**Sort** them by `SegmentID` to reassemble the original file.'
    text: '**Sort** them by `SegmentID` to reassemble the original file.'
  - name: '**Validate** the `Checksum` against the concatenated payload (Aspose does
      this internally, but you can re‑run a CRC if you need extra safety).'
    text: '**Validate** the `Checksum` against the concatenated payload (Aspose does
      this internally, but you can re‑run a CRC if you need extra safety).'
  type: HowTo
tags:
- barcode
- csharp
- aspnet
- image-processing
title: Считывание штрихкода с изображения – пример считывателя штрихкода на C#
url: /ru/net/one-dimensional-barcode-types/read-barcode-from-image-c-barcode-reader-example/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Считывание штрихкода с изображения – пример считывателя штрихкода на C#

Нужно **считать штрихкод с изображения** в приложении на C#? Вы попали по адресу. В этом руководстве мы пройдем полный *пример считывателя штрихкода на C#*, использующий библиотеку Aspose.BarCode for .NET для декодирования штрихкода Macro PDF417 и извлечения всей расширенной информации, предоставляемой стандартом.

Представьте, что вы только что отсканировали транспортную этикетку, посадочный талон или государственное удостоверение, в котором встроен сегмент Macro PDF417. Вы хотите получить идентификатор файла, количество сегментов, метки времени и, возможно, даже имя отправителя — и всё это без выхода из кода. Именно этого мы добьёмся, и сделаем это так, чтобы было легко скопировать‑вставить в ваш собственный проект.

---

## Чему вы научитесь

- Как добавить пакет Aspose.BarCode NuGet в проект .NET.  
- Как открыть файл изображения, содержащий штрихкод Macro PDF417.  
- Как перебрать результаты **считать штрихкод с изображения** и получить доступ ко всем расширенным полям.  
- Советы по работе с несколькими сегментами, проверке контрольных сумм и устранению распространённых проблем.

К концу этого руководства у вас будет работающее консольное приложение, которое выводит все метаданные Macro PDF417, готовое к интеграции в более крупные системы, такие как трекеры инвентаря или конвейеры управления документами.

---

## Требования

Перед тем как приступить, убедитесь, что у вас есть следующее:

| Требование | Почему это важно |
|------------|-------------------|
| .NET 6.0 SDK или новее (подойдёт любая recent версия) | Обеспечивает среду выполнения для консольного приложения. |
| Visual Studio 2022 (или VS Code с расширением C#) | Делает редактирование и отладку безболезненной. |
| Aspose.BarCode for .NET (бесплатная пробная версия или лицензия) | Библиотека, которая действительно декодирует штрихкод. |
| Файл изображения (`MacroPdf417Meta.png`), содержащий штрихкод Macro PDF417 | Источник, из которого мы будем считывать. |

Если у вас ещё нет Aspose.BarCode, вы можете получить его из NuGet:

```bash
dotnet add package Aspose.BarCode
```

Эта единственная строка устанавливает всё, что вам нужно, включая `BarCodeReader`, `DecodeType` и богатый набор свойств `Extended`, который мы изучим.

---

## Шаг 1 – Настройте проект и импортируйте библиотеку

Создайте новый консольный проект (или вставьте код в существующий). Директивы `using` обязательны; они делают классы штрихкода доступными в области видимости.

```csharp
// Program.cs – entry point for the demo
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;   // contains BarCodeReader and DecodeType
```

> **Pro tip:** Если вы используете Visual Studio, IDE предложит автоматически добавить недостающие инструкции `using` — просто нажмите *Ctrl+.`*.

---

## Шаг 2 – Подготовьте путь к изображению

Жёстко заданный абсолютный путь подходит для быстрой демонстрации, но в продакшене вы, вероятно, будете принимать аргумент командной строки или параметр конфигурации. Для ясности оставим всё просто:

```csharp
// Adjust the path to point at your image file
string imagePath = @"C:\Barcodes\MacroPdf417Meta.png";
```

> **Why this matters:** `BarCodeReader` ожидает корректный путь к файлу; неверный путь вызывает `FileNotFoundException` ещё до начала декодирования.

---

## Шаг 3 – **Считать штрихкод с изображения** и извлечь детали Macro PDF417

Теперь начинается сердце **пример считывателя штрихкода на C#**. Мы создадим экземпляр `BarCodeReader` с флагом `DecodeType.MacroPdf417`, пройдемся по всем результатам (в одном изображении может быть более одного штрихкода) и выведем каждое расширенное свойство.

```csharp
// Step 3: Open the image and decode Macro PDF417 barcodes
using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
{
    // Iterate over every barcode found in the image
    foreach (BarCodeResult macroResult in reader.ReadBarCodes())
    {
        // The Extended property contains the Macro PDF417 specific fields
        var pdf417 = macroResult.Extended?.Pdf417;

        if (pdf417 == null)
        {
            Console.WriteLine("No Macro PDF417 extension data found for this barcode.");
            continue;
        }

        // Output each piece of metadata – this is what makes the example useful
        Console.WriteLine($"FileID: {pdf417.MacroPdf417FileID}");
        Console.WriteLine($"SegmentID: {pdf417.MacroPdf417SegmentID}");
        Console.WriteLine($"SegmentsCount: {pdf417.MacroPdf417SegmentsCount}");
        Console.WriteLine($"FileName: {pdf417.MacroPdf417FileName}");
        Console.WriteLine($"Checksum: {pdf417.MacroPdf417Checksum}");
        Console.WriteLine($"FileSize: {pdf417.MacroPdf417FileSize}");
        Console.WriteLine($"TimeStamp: {pdf417.MacroPdf417TimeStamp}");
        Console.WriteLine($"Addressee: {pdf417.MacroPdf417Addressee}");
        Console.WriteLine($"Sender: {pdf417.MacroPdf417Sender}");
        Console.WriteLine($"Terminator: {pdf417.MacroPdf417Terminator}");
        Console.WriteLine(new string('-', 40)); // separator for readability
    }
}
```

### Что делает код (почему, а не только как)

1. **`using` блок** — Гарантирует, что нативные ресурсы (дескрипторы файлов, память декодера) освобождаются сразу после операции. Пропуск этого может привести к блокировке файлов в Windows.  
2. **`DecodeType.MacroPdf417`** — Инструктирует Aspose искать именно символы Macro PDF417; остальные типы штрихкодов игнорируются, что ускоряет сканирование.  
3. **`ReadBarCodes()`** — Возвращает коллекцию, потому что изображение может содержать несколько сегментов Macro PDF417 (например, многостраничный документ, разбитый на несколько штрихкодов).  
4. **`macroResult.Extended?.Pdf417`** — Объект `Extended` может быть `null`; оператор безопасной навигации (`?.`) предотвращает `NullReferenceException`, если у штрихкода нет расширенных данных.  
5. **Вывод каждого поля** — Позволяет увидеть идентификатор файла, порядок сегментов, проверку контрольной суммы и необязательные текстовые поля, такие как отправитель или получатель.

---

## Шаг 4 – Запустите приложение и проверьте вывод

Скомпилируйте и выполните программу:

```bash
dotnet run
```

Если всё настроено правильно, в консоли вы увидите нечто похожее на следующее:

```
FileID: 12
SegmentID: 3
SegmentsCount: 5
FileName: invoice_2023.pdf
Checksum: 0x1A2B
FileSize: 45231
TimeStamp: 2023-08-15T14:32:00Z
Addressee: Acme Corp.
Sender: Warehouse 7
Terminator: 0xFF
----------------------------------------
```

> **Note:** Точные значения зависят от штрихкода, который вы декодируете. Если вы получаете сообщение «No Macro PDF417 extension data found», дважды проверьте, что изображение действительно содержит код Macro PDF417 и что вы используете правильный `DecodeType`.

---

## Обработка нескольких сегментов и проверка (продвинутый уровень)

Macro PDF417 предназначен для больших объёмов данных, разбитых на несколько символов. Когда вы сталкиваетесь с более чем одним сегментом, обычно требуется:

1. **Собрать все сегменты** в словарь, ключом которого будет `SegmentID`.  
2. **Отсортировать** их по `SegmentID`, чтобы восстановить оригинальный файл.  
3. **Проверить** `Checksum` относительно объединённого полезного нагрузки (Aspose делает это внутри, но вы можете выполнить CRC повторно, если нужна дополнительная безопасность).  

Вот быстрый набросок:

```csharp
var segments = new SortedDictionary<int, BarCodeResult>();

using (var reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
{
    foreach (var result in reader.ReadBarCodes())
    {
        var pdf = result.Extended?.Pdf417;
        if (pdf != null)
            segments[pdf.MacroPdf417SegmentID] = result;
    }
}

// Reassemble data (pseudo‑code)
byte[] fullPayload = AssembleSegments(segments);
bool isValid = VerifyChecksum(fullPayload, segments[0].Extended.Pdf417.MacroPdf417Checksum);
Console.WriteLine(isValid ? "Checksum OK" : "Checksum mismatch");
```

Вам понадобится реализовать `AssembleSegments` и `VerifyChecksum` в соответствии с форматом вашей полезной нагрузки — обычно это просто конкатенация массивов байтов с последующей проверкой CRC‑16.

---

## Распространённые подводные камни и как их избежать

| Симптом | Вероятная причина | Решение |
|---------|-------------------|---------|
| `null` возвращён из `macroResult.Extended` | Изображение содержит обычный PDF417, а не Macro‑версию. | Используйте `DecodeType.Pdf417` вместо этого, либо проверьте исходный штрихкод. |
| Нет вывода вообще | Неправильный `imagePath` или файл недоступен. | Проверьте путь к файлу; убедитесь, что приложение имеет права чтения. |
| Исключение «Object disposed» | Попытка использовать `reader` после блока `using`. | Держите всю обработку внутри блока `using`. |

---

## Что изучать дальше?

Следующие руководства охватывают тесно связанные темы, которые развивают техники, продемонстрированные в этом руководстве. Каждый ресурс включает полностью работающие примеры кода с пошаговыми объяснениями, чтобы помочь вам освоить дополнительные возможности API и исследовать альтернативные подходы в ваших проектах.

- [DataMatrix Reader Programming with Aspose.BarCode for .NET](/barcode/english/net/datamatrix-barcode-reading/datamatrix-reader-programming/)
- [DotCode Reader Initialization with Aspose.BarCode for .NET](/barcode/english/net/dotcode-barcode-configuration/dotcode-reader-initialization/)
- [How to Read DataMatrix Barcodes with Aspose.BarCode for .NET](/barcode/english/net/datamatrix-barcode-reading/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}