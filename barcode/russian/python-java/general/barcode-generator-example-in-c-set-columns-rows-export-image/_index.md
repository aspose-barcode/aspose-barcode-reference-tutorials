---
category: general
date: 2026-07-15
description: Пример генератора штрихкодов на C#, показывающий, как задать столбцы,
  как задать строки и быстро экспортировать изображение штрихкода. Следуйте этому
  пошаговому руководству.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- barcode generator example
- how to set columns
- how to set rows
- export barcode image
- create barcode image c#
language: ru
lastmod: 2026-07-15
og_description: Пример генератора штрихкодов на C# демонстрирует, как задавать столбцы,
  как задавать строки и экспортировать изображение штрихкода. Узнайте полный процесс
  за несколько минут.
og_image_alt: Screenshot of a barcode generator example showing column and row settings
  in C#
og_title: Пример генератора штрихкодов на C# – столбцы, строки и экспорт изображения
schemas:
- author: Aspose
  dateModified: '2026-07-15'
  description: Barcode generator example in C# showing how to set columns, how to
    set rows, and export barcode image quickly. Follow this step‑by‑step guide.
  headline: Barcode Generator Example in C# – Set Columns, Rows & Export Image
  type: TechArticle
- description: Barcode generator example in C# showing how to set columns, how to
    set rows, and export barcode image quickly. Follow this step‑by‑step guide.
  name: Barcode Generator Example in C# – Set Columns, Rows & Export Image
  steps:
  - name: '**Add colors** – Set `generator.Parameters.Barcode.ForegroundColor` to
      `Color.Blue`.'
    text: '**Add colors** – Set `generator.Parameters.Barcode.ForegroundColor` to
      `Color.Blue`.'
  - name: '**Encode different data** – Pass a variable string instead of the hard‑coded
      `"Databar Expanded Stacked long"`.'
    text: '**Encode different data** – Pass a variable string instead of the hard‑coded
      `"Databar Expanded Stacked long"`.'
  - name: '**Batch processing** – Loop over a CSV file of product codes, generating
      a PNG for each.'
    text: '**Batch processing** – Loop over a CSV file of product codes, generating
      a PNG for each.'
  - name: '**Integrate with a web API** – Expose an endpoint that returns the barcode
      as a base64‑encoded string.'
    text: '**Integrate with a web API** – Expose an endpoint that returns the barcode
      as a base64‑encoded string.'
  type: HowTo
tags:
- barcode
- C#
- image export
title: Пример генератора штрихкодов на C# – установка столбцов, строк и экспорт изображения
url: /ru/python-java/general/barcode-generator-example-in-c-set-columns-rows-export-image/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Пример генератора штрихкодов на C# – Полный разбор

Когда‑нибудь задумывались, как создать **пример генератора штрихкодов** на C#, который позволяет менять количество столбцов, строк и затем экспортировать результат в виде изображения? Вы не одиноки. Многие разработчики сталкиваются с проблемой, когда нужен быстрый способ генерировать DataBar Expanded Stacked штрихкоды с пользовательскими параметрами макета. В этом руководстве мы решим эту задачу шаг за шагом, покажем, **как задать столбцы**, **как задать строки** и, наконец, **как экспортировать изображения штрихкода** — всё с чистым, готовым к продакшну кодом.

К концу этого руководства у вас будет полностью готовая, исполняемая программа, которая создаёт изображение штрихкода, настраивает его макет и сохраняет два PNG‑файла на диск. Никаких загадочных библиотек, никаких скрытых настроек — только чистый C# и надёжный barcode SDK.

---

## Требования

Прежде чем погрузиться в детали, убедитесь, что у вас есть следующее:

- **.NET 6.0** (или более поздняя версия .NET). Код также компилируется под .NET Framework, но .NET 6+ предоставляет последние улучшения среды выполнения.
- **Библиотека генерации штрихкодов**, поддерживающая DataBar Expanded Stacked. В примерах мы будем использовать **Aspose.BarCode for .NET**, которая доступна в бесплатной trial‑версии и имеет простой API.
- Среда разработки — Visual Studio 2022, Rider или VS Code подойдут.
- Права записи в папку, куда будут сохраняться PNG‑файлы.

Если библиотека ещё не установлена, получите её из NuGet:

```bash
dotnet add package Aspose.BarCode
```

