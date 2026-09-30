---
category: general
date: 2026-09-07
description: Узнайте, как декодировать штрихкоды PDF417 в C# с помощью BarCodeReader.
  Это пошаговое руководство также объясняет, как эффективно считывать данные PDF417.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to decode pdf417
- how to read pdf417
- PDF417 barcode decoding C#
- MacroPdf417 extraction C#
- barcode reader BarCodeReader
- GroupDocs.Barcode tutorial
language: ru
lastmod: 2026-09-07
og_description: Как декодировать штрихкоды PDF417 в C# с помощью BarCodeReader. Следуйте
  этому руководству, чтобы узнать, как считывать данные PDF417 и извлекать поля MacroPdf417.
og_image_alt: Screenshot of C# code reading PDF417 barcode fields in the console
og_title: Как декодировать штрихкоды PDF417 в C# – полное руководство
schemas:
- author: GroupDocs
  dateModified: '2026-09-07'
  description: Learn how to decode PDF417 barcodes in C# using BarCodeReader. This
    step‑by‑step guide also explains how to read PDF417 data efficiently.
  headline: How to decode PDF417 barcodes in C# with BarCodeReader
  type: TechArticle
- description: Learn how to decode PDF417 barcodes in C# using BarCodeReader. This
    step‑by‑step guide also explains how to read PDF417 data efficiently.
  name: How to decode PDF417 barcodes in C# with BarCodeReader
  steps:
  - name: Prepare the project and import namespaces
    text: '```csharp using System; using GroupDocs.Barcode; using GroupDocs.Barcode.Common;
      ```'
  - name: Define the image path
    text: '```csharp // Replace with the absolute or relative path to your barcode
      image string imagePath = "YOUR_DIRECTORY/ExtPDF417Meta.png"; ```'
  - name: Initialize the barcode reader for MacroPdf417 decoding
    text: '```csharp using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
      { // Step 4 runs inside this block } ```'
  - name: Read every barcode found in the image
    text: '```csharp foreach (BarCodeResult result in reader.ReadBarCodes()) { //
      Step 5 extracts the MacroPdf417 fields } ```'
  - name: Retrieve and display Macro PDF417 specific data
    text: '```csharp Console.WriteLine($"Pdf417MacroFileID: {result.Extended.Pdf417.MacroPdf417FileID}");
      Console.WriteLine($"Pdf417MacroSegmentID: {result.Extended.Pdf417.MacroPdf417SegmentID}");
      Console.WriteLine($"Pdf417MacroSegmentCount: {result.Extended.Pdf417.MacroPdf417SegmentCount}");
      Console.WriteLine'
  - name: Full runnable example
    text: 'Combine the snippets above into a single `Program.cs` file:'
  type: HowTo
tags:
- PDF417
- C#
- barcode decoding
title: Как декодировать штрихкоды PDF417 в C# с помощью BarCodeReader
url: /ru/net/compact-pdf417-encoding/how-to-decode-pdf417-barcodes-in-c-with-barcodereader/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Как декодировать штрихкоды PDF417 в C# с помощью BarCodeReader

Если вам нужно **как декодировать PDF417** штрихкоды в .NET‑приложении, это руководство проведёт вас через весь процесс. Вы также узнаете **как читать PDF417** данные, такие как идентификаторы файлов и сегментов MacroPdf417, используя всего несколько строк C#.

Декодирование PDF417 часто требуется при работе с транспортными билетами, водительскими удостоверениями или транспортировочными этикетками. К концу этого урока у вас будет готовая консольная программа, выводящая каждое поле MacroPdf417, доступное в SDK GroupDocs.Barcode.

## Требования

Прежде чем начать, убедитесь, что у вас есть:

* .NET 6.0 SDK или новее (код компилируется и в .NET Core, и в .NET Framework)
* Visual Studio 2022 или любой IDE, поддерживающий C#
* NuGet‑пакет **GroupDocs.Barcode** (`GroupDocs.Barcode` ≥ 23.3)
* Файл изображения, содержащий штрихкод Macro PDF417 (например, `ExtPDF417Meta.png`)

