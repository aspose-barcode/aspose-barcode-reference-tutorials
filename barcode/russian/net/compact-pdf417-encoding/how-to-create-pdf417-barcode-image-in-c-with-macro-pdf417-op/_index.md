---
category: general
date: 2026-09-13
description: Узнайте, как создать изображение штрих‑кода PDF417 на C# с помощью BarcodeGenerator
  и опций Macro PDF417. Пошаговый код, советы и полный пример.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create PDF417 barcode image
- macro PDF417 options
- BarcodeGenerator class
- C# barcode generation
- barcode image format
language: ru
lastmod: 2026-09-13
og_description: Создайте изображение штрихкода PDF417 на C# с помощью BarcodeGenerator.
  Следуйте этому подробному руководству, чтобы настроить параметры Macro PDF417 и
  сохранить штрихкод в формате PNG.
og_image_alt: Screenshot of a generated PDF417 barcode image created with C# code
og_title: Создание изображения штрихкода PDF417 в C# — полное руководство
schemas:
- author: Aspose
  dateModified: '2026-09-13'
  description: Learn how to create PDF417 barcode image in C# using BarcodeGenerator
    and Macro PDF417 options. Step‑by‑step code, tips, and full example.
  headline: How to create PDF417 barcode image in C# with Macro PDF417 options
  type: TechArticle
- description: Learn how to create PDF417 barcode image in C# using BarcodeGenerator
    and Macro PDF417 options. Step‑by‑step code, tips, and full example.
  name: How to create PDF417 barcode image in C# with Macro PDF417 options
  steps:
  - name: '**Create the generator** – instantiate `BarcodeGenerator` with `EncodeTypes.MacroPdf417`
      and the data you want to encode.'
    text: '**Create the generator** – instantiate `BarcodeGenerator` with `EncodeTypes.MacroPdf417`
      and the data you want to encode.'
  - name: '**Define the module size** – set `XDimension.Pixels` to control the physical
      width of each barcode element.'
    text: '**Define the module size** – set `XDimension.Pixels` to control the physical
      width of each barcode element.'
  - name: '**Configure Macro PDF417 options** – specify columns, file identifiers,
      segment numbers, and optional checksum.'
    text: '**Configure Macro PDF417 options** – specify columns, file identifiers,
      segment numbers, and optional checksum.'
  - name: '**Save the barcode** – write the generated image to disk using a supported
      **barcode image format** such as PNG.'
    text: '**Save the barcode** – write the generated image to disk using a supported
      **barcode image format** such as PNG.'
  - name: Create a new .NET 6 (or later) console project.
    text: Create a new .NET 6 (or later) console project.
  - name: Add the Aspose.BarCode NuGet package (`dotnet add package Aspose.BarCode`).
    text: Add the Aspose.BarCode NuGet package (`dotnet add package Aspose.BarCode`).
  - name: Replace the generated `Program.cs` with the code above.
    text: Replace the generated `Program.cs` with the code above.
  - name: Adjust `outputPath` to a folder you have write access to.
    text: Adjust `outputPath` to a folder you have write access to.
  - name: Build and run – the console will confirm the image location.
    text: Build and run – the console will confirm the image location.
  type: HowTo
tags:
- PDF417
- C#
- Barcode
title: Как создать изображение штрихкода PDF417 в C# с опциями Macro PDF417
url: /ru/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-image-in-c-with-macro-pdf417-op/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Как создать изображение штрихкода PDF417 в C# с параметрами Macro PDF417

Если вам нужно **создать изображение штрихкода PDF417** в C#, это руководство покажет вам точно, как это сделать с использованием **класса BarcodeGenerator**. Независимо от того, создаёте ли вы систему отслеживания документов или кодируете большие файлы, пошаговые инструкции ниже охватывают всё — от настройки параметров Macro PDF417 до сохранения конечного PNG.

Создание штрихкода становится простым, как только вы понимаете ключевые параметры. В этом учебнике вы узнаете, как:

* Инициализировать `BarcodeGenerator` для **Macro PDF417**.  
* Отрегулировать размер модуля штрихкода (`XDimension`).  
* Настроить параметры, специфичные для сегмента, такие как идентификатор файла, идентификатор сегмента и контрольная сумма.  
* Сохранить результат в **формате изображения штрихкода** (PNG), который можно отобразить в любом интерфейсе.

