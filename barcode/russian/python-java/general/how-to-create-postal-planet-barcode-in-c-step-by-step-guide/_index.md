---
category: general
date: 2026-09-23
description: Узнайте, как создавать изображения штрих‑кодов Postal Planet в C# с заполненными
  и пустыми полосами. Следуйте этому полному примеру, используя BarcodeGenerator и
  настройки X‑размера.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create postal planet barcode
- Planet barcode generator C#
- barcode X‑dimension pixels
- filled bars vs empty bars
- BarCodeImageFormat PNG
language: ru
lastmod: 2026-09-23
og_description: Создайте почтовый планетарный штрих‑код в C# с помощью этого подробного
  руководства. Генерируйте как заполненные, так и пустые стили штрихов, используя
  BarcodeGenerator и настройки X‑размера.
og_image_alt: Screenshot showing a created postal planet barcode with filled bars
og_title: Создание почтового планетарного штрихкода на C# – полное руководство по
  программированию
schemas:
- author: Aspose
  dateModified: '2026-09-23'
  description: Learn how to create postal planet barcode images in C# with filled
    and empty bars. Follow this complete example using BarcodeGenerator and X‑dimension
    settings.
  headline: How to create postal planet barcode in C# – step‑by‑step guide
  type: TechArticle
tags:
- barcode
- C#
- Aspose.Barcode
title: Как создать штрих‑код Postal Planet в C# – пошаговое руководство
url: /ru/python-java/general/how-to-create-postal-planet-barcode-in-c-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Как создать штрих‑код Postal Planet в C# – пошаговое руководство

Если вам нужно **создать штрих‑код Postal Planet** в виде изображений в приложении .NET, этот учебник покажет готовое решение. Независимо от того, создаёте ли вы систему печати почтовых этикеток или инструмент проверки адресов, вы увидите, как генерировать варианты с заполненными и пустыми полосами с помощью класса Aspose.Barcode `BarcodeGenerator`.

Вы узнаете, как настроить **генератор штрих‑кода Planet**, задать **X‑размер** (ширину каждой полосы) в пикселях и сохранить результат в файл PNG. Руководство также объясняет, почему вы можете выбрать заполненные полосы вместо пустых и как переключаться между ними одной строкой кода.

## Что вам понадобится