> **Pro tip:** Установите пакет через CLI:  
> `dotnet add package GroupDocs.Barcode --version 23.3`

## Как декодировать штрихкоды PDF417 в C#

Ниже решение разбито на логические шаги. Каждый шаг включает точный код, который вам нужен, и краткое объяснение, почему он важен.

### Шаг 1: Подготовьте проект и импортируйте пространства имён

```csharp
using System;
using GroupDocs.Barcode;
using GroupDocs.Barcode.Common;
```

*Почему?*  
`GroupDocs.Barcode` предоставляет класс `BarCodeReader`, а `GroupDocs.Barcode.Common` содержит перечисление `DecodeType`, необходимое для декодирования PDF417.

### Шаг 2: Задайте путь к изображению

```csharp
// Replace with the absolute or relative path to your barcode image
string imagePath = "YOUR_DIRECTORY/ExtPDF417Meta.png";
```

*Почему?*  
Читатель работает с любым форматом изображения, поддерживаемым .NET (`.png`, `.jpg`, `.bmp`). Указание правильного пути гарантирует, что SDK найдёт файл.

### Шаг 3: Инициализируйте считыватель штрихкодов для декодирования MacroPdf417

```csharp
using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
{
    // Step 4 runs inside this block
}
```

*Почему?*  
`DecodeType.MacroPdf417` указывает SDK искать расширенный формат Macro PDF417, который содержит дополнительную метаинформацию, такую как идентификаторы файлов и сегментов. Оператор `using` гарантирует своевременное освобождение неуправляемых ресурсов.

### Шаг 4: Прочитайте все штрихкоды, найденные на изображении

```csharp
foreach (BarCodeResult result in reader.ReadBarCodes())
{
    // Step 5 extracts the MacroPdf417 fields
}
```

*Почему?*  
На изображении может быть несколько штрихкодов. Метод `ReadBarCodes()` возвращает коллекцию, позволяя обрабатывать каждый элемент отдельно.

### Шаг 5: Получите и отобразите данные, специфичные для Macro PDF417

```csharp
Console.WriteLine($"Pdf417MacroFileID: {result.Extended.Pdf417.MacroPdf417FileID}");
Console.WriteLine($"Pdf417MacroSegmentID: {result.Extended.Pdf417.MacroPdf417SegmentID}");
Console.WriteLine($"Pdf417MacroSegmentCount: {result.Extended.Pdf417.MacroPdf417SegmentCount}");
Console.WriteLine($"Pdf417MacroFileName: {result.Extended.Pdf417.MacroPdf417FileName}");
Console.WriteLine($"Pdf417MacroTimestamp: {result.Extended.Pdf417.MacroPdf417Timestamp}");
```

*Почему?*  
Объект `Extended.Pdf417` раскрывает все поля Macro PDF417, определённые спецификацией. Их вывод позволяет убедиться, что декодирование прошло успешно, и предоставляет нужные данные для дальнейшей обработки.

### Полный исполняемый пример

Объедините фрагменты выше в один файл `Program.cs`:

```csharp
using System;
using GroupDocs.Barcode;
using GroupDocs.Barcode.Common;

class Program
{
    static void Main()
    {
        // 1️⃣ Path to the image that contains the Macro PDF417 barcode
        string imagePath = "YOUR_DIRECTORY/ExtPDF417Meta.png";

        // 2️⃣ Create a reader configured for MacroPdf417 decoding
        using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
        {
            // 3️⃣ Iterate over all detected barcodes
            foreach (BarCodeResult result in reader.ReadBarCodes())
            {
                // 4️⃣ Output Macro PDF417 metadata
                Console.WriteLine($"Pdf417MacroFileID: {result.Extended.Pdf417.MacroPdf417FileID}");
                Console.WriteLine($"Pdf417MacroSegmentID: {result.Extended.Pdf417.MacroPdf417SegmentID}");
                Console.WriteLine($"Pdf417MacroSegmentCount: {result.Extended.Pdf417.MacroPdf417SegmentCount}");
                Console.WriteLine($"Pdf417MacroFileName: {result.Extended.Pdf417.MacroPdf417FileName}");
                Console.WriteLine($"Pdf417MacroTimestamp: {result.Extended.Pdf417.MacroPdf417Timestamp}");
                Console.WriteLine(); // Blank line for readability
            }
        }
    }
}
```

