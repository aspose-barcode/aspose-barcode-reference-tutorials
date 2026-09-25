---
category: general
date: 2026-08-22
description: Узнайте, как создать микробаркод micro PDF417 на C# и сгенерировать PNG‑изображение
  штрихкода. Включает настройку размеров штрихкода и сохранение файла.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create micro pdf417 barcode
- how to generate barcode png
- create barcode image c#
- how to set barcode dimensions
language: ru
lastmod: 2026-08-22
og_description: Создайте микробаркод PDF417 на C# и экспортируйте его в PNG. Следуйте
  этому руководству, чтобы задать размеры штрихкода и быстро сгенерировать его изображение.
og_image_alt: Screenshot of a micro PDF417 barcode generated with C# code
og_title: Создание микроштрихкода PDF417 в C# – полный учебник по программированию
schemas:
- author: Aspose
  dateModified: '2026-08-22'
  description: Learn how to create micro PDF417 barcode in C# and generate a barcode
    PNG image. Includes setting barcode dimensions and saving the file.
  headline: How to create micro PDF417 barcode in C# – step‑by‑step guide
  type: TechArticle
- description: Learn how to create micro PDF417 barcode in C# and generate a barcode
    PNG image. Includes setting barcode dimensions and saving the file.
  name: How to create micro PDF417 barcode in C# – step‑by‑step guide
  steps:
  - name: 'Build the project: `dotnet build`.'
    text: 'Build the project: `dotnet build`.'
  - name: 'Execute: `dotnet run`.'
    text: 'Execute: `dotnet run`.'
  - name: Open `MicroPdf417.png` on your desktop and scan it with a mobile barcode
      scanner app.
    text: Open `MicroPdf417.png` on your desktop and scan it with a mobile barcode
      scanner app.
  type: HowTo
tags:
- barcode
- C#
- MicroPdf417
- image generation
title: Как создать микроштрих‑код PDF417 в C# — пошаговое руководство
url: /ru/net/compact-pdf417-encoding/how-to-create-micro-pdf417-barcode-in-c-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Как создать микробаркод Micro PDF417 в C# – пошаговое руководство

Если вам нужно **создать микробаркод Micro PDF417** для системы билетов, этикетки инвентаря или мобильного сканирования, это руководство покажет, как это сделать. Вы увидите полностью готовую программу на C#, генерирующую PNG‑изображение баркода, узнаете, как задавать размеры баркода, и поймёте каждую опцию конфигурации.

К концу этого руководства вы сможете генерировать изображение баркода высокого разрешения, настраивать X‑размер, выбирать количество столбцов и сохранять результат в файл PNG — всё это несколькими строками кода.

## Что понадобится

- .NET 6.0 SDK или новее (код работает с .NET Core и .NET Framework)
- Visual Studio 2022 или любой IDE, поддерживающий C#
- NuGet‑пакет **Aspose.BarCode for .NET** (или любая библиотека, поддерживающая `EncodeTypes.MicroPdf417`)
- Базовые знания синтаксиса C#

> **Pro tip:** Бесплатная community‑версия Aspose.BarCode достаточно для разработки и тестирования. Для продакшна получите лицензию, чтобы убрать водяные знаки оценки.

## Шаг 1: Установите библиотеку баркодов

Откройте терминал в папке проекта и выполните:

```bash
dotnet add package Aspose.BarCode
```

Это добавит сборку `Aspose.BarCode`, предоставляющую класс `BarcodeGenerator`, используемый для **создания изображений баркодов C#**.

## Шаг 2: Инициализируйте генератор – создайте микробаркод Micro PDF417

Первая исполняемая строка создаёт экземпляр `BarcodeGenerator`, настроенный для символьного набора Micro PDF417, и передаёт данные, которые нужно закодировать.

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        // Step 2: Initialize a Micro PDF417 barcode generator with the data to encode
        BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MicroPdf417, "Sample text");
```

*Почему это важно*: Перечисление `EncodeTypes.MicroPdf417` указывает библиотеке использовать компактную версию PDF417, что идеально подходит для небольших этикеток и мобильных экранов.

## Шаг 3: Как задать размеры баркода в C#

Точная настройка ширины модуля (X‑размер) контролирует визуальную плотность баркода. Меньшее значение даёт более чёткое изображение, большее — упрощает сканирование с расстояния.

```csharp
        // Step 3: Set the X‑dimension (module width) to 2 pixels for finer resolution
        generator.Parameters.Barcode.XDimension.Pixels = 2;
```

> **Почему стоит задавать размеры**: Без изменения X‑размера значение по умолчанию может привести к размытости баркода при рендеринге с высоким DPI. Установка в 2 пикселя — хороший компромисс для большинства сканирований с экрана.

## Шаг 4: Выбор количества столбцов – управление шириной баркода

Micro PDF417 допускает от 1 до 4 столбцов. Большее количество столбцов сжимает данные по горизонтали, уменьшая общую ширину изображения.

```csharp
        // Step 4: Define the number of columns (allowed values: 1‑4)
        generator.Parameters.Barcode.Pdf417.Columns = 4;
