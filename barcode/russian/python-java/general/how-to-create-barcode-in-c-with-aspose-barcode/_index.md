---
category: general
date: 2026-09-26
description: Узнайте, как создавать штрихкоды в C# с помощью Aspose.BarCode. Это пошаговое
  руководство включает пример генератора штрихкодов и показывает, как настроить высоту
  полос.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode c#
- barcode generator example
- how to adjust bar height
- change barcode height
- generate barcode aspose
language: ru
lastmod: 2026-09-26
og_description: Создайте штрих‑код в C# с помощью Aspose.BarCode. Следуйте этому руководству,
  чтобы сгенерировать штрих‑код, настроить высоту полосы и сохранить изображения в
  формате PNG.
og_image_alt: Diagram illustrating how to create barcode in C# using Aspose.BarCode
og_title: Создание штрихкода в C# с Aspose.BarCode – полное руководство
schemas:
- author: Aspose
  dateModified: '2026-09-26'
  description: Learn how to create barcode in C# using Aspose.BarCode. This step‑by‑step
    guide includes a barcode generator example and shows how to adjust bar height.
  headline: How to create barcode in C# with Aspose.BarCode
  type: TechArticle
- description: Learn how to create barcode in C# using Aspose.BarCode. This step‑by‑step
    guide includes a barcode generator example and shows how to adjust bar height.
  name: How to create barcode in C# with Aspose.BarCode
  steps:
  - name: Import required namespaces
    text: '```csharp using System; using Aspose.BarCode.Generation; using Aspose.BarCode;
      ```'
  - name: Initialise the barcode generator
    text: We’ll generate a **Databar Omni‑Directional** symbol that encodes a GTIN‑14
      value. The constructor takes the symbology and the raw data string.
  - name: Set common barcode parameters
    text: 'Two visual parameters are most often tweaked: the X‑dimension (the narrow
      bar width) and the overall bar height.'
  - name: Save the first image (30‑pixel height)
    text: '```csharp // Save the barcode as a 30‑pixel‑high PNG generator.Save("DatabarBarHeight30Pixels.png",
      BarCodeImageFormat.Png); ```'
  - name: Change the bar height to 60 pixels
    text: Now we demonstrate **how to adjust bar height** at runtime. The same `generator`
      instance is reused; only the `BarHeight` property changes.
  - name: Full source code
    text: 'Putting everything together yields a concise, runnable program:'
  - name: Switching to a different symbology
    text: 'If you need a QR code instead of a Databar, replace the `EncodeTypes` value:'
  - name: Using `BarHeight` in millimetres
    text: 'Aspose.BarCode also supports physical units. To set a height of 10 mm:'
  - name: Handling errors
    text: 'If the data string does not conform to the selected symbology, `BarcodeGenerator`
      throws an `ArgumentException`. Wrap the generation logic in a try‑catch block
      to provide a friendly message:'
  type: HowTo
tags:
- barcode
- C#
- Aspose
title: Как создать штрих‑код в C# с помощью Aspose.BarCode
url: /ru/python-java/general/how-to-create-barcode-in-c-with-aspose-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Как создать штрих‑код в C# с помощью Aspose.BarCode  

Если вам нужно **быстро создавать проекты с штрих‑кодом c#**, Aspose.BarCode предоставляет удобный API, который берёт на себя сложную работу. В этом руководстве вы увидите полный **пример генератора штрих‑кода**, узнаете **как настроить высоту полосы**, и экспортируете результат в файлы PNG.  

Независимо от того, создаёте ли вы систему розничных касс, генерируете теги инвентаря или автоматизируете транспортные этикетки, возможность программно изменять визуальный размер штрих‑кода является важной. Это руководство предполагает, что у вас есть базовые знания C# и среда разработки, например Visual Studio 2022.  

## Требования  

* .NET 6.0 SDK или более поздняя версия установлен(а).  
* Visual Studio 2022 (или любая IDE для C#).  
* Активная лицензия Aspose.BarCode (бесплатная пробная версия подходит для обучения).  

Вам также потребуется добавить пакет Aspose.BarCode NuGet в ваш проект:

```bash
dotnet add package Aspose.BarCode
```

> **Pro tip:** Если вы планируете генерировать множество штрих‑кодов в цикле, переиспользуйте один экземпляр `BarcodeGenerator` и изменяйте только те параметры, которые меняются. Это уменьшает выделения памяти и повышает производительность.

## Как создать штрих‑код в C# с помощью Aspose.BarCode  

Следующие разделы пошагово рассматривают каждый шаг **примера генератора штрих‑кода**. Код автономный; скопируйте его в новое консольное приложение и запустите.

### Шаг 1: Импортировать необходимые пространства имён  

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;
```

