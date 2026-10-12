---
category: general
date: 2026-10-02
description: Узнайте, как задавать столбцы и строки в генераторе штрихкодов на C#
  для создания штрихкодов DataBar. Пошаговое руководство с полным кодом.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- c# barcode generator
- how to set columns
- how to set rows
- create databar barcode
language: ru
lastmod: 2026-10-02
og_description: Руководство по генератору штрихкодов на C# — узнайте, как задавать
  столбцы и строки для создания штрихкодов DataBar с полными примерами кода.
og_image_alt: Screenshot of a DataBar Expanded Stacked barcode generated with a C#
  barcode generator
og_title: 'Генератор штрихкодов C#: задайте столбцы и строки для штрихкодов DataBar'
schemas:
- author: Aspose
  dateModified: '2026-10-02'
  description: Learn how to set columns and rows in a C# barcode generator to create
    DataBar barcodes. Step‑by‑step guide with complete code.
  headline: How to use a C# barcode generator to create DataBar barcodes with custom
    columns and rows
  type: TechArticle
tags:
- barcode
- c#
- databar
title: Как использовать генератор штрихкодов на C# для создания штрихкодов DataBar
  с пользовательскими столбцами и строками
url: /ru/python-java/general/how-to-use-a-c-barcode-generator-to-create-databar-barcodes/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Как использовать генератор штрих‑кодов C# для создания DataBar штрих‑кодов с пользовательскими столбцами и строками

Если вам нужен **c# barcode generator**, способный создавать DataBar штрих‑коды с точными настройками столбцов и строк, этот учебник покажет вам, как это сделать. Вы узнаете, почему важно регулировать столбцы и строки, и получите полностью готовый пример, который создаёт как 4‑столбцовый, так и 3‑строчный DataBar Expanded Stacked штрих‑код.

В последующих разделах мы рассмотрим:

* Предварительные требования для использования библиотеки Aspose.BarCode for .NET.
* Как задать столбцы (`how to set columns`) и строки (`how to set rows`) в DataBar штрих‑коде.
* Полную консольную программу на C#, которую можно скопировать, скомпилировать и выполнить.
* Ожидаемые файлы вывода и советы по устранению неполадок.

К концу этого руководства вы сможете **create databar barcode** изображения, адаптированные под ваши требования к макету.

## Предварительные требования

Прежде чем начать, убедитесь, что у вас есть:

| Требование | Причина |
|-------------|--------|
| .NET 6.0 SDK или новее | Обеспечивает среду выполнения для кода C#. |
| Visual Studio 2022 (или любая IDE, поддерживающая .NET) | Упрощает создание проекта и отладку. |
| NuGet‑пакет Aspose.BarCode for .NET | Предоставляет класс `BarcodeGenerator`, используемый в примерах. |
| Права записи в папку для выходных PNG‑файлов | Генератор записывает изображения штрих‑кодов на диск. |

Установите пакет Aspose.BarCode с помощью следующей команды:

```bash
dotnet add package Aspose.BarCode
```

## Шаг 1: Создание базового DataBar Expanded Stacked штрих‑кода

Первый шаг — создать **c# barcode generator** с форматом `EncodeTypes.DatabarExpandedStacked`. Этот формат представляет собой двумерный DataBar штрих‑код, способный кодировать до 74 числовых символов.

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

// ...

// Create a generator for a DataBar Expanded Stacked barcode
var generator = new BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked,
    "Databar Expanded Stacked long");
