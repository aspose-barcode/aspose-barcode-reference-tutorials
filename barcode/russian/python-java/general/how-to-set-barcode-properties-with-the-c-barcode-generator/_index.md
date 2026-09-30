---
category: general
date: 2026-09-10
description: Как установить штрих‑код в C# с помощью генератора штрих‑кодов. Настройте
  ширину модуля штрих‑кода, генерируйте изображения штрих‑кодов и узнайте, как сохранять
  файлы штрих‑кодов.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to set barcode
- c# barcode generator
- barcode module width
- how to generate barcode
- how to save barcode
language: ru
lastmod: 2026-09-10
og_description: Как установить штрих-код в C# с помощью генератора штрих-кодов. Узнайте,
  как настроить ширину модуля, сгенерировать штрих-код и эффективно сохранить изображение
  штрих-кода.
og_image_alt: Screenshot showing a Planet barcode with filled and empty bars generated
  by C# code
og_title: Как установить свойства штрихкода с помощью генератора штрихкодов на C#
schemas:
- author: Aspose
  dateModified: '2026-09-10'
  description: How to set barcode in C# using a Barcode Generator. Adjust barcode
    module width, generate barcode images, and learn how to save barcode files.
  headline: How to set barcode properties with the C# Barcode Generator
  type: TechArticle
tags:
- barcode
- c#
- image generation
title: Как установить свойства штрихкода с помощью генератора штрихкодов C#
url: /ru/python-java/general/how-to-set-barcode-properties-with-the-c-barcode-generator/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Как установить свойства штрихкода с помощью генератора штрихкодов C#

Установка свойств штрихкода имеет решающее значение, когда требуется точный контроль над визуальным стилем штрихкода. В этом руководстве показано, как сгенерировать штрихкод Planet, настроить ширину модуля штрихкода и сохранить изображение штрихкода с помощью генератора штрихкодов C#.

Вы увидите полный, исполняемый пример, охватывающий каждый шаг от создания объекта штрихкода до записи PNG‑файлов на диск. Внешняя документация не требуется — достаточно кода ниже и библиотеки Aspose.BarCode (или любой совместимой SDK для штрихкодов). К концу руководства вы сможете ответить на такие вопросы, как «как сгенерировать штрихкод с пользовательскими размерами?» и «как сохранить штрихкод в разных форматах?».

## Предварительные требования

