---
category: general
date: 2026-10-15
description: Создайте PNG‑изображение штрих‑кода в C# с компактным примером PDF417
  — узнайте, как задать столбцы, настроить размеры и сгенерировать изображение.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode png
- how to create barcode
- how to set columns
- c# barcode example
language: ru
lastmod: 2026-10-15
og_description: Создайте PNG‑штрихкод в C# с примером компактного PDF417. Это руководство
  показывает, как задать столбцы, настроить размеры и сохранить изображение.
og_image_alt: Screenshot showing a generated barcode PNG created with C#
og_title: Создайте PNG штрихкода в C# – полный учебник по программированию
schemas:
- author: Aspose
  dateModified: '2026-10-15'
  description: Create barcode PNG in C# with a compact PDF417 example – learn how
    to set columns, adjust dimensions, and generate the image.
  headline: How to create barcode PNG in C# – step‑by‑step guide
  type: TechArticle
- description: Create barcode PNG in C# with a compact PDF417 example – learn how
    to set columns, adjust dimensions, and generate the image.
  name: How to create barcode PNG in C# – step‑by‑step guide
  steps:
  - name: Initialise the barcode generator with the desired text
    text: '```csharp using Aspose.BarCode.Generation;'
  - name: Set the module (X) dimension in pixels
    text: '```csharp // Set the width of the smallest bar (module) to 2 pixels generator.Parameters.Barcode.XDimension.Pixels
      = 2; ```'
  - name: Define the number of columns for the PDF417 barcode
    text: '```csharp // Specify that the barcode should use 3 columns generator.Parameters.Barcode.Pdf417.Columns
      = 3; ```'
  - name: Enable the compact layout by truncating the barcode
    text: '```csharp // Truncate removes unnecessary empty rows, making the barcode
      shorter generator.Parameters.Barcode.Pdf417.Truncate = true; ```'
  - name: Save the barcode image as PNG
    text: '```csharp // Choose the output folder and file name string outputPath =
      Path.Combine(Environment.CurrentDirectory, "CompactPdf417.png");'
  - name: Full, runnable example
    text: 'Putting everything together, here is a self‑contained program you can copy,
      paste, and run:'
  type: HowTo
tags:
- barcode
- C#
- PDF417
- image generation
title: Как создать PNG‑штрихкод в C# — пошаговое руководство
url: /ru/net/compact-pdf417-encoding/how-to-create-barcode-png-in-c-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Как создать PNG штрихкода в C# – пошаговое руководство

Если вам нужно **создать PNG штрихкода** из кода C#, этот учебник покажет полное решение в несколько строк. Вы увидите, как задать количество колонок, настроить размер модуля и сохранить компактный PDF417 штрихкод как PNG‑изображение — всё в одном простом примере.

Программное создание штрихкодов устраняет ручной шаг с графическим редактором и позволяет внедрять штрихкоды напрямую в счета, билеты или этикетки. В последующих разделах мы рассмотрим всё, что нужно знать о **создании штрихкода**, почему важна каждая настройка и как адаптировать код под разные сценарии.

## Требования

Прежде чем начать, убедитесь, что у вас есть:

* .NET 6.0 или новее (код также работает с .NET Framework 4.7+)
* Ссылка на библиотеку штрихкодов, поддерживающую PDF417, например **Aspose.BarCode for .NET** или **IronBarcode**. В примере используется Aspose.BarCode, которую можно установить через NuGet:

```bash
dotnet add package Aspose.BarCode
```

* Базовые знания синтаксиса C# и Visual Studio (или любой другой IDE).

> **Pro tip:** Если вы ищете бесплатную альтернативу, открытая библиотека **ZXing.Net** также поддерживает PDF417, но имена свойств немного отличаются. Показанные здесь концепции остаются теми же.

## Как создать PNG штрихкода в C# (основной шаг)

Суть решения — объект `BarcodeGenerator`, настроенный для кодирования PDF417. Ниже разбираются все строки кода, объясняется **как задать колонки** и почему эти настройки влияют на конечный размер PNG.

### Шаг 1: Инициализировать генератор штрихкода с нужным текстом

```csharp
using Aspose.BarCode.Generation;

// The text you want to encode in the barcode
string barcodeText = "Compact example";

// Create a generator for PDF417 barcodes
using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, barcodeText))
{
    // Subsequent configuration goes here
}
```

