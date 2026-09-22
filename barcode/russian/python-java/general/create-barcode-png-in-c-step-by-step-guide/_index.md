---
category: general
date: 2026-08-03
description: Создайте PNG‑изображение штрихкода на C# и узнайте, как изменить соотношение
  сторон для изображений DataBar. Следуйте этому полному примеру с кодом и советами.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode PNG
- how to change aspect ratio
- Aspose.BarCode C#
- DataBar stacked omnidirectional
- barcode image format PNG
language: ru
lastmod: 2026-08-03
og_description: Создайте PNG‑изображение штрих‑кода на C# и узнайте, как изменить
  соотношение сторон для штрих‑кодов DataBar. Это руководство предоставляет готовый
  к запуску код и практические советы.
og_image_alt: Sample barcode PNG generated with aspect ratio 15
og_title: Создание PNG‑штрихкода в C# – полный пример с контролем соотношения сторон
schemas:
- author: Aspose
  dateModified: '2026-08-03'
  description: Create barcode PNG in C# and learn how to change aspect ratio for DataBar
    images. Follow this complete example with code and tips.
  headline: Create barcode PNG in C# – step‑by‑step guide
  type: TechArticle
- description: Create barcode PNG in C# and learn how to change aspect ratio for DataBar
    images. Follow this complete example with code and tips.
  name: Create barcode PNG in C# – step‑by‑step guide
  steps:
  - name: How to change other visual properties?
    text: 'You can adjust foreground color, background color, or add human‑readable
      text through the `generator.Parameters.Barcode` object. For example:'
  - name: What if I need a different image format?
    text: Replace `BarCodeImageFormat.Png` with `Jpeg`, `Bmp`, or `Gif` as needed.
      PNG remains the best choice for lossless barcode images.
  - name: Does the aspect ratio affect scanning speed?
    text: Higher aspect ratios increase the barcode’s height, which can improve scan
      reliability on devices that struggle with short stacked symbols. However, extremely
      tall barcodes may not fit on small labels, so test with your target hardware.
  - name: Can I generate multiple barcodes in a loop?
    text: Yes. Create a new `BarcodeGenerator` instance for each data string or reuse
      the same instance while updating `CodeText` and `DataBar.AspectRatio`. This
      approach reduces object allocation overhead.
  type: HowTo
tags:
- barcode
- C#
- PNG
- Aspose
title: Создание PNG‑штрихкода в C# – пошаговое руководство
url: /ru/python-java/general/create-barcode-png-in-c-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Создание PNG‑изображения штрих‑кода в C# – пошаговое руководство

Если вам нужно **создать PNG‑изображение штрих‑кода** в C#, это руководство покажет, как это сделать. Вы сгенерируете многослойный всенаправленный DataBar‑штрих‑код, сохраните его в файл PNG и узнаете **как изменить соотношение сторон**, чтобы адаптировать его к различным условиям сканирования.

В руководстве изложены все необходимые шаги: требуемые пакеты, полностью готовая к запуску программа и объяснения, почему каждое из настроек важно. По завершении у вас будет два PNG‑файла — один с соотношением сторон 15, другой 30 — готовые к тестированию или использованию в продакшене.

## Требования

Прежде чем начать, убедитесь, что у вас есть:

