---
category: general
date: 2026-10-28
description: Как быстро декодировать штрихкоды PDF417 в C#. Узнайте, как считывать
  изображение штрихкода в C# с помощью Aspose.BarCode, используя полный, исполняемый
  пример.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to decode pdf417
- read barcode image c#
- PDF417 decoding C#
- barcode reader C#
- Aspose.BarCode example
language: ru
lastmod: 2026-10-28
og_description: Как декодировать штрихкоды PDF417 в C# с помощью Aspose.BarCode. Это
  руководство показывает, как читать изображение штрихкода в C# шаг за шагом, с полным
  кодом.
og_image_alt: Screenshot of C# code that decodes a PDF417 barcode from an image
og_title: Как декодировать штрихкоды PDF417 в C# – руководство по чтению изображения
  штрихкода в C#
schemas:
- author: Aspose
  dateModified: '2026-10-28'
  description: How to decode PDF417 barcodes in C# quickly. Learn to read barcode
    image C# using Aspose.BarCode with a complete, runnable example.
  headline: How to decode PDF417 barcodes in C# and read barcode image C#
  type: TechArticle
- description: How to decode PDF417 barcodes in C# quickly. Learn to read barcode
    image C# using Aspose.BarCode with a complete, runnable example.
  name: How to decode PDF417 barcodes in C# and read barcode image C#
  steps:
  - name: What each line does
    text: '| Line | Explanation | |------|-------------| | `result.CodeTypeName` |
      Human‑readable name of the detected barcode type (e.g., “MacroPdf417”). | |
      `result.CodeText` | The raw data encoded in the barcode. | | `result.Extended.Pdf417.MacroPdf417FileID`
      | Identifier that ties all segments of a macro P'
  - name: Handling common edge cases
    text: '| Situation | Recommended handling | |-----------|----------------------|
      | **No barcode found** | Check `reader.ReadBarCodes().Any()` before the loop
      and display a friendly message. | | **Corrupted image** | Wrap the `BarCodeReader`
      creation in a `try/catch` block for `BarCodeException`. | | **Mult'
  - name: Next steps
    text: '* Explore other barcode formats by changing `DecodeType` (e.g., `DecodeType.QR`,
      `DecodeType.Code128`). * Combine multiple decoded segments to reconstruct the
      original document. * Use the `BarCodeGenerator` class to create test PDF417
      barcodes on the fly.'
  type: HowTo
tags:
- barcode
- pdf417
- csharp
title: Как декодировать штрихкоды PDF417 в C# и считывать изображение штрихкода в
  C#
url: /ru/net/compact-pdf417-encoding/how-to-decode-pdf417-barcodes-in-c-and-read-barcode-image-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Как декодировать PDF417 штрихкоды в C# и читать изображение штрихкода C#

Если вам нужно **how to decode pdf417** в приложении .NET, это руководство предоставляет готовое решение. Вы точно увидите, как **read barcode image c#** с помощью библиотеки Aspose.BarCode, извлечь поля macro‑PDF417 и отобразить их в консоли.

Декодирование PDF417 штрихкодов часто встречается в системах логистики, билетирования и проверки личности. К концу этого руководства вы сможете загрузить любое изображение, содержащее Macro PDF417 штрихкод, декодировать его и получить значения file ID, segment ID и segment count, которые необходимы для сборки много‑сегментных документов.

## Предварительные требования

Перед началом убедитесь, что у вас есть:

* .NET 6.0 SDK или более поздняя версия установлен(а)  
* Visual Studio 2022 (или любой C# IDE)  
* Пакет NuGet Aspose.BarCode for .NET (`Aspose.BarCode`)  
* Файл изображения, содержащий Macro PDF417 штрихкод (в примере используется `ExtPDF417Meta.png`)

Вы можете добавить пакет NuGet с помощью следующей команды:

```bash
dotnet add package Aspose.BarCode
```

## Шаг 1: Настройте проект и импортируйте пространства имён

Создайте новый консольный проект и импортируйте необходимые пространства имён. Директивы `using` дают доступ к `BarCodeReader`, `DecodeType` и объектам расширения результата.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;
```

> **Почему этот шаг важен** – Импорт правильных пространств имён предотвращает ошибки компиляции и делает API доступным для последующей логики декодирования.

## Шаг 2: Укажите путь к изображению

Определите полный или относительный путь к изображению штрихкода. Хранение пути в переменной делает код переиспользуемым для разных изображений.

```csharp
// Step 2: Specify the path to the image that contains a Macro PDF417 barcode
string imagePath = "YOUR_DIRECTORY/ExtPDF417Meta.png";
```

> **Подсказка:** Используйте `Path.Combine`, если собираете путь из нескольких частей; он корректно обрабатывает разделители каталогов в разных операционных системах.

## Шаг 3: Создайте `BarCodeReader`, настроенный для декодирования Macro PDF417

Создайте экземпляр `BarCodeReader` с указанием пути к изображению и флагом `DecodeType.MacroPdf417`. Это указывает библиотеке искать именно символы Macro PDF417.

```csharp
// Step 3: Create a BarCodeReader configured for MacroPdf417 decoding
using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
{
    // The reader is now ready to scan the image.
```

> **Почему этот шаг важен** – Выбор правильного `DecodeType` повышает производительность, так как движок пропускает несвязанные форматы штрихкодов.

## Шаг 4: Считайте все штрихкоды и отобразите macro‑информацию

Пройдитесь в цикле по каждому `BarCodeResult`, возвращаемому `reader.ReadBarCodes()`. Объект результата содержит как общие поля (`CodeTypeName`, `CodeText`), так и специфические для Macro PDF417 расширения (`MacroPdf417FileID`, `MacroPdf417SegmentID`, `MacroPdf417SegmentsCount`).

```csharp
    // Step 4: Read all barcodes in the image and display the most relevant macro information
    foreach (BarCodeResult result in reader.ReadBarCodes())
    {
        Console.WriteLine($"Code Type : {result.CodeTypeName}");
        Console.WriteLine($"Code Text : {result.CodeText}");

        // Macro PDF417 specific fields
        Console.WriteLine($"File ID   : {result.Extended.Pdf417.MacroPdf417FileID}");
        Console.WriteLine($"Segment ID: {result.Extended.Pdf417.MacroPdf417SegmentID}");
        Console.WriteLine($"Segments  : {result.Extended.Pdf417.MacroPdf417SegmentsCount}");
    }
}
```

### Что делает каждая строка

| Line | Explanation |
|------|-------------|
| `result.CodeTypeName` | Человекочитаемое название обнаруженного типа штрихкода (например, “MacroPdf417”). |
| `result.CodeText` | Необработанные данные, закодированные в штрихкоде. |
| `result.Extended.Pdf417.MacroPdf417FileID` | Идентификатор, связывающий все сегменты документа macro PDF417. |
| `result.Extended.Pdf417.MacroPdf417SegmentID` | Индекс текущего сегмента в пределах всего документа. |
| `result.Extended.Pdf417.MacroPdf417SegmentsCount` | Общее количество сегментов, ожидаемых для документа. |

> **Полезный совет:** Сохраняйте macro‑поля в базе данных, если позже нужно собрать полный документ. `File ID` позволяет группировать сегменты, принадлежащие одному источнику.

## Шаг 5: Запустите программу и проверьте вывод

Соберите и запустите консольное приложение:

```bash
dotnet run
```

Типичный вывод консоли выглядит так:

```
Code Type : MacroPdf417
Code Text : 0123456789ABCD
File ID   : 101
Segment ID: 1
Segments  : 3
```

Если изображение содержит несколько символов Macro PDF417, цикл выводит каждый последовательно.

### Обработка распространённых граничных случаев

| Situation | Recommended handling |
|-----------|----------------------|
| **No barcode found** | Проверьте `reader.ReadBarCodes().Any()` перед циклом и выведите дружелюбное сообщение. |
| **Corrupted image** | Оберните создание `BarCodeReader` в блок `try/catch` для `BarCodeException`. |
| **Multiple barcode formats** | Используйте `DecodeType.AllSupported` и отфильтруйте результаты по `result.CodeTypeName == "MacroPdf417"`. |
| **Large images** | Уменьшите размер изображения перед декодированием для повышения производительности; библиотека принимает объект `Bitmap`. |

## Полный исходный код

Ниже приведена полная, автономная программа. Скопируйте её в `Program.cs` нового консольного проекта и замените `YOUR_DIRECTORY/ExtPDF417Meta.png` реальным путём к вашему изображению.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

namespace Pdf417Decoder
{
    class Program
    {
        static void Main(string[] args)
        {
            // Step 2: Specify the path to the image that contains a Macro PDF417 barcode
            string imagePath = "YOUR_DIRECTORY/ExtPDF417Meta.png";

            // Step 3: Create a BarCodeReader configured for MacroPdf417 decoding
            using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
            {
                // Step 4: Read all barcodes in the image and display the most relevant macro information
                foreach (BarCodeResult result in reader.ReadBarCodes())
                {
                    Console.WriteLine($"Code Type : {result.CodeTypeName}");
                    Console.WriteLine($"Code Text : {result.CodeText}");

                    // Macro PDF417 specific fields
                    Console.WriteLine($"File ID   : {result.Extended.Pdf417.MacroPdf417FileID}");
                    Console.WriteLine($"Segment ID: {result.Extended.Pdf417.MacroPdf417SegmentID}");
                    Console.WriteLine($"Segments  : {result.Extended.Pdf417.MacroPdf417SegmentsCount}");
                }
            }
        }
    }
}
```

## Заключение

Теперь вы знаете **how to decode pdf417** штрихкоды в C# и как **read barcode image c#** с помощью Aspose.BarCode. Руководство провело вас через настройку проекта, загрузку изображения, конфигурацию считывателя, извлечение результатов и обработку граничных случаев. Имея эту основу, вы можете интегрировать декодирование PDF417 в системы учёта, билетные валидаторы или любой рабочий процесс, использующий macro‑закодированные данные.

### Следующие шаги

* Исследуйте другие форматы штрихкодов, изменяя `DecodeType` (например, `DecodeType.QR`, `DecodeType.Code128`).  
* Объединяйте несколько декодированных сегментов для восстановления оригинального документа.  
* Используйте класс `BarCodeGenerator` для создания тестовых PDF417 штрихкодов «на лету».  

Не стесняйтесь экспериментировать с различными источниками изображений, настраивать вывод в консоль или внедрять логику декодирования в веб‑API для обработки в реальном времени. Приятного кодирования!

## Что вам стоит изучить дальше?

Следующие руководства охватывают тесно связанные темы, построенные на техниках, продемонстрированных в этом руководстве. Каждый ресурс включает полные рабочие примеры кода с пошаговыми объяснениями, чтобы помочь вам освоить дополнительные возможности API и исследовать альтернативные подходы к реализации в ваших проектах.

- [Как декодировать PDF417 в C# с примером считывателя штрихкода](/barcode/english/net/compact-pdf417-encoding/how-to-decode-pdf417-in-c-with-a-barcode-reader-example/)
- [Как генерировать PDF417 штрихкоды в C# с Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcodes-in-c-with-aspose-barcode/)
- [Как считать штрихкод с изображения c# используя Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/how-to-read-barcode-from-image-c-using-aspose-barcode/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}