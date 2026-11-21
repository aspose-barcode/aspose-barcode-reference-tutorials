---
category: general
date: 2026-11-20
description: Узнайте, как генерировать штрих‑код PDF417 в C# с помощью BarcodeGenerator.
  Это пошаговое руководство охватывает X‑Dimension, настройки колонок и экспорт в
  PNG.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate pdf417 barcode
- PDF417 barcode in C#
- BarcodeGenerator EncodeTypes
- set XDimension pixels
- configure PDF417 columns
- save barcode as PNG
language: ru
lastmod: 2026-11-20
og_description: Быстро создавайте штрих‑код PDF417 на C#. Следуйте этому руководству,
  чтобы задать размеры, количество столбцов и экспортировать штрих‑код в виде PNG‑изображения.
og_image_alt: Screenshot of C# code that generates a PDF417 barcode and saves it as
  a PNG file
og_title: Создание штрих‑кода PDF417 на C# – полное пошаговое руководство
schemas:
- author: Aspose
  dateModified: '2026-11-20'
  description: Learn how to generate PDF417 barcode in C# using BarcodeGenerator.
    This step‑by‑step guide covers X‑Dimension, column settings, and PNG export.
  headline: How to generate PDF417 barcode in C# with BarcodeGenerator
  type: TechArticle
- description: Learn how to generate PDF417 barcode in C# using BarcodeGenerator.
    This step‑by‑step guide covers X‑Dimension, column settings, and PNG export.
  name: How to generate PDF417 barcode in C# with BarcodeGenerator
  steps:
  - name: '**Initialize the generator** – The `BarcodeGenerator` ties the chosen symbology
      (`EncodeTypes.Pdf417`) to the data you want to encode. Without this object you
      cannot access any further configuration.'
    text: '**Initialize the generator** – The `BarcodeGenerator` ties the chosen symbology
      (`EncodeTypes.Pdf417`) to the data you want to encode. Without this object you
      cannot access any further configuration.'
  - name: '**Set X‑Dimension** – PDF417 is built from tiny rectangular modules. Changing
      `XDimension.Pixels` lets you control the barcode’s visual density, which is
      crucial for readability on low‑resolution displays or printers.'
    text: '**Set X‑Dimension** – PDF417 is built from tiny rectangular modules. Changing
      `XDimension.Pixels` lets you control the barcode’s visual density, which is
      crucial for readability on low‑resolution displays or printers.'
  - name: '**Configure columns** – PDF417 can arrange its codewords in a variable
      number of columns. Fewer columns produce a taller barcode, while more columns
      flatten it. Adjust this to fit the space where the image will be placed.'
    text: '**Configure columns** – PDF417 can arrange its codewords in a variable
      number of columns. Fewer columns produce a taller barcode, while more columns
      flatten it. Adjust this to fit the space where the image will be placed.'
  - name: '**Save as PNG** – PNG is a loss‑less format, preserving the sharp edges
      required for accurate scanning. You could also choose JPEG or BMP, but PNG is
      the safest default.'
    text: '**Save as PNG** – PNG is a loss‑less format, preserving the sharp edges
      required for accurate scanning. You could also choose JPEG or BMP, but PNG is
      the safest default.'
  type: HowTo
tags:
- barcode
- PDF417
- C#
- Aspose.BarCode
title: Как сгенерировать штрих‑код PDF417 в C# с помощью BarcodeGenerator
url: /ru/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-with-barcodegenerator/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Как генерировать штрих‑код PDF417 в C# с помощью BarcodeGenerator

Если вам нужно **создать штрих‑код PDF417** в .NET‑приложении, это руководство покажет, как это сделать. Вы увидите полностью готовый, исполняемый пример, который задаёт X‑Dimension, выбирает количество столбцов и сохраняет результат в виде PNG‑изображения.

Создание штрих‑кода PDF417 часто требуется, когда нужно закодировать большой объём данных — например, водительское удостоверение, посадочный талон или запись инвентаря — в компактное, машинно‑читаемое изображение. В этом уроке мы используем класс **BarcodeGenerator** из библиотеки Aspose.BarCode, но принципы применимы к любой библиотеке, поддерживающей PDF417.

К концу статьи вы сможете:

* Инициализировать `BarcodeGenerator` для кодирования PDF417.  
* Регулировать размер модуля с помощью **set XDimension pixels**.  
* Управлять расположением с помощью **configure PDF417 columns**.  
* **Сохранить штрих‑код как PNG** для использования в веб‑страницах, мобильных приложениях или печатных материалах.  

