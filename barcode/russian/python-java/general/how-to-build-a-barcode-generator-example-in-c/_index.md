---
category: general
date: 2026-09-19
description: пример генератора штрихкодов, показывающий, как изменить высоту, создать
  DataBar Omni‑Directional и настроить размеры штрихкода для вывода изображения в
  C#
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- barcode generator example
- how to change height
- how to create databar
- adjust barcode dimensions
- create barcode image c#
language: ru
lastmod: 2026-09-19
og_description: пример генератора штрихкодов, который учит менять высоту, создавать
  DataBar Omni‑Directional и настраивать размеры штрихкода для PNG‑изображения на
  C#
og_image_alt: Screenshot of a DataBar Omni‑Directional barcode generated in C#
og_title: Пример генератора штрих‑кодов на C# – пошаговое руководство
schemas:
- author: Aspose
  dateModified: '2026-09-19'
  description: barcode generator example showing how to change height, create DataBar
    Omni‑Directional, and adjust barcode dimensions for C# image output
  headline: How to build a barcode generator example in C#
  type: TechArticle
tags:
- barcode
- C#
- Aspose.BarCode
title: Как создать пример генератора штрихкода на C#
url: /ru/python-java/general/how-to-build-a-barcode-generator-example-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Пример генератора штрих‑кодов на C# – полное руководство по программированию

Если вам нужен **пример генератора штрих‑кодов** для проекта .NET, это руководство покажет, как создать, настроить и сохранить штрих‑код DataBar Omni‑Directional с помощью C#. Вы узнаете, как изменить высоту, отрегулировать размеры штрих‑кода и вывести высококачественное PNG‑изображение — всё в одном исполняемом консольном приложении.

Ниже представлены все шаги от установки необходимого SDK до настройки X‑dimension и высоты штриха. По завершении урока у вас будет готовый генератор штрих‑кодов, который можно интегрировать в системы выставления счетов, учёта или любой процесс сканирования.

## Предварительные требования

Прежде чем начать, убедитесь, что у вас есть:

* .NET 6.0 SDK или более поздняя версия  
* Visual Studio 2022 (или любая IDE, поддерживающая .NET)  
* Действующая лицензия **Aspose.BarCode for .NET** (бесплатная пробная версия подходит для тестирования)  

Если вы предпочитаете другую библиотеку, концепции настройки размеров и сохранения изображения остаются теми же; просто замените вызовы API соответствующим образом.

## Шаг 1: Создание проекта и добавление пакета Aspose.BarCode

Создайте новый консольный проект и подключите библиотеку штрих‑кодов.

```bash
dotnet new console -n BarcodeDemo
cd BarcodeDemo
dotnet add package Aspose.BarCode
```

Команда `dotnet add package` загружает последнюю стабильную версию Aspose.BarCode, которая полностью поддерживает символы DataBar Omni‑Directional.

## Шаг 2: Написание полного примера генератора штрих‑кодов

