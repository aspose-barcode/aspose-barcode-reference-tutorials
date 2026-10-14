---
category: general
date: 2026-09-29
description: Создайте штрих‑код Planet в C# с заполненными и пустыми полосами — пошаговое
  руководство с использованием Aspose.Barcode.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create planet barcode
- Planet barcode XDimension
- filled bars
- empty bars
- Aspose.Barcode C#
language: ru
lastmod: 2026-09-29
og_description: Быстро создайте планетарный штрих‑код на C#. Узнайте, как отрисовывать
  заполненные полосы, переключаться на пустые полосы и настраивать X‑размер с помощью
  Aspose.Barcode.
og_image_alt: 'Screenshot of two Planet barcodes: one with filled bars, one with empty
  bars'
og_title: Создайте планетарный штрих‑код с заполненными и пустыми полосами – учебник
  C#
schemas:
- author: Aspose
  dateModified: '2026-09-29'
  description: Create planet barcode in C# with both filled and empty bars – step‑by‑step
    guide using Aspose.Barcode.
  headline: How to create planet barcode with filled and empty bars
  type: TechArticle
- description: Create planet barcode in C# with both filled and empty bars – step‑by‑step
    guide using Aspose.Barcode.
  name: How to create planet barcode with filled and empty bars
  steps:
  - name: Changing the bar width
    text: If your label printer expects a different bar width, modify the `XDimension.Pixels`
      value. For high‑resolution printers, a value of **2** or **3** pixels may be
      preferable; for low‑resolution printers, **5** or **6** pixels can improve scan
      reliability.
  - name: Using a different image format
    text: Aspose.Barcode supports PNG, JPEG, BMP, GIF, and TIFF. Swap `BarCodeImageFormat.Png`
      with another enum value to match your downstream workflow.
  - name: Generating multiple barcodes in a loop
    text: When you need a batch of Planet barcodes (e.g., for a mailing list), wrap
      the generator logic in a `foreach` loop and change the data string each iteration.
  - name: Handling invalid input
    text: The Planet symbology accepts only numeric strings of **5‑8** digits. Supplying
      an invalid value throws an `ArgumentException`. Guard against this with a simple
      validation method.
  type: HowTo
tags:
- barcode
- C#
- Aspose
title: Как создать планетный штрих‑код с заполненными и пустыми полосами
url: /ru/python-java/general/how-to-create-planet-barcode-with-filled-and-empty-bars/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Как создать Planet barcode с заполненными и пустыми полосами

Если вам нужно **создать planet barcode** изображения в C#, это руководство покажет, как точно сгенерировать версии с заполненными‑бар и пустыми‑бар. Вы увидите, как установить ширину полосы (X‑dimension), переключить свойство `FilledBars` и сохранить результаты в виде PNG‑файлов — всё с помощью библиотеки Aspose.Barcode.

Создание почтовых штрих‑кодов является распространённой задачей для систем доставки, приложений списков рассылки и панелей логистики. К концу этого руководства у вас будет два готовых PNG‑файла, которые можно внедрять в отчёты, письма или печатные материалы.

## Предварительные требования