```

*Особый случай*: При запросе 5 столбцов библиотека бросит `ArgumentOutOfRangeException`. Всегда оставайтесь в пределах документированного диапазона.

## Шаг 5: Как сгенерировать PNG‑баркод – сохранение изображения

Теперь можно экспортировать сгенерированный баркод в файл PNG. PNG сохраняет качество без потерь, что критично для надёжного сканирования.

```csharp
        // Step 5: Save the generated barcode as a PNG image
        string outputPath = Path.Combine(
            Environment.GetFolderPath(Environment.SpecialFolder.Desktop),
            "MicroPdf417.png");
        generator.Save(outputPath, BarCodeImageFormat.Png);
        Console.WriteLine($"Barcode saved to {outputPath}");
    }
}
```

При запуске программы в консоли появится сообщение, подтверждающее путь к файлу. Полученный `MicroPdf417.png` выглядит так:

![Скриншот, показывающий сгенерированный микробаркод Micro PDF417, созданный с помощью C#](micro-pdf417-example.png "Сгенерированный микробаркод Micro PDF417")

*Текст альтернативы изображения*: **микробаркод micro PDF417, сгенерированный в C#** – демонстрирует окончательный результат после применения размеров и настроек столбцов.

## Шаг 6: Запустите и проверьте результат

1. Сборка проекта: `dotnet build`.
2. Выполнение: `dotnet run`.
3. Откройте `MicroPdf417.png` на рабочем столе и отсканируйте его мобильным приложением‑сканером баркодов.

Вы должны увидеть декодированный текст **«Sample text»**. Если сканер выдаёт ошибку, проверьте X‑размер и количество столбцов — экстремальные значения могут сделать баркод слишком плотным для некоторых устройств.

## Распространённые варианты и устранение неполадок

| Ситуация | Корректировка |
|-----------|------------|
| **Нужен более крупный баркод для принтеров низкого разрешения** | Увеличьте `XDimension.Pixels` до 3 или 4. |
| **Хотите более высокий баркод без изменения ширины** | Установите `generator.Parameters.Barcode.Pdf417.Rows` (диапазон строк 3‑90). |
| **Генерация нескольких баркодов в цикле** | Переиспользуйте один экземпляр `BarcodeGenerator` и меняйте только `CodeText` перед каждым `Save`. |
| **Сохранение в JPEG вместо PNG** | Замените `BarCodeImageFormat.Png` на `BarCodeImageFormat.Jpeg`. |
| **Запуск на .NET Framework 4.7** | Тот же код работает; просто подключите соответствующий `Aspose.BarCode.dll`. |

## Полный листинг исходного кода (рабочий)

```csharp
using System;
using System.IO;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace MicroPdf417Demo
{
    class Program
    {
        static void Main()
        {
            // Initialize a Micro PDF417 barcode generator with the data to encode
            BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MicroPdf417, "Sample text");

            // Set the X‑dimension (module width) to 2 pixels for finer resolution
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // Define the number of columns (allowed values: 1‑4)
            generator.Parameters.Barcode.Pdf417.Columns = 4;

            // Save the generated barcode as a PNG image
            string outputPath = Path.Combine(
                Environment.GetFolderPath(Environment.SpecialFolder.Desktop),
                "MicroPdf417.png");
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"Barcode saved to {outputPath}");
        }
    }
}
```

**Ожидаемый результат** – PNG‑файл размером 200 × 100 пикселей с чётким микробаркодом Micro PDF417, который декодируется как «Sample text».

## Заключение

Теперь вы знаете, как **создать микробаркод Micro PDF417 в C#**, **задать размеры баркода** и **сгенерировать PNG‑изображение баркода**. Полный пример демонстрирует каждый необходимый шаг — от установки библиотеки до сохранения финального файла — чтобы вы могли встроить генерацию баркодов непосредственно в свои приложения.

Далее изучайте связанные темы, такие как **создание QR‑кодов с Aspose.BarCode**, **настройка цветов** или **встраивание баркодов в PDF‑документы**. Все они опираются на те же фундаментальные возможности `BarcodeGenerator`, рассмотренные здесь.

Экспериментируйте с различными строками данных, количеством столбцов и значениями X‑размера, подбирая оптимальные параметры под вашу среду сканирования. Приятного кодинга!

## Что изучать дальше?

Следующие руководства охватывают тесно связанные темы, которые развивают техники, продемонстрированные в этом руководстве. Каждый ресурс содержит полностью работающие примеры кода с пошаговыми объяснениями, помогающими освоить дополнительные возможности API и исследовать альтернативные подходы в ваших проектах.

- [How to Create Barcode – Compact PDF417 with Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [How to Generate PDF417 Barcode – Compact PDF417 Encoding](/barcode/english/net/compact-pdf417-encoding/)
- [How to create Aztec barcode with Aspose.BarCode for .NET](/barcode/english/net/aztec-barcode-encoding/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}