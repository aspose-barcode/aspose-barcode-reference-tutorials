---
category: general
date: 2026-11-20
description: Создайте изображение штрихкода в C# с использованием Aspose.BarCode.
  Узнайте, как сгенерировать штрихкод PDF417 с пользовательским макетом и сохранить
  его в формате PNG.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode image
- generate pdf417 barcode
- how to generate pdf417
language: ru
lastmod: 2026-11-20
og_description: Создайте изображение штрихкода в C# с помощью Aspose.BarCode. Это
  руководство показывает, как сгенерировать штрихкод PDF417, настроить макет и экспортировать
  в PNG.
og_image_alt: Screenshot of generated barcode image created with PDF417 using C#
og_title: Создайте изображение штрихкода PDF417 в C# – полный учебник
schemas:
- author: Aspose
  dateModified: '2026-11-20'
  description: Create barcode image in C# using Aspose.BarCode. Learn how to generate
    PDF417 barcode with a custom layout and save it as PNG.
  headline: How to create barcode image with PDF417 in C# – step‑by‑step guide
  type: TechArticle
- description: Create barcode image in C# using Aspose.BarCode. Learn how to generate
    PDF417 barcode with a custom layout and save it as PNG.
  name: How to create barcode image with PDF417 in C# – step‑by‑step guide
  steps:
  - name: Why this code works
    text: '* **`BarcodeGenerator`** is the entry point for all barcode types. By passing
      `EncodeTypes.Pdf417` you tell the library to produce a PDF417 symbol. * **Columns
      and rows** are the primary levers for layout. Fewer columns produce a taller
      barcode; more columns make it wider. Adjust these values to fit'
  - name: Adjusting data length
    text: 'PDF417 can encode up to 1,850 characters. If you need to encode longer
      strings, consider splitting the data across multiple barcodes or using the **compact
      mode**:'
  - name: Controlling image size
    text: 'The default image size is calculated from the module size (the smallest
      square in the barcode). You can explicitly set the DPI or scale the image after
      generation:'
  - name: Handling special characters
    text: 'PDF417 supports the full ASCII set. If your data contains Unicode characters,
      ensure you encode the string as UTF‑8:'
  type: HowTo
tags:
- barcode
- PDF417
- C#
title: Как создать изображение штрихкода PDF417 на C# – пошаговое руководство
url: /ru/net/compact-pdf417-encoding/how-to-create-barcode-image-with-pdf417-in-c-step-by-step-gu/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Как создать изображение штрих‑кода PDF417 в C# – пошаговое руководство

Если вам нужно **создать изображение штрих‑кода** в .NET‑приложении, это руководство покажет, **как сгенерировать штрих‑код PDF417** с пользовательским макетом и сохранить его в файл PNG. Вы увидите полностью готовый, исполняемый код, поймёте, почему важна каждая настройка, и узнаете о типичных подводных камнях, чтобы ваш штрих‑код надёжно работал в продакшене.

В этом уроке вы:

* Инициализируете генератор Aspose.BarCode для PDF417.
* Настроите количество столбцов и строк, чтобы управлять формой штрих‑кода.
* Экспортируете результат в высококачественное PNG‑изображение.
* Исследуете дополнительные параметры для коррекции ошибок и длины данных.

Единственное требование — актуальный .NET SDK (.NET 6 или новее) и лицензия или бесплатный пробный период **Aspose.BarCode for .NET**.

---

## Требования и настройка

Прежде чем начать, убедитесь, что у вас есть:

| Требование | Почему это важно |
|------------|-------------------|
| .NET 6 SDK или новее | Предоставляет среду выполнения для консольного приложения C#. |
| Visual Studio 2022 (или VS Code) | Позволяет работать в IDE с IntelliSense для API Aspose. |
| NuGet‑пакет Aspose.BarCode for .NET | Содержит `BarcodeGenerator`, `EncodeTypes` и вспомогательные функции экспорта изображений. |
| Права записи в папку вывода | Генератор записывает PNG‑файл на диск. |

Добавить NuGet‑пакет можно следующей командой:

```bash
dotnet add package Aspose.BarCode
```

---

## Шаг 1: Создать новый консольный проект

Сначала создайте простой консольный проект, в котором будет размещена логика генерации штрих‑кода.

```csharp
using System;
using Aspose.BarCode.Generation;

namespace Pdf417Demo
{
    class Program
    {
        static void Main(string[] args)
        {
            // The full barcode generation flow is encapsulated in GeneratePdf417().
            GeneratePdf417();
            Console.WriteLine("Barcode image created successfully.");
        }

        // -----------------------------------------------------------------
        // Generates a PDF417 barcode with a custom layout and saves it as PNG.
        // -----------------------------------------------------------------
        static void GeneratePdf417()
        {
            // -------------------------------------------------------------
            // Step 2: Initialize the barcode generator for PDF417 with text.
            // -------------------------------------------------------------
            var generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Sample data for PDF417 barcode");

            // -------------------------------------------------------------
            // Step 3: Define a custom layout – set the number of columns and rows.
            // -------------------------------------------------------------
            generator.Parameters.Barcode.Pdf417.Columns = 4; // Controls horizontal density.
            generator.Parameters.Barcode.Pdf417.Rows = 9;    // Controls vertical density.

            // Optional: increase error correction level for noisy environments.
            // Values: 0 (no correction) to 8 (maximum correction).
            generator.Parameters.Barcode.Pdf417.ErrorCorrectionLevel = 2;

            // -------------------------------------------------------------
            // Step 4: Save the generated barcode as a PNG image.
            // -------------------------------------------------------------
            string outputPath = System.IO.Path.Combine(
                Environment.CurrentDirectory, "CustomPdf417.png");
            generator.Save(outputPath, BarCodeImageFormat.Png);
        }
    }
}
```

### Почему этот код работает

* **`BarcodeGenerator`** — точка входа для всех типов штрих‑кодов. Передавая `EncodeTypes.Pdf417`, вы указываете библиотеке создавать символ PDF417.
* **Столбцы и строки** — основные рычаги для макета. Меньшее количество столбцов делает штрих‑код выше; больше столбцов — шире. Подгоняйте эти значения под пространство, где будет отображаться изображение (например, принтер этикеток vs. веб‑страница).
* **Коррекция ошибок** повышает надёжность считывания, когда штрих‑код может быть размазан или напечатан на низкокачественном носителе. Уровень по умолчанию — 0; небольшое увеличение (2–4) обеспечивает хороший компромисс между размером и устойчивостью.
* **`Save`** записывает изображение на диск в формате PNG, который сохраняет чёткие границы и работает во всех браузерах и мобильных устройствах.

При запуске программы (`dotnet run`) будет создан файл `CustomPdf417.png` в папке проекта. PNG выглядит так:

![Сгенерированное изображение штрих‑кода PDF417](https://example.com/images/pdf417-sample.png "Скриншот сгенерированного изображения штрих‑кода, созданного с помощью PDF417 в C#")

*Alt text:* **create barcode image** – штрих‑код PDF417, сгенерированный в C# и сохранённый как PNG.

---

## Шаг 2: Тонкая настройка штрих‑кода для реальных сценариев

### Регулировка длины данных

PDF417 может кодировать до 1 850 символов. Если нужно закодировать более длинные строки, рассмотрите разбивку данных на несколько штрих‑кодов или использование **компактного режима**:

```csharp
generator.Parameters.Barcode.Pdf417.CompactMode = true;
```

Компактный режим уменьшает количество строк, но может увеличить визуальную плотность, поэтому протестируйте его со своим сканером.

### Управление размером изображения

Размер изображения по умолчанию рассчитывается из размера модуля (самый маленький квадрат в штрих‑коде). Вы можете явно задать DPI или масштабировать изображение после генерации:

```csharp
generator.Parameters.ImageResolution = new Resolution(300); // 300 DPI for printing.
```

Или, после сохранения, изменить размер с помощью `System.Drawing`, если нужен миниатюрный вариант.

### Обработка специальных символов

PDF417 поддерживает полный набор ASCII. Если ваши данные содержат Unicode‑символы, убедитесь, что строка кодируется как UTF‑8:

```csharp
var generator = new BarcodeGenerator(EncodeTypes.Pdf417, System.Text.Encoding.UTF8.GetString(bytes));
```

---

## Шаг 3: Типичные подводные камни и как их избежать

| Проблема | Симптом | Решение |
|----------|----------|----------|
| Слишком много столбцов для заданных данных | Штрих‑код обрезается или бросает исключение. | Уменьшите `Columns` или позвольте библиотеке автоматически подобрать размер, убрав эту настройку. |
| Низкий уровень коррекции ошибок на шумном принтере | Сканеры периодически не читают штрих‑код. | Увеличьте `ErrorCorrectionLevel` минимум до 2. |
| Сохранение в каталог только для чтения | `UnauthorizedAccessException` во время выполнения. | Используйте записываемую папку, например `Environment.CurrentDirectory` или `Path.GetTempPath()`. |
| Используется устаревшая версия Aspose.BarCode | Отсутствуют свойства, такие как `CompactMode`. | Обновите NuGet‑пакет до последней стабильной версии. |

---

## Шаг 4: Проверка результата

Чтобы убедиться, что штрих‑код сгенерирован правильно, можно:

1. Открыть `CustomPdf417.png` в любом просмотрщике изображений — штрих‑код должен быть чётким, с чёрными модулями на белом фоне.
2. Воспользоваться бесплатным приложением‑сканером PDF417 (доступно для iOS и Android) и отсканировать изображение. Приложение должно отобразить **«Sample data for PDF417 barcode»**.
3. (Опционально) Загрузить изображение в модуль тестов с помощью `System.Drawing.Bitmap` и проверить, что пиксель в координате `(0,0)` чёрный, подтверждая, что изображение не пустое.

```csharp
using System.Drawing;

Bitmap bmp = new Bitmap("CustomPdf417.png");
bool topLeftIsBlack = bmp.GetPixel(0, 0).R == 0;
Console.WriteLine($"Top‑left pixel black? {topLeftIsBlack}");
```

Если проверка проходит, вы успешно **create barcode image** и **generate PDF417 barcode** программно.

---

## Заключение

Теперь вы знаете, как **create barcode image** в C# путем **generating PDF417 barcode** с пользовательским макетом, настройкой коррекции ошибок и экспортом в PNG. Полный пример демонстрирует каждый необходимый шаг — от инициализации `BarcodeGenerator` до сохранения финального изображения — чтобы вы могли скопировать, вставить и запустить его в своём проекте.

Дальше вы можете изучить:

* **Встраивание PNG в веб‑API**, чтобы клиенты могли запрашивать штрих‑коды по требованию (`generate pdf417` как сервис).
* **Пакетную генерацию** для больших наборов данных — циклически обрабатывать список строк и сохранять каждый PNG в базе данных.
* **Альтернативные форматы вывода** (SVG, JPEG), изменив `BarCodeImageFormat`.

Экспериментируйте с соотношением столбцов/строк, уровнями коррекции ошибок и разрешением изображения, чтобы точно соответствовать требованиям вашего сканера или дизайна UI. Приятного кодинга!

## Что изучать дальше?

Следующие руководства охватывают смежные темы, построенные на техниках, продемонстрированных в этом гайде. Каждый ресурс содержит полностью рабочие примеры кода с пошаговыми объяснениями, помогающими освоить дополнительные возможности API и исследовать альтернативные подходы в ваших проектах.

- [Как создать изображение штрих‑кода PDF417 в C# – полное руководство](/barcode/english/net/compact-pdf417-encoding/generate-pdf417-barcode-in-c-complete-guide/)
- [Как создать изображение штрих‑кода PDF417 в C# с опциями Macro PDF417](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-image-in-c-with-macro-pdf417-op/)
- [Как создать микро‑PDF417 штрих‑код и сгенерировать PNG в C#](/barcode/english/net/compact-pdf417-encoding/how-to-create-micro-pdf417-barcode-and-generate-png-in-c/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}