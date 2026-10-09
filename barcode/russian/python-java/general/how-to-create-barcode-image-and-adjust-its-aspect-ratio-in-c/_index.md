---
category: general
date: 2026-10-08
description: Узнайте, как создать изображение штрих‑кода в C#, и откройте, как настроить
  соотношение сторон для многоплоскостных (omni‑directional) штрих‑кодов DataBar stacked.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode image
- how to adjust aspect ratio
- Aspose.BarCode C#
- DataBar stacked omni‑directional
- barcode X‑dimension
language: ru
lastmod: 2026-10-08
og_description: Создайте изображение штрих‑кода на C# и узнайте, как настроить соотношение
  сторон для многослойных omni‑directional DataBar штрих‑кодов, с полным примером
  кода.
og_image_alt: Result of create barcode image with aspect ratio 15 using Aspose.BarCode
og_title: Создание изображения штрих‑кода в C# – пошаговое руководство
schemas:
- author: Aspose
  dateModified: '2026-10-08'
  description: Learn how to create barcode image in C# and discover how to adjust
    aspect ratio for DataBar stacked omni‑directional barcodes.
  headline: How to create barcode image and adjust its aspect ratio in C#
  type: TechArticle
- description: Learn how to create barcode image in C# and discover how to adjust
    aspect ratio for DataBar stacked omni‑directional barcodes.
  name: How to create barcode image and adjust its aspect ratio in C#
  steps:
  - name: Expected output
    text: 'After running the program you will find two PNG files in the execution
      directory:'
  - name: What if I need a different X‑dimension?
    text: You can change `barcodeGenerator.Parameters.Barcode.XDimension.Pixels` to
      any integer greater than zero. For very high‑resolution output (e.g., 300 dpi),
      a value of 3‑4 pixels often yields clearer results.
  - name: How do I choose the right aspect ratio?
    text: 'The optimal ratio depends on the scanning environment: * **Low‑profile
      labels** – use a smaller ratio (e.g., 10‑15) to keep the barcode compact. *
      **Large shipping containers** – a higher ratio (e.g., 25‑35) improves readability
      from a distance. * **Regulatory requirements** – some standards mandate'
  - name: Can I generate other barcode formats with the same code?
    text: Yes. Replace `EncodeTypes.DatabarStackedOmniDirectional` with any other
      `EncodeTypes` value (e.g., `EncodeTypes.Code128`). The rest of the code—X‑dimension,
      aspect ratio (if applicable), and saving—remains the same.
  - name: What if I need to create the image in a different format?
    text: '`BarCodeImageFormat` supports PNG, JPEG, BMP, GIF, and TIFF. Just change
      the second argument of `Save`, for example:'
  - name: Next steps
    text: '* Explore other symbologies such as **Code128** or **QR Code** by swapping
      the `EncodeTypes` value. * Combine the barcode generation with PDF creation
      (e.g., using Aspose.PDF) to embed barcodes directly into invoices. * Experiment
      with dynamic aspect‑ratio selection based on label size—this extends '
  type: HowTo
tags:
- barcode
- C#
- Aspose.BarCode
title: Как создать изображение штрихкода и настроить его соотношение сторон в C#
url: /ru/python-java/general/how-to-create-barcode-image-and-adjust-its-aspect-ratio-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Как создать изображение штрих‑кода и настроить его соотношение сторон в C#

Если вам нужно **создать изображение штрих‑кода** программно, это руководство покажет готовое решение, готовое к запуску. Вы увидите, **как настроить соотношение сторон** для штрих‑кода DataBar stacked omni‑directional — требование, часто встречающееся в розничной торговле и логистике.

В этом учебнике вы узнаете, как:
* Инициализировать `BarcodeGenerator` из Aspose.BarCode для символьного набора DataBar stacked omni‑directional.  
* Установить X‑размер (ширину модуля) в пикселях для управления толщиной полос.  
* Применить два разных соотношения сторон и сохранить каждый результат в виде PNG‑файла.  
* Проверить вывод и понять, почему соотношение сторон имеет значение.

