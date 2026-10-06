---
category: general
date: 2026-08-19
description: Быстро генерируйте штрих‑код PDF417 на C#. Узнайте, как генерировать
  штрих‑код PDF417 в C# с помощью Aspose.BarCode в компактном режиме и с пользовательскими
  настройками.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate pdf417 barcode
- how to generate pdf417 barcode c#
- Aspose.BarCode PDF417
- compact PDF417 barcode
- barcode X‑dimension
language: ru
lastmod: 2026-08-19
og_description: Создайте штрих‑код PDF417 на C# с помощью Aspose.BarCode. Этот учебник
  показывает, как генерировать штрих‑код PDF417 на C# в компактном режиме, установить
  X‑размер и сохранить в PNG.
og_image_alt: Screenshot of a compact PDF417 barcode saved as PNG
og_title: Создание штрих‑кода PDF417 на C# – пошаговое руководство
schemas:
- author: Aspose
  dateModified: '2026-08-19'
  description: Generate PDF417 barcode in C# quickly. Learn how to generate PDF417
    barcode C# using Aspose.BarCode with compact mode and custom settings.
  headline: Generate PDF417 barcode in C# – complete guide with compact layout
  type: TechArticle
- description: Generate PDF417 barcode in C# quickly. Learn how to generate PDF417
    barcode C# using Aspose.BarCode with compact mode and custom settings.
  name: Generate PDF417 barcode in C# – complete guide with compact layout
  steps:
  - name: Why each line matters
    text: '* **`EncodeTypes.Pdf417`** – selects the PDF417 symbology, which supports
      up to ~1.1 KB of data. * **`XDimension.Pixels = 2`** – sets the basic bar width.
      Smaller values make the barcode thinner; larger values improve readability on
      low‑resolution devices. * **`Pdf417.Columns = 3`** – limits the num'
  - name: 4️⃣ Generate a high‑density PDF417 for printing
    text: 'If you need a barcode that fits on a small label, increase the column count
      and lower the X‑dimension:'
  - name: 5️⃣ Change the output format to SVG for vector scaling
    text: '```csharp generator.Save("CompactPdf417.svg", BarCodeImageFormat.Svg);
      ```'
  - name: 6️⃣ Encode binary data (e.g., a byte array)
    text: 'If you need to embed binary payloads, convert them to a Base64 string first:'
  type: HowTo
tags:
- barcode
- C#
- Aspose
title: Генерация штрихкода PDF417 в C# – полное руководство с компактным макетом
url: /ru/net/compact-pdf417-encoding/generate-pdf417-barcode-in-c-complete-guide-with-compact-lay/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Генерация PDF417 barcode в C# – полное руководство

Если вам нужно **generate PDF417 barcode** в приложении .NET, этот учебник покажет, как это сделать. Вы увидите лаконичный, готовый к продакшну пример, который создает компактный PDF417 штрих‑код, настраивает X‑dimension и сохраняет результат в виде PNG‑изображения.

Создание PDF417 штрих‑кода часто требуется, когда нужно закодировать большие объёмы данных — например, информацию о билетах, транспортных накладных или удостоверениях личности — в машинно‑читаемом формате. Использование Aspose.BarCode упрощает процесс, а код работает с .NET 6+ или .NET Framework 4.7.2 и новее.

В этом руководстве вы:

* Установить пакет NuGet Aspose.BarCode.
* Написать автономную программу на C#, которая **generates PDF417 barcode** с небольшим количеством столбцов и в компактном (усечённом) режиме.
* Отрегулировать ширину полос (X‑dimension) для более чёткого отображения.
* Сохранить штрих‑код в файл PNG.
* Исследовать варианты, граничные случаи и рекомендации лучших практик.

## Предварительные требования

Перед началом убедитесь, что у вас есть:

* Visual Studio 2022 (или любой IDE для C#) с установленным .NET 6 SDK.
* Доступ к Интернету для загрузки пакета NuGet **Aspose.BarCode**.
* Права записи в папку, где будет сохраняться файл PNG.

Дополнительные библиотеки не требуются; Aspose.BarCode обрабатывает кодирование изображения внутри.

## Шаг 1: Добавьте пакет Aspose.BarCode

Откройте ваш проект в Visual Studio, щёлкните правой кнопкой мыши по решению и выберите **Manage NuGet Packages**. Найдите `Aspose.BarCode` и установите последнюю стабильную версию.

```bash
dotnet add package Aspose.BarCode
```

> **Pro tip:** Держите пакет в актуальном состоянии. Новые версии часто включают улучшения производительности и поддержку последних .NET рантаймов.

## Шаг 2: Создайте минимальное консольное приложение

Создайте новый C# консольный проект, если у вас его ещё нет:

```bash
dotnet new console -n Pdf417Demo
cd Pdf417Demo
```

Замените содержимое `Program.cs` полным примером ниже. Эта программа демонстрирует **how to generate PDF417 barcode C#** от начала до конца.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode.BarCodeImageFormat;

namespace Pdf417Demo
{
    class Program
    {
        static void Main(string[] args)
        {
            // -----------------------------------------------------------------
            // 1️⃣  Define the data you want to encode.
            // -----------------------------------------------------------------
            // The string can contain Unicode characters; Aspose.BarCode handles
            // encoding automatically. Here we use characters with diacritics to
            // prove Unicode support.
            string data = "Åspóse.Barcóde©";

            // -----------------------------------------------------------------
            // 2️⃣  Initialise the BarcodeGenerator for PDF417.
            // -----------------------------------------------------------------
            // EncodeTypes.Pdf417 tells the library which symbology to use.
            // The constructor also accepts the data to encode.
            BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, data);

            // -----------------------------------------------------------------
            // 3️⃣  Configure visual parameters.
            // -----------------------------------------------------------------
            // • XDimension controls the bar width in pixels. A value of 2 gives
            //   a clear, readable barcode on most screens.
            // • Columns define how many data columns the barcode will use.
            //   Fewer columns produce a more compact image but increase the
            //   number of rows.
            // • Truncate enables “compact mode”, which removes the trailing
            //   stop pattern and reduces the overall size.
            generator.Parameters.Barcode.XDimension.Pixels = 2;
            generator.Parameters.Barcode.Pdf417.Columns = 3;
            generator.Parameters.Barcode.Pdf417.Truncate = true; // compact mode

            // -----------------------------------------------------------------
            // 4️⃣  Choose the output format and save the image.
            // -----------------------------------------------------------------
            // BarCodeImageFormat.Png yields a lossless PNG file that works
            // well for web, print, and further image processing.
            string outputPath = "CompactPdf417.png";
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"PDF417 barcode saved to: {outputPath}");
        }
    }
}
```

