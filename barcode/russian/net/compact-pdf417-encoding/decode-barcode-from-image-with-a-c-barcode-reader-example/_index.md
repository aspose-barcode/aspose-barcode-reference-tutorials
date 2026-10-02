---
category: general
date: 2026-09-10
description: Узнайте, как декодировать штрих‑код с изображения, используя лаконичный
  пример считывателя штрих‑кодов на C#, который читает коды Macro PDF417 всего в несколько
  строк.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- decode barcode from image
- c# barcode reader example
- read barcode C#
- barcode decoding tutorial
- Macro PDF417 C#
language: ru
lastmod: 2026-09-10
og_description: Декодируйте штрих‑код с изображения с помощью короткого примера считывателя
  штрих‑кодов на C#. Следуйте пошаговому руководству, чтобы мгновенно прочитать данные
  Macro PDF417.
og_image_alt: Screenshot of console output showing decoded Macro PDF417 barcode information
og_title: Декодировать штрих‑код из изображения с примером считывателя штрих‑кодов
  на C#
schemas:
- author: Aspose
  dateModified: '2026-09-10'
  description: Learn how to decode barcode from image using a concise C# barcode reader
    example that reads Macro PDF417 codes in just a few lines.
  headline: Decode barcode from image with a C# barcode reader example
  type: TechArticle
- description: Learn how to decode barcode from image using a concise C# barcode reader
    example that reads Macro PDF417 codes in just a few lines.
  name: Decode barcode from image with a C# barcode reader example
  steps:
  - name: '**Initialize** a `BarCodeReader` for the target image.'
    text: '**Initialize** a `BarCodeReader` for the target image.'
  - name: '**Iterate** over every detected barcode.'
    text: '**Iterate** over every detected barcode.'
  - name: '**Print** the standard and extended Macro PDF417 data.'
    text: '**Print** the standard and extended Macro PDF417 data.'
  type: HowTo
tags:
- barcode
- C#
- image processing
title: Декодировать штрих‑код из изображения с примером считывателя штрих‑кода на
  C#
url: /ru/net/compact-pdf417-encoding/decode-barcode-from-image-with-a-c-barcode-reader-example/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Декодировать штрих‑код с изображения с помощью примера считывателя штрих‑кодов на C#

Если вам нужно **декодировать штрих‑код с изображения**, это руководство покажет, как сделать это на C#. С помощью компактного **примера считывателя штрих‑кодов на C#** вы сможете прочитать данные Macro PDF417 всего в несколько строк кода.

Вы увидите полностью готовую программу, поймёте, почему каждый её элемент важен, и узнаете приёмы, позволяющие избежать распространённых ошибок. Внешняя документация не требуется — всё, что нужно, находится здесь.

## Что вы узнаете

- Установить необходимый пакет NuGet для декодирования штрих‑кодов.  
- Написать **пример считывателя штрих‑кодов на C#**, который открывает файл изображения и извлекает каждый штрих‑код.  
- Получить расширенные поля Macro PDF417, такие как идентификатор файла.  
- Проверить вывод и адаптировать код для других типов штрих‑кодов.

### Требования

- .NET 6.0 SDK или новее (код также работает с .NET Core 3.1 и .NET Framework 4.7+).  
- Базовые знания консольных приложений C#.  
- Файл изображения, содержащий штрих‑код Macro PDF417 (например, `MacroPdf417.png`).  

## Шаг 1: Установить библиотеку для штрих‑кодов

В примере используется **Aspose.BarCode for .NET**, широко применяемая библиотека, поддерживающая декодирование Macro PDF417.

```bash
dotnet add package Aspose.BarCode
```

> **Почему именно эта библиотека?**  
> Она предоставляет один класс `BarCodeReader`, который работает с множеством форматов, обеспечивает высокую точность и возвращает расширенную информацию для кодов Macro PDF417 — без дополнительной настройки.

## Шаг 2: Создать пример считывателя штрих‑кодов на C#

Создайте новый консольный проект и замените сгенерированный `Program.cs` кодом ниже. Пример состоит из трёх чётко очерченных действий:

1. **Инициализировать** `BarCodeReader` для целевого изображения.  
2. **Перебрать** каждый обнаруженный штрих‑код.  
3. **Вывести** стандартные и расширенные данные Macro PDF417.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

