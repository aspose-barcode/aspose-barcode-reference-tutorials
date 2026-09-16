---
category: general
date: 2026-09-16
description: Узнайте, как создать макро‑PDF417 штрихкод в C# с помощью Aspose.BarCode
  — пошаговое руководство, охватывающее макет, X‑размер и метаданные макроса.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create macro PDF417 barcode
- Aspose.BarCode for .NET
- C# barcode generation
- PDF417 column layout
- macro PDF417 file segmentation
- barcode X-dimension setting
language: ru
lastmod: 2026-09-16
og_description: Создайте макро‑штрихкод PDF417 на C# с помощью Aspose.BarCode. Следуйте
  этому руководству, чтобы генерировать сегментированные штрихкоды, управлять X‑размером
  и задавать расположение столбцов.
og_image_alt: Screenshot of a generated macro PDF417 barcode created with C#
og_title: Создание макро‑штрихкода PDF417 в C# – полное руководство Aspose.BarCode
schemas:
- author: Aspose
  dateModified: '2026-09-16'
  description: Learn how to create macro PDF417 barcode in C# with Aspose.BarCode
    – step‑by‑step guide covering layout, X‑dimension, and macro metadata.
  headline: How to create macro PDF417 barcode in C# using Aspose.BarCode
  type: TechArticle
tags:
- Aspose
- C#
- Barcode
- PDF417
title: Как создать макро PDF417 штрих‑код в C# с помощью Aspose.BarCode
url: /ru/net/compact-pdf417-encoding/how-to-create-macro-pdf417-barcode-in-c-using-aspose-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Как создать макро‑PDF417 штрих‑код в C# с помощью Aspose.BarCode

Если вам нужно **создать макро‑PDF417 штрих‑код** в .NET‑приложении, это руководство покажет точные шаги. Вы увидите, как настроить визуальный вид, определить макет PDF417 и внедрить метаданные macro‑PDF417, чтобы штрих‑код можно было разбить на несколько файлов.

Создание макро‑PDF417 штрих‑кода часто требуется, когда нужно закодировать большие документы (например, многостраничные PDF) в серию штрих‑кодов, которые можно сканировать и позже собрать обратно. Это учебное пособие проходит через полностью готовый к запуску пример, объясняет, почему каждое значение важно, и выделяет типичные подводные камни.

К концу статьи у вас будет полностью рабочая программа на C#, генерирующая изображение макро‑PDF417 штрих‑кода, готовое к печати или отображению в пользовательском интерфейсе. Не требуется внешних инструментов, кроме библиотеки **Aspose.BarCode for .NET**.

## Требования

* .NET 6.0 SDK или новее (код также работает с .NET Framework 4.7+).  
* Действительная лицензия Aspose.BarCode for .NET (или временный оценочный ключ).  
* Visual Studio 2022, VS Code или любой IDE, поддерживающий C#.  

Если вы новичок в **генерации штрих‑кодов на C#**, возможно, стоит сначала прочитать статью быстрого старта Aspose.BarCode, но нижеизложенные шаги являются самостоятельными.

## Шаг 1: Создать генератор штрих‑кода для создания макро‑PDF417 штрих‑кода

Первый объект, который вам нужен, — `BarcodeGenerator`. Он сообщает Aspose.BarCode, какую символьную систему использовать и какой исходный текст кодировать.

```csharp
using Aspose.BarCode.Generation;

// The EncodeTypes enum contains all supported symbologies.
// EncodeTypes.MacroPdf417 selects the macro PDF417 mode.
var generator = new BarcodeGenerator(EncodeTypes.MacroPdf417, "Sample text for macro PDF417");
```

**Почему это важно:** Выбор `MacroPdf417` заставляет движок добавить дополнительные макрополя (идентификатор файла, идентификатор сегмента и т.д.), которые позволяют сегментировать файл. Без этого режима вы получите обычный PDF417 штрих‑код, который нельзя собрать в много‑сегментный файл.