Единственное требование — наличие среды разработки .NET (Visual Studio 2022 или новее) и пакета NuGet Aspose.BarCode for .NET, который предоставляет API `BarcodeGenerator`, используемое в примерах.

---

## Как создать изображение штрихкода PDF417 в C# — обзор

Создание изображения штрихкода PDF417 состоит из четырёх логических шагов:

1. **Создать генератор** — создать экземпляр `BarcodeGenerator` с `EncodeTypes.MacroPdf417` и данными, которые нужно закодировать.  
2. **Определить размер модуля** — установить `XDimension.Pixels`, чтобы контролировать физическую ширину каждого элемента штрихкода.  
3. **Настроить параметры Macro PDF417** — указать количество столбцов, идентификаторы файлов, номера сегментов и необязательную контрольную сумму.  
4. **Сохранить штрихкод** — записать сгенерированное изображение на диск, используя поддерживаемый **формат изображения штрихкода**, например PNG.

Каждый шаг подробно объяснён ниже, с полным, исполняемым кодом C#.

---

## Шаг 1: Инициализировать BarcodeGenerator для Macro PDF417

Первая строка создаёт объект `BarcodeGenerator`, который знает, что должен генерировать **Macro PDF417** штрихкод. Конструктор принимает два аргумента: тип кодирования и строку исходных данных.

```csharp
using Aspose.BarCode.Generation;   // NuGet: Aspose.BarCode
using System.Drawing.Imaging;      // For ImageFormat if you prefer System.Drawing

// Step 1 – create a barcode generator for Macro PDF417
using (var barcodeGenerator = new BarcodeGenerator(EncodeTypes.MacroPdf417, "Sample data"))
{
    // Subsequent configuration goes here
}
```

**Почему это важно:**  
`EncodeTypes.MacroPdf417` сообщает библиотеке рассматривать штрихкод как контейнер с несколькими сегментами, что необходимо, когда нужно разбить большой файл на несколько символов. Экземпляр `BarcodeGenerator` реализует `IDisposable`, поэтому блок `using` гарантирует освобождение всех неуправляемых ресурсов после сохранения изображения.

---

## Шаг 2: Установить размер модуля штрихкода (XDimension)

`XDimension` контролирует ширину в пикселях одного модуля штрихкода (самой маленькой чёрной или белой полосы). Значение **2 пикселя** даёт компактное, но читаемое изображение.

```csharp
    // Step 2 – define the size of each barcode module (pixel width)
    barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

**Практический совет:**  
Если ваш целевой принтер имеет низкое DPI, увеличьте количество пикселей (например, `3` или `4`), чтобы избежать размазывания. Для отображения на экране можно оставить значение небольшим, чтобы уменьшить размер файла.

---

## Шаг 3: Настроить параметры Macro PDF417

Macro PDF417 добавляет метаданные, позволяющие сканеру восстановить оригинальный файл из нескольких сегментов штрихкода. Наиболее часто используемые параметры:

| Property | Meaning |
|----------|---------|
| `Columns` | Количество столбцов в каждом символе (влияет на ширину). |
| `MacroPdf417FileID` | Уникальный идентификатор всего файла. |
| `MacroPdf417SegmentID` | Индекс текущего сегмента (начинается с 1). |
| `MacroPdf417SegmentsCount` | Общее количество сегментов, составляющих файл. |
| `MacroPdf417FileName` | Исходное имя файла (необязательно, для отображения). |
| `MacroPdf417Checksum` | Необязательная 16‑битная контрольная сумма для проверки целостности. |

```csharp
    // Step 3 – configure Macro PDF417 specific options
    barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 5;                     // Number of columns in the symbol
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;    // Unique file identifier
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 1;       // Current segment number
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 10; // Total number of segments
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "report.pdf"; // Original file name
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 0x1A2B;    // Optional checksum
```

**Почему эти настройки важны:**  
- **Columns** влияют на читаемость и общие размеры изображения.  
- **FileID** должен быть одинаковым во всех сегментах, чтобы декодер понял, что они принадлежат к одному файлу.  
- **SegmentID** и **SegmentsCount** позволяют сканеру правильно упорядочить части.  
- **FileName** и **Checksum** необязательны, но улучшают пользовательский опыт и целостность данных.

**Пограничный случай:** Если вы генерируете более 999 сегментов, поле `SegmentID` переполняется; в этом случае разбейте данные на несколько файлов.

---

## Шаг 4: Сохранить сгенерированный штрихкод в виде PNG‑изображения

Последний шаг записывает штрихкод на диск. `BarCodeImageFormat.Png` создаёт без потерь изображение, которое работает в вебе, на настольных и мобильных платформах.

```csharp
    // Step 4 – save the generated barcode as a PNG image
    barcodeGenerator.Save("YOUR_DIRECTORY/MacroPdf417.png", BarCodeImageFormat.Png);
}
```

**Альтернативные форматы:**  
Вы можете заменить `BarCodeImageFormat.Png` на `Jpeg`, `Bmp` или `Gif`, если ваша downstream‑система требует определённый формат. Учтите, что JPEG вводит артефакты сжатия, которые могут снизить надёжность сканирования.

**Ожидаемый результат:**  
Файл `MacroPdf417.png` будет содержать контрастный, многосегментный штрихкод PDF417. При открытии он должен выглядеть аналогично иллюстрации ниже.

![Пример создания изображения штрихкода PDF417](image.png){: .align-center alt="Пример создания изображения штрихкода PDF417, сгенерированный кодом C#"}

---

## Полный исходный код — готов к копированию и запуску

Ниже представлена полная, автономная программа. В ней включены необходимые директивы `using`, метод `Main` и комментарии, объясняющие каждую неочевидную строку.

```csharp
using System;
using Aspose.BarCode.Generation;   // Install-Package Aspose.BarCode
// No other external dependencies are required.

