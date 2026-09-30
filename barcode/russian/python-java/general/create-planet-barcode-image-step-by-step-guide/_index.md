---
category: general
date: 2026-07-27
description: Быстро создавайте изображение штрихкода планеты. Узнайте, как генерировать
  штрихкод планеты с помощью C# и настраивать заполненные или пустые полосы.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create planet barcode image
- how to generate planet barcode
- planet barcode C#
- barcode X‑dimension
- filled vs empty bars
language: ru
lastmod: 2026-07-27
og_description: Создайте изображение штрихкода планеты за секунды. Следуйте этому
  руководству, чтобы узнать, как генерировать штрихкод планеты, настраивать X‑размер
  и переключаться между заполненными и пустыми полосами.
og_image_alt: Screenshot showing a create planet barcode image with filled bars
og_title: Создать изображение штрихкода планеты — Полный учебник C#
schemas:
- author: Aspose
  dateModified: '2026-07-27'
  description: create planet barcode image quickly. Learn how to generate planet barcode
    with C# and customize filled or empty bars.
  headline: create planet barcode image – Step‑by‑Step Guide
  type: TechArticle
- description: create planet barcode image quickly. Learn how to generate planet barcode
    with C# and customize filled or empty bars.
  name: create planet barcode image – Step‑by‑Step Guide
  steps:
  - name: Why the X‑dimension matters
    text: The X‑dimension controls how wide each tiny bar (or “module”) is. A value
      of **4 pixels** yields a barcode that’s clear on screen and prints nicely on
      standard label printers. If you need a denser image for a high‑resolution print,
      bump the value up to 6 or 8.
  - name: Expected output
    text: Open the resulting `PostalPlanetFilledBars.png` and you should see a classic
      Planet barcode—solid vertical bars with a quiet zone on each side. It looks
      just like the example you’d find on a postal envelope.
  - name: What “FilledBars = false” does
    text: Setting `FilledBars` to `false` tells the rendering engine to draw only
      the bar outlines. This is useful when you need a lighter‑weight image for on‑screen
      display or when a printing guideline explicitly requires the empty style.
  - name: Expected output
    text: The `PostalPlanetEmptyBars.png` file shows the same pattern as before, but
      each bar is a thin line instead of a solid block. It’s perfect for low‑contrast
      printing on colored paper.
  - name: When to use RM4SCC
    text: RM4SCC is the Dutch “Postcode” barcode. If you’re building a multi‑country
      logistics platform, having both Planet and RM4SCC generators at hand saves you
      a lot of boilerplate code.
  - name: What if I need a different image format?
    text: Just swap `BarCodeImageFormat.Png` for `Jpeg`, `Bmp`, or `Gif`. The library
      handles the conversion automatically.
  - name: How do I change the barcode height?
    text: Use `planetFilled.Parameters.Barcode.BarHeight = 50; // height in points`
      (or pixels, depending on the library version). Higher values give you a taller
      barcode, which can improve scan reliability on low‑resolution scanners.
  - name: Can I embed the barcode directly into a PDF?
    text: Absolutely. The `Save` method returns a `byte[]` if you call the overload
      that writes to a stream. Feed that stream into a PDF generation library (e.g.,
      iTextSharp) and you’ve got a fully‑automated mailing label.
  - name: What if the data string contains non‑numeric characters?
    text: 'Planet and RM4SCC expect **numeric only** payloads. Passing letters will
      throw an `ArgumentException`. Validate your input first:'
  - name: Does the X‑dimension affect scanning speed?
    text: A larger X‑dimension creates a more robust barcode, which generally improves
      scanning speed, especially on low‑quality scanners. However, it also increases
      the physical size of the label, so balance readability with space constraints.
  type: HowTo
tags:
- barcode
- C#
- imaging
title: Создать изображение штрихкода планеты – пошаговое руководство
url: /ru/python-java/general/create-planet-barcode-image-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# создать planet barcode image – Полный учебник C#