## Шаг 2: Установить X‑размер штрих‑кода (визуальный вид)

X‑размер управляет шириной самого маленького модуля («пикселя» штрих‑кода). Его настройка влияет как на читаемость, так и на размер печати.

```csharp
// Set the module width to 2 pixels. Smaller values produce denser barcodes.
generator.Parameters.Barcode.XDimension.Pixels = 2;
```

**Почему стоит подрегулировать X‑размер:** Слишком маленький X‑размер может сделать штрих‑код нечитаемым для сканеров низкого разрешения, а слишком большой — тратить место. **Настройка X‑размера штрих‑кода** особенно важна для macro PDF417, поскольку каждый сегмент добавляет дополнительные строки данных.

## Шаг 3: Настроить раскладку столбцов PDF417

PDF417 позволяет задать количество столбцов (т.е. кодовых слов в строке), которое должен содержать штрих‑код. Большее количество столбцов делает штрих‑код короче, но требует более высокого разрешения печати.

```csharp
// Choose a column count that balances size and readability.
// 5 columns is a good starting point for screen display.
generator.Parameters.Barcode.Pdf417.Columns = 5;
```

**Почему количество столбцов имеет значение:** **Расположение столбцов PDF417** напрямую влияет на высоту штрих‑кода. При большом числе макросегментов компактное количество столбцов предотвращает чрезмерную высоту конечного изображения.

## Шаг 4: Добавить метаданные macro PDF417 для сегментации файла

Macro‑PDF417 использует несколько полей для идентификации и восстановления оригинального файла. Вы должны установить каждое поле последовательно во всех сегментах.

```csharp
// Unique identifier for the whole file (must be the same for every segment)
generator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;

// Segment identification – start counting at 1
generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 1;

// Total number of segments that will be generated
generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 3;

// Original file name (optional but helpful for the reassembly process)
generator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "myFile.pdf";

// CCITT‑16 checksum – Aspose can calculate it automatically,
// but you can also provide a custom value if needed.
generator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 4321;
```

**Почему каждое поле необходимо:**

| Field | Purpose |
|-------|---------|
| **MacroPdf417FileID** | Уникально связывает все сегменты; сканеры используют его для группировки штрих‑кодов. |
| **MacroPdf417SegmentID** | Указывает номер текущего сегмента (нумерация с 1). |
| **MacroPdf417SegmentsCount** | Сообщает сканеру, сколько сегментов следует ожидать. |
| **MacroPdf417FileName** | Необязательное человекочитаемое имя, отображаемое после сборки. |
| **MacroPdf417Checksum** | Проверяет целостность данных между сегментами; несоответствие контрольных сумм приводит к ошибке сборки. |

При генерации дополнительных сегментов меняется только `MacroPdf417SegmentID` (2, 3, …). Все остальные поля остаются одинаковыми.

## Шаг 5: Сохранить изображение штрих‑кода

Наконец, запишите штрих‑код в файл. Перечисление `BarCodeImageFormat` позволяет выбрать PNG, JPEG, BMP и др.

```csharp
// Ensure the output directory exists or create it beforehand.
string outputPath = @"C:\Barcodes\MacroPdf417.png";

generator.Save(outputPath, BarCodeImageFormat.Png);
Console.WriteLine($"Macro PDF417 barcode saved to {outputPath}");
```

**Результат:** Программа создает PNG‑изображение (`MacroPdf417.png`), содержащее полностью квалифицированный макро‑PDF417 штрих‑код. Вы можете открыть файл в любом просмотрщике изображений или встроить его в PDF‑отчет.

---

