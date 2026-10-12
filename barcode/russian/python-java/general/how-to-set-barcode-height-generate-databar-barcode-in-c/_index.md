---
category: general
date: 2026-10-12
description: Как установить высоту штрих‑кода и сгенерировать DataBar штрих‑код в
  C# с использованием Aspose.BarCode. Следуйте пошаговому руководству с полным кодом.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to set barcode
- generate barcode c#
- how to create databar
- create databar barcode
- change barcode height
language: ru
lastmod: 2026-10-12
og_description: Как установить высоту штрихкода в C# и сгенерировать DataBar штрихкод
  с помощью Aspose.BarCode. Узнайте полный код, почему каждый шаг важен, и как изменить
  высоту штрихкода.
og_image_alt: Screenshot showing how to set barcode height in a C# barcode generator
og_title: Как установить высоту штрихкода и сгенерировать DataBar‑штрихкод в C#
schemas:
- author: Aspose
  dateModified: '2026-10-12'
  description: How to set barcode height and generate a DataBar barcode in C# using
    Aspose.BarCode. Follow a step‑by‑step guide with complete code.
  headline: How to set barcode height, generate DataBar barcode in C#
  type: TechArticle
tags:
- barcode
- C#
- Aspose.BarCode
title: Как задать высоту штрихкода и сгенерировать DataBar‑штрихкод в C#
url: /ru/python-java/general/how-to-set-barcode-height-generate-databar-barcode-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Как установить высоту штрихкода, сгенерировать DataBar штрихкод в C#

Если вам нужно **как установить высоту штрихкода** программно, это руководство покажет точные шаги. Вы узнаете, как сгенерировать DataBar Omni‑directional штрихкод, отрегулировать его высоту и сохранить обе версии в виде PNG‑файлов.

Изменение высоты полос штрихкода — частая задача при интеграции штрихкодов в чеки, этикетки товаров или мобильные экраны. Пример ниже использует библиотеку Aspose.BarCode, которая поддерживает полный набор символогий GS1 DataBar.

## Что вы получите

К концу этого урока вы сможете:

* **как установить высоту штрихкода** для DataBar Omni‑directional штрихкода  
* **generate barcode c#** код, создающий два изображения с разной высотой  
* понять **how to create databar** символы и почему высота полос важна  
* применить логику **change barcode height** без повторного создания генератора  

Никакие внешние инструменты не требуются, кроме пакета Aspose.BarCode NuGet и среды выполнения .NET 6+.

## Предварительные требования

* .NET 6 SDK или новее  
* Visual Studio 2022 (или любой редактор C#)  
* Aspose.BarCode for .NET – установить через `dotnet add package Aspose.BarCode`  

> **Pro tip:** Используйте бесплатную пробную лицензию Aspose, если у вас нет коммерческого ключа; API работает так же.

## Шаг 1: Установите пакет Aspose.BarCode

Откройте терминал в папке проекта и выполните:

```bash
dotnet add package Aspose.BarCode
```

Пакет добавляет пространство имён `Aspose.BarCode`, в котором находится класс `BarcodeGenerator`, который мы будем использовать для **generate barcode c#** изображений.

## Шаг 2: Создайте генератор DataBar штрихкода

Первое конкретное действие для **как установить высоту штрихкода** — создать экземпляр `BarcodeGenerator` с нужной символогией и строкой данных.

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

// Step 2: Initialize the generator for a DataBar Omni‑directional barcode
var barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarOmniDirectional, // symbology
    "(01)12345678901231");               // GS1 data payload