Никакие внешние инструменты не требуются — только библиотека Aspose.BarCode для .NET и среда разработки .NET 6 (или новее).

## Как создать изображение штрих‑кода с помощью Aspose.BarCode

Первый шаг — создать экземпляр генератора с нужным символьным набором и строкой данных. Перечисление `EncodeTypes.DatabarStackedOmniDirectional` указывает Aspose.BarCode генерировать штрих‑код DataBar stacked omni‑directional, широко используемый в приложениях GS1‑128.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        // 1️⃣ Create a BarcodeGenerator for DataBar stacked omni‑directional.
        // The data string "(01)12345678901231" follows the GS1 Application Identifier format.
        BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
            EncodeTypes.DatabarStackedOmniDirectional,
            "(01)12345678901231");
```

**Почему это важно:** Объект `BarcodeGenerator` является точкой входа для всех задач создания штрих‑кодов. Указывая символьный набор и исходные данные сразу, вы гарантируете, что сгенерированное изображение соответствует стандарту GS1.

## Установка X‑размера (ширины модуля)

X‑размер определяет ширину самой узкой полосы (модуля). Больший X‑размер дает более толстый штрих‑код, что может быть полезно для принтеров с низким разрешением.

```csharp
        // 2️⃣ Define the X‑dimension in pixels.
        // A value of 2 pixels provides a good balance between readability and file size.
        barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

**Почему это важно:** Регулировка X‑размера — часть процесса визуальной настройки. Это не влияет на закодированные данные, но повышает надёжность сканирования на разных устройствах.

## Как настроить соотношение сторон — первая версия (15)

Соотношение сторон управляет отношением высоты к ширине штрих‑кода DataBar. Свойство `DataBar.AspectRatio` принимает целочисленные значения; большие числа делают полосы выше.

```csharp
        // 3️⃣ Set the aspect ratio to 15 and save the first image.
        barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 15;
        barcodeGenerator.Save("DatabarAspectRatio15.png", BarCodeImageFormat.Png);
```

**Почему это важно:** Соотношение сторон 15 является обычным значением по умолчанию для розничных сканеров. Полученный PNG (`DatabarAspectRatio15.png`) будет выглядеть выше, что может улучшить успех сканирования на портативных устройствах.

## Как настроить соотношение сторон — вторая версия (30)

В некоторых случаях требуется более высокий штрих‑код для специфических форматов этикеток. Изменить соотношение сторон так же просто, как присвоить новое целочисленное значение перед повторным вызовом `Save`.

```csharp
        // 4️⃣ Change the aspect ratio to 30 and save a second image.
        barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 30;
        barcodeGenerator.Save("DatabarAspectRatio30.png", BarCodeImageFormat.Png);
    }
}
```

**Почему это важно:** Демонстрируя **как настроить соотношение сторон**, вы можете генерировать несколько изображений штрих‑кода из одного источника данных без повторного создания генератора. Это снижает расход памяти и ускоряет пакетную обработку.

### Ожидаемый результат

После выполнения программы в каталоге запуска появятся два PNG‑файла:

| Имя файла                     | Соотношение сторон | Описание внешнего вида |
|-------------------------------|--------------------|------------------------|
| `DatabarAspectRatio15.png`    | 15                 | Стандартная высота, подходит для большинства сканеров точки продаж. |
| `DatabarAspectRatio30.png`    | 30                 | Более высокие полосы, полезны для больших этикеток или принтеров с низким разрешением. |

Оба изображения содержат один и тот же закодированный GTIN `(01)12345678901231`, но визуальные пропорции различаются в зависимости от установленного соотношения сторон.

## Часто задаваемые вопросы и обработка граничных случаев

### Что делать, если нужен другой X‑размер?