Ever wondered **how to generate planet barcode** for a mailing system or a logistics app? You're not the first one scratching their head over that. In this tutorial we’ll walk through everything you need to **create planet barcode image** files, from the basics of the `BarcodeGenerator` class to tweaking the X‑dimension and swapping filled bars for empty ones.

Мы также взглянем на связанную символогию —RM4SCC—чтобы вы могли увидеть, как тот же шаблон работает для других почтовых штрихкодов. К концу у вас будет три готовых к запуску фрагмента, которые генерируют PNG‑файлы, готовые к использованию в вашем проекте.

## Что понадобится

- .NET 6.0 или новее (код также работает на .NET Framework 4.7+)  
- Ссылка на **Aspose.BarCode** (или любую библиотеку, предоставляющую `BarcodeGenerator`, `EncodeTypes`, `BarCodeImageFormat`)  
- IDE, с которой вам удобно работать — Visual Studio, Rider или VS Code подойдёт  
- Папка, в которую можно записывать изображения (замените `YOUR_DIRECTORY` в примерах)

Вот и всё. Дополнительных пакетов NuGet, кроме самой библиотеки штрихкодов, не требуется.

---

## Шаг 1: Настройка проекта и импортов

Для начала создадим небольшое консольное приложение, чтобы сразу запустить код.

```csharp
using System;
using Aspose.BarCode.Generation;   // Core barcode generator
using Aspose.BarCode;               // For BarCodeImageFormat enum

namespace PlanetBarcodeDemo
{
    class Program
    {
        static void Main(string[] args)
        {
            // We'll call helper methods here (see later)
            GeneratePlanetFilledBars();
            GeneratePlanetEmptyBars();
            GenerateRM4SCCFilledBars();
        }
```

> **Pro tip:** Держите ваш метод `Main` аккуратным; делегируйте каждый сценарий отдельному методу. Это делает код более читаемым и отражает три примера в оригинальном фрагменте.

---

## Шаг 2: **create planet barcode image** с заполненными полосами по умолчанию

Симвология Planet используется многими почтовыми службами для номеров отслеживания. Чтобы **create planet barcode image** с обычными сплошными полосами, выполните следующие три строки:

```csharp
        static void GeneratePlanetFilledBars()
        {
            // 1️⃣ Create a generator for the Planet symbology with data "123456"
            BarcodeGenerator planetFilled = new BarcodeGenerator(EncodeTypes.Planet, "123456");

            // 2️⃣ Set the X‑dimension (module width) to 4 pixels for better visibility
            planetFilled.Parameters.Barcode.XDimension.Pixels = 4;

            // 3️⃣ Save the barcode as a PNG image
            planetFilled.Save("YOUR_DIRECTORY/PostalPlanetFilledBars.png", BarCodeImageFormat.Png);
        }
```

### Почему X‑dimension важна
X‑dimension определяет ширину каждой маленькой полосы (или «модуля»). Значение **4 пикселя** даёт штрихкод, который чётко отображается на экране и хорошо печатается на стандартных принтерах этикеток. Если нужен более плотный рисунок для печати высокого разрешения, увеличьте значение до 6 или 8.

### Ожидаемый результат
Откройте полученный файл `PostalPlanetFilledBars.png`, и вы увидите классический штрихкод Planet — сплошные вертикальные полосы с зоной тишины по обеим сторонам. Он выглядит точно так же, как пример на почтовом конверте.

---

## Шаг 3: **create planet barcode image** с пустыми полосами

Иногда почтовая спецификация требует стиль *empty‑bar*, когда полосы являются контурами, а не сплошными заливками. Переключение в этот режим происходит одной сменой свойства.

