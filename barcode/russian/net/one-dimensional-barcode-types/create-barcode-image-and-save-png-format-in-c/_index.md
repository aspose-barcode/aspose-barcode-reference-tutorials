---
category: general
date: 2026-11-27
description: Создание изображения штрих‑кода в C# и сохранение его в формате PNG с
  помощью Aspose.BarCode – пошаговое руководство.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode image
- save image PNG format
- Aspose.BarCode C#
- Macro PDF417 barcode
- barcode generation .NET
language: ru
lastmod: 2026-11-27
og_description: Создайте изображение штрихкода на C# и сохраните его в формате PNG
  с помощью Aspose.BarCode. Следуйте этому руководству, чтобы пошагово сгенерировать
  штрихкод Macro PDF417.
og_image_alt: Screenshot of a created barcode image saved as PNG
og_title: Создание изображения штрих‑кода и сохранение в формате PNG на C# – полное
  руководство
schemas:
- author: Aspose
  dateModified: '2026-11-27'
  description: Create barcode image in C# and save image PNG format with Aspose.BarCode
    – step‑by‑step guide.
  headline: Create barcode image and save PNG format in C#
  type: TechArticle
tags:
- barcode
- C#
- Aspose
title: Создать изображение штрих‑кода и сохранить в формате PNG в C#
url: /ru/net/one-dimensional-barcode-types/create-barcode-image-and-save-png-format-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Создать изображение штрихкода и сохранить в формате PNG в C#

Если вам нужно **создать изображение штрихкода** в .NET‑приложении, это руководство покажет, как сгенерировать Macro PDF417 штрихкод и **сохранить изображение в формате PNG** с помощью Aspose.BarCode. Вы получите полностью готовый пример и объяснение каждой настройки, чтобы вы могли адаптировать код под свои требования.

Генерация штрихкода — это больше, чем вызов одной функции; необходимо настроить размер модуля, параметры macro и формат вывода. К концу этого руководства вы поймёте, почему важна каждая свойство, как обрабатывать распространённые граничные случаи и как проверить, что PNG‑файл записан корректно.

## Что понадобится

- .NET 6.0 или новее (код также работает с .NET Framework 4.6+)
- Aspose.BarCode for .NET (доступно через NuGet: `Install-Package Aspose.BarCode`)
- IDE, например Visual Studio 2022 или Visual Studio Code
- Права записи в папку, где будет сохранён PNG‑файл

## Шаг 1: Инициализировать генератор штрихкода

Первый шаг — создать экземпляр `BarcodeGenerator`, указав симбологию `EncodeTypes.MacroPdf417` и текст, который нужно закодировать.

```csharp
using Aspose.BarCode.Generation;

// Step 1: Initialize a Macro PDF417 barcode generator with the desired text
using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MacroPdf417, "Sample text"))
{
    // Subsequent steps go here
}
```

**Почему это важно:**  
`EncodeTypes.MacroPdf417` сообщает библиотеке использовать вариант PDF417 macro, который поддерживает сегментацию файла и дополнительные метаданные. Конструктор также принимает человекочитаемый текст, который будет закодирован в штрихкоде.

## Шаг 2: Определить размер модуля (X‑dimension)

X‑dimension управляет шириной отдельного модуля штрихкода (самого маленького чёрно‑белого элемента). Значение `2` пикселя хорошо подходит для PNG‑изображений, отображаемых на экране.

```csharp
    // Step 2: Define the module size (X‑dimension) in pixels
    generator.Parameters.Barcode.XDimension.Pixels = 2;
```

**Практический совет:**  
Если планируете печатать штрихкод, увеличьте значение пикселей (например, `4` или `5`), чтобы избежать размытия на принтерах с низким разрешением.

## Шаг 3: Настроить параметры PDF417 macro

Macro PDF417 добавляет несколько необязательных полей, помогающих идентифицировать исходный файл, порядок сегментов и проверку целостности. Ниже приведён полный набор типовых параметров; вы можете опустить любые, которые не нужны.

```csharp
    // Step 3: Set PDF417 macro parameters
    generator.Parameters.Barcode.Pdf417.Columns = 5;                     // Number of columns per row
    generator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;    // Unique file identifier
    generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;      // Current segment number
    generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20; // Total number of segments
    generator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01"; // Logical file name
    generator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234;     // CCITT‑16 checksum
    generator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000;  // Approximate file size in bytes
    generator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2019, 11, 1);
    generator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
    generator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
    generator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;
```

**Почему эти поля полезны:**  

| Параметр | Назначение |
|-----------|------------|
| `Columns` | Управляет шириной штрихкода; меньше колонок — более высокий штрихкод. |
| `MacroPdf417FileID` | Уникальный идентификатор, связывающий все сегменты вместе. |
| `MacroPdf417SegmentID` | Позиция данного сегмента в полном файле. |
| `MacroPdf417SegmentsCount` | Общее количество сегментов; требуется для восстановления. |
| `MacroPdf417FileName` | Человекочитаемое имя, которое может отображаться в приложениях‑сканерах. |
| `MacroPdf417Checksum` | Помогает получателям проверять целостность данных (CCITT‑16). |
| `MacroPdf417FileSize` | Необязательная подсказка о размере оригинального файла. |
| `MacroPdf417TimeStamp` | Временная метка создания оригинального файла. |
| `MacroPdf417Addressee` / `MacroPdf417Sender` | Метаданные для маршрутизации или владения. |
| `MacroPdf417Terminator` | Указывает, является ли это последним сегментом (`Set`) или промежуточным (`Unset`). |

