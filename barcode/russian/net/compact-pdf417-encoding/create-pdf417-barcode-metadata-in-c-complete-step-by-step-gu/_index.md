---
category: general
date: 2026-09-28
description: Создайте метаданные штрих‑кода PDF417 в C# с помощью Aspose.BarCode.
  Это руководство показывает все настройки, необходимые для внедрения идентификатора
  файла, меток времени и прочего.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create pdf417 barcode metadata
- increase barcode resolution
- macro pdf417 c#
- aspose barcode c#
- barcode metadata fields
lastmod: 2026-09-28
og_description: Узнайте, как создать метаданные штрих‑кода PDF417 в C# с использованием
  Aspose.BarCode. В учебнике рассматриваются настройки Macro PDF417, поля метаданных,
  экспорт изображений и поддержка Unicode.
og_image_alt: Screenshot of a generated PDF417 barcode containing metadata fields
og_title: Создание метаданных штрих‑кода PDF417 в C# – пошаговое руководство
schemas:
- author: Aspose
  dateModified: '2026-09-28'
  description: Create PDF417 barcode metadata in C# using Aspose.BarCode. Learn Macro
    PDF417 settings, save as PNG, and handle Unicode text.
  headline: Create PDF417 barcode metadata in C# – Complete Step‑by‑Step Guide
  type: TechArticle
- description: Create PDF417 barcode metadata in C# using Aspose.BarCode. Learn Macro
    PDF417 settings, save as PNG, and handle Unicode text.
  name: Create PDF417 barcode metadata in C# – Complete Step‑by‑Step Guide
  steps:
  - name: Setting up the Aspose.BarCode NuGet package.
    text: Setting up the Aspose.BarCode NuGet package.
  - name: Initializing a `BarcodeGenerator` for **Macro PDF417**.
    text: Initializing a `BarcodeGenerator` for **Macro PDF417**.
  - name: Populating every useful **barcode metadata field** (file ID, segment ID,
      checksum, etc.).
    text: Populating every useful **barcode metadata field** (file ID, segment ID,
      checksum, etc.).
  - name: Saving the barcode to disk and verifying the output.
    text: Saving the barcode to disk and verifying the output.
  type: HowTo
- questions:
  - answer: Increase `XDimension.Pixels` or switch to a higher‑resolution image format.
    question: What if the barcode looks blurry?
  - answer: No. Only the fields required by your downstream system are mandatory.
      Unused fields can stay at their defaults.
    question: Do I need to set every metadata field?
  - answer: Yes—loop over the data, increment `MacroPdf417SegmentID`, and generate
      a separate barcode for each segment. Remember to keep `MacroPdf417FileID` consistent
      across all segments.
    question: Can I generate a multi‑segment file automatically?
  - answer: Absolutely. The sample text contains `Å`, `ó`, and `©`, showing that Aspose.BarCode
      handles UTF‑8 out of the box.
    question: Is Unicode supported?
  type: FAQPage
tags:
- barcode
- csharp
- aspose
- pdf417
title: Создание метаданных штрих‑кода PDF417 в C# – Полное пошаговое руководство
url: /ru/net/compact-pdf417-encoding/create-pdf417-barcode-metadata-in-c-complete-step-by-step-gu/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Создание метаданных штрих‑кода PDF417 в C# – Полное пошаговое руководство

Когда‑нибудь вам нужно было **создать метаданные штрих‑кода PDF417** в C#, но вы не знали, какие свойства настроить? Вы не одиноки — разработчики часто сталкиваются с проблемой, когда спецификация требует такие вещи, как идентификаторы файлов, количество сегментов или пользовательские метки времени.  

Хорошая новость в том, что Aspose.BarCode делает это проще простого. В этом руководстве мы создадим `BarcodeGenerator` для **Macro PDF417**, добавим все важные метаданные и сохраним результат в виде PNG‑изображения. К концу вы получите полностью функциональный штрих‑код, готовый к использованию в любой системе управления цепочками поставок или документами.

