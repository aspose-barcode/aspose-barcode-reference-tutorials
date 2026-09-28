---
category: general
date: 2026-08-09
description: Создайте 4‑колоночный датабар‑код в C# быстро с Aspose.BarCode. Узнайте,
  как настроить столбцы, строки и сохранить PNG‑изображения в этом кратком руководстве.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create 4‑column databar barcode
- databar expanded stacked
- barcode generator c#
- set barcode rows
- barcode image format
language: ru
lastmod: 2026-08-09
og_description: Создайте 4‑колоночный датабар‑код в C# с использованием Aspose.BarCode,
  затем настройте строки и экспортируйте PNG‑изображения для вашего приложения.
og_image_alt: Screenshot of a 4‑column DataBar Expanded Stacked barcode generated
  in C#
og_title: Создайте 4‑колоночный штрих‑код Databar в C# – быстрый учебник
schemas:
- author: Aspose
  dateModified: '2026-08-09'
  description: Create 4‑column databar barcode in C# quickly with Aspose.BarCode.
    Learn how to configure columns, rows, and save PNG images in this concise guide.
  headline: Create 4‑column databar barcode in C# – step‑by‑step guide
  type: TechArticle
- description: Create 4‑column databar barcode in C# quickly with Aspose.BarCode.
    Learn how to configure columns, rows, and save PNG images in this concise guide.
  name: Create 4‑column databar barcode in C# – step‑by‑step guide
  steps:
  - name: Configure DataBar Expanded Stacked columns
    text: If you need a different column count, simply change the integer assigned
      to `Columns`. The property accepts values from 1 to 4 for the expanded stacked
      variant.
  - name: Save the barcode image
    text: The `BarCodeImageFormat` enumeration provides several options (`Png`, `Jpeg`,
      `Bmp`, `Gif`, `Tiff`). PNG is loss‑less and works well for most web and desktop
      scenarios.
  - name: Set barcode rows dynamically
    text: 'You can compute the row count at runtime based on input data:'
  type: HowTo
tags:
- barcode
- C#
- Aspose
- DataBar
title: Создание 4‑колоночного штрих‑кода Databar в C# – пошаговое руководство
url: /ru/python-java/general/create-4-column-databar-barcode-in-c-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Создание 4‑колоночного штрих‑кода DataBar в C# – пошаговое руководство

Если вам нужно **создать 4‑колоночный штрих‑код DataBar** в C#, этот учебник покажет вам, как это сделать. Мы пройдем процесс генерации штрих‑кода DataBar Expanded Stacked, настройки четырёх колонок и сохранения результата в виде PNG‑изображения.

В этом руководстве вы узнаете, как:

* Инициализировать `BarcodeGenerator` для символа **DataBar Expanded Stacked**.  
* Установить количество колонок равным 4 (основное требование).  
* Настроить количество строк, когда нужен стековый макет с тремя строками.  
* Экспортировать штрих‑код в PNG, используя соответствующий **barcode image format**.

Вам понадобится только библиотека Aspose.BarCode for .NET (версии 23.10 или новее) и среда разработки .NET 6+ вроде Visual Studio 2022. Дополнительные зависимости не требуются.

---

## Как создать 4‑колоночный штрих‑код DataBar