Откройте **Program.cs** и замените его содержимое следующим кодом. Этот блок содержит полный **barcode generator example** — без пропусков.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Create a barcode generator for a DataBar Omni‑Directional symbol
            // The GTIN‑14 value "(01)12345678901231" is encoded as a numeric string.
            BarcodeGenerator generator = new BarcodeGenerator(
                EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");

            // 2️⃣ Adjust barcode dimensions
            // Set the X‑dimension (module width) to 2 pixels – this controls the thin bar width.
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // 3️⃣ How to change height
            // Set the bar height to 30 pixels. Height influences readability on larger scanners.
            generator.Parameters.Barcode.BarHeight.Pixels = 30;

            // 4️⃣ Optional: fine‑tune additional properties (quiet zone, color, etc.)
            generator.Parameters.Barcode.QrCodeErrorLevel = QRErrorLevel.LevelM; // example property
            generator.Parameters.ImageOptions.ForeColor = System.Drawing.Color.Black;
            generator.Parameters.ImageOptions.BackColor = System.Drawing.Color.White;

            // 5️⃣ Create barcode image C#
            // Save the generated barcode as a PNG file in the output folder.
            string outputPath = "DatabarOmniDirectional.png";
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"Barcode saved to {outputPath}");
        }
    }
}
```

### Почему важна каждая строка

* **Create a barcode generator** — Конструктор `BarcodeGenerator` связывает тип кодирования (`EncodeTypes.DatabarOmniDirectional`) с данными, которые вы хотите зашифровать. Это ядро шага **how to create databar**.  
* **Adjust barcode dimensions** — Свойство `XDimension.Pixels` задаёт ширину самого узкого штриха. Изменение этого значения влияет на общий размер и надёжность сканирования.  
* **How to change height** — Свойство `BarHeight.Pixels` контролирует вертикальный размер. Увеличение высоты улучшает читаемость для ручных сканеров, а уменьшение экономит место на небольших этикетках.  
* **Optional tweaks** — Установка цветов переднего/фонового плана или уровней коррекции ошибок необязательна, но демонстрирует, как расширить концепцию **adjust barcode dimensions**.  
* **Create barcode image C#** — Метод `Save` записывает штрих‑код на диск. Использование `BarCodeImageFormat.Png` обеспечивает безпотерьное сжатие, что идеально для большинства приложений.

## Шаг 3: Сборка и запуск примера

Скомпилируйте и выполните программу:

```bash
dotnet run
```

В консоли вы увидите вывод:

```
Barcode saved to DatabarOmniDirectional.png
```

В папке проекта появится файл **DatabarOmniDirectional.png**. При открытии изображения вы увидите чёткий штрих‑код DataBar Omni‑Directional, готовый к сканированию.

## Как изменить высоту после создания

Если требуется генерировать штрих‑коды с разной высотой, вынесите установку высоты в отдельный метод:

```csharp
static void SetBarHeight(BarcodeGenerator gen, int heightPixels)
{
    gen.Parameters.Barcode.BarHeight.Pixels = heightPixels;
}
```

Вызовите `SetBarHeight(generator, 45);` перед `Save`. Такой подход позволяет **how to change height** динамически, основываясь на вводе пользователя или файлах конфигурации.

## Как создавать DataBar Omni‑Directional штрих‑коды с разными данными

Символика DataBar Omni‑Directional поддерживает GTIN‑14, GTIN‑13 и другие числовые идентификаторы. Чтобы закодировать другое значение, просто замените строку в конструкторе:

```csharp
new BarcodeGenerator(EncodeTypes.DatabarOmniDirectional, "(01)98765432109876");
```

Помните, что данные должны быть числовыми и правильно отформатированы; иначе генератор бросит `BarcodeException`.

## Настройка размеров штрих‑кода для разных сценариев печати

Разные принтеры и размеры этикеток требуют различных X‑dimension и высот. Используйте таблицу ниже в качестве быстрой справки:

| Scenario                     | X‑Dimension (pixels) | Bar Height (pixels) |
|------------------------------|----------------------|---------------------|
| Small label (25 mm × 15 mm)  | 1                    | 20                  |
| Medium label (50 mm × 30 mm) | 2                    | 30                  |
| Large label (100 mm × 50 mm) | 3                    | 45                  |

Применяйте эти значения, задавая `generator.Parameters.Barcode.XDimension.Pixels` и `BarHeight.Pixels` соответственно.

## Pro tip: проверка сгенерированного штрих‑кода

Перед отправкой этикетки вы можете программно проверить её читаемость:

```csharp
using Aspose.BarCode.BarCodeRecognition;

// ...