```

Конструктор принимает два аргумента:

* `EncodeTypes.DatabarExpandedStacked` – указывает библиотеке, какую символьную схему использовать.
* `"Databar Expanded Stacked long"` – текст, который будет закодирован.

## Шаг 2: Как задать столбцы

Столбцы влияют на горизонтальную плотность DataBar штрих‑кода. Увеличение количества столбцов делает штрих‑код шире, что может повысить надёжность сканирования на принтерах с низким разрешением.

```csharp
// Set the number of columns to 4
generator.Parameters.Barcode.DataBar.Columns = 4;
```

**Почему 4 столбца?**  
Четыре столбца обеспечивают хороший баланс между размером и читаемостью для большинства розничных приложений. Вы можете экспериментировать со значениями от 1 до 8; библиотека автоматически скорректирует ширину модуля.

## Шаг 3: Сохранение штрих‑кода с настроенными столбцами

```csharp
// Save the image that uses the column setting
generator.Save(@"C:\Barcodes\DatabarCols4.png", BarCodeImageFormat.Png);
```

Изображение сохраняется в формате PNG, что сохраняет чёткие края, необходимые сканерам штрих‑кодов.

## Шаг 4: Создание отдельного генератора для настройки строк

Настройка строк работает аналогично, но влияет на вертикальную плотность. Чтобы не смешивать параметры столбцов и строк, мы создаём новый экземпляр генератора.

```csharp
var generatorRows = new BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked,
    "Databar Expanded Stacked long");
```

## Шаг 5: Как задать строки

```csharp
// Set the number of rows to 3
generatorRows.Parameters.Barcode.DataBar.Rows = 3;
```

**Когда использовать больше строк?**  
Добавление строк делает штрих‑код выше, что может быть полезно, когда горизонтальное пространство ограничено, а вертикальное достаточно (например, на этикетке продукта, которая выше, чем широка).

## Шаг 6: Сохранение штрих‑кода с настроенными строками

```csharp
// Save the image that uses the row setting
generatorRows.Save(@"C:\Barcodes\DatabarRows3.png", BarCodeImageFormat.Png);
```

Оба PNG‑файла (`DatabarCols4.png` и `DatabarRows3.png`) появятся в папке `C:\Barcodes`.

## Полный, исполняемый пример

Ниже представлено автономное консольное приложение, включающее каждый описанный выше шаг. Скопируйте код в новый .NET консольный проект и запустите его.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace DatabarDemo
{
    class Program
    {
        static void Main()
        {
            // Output directory – change to a folder that exists on your machine
            const string outputDir = @"C:\Barcodes";

            // -------------------------------------------------
            // 1️⃣ Create a barcode generator for column testing
            // -------------------------------------------------
            var colGenerator = new BarcodeGenerator(
                EncodeTypes.DatabarExpandedStacked,
                "Databar Expanded Stacked long");

            // Set the number of columns (how to set columns)
            colGenerator.Parameters.Barcode.DataBar.Columns = 4;

            // Save the column‑based barcode
            string colPath = System.IO.Path.Combine(outputDir, "DatabarCols4.png");
            colGenerator.Save(colPath, BarCodeImageFormat.Png);
            Console.WriteLine($"Column barcode saved to: {colPath}");

            // -------------------------------------------------
            // 2️⃣ Create a barcode generator for row testing
            // -------------------------------------------------
            var rowGenerator = new BarcodeGenerator(
                EncodeTypes.DatabarExpandedStacked,
                "Databar Expanded Stacked long");

            // Set the number of rows (how to set rows)
            rowGenerator.Parameters.Barcode.DataBar.Rows = 3;

            // Save the row‑based barcode
            string rowPath = System.IO.Path.Combine(outputDir, "DatabarRows3.png");
            rowGenerator.Save(rowPath, BarCodeImageFormat.Png);
            Console.WriteLine($"Row barcode saved to: {rowPath}");

            // -------------------------------------------------
            // 3️⃣ Confirmation message
            // -------------------------------------------------
            Console.WriteLine("Both DataBar barcodes have been generated successfully.");
        }
    }
}
```

### Что делает код

| Раздел | Назначение |
|---------|------------|
| **Импорт пространств имён** | Подключает `Aspose.BarCode` и `Aspose.BarCode.Generation`. |
| **Каталог вывода** | Централизует путь, чтобы менять его в одном месте при перемещении папки. |
| **Генератор столбцов** | Демонстрирует **how to set columns** на `c# barcode generator`. |
| **Генератор строк** | Демонстрирует **how to set rows** на `c# barcode generator`. |
| **Вызовы Save** | Записывает PNG‑файлы на диск, делая их готовыми к сканированию или включению в отчёты. |
| **Вывод в консоль** | Предоставляет мгновенную обратную связь, полезную во время разработки. |