namespace BarcodeDemo
{
    internal class Program
    {
        private static void Main()
        {
            // Path to the image that contains the Macro PDF417 barcode
            const string imagePath = "YOUR_DIRECTORY/MacroPdf417.png";

            // 1️⃣ Create a BarCodeReader configured for Macro PDF417 decoding
            using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
            {
                // 2️⃣ Read all barcodes found in the image
                foreach (BarCodeResult result in reader.ReadBarCodes())
                {
                    // 3️⃣ Display basic information
                    Console.WriteLine($"Code Type: {result.CodeTypeName}");
                    Console.WriteLine($"Code Text: {result.CodeText}");

                    // 3️⃣ Display Macro PDF417 extended fields (if available)
                    if (result.Extended?.Pdf417?.MacroPdf417FileID != null)
                    {
                        Console.WriteLine($"Macro PDF417 File ID: {result.Extended.Pdf417.MacroPdf417FileID}");
                    }

                    Console.WriteLine(new string('-', 40));
                }
            }
        }
    }
}
```

### Пояснение каждой части

- **Конструктор `BarCodeReader`** — первый аргумент это путь к изображению; второй указывает библиотеке искать именно коды Macro PDF417. Такое целенаправленное декодирование повышает производительность по сравнению со сканированием всех возможных форматов.  
- **`ReadBarCodes()`** — возвращает перечисление всех штрих‑кодов, обнаруженных на изображении, позволяя обрабатывать несколько кодов в одном файле.  
- **`result.Extended.Pdf417.MacroPdf417FileID`** — Macro PDF417 хранит дополнительную мета‑информацию (идентификатор файла, количество сегментов и т.д.). Пример проверяет значение на `null`, чтобы избежать `NullReferenceException`, если изображение содержит не Macro‑штрих‑код.

## Шаг 3: Запустить программу и проверить вывод

Соберите и запустите консольное приложение:

```bash
dotnet run
```

Вы должны увидеть вывод, похожий на:

```
Code Type: MacroPdf417
Code Text: 1234567890ABCDEF
Macro PDF417 File ID: 42
----------------------------------------
```

Если изображение не содержит штрих‑код Macro PDF417, программа всё равно перечислит любые другие найденные форматы, но расширенное поле будет опущено.

## Полезный совет: Декодировать другие типы штрих‑кодов без значительных изменений кода

Чтобы **декодировать штрих‑код с изображения** другого формата, измените значение перечисления `DecodeType`:

```csharp
using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.QR))
```

Можно также передать `DecodeType.AllSupportedTypes`, чтобы библиотека сама определяла любой известный ей штрих‑код.

## Распространённые проблемы и как их избежать

| Симптом | Причина | Решение |
|---------|---------|---------|
| Нет вывода вообще | Неправильный путь к изображению или неподдерживаемый формат файла | Проверьте путь, убедитесь, что файл — поддерживаемое изображение (PNG, JPEG, BMP) |
| `result.Extended` равно null для Macro PDF417 | Штрих‑код не является вариантом Macro PDF417 | Убедитесь, что исходное изображение действительно содержит код Macro PDF417 |
| Исключение `System.IO.FileNotFoundException` | Отсутствует пакет NuGet во время выполнения | Выполните `dotnet restore` и убедитесь, что `Aspose.BarCode.dll` скопирован в папку вывода |

## Полный листинг исходного кода для быстрого копирования

Ниже представлена вся программа, готовая к копированию в `Program.cs`. Дополнительные файлы не требуются.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

namespace BarcodeDemo
{
    internal class Program
    {
        private static void Main()
        {
            const string imagePath = "YOUR_DIRECTORY/MacroPdf417.png";

            using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
            {
                foreach (BarCodeResult result in reader.ReadBarCodes())
                {
                    Console.WriteLine($"Code Type: {result.CodeTypeName}");
                    Console.WriteLine($"Code Text: {result.CodeText}");

                    if (result.Extended?.Pdf417?.MacroPdf417FileID != null)
                    {
                        Console.WriteLine($"Macro PDF417 File ID: {result.Extended.Pdf417.MacroPdf417FileID}");
                    }

                    Console.WriteLine(new string('-', 40));
                }
            }
        }
    }
}
```

## Следующие шаги

- **Исследовать другие расширенные поля**, такие как `MacroPdf417SegmentID` или `MacroPdf417FileSize`, чтобы построить рабочие процессы полной реконструкции документа.  
- **Интегрировать считыватель в веб‑API**, чтобы клиенты могли загружать изображения и мгновенно получать декодированные данные.  
- **Провести бенчмарк производительности**, декодируя большие партии изображений; `BarCodeReader` поддерживает асинхронную обработку в более новых версиях Aspose.

---

Следуя этому **примеру считывателя штрих‑кодов на C#**, вы получили надёжный способ **декодировать штрих‑код с изображения** и извлекать богатую информацию Macro PDF417. Экспериментируйте с различными значениями `DecodeType`, комбинируйте эту логику с наблюдателями файловой системы или внедряйте её в мобильные бек‑энды — ваши возможности по обработке штрих‑кодов готовы к масштабированию.


## Что стоит изучить дальше?


Следующие руководства охватывают тесно связанные темы, опираясь на техники, продемонстрированные в этом пособии. Каждый ресурс содержит полностью рабочие примеры кода с пошаговыми объяснениями, помогающими освоить дополнительные возможности API и исследовать альтернативные подходы в собственных проектах.

- [How to Read PDF417 in C# – Complete Barcode Reader Example](/barcode/english/net/compact-pdf417-encoding/how-to-read-pdf417-in-c-complete-barcode-reader-example/)
- [Generate barcode with text – Full PDF417 Macro Guide](/barcode/english/net/compact-pdf417-encoding/generate-barcode-with-text-full-pdf417-macro-guide/)
- [How to Create PDF417 Barcode with Aspose – Complete Step‑by‑Step Guide](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-with-aspose-complete-step-by-st/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}