BarCodeReader reader = new BarCodeReader(outputPath, DecodeType.DatabarOmniDirectional);
if (reader.Read())
{
    Console.WriteLine("Validation succeeded: " + reader.GetCodeText());
}
else
{
    Console.WriteLine("Validation failed – barcode may be unreadable.");
}
```

Этот фрагмент демонстрирует быструю проверку **adjust barcode dimensions**, гарантируя, что штрих‑код соответствует требованиям сканирования.

## Распространённые подводные камни и как их избежать

| Pitfall                              | Why it happens                              | Fix                                                                 |
|--------------------------------------|---------------------------------------------|---------------------------------------------------------------------|
| Using non‑numeric data for DataBar    | DataBar expects numeric GTIN formats        | Ensure the string matches the `(01)XXXXXXXXXXXXX` pattern.         |
| Setting X‑dimension to 0 or negative  | Library throws `ArgumentOutOfRangeException`| Use a minimum of 1 pixel; test on target printer first.            |
| Saving to a read‑only folder          | `UnauthorizedAccessException` on `Save`     | Choose a writable directory or run the app with appropriate rights.|
| Forgetting to dispose `BarCodeReader` | Memory leak in long‑running services        | Wrap the reader in a `using` block or call `Dispose()` manually.   |

Раннее устранение этих проблем экономит время отладки и повышает стабильность в продакшене.

## Полный перечень исходного кода

Ниже представлен полностью готовый к копированию программный код, реализующий **barcode generator example** от начала до конца.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;
using Aspose.BarCode.BarCodeRecognition;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // Create generator – how to create databar
            BarcodeGenerator generator = new BarcodeGenerator(
                EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");

            // Adjust barcode dimensions
            generator.Parameters.Barcode.XDimension.Pixels = 2;   // thin bar width
            generator.Parameters.Barcode.BarHeight.Pixels = 30; // how to change height

            // Optional visual tweaks
            generator.Parameters.ImageOptions.ForeColor = System.Drawing.Color.Black;
            generator.Parameters.ImageOptions.BackColor = System.Drawing.Color.White;

            // Save image – create barcode image c#
            string filePath = "DatabarOmniDirectional.png";
            generator.Save(filePath, BarCodeImageFormat.Png);
            Console.WriteLine($"Barcode saved to {filePath}");

            // Validate barcode (optional)
            using (BarCodeReader reader = new BarCodeReader(filePath, DecodeType.DatabarOmniDirectional))
            {
                if (reader.Read())
                    Console.WriteLine($"Validation succeeded: {reader.GetCodeText()}");
                else
                    Console.WriteLine("Validation failed – barcode may be unreadable.");
            }
        }
    }
}
```

Запуск этой программы создаёт PNG‑файл, выглядящий примерно так (для иллюстрации):

![DataBar Omni‑Directional barcode generated in C#](https://example.com/og-image.png "DataBar Omni‑Directional barcode generated in C#")

*Текст альтернативного изображения*: **DataBar Omni‑Directional штрих‑код, сгенерированный в C#** (соответствует `og_image_alt`).

## Заключение

Теперь у вас есть **barcode generator example**, демонстрирующий, как изменить высоту, как создавать символы DataBar Omni‑Directional и как **adjust barcode dimensions** для оптимального сканирования. Полный C#‑код сохраняет PNG‑изображение, проверяет его и может быть расширен для пакетной генерации или интеграции в веб‑службы.

Далее изучайте связанные темы, такие как **создание QR‑кодов с Aspose.BarCode**, **пакетная обработка нескольких значений штрих‑кодов** или **встраивание штрих‑кодов в PDF‑документы**. Все они опираются на те же фундаментальные принципы, рассмотренные в этом руководстве.

Счастливого кодинга, и пусть ваши штрих‑коды всегда читаются!

## Что стоит изучить дальше?

Следующие учебники охватывают тесно связанные темы, расширяющие техники, продемонстрированные в этом руководстве. Каждый ресурс содержит полностью работающие примеры кода с пошаговыми объяснениями, помогающими освоить дополнительные возможности API и исследовать альтернативные подходы в ваших проектах.

- [Barcode Generator Example – Build DataBar Image in C#](/barcode/english/python-java/general/barcode-generator-example-build-databar-image-in-c/)
- [How to Generate and Adjust Barcode Height for One-Dimensional Databar using Aspose.BarCode for .NET](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-barcode-height-adjustment/)
- [Barcode generator example in C# – set width and height](/barcode/english/python-java/general/barcode-generator-example-in-c-set-width-and-height/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}