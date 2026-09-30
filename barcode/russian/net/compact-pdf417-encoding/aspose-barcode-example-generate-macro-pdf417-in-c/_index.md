---
category: general
date: 2026-08-09
description: Пример Aspose Barcode, показывающий, как с помощью генератора штрихкодов
  на C# создать Macro PDF417 с полной поддержкой метаданных.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- aspose barcode example
- barcode generator c#
language: ru
lastmod: 2026-08-09
og_description: Пример штрихкода Aspose демонстрирует использование генератора штрихкодов
  C# для создания штрихкода Macro PDF417, который включает идентификатор файла, данные
  сегмента, метку времени и другие метаданные.
og_image_alt: Screenshot of a Macro PDF417 barcode generated with Aspose.BarCode in
  C#
og_title: Пример штрихкода Aspose – создание Macro PDF417 с помощью C#
schemas:
- author: Aspose
  dateModified: '2026-08-09'
  description: Aspose barcode example showing how to use a barcode generator C# to
    create a Macro PDF417 with full metadata support.
  headline: 'Aspose barcode example: generate Macro PDF417 in C#'
  type: TechArticle
tags:
- Aspose.BarCode
- C#
- Macro PDF417
title: 'Пример штрихкода Aspose: генерация Macro PDF417 на C#'
url: /ru/net/compact-pdf417-encoding/aspose-barcode-example-generate-macro-pdf417-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Пример Aspose barcode: генерация Macro PDF417 на C#

Если вам нужен **aspose barcode example**, который создает штрих‑код Macro PDF417, это руководство покажет, как сделать это с помощью **barcode generator C#**. Вы увидите все необходимые настройки, от базовых размеров до полного набора полей метаданных Macro PDF417, и получите PNG‑изображение, готовое для последующей обработки.

В руководстве описан полный рабочий процесс, объясняется, почему каждый параметр важен, и предоставляется готовый к запуску пример кода. Внешние ссылки не требуются; вы можете скопировать код, скорректировать значения и сразу запустить его.

## Требования

- .NET 6.0 (или новее) установлен  
- Visual Studio 2022 или любая IDE, совместимая с C#  
- Действительная лицензия на **Aspose.BarCode for .NET** (бесплатная пробная версия подходит для этого примера)  

Add the Aspose.BarCode NuGet package to your project:

```bash
dotnet add package Aspose.BarCode
```

## Шаг 1: Создание экземпляра barcode generator C#  

Первый шаг — создать экземпляр `BarcodeGenerator`, передав значение перечисления `EncodeTypes.MacroPdf417` и текст, который необходимо закодировать. Текст может содержать символы Unicode, которые библиотека обрабатывает автоматически.

```csharp
using Aspose.BarCode.Generation;
using System;

using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MacroPdf417, "Åspóse.Barcóde©"))
{
    // Subsequent steps are performed inside this using block.
```

*Почему это важно*: `EncodeTypes.MacroPdf417` указывает движку генерировать символ Macro PDF417, который поддерживает сегментированные данные и дополнительные метаданные уровня файла. Оператор `using` гарантирует освобождение неуправляемых ресурсов после сохранения изображения.

## Шаг 2: Определение базового внешнего вида штрих‑кода  

Штрих‑код Macro PDF417 состоит из квадратных модулей. Управление размером модуля и количеством колонок влияет как на читаемость, так и на размер файла.

```csharp
    // Pixel size of a single module (X dimension)
    generator.Parameters.Barcode.XDimension.Pixels = 2;

    // Number of columns in the symbol; fewer columns produce a taller barcode
    generator.Parameters.Barcode.Pdf417.Columns = 5;
```

*Почему это важно*: `XDimension.Pixels` определяет визуальную плотность; значение 2 пикселя хорошо подходит для отображения на экране при небольшом размере изображения. Настройте количество колонок в соответствии с ограничениями макета — больше колонок создают более широкий и короткий штрих‑код.

## Шаг 3: Установка специфических метаданных Macro PDF417  

Macro PDF417 расширяет стандартный формат PDF417 полями, позволяющими восстанавливать большие файлы из нескольких сегментов штрих‑кода. Каждое поле необязательно, но их установка демонстрирует полные возможности API.

```csharp
    // Unique identifier for the entire file
    generator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;

    // Identifier of the current segment (zero‑based)
    generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;

    // Total number of segments that compose the file
    generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;

    // Logical name of the source file
    generator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";

    // 16‑bit CCITT checksum for error detection
    generator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234;

    // Approximate size of the original file in bytes
    generator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400000;

    // Timestamp when the file was generated
    generator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2019, 11, 1);

    // Optional address fields for routing information
    generator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
    generator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";

    // Terminator indicates that this is the last segment
    generator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;
```

*Почему это важно*:  
- `MacroPdf417FileID` связывает все сегменты, принадлежащие одному логическому файлу.  
- `MacroPdf417SegmentID` и `MacroPdf417SegmentsCount` позволяют декодеру правильно упорядочить фрагменты.  
- `MacroPdf417Checksum` обеспечивает быструю проверку целостности без декодирования всей полезной нагрузки.  
- `MacroPdf417FileSize` и `MacroPdf417TimeStamp` позволяют системам downstream проверять, что восстановленный файл соответствует оригиналу.  
- `MacroPdf417Addressee` / `MacroPdf417Sender` полезны в сценариях логистики или обмена документами.  
- Установка `MacroPdf417Terminator` в `Set` помечает этот штрих‑код как последний сегмент, что упрощает алгоритм восстановления.