## Быстрые ответы
- **Какой основной класс для генерации штрих‑кодов?** Класс `BarcodeGenerator` создает изображения штрих‑кодов на основе предоставленных настроек.  
- **Какая настройка контролирует резкость изображения?** Увеличьте `XDimension.Pixels` или используйте формат более высокого разрешения, например PNG.  
- **Нужно ли заполнять каждое поле метаданных?** Нет. Обязательными являются только те поля, которые требуются вашей последующей системе.  
- **Можно ли встраивать символы Unicode?** Да — Aspose.BarCode поддерживает UTF‑8 из коробки, как показано в примере текста.  
- **Сколько типов штрих‑кодов поддерживает Aspose.BarCode?** Более 30 символогий, включая PDF417 длиной до 5 000 модулей.

## Что покрывает данное руководство

Мы рассмотрим:

1. Настройку пакета Aspose.BarCode NuGet.  
2. Инициализацию `BarcodeGenerator` для **Macro PDF417**.  
3. Заполнение всех полезных **полей метаданных штрих‑кода** (file ID, segment ID, checksum и т.д.).  
4. Сохранение штрих‑кода на диск и проверку результата.  

Предыдущий опыт работы с Macro PDF417 не требуется — достаточно базовых знаний C# и актуального .NET runtime.  

Зачем это нужно? Встраивание богатых метаданных непосредственно в штрих‑код позволяет сканерам на стороне получателя проверять целостность передачи файлов, обнаруживать отсутствующие сегменты или даже запускать автоматические рабочие процессы. Другими словами, вы получаете **надёжные, самодокументирующиеся данные** без отдельного обращения к базе данных.

## Как создать метаданные штрих‑кода PDF417 в C#?

Загрузите `BarcodeGenerator`, настроенный для `EncodeTypes.MacroPdf417`, задайте необходимые свойства метаданных и вызовите `Save`, чтобы записать PNG‑файл. Этот трёхшаговый процесс обрабатывает Unicode‑текст, назначает уникальный идентификатор файла и при необходимости разбивает большой объём данных на несколько сегментов. Подход работает на .NET 6+, .NET Framework 4.7+ и требует только пакет Aspose.BarCode NuGet.

### Шаг 1: установить пакет Aspose.BarCode NuGet

Вы можете установить пакет с помощью следующей команды:

```bash
dotnet add package Aspose.BarCode
```

Теперь, когда у нас есть основа, давайте перейдём к реальной реализации.

## Шаг 1: инициализировать BarcodeGenerator для Macro PDF417

Класс `BarcodeGenerator` создает изображения штрих‑кодов на основе предоставленных настроек. Первое, что нам нужно, — это экземпляр `BarcodeGenerator`, настроенный для **Macro PDF417**. Это сообщает Aspose.BarCode, какой алгоритм кодирования использовать, и предоставляет место для ввода читаемого человеком текста.

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;
using System;