Эта единственная строка подтягивает всё необходимое, включая класс `BarcodeGenerator` и перечисление `BarCodeImageFormat`, используемые позже.

---

## Шаг 1: Создание каркаса проекта

Создайте новое консольное приложение и добавьте необходимые директивы `using`:

```csharp
using System;
using Aspose.BarCode.Generation;   // Core barcode generation classes
using Aspose.BarCode;               // For BarCodeImageFormat enum
```

Ниже — **полный** скелет файла `Program.cs`:

```csharp
namespace BarcodeDemo
{
    internal class Program
    {
        static void Main(string[] args)
        {
            // We'll fill this in in the next steps.
        }
    }
}
```

> **Pro tip:** Держите метод `Main` аккуратным; тяжёлую работу мы вынесем в вспомогательные методы. Это упрощает тестирование и повторное использование кода.

---

## Шаг 2: Создание примера генератора штрихкода

Теперь построим ядро **примера генератора штрихкода**, которое создаёт DataBar Expanded Stacked штрихкод. Это сердце руководства.

```csharp
static BarcodeGenerator CreateGenerator()
{
    // Step 1: Instantiate the generator for DataBar Expanded Stacked.
    // The second argument is the text you want encoded.
    var generator = new BarcodeGenerator(
        EncodeTypes.DatabarExpandedStacked,
        "Databar Expanded Stacked long");

    // Optional: fine‑tune image size or resolution if needed.
    generator.Parameters.Image.Width = 300;
    generator.Parameters.Image.Height = 150;

    return generator;
}
```

Зачем выносить это в отдельный метод? Он изолирует логику **примера генератора штрихкода**, делая её переиспользуемой, если позже понадобится генерировать несколько штрихкодов с разными данными.

---

## Шаг 3: Как задать столбцы

Формат DataBar Expanded Stacked может быть отрисован в макете, ориентированном на столбцы. По умолчанию SDK выбирает разумное значение, но часто требуется подогнать под конкретный размер этикетки. Вот **как задать столбцы** в четыре:

```csharp
static void SetColumns(BarcodeGenerator generator, int columns)
{
    // Step 2: Adjust the column count.
    generator.Parameters.Barcode.DataBar.Columns = columns;
}
```

> **Почему столбцы важны:** Каждый столбец добавляет вертикальное пространство, что может быть критично при печати на узких этикетках. Установка значения `4` даёт сбалансированный, читаемый штрихкод без потери надёжности сканирования.

В основной последовательности мы вызовем этот метод:

```csharp
var generator = CreateGenerator();
SetColumns(generator, 4);
```

---

## Шаг 4: Как задать строки

Иногда нужен более компактный макет, особенно при печати на короткой, широкой этикетке. Здесь в игру вступает **как задать строки**. Переход от столбцового к строковому расположению может уменьшить площадь штрихкода.

```csharp
static void SetRows(BarcodeGenerator generator, int rows)
{
    // Step 4: Change the layout to use rows instead of columns.
    generator.Parameters.Barcode.DataBar.Rows = rows;
}
```

Вызов выглядит так:

```csharp
SetRows(generator, 3);
```

> **Примечание о граничных случаях:** Нельзя задавать одновременно и столбцы, и строки — SDK отдаёт приоритет строкам, если вы присвоили ненулевое значение `Rows`. Поэтому перед переключением макета сбрасывайте противоположное свойство:

```csharp
generator.Parameters.Barcode.DataBar.Columns = 0; // Disable columns when using rows
```

---

## Шаг 5: Экспорт изображения штрихкода

После настройки макета последний шаг — **экспортировать изображения штрихкода**. SDK поддерживает PNG, JPEG, BMP и другие форматы. PNG — без потерь и хорошо подходит для большинства принтеров этикеток.

```csharp
static void SaveBarcode(BarcodeGenerator generator, string filePath)
{
    // Step 5: Save the image using the PNG format.
    generator.Save(filePath, BarCodeImageFormat.Png);
}
```

Собираем всё вместе в `Main`:

```csharp
static void Main(string[] args)
{
    // 1️⃣ Create the generator (barcode generator example)
    var generator = CreateGenerator();

    // 2️⃣ Set columns and save the first image
    SetColumns(generator, 4);
    string colsPath = @"YOUR_DIRECTORY\DatabarCols4.png";
    SaveBarcode(generator, colsPath);
    Console.WriteLine($"Barcode with 4 columns saved to {colsPath}");

    // 3️⃣ Switch to rows and save the second image
    SetRows(generator, 3);
    // Clear columns to avoid conflict
    generator.Parameters.Barcode.DataBar.Columns = 0;
    string rowsPath = @"YOUR_DIRECTORY\DatabarRows3.png";
    SaveBarcode(generator, rowsPath);
    Console.WriteLine($"Barcode with 3 rows saved to {rowsPath}");
}
```

### Ожидаемый результат

При запуске программы вы увидите два PNG‑файла в `YOUR_DIRECTORY`:

- **DatabarCols4.png** — штрихкод, отрисованный с четырьмя вертикальными столбцами.
- **DatabarRows3.png** — те же данные, но выстроенные в три горизонтальные строки.

Оба изображения будут иметь размер 300 × 150 px (как задано в `CreateGenerator`) и будут готовы к печати или встраиванию в PDF.

---

## Распространённые ошибки и советы

| Проблема | Почему происходит | Решение |
|----------|-------------------|---------|
| **Ошибки пути к файлу** | Использование относительного пути без правильного каталога может вызвать `DirectoryNotFoundException`. | Используйте `Path.Combine(Environment.CurrentDirectory, "output", "file.png")` или создайте папку заранее с помощью `Directory.CreateDirectory`. |
| **Конфликт строк и столбцов** | Установка обоих свойств приводит к игнорированию столбцов SDK‑ом. | При переключении макета явно задавайте противоположное свойство `0`. |
| **Неподдерживаемый тип штрихкода** | Не все библиотеки поддерживают DataBar Expanded Stacked. | Убедитесь, что ваша версия библиотеки содержит `EncodeTypes.DatabarExpandedStacked`. |
| **Низкое качество изображения** | DPI по умолчанию может быть недостаточным для принтеров высокого разрешения. | Установите `generator.Parameters.Image.ResolutionX/Y` в `300` или выше. |

---

## Расширение примера генератора штрихкода

Теперь, когда у вас есть надёжный **пример генератора штрихкода**, вы, вероятно, задаётесь вопросом, что ещё можно сделать.

1. **Добавить цвета** — задайте `generator.Parameters.Barcode.ForegroundColor` в `Color.Blue`.
2. **Кодировать другие данные** — передайте переменную строку вместо жёстко заданного `"Databar Expanded Stacked long"`.
3. **Пакетная обработка** — пройдитесь по CSV‑файлу с кодами продуктов, генерируя PNG для каждого.
4. **Интеграция с веб‑API** — откройте endpoint, который возвращает штрихкод в виде base64‑строки.

Каждое из этих расширений следует той же схеме: настроить экземпляр `BarcodeGenerator`, затем вызвать `Save` или `Export` по необходимости.

---

## Заключение

Мы прошли полный **пример генератора штрихкода** на C#, показали **как задать столбцы**, **как задать строки** и как **экспортировать изображения штрихкода**. Код автономный, работает сразу с Aspose.BarCode и демонстрирует лучшие практики читаемости и поддерживаемости.

Экспериментируйте — меняйте строку данных, подгоняйте размеры изображения или переключайте символьную систему. Принципы, которые вы изучили — инициализация генератора, настройка параметров макета и экспорт — применимы к практически любому типу штрихкода, поддерживаемому SDK.

Есть вопросы по созданию программ генерации штрихкодов на C#, или нужна помощь с конкретным принтером этикеток? Оставляйте комментарий ниже, и удачной разработки!

---


## Что изучать дальше?


Следующие руководства охватывают тесно связанные темы, расширяющие техники, продемонстрированные в этом гайде. Каждый ресурс включает полностью рабочие примеры кода с пошаговыми объяснениями, чтобы помочь вам освоить дополнительные возможности API и исследовать альтернативные подходы в собственных проектах.

- [Create DotCode barcode image – rows & columns (Aspose.BarCode)](/barcode/english/net/dotcode-barcode-configuration/dotcode-rows-columns-configuration/)
- [Create barcode image c# – Configure Codablock F Rows & Columns](/barcode/english/net/codablock-f-encoding/codablock-f-row-column-configuration/)
- [Create barcode image C# – GS1 DataMatrix Example](/barcode/english/net/gs1-barcode-encoding/gs1-datamatrix-example/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}