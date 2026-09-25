---
category: general
date: 2026-07-24
description: Создайте почтовый штрих‑код с помощью генератора штрих‑кодов на C#. Узнайте,
  как создать штрих‑код Planet и сохранить изображение штрих‑кода всего в несколько
  строк кода.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate postal barcode
- c# barcode generator
- create planet barcode
- barcode save image
language: ru
lastmod: 2026-07-24
og_description: Создайте почтовый штрих‑код с помощью генератора штрих‑кодов на C#,
  затем сохраните изображение штрих‑кода в формате PNG для почтовых приложений. Быстро,
  надёжно и полностью объяснено.
og_image_alt: Screenshot of a generated postal barcode image saved by a C# barcode
  generator
og_title: Создание почтового штрихкода в C# – Руководство Planet Barcode
schemas:
- author: Aspose
  dateModified: '2026-07-24'
  description: Generate postal barcode using a C# barcode generator. Learn how to
    create Planet barcode and barcode save image in just a few lines of code.
  headline: Generate Postal Barcode in C# – Complete Guide with Planet Barcode
  type: TechArticle
- description: Generate postal barcode using a C# barcode generator. Learn how to
    create Planet barcode and barcode save image in just a few lines of code.
  name: Generate Postal Barcode in C# – Complete Guide with Planet Barcode
  steps:
  - name: What if my data contains letters?
    text: Planet barcodes accept only numeric characters. If you need alphanumeric
      data, consider switching to **Code128** or **QR** symbologies—both are supported
      by the same **c# barcode generator** library.
  - name: How do I change the image format?
    text: The `Save` method accepts `BarCodeImageFormat.Jpeg`, `Gif`, `Bmp`, etc.
      Just replace `BarCodeImageFormat.Png` with the desired enum value. PNG is recommended
      for lossless quality, but JPEG can reduce file size for web‑based applications.
  - name: Can I set a custom foreground/background color?
    text: 'Absolutely. Use the `Parameters.Barcode.BarcodeColor` and `Parameters.Barcode.BackgroundColor`
      properties:'
  - name: What about high‑resolution printing (300 dpi+)?
    text: 'Increase the `Resolution` property on the `BarcodeGenerator`:'
  type: HowTo
tags:
- barcode
- C#
- Aspose.Barcode
title: Создание почтового штрихкода в C# – полное руководство с Planet Barcode
url: /ru/python-java/general/generate-postal-barcode-in-c-complete-guide-with-planet-barc/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Создание почтового штрихкода в C# – Полное руководство с Planet Barcode

Когда‑нибудь вам нужно было **создать почтовый штрихкод** в проекте .NET, но вы не знали, какой API выбрать? Вы не одиноки — многие разработчики сталкиваются с этой проблемой при создании почтовых решений, особенно когда почтовая служба требует конкретную символьную схему **Planet**.  

В этом руководстве мы пройдем весь процесс с использованием **C# barcode generator**, покажем, как **create Planet barcode** объекты, и продемонстрируем лучший способ **barcode save image** файлов, чтобы они были готовы к печати или цифровому использованию. К концу у вас будет два готовых PNG: один с заполненными полосами, другой с пустыми полосами, точно в соответствии с требованиями почтовой спецификации.

## Необходимые условия

- .NET 6.0 или новее (код также работает на .NET Framework 4.6+)
- Ссылка на библиотеку **Aspose.BarCode for .NET** (или любой совместимый класс `BarcodeGenerator`)
- Базовые знания C# — если вы умеете писать `Console.WriteLine`, вы готовы приступить  

Никаких дополнительных сервисов, без облачных вызовов, только локальный пакет NuGet и несколько строк кода.

---

## Шаг 1: Установите библиотеку C# Barcode Generator

Сначала добавьте библиотеку в ваш проект. Мы будем использовать NuGet, потому что это самый простой способ.

```bash
dotnet add package Aspose.BarCode
```

> **Совет:** Если вы нацелены на .NET Framework, откройте NuGet Package Manager в Visual Studio и найдите **Aspose.BarCode**.

Установка пакета дает вам доступ к классу `BarcodeGenerator`, который является ядром нашего рабочего процесса **c# barcode generator**.