## Шаг 4: Сохранение сгенерированного изображения штрих‑кода  

Наконец, запишите штрих‑код в файл PNG. Вы можете выбрать любой поддерживаемый формат (`Png`, `Jpeg`, `Bmp`, `Gif`, `Tiff`).

```csharp
    // Save the barcode image to the specified path
    generator.Save("YOUR_DIRECTORY/ExtPDF417Meta.png", BarCodeImageFormat.Png);
}
```

*Почему это важно*: PNG сохраняет пиксельные данные без потерь, гарантируя, что сканеры считывают точно такой же шаблон модулей, который вы настроили. Изменение формата может повлиять на визуальное качество и размер файла.

### Ожидаемый результат

Запуск полной программы создаёт файл с именем **ExtPDF417Meta.png**. При открытии изображения отображается прямоугольный штрих‑код Macro PDF417 с закодированным текстом «Åspóse.Barcóde©», а визуальная плотность соответствует установленному 2‑пиксельному X‑размеру. Сканирование изображения с помощью считывателя, совместимого с PDF417, возвращает все поля метаданных, определённые в Шаге 3.

## Полный рабочий пример  

Скопируйте код ниже в новый консольный проект (`dotnet new console`) и замените `YOUR_DIRECTORY` на абсолютный или относительный путь, существующий на вашем компьютере.

```csharp
using Aspose.BarCode.Generation;
using System;

namespace MacroPdf417Demo
{
    class Program
    {
        static void Main()
        {
            // Step 1: Create a barcode generator for Macro PDF417 with the desired text
            using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MacroPdf417, "Åspóse.Barcóde©"))
            {
                // Step 2: Define the basic barcode appearance
                generator.Parameters.Barcode.XDimension.Pixels = 2;          // pixel size of a single module
                generator.Parameters.Barcode.Pdf417.Columns = 5;           // number of columns in the symbol

                // Step 3: Set Macro PDF417 specific metadata
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
                generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;
                generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";
                generator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234; // CCITT‑16 example
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400000;
                generator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2019, 11, 1);
                generator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
                generator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
                generator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;

                // Step 4: Save the generated barcode image
                generator.Save("YOUR_DIRECTORY/ExtPDF417Meta.png", BarCodeImageFormat.Png);
            }

            Console.WriteLine("Macro PDF417 barcode generated successfully.");
        }
    }
}
```

Запустите программу (`dotnet run`). После выполнения проверьте, что файл PNG появился в указанном месте. Используйте любое приложение для чтения штрих‑кодов, поддерживающее Macro PDF417, чтобы убедиться, что метаданные правильно внедрены.

## Распространённые варианты и граничные случаи  

- **Разные форматы изображений**: замените `BarCodeImageFormat.Png` на `Jpeg`, `Bmp` или `Tiff`, если ваша downstream‑система предпочитает другой формат.  
- **Изменение размера модуля**: большие значения `XDimension.Pixels` повышают надёжность сканирования на сканерах с низким разрешением, но увеличивают размер изображения.  
- **Несколько сегментов**: для создания многосегментного файла генерируйте серию штрих‑кодов, увеличивая `MacroPdf417SegmentID` для каждого, и оставляйте `MacroPdf417FileID` постоянным. Только последний сегмент должен иметь установленный `MacroPdf417Terminator`.  
- **Поддержка Unicode**: генератор автоматически кодирует символы Unicode; убедитесь, что ваша исходная строка использует кодировку UTF‑8, если вы читаете её из внешнего файла.  
- **Обработка ошибок**: оберните блок `using` в try‑catch, чтобы перехватывать `BarCodeException` при недопустимых параметрах (например, количество колонок вне диапазона).

## Профессиональные советы  

- **Производительность**: переиспользуйте один экземпляр `BarcodeGenerator` при создании множества штрих‑кодов с одинаковыми настройками; меняйте только свойство `CodeText` между сохранениями.  
- **Оценка размера файла**: поле `MacroPdf417FileSize` должно соответствовать количеству байт оригинальной полезной нагрузки; несоответствия могут привести к ошибкам проверки downstream‑систем.  
- **Тестирование**: проверяйте сгенерированные штрих‑коды как встроенным декодером Aspose (`BarCodeReader`), так и сторонним сканером, чтобы обеспечить совместимость.

## Заключение  

Этот **aspose barcode example

## Что вам следует изучить дальше?

Следующие руководства охватывают тесно связанные темы, которые опираются на техники, продемонстрированные в этом руководстве. Каждый ресурс включает полностью работающие примеры кода с пошаговыми объяснениями, чтобы помочь вам освоить дополнительные возможности API и исследовать альтернативные подходы к реализации в ваших проектах.

- [Как создать штрих‑код – Compact PDF417 с Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [Как создать тихую зону штрих‑кода для Code 16K с использованием Aspose.BarCode for .NET](/barcode/english/net/code-16k-encoding/code-16k-quiet-zone-settings/)
- [Как создать тихую зону штрих‑кода для ITF-14 с использованием Aspose.BarCode for .NET](/barcode/english/net/itf-14-barcode-customization/itf-14-barcode-quiet-zone-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}