- .NET 6.0 SDK или более новая версия
- Visual Studio 2022 (или любая другая IDE для C#)
- NuGet‑ссылка на **Aspose.BarCode** (библиотека, предоставляющая `BarcodeGenerator`)
- Права записи в каталог, куда будут сохраняться PNG‑файлы

Пакет Aspose.BarCode можно добавить следующей командой:

```bash
dotnet add package Aspose.BarCode
```

## Шаг 1: Создание проекта и импорт пространств имён

Создайте новое консольное приложение и импортируйте пространства имён, необходимые для генерации штрих‑кода и работы с файловой системой.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

namespace BarcodePngDemo
{
    class Program
    {
        static void Main()
        {
            // All subsequent steps are inside Main
```

**Почему это важно:** Импорт `Aspose.BarCode.Generation` даёт доступ к `BarcodeGenerator`. Размещение кода внутри `Main` делает пример автономным и простым для запуска.

## Шаг 2: Создание генератора штрих‑кода для многослойного всенаправленного DataBar

Создайте экземпляр `BarcodeGenerator` с типом `EncodeTypes.DatabarStackedOmniDirectional` и примером строки данных GS1‑128.

```csharp
            // Step 2: Create a barcode generator for a stacked omnidirectional DataBar
            BarcodeGenerator generator = new BarcodeGenerator(
                EncodeTypes.DatabarStackedOmniDirectional,
                "(01)12345678901231");
```

**Почему это важно:** Выбранный тип кодирования генерирует высокоплотный DataBar, который может считываться большинством современных сканеров. Строка данных соответствует формату идентификатора GS1 Application Identifier (01), часто используемому для обозначения товаров.

## Шаг 3: Задание X‑размера (ширины модуля) в пикселях

Установите ширину модуля, чтобы контролировать общий размер штрих‑кода без влияния на его читаемость.

```csharp
            // Step 3: Define the X‑dimension (module width) in pixels
            generator.Parameters.Barcode.XDimension.Pixels = 2;
```

**Почему это важно:** X‑размер 2 пикселя даёт штрих‑код, который не слишком мал для сканеров и не слишком велик для типовых этикеток.

## Шаг 4: Сохранение первого PNG с соотношением сторон 15

Отрегулируйте соотношение сторон DataBar, затем сохраните изображение в файл PNG.

```csharp
            // Step 4: Set the DataBar aspect ratio to 15 and save the image
            generator.Parameters.Barcode.DataBar.AspectRatio = 15;
            string outputPath15 = @"YOUR_DIRECTORY\DatabarAspectRatio15.png";
            generator.Save(outputPath15, BarCodeImageFormat.Png);
            Console.WriteLine($"Barcode saved to {outputPath15} (aspect ratio 15).");
```

**Почему это важно:** Соотношение сторон определяет соотношение высоты к ширине у многослойного DataBar. Значение 15 — распространённый параметр по умолчанию, обеспечивающий баланс между читаемостью и высотой этикетки.

## Шаг 5: Изменение соотношения сторон на 30 и сохранение второго PNG

Измените тот же экземпляр генератора, задав более высокое соотношение сторон, затем сохраните второе изображение.

```csharp
            // Step 5: Change the aspect ratio to 30 and save another image
            generator.Parameters.Barcode.DataBar.AspectRatio = 30;
            string outputPath30 = @"YOUR_DIRECTORY\DatabarAspectRatio30.png";
            generator.Save(outputPath30, BarCodeImageFormat.Png);
            Console.WriteLine($"Barcode saved to {outputPath30} (aspect ratio 30).");
        }
    }
}
```

**Почему это важно:** Увеличение соотношения сторон растягивает штрих‑код по вертикали, что может повысить надёжность сканирования на устройствах с низким разрешением или при печати на узких носителях.

## Ожидаемый результат

Запуск программы создаёт два PNG‑файла:

| Файл                               | Соотношение сторон | Приблизительные размеры (пиксели) |
|------------------------------------|--------------------|-----------------------------------|
| `DatabarAspectRatio15.png`         | 15                 | 200 × 300 (ширина × высота)        |
| `DatabarAspectRatio30.png`         | 30                 | 200 × 600 (ширина × высота)        |

Оба изображения содержат чёткий, сканируемый DataBar‑штрих‑код, кодирующий GS1‑идентификатор `(01)12345678901231`.

## Часто задаваемые вопросы и особые случаи

### Как изменить другие визуальные свойства?

Можно настроить цвет переднего плана, цвет фона или добавить человекочитаемый текст через объект `generator.Parameters.Barcode`. Например:

```csharp
generator.Parameters.Barcode.ForeColor = System.Drawing.Color.Black;
generator.Parameters.Barcode.BackColor = System.Drawing.Color.White;
generator.Parameters.Barcode.CodeTextParameters.ShowCodeText = true;
```

### Что делать, если нужен другой формат изображения?

Замените `BarCodeImageFormat.Png` на `Jpeg`, `Bmp` или `Gif` по необходимости. PNG остаётся лучшим выбором для без потерь изображений штрих‑кодов.

### Влияет ли соотношение сторон на скорость сканирования?

Более высокие соотношения увеличивают высоту штрих‑кода, что может улучшить надёжность сканирования на устройствах, испытывающих трудности с короткими многослойными символами. Однако чрезмерно высокие штрих‑коды могут не помещаться на небольших этикетках, поэтому тестируйте их с целевым оборудованием.

### Можно ли генерировать несколько штрих‑кодов в цикле?

Да. Создавайте новый экземпляр `BarcodeGenerator` для каждой строки данных или переиспользуйте один экземпляр, обновляя свойства `CodeText` и `DataBar.AspectRatio`. Такой подход уменьшает накладные расходы на создание объектов.

## Полезные советы

- **Переиспользуйте генератор**: меняя только `CodeText` или `AspectRatio`, вы избегаете повторного создания объекта, что ускоряет пакетную обработку.
- **Проверяйте результат**: используйте ручной сканер или мобильное приложение, чтобы убедиться, что сгенерированный PNG читается корректно перед выпуском в продакшн.
- **Именование файлов**: включайте соотношение сторон в имя файла (как показано), чтобы легко отслеживать варианты во время тестирования.

## Заключение

Теперь вы знаете, как **создавать PNG‑изображения штрих‑кодов** в C# и точно **изменять соотношение сторон** для многослойных всенаправленных DataBar‑символов. Полный пример демонстрирует инициализацию, настройку X‑размера, манипуляцию соотношением сторон и сохранение изображения — всё в одной готовой к запуску программе.

Далее вы можете изучать другие типы штрих‑кодов, экспериментировать с цветами или интегрировать генератор в более крупные системы отчётности или учёта. Приятного кодинга!

## Что изучать дальше?

Следующие руководства охватывают смежные темы, расширяющие техники, продемонстрированные в этом пособии. Каждый ресурс содержит полностью рабочие примеры кода с пошаговыми объяснениями, помогающие освоить дополнительные возможности API и исследовать альтернативные подходы в ваших проектах.

- [Create Barcode PNG – DataMatrix Aspect Ratio – Aspose.BarCode](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-aspect-ratio-customization/)
- [How to generate Aztec barcode with custom aspect ratio using Aspose.BarCode for .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)
- [How to Customize Barcode - Codablock F Aspect Ratio with Aspose.BarCode for .NET](/barcode/english/net/codablock-f-encoding/codablock-f-aspect-ratio-customization/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}