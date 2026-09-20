---
category: general
date: 2026-09-19
description: Как декодировать PDF417 в C# — научитесь считывать штрихкоды с изображения,
  используя лаконичный пример считывателя штрихкодов, который извлекает полные данные
  Macro PDF417.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to decode pdf417
- read barcodes from image
- decode pdf417 barcode
- c# barcode reader example
language: ru
lastmod: 2026-09-19
og_description: Как декодировать PDF417 в C# с пошаговым примером считывателя штрихкода.
  Извлеките каждое поле Macro PDF417 из изображения за секунды.
og_image_alt: Screenshot showing how to decode PDF417 in C# using a barcode reader
og_title: Как декодировать PDF417 в C# – полное руководство по чтению штрихкода
schemas:
- author: Aspose
  dateModified: '2026-09-19'
  description: How to decode PDF417 in C# – learn to read barcodes from image using
    a concise barcode reader example that extracts full Macro PDF417 data.
  headline: How to decode PDF417 in C# with a barcode reader example
  type: TechArticle
tags:
- barcode
- pdf417
- csharp
title: Как декодировать PDF417 в C# с примером считывателя штрихкода
url: /ru/net/compact-pdf417-encoding/how-to-decode-pdf417-in-c-with-a-barcode-reader-example/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Как декодировать PDF417 в C# с примером считывателя штрихкодов

Если вам нужно декодировать PDF417 в C#, это руководство покажет, как именно декодировать PDF417 из файла изображения. Вы узнаете, как считывать штрихкоды с изображения, получать расширенные поля Macro PDF417 и интегрировать решение в любой проект .NET.

Декодирование штрихкодов PDF417 широко используется в логистике, билетных системах и проверке личности. В этом учебнике рассматривается всё, что необходимо для готовой к производству реализации, включая требуемые библиотеки, полный исходный код и рекомендации по обработке граничных случаев.

## Требования

Прежде чем начать, убедитесь, что у вас есть:

- .NET 6.0 или новее  
- Visual Studio 2022 (или любая IDE, поддерживающая C#)  
- NuGet‑пакет **Aspose.BarCode for .NET** (версия 23.11 или новее)  

Пакет можно добавить следующей командой:

```bash
dotnet add package Aspose.BarCode
```

Класс `BarCodeReader` из этой библиотеки поддерживает тип декодирования `MacroPdf417`, необходимый для полной извлечения PDF417.

## Шаг 1: Как декодировать PDF417 в C# – инициализация считывателя

Первый шаг создаёт экземпляр `BarCodeReader`, который работает с изображением Macro PDF417. Флаг `DecodeType.MacroPdf417` указывает библиотеке разбирать расширенные макрополя.

```csharp
using System;
using Aspose.BarCode;               // Core barcode classes
using Aspose.BarCode.BarCodeRecognition; // Reader and result types

// Path to the Macro PDF417 image
string imagePath = @"YOUR_DIRECTORY\MacroPdf417.png";

// Initialise the reader for Macro PDF417 decoding
using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
{
    // Continue with step 2...
```

**Почему это важно:** Инициализация с `MacroPdf417` включает свойство `Extended.Pdf417` у каждого `BarCodeResult`, предоставляя доступ к метаданным уровня файла, таким как идентификаторы сегментов и метки времени.

## Шаг 2: Считывание штрихкодов с изображения

Изображение PDF417 может содержать несколько макросегментов. Метод `ReadBarCodes()` возвращает перечисление всех обнаруженных штрихкодов, поэтому их можно безопасно перебрать в цикле.

```csharp
    // Step 2: Read every barcode present in the image
    foreach (BarCodeResult result in reader.ReadBarCodes())
    {
        // Continue with step 3...
```

**Совет:** Если вы ожидаете только один штрихкод, можно выйти из цикла после первой итерации, но перебор всех результатов гарантирует захват каждого сегмента в многостраничных документах.

## Шаг 3: Декодирование штрихкода PDF417 – извлечение базовых и расширенных данных

Внутри цикла выводятся как общие сведения о штрихкоде, так и поля, специфичные для Macro. Объект `Extended.Pdf417` содержит все метаданные, определённые стандартом PDF417.

```csharp
        // Basic barcode information
        Console.WriteLine($"CodeType: {result.CodeTypeName}");
        Console.WriteLine($"CodeText: {result.CodeText}");

        // Macro PDF417 extended data
        Console.WriteLine($"Pdf417MacroFileID: {result.Extended.Pdf417.MacroPdf417FileID}");
        Console.WriteLine($"Pdf417MacroSegmentID: {result.Extended.Pdf417.MacroPdf417SegmentID}");
        Console.WriteLine($"Pdf417MacroSegmentsCount: {result.Extended.Pdf417.MacroPdf417SegmentsCount}");
        Console.WriteLine($"Pdf417MacroFileName: {result.Extended.Pdf417.MacroPdf417FileName}");
        Console.WriteLine($"Pdf417MacroChecksum: {result.Extended.Pdf417.MacroPdf417Checksum}");
        Console.WriteLine($"Pdf417MacroFileSize: {result.Extended.Pdf417.MacroPdf417FileSize}");
        Console.WriteLine($"Pdf417MacroTimeStamp: {result.Extended.Pdf417.MacroPdf417TimeStamp}");
        Console.WriteLine($"Pdf417MacroAddressee: {result.Extended.Pdf417.MacroPdf417Addressee}");
        Console.WriteLine($"Pdf417MacroSender: {result.Extended.Pdf417.MacroPdf417Sender}");
        Console.WriteLine($"MacroPdf417Terminator: {result.Extended.Pdf417.MacroPdf417Terminator}");
    }
}
```

**Описание ключевых полей**

| Поле | Значение |
|------|----------|
| `MacroPdf417FileID` | Идентификатор, группирующий все сегменты, принадлежащие одному логическому файлу |
| `MacroPdf417SegmentID` | Индекс текущего сегмента (начинается с 0) |
| `MacroPdf417SegmentsCount` | Общее количество ожидаемых сегментов для файла |
| `MacroPdf417FileName` | Необязательное имя файла, встроенное в макрос |
| `MacroPdf417Checksum` | CRC‑16 контрольная сумма для проверки целостности данных |
| `MacroPdf417FileSize` | Исходный размер файла в байтах |
| `MacroPdf417TimeStamp` | Метка времени создания макросегмента |
| `MacroPdf417Addressee` | Предназначенный получатель данных макросегмента |
| `MacroPdf417Sender` | Отправитель данных макросегмента |
| `MacroPdf417Terminator` | Булевый флаг, указывающий, что это последний сегмент |

Доступ к этим полям позволяет восстановить оригинальный документ, проверить его целостность или маршрутизировать данные в зависимости от информации об отправителе/получателе.

## Шаг 4: Полный пример считывателя штрихкодов на C# – собираем всё вместе

Ниже представлен полностью готовый к запуску код. Замените `YOUR_DIRECTORY` на путь к папке, где находится ваш файл `MacroPdf417.png`.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

namespace Pdf417Decoder
{
    class Program
    {
        static void Main()
        {
            // Path to the image containing a Macro PDF417 barcode
            string imagePath = @"YOUR_DIRECTORY\MacroPdf417.png";

            // Initialise the reader for Macro PDF417 decoding
            using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
            {
                // Iterate through all detected barcodes
                foreach (BarCodeResult result in reader.ReadBarCodes())
                {
                    // Basic information
                    Console.WriteLine($"CodeType: {result.CodeTypeName}");
                    Console.WriteLine($"CodeText: {result.CodeText}");

                    // Extended Macro PDF417 data
                    Console.WriteLine($"Pdf417MacroFileID: {result.Extended.Pdf417.MacroPdf417FileID}");
                    Console.WriteLine($"Pdf417MacroSegmentID: {result.Extended.Pdf417.MacroPdf417SegmentID}");
                    Console.WriteLine($"Pdf417MacroSegmentsCount: {result.Extended.Pdf417.MacroPdf417SegmentsCount}");
                    Console.WriteLine($"Pdf417MacroFileName: {result.Extended.Pdf417.MacroPdf417FileName}");
                    Console.WriteLine($"Pdf417MacroChecksum: {result.Extended.Pdf417.MacroPdf417Checksum}");
                    Console.WriteLine($"Pdf417MacroFileSize: {result.Extended.Pdf417.MacroPdf417FileSize}");
                    Console.WriteLine($"Pdf417MacroTimeStamp: {result.Extended.Pdf417.MacroPdf417TimeStamp}");
                    Console.WriteLine($"Pdf417MacroAddressee: {result.Extended.Pdf417.MacroPdf417Addressee}");
                    Console.WriteLine($"Pdf417MacroSender: {result.Extended.Pdf417.MacroPdf417Sender}");
                    Console.WriteLine($"MacroPdf417Terminator: {result.Extended.Pdf417.MacroPdf417Terminator}");
                    Console.WriteLine(new string('-', 40));
                }
            }

            Console.WriteLine("Decoding complete.");
        }
    }
}
```

**Ожидаемый вывод в консоль (пример)**

```
CodeType: MacroPdf417
CodeText: https://example.com/document.pdf
Pdf417MacroFileID: 12
Pdf417MacroSegmentID: 0
Pdf417MacroSegmentsCount: 3
Pdf417MacroFileName: document.pdf
Pdf417MacroChecksum: 0x1A2B
Pdf417MacroFileSize: 452312
Pdf417MacroTimeStamp: 2024-03-15T14:27:00Z
Pdf417MacroAddressee: LogisticsDept
Pdf417MacroSender: Warehouse01
MacroPdf417Terminator: False
----------------------------------------
Decoding complete.
```

Точные значения будут отличаться в зависимости от содержимого вашего штрихкода Macro PDF417.

## Обработка распространённых граничных случаев

| Ситуация | Рекомендованный подход |
|----------|------------------------|
| **Штрихкод не обнаружен** | Проверьте путь к изображению, убедитесь, что файл не повреждён, и что штрихкод видим (достаточный контраст). |
| **Неполные макросегменты** | Используйте `MacroPdf417SegmentsCount` для обнаружения отсутствующих частей. Запросите недостающие сегменты у источника и повторно запустите декодер. |
| **Большие изображения, вызывающие нагрузку на память** | Загрузите изображение в `System.Drawing.Bitmap` с уменьшённым разрешением перед передачей в `BarCodeReader`. |
| **Не‑Macro PDF417** | Поменяйте `DecodeType.MacroPdf417` на `DecodeType.Pdf417`, если нужен только обычный текст штрихкода. |

## Профессиональные советы

- **Пакетная обработка:** Оберните логику считывателя в метод, принимающий список путей к файлам. Переиспользуйте один экземпляр `BarCodeReader` на поток, чтобы снизить накладные расходы на создание объектов.  
- **Производительность:** Для сценариев с высоким пропуском включите свойство `ReaderOptions.ReadQuality`, чтобы сбалансировать скорость и точность.  
- **Безопасность:** Проверяйте `CodeText` перед использованием в операциях с файловой системой, чтобы предотвратить атаки типа обхода пути.

## Заключение

В этом учебнике вы узнали, как декодировать PDF417 в C#, считывая штрихкоды с изображения, извлекая каждый Macro PDF417‑поле и создавая полноценный пример считывателя штрихкодов на C#. Решение работает с последней версией библиотеки Aspose.BarCode, поддерживает многосегментные макросы и даёт практические рекомендации для реальных проектов.

Далее изучайте связанные темы, такие как **чтение QR‑кодов**, **пакетная обработка штрихкодов** и **генерация штрихкодов PDF417**, чтобы расширить свой набор инструментов для автоматизации документов. Экспериментируйте с различными источниками изображений, интегрируйте код в сервисы ASP.NET или сохраняйте извлечённые метаданные в базе данных. Приятного кодирования!

## Что вам следует изучить дальше?

Следующие учебники охватывают тесно связанные темы, построенные на техниках, продемонстрированных в этом руководстве. Каждый ресурс включает полностью работающие примеры кода с пошаговыми объяснениями, чтобы помочь вам освоить дополнительные возможности API и исследовать альтернативные подходы в собственных проектах.

- [How to Read PDF417 in C# – Complete Barcode Reader Example](/barcode/english/net/compact-pdf417-encoding/how-to-read-pdf417-in-c-complete-barcode-reader-example/)
- [How to Generate PDF417 Barcode Image in C# with Aspose](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-image-in-c-with-aspose/)
- [Read barcode from image – C# barcode reader example](/barcode/english/net/one-dimensional-barcode-types/read-barcode-from-image-c-barcode-reader-example/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}