namespace Pdf417BarcodeDemo
{
    class Program
    {
        static void Main(string[] args)
        {
            // Data to encode – can be any UTF‑8 string up to 1,800 characters.
            const string dataToEncode = "Sample data";

            // Output directory – change this to a valid path on your machine.
            const string outputPath = @"C:\Barcodes\MacroPdf417.png";

            // Create a BarcodeGenerator for Macro PDF417.
            using (var barcodeGenerator = new BarcodeGenerator(EncodeTypes.MacroPdf417, dataToEncode))
            {
                // 1️⃣ Define module size (pixel width of each bar).
                barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;

                // 2️⃣ Configure Macro PDF417 options.
                barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 5;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 1;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 10;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "report.pdf";
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 0x1A2B;

                // 3️⃣ Save the barcode as a PNG image.
                barcodeGenerator.Save(outputPath, BarCodeImageFormat.Png);
            }

            Console.WriteLine($"PDF417 barcode image created at: {outputPath}");
        }
    }
}
```

**Запуск программы:**  

1. Создайте новый консольный проект .NET 6 (или новее).  
2. Добавьте пакет NuGet Aspose.BarCode (`dotnet add package Aspose.BarCode`).  
3. Замените сгенерированный `Program.cs` кодом выше.  
4. Отрегулируйте `outputPath`, указав папку, в которую у вас есть права записи.  
5. Скомпилируйте и запустите — консоль подтвердит расположение изображения.

---

## Часто задаваемые вопросы и устранение неполадок

| Question | Answer |
|----------|--------|
| *Что делать, если штрихкод слишком широкий для моей этикетки?* | Уменьшите `Columns` или увеличьте `XDimension.Pixels`, чтобы сбалансировать ширину и читаемость. |
| *Нужно ли задавать контрольную сумму?* | Контрольная сумма необязательна |

## Что следует изучить дальше?

Следующие учебники охватывают тесно связанные темы, которые развивают техники, продемонстрированные в этом руководстве. Каждый ресурс включает полностью работающие примеры кода с пошаговыми объяснениями, чтобы помочь вам освоить дополнительные возможности API и исследовать альтернативные подходы в ваших проектах.

- [Create PDF417 Barcode in C# – Complete Step‑by‑Step Guide](/barcode/english/net/compact-pdf417-encoding/create-pdf417-barcode-in-c-complete-step-by-step-guide/)
- [Create PDF417 Barcode Metadata in C# – Complete Step‑by‑Step Guide](/barcode/english/net/compact-pdf417-encoding/create-pdf417-barcode-metadata-in-c-complete-step-by-step-gu/)
- [Generate barcode with text – Full PDF417 Macro Guide](/barcode/english/net/compact-pdf417-encoding/generate-barcode-with-text-full-pdf417-macro-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}