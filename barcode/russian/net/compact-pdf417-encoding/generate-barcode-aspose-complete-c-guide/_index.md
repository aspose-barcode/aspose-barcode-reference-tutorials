---
category: general
date: 2026-08-12
description: Создайте штрих‑код Aspose с помощью Aspose.BarCode и узнайте, как генерировать
  PDF417 с пользовательским текстом за несколько простых шагов.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate barcode aspose
- how to generate pdf417
- create barcode custom text
- Aspose.BarCode macro pdf417
- barcode metadata Aspose
language: ru
lastmod: 2026-08-12
og_description: Создайте штрих‑код с помощью Aspose.BarCode. Этот учебник показывает,
  как сгенерировать PDF417 с пользовательским текстом, макро‑метаданными и сохранить
  результат в формате PNG.
og_image_alt: Screenshot of a MacroPdf417 barcode generated with Aspose.BarCode in
  C#
og_title: Создание штрих‑кода Aspose – пошаговое руководство
schemas:
- author: Aspose
  dateModified: '2026-08-12'
  description: Generate barcode aspose with Aspose.BarCode and learn how to generate
    pdf417 with custom text in a few easy steps.
  headline: Generate barcode aspose – complete C# guide
  type: TechArticle
tags:
- Aspose
- barcode
- pdf417
title: Генерация штрихкода Aspose – полное руководство по C#
url: /ru/net/compact-pdf417-encoding/generate-barcode-aspose-complete-c-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Генерация штрихкода Aspose – полное руководство на C#

Если вам нужно **generate barcode aspose** для символа MacroPdf417, это руководство проведет вас через весь процесс. Вы увидите, как настроить макроспецифические параметры, встроить пользовательский текст и сохранить штрихкод как PNG‑изображение.

Создание штрихкода с помощью Aspose.BarCode исключает необходимость ручных вычислений и гарантирует соответствие спецификации PDF417. В последующих шагах вы также узнаете **how to generate pdf417** с пользовательскими метаданными, такими как идентификатор файла, количество сегментов и метки времени. К концу руководства у вас будет готовый пример кода, который можно вставить в любой проект .NET.

## Требования

* .NET 6.0 или новее (код также работает с .NET Framework 4.7+)
* Действительная лицензия Aspose.BarCode for .NET (бесплатная оценочная версия подходит для тестирования)
* Visual Studio 2022 или любой предпочитаемый вами IDE для C#
* Базовое знакомство с синтаксисом C# и объектно‑ориентированными концепциями

Дополнительные пакеты NuGet не требуются, кроме **Aspose.BarCode**.

## Шаг 1: Установите пакет NuGet Aspose.BarCode

Откройте ваш проект в Visual Studio, затем выполните следующую команду в консоли диспетчера пакетов:

```powershell
Install-Package Aspose.BarCode
```

Пакет добавляет пространство имён `Aspose.BarCode`, которое содержит класс `BarcodeGenerator`, используемый на протяжении всего руководства.

## Шаг 2: Создайте генератор штрихкода для MacroPdf417

Первая строка создаёт экземпляр `BarcodeGenerator`, который нацелен на символику **MacroPdf417** и встраивает пользовательский текст, который вы хотите закодировать.

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;
using System;

// Step 2: Initialize the generator with custom text
using (BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
           EncodeTypes.MacroPdf417, "Åspóse.Barcóde©"))
{
    // The rest of the configuration goes here
}
```

*Почему это важно*: Перечисление `EncodeTypes.MacroPdf417` указывает Aspose рассматривать штрихкод как макро‑включённый символ PDF417, который поддерживает разбивку больших данных на несколько сегментов. Строка `"Åspóse.Barcóde©"` демонстрирует, что генератор корректно обрабатывает символы Unicode.

## Шаг 3: Определите базовый размер модуля

Размер модуля управляет визуальной плотностью штрихкода. Значение в `2` пикселя даёт чёткое изображение, которое хорошо печатается на стандартных принтерах этикеток.

```csharp
    // Step 3: Set the X‑dimension (module width) in pixels
    barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

Увеличение значения делает штрихкод больше, а уменьшение может вызвать проблемы сканирования на устройствах с низким разрешением.

## Шаг 4: Настройте параметры макро‑специфической раскладки PDF417

MacroPdf417 требует нескольких дополнительных параметров. Эти настройки позволяют разбить данные на несколько файлов, идентифицировать каждый сегмент и проверять целостность.

```csharp
    // Step 4: Macro‑specific layout
    barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 5;                     // Number of columns per row
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;    // Unique file identifier
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;       // Current segment number
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20; // Total number of segments
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";
```

*Почему это важно*: Свойство `Columns` влияет на ширину штрихкода, а макрополя (`FileID`, `SegmentID`, `SegmentsCount`, `FileName`) позволяют системам downstream правильно собрать исходные данные.

## Шаг 5: Добавьте дополнительные макрометаданные

Aspose.BarCode позволяет встраивать необязательные макрополя, такие как контрольная сумма, размер файла, метка времени и информация об отправителе/получателе. Эти поля полезны для аудита и обнаружения ошибок.

```csharp
    // Step 5: Optional macro metadata
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234;                 // CCITT‑16 example
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000;              // Approximate size in bytes
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = 
        new DateTime(2019, 11, 1);                                                       // Creation date
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = 
        Pdf417MacroTerminator.Set;                                                       // Marks the last segment
```

