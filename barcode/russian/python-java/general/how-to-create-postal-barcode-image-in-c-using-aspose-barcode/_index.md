---
category: general
date: 2026-10-02
description: Создайте изображение почтового штрихкода на C# с помощью Aspose.BarCode.
  Узнайте, как генерировать штрихкоды Planet и RM4SCC, настраивать заполненные полосы
  и сохранять файлы PNG.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create postal barcode image
- generate planet barcode
- Aspose.BarCode C#
- postal barcode PNG
- barcode XDimension setting
language: ru
lastmod: 2026-10-02
og_description: Создайте изображение почтового штрихкода на C# с помощью Aspose.BarCode.
  В этом руководстве показано, как генерировать штрихкоды Planet и RM4SCC, настраивать
  заливку полос и экспортировать файлы PNG.
og_image_alt: Postal barcode image generated with Aspose.BarCode (filled bars)
og_title: Создание изображения почтового штрихкода в C# – пошаговое руководство
schemas:
- author: Aspose
  dateModified: '2026-10-02'
  description: Create postal barcode image in C# with Aspose.BarCode. Learn to generate
    Planet and RM4SCC barcodes, customize filled bars, and save PNG files.
  headline: How to create postal barcode image in C# using Aspose.BarCode
  type: TechArticle
- description: Create postal barcode image in C# with Aspose.BarCode. Learn to generate
    Planet and RM4SCC barcodes, customize filled bars, and save PNG files.
  name: How to create postal barcode image in C# using Aspose.BarCode
  steps:
  - name: Why each line matters
    text: '* **`new BarcodeGenerator(EncodeTypes.Planet, "123456")`** – The `EncodeTypes.Planet`
      enum tells Aspose.BarCode to use the *Planet* symbology, which is a standard
      postal barcode in many countries. This is the core of how you **generate planet
      barcode** images. * **`XDimension.Pixels = 4`** – The wid'
  - name: Expected output
    text: 'After running the program, the `YOUR_DIRECTORY` folder contains three PNG
      files:'
  - name: Change image format
    text: If you need a different format (e.g., JPEG for web delivery), replace `BarCodeImageFormat.Png`
      with `BarCodeImageFormat.Jpeg`. Keep in mind that JPEG introduces compression
      artifacts, which can affect scanner performance.
  - name: Adjust image size without scaling
    text: Instead of changing `XDimension`, you can control the overall image dimensions
      via `Parameters.Image.Height` and `Parameters.Image.Width`. This is useful when
      you have a fixed label size.
  - name: Use a different barcode symbology
    text: Aspose.BarCode supports dozens of postal symbologies (e.g., **USPS Intelligent
      Mail**, **Japan Post**). To **generate planet barcode** alternatives, replace
      `EncodeTypes.Planet` with the desired enum value.
  - name: Handling invalid data
    text: Postal barcodes have strict data length rules. If you pass a string that
      does not meet the specification, Aspose.BarCode throws an `ArgumentException`.
      Wrap the generator creation in a `try/catch` block to provide a friendly error
      message.
  type: HowTo
tags:
- barcode
- C#
- Aspose
title: Как создать изображение почтового штрихкода в C# с помощью Aspose.BarCode
url: /ru/python-java/general/how-to-create-postal-barcode-image-in-c-using-aspose-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Как создать изображение почтового штрихкода в C# с помощью Aspose.BarCode

Если вам нужно **создать изображение почтового штрихкода** в C#, Aspose.BarCode предоставляет чистый API, который справляется с тяжелой работой. Независимо от того, создаете ли вы систему почтовых этикеток или сервис проверки адресов, это руководство покажет, как точно генерировать штрихкоды Planet и RM4SCC, переключаться между заполненными и пустыми полосами и экспортировать результат в виде PNG‑файлов.

Вы узнаете, как настроить размер штрихкода, управлять поведением заполнения полос и сохранять изображение на диск — всё в одной исполняемой программе. Ни какие внешние инструменты не требуются, кроме библиотеки Aspose.BarCode для .NET.

## Требования

* .NET 6.0 SDK или новее (код также работает с .NET Framework 4.7+)
* Visual Studio 2022 или любой совместимый с C# IDE
* Лицензионная или оценочная копия **Aspose.BarCode for .NET** (доступна через NuGet)

```bash
dotnet add package Aspose.BarCode
```

## Обзор решения

Учебник разделён на три логических шага:

1. **Создать штрихкод Planet с полосами по умолчанию (заполненными)** – это демонстрирует типичный вид для почтовых служб.
2. **Создать штрихкод Planet с пустыми полосами** – полезно, когда процесс печати ожидает незаполненные полосы.
3. **Создать штрихкод RM4SCC с заполненными полосами** – ещё один распространённый почтовый формат, используемый во многих странах.

Каждый шаг следует той же схеме: создать экземпляр `BarcodeGenerator`, установить `XDimension` (ширина в пикселях одной полосы), при необходимости скорректировать `FilledBars` и вызвать `Save` для записи PNG‑файла.

---

## Создание изображения почтового штрихкода с Aspose.BarCode

Ниже представлена полная, автономная программа. Сохраните её как `Program.cs` и запустите из командной строки или вашей IDE.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace PostalBarcodeDemo
{
    class Program
    {
        static void Main(string[] args)
        {
            // Define the output folder – change this to a writable location on your machine
            string outputDir = @"YOUR_DIRECTORY";

            // -------------------------------------------------
            // Step 1: Generate a Planet barcode with filled bars
            // -------------------------------------------------
            var planetFilled = new BarcodeGenerator(EncodeTypes.Planet, "123456")
            {
                // XDimension controls the width of a single bar in pixels.
                // A value of 4 gives a good balance between readability and file size.
                Parameters = { Barcode = { XDimension = { Pixels = 4 } } }
            };
            string planetFilledPath = System.IO.Path.Combine(outputDir, "PostalPlanetFilledBars.png");
            planetFilled.Save(planetFilledPath, BarCodeImageFormat.Png);
            Console.WriteLine($"Filled Planet barcode saved to {planetFilledPath}");

            // -------------------------------------------------
            // Step 2: Generate a Planet barcode with empty bars
            // -------------------------------------------------
            var planetEmpty = new BarcodeGenerator(EncodeTypes.Planet, "123456")
            {
                Parameters = {
                    Barcode = {
                        XDimension = { Pixels = 4 },
                        // Setting FilledBars to false renders the bars as empty outlines.
                        FilledBars = false
                    }
                }
            };
            string planetEmptyPath = System.IO.Path.Combine(outputDir, "PostalPlanetEmptyBars.png");
            planetEmpty.Save(planetEmptyPath, BarCodeImageFormat.Png);
            Console.WriteLine($"Empty Planet barcode saved to {planetEmptyPath}");

            // -------------------------------------------------
            // Step 3: Generate an RM4SCC barcode with filled bars
            // -------------------------------------------------
            var rm4sccFilled = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456")
            {
                Parameters = { Barcode = { XDimension = { Pixels = 4 } } }
            };
            string rm4sccPath = System.IO.Path.Combine(outputDir, "PostalRM4SCCFilledBars.png");
            rm4sccFilled.Save(rm4sccPath, BarCodeImageFormat.Png);
            Console.WriteLine($"Filled RM4SCC barcode saved to {rm4sccPath}");

            // End of demo
            Console.WriteLine("All barcode images have been generated successfully.");
        }
    }
}
```

### Почему важна каждая строка

* **`new BarcodeGenerator(EncodeTypes.Planet, "123456")`** – Перечисление `EncodeTypes.Planet` сообщает Aspose.BarCode использовать символогию *Planet*, которая является стандартным почтовым штрихкодом во многих странах. Это основа того, как вы **generate planet barcode** изображения.
* **`XDimension.Pixels = 4`** – Ширина одной полосы влияет как на надежность сканирования, так и на визуальный размер. Значение 4 px хорошо работает для большинства принтеров этикеток; вы можете увеличить его для вывода с более высоким разрешением.
* **`FilledBars = false`** – По умолчанию полосы заполнены. Установка значения `false` создаёт стиль «пустой полосы», требуемый некоторыми почтовыми спецификациями.
* **`Save(..., BarCodeImageFormat.Png)`** – PNG сохраняет без потерь, что делает его идеальным для изображений штрихкодов, которые должны считываться сканерами.

### Ожидаемый результат

После выполнения программы в папке `YOUR_DIRECTORY` появятся три PNG‑файла:

| Имя файла | Визуальное описание |
|---|---|
| `PostalPlanetFilledBars.png` | Штрихкод Planet с сплошными черными полосами |
| `PostalPlanetEmptyBars.png` | Штрихкод Planet, где полосы только очерчены (пустые) |
| `PostalRM4SCCFilledBars.png` | Штрихкод RM4SCC со сплошными полосами |

Вы можете открыть любое из этих изображений в просмотрщике изображений или встроить их напрямую в PDF/HTML‑этикетку.

---

## Дополнительная настройка штрихкода (необязательно)

### Изменить формат изображения

Если вам нужен другой формат (например, JPEG для веб‑доставки), замените `BarCodeImageFormat.Png` на `BarCodeImageFormat.Jpeg`. Учтите, что JPEG вводит артефакты сжатия, что может повлиять на работу сканера.

### Регулировать размер изображения без масштабирования

Вместо изменения `XDimension` вы можете управлять общими размерами изображения через `Parameters.Image.Height` и `Parameters.Image.Width`. Это полезно, когда у вас фиксированный размер этикетки.

```csharp
planetFilled.Parameters.Image.Height = 150; // pixels
planetFilled.Parameters.Image.Width = 300;  // pixels
```

### Использовать другую символогию штрихкода

Aspose.BarCode поддерживает десятки почтовых символогий (например, **USPS Intelligent Mail**, **Japan Post**). Чтобы **generate planet barcode** альтернативы, замените `EncodeTypes.Planet` на нужное значение перечисления.

```csharp
var uspsBarcode = new BarcodeGenerator(EncodeTypes.USPSIntelligentMail, "123456789012");
```

### Обработка недопустимых данных

Почтовые штрихкоды имеют строгие правила длины данных. Если передать строку, не соответствующую спецификации, Aspose.BarCode бросит `ArgumentException`. Оберните создание генератора в блок `try/catch`, чтобы предоставить понятное сообщение об ошибке.

```csharp
try
{
    var invalid = new BarcodeGenerator(EncodeTypes.Planet, "ABC");
}
catch (ArgumentException ex)
{
    Console.Error.WriteLine($"Invalid barcode data: {ex.Message}");
}
```

---

## Распространённые ошибки и профессиональные советы

| Подводный камень | Почему происходит | Совет |
|---|---|---|
| **Использование слишком малого XDimension** | Полосы становятся тоньше минимального разрешения сканера, вызывая ошибки чтения. | Начните с `Pixels = 4` и протестируйте на целевом принтере; при необходимости увеличьте. |
| **Сохранение в папку только для чтения** | `Save` бросает `UnauthorizedAccessException`. | Убедитесь, что `outputDir` указывает на доступное для записи место, или используйте `Environment.GetFolderPath(Environment.SpecialFolder.Desktop)`. |
| **Пренебрежение освобождением генератора** | Большие изображения могут удерживать неуправляемые ресурсы. | Оборачивайте генератор в оператор `using` или вызывайте `Dispose()` после `Save`. |
| **Смешивание форматов штрихкодов в одном изображении** | Некоторые принтеры ожидают одну символогию на этикетке. | Генерируйте каждый штрихкод отдельно и при необходимости объединяйте их с помощью графической библиотеки. |

---

## Проверка сгенерированных штрихкодов

Чтобы убедиться, что штрихкоды корректны, вы можете воспользоваться бесплатным сайтом **Aspose.BarCode Demo** или любым стандартным приложением‑сканером штрихкодов. Загрузите PNG‑файлы и отсканируйте их; декодированное значение должно быть `123456` как для примеров Planet, так и RM4SCC.

---

## Заключение

В этом руководстве вы узнали, как **create postal barcode image** файлы в C# с помощью Aspose.BarCode. Вы увидели, как **generate planet barcode** изображения с заполненными и пустыми полосами, как создать штрихкод RM4SCC и как настроить размер, формат и обработку ошибок. С полным, исполняемым кодом вы теперь можете интегрировать генерацию почтовых штрихкодов в любое приложение .NET.

**Следующие шаги**

* Исследуйте другие почтовые символогии, такие как `EncodeTypes.USPSIntelligentMail` (вторичное ключевое слово: postal barcode PNG).

## Что вам следует изучить дальше?

Следующие учебники охватывают тесно связанные темы, основанные на техниках, продемонстрированных в этом руководстве. Каждый ресурс включает полностью работающие примеры кода с пошаговыми объяснениями, чтобы помочь вам освоить дополнительные возможности API и исследовать альтернативные подходы к реализации в ваших проектах.

- [Создать изображение почтового штрихкода в C# – Полное пошаговое руководство](/barcode/english/python-java/general/create-postal-barcode-image-in-c-full-step-by-step-guide/)
- [Генерировать почтовый штрихкод в C# – Полное руководство с штрихкодом Planet](/barcode/english/python-java/general/generate-postal-barcode-in-c-complete-guide-with-planet-barc/)
- [Как генерировать почтовый штрихкод в C# с Aspose.BarCode](/barcode/english/python-java/general/how-to-generate-postal-barcode-in-c-with-aspose-barcode/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}