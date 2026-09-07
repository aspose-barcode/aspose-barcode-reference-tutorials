---
category: general
date: 2026-09-07
description: Узнайте, как создать изображение штрихкода в C# и настроить его высоту,
  ширину и формат, чтобы быстро генерировать PNG‑файлы штрихкода.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode image
- how to set barcode
- how to adjust barcode
- generate barcode png
- change barcode height
language: ru
lastmod: 2026-09-07
og_description: Создайте изображение штрихкода на C# и узнайте, как задать размеры
  штрихкода, изменить его высоту и генерировать PNG‑файлы штрихкода для любого приложения.
og_image_alt: C# generated barcode image saved as PNG with custom height
og_title: Создание изображения штрих‑кода в C# — пошаговое руководство
schemas:
- author: Aspose
  dateModified: '2026-09-07'
  description: Learn how to create barcode image in C# and adjust its height, width,
    and format to generate barcode PNG files quickly.
  headline: How to create barcode image in C# with adjustable height
  type: TechArticle
- description: Learn how to create barcode image in C# and adjust its height, width,
    and format to generate barcode PNG files quickly.
  name: How to create barcode image in C# with adjustable height
  steps:
  - name: 3.1 Adjust the narrow bar width (X‑dimension)
    text: The X‑dimension controls the thickness of the thinnest bar. A value of **2
      pixels** yields a finer appearance, useful when you need a compact label.
  - name: 3.2 Change barcode height for visual balance
    text: Bar height determines how tall the barcode appears. Below we show two common
      heights—30 pixels for a small label and 60 pixels for a larger visual. This
      demonstrates **how to adjust barcode** height programmatically.
  - name: 4.1 Save the first image (30 px height)
    text: '```csharp // Save a 30‑pixel‑high barcode as PNG generator.Save("DatabarBarHeight30Pixels.png",
      BarCodeImageFormat.Png); ```'
  - name: 4.2 Increase the height and save a second image
    text: '```csharp // Increase height to 60 pixels for a larger visual generator.Parameters.Barcode.BarHeight.Pixels
      = 60;'
  type: HowTo
tags:
- barcode
- C#
- image generation
title: Как создать изображение штрихкода в C# с регулируемой высотой
url: /ru/python-java/general/how-to-create-barcode-image-in-c-with-adjustable-height/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Как создать изображение штрих‑кода в C# с регулируемой высотой

Если вам нужно создать изображение штрих‑кода в C# для системы точек продаж или учёта запасов, это руководство покажет полный рабочий процесс. Вы увидите, как задать параметры штрих‑кода, изменить его высоту и сгенерировать PNG‑файлы штрих‑кода, соответствующие визуальным требованиям.

Создание изображения штрих‑кода — распространённая задача при интеграции сканирующего оборудования, печати этикеток или построении панелей отчётов. К концу этого урока у вас будет переиспользуемый фрагмент кода, позволяющий регулировать X‑размер, высоту и формат вывода штрих‑кода, не покидая IDE.

## Требования

Прежде чем начать, убедитесь, что у вас есть:

* .NET 6.0 (или новее) — код компилируется любой современной .NET SDK.
* Ссылка на библиотеку **Aspose.BarCode** (доступно через NuGet `Aspose.BarCode`).
* Базовое знакомство с консольными приложениями C#.

Эти требования гарантируют, что пример будет работать «из коробки» на Windows, Linux или macOS.

## Шаг 1: Создание проекта и импорт библиотеки

Создайте новый консольный проект и добавьте пакет штрих‑кода:

```bash
dotnet new console -n BarcodeDemo
cd BarcodeDemo
dotnet add package Aspose.BarCode
```