* .NET 6.0 SDK или новее (код также работает с .NET Core и .NET Framework)  
* Visual Studio 2022 (или любой IDE, поддерживающий C#)  
* NuGet‑пакет Aspose.Barcode for .NET (`Aspose.Barcode`), установленный в вашем проекте  
* Права записи в папку, куда будут сохраняться сгенерированные PNG‑файлы  

Эти предварительные условия гарантируют, что пример скомпилируется без дополнительной настройки.

## Шаг 1: Настройте папку вывода

Первый шаг — определить, куда будут записываться изображения штрих‑кода. Подойдёт как абсолютный, так и относительный путь; просто убедитесь, что папка существует, либо создайте её программно.

```csharp
// Step 1: Define the output folder
string outputFolder = "C:/Barcodes/";

// Ensure the folder exists
if (!Directory.Exists(outputFolder))
{
    Directory.CreateDirectory(outputFolder);
}
```

*Почему это важно*: Если папка не существует, `BarcodeGenerator.Save` бросает исключение. Создайте папку заранее, чтобы код был надёжным в средах развертывания.

## Шаг 2: Инициализируйте генератор штрих‑кода Planet

**Генератор штрих‑кода Planet** (EncodeTypes.Planet) — это специфическая символьность, используемая многими почтовыми службами. Инициализируйте его данными, которые хотите закодировать, в данном случае числовой строкой `"123456"`.

```csharp
// Step 2: Create a Planet barcode generator with the data "123456"
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(EncodeTypes.Planet, "123456");
```

*Почему это важно*: `EncodeTypes.Planet` сообщает Aspose.Barcode использовать символьность Planet, которая имеет фиксированный шаблон полос и пробелов, подходящий для почтовой маршрутизации.

## Шаг 3: Настройте X‑размер штрих‑кода

**X‑размер штрих‑кода** контролирует ширину каждой отдельной полосы. Установка значения в 4 пикселя даёт чёткий, читаемый штрих‑код, который хорошо печатается на стандартных принтерах этикеток.

```csharp
// Step 3: Set the X‑dimension (width of each bar) to 4 pixels
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 4;
```

*Почему это важно*: Слишком маленький X‑размер может сделать штрих‑код нечитаемым, а слишком большой — тратить место на этикетке. Четыре пикселя — распространённый оптимальный параметр для принтеров с разрешением 300 dpi.

## Шаг 4: Сгенерируйте штрих‑код Planet с заполненными полосами

Режим рендеринга по умолчанию использует **заполненные полосы** (чёрные полосы на белом фоне). Сохраните изображение в PNG, чтобы сохранить без потерь качество.

```csharp
// Step 4: Save the barcode using the default setting (filled bars)
barcodeGenerator.Save($"{outputFolder}PostalPlanetFilledBars.png", BarCodeImageFormat.Png);
```

**Ожидаемый результат**: `PostalPlanetFilledBars.png` показывает классический штрих‑код Planet, где каждая полоса заполнена.  

![Пример созданного штрих‑кода Postal Planet с заполненными полосами](https://example.com/filled-bars.png "Пример созданного штрих‑кода Postal Planet с заполненными полосами")

*Почему это важно*: Заполненные полосы являются отраслевым стандартом для большинства почтовых сканеров. Использование PNG гарантирует, что изображение останется чётким при печати.

## Шаг 5: Создайте второй генератор для пустых полос

Чтобы проиллюстрировать сравнение **заполненных полос vs пустых полос**, мы создаём ещё один экземпляр `BarcodeGenerator` с теми же данными. Повторное использование одинаковых данных гарантирует визуальное сопоставление обеих картинок.

```csharp
// Step 5: Create another Planet barcode generator for the same data
BarcodeGenerator emptyBarGenerator = new BarcodeGenerator(EncodeTypes.Planet, "123456");
```

## Шаг 6: Примените тот же X‑размер и переключитесь на пустые полосы

Свойство `FilledBars` переключает режим рендеринга. Установка его в `false` создаёт **пустые полосы** (белые полосы на чёрном фоне). X‑размер остаётся тем же, чтобы размер был согласован.

```csharp
// Step 6: Apply the same X‑dimension and configure the barcode to use empty bars
emptyBarGenerator.Parameters.Barcode.XDimension.Pixels = 4;
emptyBarGenerator.Parameters.Barcode.FilledBars = false;
```

*Почему это важно*: Некоторые почтовые службы или пользовательские процессы требуют обратной цветовой схемы для лучшего контраста на тёмных носителях. Флаг `FilledBars` даёт эту гибкость одной строкой кода.

## Шаг 7: Сгенерируйте штрих‑код Planet с пустыми полосами

Наконец, сохраните версию с пустыми полосами в ту же папку вывода.

```csharp
// Step 7: Save the barcode with empty bars
emptyBarGenerator.Save($"{outputFolder}PostalPlanetEmptyBars.png", BarCodeImageFormat.Png);
```

**Ожидаемый результат**: `PostalPlanetEmptyBars.png` отображает тот же шаблон Planet, но полосы пустые (белые), а фон чёрный.

![Пример созданного штрих‑кода Postal Planet с пустыми полосами](https://example.com/empty-bars.png "Пример созданного штрих‑кода Postal Planet с пустыми полосами")

## Проверьте результаты

Откройте оба PNG‑файла в любом просмотрщике изображений. Вы должны увидеть два визуально идентичных штрих‑кода, различающихся только инверсией цветов. Чтобы убедиться, что штрих‑коды сканируются, можно воспользоваться приложением для чтения штрих‑кодов на смартфоне, поддерживающим символьность Planet.

Если изображения выглядят искажёнными, ещё раз проверьте значение **X‑размера** и убедитесь, что путь к папке вывода не содержит недопустимых символов.

## Распространённые ошибки и рекомендации по лучшим практикам

| Проблема | Почему происходит | Как исправить |
|----------|-------------------|---------------|
| **Папка не найдена** | `Save` бросает `DirectoryNotFoundException`, когда путь отсутствует. | Создайте папку с помощью `Directory.CreateDirectory` перед сохранением. |
| **Неправильный размер штрих‑кода** | Использование нецелого X‑размера или значения менее 2 пикселей приводит к нечитаемым кодам. | Сохраняйте X‑размер ≥ 2 пикселей; 4 пикселя подходят для большинства принтеров. |
| **Инверсия цвета не применена** | Забыли установить `FilledBars = false`. | Явно установите `FilledBars` после настройки X‑размера. |
| **Неправильный формат изображения** | Сохранение в JPEG может добавить артефакты сжатия. | Используйте `BarCodeImageFormat.Png` для без потерь вывода. |

## Расширение примера

* **Измените данные** – замените `"123456"` любой числовой строкой до 12 символов (Planet поддерживает до 12 цифр).  
* **Настройте размер изображения** – измените `XDimension.Pixels` или задайте `Height`/`Width` через `barcodeGenerator.Parameters.Image`.  
* **Добавьте рамку** – используйте `barcodeGenerator.Parameters.Barcode.BorderWidth` для рисования тонкой обводки вокруг штрих‑кода.  
* **Экспорт в другие форматы** – замените `BarCodeImageFormat.Png` на `Jpeg`, `Bmp` или `Tiff`, если ваш процесс требует этого.  

## Заключение

Теперь вы знаете, как **создать штрих‑код Postal Planet** в C# с помощью Aspose.Barcode `BarcodeGenerator`. В руководстве рассмотрены инициализация **генератора штрих‑кода Planet**, настройка **X‑размера штрих‑кода** и создание PNG‑файлов как с **заполненными**, так и с **пустыми** полосами. Обладая этими базовыми знаниями, вы сможете интегрировать генерацию почтовых штрих‑кодов в любое .NET‑приложение, настраивать внешний вид и обеспечивать надёжное сканирование в реальных почтовых системах.

Готовы исследовать дальше? Попробуйте генерировать другие почтовые символьности (например, **Postnet** или **Intelligent Mail**) или объединить штрих‑код с PDF‑этикеткой с помощью Aspose.PDF. Приятного кодинга!

## Что стоит изучить дальше?

Следующие учебники охватывают тесно связанные темы, построенные на техниках, продемонстрированных в этом руководстве. Каждый ресурс включает полностью работающие примеры кода с пошаговыми объяснениями, помогающими освоить дополнительные возможности API и исследовать альтернативные подходы к реализации в ваших проектах.

- [Создать изображение штрих‑кода Planet в C# – Как генерировать почтовый штрих‑код](/barcode/english/python-java/general/create-planet-barcode-image-in-c-how-to-generate-postal-barc/)
- [Генератор штрих‑кодов C# – пример создания штрих‑кода Planet и RM4SCC](/barcode/english/python-java/general/barcode-generator-c-create-planet-barcode-and-rm4scc-example/)
- [Создать штрих‑код Planet в C# – Полное пошаговое руководство](/barcode/english/python-java/general/create-planet-barcode-in-c-full-step-by-step-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}