Эти пространства имён предоставляют доступ к классу `BarcodeGenerator` и перечислению `EncodeTypes`.  

### Шаг 2: Инициализировать генератор штрих‑кода  

Мы сгенерируем символ **Databar Omni‑Directional**, который кодирует значение GTIN‑14. Конструктор принимает тип символьности и строку исходных данных.

```csharp
// Initialise a generator for Databar Omni‑Directional
BarcodeGenerator generator = new BarcodeGenerator(
    EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");
```

Значение `EncodeTypes.DatabarOmniDirectional` указывает Aspose.BarCode, какой стандарт штрих‑кода использовать. Строка данных следует формату идентификатора приложения GS1, который распространён в розничных штрих‑кодах.  

### Шаг 3: Установить общие параметры штрих‑кода  

Чаще всего настраиваются два визуальных параметра: X‑dimension (ширина узкой полосы) и общая высота полосы.  

```csharp
// Set the narrow bar width to 2 pixels
generator.Parameters.Barcode.XDimension.Pixels = 2;

// Set the initial bar height to 30 pixels
generator.Parameters.Barcode.BarHeight.Pixels = 30;
```

**X‑dimension** управляет плотностью штрих‑кода, тогда как **BarHeight** определяет вертикальный размер каждой полосы. Регулировка **BarHeight** именно то, что вам нужно, когда вы хотите **изменить высоту штрих‑кода** для разных печатных носителей.  

### Шаг 4: Сохранить первое изображение (высота 30 пикселей)  

```csharp
// Save the barcode as a 30‑pixel‑high PNG
generator.Save("DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);
```

Метод `Save` записывает отрисованное изображение на диск. Имя файла явно указывает использованную высоту, что помогает при сравнении разных результатов.  

### Шаг 5: Изменить высоту полосы до 60 пикселей  

Теперь мы демонстрируем **как настроить высоту полосы** во время выполнения. Тот же экземпляр `generator` переиспользуется; меняется только свойство `BarHeight`.  

```csharp
// Increase the bar height to 60 pixels
generator.Parameters.Barcode.BarHeight.Pixels = 60;

// Save the larger barcode
generator.Save("DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);
```

Поскольку генератор сохраняет все остальные настройки (символьность, данные, X‑dimension), единственное визуальное различие между двумя PNG‑файлами — вертикальный размер полос.  

### Полный исходный код  