Теперь откройте *Program.cs* и добавьте необходимые директивы `using`:

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode.Encoding;
using Aspose.BarCode;
```

Эти импорты дают доступ к `BarcodeGenerator`, `EncodeTypes` и перечислениям форматов изображений, необходимым для **создания изображения штрих‑кода**.

## Шаг 2: Инициализация генератора с нужной символьностью

Первая строка кода создаёт `BarcodeGenerator`, который знает, какой тип штрих‑кода кодировать. В этом примере мы используем символьность DataBar Omni‑Directional, но вы можете заменить `EncodeTypes.DatabarOmniDirectional` любой другой поддерживаемой Aspose.BarCode.

```csharp
// Initialize a generator for a DataBar Omni‑Directional barcode
var generator = new BarcodeGenerator(
    EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");
```

Строка `"(01)12345678901231"` следует формату GS1 Application Identifier, требуемому многими розничными сетями. Инициализация генератора — фундамент для любой последующей **операции по настройке штрих‑кода**.

## Шаг 3: Как задать размеры штрих‑кода — X‑размер и высоту

### 3.1 Регулировка ширины узкой полосы (X‑размер)

X‑размер контролирует толщину самой тонкой полосы. Значение **2 пикселя** даёт более тонкое изображение, полезное для компактных этикеток.

```csharp
// Set the narrow bar width to 2 pixels
generator.Parameters.Barcode.XDimension.Pixels = 2;
```

### 3.2 Изменение высоты штрих‑кода для визуального баланса

Высота определяет, насколько «высоким» будет штрих‑код. Ниже показаны два типичных варианта — 30 пикселей для небольшой этикетки и 60 пикселей для более крупного изображения. Это демонстрирует **как программно регулировать высоту штрих‑кода**.

```csharp
// Height 30 pixels – suitable for compact labels
generator.Parameters.Barcode.BarHeight.Pixels = 30;
```

## Шаг 4: Генерация PNG‑файлов штрих‑кода с разными высотами

### 4.1 Сохранение первого изображения (высота 30 px)

```csharp
// Save a 30‑pixel‑high barcode as PNG
generator.Save("DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);
```

### 4.2 Увеличение высоты и сохранение второго изображения

```csharp
// Increase height to 60 pixels for a larger visual
generator.Parameters.Barcode.BarHeight.Pixels = 60;

// Save a 60‑pixel‑high barcode as PNG
generator.Save("DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);
```

Эти два вызова `Save` показывают **генерацию PNG‑файлов штрих‑кода** с различными размерами, используя один и тот же экземпляр генератора. Формат изображения явно установлен как PNG, что сохраняет без потерь качество — идеально для печати или отображения на экране.

## Шаг 5: Полный, готовый к запуску пример

Объединив всё вместе, получаем один метод `Main`, который можно скопировать в любой консольный проект C#:

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode.Encoding;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        // 1️⃣ Create a DataBar Omni‑Directional barcode generator
        var generator = new BarcodeGenerator(
            EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");

        // 2️⃣ Set the narrow bar width (X‑dimension) to 2 pixels
        generator.Parameters.Barcode.XDimension.Pixels = 2;

        // 3️⃣ Create a 30‑pixel‑high barcode and save it as PNG
        generator.Parameters.Barcode.BarHeight.Pixels = 30;
        generator.Save("DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved 30‑pixel barcode as DatabarBarHeight30Pixels.png");

        // 4️⃣ Change barcode height to 60 pixels and save again
        generator.Parameters.Barcode.BarHeight.Pixels = 60;
        generator.Save("DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved 60‑pixel barcode as DatabarBarHeight60Pixels.png");
    }
}
```

Запуск этой программы создаст два PNG‑файла в папке вывода проекта:

* `DatabarBarHeight30Pixels.png` — компактный штрих‑код высотой 30 px.
* `DatabarBarHeight60Pixels.png` — более крупный штрих‑код высотой 60 px.

Оба файла содержат **созданное изображение штрих‑кода**, которое можно встроить в HTML, напечатать на этикетках или отправить в мобильное приложение для сканирования.

## Часто задаваемые вопросы и обработка граничных случаев

| Вопрос | Ответ |
|----------|--------|
| **Что делать, если нужен другой формат изображения?** | Замените `BarCodeImageFormat.Png` на `BarCodeImageFormat.Jpeg`, `Bmp` или `Gif`. Библиотека автоматически выполнит конвертацию. |
| **Можно ли изменить цвета переднего/фонового плана?** | Да. Используйте `generator.Parameters.Barcode.ForeColor` и `BackColor`, задав значения `System.Drawing.Color` перед вызовом `Save`. |
| **Как сгенерировать штрих‑код без записи в файл?** | Вызовите `generator.GenerateBarCodeImage()`, чтобы получить объект `System.Drawing.Image`, затем передайте его напрямую в ответ или в базу данных. |
| **Что если строка данных превышает лимит символьности?** | Генератор бросит `ArgumentException`. Проверьте длину входных данных или обрежьте её согласно спецификации символьности. |
| **Есть ли способ пакетной обработки нескольких штрих‑кодов?** | Оберните шаги в цикл `foreach`, обновляя `generator.CodeText` и `BarHeight` для каждого элемента, затем вызывайте `Save` с уникальным именем файла. |

Учёт этих сценариев делает логику **регулировки штрих‑кода** надёжной для реальных проектов.

## Профессиональные советы для надёжного создания штрих‑кодов

* **Кешируйте генератор**, если создаёте много штрих‑кодов одного типа; повторное использование объекта снижает нагрузку на выделение памяти.
* **Устанавливайте `Resolution`** (`generator.Parameters.ImageResolution.Dpi`), если нужны PNG‑файлы высокого разрешения для печати.
* **Проверяйте GS1‑данные** перед присвоением их `CodeText`, чтобы избежать ошибок кодирования, которые могут привести к сбоям сканирования.
* **Тестируйте на реальных сканерах** после изменения высоты или X‑размера — некоторые старые устройства требуют минимального размера.

## Заключение

Теперь вы знаете, как **создать изображение штрих‑кода** в C#, **как задать размеры штрих‑кода**, **как регулировать высоту штрих‑кода** и **генерировать PNG‑файлы штрих‑кода** для любых визуальных требований. Регулируя `XDimension` и `BarHeight`, вы можете получать как компактные, так и крупные штрих‑коды без изменения исходных данных.

Далее изучайте связанные темы, такие как **динамическое изменение высоты штрих‑кода** в зависимости от ввода пользователя, встраивание штрих‑кодов в PDF‑отчёты с помощью Aspose.PDF или переход к генерации QR‑кодов через `EncodeTypes.QR`. Экспериментируйте с различными символьностями и форматами вывода, чтобы полностью освоить создание штрих‑кодов в C#.

## Что изучать дальше?

Следующие руководства охватывают тесно связанные темы, расширяющие техники, продемонстрированные в этом руководстве. Каждый ресурс включает полностью работающие примеры кода с пошаговыми объяснениями, помогающими освоить дополнительные возможности API и исследовать альтернативные подходы в ваших проектах.

- [Создание изображений GS1 штрих‑кода в C# – Как быстро генерировать штрих‑код в C#](/barcode/english/net/gs1-barcode-encoding/create-gs1-barcode-images-in-c-how-to-generate-barcode-c-qui/)
- [Как генерировать и регулировать высоту штрих‑кода для одностороннего Databar с помощью Aspose.BarCode для .NET](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-barcode-height-adjustment/)
- [Как создать изображение штрих‑кода в C# – Руководство по MicroPdf417](/barcode/english/net/compact-pdf417-encoding/how-to-generate-barcode-image-in-c-micropdf417-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}