> **Требования**  
> * .NET 6.0 или новее (код также работает с .NET Framework 4.7+).  
> * Ссылка на NuGet‑пакет **Aspose.BarCode** (`Install-Package Aspose.BarCode`).  
> * Базовые знания C# и Visual Studio (или любой другой IDE).

---

## Как генерировать штрих‑код PDF417 в C#

Суть решения — четырёхшаговый процесс. Каждый шаг вынесен в отдельный метод, чтобы вы могли переиспользовать логику в более крупных проектах.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace Pdf417Demo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Initialize the generator with the desired text
            var generator = CreateGenerator("Åspóse.Barcóde©");

            // 2️⃣ Adjust the X‑Dimension (module size)
            SetXDimension(generator, 2);

            // 3️⃣ Define how many columns the barcode should have
            SetPdf417Columns(generator, 3);

            // 4️⃣ Save the barcode as a PNG file
            SaveAsPng(generator, @"YOUR_DIRECTORY\Pdf417Basic.png");

            Console.WriteLine("PDF417 barcode generated successfully.");
        }

        // ---------------------------------------------------------
        // Step 1: Create a BarcodeGenerator for PDF417
        // ---------------------------------------------------------
        private static BarcodeGenerator CreateGenerator(string text)
        {
            // EncodeTypes.Pdf417 tells the library to use the PDF417 symbology.
            return new BarcodeGenerator(EncodeTypes.Pdf417, text);
        }

        // ---------------------------------------------------------
        // Step 2: Set the X‑Dimension (size of a single module)
        // ---------------------------------------------------------
        private static void SetXDimension(BarcodeGenerator generator, int pixels)
        {
            // XDimension controls the width of the smallest black/white bar.
            // A value of 2 pixels works well for most screen resolutions.
            generator.Parameters.Barcode.XDimension.Pixels = pixels;
        }

        // ---------------------------------------------------------
        // Step 3: Configure the number of columns in the PDF417 barcode
        // ---------------------------------------------------------
        private static void SetPdf417Columns(BarcodeGenerator generator, int columns)
        {
            // Columns affect the barcode’s aspect ratio.
            // Small numbers (e.g., 3) produce a tall barcode; larger numbers make it wider.
            generator.Parameters.Barcode.Pdf417.Columns = columns;
        }

        // ---------------------------------------------------------
        // Step 4: Export the barcode as a PNG image
        // ---------------------------------------------------------
        private static void SaveAsPng(BarcodeGenerator generator, string outputPath)
        {
            // BarCodeImageFormat.Png ensures lossless quality.
            generator.Save(outputPath, BarCodeImageFormat.Png);
        }
    }
}
```

### Почему важны именно эти четыре шага

1. **Инициализация генератора** — `BarcodeGenerator` связывает выбранную символьность (`EncodeTypes.Pdf417`) с данными, которые вы хотите закодировать. Без этого объекта дальнейшая настройка невозможна.  
2. **Установка X‑Dimension** — PDF417 состоит из крошечных прямоугольных модулей. Изменяя `XDimension.Pixels`, вы контролируете визуальную плотность штрих‑кода, что критично для читаемости на низко‑разрешающих дисплеях или принтерах.  
3. **Настройка столбцов** — PDF417 может располагать свои кодовые слова в переменном числе столбцов. Меньшее количество столбцов даёт более высокий штрих‑код, большее — более широкий. Подгоняйте это под доступное пространство.  
4. **Сохранение как PNG** — PNG — формат без потерь, сохраняющий резкие границы, необходимые для точного сканирования. Можно также выбрать JPEG или BMP, но PNG — самый надёжный вариант по умолчанию.

---

## Настройка размеров штрих‑кода (X‑Dimension)

Шаг **set XDimension pixels** напрямую влияет на то, как сканеры интерпретируют штрих‑код. Если модуль слишком мал, камеры низкого качества могут пропустить отдельные полосы; если он слишком велик, штрих‑код станет избыточно большим.

```csharp
generator.Parameters.Barcode.XDimension.Pixels = 2; // 2‑pixel modules
```

**Рекомендация:** протестируйте полученное изображение при планируемом размере печати. Для печати высокой плотности (300 dpi и выше) хорошо подходит значение `1` или `2`. Для отображения на экране при 96 dpi оптимальны `2`–`3`, обеспечивая чёткое изображение.

---

## Установка количества столбцов PDF417

Шаг **configure PDF417 columns** позволяет задать форму штрих‑кода.

```csharp
generator.Parameters.Barcode.Pdf417.Columns = 3; // three columns → tall barcode
```

### Когда менять количество столбцов

| Столбцы | Получаемая форма | Типичный сценарий |
|---------|------------------|-------------------|
| 1–3     | Высокий, узкий   | Этикетки с ограниченной шириной |
| 4–9     | Сбалансированный | Универсальное сканирование |
| 10+    | Широкий, низкий  | Большие вывески или веб‑графика |

Если объём данных превышает стандартную ёмкость, библиотека автоматически добавит дополнительные строки, но вы всё равно можете влиять на соотношение сторон, подбирая количество столбцов.

---

## Экспорт штрих‑кода в PNG

Сохранить штрих‑код как PNG‑изображение просто:

```csharp
generator.Save(@"C:\Barcodes\Pdf417Basic.png", BarCodeImageFormat.Png);
```

**Почему PNG?**  
* Сжатие без потерь сохраняет чёткие границы, необходимые сканерам.  
* PNG поддерживает прозрачность, что может пригодиться, если позже наложить штрих‑код на цветной фон.

Если нужен другой формат, замените `BarCodeImageFormat.Png` на `Jpeg`, `Bmp` или `Svg` — API выполнит конвертацию автоматически.

---

## Частые ошибки и их устранение

| Проблема | Возможная причина | Решение |
|----------|-------------------|---------|
| Штрих‑код выглядит размытым | X‑Dimension слишком мал для текущего разрешения вывода | Увеличьте `XDimension.Pixels` до 3 или 4. |
| Сканер не читает код | Юникод‑символы не поддерживаются выбранным шрифтом | Убедитесь, что шрифт библиотеки поддерживает символы, либо замените их на ASCII‑эквиваленты. |
| Файл не создаётся | Неправильный путь или отсутствие прав записи | Используйте абсолютный путь и проверьте права доступа к папке. |
| Слишком много строк, штрих‑код высокий | Количество столбцов слишком мало для длины данных | Увеличьте `Pdf417.Columns` до большего числа (например, 6). |

---

## Полный рабочий пример

Ниже представлена **полная программа**, которую можно скопировать в новый консольный проект. Дополнительный код не требуется, кроме `using`‑директив и пакета Aspose.BarCode.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace Pdf417Demo
{
    class Program
    {
        static void Main()
        {
            var generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Åspóse.Barcóde©");
            generator.Parameters.Barcode.XDimension.Pixels = 2;
            generator.Parameters.Barcode.Pdf417.Columns = 3;
            generator.Save(@"YOUR_DIRECTORY\Pdf417Basic.png", BarCodeImageFormat.Png);
            Console.WriteLine("PDF417 barcode generated and saved as PNG.");
        }
    }
}
```

