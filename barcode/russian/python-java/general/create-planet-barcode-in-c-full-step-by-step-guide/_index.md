---
category: general
date: 2026-07-18
description: Создайте штрих‑код Planet быстро с помощью C#. Узнайте, как генерировать
  заполненные и пустые полосы, задавать X‑размер и сохранять PNG‑изображения — всё
  в одном руководстве.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create planet barcode
- Planet barcode generator
- BarcodeGenerator parameters
- XDimension pixels
- filled bars vs empty bars
language: ru
lastmod: 2026-07-18
og_description: Создайте штрих‑код Planet мгновенно. Это руководство показывает, как
  установить X‑размер, переключаться между заполненными и пустыми полосами и экспортировать
  PNG‑файлы с помощью Aspose.BarCode.
og_image_alt: Screenshot of a generated Planet barcode saved as PNG
og_title: Создание Planet Barcode на C# – Полный пошаговый обзор программирования
schemas:
- author: Aspose
  dateModified: '2026-07-18'
  description: Create Planet barcode quickly with C#. Learn how to generate filled
    and empty bars, set X‑dimension, and save PNG images – all in one tutorial.
  headline: Create Planet Barcode in C# – Full Step‑by‑Step Guide
  type: TechArticle
- description: Create Planet barcode quickly with C#. Learn how to generate filled
    and empty bars, set X‑dimension, and save PNG images – all in one tutorial.
  name: Create Planet Barcode in C# – Full Step‑by‑Step Guide
  steps:
  - name: “Can I change the image format?”
    text: Absolutely. The `Save` method accepts `BarCodeImageFormat.Jpeg`, `Bmp`,
      `Gif`, etc. Just replace `BarCodeImageFormat.Png` with your desired format.
  - name: “What if I need a different barcode height?”
    text: 'Use `planetBarcode.Parameters.Barcode.BarHeight` (in points) to increase
      or decrease the vertical size. For example:'
  - name: “Is there a way to add a human‑readable caption?”
    text: 'Yes. Set the `CodeText` property on `planetBarcode.Parameters.Caption`:'
  - name: “Do I need to dispose the generator?”
    text: 'The `BarcodeGenerator` implements `IDisposable`. Wrap it in a `using` block
      if you’re creating many barcodes in a loop:'
  - name: “What about error handling?”
    text: 'Enclose the `Save` calls in a `try…catch` block to capture `IOException`
      (disk issues) or `ArgumentException` (invalid parameters). Example:'
  type: HowTo
tags:
- barcode
- C#
- Aspose.BarCode
title: Создание Planet Barcode на C# – Полное пошаговое руководство
url: /ru/python-java/general/create-planet-barcode-in-c-full-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Создание штрих‑кода Planet в C# – Полное пошаговое руководство

Когда‑то вам нужно было **создать штрих‑код planet**, но вы не знали, какие свойства менять? Вы не одиноки. Многие разработчики сталкиваются с тем, что заполненные полосы по умолчанию не соответствуют спецификации, либо ширина полосы должна соответствовать DPI принтера.  

В этом руководстве вы узнаете, как **создавать файлы штрих‑кода planet** с помощью библиотеки Aspose.BarCode, как управлять **пикселями XDimension**, и как переключаться между **заполненными полосами** и **пустыми полосами**, не переписывая код. В конце у вас будет два PNG‑файла — один с сплошными полосами, другой с пустыми — готовые для любой почтовой системы, использующей симбологию Planet.

## Требования

- .NET 6.0 или новее (код также работает на .NET Framework 4.7 +)  
- NuGet‑пакет Aspose.BarCode for .NET (`Install-Package Aspose.BarCode`)  
- Базовые знания C# (позже вы увидите, зачем нужны `using`‑операторы)  
- Папка, в которую приложение может записывать PNG‑файлы  

Если всё это у вас есть, можно сразу переходить к реализации.

## Шаг 1 – Создание проекта и подключение библиотеки

