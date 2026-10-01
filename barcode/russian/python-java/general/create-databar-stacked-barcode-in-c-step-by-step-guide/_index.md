---
category: general
date: 2026-08-06
description: Быстро создавайте штрих‑код DataBar Stacked в C#. Узнайте, как задать
  размер X, отрегулировать соотношение сторон и экспортировать PNG‑файлы с помощью
  генератора DataBar Stacked Omnidirectional.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create databar stacked barcode
- DataBar Stacked Omnidirectional
- barcode aspect ratio
- BarcodeGenerator C#
- BarCodeImageFormat PNG
language: ru
lastmod: 2026-08-06
og_description: Создайте штрих‑код Databar Stacked в C# с помощью Aspose.BarCode.
  Этот учебник показывает, как настроить размер X, изменить соотношение сторон и сохранить
  изображения в формате PNG.
og_image_alt: Screenshot of two PNG files generated from a DataBar Stacked Omnidirectional
  barcode with different aspect ratios
og_title: Создание стэкового штрихкода Databar в C# — полное руководство по программированию
schemas:
- author: Aspose
  dateModified: '2026-08-06'
  description: Create databar stacked barcode in C# quickly. Learn to set X dimension,
    adjust aspect ratio, and export PNG files using the DataBar Stacked Omnidirectional
    generator.
  headline: Create databar stacked barcode in C# – step‑by‑step guide
  type: TechArticle
tags:
- barcode
- C#
- Aspose.BarCode
title: Создание штрих‑кода Databar Stacked в C# – пошаговое руководство
url: /ru/python-java/general/create-databar-stacked-barcode-in-c-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Создание датабар-стекового штрихкода в C# – пошаговое руководство

Если вам нужно **создать датабар-стековый штрихкод** в C#, это руководство покажет, как сделать это с помощью библиотеки Aspose.BarCode. Вы научитесь задавать X‑размер, менять соотношение сторон штрихкода и сохранять результат в виде PNG‑файлов — всё за несколько лаконичных шагов.

Создание DataBar Stacked штрихкода часто требуется, когда необходимо закодировать данные GS1‑128 для розничного сканирования или отслеживания логистики. В последующих разделах мы рассмотрим всё — от настройки проекта до проверки результата, чтобы вы могли интегрировать решение в любое .NET‑приложение без упущений.

## Необходимые условия

* **.NET 6.0** (или новее) установлен — код ориентирован на современный SDK.
* **Лицензированная** копия **Aspose.BarCode for .NET**. Бесплатная оценочная версия подходит для тестирования, но добавляет водяной знак.
* IDE, например **Visual Studio 2022** или **VS Code** с расширением C#.
* Базовое знакомство с синтаксисом **C#** и концепцией идентификаторов приложений GS1.

> **Совет:** Если вы используете менеджер пакетов NuGet, команда `dotnet add package Aspose.BarCode` автоматически разрешит все зависимости.

## Шаг 1: Создайте новый консольный проект

Откройте терминал или консоль диспетчера пакетов и выполните:

```bash
dotnet new console -n DatabarStackedDemo
cd DatabarStackedDemo
dotnet add package Aspose.BarCode
```

Команда `dotnet new console` создаёт минимальный файл **Program.cs**. Добавление пакета **Aspose.BarCode** делает доступным класс `BarcodeGenerator`.

## Шаг 2: Инициализируйте генератор DataBar Stacked Omnidirectional

Откройте **Program.cs** и замените содержимое по умолчанию следующим кодом. Первая строка создаёт **BarcodeGenerator**, настроенный для символьного набора **DataBar Stacked Omnidirectional**, и передаёт полезную нагрузку GS1‑128.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Step 2: Initialize the generator for a DataBar Stacked Omnidirectional barcode
        // "(01)12345678901231" encodes a GTIN‑14 with Application Identifier (01)
        var generator = new BarcodeGenerator(
            EncodeTypes.DatabarStackedOmniDirectional,
            "(01)12345678901231");

        // Continue with configuration...
```

**Почему это важно:** Значение перечисления `EncodeTypes.DatabarStackedOmniDirectional` указывает библиотеке генерировать **databar stacked barcode**, который является стековой вариацией семейства omnidirectional DataBar. Эта символьная система может содержать до 14 цифровых символов, что делает её идеальной для кодов GTIN‑14.

## Шаг 3: Установите X‑размер (ширина модуля)

X‑размер определяет ширину самого маленького штриха (модуля). Слишком маленькое значение может плохо отображаться на принтерах с низким разрешением, а слишком большое — превысить доступное пространство этикетки.

```csharp
        // Step 3: Define the module width – 2 pixels gives a crisp, printable barcode
        generator.Parameters.Barcode.XDimension.Pixels = 2;
```

> **Подсказка:** Свойство `Pixels` удобно для тестирования на экране. Для сценариев, ориентированных на печать, используйте `generator.Parameters.Barcode.XDimension.Millimeters`.

## Шаг 4: Настройте соотношение сторон и сохраните первое изображение

**Соотношение сторон** влияет на соотношение высоты к ширине стекового штрихкода. Тип DataBar Stacked Omnidirectional поддерживает соотношения от 10 до 30. Мы сгенерируем два изображения, чтобы продемонстрировать визуальный эффект.

```csharp
        // Step 4a: Set aspect ratio to 15 (default is 15) and save as PNG
        generator.Parameters.Barcode.DataBar.AspectRatio = 15;
        generator.Save("DatabarAspectRatio15.png", BarCodeImageFormat.Png);