**Ожидаемый результат:** файл `Pdf417Basic.png`, содержащий чёткий штрих‑код PDF417, кодирующий строку `Åspóse.Barcóde©`. При открытии изображение должно показывать серию вертикальных прямоугольных полос с более плотной левой частью (из‑за трёх‑столбцовой раскладки).

---

## Заключение

Теперь вы знаете, как **генерировать штрих‑код PDF417** в C# с помощью класса `BarcodeGenerator`. В уроке рассмотрены инициализация генератора, **set XDimension pixels**, **configure PDF417 columns** и **save barcode as PNG** — ключевые шаги любого готового к продакшну процесса создания штрих‑кодов.

Дальше вы можете:

* Поэкспериментировать с другими `EncodeTypes` (например, QR, Code128).  
* Добавить уровни коррекции ошибок через `generator.Parameters.Barcode.Pdf417.ErrorLevel`.  
* Выводить штрих‑код напрямую в `MemoryStream` для веб‑API.  

Не стесняйтесь адаптировать код под свой проект и делиться результатами в комментариях или на Stack Overflow, используя тег `#pdf417`. Приятного кодинга!

## Что изучать дальше?

Следующие руководства охватывают смежные темы, расширяющие техники, продемонстрированные в этом пособии. Каждый ресурс содержит полностью рабочие примеры кода с пошаговыми объяснениями, помогающими освоить дополнительные возможности API и исследовать альтернативные подходы в ваших проектах.

- [Generate PDF417 barcode as PNG in C# – step‑by‑step guide](/barcode/english/net/compact-pdf417-encoding/generate-pdf417-barcode-as-png-in-c-step-by-step-guide/)
- [How to generate PDF417 barcode in C# – step‑by‑step guide](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-step-by-step-guide/)
- [How to generate PDF417 barcode in C# with custom dimensions](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-with-custom-dimensions/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}