## Шаг 2: Создайте простое консольное приложение

Создайте новый консольный проект (или добавьте код в существующий). Скелет выглядит так:

```csharp
using System;
using Aspose.BarCode.Generation;   // <-- core namespace
using Aspose.BarCode;               // for BarCodeImageFormat

namespace PostalBarcodeDemo
{
    class Program
    {
        static void Main(string[] args)
        {
            // We'll fill this in in the next steps.
        }
    }
}
```

Запуск этой пустой программы не должен выводить ничего, но подтверждает, что компилятор видит ссылки `Aspose.BarCode`.

## Шаг 3: Создайте почтовый штрихкод – заполненные полосы

Теперь мы **generate postal barcode** с классическим стилем заполненных полос. Символика Planet ожидает числовую строку; здесь мы используем `"123456"` как пример.

```csharp
// Step 3.1: Create a Planet barcode generator with the data to encode
BarcodeGenerator filledGenerator = new BarcodeGenerator(EncodeTypes.Planet, "123456");

// Step 3.2: Define the width of each bar (4 pixels works well for most printers)
filledGenerator.Parameters.Barcode.XDimension.Pixels = 4;

// Step 3.3: Save the barcode image – bars are filled by default
filledGenerator.Save("PostalPlanetFilledBars.png", BarCodeImageFormat.Png);
```

**Почему такие настройки?**  
- `EncodeTypes.Planet` сообщает библиотеке, что нам нужен формат **Planet**, который является стандартом для многих почтовых служб.  
- `XDimension.Pixels` управляет физической шириной полосы; 4 px дают чёткое, сканируемое изображение на обычных принтерах этикеток.  
- Вызов `Save` выполняет операцию **barcode save image**. Мы выбираем PNG, потому что он сохраняет детали без потерь, что важно для печати высокого разрешения.  

Когда вы запустите программу, вы найдете `PostalPlanetFilledBars.png` в рабочем каталоге исполняемого файла. Откройте его, и вы увидите ряд тёмных вертикальных полос — именно то, что ожидает почтовая служба.

## Шаг 4: Создайте почтовый штрихкод – вариант с пустыми полосами

Некоторые почтовые спецификации (или бренд‑гайды) требуют стиль «пустых» полос, где фон тёмный, а полосы прозрачные. Чтобы достичь этого, мы снова **create planet barcode**, но переключим единственное свойство.

```csharp
// Step 4.1: Create a second Planet barcode generator for the same data
BarcodeGenerator emptyGenerator = new BarcodeGenerator(EncodeTypes.Planet, "123456");

// Step 4.2: Reuse the same bar width
emptyGenerator.Parameters.Barcode.XDimension.Pixels = 4;

// Step 4.3: Configure the barcode to render empty bars (filled bars = false)
emptyGenerator.Parameters.Barcode.FilledBars = false;

// Step 4.4: Save the barcode image with empty bars
emptyGenerator.Save("PostalPlanetEmptyBars.png", BarCodeImageFormat.Png);
```

**Что изменилось?** Единственное различие — `FilledBars = false`. Это меняет режим рендеринга, создавая изображение, где полосы являются «дырами» в тёмном поле — идеально для некоторых этикеток, уже имеющих тёмный фон.

## Шаг 5: Проверьте результат

После двух вызовов `Save` у вас должно быть два PNG‑файла рядом:

| File | Описание визуального вида |
|------|---------------------------|
| `PostalPlanetFilledBars.png` | Тёмные полосы на белом фоне — классический почтовый вид |
| `PostalPlanetEmptyBars.png` | Светлые «полосы», вырезанные из тёмного фона — стиль пустых полос |

![Пример генерации почтового штрихкода](example-barcode.png){: .center alt="Пример генерации почтового штрихкода"}

Если изображения выглядят размытыми, проверьте значение `XDimension.Pixels`; увеличение его до 5 или 6 может улучшить читаемость на принтерах с низким DPI.

## Часто задаваемые вопросы и особые случаи

### Что если мои данные содержат буквы?

