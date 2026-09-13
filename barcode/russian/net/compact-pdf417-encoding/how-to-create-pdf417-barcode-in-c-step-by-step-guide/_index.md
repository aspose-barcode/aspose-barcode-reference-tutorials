---
category: general
date: 2026-09-13
description: Узнайте, как создавать штрих‑код PDF417 в C# и быстро генерировать изображения
  штрих‑кода PDF417 с полным, готовым к запуску примером.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create pdf417 barcode
- generate pdf417 barcode
- create barcode image c#
language: ru
lastmod: 2026-09-13
og_description: Создайте штрих‑код PDF417 на C# и генерируйте изображения штрих‑кода
  PDF417 с помощью этого краткого руководства. Следуйте полному примеру и мгновенно
  получите файл PNG.
og_image_alt: Screenshot of a PDF417 barcode generated in C#
og_title: Создание штрихкода PDF417 на C# – полное руководство по программированию
schemas:
- author: Aspose
  dateModified: '2026-09-13'
  description: Learn how to create pdf417 barcode in C# and generate pdf417 barcode
    images quickly with a complete, runnable example.
  headline: How to create pdf417 barcode in C# – step‑by‑step guide
  type: TechArticle
tags:
- barcode
- C#
- PDF417
title: Как создать штрих‑код pdf417 в C# – пошаговое руководство
url: /ru/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-in-c-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Как создать штрих‑код pdf417 в C# – пошаговое руководство

Если вам нужно **создать штрих‑код pdf417** в приложении .NET, это руководство покажет, как это сделать. Вы увидите, как генерировать изображения штрих‑кода pdf417 в C# с помощью библиотеки Aspose.BarCode, и получите готовый PNG‑файл.

Создание штрих‑кода — распространённая задача для систем учёта, билетов или проверки документов. К концу этого руководства вы сможете **создавать изображения штрих‑кода pdf417** программно, настраивать ключевые параметры, такие как ширина модуля, количество столбцов и строк, и сохранять результат в PNG без внешних инструментов.

## Что понадобится

- .NET 6.0 или новее (код также работает на .NET Framework 4.7+)
- Ссылка на NuGet‑пакет **Aspose.BarCode for .NET**  
  ```bash
  dotnet add package Aspose.BarCode
  ```
- Базовые знания синтаксиса C# и среда разработки (Visual Studio, VS Code или Rider)

## Шаг 1: Создайте проект и импортируйте пространства имён

Создайте новый консольный проект (или добавьте код в существующий) и импортируйте необходимые пространства имён. Этот шаг подготавливает окружение для генерации штрих‑кода.

```csharp
using System;
using Aspose.BarCode.Generation;   // Core barcode generation classes
using Aspose.BarCode;               // For BarCodeImageFormat enumeration
```

**Почему это важно:** Импорт `Aspose.BarCode.Generation` даёт доступ к `BarcodeGenerator` — классу, который действительно создаёт штрих‑код. Пространство имён `Aspose.BarCode` содержит перечисление форматов изображений, которое вы будете использовать при **сохранении изображения штрих‑кода**.

## Шаг 2: Инициализируйте BarcodeGenerator с настройками PDF417

Конструктор `BarcodeGenerator` принимает два аргумента: тип штрих‑кода (`EncodeTypes.Pdf417`) и текст, который нужно закодировать. Здесь мы кодируем строку `"Layout demo"`.

```csharp
// Step 2: Initialise generator for PDF417
using (var barcodeGenerator = new BarcodeGenerator(EncodeTypes.Pdf417, "Layout demo"))
{
    // All further configuration goes inside this block
```

**Почему это важно:** Выбор `EncodeTypes.Pdf417` сообщает библиотеке использовать 2‑D‑символику PDF417, идеальную для хранения больших объёмов данных и широко поддерживаемую в логистике и удостоверениях личности.

## Шаг 3: Настройте X‑размер (ширина модуля)

X‑размер контролирует ширину каждого отдельного модуля (самого маленького чёрного или белого элемента). Установка в пикселях даёт точный контроль над конечным размером изображения.

```csharp
    // Step 3: Set module width to 2 pixels
    barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

**Почему это важно:** Меньший X‑размер делает штрих‑код более компактным, а больший — упрощает сканирование на расстоянии. Регулируйте это значение в зависимости от условий сканирования вашего приложения.

## Шаг 4: Задайте макет — столбцы и строки

PDF417 позволяет указать, сколько столбцов и строк будет использовать штрих‑код. Это влияет как на размер, так и на ёмкость данных.

```csharp
    // Step 4: Define layout
    barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 4; // Number of data columns
    barcodeGenerator.Parameters.Barcode.Pdf417.Rows    = 9; // Number of rows (height)
