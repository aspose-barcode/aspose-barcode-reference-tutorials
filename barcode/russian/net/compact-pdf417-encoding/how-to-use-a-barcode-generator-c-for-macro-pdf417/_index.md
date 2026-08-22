---
category: general
date: 2026-08-22
description: Учебник по генератору штрихкодов на C# показывает, как создать штрихкод
  Macro PDF417 с метаданными и сохранить его в формате PNG с помощью Aspose.BarCode.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- barcode generator C#
- Macro PDF417
- Aspose.BarCode
- C# barcode library
- PDF417 barcode
- barcode metadata
language: ru
lastmod: 2026-08-22
og_description: Генератор штрихкодов C# позволяет создавать штрихкод Macro PDF417
  с полными метаданными уровня файла и экспортировать его в PNG. Следуйте этому руководству,
  чтобы реализовать решение.
og_image_alt: Screenshot of a Macro PDF417 barcode generated with C#
og_title: Генератор штрихкодов C# – пошаговое создание Macro PDF417 штрихкодов
schemas:
- author: Aspose
  dateModified: '2026-08-22'
  description: barcode generator C# tutorial shows how to create a Macro PDF417 barcode
    with metadata and save it as PNG using Aspose.BarCode.
  headline: How to use a barcode generator C# for Macro PDF417
  type: TechArticle
tags:
- barcode
- C#
- PDF417
title: Как использовать генератор штрихкодов C# для Macro PDF417
url: /ru/net/compact-pdf417-encoding/how-to-use-a-barcode-generator-c-for-macro-pdf417/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Как использовать генератор штрих‑кодов C# для Macro PDF417

Если вам нужен **генератор штрих‑кодов C#**, способный создавать символ Macro PDF417 с метаданными уровня файла, это руководство предоставляет готовое решение, готовое к запуску. Вы увидите, как настроить внешний вид штрих‑кода, внедрить макро‑информацию, такую как идентификатор файла и количество сегментов, и, наконец, сохранить результат в виде PNG‑изображения.

В примере используется библиотека Aspose.BarCode, широко применяемая **C# barcode library**, поддерживающая полный набор функций PDF417. Внешние сервисы не требуются, код работает с .NET 6 и новее.

## Требования

Прежде чем начать, убедитесь, что у вас есть:

* .NET 6 SDK (или более поздняя версия) установлен.
* Visual Studio 2022, VS Code или другая IDE для C#.
* Ссылка NuGet на **Aspose.BarCode** (`dotnet add package Aspose.BarCode`).

Базовое понимание синтаксиса C# и концепции штрих‑кодов PDF417 поможет вам следовать инструкциям, но в руководстве подробно объяснены все параметры конфигурации.

## Что покрывается в руководстве

* Инициализация экземпляра **генератора штрих‑кодов C#** для формата Macro PDF417.  
* Настройка визуальных параметров, таких как X‑размер и количество колонок.  
* Передача полей уровня файла Macro PDF417: идентификатор файла, идентификатор сегмента, количество сегментов, имя файла, контрольная сумма, размер файла, метка времени, получатель, отправитель и флаг завершения.  
* Сохранение сгенерированного символа в PNG‑файл.  
* Советы по обработке граничных случаев, таких как большие размеры файлов или пользовательские метки времени.

По завершении этой статьи у вас будет автономная программа, генерирующая полностью совместимый штрих‑код Macro PDF417.

## Шаг 1: Создать экземпляр генератора штрих‑кодов C#

Первой операцией является создание `BarcodeGenerator` с перечислением `EncodeTypes.MacroPdf417` и текстом, который вы хотите закодировать. Конструктор также принимает строку полезной нагрузки, которая становится данными макро‑штрих‑кода.

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;

// Step 1: Create a barcode generator for Macro PDF417
using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MacroPdf417, "Sample text"))
{
    // Subsequent configuration goes here
}
```

**Почему это важно** – Флаг `EncodeTypes.MacroPdf417` сообщает Aspose.BarCode рассматривать символ как макро‑штрих‑код, включая дополнительные поля, описанные ниже. Без этого флага библиотека создала бы обычный PDF417 без метаданных уровня файла.

## Шаг 2: Настроить базовый внешний вид штрих‑кода (визуальные параметры PDF417)

Визуальная чёткость критична для надёжного сканирования. Два часто используемых параметра – ширина модуля (`XDimension`) и количество колонок. Их настройка позволяет сбалансировать размер и читаемость.

```csharp
    // Step 2: Adjust basic barcode appearance
    generator.Parameters.Barcode.XDimension.Pixels = 2;   // width of a single module
    generator.Parameters.Barcode.Pdf417.Columns = 5;    // number of columns in the symbol
```

* `XDimension.Pixels` управляет шириной каждой чёрной/белой полосы. Значение **2** хорошо подходит для большинства этикеточных принтеров.
* `Pdf417.Columns` определяет, сколько колонок будет использовать штрих‑код. Пять колонок дают компактный символ без потери ёмкости данных.

## Шаг 3: Определить информацию уровня файла Macro PDF417

Macro PDF417 расширяет стандартный формат PDF417 полями, описывающими, как большой файл разбивается на несколько сегментов штрих‑кода. Заполнение этих полей гарантирует, что сканеры смогут восстановить исходный файл.

```csharp
    // Step 3: Define Macro PDF417 file‑level information
    generator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;          // unique file identifier
    generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;            // current segment number (0‑indexed)
    generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;       // total number of segments
    generator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";      // optional logical file name
