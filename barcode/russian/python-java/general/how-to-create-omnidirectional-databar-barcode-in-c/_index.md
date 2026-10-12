---
category: general
date: 2026-09-29
description: Узнайте, как создать всенаправленный Databar‑штрихкод в C# с помощью
  Aspose.BarCode. Настройте X‑размер, задайте соотношение сторон и сохраните изображения
  в формате PNG.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create omnidirectional databar barcode
- DataBar stacked omnidirectional barcode
- set barcode aspect ratio
- Aspose.BarCode C#
- generate barcode image
language: ru
lastmod: 2026-09-29
og_description: Создайте всенаправленный Databar‑штрихкод на C# с использованием Aspose.BarCode.
  Узнайте, как установить X‑размер, отрегулировать соотношение сторон и экспортировать
  PNG‑файлы.
og_image_alt: Screenshot showing two PNG files of an omnidirectional Databar barcode
  with different aspect ratios
og_title: Создайте всенаправленный Databar‑штрихкод в C# — пошаговое руководство
schemas:
- author: Aspose
  dateModified: '2026-09-29'
  description: Learn how to create omnidirectional Databar barcode in C# with Aspose.BarCode.
    Adjust X‑dimension, set aspect ratio, and save PNG images.
  headline: How to create omnidirectional Databar barcode in C#
  type: TechArticle
- description: Learn how to create omnidirectional Databar barcode in C# with Aspose.BarCode.
    Adjust X‑dimension, set aspect ratio, and save PNG images.
  name: How to create omnidirectional Databar barcode in C#
  steps:
  - name: What if I need a different X‑dimension?
    text: You can assign any integer value to `XDimension.Pixels`. Values below `1`
      are ignored, and values above `10` may produce oversized modules that exceed
      printer margins. Test the visual output after each change.
  - name: How do I encode other AI‑generated data (e.g., UPC, EAN)?
    text: Replace the data string in the `BarcodeGenerator` constructor with the appropriate
      Application Identifier (AI). For a UPC‑A code, use `"012345678905"` without
      an AI prefix.
  - name: Can I export to formats other than PNG?
    text: Yes. The `Save` method accepts `BarCodeImageFormat.Jpeg`, `BarCodeImageFormat.Gif`,
      `BarCodeImageFormat.Tiff`, and `BarCodeImageFormat.Bmp`. Choose the format that
      matches your downstream workflow.
  type: HowTo
tags:
- barcode
- C#
- Aspose
title: Как создать всенаправленный штрих‑код Databar в C#
url: /ru/python-java/general/how-to-create-omnidirectional-databar-barcode-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Как создать всенаправленный Databar штрих‑код в C#

Если вам нужно **создать всенаправленный Databar штрих‑код** в приложении .NET, это руководство покажет точные шаги. Вы увидите, как инициализировать DataBar stacked omnidirectional штрих‑код, настроить его X‑dimension, изменить соотношение сторон и сгенерировать PNG‑изображения с помощью Aspose.BarCode.

Генерация **DataBar stacked omnidirectional штрих‑кода** часто требуется, когда необходимо закодировать идентификаторы продуктов для розничных сканеров. В этом уроке вы научитесь **устанавливать соотношение сторон штрих‑кода**, управлять размером модуля и экспортировать результат, не покидая IDE.

## Требования

Перед началом убедитесь, что у вас есть:

- .NET 6.0 или новее установлен
- Visual Studio 2022 (или любая IDE, совместимая с C#)
- Пакет **Aspose.BarCode for .NET** NuGet (версия 23.12 или новее)

Вы можете добавить пакет через NuGet Package Manager:

```bash
dotnet add package Aspose.BarCode
```

## Шаг 1: Инициализировать всенаправленный Databar штрих‑код

Первый шаг — создать экземпляр `BarcodeGenerator`, который нацелен на символьность **DataBar stacked omnidirectional**. Конструктор принимает тип кодирования и строку данных.

```csharp
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Initialise a DataBar stacked omnidirectional barcode with GTIN data
        var generator = new BarcodeGenerator(
            EncodeTypes.DatabarStackedOmniDirectional,
            "(01)12345678901231");
```

**Почему это важно:** Значение `EncodeTypes.DatabarStackedOmniDirectional` сообщает Aspose.BarCode отрисовать конкретный всенаправленный формат Databar, который требуется для сканирования в обоих направлениях.

## Шаг 2: Задать X‑dimension (размер модуля)

X‑dimension управляет шириной отдельного модуля штрих‑кода в пикселях. Значение `2` пикселя хорошо подходит для отображения на экране и большинства принтеров.

```csharp
        // Set the basic size of the barcode modules (X‑dimension) in pixels
        generator.Parameters.Barcode.XDimension.Pixels = 2;
```

**Почему это важно:** Последовательный X‑dimension гарантирует, что штрих‑код соответствует минимальным требованиям размеров для розничных сканеров, одновременно удерживая размер файла изображения в разумных пределах.

## Шаг 3: Установить первое соотношение сторон и сохранить изображение

**Соотношение сторон** определяет соотношение высоты к ширине DataBar. Соотношение `15` дает компактный, высокий штрих‑код, идеальный для узких этикеток.

```csharp
        // Apply aspect ratio 15 and save the first PNG
        generator.Parameters.Barcode.DataBar.AspectRatio = 15;
        generator.Save("DatabarAspectRatio15.png", BarCodeImageFormat.Png);
```

**Почему это важно:** Регулировка соотношения сторон позволяет разместить штрих‑код в разных макетах этикеток без потери читаемости. Сохранённый PNG можно просмотреть в любом просмотрщике изображений.

## Шаг 4: Изменить соотношение сторон и сгенерировать второе изображение

Иногда нужен более широкий штрих‑код — например, когда на этикетке есть больше горизонтального пространства. Изменив соотношение на `30`, вы получите более плоское изображение.

```csharp
        // Change aspect ratio to 30 and save a second PNG
        generator.Parameters.Barcode.DataBar.AspectRatio = 30;
        generator.Save("DatabarAspectRatio30.png", BarCodeImageFormat.Png);
    }
}
```

**Почему это важно:** Благодаря свойству **set barcode aspect ratio** вы можете создавать несколько вариантов штрих‑кода из одного кода, упрощая автоматизированные конвейеры генерации этикеток.

## Ожидаемый результат

Запуск программы создаёт два PNG‑файла в папке вывода приложения:

| Имя файла                | Соотношение сторон | Визуальное описание |
|--------------------------|---------------------|----------------------|
| `DatabarAspectRatio15.png` | 15                  | Высокий, узкий штрих‑код, подходящий для узких этикеток |
| `DatabarAspectRatio30.png` | 30                  | Широкий штрих‑код, заполняющий больше горизонтального пространства |

Эти изображения можно вставлять в отчёты, печатать на упаковке продукта или отправлять в веб‑службу для дальнейшей обработки.

![Пример создания всенаправленного Databar штрих‑кода](databar-example.png "Пример создания всенаправленного Databar штрих‑кода")

*Скриншот показывает два сгенерированных PNG‑файла рядом друг с другом.*

## Часто задаваемые вопросы и особые случаи

### Что если мне нужен другой X‑dimension?

Вы можете задать любое целое значение `XDimension.Pixels`. Значения ниже `1` игнорируются, а значения выше `10` могут привести к слишком большим модулям, выходящим за пределы полей принтера. После каждого изменения проверяйте визуальный результат.

### Как закодировать другие данные, сгенерированные AI (например, UPC, EAN)?

Замените строку данных в конструкторе `BarcodeGenerator` на соответствующий идентификатор приложения (AI). Для кода UPC‑A используйте `"012345678905"` без префикса AI.

### Можно ли экспортировать в форматы, отличные от PNG?

Да. Метод `Save` принимает `BarCodeImageFormat.Jpeg`, `BarCodeImageFormat.Gif`, `BarCodeImageFormat.Tiff` и `BarCodeImageFormat.Bmp`. Выберите формат, соответствующий вашему последующему рабочему процессу.

## Совет: повторное использование генератора для пакетной обработки

Если нужно сгенерировать десятки штрих‑кодов с разными соотношениями сторон, держите экземпляр `BarcodeGenerator` живым и меняйте `DataBar.AspectRatio` перед каждым вызовом `Save`. Это избавит от накладных расходов на повторное создание генератора для каждого изображения.

```csharp
var ratios = new[] { 10, 15, 20, 30 };
foreach (var ratio in ratios)
{
    generator.Parameters.Barcode.DataBar.AspectRatio = ratio;
    generator.Save($"DatabarAspectRatio{ratio}.png", BarCodeImageFormat.Png);
}
```

## Заключение

Теперь вы знаете, как **создать всенаправленный Databar штрих‑код** в C# с помощью Aspose.BarCode. Инициализировав `BarcodeGenerator`, задав X‑dimension, отрегулировав **set barcode aspect ratio** и сохранив PNG‑файлы, вы можете получать изображения штрих‑кодов, отвечающие разнообразным требованиям этикеток.  

Далее изучайте связанные темы, такие как **generate barcode image** для QR‑кодов, проверка **DataBar stacked omnidirectional barcode**, или интеграция сгенерированных PNG в PDF‑счета с помощью Aspose.PDF. Экспериментируйте с различными соотношениями сторон и размерами модулей, чтобы найти оптимальную конфигурацию для вашего конкретного печатного оборудования.

---


## Что стоит изучить дальше?

Следующие руководства охватывают тесно связанные темы, построенные на техниках, продемонстрированных в этом руководстве. Каждый ресурс включает полностью рабочие примеры кода с пошаговыми объяснениями, помогающими освоить дополнительные возможности API и исследовать альтернативные подходы к реализации в ваших проектах.

- [Как использовать генератор штрих‑кодов C# для создания DataBar Omni‑directional штрих‑кодов](/barcode/english/python-java/general/how-to-use-a-barcode-generator-c-to-create-databar-omni-dire/)
- [databar stacked omnidirectional штрих‑код в C# – Полное руководство](/barcode/english/python-java/general/databar-stacked-omnidirectional-barcode-in-c-complete-guide/)
- [Как сгенерировать штрих‑код в C# – создать изображение штрих‑кода c# с DataBar Expanded](/barcode/english/python-java/general/how-to-generate-barcode-in-c-create-barcode-image-c-with-dat/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}