```csharp
        static void GeneratePlanetEmptyBars()
        {
            // 1️⃣ Create the generator (same data as before)
            BarcodeGenerator planetEmpty = new BarcodeGenerator(EncodeTypes.Planet, "123456");

            // 2️⃣ Keep the X‑dimension consistent
            planetEmpty.Parameters.Barcode.XDimension.Pixels = 4;

            // 3️⃣ Disable filled bars → we get an empty‑bar representation
            planetEmpty.Parameters.Barcode.FilledBars = false;

            // 4️⃣ Save the PNG
            planetEmpty.Save("YOUR_DIRECTORY/PostalPlanetEmptyBars.png", BarCodeImageFormat.Png);
        }
```

### Что делает `FilledBars = false`
Установка `FilledBars` в `false` заставляет движок рендеринга рисовать только контуры полос. Это полезно, когда нужен более лёгкий образ для отображения на экране или когда руководство по печати явно требует пустой стиль.

### Ожидаемый результат
Файл `PostalPlanetEmptyBars.png` показывает тот же шаблон, что и раньше, но каждая полоса представлена тонкой линией вместо сплошного блока. Это идеально для печати с низким контрастом на цветной бумаге.

---

## Шаг 4: Генерация штрихкода RM4SCC (Бонус)

Несмотря на то, что наш основной фокус — симвология Planet, тот же API позволяет вам **create planet barcode image**‑подобные результаты для других почтовых кодов. Вот как **how to generate planet barcode**‑стильный вывод для RM4SCC:

```csharp
        static void GenerateRM4SCCFilledBars()
        {
            // 1️⃣ Create a generator for the RM4SCC symbology
            BarcodeGenerator rm4sccFilled = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");

            // 2️⃣ Align X‑dimension with the other examples
            rm4sccFilled.Parameters.Barcode.XDimension.Pixels = 4;

            // 3️⃣ Save the image
            rm4sccFilled.Save("YOUR_DIRECTORY/PostalRM4SCCFilledBars.png", BarCodeImageFormat.Png);
        }
    }
}
```

### Когда использовать RM4SCC
RM4SCC — это голландский штрихкод «Postcode». Если вы создаёте многостранную логистическую платформу, наличие генераторов как Planet, так и RM4SCC экономит массу шаблонного кода.

---

## Часто задаваемые вопросы и особые случаи

### Что если мне нужен другой формат изображения?
Просто замените `BarCodeImageFormat.Png` на `Jpeg`, `Bmp` или `Gif`. Библиотека автоматически выполнит конвертацию.

### Как изменить высоту штрихкода?
Используйте `planetFilled.Parameters.Barcode.BarHeight = 50; // высота в пунктах` (или пикселях, в зависимости от версии библиотеки). Большие значения дают более высокий штрихкод, что может улучшить надёжность сканирования на сканерах низкого разрешения.

### Можно ли встроить штрихкод напрямую в PDF?
Конечно. Метод `Save` возвращает `byte[]`, если вызвать перегрузку, записывающую в поток. Передайте этот поток в библиотеку генерации PDF (например, iTextSharp), и вы получите полностью автоматизированную почтовую этикетку.

### Что если строка данных содержит нечисловые символы?
Planet и RM4SCC ожидают **только числовые** данные. Передача букв вызовет `ArgumentException`. Сначала проверьте ввод:

```csharp
if (!Regex.IsMatch(data, @"^\d+$"))
    throw new ArgumentException("Planet barcode data must be numeric.");
```

### Влияет ли X‑dimension на скорость сканирования?
Большее значение X‑dimension создаёт более надёжный штрихкод, что обычно повышает скорость сканирования, особенно на сканерах низкого качества. Однако это также увеличивает физический размер этикетки, поэтому необходимо балансировать читаемость и ограничения по пространству.

---

## Полный рабочий пример (Все три метода)

Ниже полная программа, которую можно скопировать и вставить в новый консольный проект. Замените `YOUR_DIRECTORY` на абсолютный или относительный путь, в который ваше приложение может записывать.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