**Ожидаемый вывод в консоль** (значения будут отличаться в зависимости от содержимого штрихкода):

```
Pdf417MacroFileID: 12345
Pdf417MacroSegmentID: 1
Pdf417MacroSegmentCount: 3
Pdf417MacroFileName: shipment_data
Pdf417MacroTimestamp: 2024-07-15T10:23:45Z
```

Если изображение не содержит штрихкода Macro PDF417, коллекция `ReadBarCodes()` будет пустой и ничего не будет выведено.

## Общие варианты и граничные случаи

| Ситуация | Как адаптировать код |
|-----------|----------------------|
| **Стандартный (не‑macro) PDF417** | Замените `DecodeType.MacroPdf417` на `DecodeType.Pdf417`. Объект `Extended.Pdf417` будет `null`, поэтому необходимо проверять ссылки на `null`. |
| **Несколько изображений** | Оберните инициализацию считывателя в цикл `foreach (var path in imagePaths)`. |
| **Большие изображения** | Установите `reader.Options.ImageProcessingOptions.MaxImageDimension = 2000;` для ограничения потребления памяти. |
| **Пакетная обработка с высокой производительностью** | Переиспользуйте один экземпляр `BarCodeReader`, вызывая `reader.SetImage(path)` вместо создания нового объекта для каждого файла. |

## Список проверок при устранении неполадок

* **Нет вывода:** Убедитесь, что `imagePath` указывает на существующий файл и что изображение действительно содержит штрихкод PDF417. |
* **`Extended.Pdf417` равно `null`:** Скорее всего, вы использовали `DecodeType.Pdf417` вместо `MacroPdf417`. |
* **Исключение `FileNotFoundException`:** Проверьте, что рабочий каталог соответствует пути, либо используйте абсолютный путь. |
* **Низкий коэффициент уверенности:** Повышайте качество изображения или корректируйте настройки `reader.Options.Quality`. |

## Заключение

Теперь вы знаете **как декодировать PDF417** штрихкоды в C# и **как читать PDF417** метаданные, такие как идентификаторы файлов Macro, идентификаторы сегментов и метки времени. Полный пример демонстрирует инициализацию `BarCodeReader`, выбор правильного типа декодирования, перебор результатов и извлечение каждого доступного поля MacroPdf417.

Дальше вы можете:

* Интегрировать извлечённые данные в систему логистики или проверки билетов.
* Расширить консольное приложение, чтобы сохранять результаты в базу данных или файл JSON.
* Исследовать другие форматы штрихкодов, поддерживаемые GroupDocs.Barcode (QR, DataMatrix, Code128 и др.), меняя значение перечисления `DecodeType`.

Удачной разработки, экспериментируйте с разными изображениями и настройками штрихкодов, чтобы полностью освоить декодирование PDF417 в ваших .NET‑проектах!

## Что изучать дальше?

Следующие руководства охватывают тесно связанные темы, расширяющие техники, продемонстрированные в этом материале. Каждый ресурс содержит полностью рабочие примеры кода с пошаговыми объяснениями, помогающими вам освоить дополнительные возможности API и исследовать альтернативные подходы в собственных проектах.

- [How to Read PDF417 in C# – Complete Step‑by‑Step Guide](/barcode/english/net/compact-pdf417-encoding/how-to-read-pdf417-in-c-complete-step-by-step-guide/)
- [How to Read PDF417 in C# – Complete Barcode Reader Example](/barcode/english/net/compact-pdf417-encoding/how-to-read-pdf417-in-c-complete-barcode-reader-example/)
- [How to Generate PDF417 Barcode – Complete Programming Guide](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-complete-programming-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}