## Ожидаемый вывод

После запуска программы вы должны увидеть два PNG‑файла:

* **DatabarCols4.png** – более широкий штрих‑код, отражающий четыре столбца.
* **DatabarRows3.png** – более высокий штрих‑код, отражающий три строки.

Оба изображения содержат текст *«Databar Expanded Stacked long»*, закодированный в символьной схеме DataBar Expanded Stacked. Вы можете открыть их в любом просмотрщике изображений или передать сканеру штрих‑кодов для проверки читаемости.

## Распространённые ошибки и как их избежать

| Проблема | Причина | Решение |
|----------|---------|----------|
| **Исключение доступа к файлу** | Папка вывода не существует или у вас нет прав записи. | Создайте папку вручную или запустите программу с повышенными привилегиями. |
| **Неправильные значения столбцов/строк** | Библиотека принимает только значения 1‑8 для столбцов и 1‑4 для строк. | Проверьте значения перед назначением, например, `if (value < 1 || value > 8) throw new ArgumentOutOfRangeException();`. |
| **Штрих‑код не сканируется** | Сгенерированное изображение слишком мало для разрешения сканера. | Увеличьте `ImageHeight` или `ImageWidth` с помощью `generator.Parameters.Image.Height` / `...Width`. |
| **Обрезка текста** | Закодированный текст превышает максимальную длину для выбранного варианта DataBar. | Используйте более короткую строку или переключитесь на `EncodeTypes.DatabarExpanded`, если требуется большая ёмкость. |

## Профессиональные советы

* **Кешировать генератор** – Если нужно создать много штрих‑кодов с одинаковыми настройками столбцов/строк, переиспользуйте один экземпляр `BarcodeGenerator` и меняйте только свойство `CodeText`.
* **Пакетная обработка** – Пройдитесь по коллекции идентификаторов продуктов, задавайте `generator.CodeText` внутри цикла и вызывайте `Save` с уникальным именем файла на каждой итерации.
* **Производительность** – Для сценариев с высоким объёмом отключите сглаживание (`generator.Parameters.Image.AntiAlias = false`), чтобы ускорить генерацию изображений без потери качества сканирования.

## Следующие шаги

Теперь, когда вы знаете **how to set columns** и **how to set rows** с помощью **c# barcode generator**, вы можете захотеть изучить:

* **Добавление читаемого человеком текста** под штрих‑кодом (`generator.Parameters.Barcode.CodeTextLocation`).
* **Изменение цветов** (`generator.Parameters.Image.ForegroundColor` и `BackgroundColor`).
* **Генерация других вариантов DataBar**, таких как `DatabarLimited` или `DatabarExpanded`.
* **Встраивание штрих‑кодов в PDF‑отчёты** с помощью Aspose.PDF.

Каждая из этих тем опирается на изложенный здесь фундамент и помогает создавать более продвинутые, готовые к производству решения со штрих‑кодами.

---

*Счастливого кодинга! Если возникнут проблемы, оставляйте комментарий или обратитесь к документации Aspose.BarCode для более подробных сведений об API.*

## Что следует изучить дальше?

Следующие учебники охватывают тесно связанные темы, которые развивают техники, продемонстрированные в этом руководстве. Каждый ресурс включает полностью рабочие примеры кода с пошаговыми объяснениями, чтобы помочь вам освоить дополнительные возможности API и исследовать альтернативные подходы к реализации в ваших проектах.

- [Как задать столбцы и строки штрих‑кода с C# BarcodeGenerator](/barcode/english/python-java/general/how-to-set-barcode-columns-and-rows-with-c-barcodegenerator/)
- [Пример генератора штрих‑кодов на C# – установка столбцов, строк и экспорт изображения](/barcode/english/python-java/general/barcode-generator-example-in-c-set-columns-rows-export-image/)
- [Как использовать генератор штрих‑кодов C# для создания DataBar штрих‑кодов](/barcode/english/python-java/general/how-to-use-a-barcode-generator-c-to-create-databar-barcodes/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}