```

*Почему это важно:* `EncodeTypes.DatabarOmniDirectional` создаёт компактный, всенаправленный DataBar, который можно сканировать под любым углом — идеально для небольших этикеток.

## Шаг 3: Установите общие параметры штрихкода (включая начальную высоту полос)

Теперь мы отвечаем на вопрос **как установить высоту штрихкода**, задавая X‑размер и высоту полос перед сохранением первого изображения.

```csharp
// Step 3: Configure X‑dimension (module width) and initial bar height
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;    // 2‑pixel modules
barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 30;   // 30‑pixel height
```

X‑размер контролирует общую ширину каждой полосы; значение 2 пикселя даёт читаемое, чёткое изображение на большинстве экранов. Шаг **change barcode height** позже переиспользует тот же генератор, экономя время и память.

## Шаг 4: Сохраните первое изображение штрихкода (высота 30 пикселей)

```csharp
// Step 4: Save the 30‑pixel barcode image
barcodeGenerator.Save("DatabarHeight30.png", BarCodeImageFormat.Png);
```

Файл `DatabarHeight30.png` теперь содержит DataBar штрихкод с высотой полос 30 пикселей.

## Шаг 5: Измените только высоту полос до 60 пикселей

Чтобы продемонстрировать **change barcode height**, изменяем только свойство `BarHeight`. Все остальные настройки остаются без изменений — самый эффективный способ получить несколько размеров из одного генератора.

```csharp
// Step 5: Update the bar height to 60 pixels
barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 60;
```

## Шаг 6: Сохраните второе изображение штрихкода (высота 60 пикселей)

```csharp
// Step 6: Save the 60‑pixel barcode image
barcodeGenerator.Save("DatabarHeight60.png", BarCodeImageFormat.Png);
```

Теперь у вас есть два PNG‑файла, каждый с разной высотой полос, но одинаковыми данными и X‑размером.

## Полный, готовый к запуску пример

Ниже полная программа, которую можно скопировать в новое консольное приложение (`dotnet new console`) и сразу запустить.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        // Initialize the generator for a DataBar Omni‑directional barcode
        var barcodeGenerator = new BarcodeGenerator(
            EncodeTypes.DatabarOmniDirectional,
            "(01)12345678901231");

        // Set X‑dimension and initial bar height (30 pixels)
        barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
        barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 30;

        // Save the first image (30‑pixel height)
        barcodeGenerator.Save("DatabarHeight30.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved DatabarHeight30.png");

        // Change only the bar height to 60 pixels
        barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 60;

        // Save the second image (60‑pixel height)
        barcodeGenerator.Save("DatabarHeight60.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved DatabarHeight60.png");
    }
}
```

### Ожидаемый результат

При запуске программа создаст два файла в рабочем каталоге исполняемого файла:

* `DatabarHeight30.png` — DataBar штрихкод с полосами высотой 30 пикселей.  
* `DatabarHeight60.png` — тот же штрихкод, но каждая полоса вдвое выше.

Оба изображения можно открыть в любом просмотрщике, встроить в PDF, HTML‑страницы или напечатать на этикетках.

## Почему важно регулировать высоту полос

* **Надёжность сканирования:** Некоторые сканеры испытывают трудности с очень короткими полосами на низкокачественных носителях; увеличение высоты улучшает обнаружение.  
* **Ограничения дизайна:** В мобильном приложении может потребоваться компактный штрихкод (30 px), а на печатном чеке — более крупный (60 px).  
* **Регуляторные требования:** В некоторых отраслях требуется минимальная высота полос для символов GS1 DataBar.

Переиспользуя один экземпляр `BarcodeGenerator`, вы избегаете накладных расходов на повторный разбор строки данных, что особенно важно в средах с высоким объёмом обработки.

## Распространённые варианты и граничные случаи

| Situation | Recommended tweak |
|-----------|-------------------|
| Нужно другое значение X‑размера | Change `XDimension.Pixels` before the first `Save`. |
| Требуется другая симвология (например, DataBar Stacked) | Use `EncodeTypes.DatabarStacked` when constructing `BarcodeGenerator`. |
| Нужно встроить штрихкод в PDF | Use `barcodeGenerator.Save(stream, BarCodeImageFormat.Png)` and add the stream to a PDF library. |
| Работа на .NET Framework 4.6 | The same code works; just reference the appropriate Aspose.BarCode assembly. |

## Pro tips for reliable barcode generation

* **Cache the generator** when you generate many barcodes with the same data but different sizes.  
* **

## Что стоит изучить дальше?

Следующие руководства охватывают тесно связанные темы, расширяющие техники, продемонстрированные в этом руководстве. Каждый ресурс включает полностью рабочие примеры кода с пошаговыми объяснениями, чтобы помочь вам освоить дополнительные возможности API и исследовать альтернативные подходы в ваших проектах.

- [Как генерировать и регулировать высоту штрихкода для односторонних Databar с помощью Aspose.BarCode for .NET](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-barcode-height-adjustment/)
- [Как создать PNG‑изображения Databar с C# и Aspose.BarCode](/barcode/english/python-java/general/how-to-create-databar-png-images-with-c-and-aspose-barcode/)
- [Как генерировать штрихкод, задавать пользовательский размер и сохранять изображение в C#](/barcode/english/python-java/general/how-to-generate-barcode-set-custom-size-and-save-image-in-c/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}