---
category: general
date: 2026-11-17
description: Узнайте, как генерировать штрих‑код PDF417, задавать его размер и выводить
  в виде изображения с помощью C#. Полное пошаговое руководство.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate PDF417 barcode
- how to generate PDF417
- render barcode to image
- how to set barcode size
language: ru
lastmod: 2026-11-17
og_description: Создайте штрих‑код PDF417 на C# и отобразите его в виде изображения.
  Следуйте этому руководству, чтобы задать размер штрих‑кода и сохранить файл PNG.
og_image_alt: Screenshot of a generated PDF417 barcode saved as a PNG image
og_title: Создание штрихкода PDF417 и вывод в PNG – руководство по C#
schemas:
- author: Aspose
  dateModified: '2026-11-17'
  description: Learn how to generate PDF417 barcode, set barcode size, and render
    barcode to image using C#. Complete step‑by‑step guide.
  headline: How to generate PDF417 barcode and render it as PNG
  type: TechArticle
- description: Learn how to generate PDF417 barcode, set barcode size, and render
    barcode to image using C#. Complete step‑by‑step guide.
  name: How to generate PDF417 barcode and render it as PNG
  steps:
  - name: Open the PNG file in any image viewer.
    text: Open the PNG file in any image viewer.
  - name: Use a smartphone barcode scanning app that supports PDF417 (e.g., Google
      Lens, QR & Barcode Scanner).
    text: Use a smartphone barcode scanning app that supports PDF417 (e.g., Google
      Lens, QR & Barcode Scanner).
  - name: Scan the image; the app should return the text *Layout demo*.
    text: Scan the image; the app should return the text *Layout demo*.
  type: HowTo
tags:
- barcode
- PDF417
- C#
- image generation
title: Как сгенерировать штрих‑код PDF417 и отобразить его в формате PNG
url: /ru/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-and-render-it-as-png/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Как сгенерировать штрих‑код PDF417 и отобразить его как PNG

Если вам нужно **сгенерировать штрих‑код PDF417** в приложении .NET, этот учебник покажет вам, как это сделать. Вы увидите, как задать размер штрих‑кода, настроить макет и **отобразить штрих‑код в изображении** всего несколькими строками кода C#.

Генерация штрих‑кода PDF417 часто используется, когда необходимо закодировать большие объёмы данных для сканирования мобильными устройствами или принтерами. К концу этого руководства у вас будет готовый PNG‑файл, который можно вставлять в отчёты, электронные письма или веб‑страницы.

## Предварительные требования

Перед началом убедитесь, что у вас есть:

- .NET 6.0 SDK или более поздняя версия, установленная  
- IDE для C#, например Visual Studio 2022 (подойдёт любой редактор)  
- NuGet‑пакет **Aspose.BarCode for .NET** (или любая совместимая библиотека, предоставляющая `BarcodeGenerator`)  

Вы можете добавить пакет с помощью:

```bash
dotnet add package Aspose.BarCode
```

## Шаг 1: Создать консольный проект C#