| Требование | Зачем это нужно |
|-------------|----------------|
| .NET 6.0 или новее | Обеспечивает среду выполнения для примера на C#. |
| Visual Studio 2022 (или любой C# IDE) | Позволяет компилировать и запускать код. |
| **Aspose.Barcode for .NET** NuGet package | Предоставляет класс `BarcodeGenerator` и `EncodeTypes.Planet`. Установите его с помощью `dotnet add package Aspose.Barcode`. |
| Разрешение на запись в папку на диске | Метод `Save` записывает PNG‑файлы по указанному пути. |

## Шаг 1: Настройте проект и импортируйте пространства имён

Создайте новый консольный проект (или добавьте код в существующий) и подключите пространство имён Aspose.Barcode.

```csharp
using System;
using Aspose.Barcode;
using Aspose.Barcode.Generation;
```

Эти директивы `using` дают вам доступ к `BarcodeGenerator`, `EncodeTypes` и перечислениям форматов изображений, необходимым для руководства.

## Шаг 2: Создайте Planet barcode с настройками по умолчанию (заполненные полосы)

Первый штрих‑код использует рендеринг библиотеки по умолчанию, который заполняет полосы.

```csharp
// Initialise a generator for the Planet (postal) barcode with sample data.
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(EncodeTypes.Planet, "123456");

// Optional: adjust the bar width (X dimension) to 4 pixels for clearer printing.
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 4;

// Save the image with filled bars.
string filledPath = @"C:\Barcodes\PlanetFilledBars.png";
barcodeGenerator.Save(filledPath, BarCodeImageFormat.Png);

Console.WriteLine($"Filled Planet barcode saved to: {filledPath}");
```

**Почему это работает:**  
`EncodeTypes.Planet` указывает Aspose.Barcode использовать символьность **Planet**, почтовый штрих‑код, используемый United States Postal Service. Свойство `XDimension` контролирует ширину каждой полосы; установка значения 4 пикселя даёт штрих‑код, который хорошо печатается на стандартных принтерах этикеток. По умолчанию `FilledBars` равно `true`, поэтому полосы отображаются сплошными.

## Шаг 3: Создайте Planet barcode с пустыми полосами

Чтобы сгенерировать те же данные с *пустыми* полосами, достаточно переключить флаг `FilledBars`, оставив остальные настройки без изменений.

```csharp
// Re‑use the same variable for clarity.
barcodeGenerator = new BarcodeGenerator(EncodeTypes.Planet, "123456");

// Keep the same X‑dimension for visual consistency.
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 4;

// Render empty bars instead of filled ones.
barcodeGenerator.Parameters.Barcode.FilledBars = false;

// Save the image with empty bars.
string emptyPath = @"C:\Barcodes\PlanetEmptyBars.png";
barcodeGenerator.Save(emptyPath, BarCodeImageFormat.Png);

Console.WriteLine($"Empty Planet barcode saved to: {emptyPath}");
```

**Почему это важно:**  
Некоторые почтовые системы требуют стиль **empty‑bars** для лучшей читаемости, когда штрих‑код печатается на тёмных фонах или используется контрастная цветовая схема. Установив `FilledBars = false`, генератор рисует только контуры полос, оставляя их внутреннюю часть прозрачной.

## Ожидаемый результат

После выполнения программы папка `C:\Barcodes` (или выбранный вами путь) будет содержать два PNG‑файла:

| Файл | Визуальное описание |
|------|---------------------|
| `PlanetFilledBars.png` | Полосы — сплошные чёрные прямоугольники на белом фоне. |
| `PlanetEmptyBars.png`  | Полосы — чёрные контуры; внутренняя часть каждой полосы прозрачна (виден фон). |

Оба изображения кодируют одну и ту же числовую строку `"123456"` и используют ширину полосы 4 пикселя, что обеспечивает их одинаковый внешний вид, за исключением стиля заполнения.

## Распространённые варианты и граничные случаи

### Изменение ширины полосы

Если ваш принтер этикеток ожидает другую ширину полосы, измените значение `XDimension.Pixels`. Для принтеров с высоким разрешением предпочтительнее значение **2** или **3** пикселя; для принтеров с низким разрешением **5** или **6** пикселей могут повысить надёжность сканирования.

```csharp
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 5; // example for coarse printers
```

### Использование другого формата изображения

Aspose.Barcode поддерживает PNG, JPEG, BMP, GIF и TIFF. Замените `BarCodeImageFormat.Png` другим значением перечисления, чтобы соответствовать вашему последующему рабочему процессу.

```csharp
barcodeGenerator.Save("Planet.tiff", BarCodeImageFormat.Tiff);
```

### Генерация нескольких штрих‑кодов в цикле

Когда требуется пакет Planet barcode (например, для списка рассылки), оберните логику генератора в цикл `foreach` и меняйте строку данных на каждой итерации.

```csharp
string[] postalCodes = { "123456", "654321", "112233" };
int index = 1;
foreach (var code in postalCodes)
{
    var gen = new BarcodeGenerator(EncodeTypes.Planet, code);
    gen.Parameters.Barcode.XDimension.Pixels = 4;
    gen.Save($@"C:\Barcodes\Planet_{index}_filled.png", BarCodeImageFormat.Png);
    gen.Parameters.Barcode.FilledBars = false;
    gen.Save($@"C:\Barcodes\Planet_{index}_empty.png", BarCodeImageFormat.Png);
    index++;
}
```

### Обработка некорректного ввода

Символьность Planet принимает только числовые строки длиной **5‑8** цифр. Передача недопустимого значения вызывает `ArgumentException`. Защититесь от этого простым методом валидации.

```csharp
bool IsValidPlanet(string value) => System.Text.RegularExpressions.Regex.IsMatch(value, @"^\d{5,8}$");

string data = "ABC123";
if (!IsValidPlanet(data))
{
    Console.WriteLine("Invalid Planet data – must be 5 to 8 digits.");
    return;
}
```

## Совет: Проверьте штрих‑код с помощью эмулятора сканера

Aspose.Barcode включает класс `BarcodeReader`, который можно использовать для подтверждения, что сгенерированное изображение декодируется обратно в исходные данные.

```csharp
using Aspose.Barcode.Reader;

// Verify filled barcode
using (BarCodeReader reader = new BarCodeReader(filledPath, DecodeType.Planet))
{
    if (reader.Read())
        Console.WriteLine($"Decoded from filled image: {reader.GetCodeText()}");
}

// Verify empty barcode
using (BarCodeReader reader = new BarCodeReader(emptyPath, DecodeType.Planet))
{
    if (reader.Read())
        Console.WriteLine($"Decoded from empty image: {reader.GetCodeText()}");
}
```

Если вывод показывает `"123456"` для обоих файлов, штрих‑код был сгенерирован корректно.

## Заключение

Теперь вы знаете, как **создать planet barcode** изображения в C# с заполненными и пустыми стилями полос, управлять **Planet barcode XDimension** и сохранять результаты в формате PNG с помощью библиотеки **Aspose.Barcode**. Регулируйте ширину полос, меняйте форматы изображений или перебирайте коллекцию значений, чтобы адаптировать процесс к любой почтовой системе.

Далее вы можете изучить:

* **Добавление читаемого человеком текста** под штрих‑кодом (`barcodeGenerator.Parameters.Caption.Show = true`).
* **Встраивание штрих‑кодов в PDF‑документы** с помощью Aspose.PDF.
* **Генерацию других почтовых символьностей**, таких как **USPS POSTNET** или **Intelligent Mail**.

Не стесняйтесь экспериментировать с параметрами и интегрировать код в вашу систему доставки или рассылки. Приятного кодинга!

## Что изучать дальше?

Следующие руководства охватывают тесно связанные темы, расширяющие техники, продемонстрированные в этом руководстве. Каждый ресурс содержит полностью работающие примеры кода с пошаговыми объяснениями, помогающими освоить дополнительные возможности API и исследовать альтернативные подходы в ваших проектах.

- [Создать Planet Barcode в C# – Полное пошаговое руководство](/barcode/english/python-java/general/create-planet-barcode-in-c-full-step-by-step-guide/)
- [Создать planet barcode в C# – полное программное руководство](/barcode/english/python-java/general/create-planet-barcode-in-c-complete-programming-guide/)
- [Генератор штрих‑кодов C# – пример создания Planet barcode и RM4SCC](/barcode/english/python-java/general/barcode-generator-c-create-planet-barcode-and-rm4scc-example/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}