### Почему каждая строка важна

* **`EncodeTypes.Pdf417`** – выбирает символьный набор PDF417, поддерживающий до ~1.1 KB данных.
* **`XDimension.Pixels = 2`** – задаёт базовую ширину полосы. Меньшие значения делают штрих‑код тоньше; большие значения повышают читаемость на устройствах с низким разрешением.
* **`Pdf417.Columns = 3`** – ограничивает количество столбцов, заставляя генератор использовать больше строк, что приводит к более высокому, но уже штрих‑коду.
* **`Pdf417.Truncate = true`** – активирует компактный режим, удаляя стоп‑шаблон и уменьшая изображение без потери целостности данных.
* **`Save(..., BarCodeImageFormat.Png)`** – сохраняет файл PNG. Вы также можете выбрать `Jpeg`, `Bmp` или `Svg` в зависимости от последующих требований.

Запустите программу:

```bash
dotnet run
```

Вы должны увидеть вывод в консоли, подтверждающий расположение файла, а в папке появится `CompactPdf417.png`. Открытие PNG покажет чёткий, компактный PDF417 штрих‑код, кодирующий Unicode‑строку.

## Шаг 3: Проверьте штрих‑код (необязательно, но рекомендуется)

Чтобы убедиться, что штрих‑код читается, вы можете использовать любое стандартное приложение‑сканер PDF417 на смартфоне или библиотеку декодера на ПК. Закодированный текст должен точно соответствовать исходной строке `data`, включая специальные символы.

Если вы столкнётесь с проблемами декодирования:

* Увеличьте `XDimension` до 3 или 4 пикселей.
* Уменьшите количество столбцов (например, установить `Columns = 2`).
* Отключите `Truncate` (`Truncate = false`), чтобы добавить стоп‑шаблон.

Эти настройки меняют размер в пользу читаемости, что полезно для принтеров или сканеров с низким разрешением.

## Шаг 4: Исследуйте распространённые варианты

### 4️⃣ Сгенерировать высокоплотный PDF417 для печати

Если вам нужен штрих‑код, который помещается на небольшой этикетке, увеличьте количество столбцов и уменьшите X‑dimension:

```csharp
generator.Parameters.Barcode.XDimension.Pixels = 1;
generator.Parameters.Barcode.Pdf417.Columns = 6;
generator.Parameters.Barcode.Pdf417.Truncate = false; // keep full pattern
```

### 5️⃣ Изменить формат вывода на SVG для векторного масштабирования

SVG вывод масштабируется без потери качества, идеально подходит для адаптивных веб‑страниц.

```csharp
generator.Save("CompactPdf417.svg", BarCodeImageFormat.Svg);
```

### 6️⃣ Кодировать бинарные данные (например, массив байтов)

Если вам нужно внедрить бинарные полезные нагрузки, сначала преобразуйте их в строку Base64:

```csharp
byte[] payload = new byte[] { 0x01, 0xFF, 0xA5 };
string base64 = Convert.ToBase64String(payload);
generator = new BarcodeGenerator(EncodeTypes.Pdf417, base64);
```

Теперь штрих‑код содержит бинарную информацию, а декодер должен выполнить обратное преобразование Base64.

## Часто задаваемые вопросы

| Question | Answer |
|----------|--------|
| **Могу ли я генерировать PDF417 без Aspose?** | Да, существуют другие библиотеки, такие как ZXing.Net или Dynamsoft, но Aspose.BarCode предоставляет более гибкое управление макетом (столбцы, усечение) и лучшую работу с Unicode. |
| **Какова максимальная длина данных?** | PDF417 может кодировать до 1 108 байт (≈ 1 KB) бинарных данных. Если вы превысите этот предел, рассмотрите возможность разбить данные на несколько штрих‑кодов. |
| **Соответствует ли компактный режим стандартам?** | Усечённый PDF417 является частью спецификации ISO/IEC 15438 и широко поддерживается, однако убедитесь, что ваш сканер явно поддерживает его. |
| **Как изменить цвет фона?** | Установите `generator.Parameters.Barcode.BackColor = System.Drawing.Color.White;` и `generator.Parameters.Barcode.ForeColor = System.Drawing.Color.Black;` перед сохранением. |

## Заключение

Теперь вы знаете **how to generate PDF417 barcode C#** с помощью Aspose.BarCode, как точно настроить X‑dimension, включить компактный режим и экспортировать результат в виде PNG‑изображения. Полный, готовый к запуску пример можно скопировать в любой проект .NET, а показанные варианты позволяют адаптировать штрих‑код для печати, веб‑использования или сценариев с бинарными полезными нагрузками.

Следующие шаги, которые вы можете изучить:

* Интегрировать генерацию штрих‑кода в ASP.NET Core API, который возвращает изображение по запросу.
* Скомбинировать PDF417 с QR‑кодами на одной этикетке для двойного сканирования.
* Использовать класс Aspose.BarCode `Reader` для декодирования сгенерированного изображения и программной проверки данных.

Удачной разработки, и наслаждайтесь гибкостью, которую решения **generate PDF417 barcode** приносят в ваши приложения!

## Что изучать дальше?

Следующие учебники охватывают тесно связанные темы, построенные на техниках, продемонстрированных в этом руководстве. Каждый ресурс включает полные рабочие примеры кода с пошаговыми объяснениями, чтобы помочь вам освоить дополнительные возможности API и исследовать альтернативные подходы к реализации в ваших проектах.

- [Как создать штрих‑код – Compact PDF417 с Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [Как сгенерировать изображение штрих‑кода с настройкой дополнительного пространства с помощью Aspose.BarCode](/barcode/english/net/supplemental-barcode-data/supplemental-barcode-space-customization/)
- [Как сгенерировать Aztec штрих‑код с пользовательским соотношением сторон с помощью Aspose.BarCode для .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}