*Почему это важно*: Контрольная сумма защищает от ошибок передачи, а метка времени и поля отправителя предоставляют контекст для последующей обработки. Установка `MacroPdf417Terminator` в `Set` сигнализирует, что это последний сегмент в серии макросов.

## Шаг 6: Сохраните штрихкод как PNG‑изображение

Наконец, запишите сгенерированный штрихкод на диск. PNG сохраняет без потерь качество, что идеально для сканирования.

```csharp
    // Step 6: Export the barcode
    string outputPath = Path.Combine(Environment.CurrentDirectory, "ExtPDF417Meta.png");
    barcodeGenerator.Save(outputPath, BarCodeImageFormat.Png);
}
```

Когда код завершится, файл `ExtPDF417Meta.png` будет содержать высоко‑разрешённый штрихкод MacroPdf417, который кодирует пользовательский текст и все макрометаданные.

### Ожидаемый результат

Открытие `ExtPDF417Meta.png` показывает вертикально ориентированный штрихкод с чётко определёнными строками и столбцами. Сканирование изображения любым считывателем PDF417 возвращает исходную строку **Åspóse.Barcóde©** и макрополя, которые вы настроили (идентификатор файла, идентификатор сегмента, контрольная сумма и т.д.).

## Как сгенерировать pdf417 без макро‑опций (альтернативный сценарий)

Если вам нужен только стандартный штрихкод PDF417, опустите макросвойства и оставьте базовую конфигурацию:

```csharp
using (BarcodeGenerator generator = new BarcodeGenerator(
           EncodeTypes.Pdf417, "Standard PDF417 data"))
{
    generator.Parameters.Barcode.XDimension.Pixels = 3;
    generator.Parameters.Barcode.Pdf417.Columns = 6;
    generator.Save("StandardPdf417.png", BarCodeImageFormat.Png);
}
```

Этот фрагмент демонстрирует **how to generate pdf417** быстро, когда макрофункциональность не требуется.

## Распространённые ошибки и профессиональные советы

| Проблема | Почему это происходит | Решение |
|----------|-----------------------|---------|
| Штрихкод слишком мал для сканирования | X‑dimension установлен в 1 пиксель или количество столбцов слишком велико | Используйте как минимум `2` пикселя для `XDimension` и держите количество столбцов между `3` и `9` для типичных размеров этикеток |
| Unicode‑символы отображаются как � | Несоответствие кодировки в файле проекта | Убедитесь, что файл проекта сохранён как UTF‑8 и исходный файл содержит правильный BOM |
| Макрополя игнорируются сканером | `MacroPdf417Terminator` не установлен для последнего сегмента | Установите `MacroPdf417Terminator = Pdf417MacroTerminator.Set` на последнем сегменте |
| Файл изображения повреждён | Поток вывода не закрыт корректно | Используйте оператор `using` (как показано), чтобы гарантировать освобождение генератора |

## Полный, исполняемый пример

Скопируйте следующий код в новое консольное приложение и запустите его. Программа создаёт штрихкод, сохраняет его и выводит путь к файлу в консоль.

```csharp
using System;
using System.IO;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace AsposeBarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // Initialize the generator with custom Unicode text
            using (BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
                       EncodeTypes.MacroPdf417, "Åspóse.Barcóde©"))
            {
                // Basic size
                barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;

                // Macro layout
                barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 5;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";

                // Optional macro metadata
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2019, 11, 1);
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;

                // Save as PNG
                string outputFile = Path.Combine(Environment.CurrentDirectory, "ExtPDF417Meta.png");
                barcodeGenerator.Save(outputFile, BarCodeImageFormat.Png);

                Console.WriteLine($"Barcode saved to: {outputFile}");
            }
        }
    }
}
```

Запуск программы выводит строку, похожую на:

```
Barcode saved to: C:\YourProject\bin\Debug\net6.0\ExtPDF417Meta.png
```

Откройте файл, чтобы проверить визуальный результат.

## Заключение

Теперь вы знаете, как **generate barcode aspose** для символьной системы MacroPdf417, встраивать пользовательский Unicode‑текст, настраивать макрометаданные и экспортировать результат как PNG‑изображение. Та же схема позволяет **how to generate pdf417** без макро‑опций, и вы можете адаптировать код для других форматов штрихкодов, поддерживаемых Aspose.BarCode.

Далее изучайте связанные темы, такие как **create barcode custom text** для QR‑кодов, добавление цветовых фильтров с параметрами `Color` или встраивание штрихкодов непосредственно в PDF‑документы с помощью Aspose.PDF. Экспериментируйте с различными значениями `XDimension` и количеством столбцов, чтобы точно настроить штрихкод под ваш конкретный принтер или сканер.

Удачной разработки и наслаждайтесь надёжностью, которую Aspose.BarCode приносит в ваши .NET решения для штрихкодов!

## Что стоит изучить дальше?

Следующие руководства охватывают тесно связанные темы, которые развивают техники, продемонстрированные в этом руководстве. Каждый ресурс включает полные рабочие примеры кода с пошаговыми объяснениями, чтобы помочь вам освоить дополнительные возможности API и исследовать альтернативные подходы к реализации в ваших проектах.

- [How to Create Barcode – Compact PDF417 with Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [How to generate DataMatrix barcode with Aspose.BarCode for .NET](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-macro-configuration/)
- [Generate Barcode Java - Set Code Text using Aspose.BarCode](/barcode/english/java/text-and-styling/setting-code-text/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}