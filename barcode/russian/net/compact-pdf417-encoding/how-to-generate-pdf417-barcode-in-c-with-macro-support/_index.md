---
category: general
date: 2026-10-21
description: Узнайте, как генерировать штрих‑код PDF417 на C# с помощью Aspose.BarCode.
  Подробные шаги охватывают настройки штрих‑кода PDF417, создание макро‑PDF417 и сохранение
  в формате PNG.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to generate PDF417 barcode
- PDF417 barcode settings
- Macro PDF417 barcode
- barcode generator C#
- BarCodeImageFormat PNG
- EncodeTypes.MacroPdf417
language: ru
lastmod: 2026-10-21
og_description: Как создать штрих‑код PDF417 в C# с помощью Aspose.BarCode. Следуйте
  этому пошаговому руководству, чтобы настроить параметры штрих‑кода PDF417, создать
  макрос‑штрих‑код PDF417 и экспортировать его в PNG.
og_image_alt: Screenshot of a Macro PDF417 barcode generated with C# code
og_title: Как сгенерировать штрих‑код PDF417 в C# – полное руководство
schemas:
- author: Aspose
  dateModified: '2026-10-21'
  description: Learn how to generate PDF417 barcode in C# using Aspose.BarCode. Detailed
    steps cover PDF417 barcode settings, macro PDF417 barcode creation, and saving
    as PNG.
  headline: How to generate PDF417 barcode in C# with macro support
  type: TechArticle
- description: Learn how to generate PDF417 barcode in C# using Aspose.BarCode. Detailed
    steps cover PDF417 barcode settings, macro PDF417 barcode creation, and saving
    as PNG.
  name: How to generate PDF417 barcode in C# with macro support
  steps:
  - name: '**Create a `BarcodeGenerator` instance** using `EncodeTypes.MacroPdf417`.'
    text: '**Create a `BarcodeGenerator` instance** using `EncodeTypes.MacroPdf417`.'
  - name: '**Adjust basic barcode appearance** (module size, colors, etc.).'
    text: '**Adjust basic barcode appearance** (module size, colors, etc.).'
  - name: '**Configure PDF417‑specific settings**, including macro‑related fields.'
    text: '**Configure PDF417‑specific settings**, including macro‑related fields.'
  - name: '**Save the generated barcode image** with `BarCodeImageFormat PNG`.'
    text: '**Save the generated barcode image** with `BarCodeImageFormat PNG`.'
  type: HowTo
tags:
- PDF417
- barcode
- C#
- Aspose.BarCode
title: Как сгенерировать штрих‑код PDF417 в C# с поддержкой макросов
url: /ru/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-with-macro-support/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Как сгенерировать штрих‑код PDF417 в C# с поддержкой макросов

Если вам нужно сгенерировать штрих‑код PDF417 в C#, это руководство покажет готовое решение, которое можно сразу запустить. Независимо от того, создаёте ли вы систему этикеток для логистики или кодируете большие блоки данных, вы увидите, как настроить параметры PDF417, создать макрос‑штрих‑код PDF417 и сохранить результат в виде PNG‑изображения.

Генерация штрих‑кода PDF417 не требует низкоуровневой работы с битами. Используя **barcode generator C#** класс из Aspose.BarCode, вы можете сосредоточиться на бизнес‑логике, а библиотека позаботится об кодировании, коррекции ошибок и рендеринге изображения.

## Что вам понадобится

Прежде чем начать, убедитесь, что у вас есть:

- **.NET 6.0** или новее (код также работает с .NET Framework 4.6+)
- NuGet‑пакет **Aspose.BarCode for .NET** (`Install-Package Aspose.BarCode`)
- Среда разработки, например Visual Studio 2022 или Visual Studio Code
- Права записи в папку, куда будет сохраняться PNG‑изображение

Эти предварительные требования гарантируют, что пример скомпилируется и запустится без дополнительной настройки.

## Как сгенерировать штрих‑код PDF417 – пошаговый обзор

Ниже представлена краткая дорожная карта процесса:

1. **Создать экземпляр `BarcodeGenerator`** с использованием `EncodeTypes.MacroPdf417`.
2. **Настроить базовый внешний вид штрих‑кода** (размер модуля, цвета и т.д.).
3. **Сконфигурировать специфические для PDF417 параметры**, включая поля макроса.
4. **Сохранить сгенерированное изображение штрих‑кода** с помощью `BarCodeImageFormat PNG`.

Каждый шаг подробно объяснён ниже, с полными фрагментами кода, которые можно скопировать прямо в консольное приложение.

## Шаг 1: Настройка среды разработки

Создайте новый консольный проект и добавьте ссылку на Aspose.BarCode:

```bash
dotnet new console -n Pdf417Demo
cd Pdf417Demo
dotnet add package Aspose.BarCode
```

Откройте `Program.cs` и добавьте необходимые пространства имён:

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;
```

Эти импорты дают доступ к `BarcodeGenerator`, `EncodeTypes` и `BarCodeImageFormat`.

## Шаг 2: Создание генератора макрос‑PDF417

Первая строка реализации создаёт объект **Macro PDF417 barcode**. Перечисление `EncodeTypes.MacroPdf417` указывает библиотеке использовать макрос‑вариант PDF417.

```csharp
// Step 1: Create a Macro PDF417 barcode generator with the desired text
using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MacroPdf417, "Sample Text"))
{
    // Subsequent configuration goes here
}
```

> **Почему это важно:** Использование `EncodeTypes.MacroPdf417` включает макрос‑поля (`FileID`, `SegmentID` и др.), позволяющие разбить большой полезный груз на несколько изображений штрих‑кода, сохраняя порядок.

## Шаг 3: Настройка базового внешнего вида штрих‑кода

Прежде чем менять параметры, специфичные для PDF417, задайте ширину модуля (пикселя). Значение `2` даёт чёткое, сканируемое изображение без излишнего размера файла.

```csharp
// Step 2: Adjust basic barcode appearance
generator.Parameters.Barcode.XDimension.Pixels = 2;   // pixel width of a single module
```

Здесь же можно изменить цвета переднего и заднего плана, если ваш UI требует иной палитры.

## Шаг 4: Конфигурация параметров PDF417

Параметры **PDF417 barcode** доступны через `generator.Parameters.Barcode.Pdf417`. Ниже показаны самые важные макрос‑поля:

```csharp
// Step 3: Configure PDF417‑specific settings
generator.Parameters.Barcode.Pdf417.Columns = 5;                     // number of columns (affects width)
generator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;     // unique file identifier
generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;       // segment number within the file
generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;  // total number of segments
generator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";  // optional human‑readable name
```

### Понимание каждого свойства

| Property | Purpose | Typical range |
|----------|---------|---------------|
| `Columns` | Controls how many data columns each row contains. More columns reduce the number of rows but increase width. | 1 – 30 |
| `MacroPdf417FileID` | A 32‑bit identifier that groups all segments of the same logical file. Must be the same for every segment. | Any positive integer |
| `MacroPdf417SegmentID` | Zero‑based index of the current segment. Increment for each subsequent barcode. | 0 – `SegmentsCount`‑1 |
| `MacroPdf417SegmentsCount` | Total number of segments that compose the full file. All segments must be generated. | ≥ 1 |
| `MacroPdf417FileName` | Optional descriptive name (max 255 characters). Helpful for debugging. | Alphanumeric string |

> **Полезный совет:** Держите `Columns` в диапазоне от 3 до 7 для большинства принтеров этикеток. Большие значения могут превысить печатную ширину на устройствах с низким разрешением.

## Шаг 5: Сохранение штрих‑кода в PNG‑изображение

Наконец, запишите штрих‑код на диск с помощью `BarCodeImageFormat PNG`. PNG сохраняет без потерь, что критично для надёжного сканирования.

```csharp
// Step 4: Save the generated barcode image
string outputPath = Path.Combine(Environment.CurrentDirectory, "MacroPdf417.png");
generator.Save(outputPath, BarCodeImageFormat.Png);
```

После завершения программы вы найдёте `MacroPdf417.png` в папке проекта. Открытие файла покажет чистый макрос‑штрих‑код PDF417, готовый к печати.

### Ожидаемый результат

Сгенерированное изображение выглядит примерно так (только для иллюстрации):

![Пример штрих‑кода Macro PDF417](macro-pdf417-barcode.png "Штрих‑код Macro PDF417, сгенерированный кодом C#")

*Текст alt‑атрибута изображения – “Macro PDF417 barcode generated with C# code”, удовлетворяет требованиям доступности и SEO.*

## Распространённые ошибки и их устранение

| Проблема | Симптом | Решение |
|----------|---------|---------|
| **Неправильный `EncodeTypes`** | Штрих‑код отображается как QR‑код или обычный текст. | Убедитесь, что используете `EncodeTypes.MacroPdf417` (а не `EncodeTypes.Pdf417`). |
| **Несоответствие идентификаторов сегментов** | Сканер сообщает “missing segment”. | Последовательно увеличивайте `MacroPdf417SegmentID` и держите `SegmentsCount` одинаковым во всех файлах. |
| **Слишком большой размер модуля** | Штрих‑код слишком широк для этикетки. | Уменьшите `XDimension.Pixels` или уменьшите `Columns`. |
| **Ошибки пути к файлу** | `UnauthorizedAccessException` при сохранении. | Сохраняйте в папку, где у вас есть права, например `Environment.CurrentDirectory`. |
| **Отсутствует NuGet‑пакет** | Ошибка компиляции: `BarcodeGenerator` не найден. | Выполните `dotnet add package Aspose.BarCode` перед сборкой. |

Раннее устранение этих проблем экономит время при интеграции генерации штрих‑кодов в более крупные рабочие процессы.

## Расширение примера

Теперь, когда вы умеете генерировать один макрос‑PDF417, рассмотрите следующие шаги:

- **Пакетная генерация**: Циклически обрабатывайте коллекцию фрагментов данных, обновляя `MacroPdf417SegmentID` на каждой итерации.
- **Другие форматы изображений**: Замените `BarCodeImageFormat.Png` на `Jpeg` или `Bmp`, если ваша downstream‑система предпочитает их.
- **Встраивание в PDF**: Используйте Aspose.PDF, чтобы разместить PNG в PDF‑отчёте для распространения.
- **Проверка сканирования**: Протестируйте сгенерированные штрих‑коды на аппаратном сканере или мобильном приложении, поддерживающем Macro PDF417.

Эти варианты сохраняют основные **PDF417 barcode settings**, адаптируя вывод под нужды вашего проекта.

## Заключение

Теперь вы знаете, **как сгенерировать штрих‑код PDF417** в C# с помощью Aspose.BarCode: от создания `BarcodeGenerator` с `EncodeTypes.MacroPdf417` до настройки макрос‑полей и сохранения результата как `BarCodeImageFormat PNG`. Полный, готовый к запуску код демонстрирует рекомендованный подход, объясняет, почему важна каждая настройка, и подчёркивает типичные подводные камни.

Экспериментируйте с количеством колонок, цветами или форматами вывода и интегрируйте генератор в свои приложения для надёжного, высокоплотного кодирования данных.

## Что вам стоит изучить дальше?

Следующие руководства охватывают тесно связанные темы, которые развивают техники, показанные в этом руководстве. Каждый ресурс включает полностью работающие примеры кода с пошаговыми объяснениями, чтобы помочь вам освоить дополнительные возможности API и исследовать альтернативные подходы в собственных проектах.

- [Как генерировать штрих‑коды PDF417 в C# с Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcodes-in-c-with-aspose-barcode/)
- [Как создать макрос‑PDF417 штрих‑код в C# с использованием Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/how-to-create-macro-pdf417-barcode-in-c-using-aspose-barcode/)
- [Как сохранить штрих‑код и сгенерировать PDF417 с Aspose в C#](/barcode/english/net/compact-pdf417-encoding/how-to-save-barcode-and-generate-pdf417-with-aspose-in-c/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}