```

Вызов `generator.Save` записывает файл **PNG** в текущий рабочий каталог. Перечисление `BarCodeImageFormat.Png` обеспечивает сжатие без потерь, что идеально подходит для дальнейшей обработки или встраивания в PDF.

## Шаг 5: Измените соотношение сторон на 30 и сохраните второе изображение

Теперь мы увеличиваем высоту стековых штрихов, изменив соотношение сторон на **30**. Это делает штрихкод выше, не меняя X‑размер.

```csharp
        // Step 5a: Increase aspect ratio to 30 for a taller barcode
        generator.Parameters.Barcode.DataBar.AspectRatio = 30;
        generator.Save("DatabarAspectRatio30.png", BarCodeImageFormat.Png);

        Console.WriteLine("Two barcode images have been generated:");
        Console.WriteLine(" • DatabarAspectRatio15.png");
        Console.WriteLine(" • DatabarAspectRatio30.png");
    }
}
```

Запуск программы теперь создаёт два PNG‑файла:

* **DatabarAspectRatio15.png** — компактный штрихкод, подходящий для небольших этикеток.
* **DatabarAspectRatio30.png** — более высокий штрихкод, повышающий надёжность сканирования на поверхностях с низким контрастом.

Вы можете открыть изображения в любом просмотрщике, чтобы убедиться, что штрихи правильно сложены и закодированные данные соответствуют исходной строке GS1.

## Шаг 6: Проверьте закодированное значение (по желанию)

Если необходимо убедиться, что штрихкод действительно представляет исходную строку, вы можете декодировать его той же библиотекой:

```csharp
        // Optional: Decode the generated PNG to ensure correctness
        var decoder = new BarCodeReader("DatabarAspectRatio15.png", DecodeType.DatabarStackedOmniDirectional);
        foreach (BarCodeResult result in decoder.ReadBarCodes())
        {
            Console.WriteLine($"Decoded text: {result.CodeText}");
        }
```

Декодер должен вывести `(01)12345678901231`, подтверждая, что процесс **создания датабар-стекового штрихкода** сохранил данные.

## Распространённые подводные камни и как их избежать

| Проблема | Почему происходит | Решение |
|----------|-------------------|---------|
| Штрихкод выглядит размытым | X‑размер установлен слишком низко для разрешения вывода | Увеличьте `XDimension.Pixels` или используйте `Millimeters` для печати |
| Сканер сообщает «символ не найден» | Соотношение сторон выходит за поддерживаемый диапазон 10‑30 | Держите соотношение в диапазоне от 10 до 30; 15 и 30 — безопасные значения по умолчанию |
| PNG содержит водяной знак | Используется бесплатная оценочная лицензия Aspose.BarCode | Приобретите полную лицензию или используйте пробную версию только для тестирования |
| Декодирование не удаётся на втором изображении | Декодер был настроен на неправильный тип символьной системы | Используйте `DecodeType.DatabarStackedOmniDirectional` при чтении стековых штрихкодов |

## Следующие шаги

Теперь, когда вы умеете **создавать датабар-стековые штрихкоды**, вы можете захотеть:

* **Встраивать PNG‑файлы в PDF‑счета** с помощью PDF‑библиотеки, такой как **Aspose.PDF**.
* **Генерировать штрихкоды «на лету» в веб‑API** — возвращать байты PNG напрямую из контроллера ASP.NET Core.
* **Экспериментировать с другими вариантами DataBar** (например, `DatabarExpanded`, `DatabarLimited`), изменяя перечисление `EncodeTypes`.
* **Настраивать цвета**, задавая `generator.Parameters.Barcode.ForeColor` и `BackColor` для бренд‑специфичных дизайнов.

Каждая из этих тем опирается на те же базовые концепции, рассмотренные здесь: инициализацию `BarcodeGenerator`, настройку визуальных параметров и сохранение результата с помощью `BarCodeImageFormat`.

---

### Заключение

В этом руководстве показано, как **создавать датабар-стековые штрихкоды** в C# с помощью Aspose.BarCode. Вы научились задавать **X‑размер**, изменять **соотношение сторон штрихкода** и экспортировать результат в виде **PNG**‑файлов с помощью `BarcodeGenerator`. С помощью дополнительного шага декодирования вы также можете убедиться в точности закодированных данных GS1. Применяйте эти шаблоны в своих системах учёта, доставки или точек продаж и изучайте многочисленные возможности настройки, предоставляемые библиотекой. Приятного кодирования!

## Что изучить дальше?

Следующие руководства охватывают тесно связанные темы, опирающиеся на техники, продемонстрированные в этом руководстве. Каждый ресурс содержит полностью работающие примеры кода с пошаговыми объяснениями, помогающими освоить дополнительные возможности API и исследовать альтернативные подходы к реализации в ваших проектах.

- [Регулировка высоты одноразмерного Databar штрихкода](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-barcode-height-adjustment/)
- [Генерация изображения штрихкода – GS1 Coupon UPC-A Databar](/barcode/english/net/gs1-barcode-encoding/gs1-coupon-upc-a-databar-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}