Первый шаг — создать экземпляр `BarcodeGenerator`, который использует символьную схему **DataBar Expanded Stacked**. Этот класс инкапсулирует все параметры рендеринга, что упрощает переключение между макетами на основе колонок и строк.

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        // 1️⃣ Initialise a generator for DataBar Expanded Stacked
        BarcodeGenerator generator = new BarcodeGenerator(
            EncodeTypes.DatabarExpandedStacked,
            "Databar Expanded Stacked long");
        
        // 2️⃣ Set the barcode to use a 4‑column layout
        generator.Parameters.Barcode.DataBar.Columns = 4;

        // 3️⃣ Save the image as PNG
        generator.Save("DatabarCols4.png", BarCodeImageFormat.Png);
    }
}
```

**Почему это работает:**  
`EncodeTypes.DatabarExpandedStacked` указывает Aspose.BarCode генерировать стековую версию семейства DataBar. Свойство `DataBar.Columns` определяет, сколько вертикальных модулей занимает штрих‑код. Установка значения 4 соответствует требованию **создать 4‑колоночный штрих‑код DataBar**. Наконец, `Save` сохраняет визуальное представление на диск, используя **barcode image format** `Png`.

### Настройка колонок DataBar Expanded Stacked

Если требуется другое количество колонок, просто измените целое число, присвоенное `Columns`. Свойство принимает значения от 1 до 4 для варианта expanded stacked.

```csharp
// Example: switch to a 2‑column layout
generator.Parameters.Barcode.DataBar.Columns = 2;
```

*Pro tip:* Всегда проверяйте сгенерированный штрих‑код сканером, поддерживающим семейство DataBar, так как только визуальный вид не гарантирует читаемость.

### Сохранение изображения штрих‑кода

Перечисление `BarCodeImageFormat` предоставляет несколько вариантов (`Png`, `Jpeg`, `Bmp`, `Gif`, `Tiff`). PNG — без потерь и хорошо подходит для большинства веб‑ и десктоп‑сценариев.

```csharp
generator.Save("DatabarCols4.png", BarCodeImageFormat.Png);
```

Если нужен другой формат, замените `Png` на требуемое значение перечисления. Сохранённый файл можно напрямую встраивать в HTML, PDF или печатать на этикетках.

## Создание штрих‑кода с пользовательскими строками

Иногда требуется стековый макет с определённым количеством строк вместо колонок. Класс `BarcodeGenerator` предоставляет свойство `Rows` для этой цели.

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class RowExample
{
    static void Main()
    {
        // 1️⃣ Initialise a generator for the same symbology
        BarcodeGenerator rowGenerator = new BarcodeGenerator(
            EncodeTypes.DatabarExpandedStacked,
            "Databar Expanded Stacked long");

        // 2️⃣ Configure the barcode to use a 3‑row layout
        rowGenerator.Parameters.Barcode.DataBar.Rows = 3;

        // 3️⃣ Save the image as PNG
        rowGenerator.Save("DatabarRows3.png", BarCodeImageFormat.Png);
    }
}
```

**Почему строки важны:**  
Когда стековый штрих‑код выше, чем шире, свойство `Rows` определяет, на сколько горизонтальных секций делится символ. Установка `Rows = 3` создаёт трехстрочный стековый штрих‑код, что полезно для узких этикеток.

### Динамическая установка строк штрих‑кода

Вы можете вычислять количество строк во время выполнения на основе входных данных:

```csharp
int desiredRows = GetRowsFromUser(); // your custom logic
rowGenerator.Parameters.Barcode.DataBar.Rows = desiredRows;
```

Эта гибкость позволяет **устанавливать строки штрих‑кода** без перекомпиляции приложения.

## Полный сквозной пример