*Почему это важно*: Перечисление `EncodeTypes.Pdf417` указывает библиотеке создавать двумерный «слоистый» штрихкод. Конструктор также принимает данные для кодирования, поэтому отдельный вызов `SetData` не требуется.

### Шаг 2: Установить размер модуля (X) в пикселях

```csharp
// Set the width of the smallest bar (module) to 2 pixels
generator.Parameters.Barcode.XDimension.Pixels = 2;
```

**X‑размер** контролирует визуальную плотность штрихкода. Меньшее значение дает более плотное изображение, что полезно, когда нужен компактный PNG для мобильных экранов или ограниченного места печати.

### Шаг 3: Задать количество колонок для PDF417 штрихкода

```csharp
// Specify that the barcode should use 3 columns
generator.Parameters.Barcode.Pdf417.Columns = 3;
```

Эта строка демонстрирует **как задать колонки**. PDF417 может автоматически выбирать оптимальное количество колонок, но явное указание даёт предсказуемую ширину, особенно при встраивании PNG в фиксированный макет.

### Шаг 4: Включить компактный макет, обрезав штрихкод

```csharp
// Truncate removes unnecessary empty rows, making the barcode shorter
generator.Parameters.Barcode.Pdf417.Truncate = true;
```

Когда `Truncate` равно `true`, библиотека удаляет завершающие строки без данных, уменьшая общую высоту изображения без потери информации.

### Шаг 5: Сохранить изображение штрихкода как PNG

```csharp
// Choose the output folder and file name
string outputPath = Path.Combine(Environment.CurrentDirectory, "CompactPdf417.png");

// Save the generated barcode as a PNG file
generator.Save(outputPath, BarCodeImageFormat.Png);
```

Метод `Save` записывает штрихкод на диск в указанном формате. PNG — без потерь, что делает его идеальным для сканирующих приложений, требующих точного обнаружения краёв.

### Полный, готовый к запуску пример

Объединив всё вместе, получаем автономную программу, которую можно скопировать, вставить и запустить:

```csharp
using System;
using System.IO;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // 1️⃣ Initialise the generator with the data to encode
        string barcodeText = "Compact example";

        using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, barcodeText))
        {
            // 2️⃣ Set module width to 2 pixels for a tighter image
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // 3️⃣ Explicitly set the number of columns (how to set columns)
            generator.Parameters.Barcode.Pdf417.Columns = 3;

            // 4️⃣ Enable compact layout by truncating empty rows
            generator.Parameters.Barcode.Pdf417.Truncate = true;

            // 5️⃣ Define the output path and save as PNG (create barcode PNG)
            string outputPath = Path.Combine(Directory.GetCurrentDirectory(), "CompactPdf417.png");
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"Barcode PNG saved to: {outputPath}");
        }
    }
}
```

**Ожидаемый результат** — После выполнения программы в папке запуска появится файл `CompactPdf417.png`. На изображении будет PDF417 штрихкод с тремя колонками, достаточно компактный, чтобы поместиться на стандартной этикетке 2 × 2 см, оставаясь полностью считываемым.

![Create barcode PNG example](placeholder.png){alt="Создать PNG штрихкода с помощью C#"}

## Как задать колонки для разных размеров данных (вторичный запрос)

Количество колонок влияет как на ширину, так и на читаемость штрихкода:

| Колонки | Приблизительная ширина (px) | Типичный сценарий |
|--------|-----------------------------|-------------------|
| 1‑2    | Узко, высоко                | Маленькие метки, печать в стиле RFID |
| 3‑5    | Сбалансировано              | Универсальные этикетки |
| 6‑9    | Широко, низко               | Большие плакаты или упаковка |

Если строка данных увеличивается, библиотека может автоматически увеличить количество строк, чтобы удержать штрихкод в пределах заданного количества колонок. Однако принудительное указание слишком малого количества колонок может привести к избыточной высоте, что может не поместиться на принтере чеков. Регулируйте количество колонок в зависимости от физических ограничений вашего носителя.

## Как создавать штрихкоды в других форматах (вторичный запрос)

