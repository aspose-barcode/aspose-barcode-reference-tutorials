---
category: general
date: 2026-11-20
description: Быстро создавайте изображение почтового штрихкода на C#. Узнайте, как
  генерировать штрихкоды Planet и RM4SCC с настраиваемыми стилями полос.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create postal barcode image
- generate planet barcode
- postal barcode C#
- Aspose.BarCode example
- barcode image generation
language: ru
lastmod: 2026-11-20
og_description: Создайте изображение почтового штрихкода в C# с помощью Aspose.BarCode.
  Этот учебник показывает, как генерировать штрихкод Planet, настраивать стили полос
  и создавать изображения RM4SCC.
og_image_alt: Create postal barcode image example showing filled and empty bars
og_title: Создание изображения почтового штрихкода в C# – пошаговое руководство
schemas:
- author: Aspose
  dateModified: '2026-11-20'
  description: Create postal barcode image in C# quickly. Learn how to generate planet
    barcode and RM4SCC barcodes with customizable bar styles.
  headline: Create postal barcode image and generate planet barcode
  type: TechArticle
tags:
- barcode
- C#
- Aspose
title: Создать изображение почтового штрихкода и сгенерировать планетарный штрихкод
url: /ru/python-java/general/create-postal-barcode-image-and-generate-planet-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Создание изображения почтового штрихкода и генерация штрихкода Planet

Создайте изображение почтового штрихкода на C# с помощью библиотеки Aspose.BarCode. Если вам нужно генерировать штрихкоды Planet или RM4SCC для почтовых приложений, этот учебник предоставляет готовое решение, готовое к запуску.

Генерация штрихкодов для почтовых служб часто требует точных размеров и возможности переключаться между заполненными и пустыми стилями полос. В этом руководстве показано, как настроить папку вывода, создать как заполненные, так и пустые штрихкоды Planet, а также создать штрихкод RM4SCC с теми же визуальными настройками. В конце у вас будет четыре PNG‑файла, которые можно сразу использовать в рабочем процессе рассылки.

## Требования

Прежде чем начать, убедитесь, что у вас есть:

* .NET 6.0 или более поздняя версия  
* Visual Studio 2022 (или любая другая IDE для C#)  
* Пакет **Aspose.BarCode** NuGet (`Install-Package Aspose.BarCode`)  

Дополнительная конфигурация не требуется; код использует только шрифт по умолчанию и PNG‑энкодер.

## Обзор создания изображения почтового штрихкода

В основе процесса находится класс `BarcodeGenerator`. Он принимает значение `EncodeTypes`, определяющее символьность штрихкода (например, `EncodeTypes.Planet` для штрихкода Planet). После настройки генератора вызывается `Save` для записи файла изображения.

![Create postal barcode image example](/images/postal_barcode_example.png)

*Alt text: Пример создания изображения почтового штрихкода, показывающий заполненные и пустые полосы.*

## Шаг 1: Настройка папки вывода

Сначала определите папку, в которой будут сохраняться PNG‑файлы. Подойдёт как абсолютный, так и относительный путь; просто убедитесь, что папка существует, либо позвольте коду создать её.

```csharp
using System.IO;
using Aspose.BarCode.Generation;

// Define the output folder (change to your own path)
string outputFolder = Path.Combine(Directory.GetCurrentDirectory(), "Barcodes");

// Ensure the directory exists
Directory.CreateDirectory(outputFolder);
```

Создание папки программно предотвращает `DirectoryNotFoundException`, когда учебник запускается на чистой машине.

## Шаг 2: Генерация штрихкода Planet с заполненными полосами

Штрихкод Planet со заполненными полосами является стилем по умолчанию. Следующий код создаёт штрихкод, задаёт X‑размер 4 пикселя (обычный размер для почтовых приложений) и сохраняет изображение.

```csharp
// Step 2: Generate a Planet barcode with filled bars
BarcodeGenerator planetFilled = new BarcodeGenerator(EncodeTypes.Planet, "123456");

// Set the X‑dimension (module width) to 4 pixels
planetFilled.Parameters.Barcode.XDimension.Pixels = 4;

// Save as PNG
string planetFilledPath = Path.Combine(outputFolder, "PostalPlanetFilledBars.png");
planetFilled.Save(planetFilledPath, BarCodeImageFormat.Png);
```

**Почему это работает:**  
* `EncodeTypes.Planet` указывает генератору использовать символьность Planet, требуемую многими почтовыми службами.  
* `XDimension.Pixels` управляет шириной каждой полосы; 4 px дают чёткое, сканируемое изображение без избыточного размера файла.  
* Метод `Save` автоматически выбирает PNG‑энкодер на основе перечисления `BarCodeImageFormat`.

## Шаг 3: Генерация штрихкода Planet с пустыми полосами

Некоторые почтовые спецификации предпочитают пустые (белые) полосы на тёмном фоне. Это достигается установкой `FilledBars` в `false`.

```csharp
// Step 3: Generate a Planet barcode with empty bars
BarcodeGenerator planetEmpty = new BarcodeGenerator(EncodeTypes.Planet, "123456");

// Keep the same X‑dimension for consistency
planetEmpty.Parameters.Barcode.XDimension.Pixels = 4;

// Disable filled bars – the bars become transparent (empty)
planetEmpty.Parameters.Barcode.FilledBars = false;

// Save the result
string planetEmptyPath = Path.Combine(outputFolder, "PostalPlanetEmptyBars.png");
planetEmpty.Save(planetEmptyPath, BarCodeImageFormat.Png);
```

**Совет:** Когда `FilledBars` равно `false`, генератор рисует полосы цветом фона (по умолчанию белый), а пробелы — цветом переднего плана (чёрный). Если нужен иной цветовой набор, измените `Parameters.Barcode.ForeColor` и `BackColor`.

## Шаг 4: Генерация штрихкода RM4SCC с заполненными полосами

RM4SCC — другая почтовая символьность, используемая в Соединённом Королевстве. Шаги создания аналогичны примеру с Planet; меняется только значение `EncodeTypes`.

```csharp
// Step 4: Generate an RM4SCC barcode with filled bars
BarcodeGenerator rm4sccFilled = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");

// Reuse the same X‑dimension for a uniform look
rm4sccFilled.Parameters.Barcode.XDimension.Pixels = 4;

// Save the PNG file
string rm4sccPath = Path.Combine(outputFolder, "PostalRM4SCCFilledBars.png");
rm4sccFilled.Save(rm4sccPath, BarCodeImageFormat.Png);
```

**Что ожидать:** Полученный PNG‑файл отображает компактный штрихкод RM4SCC, соответствующий британским почтовым требованиям. Размер изображения будет похож на штрихкоды Planet, поскольку X‑размер одинаковый.

## Шаг 5: Проверка сгенерированных изображений

После выполнения программы откройте четыре файла в папке `Barcodes`. Вы должны увидеть:

* `PostalPlanetFilledBars.png` — тёмные полосы на светлом фоне  
* `PostalPlanetEmptyBars.png` — светлые полосы на тёмном фоне (инверсия)  
* `PostalRM4SCCFilledBars.png` — стандартный шаблон RM4SCC  

Если какое‑либо изображение выглядит искажённым, проверьте следующее:

* **X‑размер** — слишком маленький (< 2 px) может вызвать размытие; слишком большой (> 10 px) может превысить ограничения размеров этикетки.  
* **Строка данных** — значение `"123456"` должно соответствовать требованиям длины выбранной символьности (Planet требует 6 цифр, RM4SCC также требует 6 цифр).  
* **Разрешения папки** — убедитесь, что приложение имеет права записи в каталог вывода.

## Распространённые варианты и граничные случаи

| Scenario | Adjustment |
|----------|------------|
| **Different barcode data** | Replace `"123456"` with any valid numeric string. For Planet, the length must be exactly 6 digits; RM4SCC also requires 6 digits. |
| **Custom colors** | Set `planetFilled.Parameters.Barcode.ForeColor = System.Drawing.Color.DarkBlue;` and `BackColor = System.Drawing.Color.LightYellow;`. |
| **Higher resolution** | Increase `XDimension.Pixels` to 6 or 8 for larger prints. |
| **Other image formats** | Use `BarCodeImageFormat.Jpeg` or `BarCodeImageFormat.Bmp` in the `Save` call. |
| **Batch generation** | Loop over a collection of strings and call the same generator logic inside the loop, reusing the `outputFolder` path. |

## Полный, готовый к запуску пример

Скопируйте код ниже в новый консольный проект C#. Он компилируется с .NET 6.0 и автоматически создаёт все четыре изображения штрихкодов.



## Что изучать дальше?

Следующие учебники охватывают тесно связанные темы, расширяющие техники, продемонстрированные в этом руководстве. Каждый ресурс включает полностью работающие примеры кода с пошаговыми объяснениями, помогая вам освоить дополнительные возможности API и исследовать альтернативные подходы в собственных проектах.

- [How to create postal barcode image with custom heights in C#](/barcode/english/python-java/general/how-to-create-postal-barcode-image-with-custom-heights-in-c/)
- [How to create RM4SCC barcode and generate planet barcode in C#](/barcode/english/python-java/general/how-to-create-rm4scc-barcode-and-generate-planet-barcode-in/)
- [Create postal barcode image in C# – step‑by‑step guide](/barcode/english/python-java/general/create-postal-barcode-image-in-c-step-by-step-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}