Ниже представлен один пример программы, который генерирует как 4‑колоночный штрих‑код, так и 3‑строчный, демонстрируя, как обе конфигурации могут сосуществовать.

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class FullExample
{
    static void Main()
    {
        // ---------- 4‑column barcode ----------
        BarcodeGenerator colGen = new BarcodeGenerator(
            EncodeTypes.DatabarExpandedStacked,
            "Databar Expanded Stacked long");
        colGen.Parameters.Barcode.DataBar.Columns = 4; // create 4‑column databar barcode
        colGen.Save("DatabarCols4.png", BarCodeImageFormat.Png);

        // ---------- 3‑row barcode ----------
        BarcodeGenerator rowGen = new BarcodeGenerator(
            EncodeTypes.DatabarExpandedStacked,
            "Databar Expanded Stacked long");
        rowGen.Parameters.Barcode.DataBar.Rows = 3; // set barcode rows to 3
        rowGen.Save("DatabarRows3.png", BarCodeImageFormat.Png);

        // Output confirmation
        System.Console.WriteLine("Barcodes generated:");
        System.Console.WriteLine(" - DatabarCols4.png (4 columns)");
        System.Console.WriteLine(" - DatabarRows3.png (3 rows)");
    }
}
```

**Ожидаемый результат:**  
В рабочем каталоге приложения появятся два PNG‑файла:

* `DatabarCols4.png` – штрих‑код DataBar Expanded Stacked с четырьмя вертикальными колонками.  
* `DatabarRows3.png` – тот же символ, расположенный в три горизонтальные строки.

Оба изображения можно открыть в любом просмотрщике изображений или встроить в элемент управления UI.

---

## Часто задаваемые вопросы и особые случаи

| Вопрос | Ответ |
|----------|--------|
| *Можно ли использовать другую символьную схему штрих‑кода?* | Да. Замените `EncodeTypes.DatabarExpandedStacked` другим значением `EncodeTypes` (например, `EncodeTypes.QR`), однако свойства `Columns` и `Rows` специфичны для семейств DataBar. |
| *Что делать, если строка данных превышает максимальную длину?* | Символьная схема DataBar Expanded Stacked поддерживает до 61 числового символа. Превышение этого лимита вызывает `ArgumentException`. Проверьте входные данные перед передачей их генератору. |
| *Нужно ли освобождать `BarcodeGenerator`?* | `BarcodeGenerator` реализует `IDisposable`. В длительно работающем сервисе оберните его в блок `using` или вызовите `Dispose()` вручную, чтобы освободить нативные ресурсы. |
| *Можно ли генерировать SVG вместо PNG?* | Конечно. Используйте `BarCodeImageFormat.Svg` в методе `Save`. |
| *Совместима ли библиотека с .NET Core?* | Aspose.BarCode for .NET поддерживает .NET Core 3.1, .NET 5, .NET 6 и более новые версии. Изменения кода не требуются. |

## Заключение

Теперь вы знаете, как **создать 4‑колоночный штрих‑код DataBar** в C# с помощью Aspose.BarCode, как настроить макет с помощью строк и как экспортировать результат в удобный **barcode image format**. Полный пример демонстрирует как конфигурацию на основе колонок, так и на основе строк, предоставляя прочную основу для любых сценариев печати этикеток или мобильного сканирования.

**Следующие шаги**

* Экспериментировать с различными данными и проверять совместимость со сканером.  
* Исследовать дополнительные параметры оформления, такие как цвета переднего/фонового плана (`generator.Parameters.Barcode.Color`).  
* Комбинировать штрих‑код с другими графическими элементами, используя API `Graphics` для создания пользовательских дизайнов этикеток.  

Не стесняйтесь адаптировать код для проектов ASP.NET Core, Windows Forms или Xamarin — Aspose.BarCode работает на всех платформах .NET. Приятного кодинга!

## Что изучать дальше?

Следующие учебники охватывают тесно связанные темы, основанные на техниках, продемонстрированных в этом руководстве. Каждый ресурс содержит полностью рабочие примеры кода с пошаговыми объяснениями, помогающие вам освоить дополнительные возможности API и исследовать альтернативные подходы к реализации в ваших проектах.

- [Создать изображение штрих‑кода DotCode – строки и колонки (Aspose.BarCode)](/barcode/english/net/dotcode-barcode-configuration/dotcode-rows-columns-configuration/)
- [Создать изображение штрих‑кода c# – Настройка строк и колонок Codablock F](/barcode/english/net/codablock-f-encoding/codablock-f-row-column-configuration/)
- [Как создать расширенный код текста dotcode с Aspose.BarCode для .NET](/barcode/english/net/dotcode-barcode-configuration/dotcode-extended-code-text-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}