// Step 1: Create a BarcodeGenerator for Macro PDF417 with the desired text
using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MacroPdf417, "Åspóse.Barcóde©"))
{
    // The rest of the steps will go inside this using block.
}
```

> **Почему это важно:** `EncodeTypes.MacroPdf417` активирует расширенный режим PDF417, поддерживающий метаданные, такие как идентификаторы файлов и номера сегментов. Пример текста содержит символы Unicode (`Å`, `ó`, `©`), демонстрируя, что генератор корректно обрабатывает ввод не‑ASCII.

## Шаг 2: определить базовый внешний вид штрих‑кода

`XDimension` задаёт ширину каждого модуля штрих‑кода в пикселях. Прежде чем добавлять метаданные, следует установить несколько визуальных параметров, чтобы штрих‑код не был микроскопической точкой. `XDimension` контролирует ширину модуля, а `Columns` влияет на общую форму.

```csharp
// Step 2: Define basic barcode appearance
generator.Parameters.Barcode.XDimension.Pixels = 2;   // module width
generator.Parameters.Barcode.Pdf417.Columns = 5;     // number of columns
```

> **Совет:** Ширина в `2` пикселя хорошо подходит для отображения на экране и большинства принтеров. Если требуется печать с более высоким разрешением, увеличьте её до `3` или `4`.

## Шаг 3: заполнить поля метаданных macro PDF417

Теперь начинается основная часть руководства — добавление **полей метаданных штрих‑кода**. Каждое свойство напрямую соответствует сегменту спецификации Macro PDF417.

```csharp
// Step 3: Set Macro PDF417 metadata
generator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;               // Unique file identifier
generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;                // Current segment number
generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;            // Total number of segments
generator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";           // Logical file name
generator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234;               // CCITT‑16 checksum
generator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400000;             // File size in bytes
generator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2019, 11, 1);
generator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";           // Intended recipient
generator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";              // Sender identifier
generator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;
```

### Что делает каждое свойство

| Свойство | Назначение | Типичное значение |
|----------|------------|-------------------|
| **MacroPdf417FileID** | Глобальный уникальный идентификатор всего набора файлов. | `12345678` |
| **MacroPdf417SegmentID** | Индекс текущего сегмента (начинается с `0`). | `12` |
| **MacroPdf417SegmentsCount** | Общее количество ожидаемых сегментов для файла. | `20` |
| **MacroPdf417FileName** | Человекочитаемое имя, часто оригинальное имя файла. | `"file01"` |
| **MacroPdf417Checksum** | 16‑битная контрольная сумма CCITT для обнаружения ошибок. | `1234` |
| **MacroPdf417FileSize** | Размер оригинального файла в байтах. | `400000` |
| **MacroPdf417TimeStamp** | Время генерации файла. | `new DateTime(2019,11,1)` |
| **MacroPdf417Addressee** | Необязательное поле, указывающее получателя. | `"street"` |
| **MacroPdf417Sender** | Необязательное поле, указывающее систему‑отправитель. | `"aspose"` |
| **MacroPdf417Terminator** | Флаг, указывающий сканеру, что это последний сегмент. | `Pdf417MacroTerminator.Set` |

> **Зачем это нужно:** Сканеры, поддерживающие Macro PDF417, могут собрать много‑сегментный файл, проверить целостность с помощью контрольной суммы и даже отклонить устаревшие данные на основе метки времени. Это устраняет необходимость в отдельном манифест‑файле.

## Шаг 4: сохранить изображение штрих‑кода

`Save` записывает сгенерированное изображение штрих‑кода в файл выбранного формата. После установки всех параметров мы просто вызываем `Save`. В примере PNG‑файл сохраняется в указанную вами папку.

```csharp
// Step 4: Save the barcode image
generator.Save("YOUR_DIRECTORY/ExtPDF417Meta.png", BarCodeImageFormat.Png);
```

> **Особый случай:** Если вы планируете позже встраивать штрих‑код в PDF, возможно, предпочтете `BarCodeImageFormat.Jpeg` или `Pdf`. PNG сохраняет детали без потерь, что удобно для проверки.

## Полный рабочий пример

Объединив всё вместе, представляем полный пример программы, который вы можете скопировать и вставить в консольное приложение:

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Create a BarcodeGenerator for Macro PDF417 with Unicode text
        using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MacroPdf417, "Åspóse.Barcóde©"))
        {
            // Basic appearance
            generator.Parameters.Barcode.XDimension.Pixels = 2;
            generator.Parameters.Barcode.Pdf417.Columns = 5;

            // Macro PDF417 metadata
            generator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
            generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;
            generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;
            generator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";
            generator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234;
            generator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400000;
            generator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2019, 11, 1);
            generator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
            generator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
            generator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;

            // Save as PNG
            generator.Save("ExtPDF417Meta.png", BarCodeImageFormat.Png);
        }

        Console.WriteLine("Macro PDF417 barcode with metadata saved successfully.");
    }
}
```

### Ожидаемый результат

Запуск программы создаёт файл с именем **ExtPDF417Meta.png** в папке исполняемого файла. Откройте его в любом просмотрщике изображений, и вы увидите плотный, высококонтрастный штрих‑код PDF417. Если просканировать его считывателем, поддерживающим Macro PDF417, сканер вернёт установленные нами значения метаданных — идентификатор файла `12345678`, сегмент `12` из `20` и т.д.

## Распространённые вопросы и подводные камни

- **Что делать, если штрих‑код выглядит размытым?** Увеличьте `XDimension.Pixels` или переключитесь на формат изображения с более высоким разрешением.  
- **Нужно ли задавать каждое поле метаданных?** Нет. Обязательными являются только те поля, которые требуются вашей последующей системе. Неиспользуемые поля могут оставаться со значениями по умолчанию.  
- **Можно ли автоматически генерировать много‑сегментный файл?** Да — выполните цикл по данным, увеличивая `MacroPdf417SegmentID`, и генерируйте отдельный штрих‑код для каждого сегмента. Не забудьте сохранять `MacroPdf417FileID` одинаковым во всех сегментах.  
- **Поддерживается ли Unicode?** Абсолютно. Пример текста содержит `Å`, `ó` и `©`, показывая, что Aspose.BarCode обрабатывает UTF‑8 из коробки.