Штрихкоды Planet принимают только числовые символы. Если вам нужны буквенно‑цифровые данные, рассмотрите переход на символьные схемы **Code128** или **QR** — обе поддерживаются той же библиотекой **c# barcode generator**.

### Как изменить формат изображения?

Метод `Save` принимает `BarCodeImageFormat.Jpeg`, `Gif`, `Bmp` и т.д. Просто замените `BarCodeImageFormat.Png` на нужное значение перечисления. PNG рекомендуется для качества без потерь, но JPEG может уменьшить размер файла для веб‑приложений.

### Можно ли задать пользовательский цвет переднего/фонового плана?

Абсолютно. Используйте свойства `Parameters.Barcode.BarcodeColor` и `Parameters.Barcode.BackgroundColor`:

```csharp
filledGenerator.Parameters.Barcode.BarcodeColor = System.Drawing.Color.DarkBlue;
filledGenerator.Parameters.Barcode.BackgroundColor = System.Drawing.Color.White;
```

### Что насчёт печати высокого разрешения (300 dpi+)?

Увеличьте свойство `Resolution` у `BarcodeGenerator`:

```csharp
filledGenerator.Parameters.ImageResolution.Dpi = 300;
```

Большее DPI приводит к большим файлам, но обеспечивает чёткую печать на принтерах этикеток.

## Полный рабочий пример

Объединив всё вместе, вот единая автономная программа, которую вы можете скопировать в `Program.cs` и запустить:

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

namespace PostalBarcodeDemo
{
    class Program
    {
        static void Main(string[] args)
        {
            // ---------- Filled‑bars Planet barcode ----------
            BarcodeGenerator filledGenerator = new BarcodeGenerator(EncodeTypes.Planet, "123456");
            filledGenerator.Parameters.Barcode.XDimension.Pixels = 4;          // bar width
            filledGenerator.Save("PostalPlanetFilledBars.png", BarCodeImageFormat.Png);
            Console.WriteLine("Filled‑bars barcode saved.");

            // ---------- Empty‑bars Planet barcode ----------
            BarcodeGenerator emptyGenerator = new BarcodeGenerator(EncodeTypes.Planet, "123456");
            emptyGenerator.Parameters.Barcode.XDimension.Pixels = 4;          // same bar width
            emptyGenerator.Parameters.Barcode.FilledBars = false;            // render empty bars
            emptyGenerator.Save("PostalPlanetEmptyBars.png", BarCodeImageFormat.Png);
            Console.WriteLine("Empty‑bars barcode saved.");

            // Optional: inform the user where the files are located
            Console.WriteLine($"Files saved to: {Environment.CurrentDirectory}");
        }
    }
}
```

Запустите `dotnet run` (или нажмите **F5** в Visual Studio), и вы увидите два подтверждающих сообщения, после чего появятся два PNG‑файла.

## Заключение

Теперь вы знаете, как **generate postal barcode** в C# с помощью надёжного **c# barcode generator**, как **create planet barcode** объекты с заполненными и пустыми стилями полос, а также точные шаги для **barcode save image** файлов для дальнейшей обработки.  

Далее вы можете изучить:

- Добавление читаемого человеком текста под штрихкодом (`Parameters.Barcode.CodeText`),
- Встраивание PNG в PDF‑счёт (см. **Aspose.PDF**),
- Автоматизация пакетной генерации для тысяч адресов.

Попробуйте, поиграйте с шириной полос, экспериментируйте с цветами, и вы быстро освоите создание почтовых штрихкодов в любой среде .NET. Приятного кодинга!

## Что изучать дальше?

Следующие руководства охватывают тесно связанные темы, которые опираются на техники, продемонстрированные в этом руководстве. Каждый ресурс включает полные рабочие примеры кода с пошаговыми объяснениями, чтобы помочь вам освоить дополнительные возможности API и исследовать альтернативные подходы к реализации в ваших проектах.

- [How to generate barcode java – Australia Post Barcode with Aspose](/barcode/english/java/barcode-configuration/generating-australia-post-barcode/)
- [Generate barcode image – Code 93 with Aspose.BarCode](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-code-93-configuration/)
- [How to Generate Barcode – Code 39 Configuration with Aspose.BarCode](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-code-39-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}