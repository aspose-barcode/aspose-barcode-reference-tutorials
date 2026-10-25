---
category: general
date: 2026-10-24
description: Узнайте, как генерировать штрих‑код PDF417 с помощью Aspose.BarCode в
  C# с компактными настройками и управлением XDimension штрих‑кода.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate PDF417 barcode
- Aspose.BarCode
- compact PDF417
- barcode XDimension
- PDF417 columns
language: ru
lastmod: 2026-10-24
og_description: Создайте штрих‑код PDF417 на C# с помощью Aspose.BarCode. Следуйте
  этому полному руководству, чтобы создавать компактные изображения PDF417, управлять
  XDimension и задавать количество столбцов.
og_image_alt: Screenshot of generated PDF417 barcode using Aspose.BarCode
og_title: Создание штрих‑кода PDF417 с помощью Aspose.BarCode – пошаговое руководство
  на C#
schemas:
- author: Aspose
  dateModified: '2026-10-24'
  description: Learn how to generate PDF417 barcode using Aspose.BarCode in C# with
    compact settings and barcode XDimension control.
  headline: How to generate PDF417 barcode with Aspose.BarCode in C#
  type: TechArticle
- description: Learn how to generate PDF417 barcode using Aspose.BarCode in C# with
    compact settings and barcode XDimension control.
  name: How to generate PDF417 barcode with Aspose.BarCode in C#
  steps:
  - name: 1. Changing the image format
    text: '```csharp generator.Save("CompactPdf417.svg", BarCodeImageFormat.Svg);
      ```'
  - name: 2. Encoding large amounts of data
    text: 'PDF417 can store up to ~1.1 KB of text. When the payload exceeds the capacity
      of three columns, the library automatically adds rows. To keep the barcode compact,
      you can:'
  - name: 3. Using a license to remove the trial watermark
    text: '```csharp Aspose.BarCode.License license = new Aspose.BarCode.License();
      license.SetLicense("Aspose.BarCode.lic"); ```'
  - name: 4. Handling exceptions
    text: '```csharp try { generator.Save(outputPath, BarCodeImageFormat.Png); } catch
      (Exception ex) { Console.Error.WriteLine($"Failed to generate barcode: {ex.Message}");
      } ```'
  type: HowTo
tags:
- barcode
- Aspose.BarCode
- PDF417
- C#
title: Как сгенерировать штрих‑код PDF417 с помощью Aspose.BarCode в C#
url: /ru/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-with-aspose-barcode-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Как сгенерировать штрихкод PDF417 с помощью Aspose.BarCode на C#

Если вам необходимо **создать штрихкод PDF417** в .NET‑приложении, это руководство покажет вам полное, готовое к запуску решение. Вы увидите, как Aspose.BarCode упрощает процесс, предоставляя тонкую настройку **compact PDF417**, **barcode XDimension** и **PDF417 columns**.

Создание штрихкода — распространённое требование для систем учёта, платформ билетирования и документооборота. К концу этого руководства у вас будет автономная программа на C#, генерирующая чёткое PNG‑изображение штрихкода PDF417, готовое к встраиванию в любой UI или печати на этикетке.

## Что вам понадобится

- .NET 6.0 SDK или новее (код также работает с .NET Framework 4.6+)
- Visual Studio 2022 или любой предпочитаемый вами редактор C#
- Действительная лицензия Aspose.BarCode for .NET (бесплатная пробная версия подходит для разработки)
- Базовое знакомство с синтаксисом C#

> **Pro tip:** Если вы оцениваете Aspose.BarCode, скачайте пробную версию с официального сайта и добавьте в проект NuGet‑пакет `Aspose.BarCode`. Пробная версия добавляет небольшую водяную метку к сгенерированному изображению, которая исчезает после применения лицензии.

## Шаг 1: Установите пакет Aspose.BarCode NuGet

Откройте терминал в папке решения и выполните:

```bash
dotnet add package Aspose.BarCode
```

Команда загружает последнюю стабильную версию (по состоянию на октябрь 2026, версия 23.12). Добавление пакета восстанавливает пространство имён `Aspose.BarCode.Generation`, которое вы будете использовать для **создания штрихкода PDF417** изображений.

## Шаг 2: Создайте базовый консольный проект C#

Если проекта ещё нет, создайте его:

```bash
dotnet new console -n Pdf417Demo
cd Pdf417Demo
```

Откройте `Program.cs`. Скелет уже содержит метод `Main`, куда мы поместим код генерации штрихкода.

## Шаг 3: Инициализируйте генератор штрихкода

Сначала импортируйте нужное пространство имён:

```csharp
using Aspose.BarCode.Generation;
```

Затем внутри `Main` создайте экземпляр `BarcodeGenerator` с символьностью PDF417 и данными, которые нужно закодировать:

```csharp
// Step 3: Initialize the generator for a PDF417 barcode
BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Åspóse.Barcóde©");
```

Строка содержит Unicode‑символы, чтобы продемонстрировать корректную работу Aspose.BarCode с не‑ASCII вводом. Если нужны только ASCII‑символы, замените текст любой обычной строкой.

## Шаг 4: Настройте XDimension штрихкода (размер модуля)

**barcode XDimension** определяет ширину самого маленького бара (модуля). Установка в пикселях даёт пиксель‑точный контроль над окончательным размером изображения:

```csharp
// Step 4: Set the module size – XDimension in pixels
generator.Parameters.Barcode.XDimension.Pixels = 2;
```

Значение `2` пикселя даёт компактное изображение без потери надёжности сканирования. Увеличьте значение для более крупных штрихкодов или уменьшите для очень плотных макетов.

## Шаг 5: Настройте параметры compact PDF417

Две настройки, специфичные для PDF417, существенно влияют на визуальный объём:

| Параметр | Значение | Типичное значение для компактного вывода |
|----------|----------|-------------------------------------------|
| `Columns` | Number of data columns | `3` |
| `Truncate` (compact mode) | Omits the right‑hand quiet zone and reduces the number of rows | `true` |

Примените их так:

```csharp
// Step 5: Use a small number of columns and enable compact mode
generator.Parameters.Barcode.Pdf417.Columns = 3;      // PDF417 columns
generator.Parameters.Barcode.Pdf417.Truncate = true; // compact PDF417
```

Использование **PDF417 columns** со значением `3` вместе с `Truncate = true` создаёт *compact PDF417* штрихкод, который удобно помещается на стандартной этикетке и остаётся читаемым большинством сканеров.

## Шаг 6: Сохраните изображение штрихкода

Наконец, запишите штрихкод на диск. В примере сохраняется PNG, но Aspose.BarCode также поддерживает BMP, JPEG, GIF, TIFF и SVG:

```csharp
// Step 6: Save the barcode as a PNG file
string outputPath = Path.Combine(Environment.CurrentDirectory, "CompactPdf417.png");
generator.Save(outputPath, BarCodeImageFormat.Png);
Console.WriteLine($"Barcode saved to {outputPath}");
```

Константа `BarCodeImageFormat.Png` указывает библиотеке генерировать без потерь PNG, что идеально подходит для дальнейшей обработки или печати.

## Полный, готовый к запуску исходный код

```csharp
using System;
using System.IO;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // 1️⃣ Create the generator for PDF417 with Unicode text
        BarcodeGenerator generator = new BarcodeGenerator(
            EncodeTypes.Pdf417,
            "Åspóse.Barcóde©");

        // 2️⃣ Set module size – barcode XDimension in pixels
        generator.Parameters.Barcode.XDimension.Pixels = 2;

        // 3️⃣ Configure compact PDF417 options
        generator.Parameters.Barcode.Pdf417.Columns = 3;      // PDF417 columns
        generator.Parameters.Barcode.Pdf417.Truncate = true; // compact PDF417

        // 4️⃣ Save as PNG
        string outputPath = Path.Combine(
            Environment.CurrentDirectory,
            "CompactPdf417.png");

        generator.Save(outputPath, BarCodeImageFormat.Png);
        Console.WriteLine($"Barcode saved to {outputPath}");
    }
}
```

Запуск программы создаёт файл `CompactPdf417.png` в корневой папке проекта. Откройте его в любом просмотрщике изображений — вы увидите плотно упакованный PDF417 штрихкод, кодирующий строку *Åspóse.Barcóde©*.

![Скриншот сгенерированного PDF417 штрихкода с использованием Aspose.BarCode](placeholder-image.png "Сгенерированный PDF417 штрихкод")

*Текст alt: Скриншот сгенерированного PDF417 штрихкода с использованием Aspose.BarCode* — этот alt‑текст содержит основной ключевой запрос для доступности и SEO.

## Проверка результата

1. Откройте PNG‑файл. Штрихкод должен состоять из трёх вертикальных колонок данных с компактным макетом (без дополнительных тихих зон справа).
2. Сканируйте изображение с помощью сканера штрихкодов на смартфоне, поддерживающего PDF417. Декодированный текст должен совпадать с исходной строкой.
3. Если сканер не читает, попробуйте увеличить `XDimension.Pixels` до `3` или `4`. Большие модули повышают читаемость на устройствах с низким разрешением.

## Распространённые варианты и граничные случаи

### 1. Изменение формата изображения

```csharp
generator.Save("CompactPdf417.svg", BarCodeImageFormat.Svg);
```

SVG — векторный формат, сохраняющий чёткость штрихкода при любом масштабе, что удобно для веб‑страниц.

### 2. Кодирование больших объёмов данных

PDF417 может хранить до ~1,1 KB текста. Когда полезная нагрузка превышает ёмкость трёх колонок, библиотека автоматически добавляет строки. Чтобы сохранить компактность, можно:

- Сократить длину данных (например, использовать идентификатор вместо полного сообщения)
- Увеличить количество **PDF417 columns** (например, `generator.Parameters.Barcode.Pdf417.Columns = 5;`)

### 3. Использование лицензии для удаления водяной метки пробной версии

```csharp
Aspose.BarCode.License license = new Aspose.BarCode.License();
license.SetLicense("Aspose.BarCode.lic");
```

Поместите файл лицензии рядом с исполняемым файлом. После активации лицензии сгенерированное изображение будет без водяной метки.

### 4. Обработка исключений

```csharp
try
{
    generator.Save(outputPath, BarCodeImageFormat.Png);
}
catch (Exception ex)
{
    Console.Error.WriteLine($"Failed to generate barcode: {ex.Message}");
}
```

Типичные ошибки включают недостаточные права записи или неподдерживаемый формат изображения.

## Почему эти настройки важны

- **barcode XDimension** — контролирует визуальный вес каждого бара. Слишком маленький делает штрихкод нечитаемым, слишком большой тратит место.
- **PDF417 columns** — меньше колонок дают более узкий штрихкод, но увеличивают количество строк.

## Что следует изучить дальше?

Следующие руководства охватывают тесно связанные темы, расширяющие техники, продемонстрированные в этом руководстве. Каждый ресурс включает полностью работающие примеры кода с пошаговыми объяснениями, помогая вам освоить дополнительные возможности API и исследовать альтернативные подходы в собственных проектах.

- [Как сгенерировать PDF417 штрихкод с Aspose – Полное руководство](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-with-aspose-complete-guide/)
- [Создать PDF417 штрихкод с компактными настройками на C#](/barcode/english/net/compact-pdf417-encoding/generate-pdf417-barcode-with-compact-settings-in-c/)
- [Как сохранить штрихкод и сгенерировать PDF417 с Aspose на C#](/barcode/english/net/compact-pdf417-encoding/how-to-save-barcode-and-generate-pdf417-with-aspose-in-c/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}