* .NET 6.0 или новее установлен  
* Visual Studio 2022 (или любой IDE для C#)  
* Пакет NuGet **Aspose.BarCode** (или другая библиотека, предоставляющая `BarcodeGenerator`)  

Вы можете добавить пакет с помощью следующей команды:

```bash
dotnet add package Aspose.BarCode
```

## Как установить ширину модуля штрихкода

*Ширина модуля* (также называется X‑dimension) определяет размер в пикселях каждой узкой полосы в штрихкоде. Установка этого значения позволяет контролировать общий размер и читаемость изображения.

```csharp
// Create a barcode generator for the Planet symbology
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(EncodeTypes.Planet, "123456");

// Set the module width to 4 pixels
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 4;
```

*Почему это важно*: Большая X‑dimension создает более крупный штрихкод, который сканерам легче считывать с расстояния, тогда как меньшее значение уменьшает размер файла при отображении на экране.

## Генерация штрихкода с заполненными полосами

Стиль по умолчанию для штрихкода Planet использует **заполненные полосы** (сплошные черные полосы). Следующий код создает изображение и сохраняет его в формате PNG.

```csharp
// Save the barcode with filled bars
barcodeGenerator.Save("YOUR_DIRECTORY/PostalPlanetFilledBars.png", BarCodeImageFormat.Png);
```

> **Результат**: `PostalPlanetFilledBars.png` содержит стандартный штрихкод Planet, где каждая полоса заполнена.

## Создание штрихкода с пустыми полосами

Иногда требуется штрихкод, отображающий только контуры полос (пустые полосы). Для этого вы дублируете генератор, сохраняете ту же ширину модуля и отключаете флаг `FilledBars`.

```csharp
// Duplicate the generator for an empty‑bar version
BarcodeGenerator emptyBarGenerator = new BarcodeGenerator(EncodeTypes.Planet, "123456");

// Apply the same X‑dimension
emptyBarGenerator.Parameters.Barcode.XDimension.Pixels = 4;

// Disable filled bars so only the outlines are drawn
emptyBarGenerator.Parameters.Barcode.FilledBars = false;

// Save the empty‑bar barcode
emptyBarGenerator.Save("YOUR_DIRECTORY/PostalPlanetEmptyBars.png", BarCodeImageFormat.Png);
```

> **Результат**: `PostalPlanetEmptyBars.png` отображает те же данные, но с незаполненными полосами, что полезно для документов с интенсивным дизайном, где требуется, чтобы штрихкод гармонировал с фоном.

## Как сохранить штрихкод в разных форматах

Метод `Save` принимает любой формат, поддерживаемый SDK, например **Jpeg**, **Bmp**, **Gif** или **Svg**. Для изменения формата достаточно заменить значение перечисления `BarCodeImageFormat`.

```csharp
// Example: save as SVG for lossless scaling
barcodeGenerator.Save("YOUR_DIRECTORY/PostalPlanet.svg", BarCodeImageFormat.Svg);
```

*Подсказка*: Используйте SVG, когда нужен векторный графический файл, который масштабируется без пикселизации, особенно для PDF‑документов, готовых к печати.

## Полный, исполняемый пример

Собрав все части вместе, вы получаете автономную программу, которую можно вставить в консольное приложение.

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // 1. Create a filled‑bar Planet barcode
        BarcodeGenerator filledGenerator = new BarcodeGenerator(EncodeTypes.Planet, "123456");
        filledGenerator.Parameters.Barcode.XDimension.Pixels = 4; // barcode module width
        filledGenerator.Save("PostalPlanetFilledBars.png", BarCodeImageFormat.Png);

        // 2. Create an empty‑bar version of the same barcode
        BarcodeGenerator emptyGenerator = new BarcodeGenerator(EncodeTypes.Planet, "123456");
        emptyGenerator.Parameters.Barcode.XDimension.Pixels = 4; // same module width
        emptyGenerator.Parameters.Barcode.FilledBars = false;   // how to set barcode to empty bars
        emptyGenerator.Save("PostalPlanetEmptyBars.png", BarCodeImageFormat.Png);

        // 3. Optional: save as SVG for scalable use
        filledGenerator.Save("PostalPlanet.svg", BarCodeImageFormat.Svg);
    }
}
```

**Ожидаемый вывод**

| File name                     | Description                                          |
|-------------------------------|------------------------------------------------------|
| `PostalPlanetFilledBars.png`  | Штрихкод Planet со сплошными черными полосами        |
| `PostalPlanetEmptyBars.png`   | Те же данные, полосы отображены как контуры          |
| `PostalPlanet.svg`            | Векторная версия для масштабирования без потери качества |

Запустите программу, откройте сгенерированные файлы и убедитесь, что штрихкоды соответствуют числовой строке «123456».

## Распространённые варианты и граничные случаи

| Ситуация                               | Корректировка                                                                 |
|----------------------------------------|-------------------------------------------------------------------------------|
| Необходим более толстый штрихкод       | Увеличьте `XDimension.Pixels` (например, `8`)                                 |
| Нужен меньший размер файла             | Используйте `BarCodeImageFormat.Jpeg` или уменьшите X‑dimension                |
| Генерация других символогий            | Замените `EncodeTypes.Planet` на `EncodeTypes.Code128`, `QR` и т.д.           |
| Печать на принтерах с высоким разрешением | Сохраните как `BarCodeImageFormat.Tiff` для без потерь растрового вывода        |
| Запуск на сервере без графического интерфейса | Кода UI не требуется; генератор работает в консольном приложении или сервисе   |

**Совет профессионала**: Всегда проверяйте сгенерированный штрихкод сканером или инструментом верификации перед выпуском в продакшн. Неправильная ширина модуля или формат могут привести к ошибкам сканирования.

## Заключение

Теперь вы знаете, как установить свойства штрихкода с помощью генератора штрихкодов C#, как контролировать ширину модуля штрихкода, как генерировать как заполненные, так и пустые стили полос, а также как сохранять штрихкод в форматах PNG или SVG. Эти шаги дают прочную основу для добавления создания штрихкодов в любое приложение .NET.

Далее изучайте связанные темы, такие как **c# barcode generator performance tuning**, **embedding barcodes in PDF documents**, и **creating QR codes with custom colors**. Экспериментируйте с различными `EncodeTypes` и форматами изображений, чтобы найти оптимальный вариант для вашего проекта.

## Что стоит изучить дальше?

Следующие руководства охватывают тесно связанные темы, которые развивают техники, продемонстрированные в этом руководстве. Каждый ресурс включает полные рабочие примеры кода с пошаговыми объяснениями, помогающими освоить дополнительные возможности API и исследовать альтернативные подходы к реализации в ваших проектах.

- [Как сохранить штрихкод в C# – Генерация PDF417 штрихкодов](/barcode/english/net/compact-pdf417-encoding/how-to-save-barcode-in-c-generate-pdf417-barcodes/)
- [Руководство по генератору штрихкодов: Как сгенерировать штрихкод PDF417 в C#](/barcode/english/net/compact-pdf417-encoding/barcode-generator-tutorial-how-to-generate-pdf417-barcode-in/)
- [Как установить уровень ошибки в штрихкоде PDF417 – Полное руководство](/barcode/english/net/compact-pdf417-encoding/how-to-set-error-level-in-pdf417-barcode-complete-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}