## Часто задаваемые вопросы

**В: Сколько форматов штрих‑кодов поддерживает Aspose.BarCode?**  
Aspose.BarCode поддерживает более 30 символогий штрих‑кодов, включая 1D, 2D и почтовые коды, и может генерировать штрих‑коды PDF417 длиной до 5 000 модулей.

**В: Можно ли встроить штрих‑код непосредственно в PDF‑документ?**  
Да — используйте библиотеку `Aspose.Pdf`, чтобы разместить сгенерированный PNG или JPEG на странице PDF, сохраняя векторное качество.

**В: Какие версии .NET совместимы?**  
Библиотека работает с .NET Framework 4.7+, .NET Core 3.1, .NET 5, .NET 6 и более новыми версиями.

**В: Как проверить метаданные после сканирования?**  
Используйте `BarcodeReader` с `DecodeType = DecodeType.MacroPdf417`, чтобы программно получить поля метаданных.

**В: Есть ли ограничение на размер файла, который можно закодировать?**  
Aspose.BarCode может обрабатывать файлы до 10 МБ необработанных данных в одном потоке Macro PDF417, автоматически разбивая более крупные данные на несколько сегментов.

## Следующие шаги: выход за пределы базовых знаний

Теперь, когда вы знаете, как **создавать метаданные штрих‑кода PDF417**, вы можете изучить следующее:

- **Встраивание штрих‑кодов в PDF** с помощью `Aspose.Pdf` для сквозной генерации документов.  
- **Чтение метаданных** с помощью `BarcodeReader` для программной проверки сканирований.  
- **Настройка цветов** (передний/фон) для брендинга.  
- **Интеграция с базой данных** для автоматического заполнения полей, таких как `FileID` или `Timestamp`.

Все эти темы связаны с нашими вторичными ключевыми словами — **increase barcode resolution**, **macro pdf417**, **aspose barcode c#**, **barcode metadata fields**, и **c# barcode generation** — поэтому вы найдёте множество материалов для дальнейшего обучения.

## Заключение

Мы только что прошли полный, готовый к продакшну пример того, как **создавать метаданные штрих‑кода PDF417** в C#. От установки Aspose.BarCode, инициализации `BarcodeGenerator`, заполнения всех соответствующих **полей метаданных штрих‑кода** до окончательного сохранения чёткого PNG — процесс прост, как только вы знаете нужные свойства.

Попробуйте, измените значения и посмотрите, как реагируют сканеры. Гибкость Macro PDF417 позволяет вам внедрять всё, что требуется последующей системе, — всё в одном сканируемом изображении. Приятного кодирования, и пусть ваши штрих‑коды всегда будут без ошибок!

## Что вам стоит изучить дальше?

Следующие руководства охватывают тесно связанные темы, построенные на техниках, продемонстрированных в этом руководстве. Каждый ресурс включает полные рабочие примеры кода с пошаговыми объяснениями, чтобы помочь вам освоить дополнительные возможности API и исследовать альтернативные подходы к реализации в ваших проектах.

- [Как создать штрих‑код — Compact PDF417 с Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [java библиотека штрих‑кодов — Добавить штрих‑код в PDF с помощью Aspose](/barcode/english/java/barcode-basics/adding-barcode-to-pdf-document/)
- [Как создать штрих‑код — Компактный PDF417 с Aspose.BarCode](/barcode/german/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)

---

**Последнее обновление:** 2026-09-28  
**Тестировано с:** Aspose.BarCode 24.10 for .NET  
**Автор:** Aspose

## Связанные руководства

- [Создание штрих‑кода Pdf417 с Aspose Barcode: пошаговое руководство](/barcode/net/compact-pdf417-encoding/create-pdf417-barcode-with-aspose-barcode-step-by-step-guide/)
- [Пример Aspose Barcode: генерация Macro Pdf417 в C](/barcode/net/compact-pdf417-encoding/aspose-barcode-example-generate-macro-pdf417-in-c/)
- [Как сгенерировать изображение штрих‑кода Pdf417 в C с помощью Aspose](/barcode/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-image-in-c-with-aspose/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}