namespace PlanetBarcodeDemo
{
    class Program
    {
        static void Main(string[] args)
        {
            GeneratePlanetFilledBars();
            GeneratePlanetEmptyBars();
            GenerateRM4SCCFilledBars();

            Console.WriteLine("All barcode images have been saved.");
        }

        static void GeneratePlanetFilledBars()
        {
            BarcodeGenerator planetFilled = new BarcodeGenerator(EncodeTypes.Planet, "123456");
            planetFilled.Parameters.Barcode.XDimension.Pixels = 4;
            planetFilled.Save("YOUR_DIRECTORY/PostalPlanetFilledBars.png", BarCodeImageFormat.Png);
        }

        static void GeneratePlanetEmptyBars()
        {
            BarcodeGenerator planetEmpty = new BarcodeGenerator(EncodeTypes.Planet, "123456");
            planetEmpty.Parameters.Barcode.XDimension.Pixels = 4;
            planetEmpty.Parameters.Barcode.FilledBars = false;
            planetEmpty.Save("YOUR_DIRECTORY/PostalPlanetEmptyBars.png", BarCodeImageFormat.Png);
        }

        static void GenerateRM4SCCFilledBars()
        {
            BarcodeGenerator rm4sccFilled = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");
            rm4sccFilled.Parameters.Barcode.XDimension.Pixels = 4;
            rm4sccFilled.Save("YOUR_DIRECTORY/PostalRM4SCCFilledBars.png", BarCodeImageFormat.Png);
        }
    }
}
```

Запустите программу, откройте три PNG‑файла, и вы увидите точно те изображения, которые описаны выше. Дополнительная настройка не требуется.

---

## Итоги и дальнейшие шаги

Мы рассмотрели **how to generate planet barcode** изображения с нуля, переключение между сплошными и контурными стилями, а также расширение того же подхода на RM4SCC. Ключевые выводы:

1. Создайте экземпляр `BarcodeGenerator` с правильным `EncodeTypes` и данными.  
2. Настройте `XDimension.Pixels` для управления шириной полос.  
3. Используйте `FilledBars = false` для варианта с пустыми полосами.  
4. Сохраните результат в предпочитаемом вами формате изображения.

Теперь, когда вы можете **create planet barcode image** файлы, рассмотрите следующие идеи:

- **Пакетная генерация**: Пройтись по CSV с номерами отслеживания и сохранить PNG для каждого.  
- **Динамический размер**: Открыть X‑dimension и высоту полос как параметры конфигурации в веб‑API.  
- **Интеграция с принтерами этикеток**: Отправить байты PNG напрямую на принтер, совместимый с ZPL, для создания этикетки «на лету».

Не стесняйтесь экспериментировать — меняйте строку данных, пробуйте разные размеры или комбинируйте штрихкод с QR‑кодом на одной этикетке. Библиотека штрихкодов достаточно гибкая, чтобы справиться со всем этим.

Есть сложный сценарий, в котором не уверены? Оставьте комментарий ниже, и мы разберёмся вместе. Счастливого кодинга!

## Что изучать дальше?

Следующие учебники охватывают тесно связанные темы, построенные на техниках, продемонстрированных в этом руководстве. Каждый ресурс включает полные рабочие примеры кода с пошаговыми объяснениями, чтобы помочь вам освоить дополнительные возможности API и исследовать альтернативные подходы к реализации в ваших проектах.

- [Создать изображение штрихкода DotCode – строки и столбцы (Aspose.BarCode)](/barcode/english/net/dotcode-barcode-configuration/dotcode-rows-columns-configuration/)
- [Создать изображение штрихкода C# – пример GS1 DataMatrix](/barcode/english/net/gs1-barcode-encoding/gs1-datamatrix-example/)
- [Создать изображение штрихкода c# – настройка строк и столбцов Codablock F](/barcode/english/net/codablock-f-encoding/codablock-f-row-column-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}