Сначала создайте минимальное консольное приложение, которое будет содержать код генерации штрих‑кода.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace Pdf417Demo
{
    class Program
    {
        static void Main(string[] args)
        {
            // The barcode generation logic will be placed here.
        }
    }
}
```

> **Совет:** Держите метод `Main` коротким и делегируйте тяжелую работу вспомогательным методам. Это улучшает читаемость и упрощает модульное тестирование.

## Шаг 2: Сгенерировать штрих‑код PDF417 с пользовательским размером

Теперь мы **сгенерируем штрих‑код PDF417** и укажем размер модуля (X‑dimension). X‑dimension определяет ширину каждого крошечного квадратика штрих‑кода, фактически задавая общий размер штрих‑кода.

```csharp
static void GeneratePdf417(string text, string outputPath)
{
    // Initialize a PDF417 barcode generator with the desired text
    BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, text);

    // Set the size of a single barcode module (X‑dimension) in pixels
    generator.Parameters.Barcode.XDimension.Pixels = 2; // 2 px per module

    // Optional: adjust the number of columns and rows for layout control
    generator.Parameters.Barcode.Pdf417.Columns = 4;   // 4 columns
    generator.Parameters.Barcode.Pdf417.Rows    = 9;   // 9 rows

    // Render the barcode and save it as a PNG image
    generator.Save(outputPath, BarCodeImageFormat.Png);
}
```

### Почему важно задавать X‑dimension?

Шаг **как задать размер штрих‑кода** важен, потому что слишком маленькая X‑dimension может сделать штрих‑код нечитаемым для сканеров с низким разрешением, а слишком большая — будет занимать лишнее пространство. Значение `2` пикселя обычно хорошо подходит для большинства экранов и печати.

## Шаг 3: Вызвать метод генерации из `Main`

Объедините всё, вызвав `GeneratePdf417` с нужным текстом и путём сохранения.

```csharp
static void Main(string[] args)
{
    string barcodeText = "Layout demo";
    string outputFile = @"C:\Barcodes\LayoutPdf417.png";

    GeneratePdf417(barcodeText, outputFile);

    Console.WriteLine($"PDF417 barcode saved to {outputFile}");
}
```

Запуск программы создаёт файл `LayoutPdf417.png`, содержащий штрих‑код:

![Сгенерированный штрих‑код PDF417](/images/layout-pdf417.png "Штрих‑код PDF417, сгенерированный кодом учебника"){: .align-center alt="Сгенерированный штрих‑код PDF417, сохранённый как PNG"}

> **Ожидаемый результат:** PNG‑файл размером примерно 200 × 100 px (в зависимости от настроек столбцов/строк), отображающий чёткий шаблон PDF417, готовый к сканированию.

## Шаг 4: Проверить работоспособность штрих‑кода

Чтобы убедиться, что штрих‑код корректен:

1. Откройте PNG‑файл в любом просмотрщике изображений.  
2. Используйте приложение для сканирования штрих‑кодов на смартфоне, поддерживающее PDF417 (например, Google Lens, QR & Barcode Scanner).  
3. Отсканируйте изображение; приложение должно вернуть текст *Layout demo*.

Если сканирование не удалось, проверьте X‑dimension и значения столбцов/строк — более крупные модули повышают читаемость на камерах с низким разрешением.

## Общие варианты и граничные случаи

| Сценарий | Корректировка |
|----------|----------------|
| **Больше данных** (например, URL) | Увеличьте `Columns` или `Rows`, чтобы разместить дополнительные codewords. |
| **Печать с высоким разрешением** | Установите `XDimension.Pixels` в 3‑4 px для более чётких полос. |
| **Прозрачный фон** | Используйте `generator.Save(outputPath, BarCodeImageFormat.Png, new ImageOptions { BackgroundColor = Color.Transparent })`. |
| **Другой формат изображения** | Замените `BarCodeImageFormat.Png` на `Jpeg` или `Bmp` по необходимости. |

Эти варианты отвечают на вопрос **как сгенерировать PDF417** для разных требований, при этом сохраняют основную логику без изменений.

## Заключение

Теперь вы знаете, как **сгенерировать штрих‑код PDF417**, **задать размер штрих‑кода** и **отобразить штрих‑код в изображении** с помощью C#. Полный, готовый к запуску пример создаёт PNG‑файл, который можно вставлять в любые места, где нужен машинно‑читаемый штрих‑код.

Далее изучайте связанные темы, такие как **встраивание PNG в PDF** (поиск по *render barcode to PDF*), или **генерацию других 2‑D штрих‑кодов**, например QR‑кодов. Настраивайте параметры макета под дизайн вашего UI и экспериментируйте с цветовыми опциями для брендинга.

Удачной разработки, и пусть ваши штрих‑коды делают тяжёлую работу за вас!

## Что изучать дальше?

Следующие учебники охватывают тесно связанные темы, расширяющие техники, продемонстрированные в этом руководстве. Каждый ресурс содержит полностью работающие примеры кода с пошаговыми объяснениями, помогающими освоить дополнительные возможности API и исследовать альтернативные подходы в ваших проектах.

- [Как сгенерировать штрих‑код PDF417 в C# – полное пошаговое руководство](/barcode/english/net/compact-pdf417-encoding/generate-pdf417-barcode-in-c-complete-step-by-step-guide/)
- [Как сгенерировать микроштрих‑код PDF417 в C# – пошаговое руководство](/barcode/english/net/compact-pdf417-encoding/how-to-generate-micro-pdf417-barcode-in-c-step-by-step-guide/)
- [Как установить уровень ошибки в штрих‑коде PDF417 – полное руководство](/barcode/english/net/compact-pdf417-encoding/how-to-set-error-level-in-pdf417-barcode-complete-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}