**Граничный случай:** Если вы генерируете одно‑сегментный штрихкод, установите `MacroPdf417SegmentsCount` в `1` и `MacroPdf417Terminator` в `Unset`. Библиотека автоматически опустит поля, связанные с сегментами, если они не применимы.

## Шаг 4: Сохранить сгенерированный штрихкод как PNG‑изображение

Наконец, вызовите `Save`, указав путь к файлу и значение перечисления `BarCodeImageFormat.Png`. Метод записывает изображение на диск в без‑потерь формате PNG.

```csharp
    // Step 4: Save the generated barcode as a PNG image
    string outputPath = Path.Combine(Environment.CurrentDirectory, "ExtPDF417Meta.png");
    generator.Save(outputPath, BarCodeImageFormat.Png);
}
```

**Почему PNG?**  
PNG сохраняет точные значения пикселей, что критично для сканеров штрихкодов, полагающихся на резкий контраст. Сжатие JPEG может ввести артефакты, нарушающие шаблон штрихкода.

### Проверка вывода

После выполнения программы вы должны увидеть файл с именем `ExtPDF417Meta.png` в папке выполнения. Открыв его в любом просмотрщике изображений, вы увидите плотный прямоугольный штрихкод. Правильность можно проверить, отсканировав изображение мобильным сканером, поддерживающим PDF417 macro; приложение обычно покажет встроенные метаданные (ID файла, номер сегмента и т.д.).

## Распространённые ошибки и как их избежать

| Симптом | Вероятная причина | Решение |
|----------|-------------------|----------|
| Штрихкод выглядит размытым | X‑dimension слишком низкое для выбранного DPI | Увеличьте `XDimension.Pixels` или рендерите с более высоким DPI (`generator.Parameters.ImageResolution`). |
| Сканер сообщает «checksum error» | Неправильное значение `MacroPdf417Checksum` | Позвольте Aspose вычислить контрольную сумму автоматически, опустив свойство, либо убедитесь, что значение соответствует алгоритму CCITT‑16. |
| PNG‑файл пустой или не создан | Неверный путь вывода или отсутствие прав записи | Используйте `Path.Combine` с известной записываемой папкой (например, `Environment.GetFolderPath(Environment.SpecialFolder.Desktop)`). |
| Поля macro игнорируются | `EncodeTypes` установлен в обычный `Pdf417` вместо `MacroPdf417` | Проверьте, что в конструкторе используется `EncodeTypes.MacroPdf417`. |

## Полный, исполняемый пример

Ниже приведена полная программа, которую можно скопировать в консольное приложение. Она компилируется с .NET 6.0 и создаёт описанный выше PNG‑файл.

```csharp
using System;
using System.IO;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Initialize a Macro PDF417 barcode generator with the desired text
        using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MacroPdf417, "Sample text"))
        {
            // Define the module size (X-dimension) in pixels
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // Set PDF417 macro parameters
            generator.Parameters.Barcode.Pdf417.Columns = 5;
            generator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
            generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;
            generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;
            generator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";
            generator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234; // CCITT‑16 checksum
            generator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000;
            generator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2019, 11, 1);
            generator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
            generator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
            generator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;

            // Save the generated barcode as a PNG image
            string outputPath = Path.Combine(Environment.CurrentDirectory, "ExtPDF417Meta.png");
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"Barcode image saved to: {outputPath}");
        }
    }
}
```

**Ожидаемый вывод (консоль):**

```
Barcode image saved to: C:\YourProject\bin\Debug\net6.0\ExtPDF417Meta.png
```

Открытие `ExtPDF417Meta.png` показывает чёткий Macro PDF417 штрихкод, готовый к сканированию.

## Следующие шаги

- **Изменить формат изображения** – замените `BarCodeImageFormat.Png` на `Jpeg` или `Bmp`, если нужен другой тип файла. Помните, что JPEG вводит артефакты сжатия, что может повлиять на надёжность сканирования.
- **Настроить разрешение** – использовать

## Что вам стоит изучить дальше?

Следующие руководства охватывают тесно связанные темы, построенные на техниках, продемонстрированных в этом руководстве. Каждый ресурс включает полные рабочие примеры кода с пошаговыми объяснениями, чтобы помочь вам освоить дополнительные возможности API и исследовать альтернативные подходы к реализации в собственных проектах.

- [Как создать изображение штрихкода с помощью Aspose.Barcode в C#](/barcode/english/python-java/general/how-to-create-barcode-image-with-aspose-barcode-in-c/)
- [Как создать изображение PDF417 штрихкода в C# с параметрами Macro PDF417](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-image-in-c-with-macro-pdf417-op/)
- [Как считывать штрихкоды с изображения с помощью C# и Aspose.BarCode – пошаговое руководство](/barcode/english/net/one-dimensional-barcode-types/how-to-read-barcodes-from-image-using-c-step-by-step-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}