Сначала создайте новое консольное приложение (или любой проект C#) и добавьте ссылку на библиотеку **генератора штрих‑кода Planet**.

```csharp
using System;
using Aspose.BarCode.Generation;

namespace PlanetBarcodeDemo
{
    class Program
    {
        static void Main(string[] args)
        {
            // The rest of the code lives here
        }
    }
}
```

> **Совет:** В Visual Studio щёлкните правой кнопкой мыши по проекту → *Manage NuGet Packages* → найдите **Aspose.BarCode** и нажмите *Install*. Это даст вам доступ к `BarcodeGenerator` и всем необходимым **параметрам BarcodeGenerator**.

## Шаг 2 – Инициализация генератора штрих‑кода Planet

Теперь действительно **создаём экземпляр генератора штрих‑кода planet** и передаём ему данные, которые нужно закодировать (`"123456"` в этом примере). Перечисление `EncodeTypes.Planet` сообщает библиотеке, какую симбологию использовать.

```csharp
// Step 2: Initialise the generator with Planet symbology and data
BarcodeGenerator planetBarcode = new BarcodeGenerator(EncodeTypes.Planet, "123456");
```

> **Почему это важно:** Флаг `EncodeTypes.Planet` автоматически применяет правильные контрольные суммы и правила раскладки для почтового штрих‑кода Planet, так что вам не придётся рассчитывать их вручную.

## Шаг 3 – Настройка X‑Dimension (ширина полосы)

Большинство принтеров ожидают, что каждая полоса будет иметь определённое количество пикселей. Здесь мы задаём **пиксели XDimension** равными `4`, что является распространённым значением для термопринтеров с разрешением 203 dpi.

```csharp
// Step 3: Set the width of each bar (X‑dimension) to 4 pixels
planetBarcode.Parameters.Barcode.XDimension.Pixels = 4;
```

> **Особый случай:** Если вы нацелены на принтер с 300 dpi, вам может потребоваться `3` или `5` пикселей. Подберите значение, исходя из документации вашего устройства.

## Шаг 4 – Сохранение версии с заполненными полосами

По умолчанию генератор создаёт **заполненные полосы** (сплошные чёрные прямоугольники). Запишем их на диск:

```csharp
// Step 4: Save the barcode with default (filled) bars
planetBarcode.Save("YOUR_DIRECTORY/PostalPlanetFilledBars.png", BarCodeImageFormat.Png);
```

Замените `YOUR_DIRECTORY` на абсолютный или относительный путь, в который приложение имеет право записывать. После выполнения этой строки вы найдёте PNG‑файл, выглядящий как классический штрих‑код Planet — идеальный для тестирования с почтовым сканером.

## Шаг 5 – Переключение на пустые полосы

Иногда почтовые службы требуют стиль «пустые полосы», когда полосы вырезаются из белого фона вместо того, чтобы быть закрашенными чёрным. Библиотека предоставляет простой переключатель:

```csharp
// Step 5: Re‑configure the generator to produce empty bars
planetBarcode.Parameters.Barcode.FilledBars = false;
```

Установка `FilledBars` в `false` заставляет рендерер инвертировать логику заполнения полос. Не нужно создавать новый экземпляр `BarcodeGenerator`; достаточно изменить существующие **параметры BarcodeGenerator**.

## Шаг 6 – Сохранение версии с пустыми полосами

Наконец, экспортируем второе изображение:

```csharp
// Step 6: Save the barcode with empty bars
planetBarcode.Save("YOUR_DIRECTORY/PostalPlanetEmptyBars.png", BarCodeImageFormat.Png);
```

Теперь у вас есть два разных PNG‑файла, каждый соответствует своему визуальному требованию.

## Полный рабочий пример

Объединив все части, получаем готовую к копированию и вставке программу:

```csharp
using System;
using Aspose.BarCode.Generation;

namespace PlanetBarcodeDemo
{
    class Program
    {
        static void Main(string[] args)
        {
            // Initialise the Planet barcode generator with data
            BarcodeGenerator planetBarcode = new BarcodeGenerator(EncodeTypes.Planet, "123456");

            // Configure bar width (X‑dimension) – 4 pixels works for most 203 dpi printers
            planetBarcode.Parameters.Barcode.XDimension.Pixels = 4;

            // Save the default filled‑bars version
            planetBarcode.Save(@"C:\Barcodes\PostalPlanetFilledBars.png", BarCodeImageFormat.Png);

            // Switch to empty‑bars style
            planetBarcode.Parameters.Barcode.FilledBars = false;

            // Save the empty‑bars version
            planetBarcode.Save(@"C:\Barcodes\PostalPlanetEmptyBars.png", BarCodeImageFormat.Png);

            Console.WriteLine("Both Planet barcode images have been generated successfully.");
        }
    }
}
```

**Ожидаемый вывод** (в консоль):

```
Both Planet barcode images have been generated successfully.
```

А в `C:\Barcodes\` вы увидите:

- `PostalPlanetFilledBars.png` — сплошные чёрные полосы  
- `PostalPlanetEmptyBars.png` — белые полосы с чёрными контурами  

Откройте их в любом просмотрщике изображений; оба файла должны соответствовать спецификации Planet.

## Часто задаваемые вопросы и советы

### «Можно ли изменить формат изображения?»

Конечно. Метод `Save` принимает `BarCodeImageFormat.Jpeg`, `Bmp`, `Gif` и т.д. Просто замените `BarCodeImageFormat.Png` на нужный вам формат.

### «А если нужна другая высота штрих‑кода?»

Используйте `planetBarcode.Parameters.Barcode.BarHeight` (в пунктах), чтобы увеличить или уменьшить вертикальный размер. Например:

```csharp
planetBarcode.Parameters.Barcode.BarHeight = 30; // 30 points tall
```

### «Можно ли добавить читаемый человеком подпись?»

Да. Установите свойство `CodeText` у `planetBarcode.Parameters.Caption`:

```csharp
planetBarcode.Parameters.Caption.Visible = true;
planetBarcode.Parameters.Caption.TopMargin = 5; // space between barcode and text
planetBarcode.Parameters.Caption.Text = "123456";
```

### «Нужно ли освобождать генератор?»

`BarcodeGenerator` реализует `IDisposable`. Оберните его в блок `using`, если создаёте много штрих‑кодов в цикле:

```csharp
using (BarcodeGenerator gen = new BarcodeGenerator(...))
{
    // configure and save
}
```

### «Как обрабатывать ошибки?»

Оберните вызовы `Save` в блок `try…catch`, чтобы отлавливать `IOException` (проблемы с диском) или `ArgumentException` (некорректные параметры). Пример:

```csharp
try
{
    planetBarcode.Save(path, BarCodeImageFormat.Png);
}
catch (Exception ex)
{
    Console.Error.WriteLine($"Failed to save barcode: {ex.Message}");
}
```

## Итоги

Мы рассмотрели всё, что нужно для **создания штрих‑кода planet** в C#:

1. Инициализировать **генератор штрих‑кода Planet** с вашими данными.  
2. Настроить **пиксели XDimension** в соответствии со спецификациями принтера.  
3. Сохранить PNG с **заполненными полосами**.  
4. Переключить `FilledBars` для получения **пустых полос**.  
5. Сохранить второй PNG.  

Дальше вы можете изучать дополнительные **параметры BarcodeGenerator**, экспериментировать с другими симболологиями (`EncodeTypes.Postnet`, `EncodeTypes.Code128` и т.д.) или интегрировать изображения в почтовый рабочий процесс.

---

**Готовы к следующему шагу?** Попробуйте добавить QR‑код в тот же документ или сгенерировать пакет штрих‑кодов Planet из CSV‑списка с помощью цикла `foreach`. API Aspose.BarCode достаточно гибок для пакетных операций, пользовательских цветов и даже векторного вывода SVG.

Если возникнут проблемы, оставьте комментарий ниже или обратитесь к официальной документации Aspose.BarCode для более глубокого изучения продвинутых возможностей. Приятного кодинга!

## Что изучать дальше?

Следующие руководства охватывают смежные темы, построенные на техниках, продемонстрированных в этом пособии. Каждый ресурс содержит полностью работающие примеры кода с пошаговыми объяснениями, помогающими освоить дополнительные возможности API и исследовать альтернативные подходы в ваших проектах.

- [Create Barcode with Aspose - Set X & Y Dimensions in Java](/barcode/english/java/barcode-configuration/managing-x-y-dimension-barcode/)
- [How to create code128 barcode images in Java with Aspose.BarCode](/barcode/english/java/advanced-settings-and-optimization/saving-barcode-images-different-formats/)
- [How to create code128 barcode Java and set bar height](/barcode/english/java/barcode-configuration/setting-bars-height/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}