Хотя PNG — самый распространённый формат для веба и мобильных устройств, вам могут потребоваться **как создать штрихкод** в JPEG, BMP или SVG для специализированных рабочих процессов:

```csharp
// Save as JPEG with 90 % quality
generator.Save("CompactPdf417.jpg", BarCodeImageFormat.Jpeg, 90);

// Save as SVG (vector, infinite scaling)
generator.Save("CompactPdf417.svg", BarCodeImageFormat.Svg);
```

Выбор формата зависит от downstream‑потребителя:

* **PNG** — без потерь, идеально для сканеров.
* **JPEG** — меньший размер файла, приемлем, если небольшие артефакты сжатия допустимы.
* **SVG** — идеально для печати высокого разрешения или масштабирования UI.

## Пример C# штрихкода: обработка ошибок и граничных случаев

Надёжный **c# barcode example** должен предусматривать возможные ошибки во время выполнения:

```csharp
try
{
    // All configuration steps as shown earlier
    generator.Save(outputPath, BarCodeImageFormat.Png);
}
catch (ArgumentException ex)
{
    Console.Error.WriteLine($"Invalid barcode parameter: {ex.Message}");
}
catch (IOException ex)
{
    Console.Error.WriteLine($"Failed to write file: {ex.Message}");
}
```

*Зачем оборачивать в `try/catch`?* Неправильные символы в тексте, неподдерживаемые размеры или проблемы с правами записи вызовут исключения. Обработка их позволяет избежать падения приложения при пакетной обработке.

## Расширение примера: добавление логотипа или фона

Во многих реальных сценариях требуется наложить логотип или задний фон. API Aspose.BarCode позволяет объединять штрихкод с bitmap‑изображением:

```csharp
// Load a logo image
using (Bitmap logo = (Bitmap)Image.FromFile("logo.png"))
{
    generator.Parameters.Barcode.ImageFormat = BarCodeImageFormat.Png;
    generator.Parameters.Barcode.Pdf417.EnablePdf417CodewordCount = true; // optional

    // Merge the logo with the barcode (centered)
    generator.Save("BarcodeWithLogo.png", BarCodeImageFormat.Png, logo);
}
```

Эта техника сохраняет рабочий процесс **create barcode PNG**, одновременно обогащая визуальный брендинг конечного изображения.

## Итоги

В этом руководстве мы показали, как **создать PNG штрихкода** в C# с использованием компактной конфигурации PDF417. Вы узнали:

* Точный код для инициализации `BarcodeGenerator`.
* **Как задать колонки** и почему их количество важно для размера и читаемости.
* Как настроить X‑размер и включить обрезку для более плотного PNG.
* Способы сохранения изображения в PNG, JPEG или SVG.
* Шаблоны обработки ошибок для production‑готового **c# barcode example**.
* Опциональные расширения, такие как наложение логотипа и настройка фона.

Теперь у вас есть готовый фрагмент кода, который можно интегрировать в генераторы счетов, системы билетов или инструменты управления запасами. Экспериментируйте с различными значениями колонок, размерами модулей или типами штрихкодов (например, QR, Code128), чтобы увидеть, как меняется изображение.

## Следующие шаги

* Исследуйте другие типы кодирования (`EncodeTypes.QR`, `EncodeTypes.Code128`), чтобы покрыть больше сценариев.
* Сочетайте генерацию штрихкода с библиотеками создания PDF (например, **iTextSharp**) для встраивания PNG непосредственно в документы.
* Изучите динамическое масштабирование: вычисляйте оптимальное количество колонок на основе длины входной строки и размеров целевой этикетки.

Приятного кодинга и наслаждайтесь простотой программного создания чётких PNG‑штрихкодов в C#!

## Что изучать дальше?

Следующие учебники охватывают близко связанные темы, расширяющие техники, продемонстрированные в этом руководстве. Каждый ресурс включает полностью работающие примеры кода с пошаговыми объяснениями, чтобы помочь вам освоить дополнительные возможности API и исследовать альтернативные подходы в собственных проектах.

- [How to create PDF417 barcode and save it as PNG in C#](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-and-save-it-as-png-in-c/)
- [How to create PDF417 barcode and set its size in C#](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-and-set-its-size-in-c/)
- [How to create PDF417 barcode in C# with compact mode](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-in-c-with-compact-mode/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}