```

* `MacroPdf417FileID` должен быть одинаковым для всех сегментов, принадлежащих одному логическому файлу.
* `MacroPdf417SegmentID` увеличивается от **0** до `SegmentsCount‑1`.
* `MacroPdf417SegmentsCount` сообщает декодеру, сколько частей ожидать.
* `MacroPdf417FileName` необязателен, но полезен для человекочитаемой идентификации.

## Шаг 4: Установить дополнительные макро‑метаданные

Помимо основной информации о файле, спецификация допускает дополнительные поля, такие как контрольная сумма, размер файла, метка времени, получатель, отправитель и флаг завершения. Заполнение этих полей повышает целостность данных и их прослеживаемость.

```csharp
    // Step 4: Set additional macro metadata
    generator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234;                     // CCITT‑16 checksum
    generator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000;                  // file size in bytes
    generator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2024, 4, 1);
    generator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
    generator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
    generator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;
```

* `MacroPdf417Checksum` предоставляет 16‑битную контрольную сумму CCITT для всего файла; декодер может проверить целостность после восстановления.
* `MacroPdf417FileSize` должен точно отражать количество байтов оригинального файла; значения больше `2^31‑1` требуют 64‑битного поля, которое Aspose обрабатывает автоматически.
* `MacroPdf417TimeStamp` фиксирует время создания штрих‑кода. Используйте UTC, чтобы избежать неоднозначности часовых поясов.
* `MacroPdf417Addressee` и `MacroPdf417Sender` – произвольные строки, в которых можно хранить информацию о маршрутизации.
* `MacroPdf417Terminator` сигнализирует, что это последний сегмент; установите его в `Set` для последней части, иначе оставьте значение по умолчанию (`NotSet`).

**Совет для граничных случаев** – Если размер вашего файла превышает 4 ГБ, разбейте содержимое на несколько макросегментов и скорректируйте `SegmentsCount` соответственно. Библиотека управляет полем большого размера без переполнения.

## Шаг 5: Сохранить штрих‑код как PNG‑изображение

Последний шаг записывает сгенерированный символ на диск. PNG сохраняет точные пиксельные размеры и широко поддерживается сканирующим оборудованием.

```csharp
    // Step 5: Save the generated barcode as a PNG image
    generator.Save("YOUR_DIRECTORY/MacroPdf417.png", BarCodeImageFormat.Png);
}
```

Замените `YOUR_DIRECTORY` на абсолютный или относительный путь, в который процесс может записать файл. Перечисление `BarCodeImageFormat.Png` гарантирует безпотерянный вывод.

**Почему PNG?** – Растровые форматы, такие как PNG, сохраняют резкие границы модулей, что важно для сканеров, полагающихся на контрастные края. Если нужен векторный формат, Aspose также поддерживает `Pdf` и `Svg`.

## Полный пример, готовый к запуску

Ниже представлена полная программа, которую можно скопировать в консольное приложение. В ней включены необходимые директивы `using` и метод `Main`.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace MacroPdf417Demo
{
    class Program
    {
        static void Main()
        {
            // Create a barcode generator for Macro PDF417 with sample payload
            using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MacroPdf417, "Sample text"))
            {
                // Adjust visual appearance
                generator.Parameters.Barcode.XDimension.Pixels = 2;
                generator.Parameters.Barcode.Pdf417.Columns = 5;

                // Define macro file‑level fields
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
                generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;
                generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";

                // Add optional metadata
                generator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234;
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000;
                generator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2024, 4, 1);
                generator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
                generator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
                generator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;

                // Export to PNG
                generator.Save("MacroPdf417.png", BarCodeImageFormat.Png);
            }

            Console.WriteLine("Macro PDF417 barcode generated successfully.");
        }
    }
}
```

### Ожидаемый результат

Запуск программы создаёт файл **MacroPdf417.png** в рабочем каталоге проекта. Открытие изображения показывает компактный PDF417‑штрих‑код с внедрёнными макро‑полями. Сканирование изображения совместимым считывателем PDF417 (например, ZXing, декодером Aspose.BarCode) возвращает исходную строку `"Sample text"` вместе с макро‑метаданными.

## Часто задаваемые вопросы и устранение неполадок

| Вопрос | Ответ |
|----------|--------|
| *Что делать, если штрих‑код слишком велик для целевой этикетки?* | Уменьшите `XDimension.Pixels` или увеличьте `Pdf417.Columns`. Оба параметра влияют на общий размер. |
| *Можно ли генерировать векторное изображение вместо PNG?* | Да. Вызовите `generator.Save("MacroPdf417.svg", BarCodeImageFormat.Svg);` для масштабируемого вывода. |
| *Как проверить контрольную сумму после сканирования?* | Декодер Aspose.BarCode автоматически валидирует `MacroPdf417Checksum` и сообщает о несоответствиях в объекте `MacroPdf417Result`. |
| *Совместима ли библиотека с .NET Core?* | Пакет NuGet поддерживает .NET Standard 2.0+, что покрывает .NET Core, .NET 5, .NET 6 и более новые версии. |
| *Что если нужно внедрить бинарные данные вместо текста?* | Преобразуйте бинарный payload в Base64 или используйте перегрузку `EncodeTypes.MacroPdf417`, принимающую массив байтов. |

## Профессиональные советы для продакшн‑использования

* **Кешировать генератор** –


## Что следует изучить дальше?


Следующие руководства охватывают близкие темы, расширяющие техники, продемонстрированные в этом руководстве. Каждый ресурс содержит полностью рабочие примеры кода с пошаговыми объяснениями, чтобы помочь вам освоить дополнительные возможности API и исследовать альтернативные подходы в ваших проектах.

- [Как создать штрих‑код – Compact PDF417 с Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [Как считывать штрих‑коды из PDF на Java с помощью Aspose.BarCode](/barcode/english/java/document-barcode-recognition/recognizing-barcodes-from-pdf/)
- [Создание штрих‑кода Codabar с Aspose.Barcode – API генератора и считывателя](/barcode/english/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}