Можно изменить `barcodeGenerator.Parameters.Barcode.XDimension.Pixels` на любое целое число больше нуля. Для вывода с очень высоким разрешением (например, 300 dpi) значение 3‑4 пикселя часто даёт более чёткий результат.

### Как выбрать правильное соотношение сторон?

Оптимальное соотношение зависит от условий сканирования:
* **Низкопрофильные этикетки** — используйте меньшее соотношение (например, 10‑15), чтобы штрих‑код был компактным.  
* **Большие транспортные контейнеры** — более высокое соотношение (например, 25‑35) улучшает читаемость с расстояния.  
* **Регуляторные требования** — некоторые стандарты требуют минимальную высоту; уточняйте детали в спецификации GS1.

### Можно ли генерировать другие форматы штрих‑кодов тем же кодом?

Да. Замените `EncodeTypes.DatabarStackedOmniDirectional` на любое другое значение `EncodeTypes` (например, `EncodeTypes.Code128`). Остальная часть кода — X‑размер, соотношение сторон (при необходимости) и сохранение — остаются без изменений.

### Что если нужно создать изображение в другом формате?

`BarCodeImageFormat` поддерживает PNG, JPEG, BMP, GIF и TIFF. Достаточно изменить второй аргумент метода `Save`, например:

```csharp
barcodeGenerator.Save("barcode.jpg", BarCodeImageFormat.Jpeg);
```

## Совет профессионала: повторное использование генератора для пакетной обработки

Когда требуется создать десятки штрих‑кодов с одинаковыми визуальными настройками, создайте генератор один раз, меняйте только свойство `CodeText` и вызывайте `Save` многократно. Это устраняет накладные расходы на повторное выделение внутренних буферов.

```csharp
// Example of batch creation
string[] gtins = { "(01)12345678901231", "(01)98765432109876", "(01)55555555555555" };
foreach (var gtin in gtins)
{
    barcodeGenerator.CodeText = gtin;
    barcodeGenerator.Save($"Barcode_{gtin.Substring(4, 6)}.png", BarCodeImageFormat.Png);
}
```

## Заключение

Теперь вы знаете, как **создать изображение штрих‑кода** в C# с помощью Aspose.BarCode и точно **настроить соотношение сторон** для символов DataBar stacked omni‑directional. Управляя X‑размером и соотношением сторон, вы можете получать штрих‑коды, соответствующие любым требованиям сканирования или макета, при этом сохраняя реализацию простой и поддерживаемой.

### Следующие шаги

* Исследуйте другие символьные наборы, такие как **Code128** или **QR Code**, заменив значение `EncodeTypes`.  
* Скомбинируйте генерацию штрих‑кода с созданием PDF (например, используя Aspose.PDF), чтобы внедрять штрих‑коды напрямую в счета‑фактуры.  
* Поэкспериментируйте с динамическим выбором соотношения сторон в зависимости от размера этикетки — это расширит шаблон **как настроить соотношение сторон** до полноценного движка дизайна этикеток.

Не стесняйтесь адаптировать пример, делиться результатами или задавать дополнительные вопросы в комментариях. Приятного кодинга!

## Что следует изучить дальше?

Следующие учебники охватывают тесно связанные темы, которые развивают техники, продемонстрированные в этом руководстве. Каждый ресурс включает полностью работающие примеры кода с пошаговыми объяснениями, помогающими освоить дополнительные возможности API и исследовать альтернативные подходы в ваших проектах.

- [How to create databar stacked barcode in C# with Aspose.Barcode](/barcode/english/python-java/general/how-to-create-databar-stacked-barcode-in-c-with-aspose-barco/)
- [How to create barcode image with Aspose.Barcode in C#](/barcode/english/python-java/general/how-to-create-barcode-image-with-aspose-barcode-in-c/)
- [How to Adjust Barcode Size – Codablock F Aspect Ratio with Aspose.BarCode for .NET](/barcode/english/net/codablock-f-encoding/codablock-f-aspect-ratio-customization/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}