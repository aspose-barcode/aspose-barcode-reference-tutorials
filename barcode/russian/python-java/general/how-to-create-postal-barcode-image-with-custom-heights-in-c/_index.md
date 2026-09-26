---
category: general
date: 2026-09-26
description: Узнайте, как создать изображение почтового штрихкода в C#. Это руководство
  покажет, как сгенерировать штрихкод Planet и задать высоту штрихкода для пользовательского
  вывода.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create postal barcode image
- generate planet barcode
- barcode generator custom height
- how to set barcode height
language: ru
lastmod: 2026-09-26
og_description: Быстро создайте изображение почтового штрихкода на C#. Следуйте этому
  руководству, чтобы сгенерировать штрихкод Planet, установить высоту штрихкода и
  получить PNG‑файлы высокого качества.
og_image_alt: Screenshot of a generated postal barcode image with custom bar height
og_title: Создайте изображение почтового штрихкода с пользовательскими высотами в
  C# – пошаговое руководство
schemas:
- author: Aspose
  dateModified: '2026-09-26'
  description: Learn how to create postal barcode image in C#. This guide shows you
    how to generate planet barcode and set barcode height for custom output.
  headline: How to create postal barcode image with custom heights in C#
  type: TechArticle
tags:
- barcode
- C#
- Aspose.Barcode
title: Как создать изображение почтового штрихкода с пользовательскими высотами в
  C#
url: /ru/python-java/general/how-to-create-postal-barcode-image-with-custom-heights-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Как создать изображение почтового штрихкода с пользовательской высотой в C#

Если вам нужно **создать изображение почтового штрихкода** для почтовых ярлыков, этот учебник покажет точные шаги. Вы узнаете, как сгенерировать штрихкод Planet, изменить высоту полосы и сохранить результат в файл PNG — все это с помощью библиотеки Aspose.BarCode для .NET.

Создание изображения штрихкода не требует внешних графических инструментов. К концу руководства вы сможете создавать как штрихкоды стандартной высоты, так и с пользовательской высотой для стандартов Planet и RM4SCC, готовые к интеграции в любой процесс отправки.

## Требования

Прежде чем начать, убедитесь, что у вас есть:

* .NET 6.0 или новее  
* Visual Studio 2022 (или любой IDE для C#)  
* Aspose.BarCode для .NET, установленный через NuGet (`Install-Package Aspose.BarCode`)  

Дополнительная настройка не требуется; библиотека самостоятельно обрабатывает рендеринг изображений.

## Шаг 1: Создание проекта и импорт пространств имён

Создайте новое консольное приложение и добавьте необходимые `using`‑директивы.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;
```

Эти пространства имён предоставляют класс `BarcodeGenerator` и перечисление `EncodeTypes`, которые вы будете использовать для **генерации штрихкода Planet** и других почтовых форматов.

## Шаг 2: Создание штрихкода Planet со стандартной высотой полосы

В первом примере создаётся штрихкод Planet с высотой полосы по умолчанию, предоставляемой библиотекой. Это базовый результат, с которым вы будете сравнивать вариант с пользовательской высотой.

```csharp
// Initialize the generator for a Planet barcode
BarcodeGenerator planetGenerator = new BarcodeGenerator(EncodeTypes.Planet, "123456");

// Set the X‑dimension (module width) to 4 pixels for better readability
planetGenerator.Parameters.Barcode.XDimension.Pixels = 4;

// Save the barcode image; the default bar height is applied automatically
planetGenerator.Save("PostalPlanetBarHeightDefault.png", BarCodeImageFormat.Png);
```

**Почему это важно:** Стандартная высота подходит большинству принтеров этикеток, но в некоторых процессах требуются более высокие полосы для повышения надёжности сканирования. Приведённый код даёт вам эталонное изображение для сравнения с версией пользовательской высоты.

## Шаг 3: Установка пользовательской высоты полосы для штрихкода Planet

Чтобы **задать высоту штрихкода** вручную, присвойте пиксельное значение свойству `BarHeight.Pixels`. Ниже показан фрагмент, создающий штрихкод Planet высотой 100 пикселей.

```csharp
// Initialize a second generator for the same data
BarcodeGenerator planetHeightGenerator = new BarcodeGenerator(EncodeTypes.Planet, "123456");

// Define X‑dimension and a custom bar height of 100 pixels
planetHeightGenerator.Parameters.Barcode.XDimension.Pixels = 4;
planetHeightGenerator.Parameters.Barcode.BarHeight.Pixels = 100;

// Save the custom‑height image
planetHeightGenerator.Save("PostalPlanetBarHeight100Pixels.png", BarCodeImageFormat.Png);
```

**Совет эксперта:** Выбирайте высоту полосы, соответствующую DPI вашего принтера. Для принтера с разрешением 300 dpi высота 100 пикселей примерно равна 0,33 дюйма, что часто рекомендуется для почтовых сканеров.

## Шаг 4: Генерация штрихкода RM4SCC со стандартной высотой

RM4SCC — ещё один распространённый почтовый символьный набор. Процесс аналогичен примеру с Planet, но используется `EncodeTypes.RM4SCC`.

```csharp
BarcodeGenerator rm4sccGenerator = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");

// Set X‑dimension; the library applies the default bar height automatically
rm4sccGenerator.Parameters.Barcode.XDimension.Pixels = 4;
rm4sccGenerator.Save("PostalRM4SCCBarHeightDefault.png", BarCodeImageFormat.Png);
```

Этот шаг подтверждает, что логика **настройки пользовательской высоты генератора штрихкода** работает с разными почтовыми форматами.

## Шаг 5: Установка пользовательской высоты для штрихкода RM4SCC

Наконец, измените высоту полосы для штрихкода RM4SCC тем же способом, что и для штрихкода Planet.

```csharp
BarcodeGenerator rm4sccHeightGenerator = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");

// Define both X‑dimension and a 100‑pixel bar height
rm4sccHeightGenerator.Parameters.Barcode.XDimension.Pixels = 4;
rm4sccHeightGenerator.Parameters.Barcode.BarHeight.Pixels = 100;

// Save the custom‑height image
rm4sccHeightGenerator.Save("PostalRM4SCCBarHeight100Pixels.png", BarCodeImageFormat.Png);
```

## Ожидаемый результат

Запуск полной программы создаёт четыре PNG‑файла в выходном каталоге проекта:

| File name                               | Bar height | Symbology |
|----------------------------------------|------------|-----------|
| `PostalPlanetBarHeightDefault.png`     | default    | Planet    |
| `PostalPlanetBarHeight100Pixels.png`   | 100 px     | Planet    |
| `PostalRM4SCCBarHeightDefault.png`     | default    | RM4SCC    |
| `PostalRM4SCCBarHeight100Pixels.png`   | 100 px     | RM4SCC    |

Каждое изображение представляет чёткий, контрастный штрихкод, готовый к печати на почтовых ярлыках. Откройте PNG‑файлы в любом просмотрщике изображений, чтобы проверить размеры полос.

## Часто задаваемые вопросы и особые случаи

**Что делать, если нужна высота полосы в миллиметрах, а не в пикселях?**  
Библиотека работает в пикселях, так как напрямую сопоставляет их с разрешением битмапа. Переведите миллиметры в пиксели, используя DPI принтера:  
`pixels = (mm / 25.4) * DPI`. Затем задайте `BarHeight.Pixels` полученным значением.

**Можно ли изменить высоту полосы после вызова `Save`?**  
Нет. Изображение штрихкода рендерится в момент вызова `Save`. Все параметры необходимо настроить до этого вызова.

**Нужен ли больший X‑dimension для более высоких полос?**  
Увеличение `XDimension` делает каждый модуль шире, что может улучшить читаемость на принтерах с низким разрешением. Однако это также увеличивает общую ширину штрихкода. Тестируйте оба параметра, чтобы найти оптимальный баланс для вашего ярлыка.

**Будет ли тот же код работать на .NET Framework 4.8?**  
Да. Aspose.BarCode поддерживает .NET Framework 4.6.2 и новее, поэтому вы можете целиться в более старые среды без изменений.

## Полный исходный код для быстрого копирования

Ниже приведена полностью готовая к запуску программа, включающая все описанные выше шаги.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // ---------- Planet barcode (default height) ----------
        BarcodeGenerator planetGenerator = new BarcodeGenerator(EncodeTypes.Planet, "123456");
        planetGenerator.Parameters.Barcode.XDimension.Pixels = 4;
        planetGenerator.Save("PostalPlanetBarHeightDefault.png", BarCodeImageFormat.Png);

        // ---------- Planet barcode (custom 100‑pixel height) ----------
        BarcodeGenerator planetHeightGenerator = new BarcodeGenerator(EncodeTypes.Planet, "123456");
        planetHeightGenerator.Parameters.Barcode.XDimension.Pixels = 4;
        planetHeightGenerator.Parameters.Barcode.BarHeight.Pixels = 100;
        planetHeightGenerator.Save("PostalPlanetBarHeight100Pixels.png", BarCodeImageFormat.Png);

        // ---------- RM4SCC barcode (default height) ----------
        BarcodeGenerator rm4sccGenerator = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");
        rm4sccGenerator.Parameters.Barcode.XDimension.Pixels = 4;
        rm4sccGenerator.Save("PostalRM4SCCBarHeightDefault.png", BarCodeImageFormat.Png);

        // ---------- RM4SCC barcode (custom 100‑pixel height) ----------
        BarcodeGenerator rm4sccHeightGenerator = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");
        rm4sccHeightGenerator.Parameters.Barcode.XDimension.Pixels = 4;
        rm4sccHeightGenerator.Parameters.Barcode.BarHeight.Pixels = 100;
        rm4sccHeightGenerator.Save("PostalRM4SCCBarHeight100Pixels.png", BarCodeImageFormat.Png);

        Console.WriteLine("All barcode images have been generated successfully.");
    }
}
```

Запустите программу, и консоль подтвердит сохранение каждого изображения. Теперь вы можете внедрять эти PNG‑файлы в шаблоны почтовых ярлыков, печатать их или отправлять в сторонний API логистики.

## Заключение

Теперь вы знаете, как **создавать изображения почтового штрихкода** в C# с помощью Aspose.BarCode. Руководство охватывало генерацию штрихкода Planet, настройку высоты полосы и применение той же техники к штрихкоду RM4SCC. Управляя `XDimension` и `BarHeight.Pixels`, вы получаете точные визуальные результаты, соответствующие требованиям почтовых служб.

Далее изучайте связанные темы, такие как **генерация QR‑кодов для отслеживания**, **встраивание штрихкодов в PDF‑счета** или **пакетная обработка множества изображений штрихкодов**. Регулировка высоты полосы — это лишь один из рычагов; вы также можете менять цвета, добавлять читаемый человеком текст или экспортировать в SVG для веб‑использования.

Удачной разработки, и пусть ваши отправления сканируются безупречно!

## Что изучать дальше?

Следующие учебники охватывают тесно связанные темы, расширяющие техники, продемонстрированные в этом руководстве. Каждый ресурс содержит полностью рабочие примеры кода с пошаговыми объяснениями, помогающими освоить дополнительные возможности API и исследовать альтернативные подходы в ваших проектах.

- [Создать изображение почтового штрихкода в C# – пошаговое руководство](/barcode/english/python-java/general/create-postal-barcode-image-in-c-step-by-step-guide/)
- [Создание почтовых штрихкодов – легко изменить высоту штрихкода](/barcode/english/python-java/general/create-postal-barcode-images-change-barcode-height-easily/)
- [Как сгенерировать почтовый штрихкод в C# с пользовательскими размерами](/barcode/english/python-java/general/how-to-generate-postal-barcode-in-c-with-custom-dimensions/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}