![Macro PDF417 barcode generated by Aspose.BarCode in C#](placeholder-image.png "Macro PDF417 barcode created with C#")

*Текст альтернативного изображения (для SEO и доступности):* **create macro PDF417 barcode** – скриншот сгенерированного макро‑PDF417 штрих‑кода, созданного с помощью C#.

## Полный, исполняемый пример

Ниже приведена полная программа, которую можно скопировать, вставить и запустить. В ней включены все необходимые директивы `using` и минимальный метод `Main`.

```csharp
using System;
using Aspose.BarCode.Generation;

namespace MacroPdf417Demo
{
    class Program
    {
        static void Main(string[] args)
        {
            // 1. Initialize the generator for macro PDF417
            var generator = new BarcodeGenerator(EncodeTypes.MacroPdf417, "Sample text for macro PDF417");

            // 2. Visual appearance – X‑dimension
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // 3. Layout – number of columns
            generator.Parameters.Barcode.Pdf417.Columns = 5;

            // 4. Macro metadata – file segmentation
            generator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
            generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 1;          // segment 1 of 3
            generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 3;
            generator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "myFile.pdf";
            generator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 4321;

            // 5. Save the barcode image
            string outputPath = @"C:\Barcodes\MacroPdf417.png";
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"Macro PDF417 barcode saved to {outputPath}");
        }
    }
}
```

**Ожидаемый вывод:** PNG‑файл с именем `MacroPdf417.png`, содержащий штрих‑код, который при сканировании читателем, поддерживающим macro‑PDF417, собирает оригинальные данные и отображает имя файла `myFile.pdf`.

## Часто задаваемые вопросы и обработка граничных случаев

| Вопрос | Ответ |
|----------|--------|
| *Нужно ли рассчитывать контрольную сумму вручную?* | Aspose.BarCode может вычислять контрольную сумму автоматически, если вы опустите `MacroPdf417Checksum`. Указывайте значение только в случае, если у вас уже есть предрасчитанная контрольная сумма из другого источника. |
| *Что делать, если мой файл превышает максимальную ёмкость одного сегмента PDF417?* | Разделите данные на несколько сегментов и увеличьте `MacroPdf417SegmentID` для каждого. Сохраняйте одинаковое значение `MacroPdf417SegmentsCount` во всех сегментах. |
| *Можно ли генерировать все сегменты в цикле?* | Да. Оберните шаги 1‑5 в цикл `for`, меняя только `MacroPdf417SegmentID` и имя выходного файла для каждой итерации. |
| *Какое разрешение следует использовать для печати?* | Рекомендуется минимум 300 dpi для макро‑PDF417 штрих‑кодов, особенно когда X‑размер установлен в 2 пикселя. |
| *Является ли PNG лучшим форматом?* | PNG сохраняет без потерь, что идеально для сканирования штрих‑кодов. JPEG может использоваться для уменьшения размера файла, но может ввести артефакты сжатия. |

## Заключение

Теперь вы знаете, как **создать макро‑PDF417 штрих‑код** в C# с помощью Aspose.BarCode, управлять **X‑размером штрих‑кода**, настраивать **раскладку столбцов PDF417** и внедрять необходимые метаданные **macro PDF417 для сегментации файла**. Полный пример демонстрирует готовый к производству подход, который вы можете адаптировать.

## Что изучать дальше?

Следующие учебные материалы охватывают тесно связанные темы, построенные на техниках, продемонстрированных в этом руководстве. Каждый ресурс включает полные рабочие примеры кода с пошаговыми объяснениями, чтобы помочь вам освоить дополнительные возможности API и исследовать альтернативные подходы в ваших проектах.

- [Генерация штрих‑кода с текстом – Полное руководство по PDF417 Macro](/barcode/english/net/compact-pdf417-encoding/generate-barcode-with-text-full-pdf417-macro-guide/)
- [Создание метаданных PDF417 штрих‑кода в C# – Полное пошаговое руководство](/barcode/english/net/compact-pdf417-encoding/create-pdf417-barcode-metadata-in-c-complete-step-by-step-gu/)
- [Как создать штрих‑код – Compact PDF417 с Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}