```

**Почему это важно:** Управление столбцами и строками позволяет точно подобрать штрих‑код под конкретные размеры этикетки или ограничения печати. Слишком много строк сделают штрих‑код слишком высоким; слишком мало столбцов могут уменьшить ёмкость данных.

## Шаг 5: Сохраните штрих‑код как PNG‑изображение

Наконец, запишите сгенерированный штрих‑код на диск. Метод `Save` принимает путь к файлу и желаемый формат изображения.

```csharp
    // Step 5: Save as PNG
    barcodeGenerator.Save("LayoutPdf417.png", BarCodeImageFormat.Png);
}
```

При запуске программы в каталоге вывода появится файл **LayoutPdf417.png**. Открыв его, вы увидите чистый штрих‑код PDF417, кодирующий текст `"Layout demo"`.

### Ожидаемый результат

![Скриншот штрих‑кода PDF417, сгенерированного в C#](placeholder-image.png "PDF417 barcode created with C#")

*Текст альтернативного описания изображения:* **Скриншот штрих‑кода PDF417, сгенерированного в C#** (соответствует `og_image_alt` для доступности).

## Полный, готовый к запуску пример

Объединив все части, получаем самостоятельное консольное приложение, которое можно скопировать, вставить и запустить.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

namespace Pdf417Demo
{
    class Program
    {
        static void Main(string[] args)
        {
            // Initialise generator for PDF417 with the desired text
            using (var barcodeGenerator = new BarcodeGenerator(EncodeTypes.Pdf417, "Layout demo"))
            {
                // Set the X‑dimension (module width) in pixels
                barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;

                // Define layout: 4 columns and 9 rows
                barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 4;
                barcodeGenerator.Parameters.Barcode.Pdf417.Rows    = 9;

                // Save the generated barcode as a PNG image
                barcodeGenerator.Save("LayoutPdf417.png", BarCodeImageFormat.Png);
            }

            Console.WriteLine("PDF417 barcode created successfully: LayoutPdf417.png");
        }
    }
}
```

**Как проверить:** После запуска программы перейдите в папку с скомпилированным бинарным файлом. Вы должны увидеть `LayoutPdf417.png`. Откройте его в любом просмотрщике изображений — штрих‑код будет чётко виден и считываем стандартными сканерами PDF417.

## Распространённые варианты и граничные случаи

| Ситуация | Что изменить | Почему |
|-----------|----------------|-----|
| **Более высокая плотность данных** | Увеличьте `Columns` (например, до 6) и при желании уменьшите `Rows` | Больше столбцов упаковывают данные по горизонтали, полезно для узких этикеток. |
| **Большая область печати** | Увеличьте `XDimension.Pixels` (например, до 4) | Большие модули упрощают сканирование с расстояния. |
| **Другой формат изображения** | Используйте `BarCodeImageFormat.Jpeg` или `Bmp` в вызове `Save` | Выберите формат, соответствующий вашему последующему конвейеру обработки. |
| **Пользовательские цвета переднего/фонового плана** | Установите `barcodeGenerator.Parameters.Barcode.ForeColor` и `BackColor` | Улучшает читаемость на цветных фонах или при печати на тёмных носителях. |
| **Кодирование Unicode‑символов** | Передайте Unicode‑строку (например, `"Пример"`). PDF417 поддерживает Unicode из коробки. | Позволяет использовать международный текст без дополнительной настройки. |

**Совет:** Всегда проверяйте сгенерированный штрих‑код на реальном сканере, который планируете использовать. У некоторых сканеров есть минимальные требования к размеру модуля; корректировка `XDimension` поможет избежать ошибок чтения.

## Часто задаваемые вопросы

**В: Работает ли это с .NET Core?**  
Да. Пакет `Aspose.BarCode` нацелен на .NET Standard 2.0, совместимый с .NET Core, .NET 5+, и .NET Framework.

**В: Можно ли генерировать несколько штрих‑кодов в цикле?**  
Конечно. Поместите блок `using` внутрь `foreach`‑цикла и меняйте текст или параметры макета для каждой итерации.

**В: Как встроить штрих‑код в PDF?**  
После генерации PNG загрузите его в библиотеку работы с PDF (например, iText7 или Aspose.PDF) и разместите на странице. Шаг генерации штрих‑кода остаётся тем же.

## Заключение

Теперь вы знаете, как **создавать изображения штрих‑кода pdf417** в C# с помощью Aspose.BarCode. Руководство охватило инициализацию генератора, настройку X‑размера, установку столбцов и строк, а также сохранение результата в PNG‑файл. С этой базой вы сможете **генерировать графику штрих‑кода pdf417** для биркок инвентаря, посадочных талонов или любых сценариев, требующих компактных 2‑D‑штрих‑кодов с высокой ёмкостью.

Далее попробуйте **create barcode image c#** для других символьных наборов, таких как QR, Code‑128 или DataMatrix, заменив `EncodeTypes.Pdf417` на нужный тип. Экспериментируйте с цветами, уровнями коррекции ошибок и встраиванием изображения напрямую в PDF или отчёты, чтобы расширить решение.

Счастливого кодинга!

## Что изучать дальше?

Следующие руководства охватывают тесно связанные темы, которые развивают техники, продемонстрированные в этом гайде. Каждый ресурс включает полностью рабочие примеры кода с пошаговыми объяснениями, помогая вам освоить дополнительные возможности API и исследовать альтернативные подходы в собственных проектах.

- [Create PDF417 Barcode Metadata in C# – Complete Step‑by‑Step Guide](/barcode/english/net/compact-pdf417-encoding/create-pdf417-barcode-metadata-in-c-complete-step-by-step-gu/)
- [How to Read PDF417 in C# – Complete Barcode Example](/barcode/english/net/compact-pdf417-encoding/how-to-read-pdf417-in-c-complete-barcode-example/)
- [Create PDF417 Barcode in C# – Complete Programming Guide](/barcode/english/net/compact-pdf417-encoding/create-pdf417-barcode-in-c-complete-programming-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}