Объединив всё вместе, получаем лаконичную, исполняемую программу:  

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Initialise the generator for Databar Omni‑Directional
            BarcodeGenerator generator = new BarcodeGenerator(
                EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");

            // 2️⃣ Configure visual parameters
            generator.Parameters.Barcode.XDimension.Pixels = 2;   // narrow bar width
            generator.Parameters.Barcode.BarHeight.Pixels = 30; // first height

            // 3️⃣ Save the 30‑pixel‑high image
            generator.Save("DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);
            Console.WriteLine("Saved 30‑pixel barcode.");

            // 4️⃣ Change the bar height to 60 pixels (how to adjust bar height)
            generator.Parameters.Barcode.BarHeight.Pixels = 60;

            // 5️⃣ Save the 60‑pixel‑high image
            generator.Save("DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);
            Console.WriteLine("Saved 60‑pixel barcode.");

            // Optional: clean up resources
            generator.Dispose();
        }
    }
}
```

**Ожидаемый результат**  

Запуск программы создаёт два PNG‑файла в рабочем каталоге исполняемого файла:  

* `DatabarBarHeight30Pixels.png` – штрих‑код с высотой полосы 30 px.  
* `DatabarBarHeight60Pixels.png` – тот же штрих‑код, но каждая полоса вдвое выше.  

Откройте изображения в любом просмотрщике; вы увидите, что общий узор остаётся идентичным, а вертикальное измерение меняется, подтверждая успешность операции **change barcode height**.  

## Расширенные варианты  

### Переключение на другую символьность  

Если вам нужен QR‑code вместо Databar, замените значение `EncodeTypes`:  

```csharp
generator = new BarcodeGenerator(EncodeTypes.QR, "https://example.com");
```

Все остальные параметры (X‑dimension, BarHeight) по‑прежнему применяются там, где это имеет смысл.  

### Использование `BarHeight` в миллиметрах  

Aspose.BarCode также поддерживает физические единицы измерения. Чтобы установить высоту 10 mm:  

```csharp
generator.Parameters.Barcode.BarHeight.Millimeters = 10;
```

Это удобно, когда вы генерируете штрих‑коды для печатных макетов, требующих точных размеров.  

### Обработка ошибок  

Если строка данных не соответствует выбранной символьности, `BarcodeGenerator` бросает `ArgumentException`. Оберните логику генерации в блок try‑catch, чтобы предоставить понятное сообщение:  

```csharp
try
{
    generator.Save("output.png", BarCodeImageFormat.Png);
}
catch (ArgumentException ex)
{
    Console.Error.WriteLine($"Invalid barcode data: {ex.Message}");
}
```

## Ответы на часто задаваемые вопросы  

* **Влияет ли изменение BarHeight на сканируемость?**  
  Штрих‑код остаётся сканируемым, пока X‑dimension и общий quiet zone соответствуют спецификациям символьности. Увеличение высоты лишь удлиняет полосы; контраст не ухудшается.  

* **Можно ли задать разную высоту отдельным полосам?**  
  Нет. Свойство `BarHeight` применяется одинаково ко всему символу. Для дизайнов с переменной высотой вам понадобится пользовательская процедура рендеринга, выходящая за рамки Aspose.BarCode.  

* **Является ли PNG лучшим форматом для печати?**  
  PNG сохраняет пиксельные данные без потерь, что делает его идеальным для отображения на экране. Для печати с высоким разрешением рассмотрите `BarCodeImageFormat.Tiff` или `Pdf`, чтобы сохранить векторную информацию.  

## Заключение  

Теперь вы знаете, как **создавать приложения с штрих‑кодом c#** с помощью Aspose.BarCode, видели полный **пример генератора штрих‑кода** и понимаете **как настроить высоту полосы**, чтобы соответствовать различным требованиям макета. Переиспользуя один и тот же экземпляр генератора и изменяя только `BarHeight`, вы можете эффективно **изменять высоту штрих‑кода** без пересоздания всего объекта.  

Далее вы можете изучить:  

* Генерацию других символьностей (`EncodeTypes.Code128`, `EncodeTypes.EAN13`).  
* Экспорт в SVG или PDF для масштабируемой графики.  
* Встраивание штрих‑кодов непосредственно в документы Word или Excel с помощью Aspose.Words или Aspose.Cells.  

Удачной разработки и наслаждайтесь гибкостью, которую Aspose.BarCode предоставляет вашим C# проектам со штрих‑кодами!  

## Что изучать дальше?  

Следующие руководства охватывают тесно связанные темы, построенные на техниках, продемонстрированных в этом руководстве. Каждый ресурс включает полные рабочие примеры кода с пошаговыми объяснениями, чтобы помочь вам освоить дополнительные возможности API и исследовать альтернативные подходы к реализации в ваших проектах.  

- [Как генерировать и настраивать высоту штрих‑кода для одностороннего Databar с помощью Aspose.BarCode для .NET](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-barcode-height-adjustment/)  
- [Как создать PNG‑файл штрих‑кода с регулируемой высотой в C#](/barcode/english/python-java/general/how-to-create-a-barcode-png-file-with-adjustable-height-in-c/)  
- [Как генерировать штрих‑код в C# – Полное руководство Aspose.BarCode](/barcode/english/python-java/general/how-to-generate-barcode-in-c-complete-aspose-barcode-guide/)  

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}