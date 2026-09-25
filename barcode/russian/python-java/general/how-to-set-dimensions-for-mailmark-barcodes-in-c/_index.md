---
category: general
date: 2026-08-22
description: Узнайте, как задавать размеры штрихкодов Mailmark в C# и сохранять их
  в виде PNG‑изображений. Включает полный код, объяснения и советы.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to set dimensions
- Mailmark barcode C# example
- BarcodeGenerator dimensions
- set barcode size in C#
- save barcode as PNG
language: ru
lastmod: 2026-08-22
og_description: Как задать размеры штрихкодов Mailmark в C# и экспортировать их в
  PNG‑файлы. Следуйте полному примеру и избегайте распространённых ошибок.
og_image_alt: Screenshot of two generated Mailmark barcode PNG files showing different
  dimensions
og_title: Как задать размеры штрих‑кодов Mailmark в C# – пошаговое руководство
schemas:
- author: Aspose
  dateModified: '2026-08-22'
  description: Learn how to set dimensions for Mailmark barcodes in C# and save them
    as PNG images. Includes full code, explanations, and tips.
  headline: How to set dimensions for Mailmark barcodes in C#
  type: TechArticle
tags:
- C#
- barcode
- Mailmark
- image generation
title: Как задать размеры штрихкодов Mailmark в C#
url: /ru/python-java/general/how-to-set-dimensions-for-mailmark-barcodes-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Как задать размеры штрихкодов Mailmark в C#

Если вам нужно **задать размеры** штрихкода Mailmark в C#, это руководство покажет точные шаги. Вы увидите, как настроить X‑dimension и высоту полос, а затем сохранить штрихкод как PNG‑изображение без дополнительного инструментария.

Создание почтовых штрихкодов — рутинная задача при разработке программного обеспечения для почтовых этикеток, но размер по умолчанию часто не соответствует требованиям принтера или макета. К концу этого руководства вы сможете точно управлять размером штрихкода и создавать два действительных типа Mailmark (C‑type и L‑type), готовых к печати.

**Что вы узнаете**

* Как задать X‑dimension (ширина модуля) и высоту полос для `BarcodeGenerator`.
* Как сохранить сгенерированный штрихкод в файл PNG с помощью `BarCodeImageFormat`.
* Распространённые подводные камни, такие как неверные пути к папкам или неподдерживаемые значения размеров.
* Советы по повторному использованию одной и той же конфигурации для нескольких штрихкодов.

## Требования

* .NET 6.0 или новее (код также работает с .NET Framework 4.6+).
* Пакет NuGet **Aspose.BarCode for .NET** (или любая совместимая библиотека, предоставляющая `BarcodeGenerator`, `EncodeTypes` и `BarCodeImageFormat`).
* Базовое знакомство с синтаксисом C# и вводом‑выводом файлов.

> **Pro tip:** Установите пакет с помощью команды CLI  
> `dotnet add package Aspose.BarCode` чтобы ваш проект оставался аккуратным.

## Шаг 1: Определите папку вывода

Прежде чем создавать любой штрихкод, вам нужно решить, куда будут записываться PNG‑файлы. Использование абсолютного пути избавляет от неожиданностей на разных машинах.

```csharp
// Step 1: Define the folder where the barcode images will be saved
string outputFolder = @"C:\Temp\Barcodes\";

// Ensure the directory exists; create it if necessary
if (!Directory.Exists(outputFolder))
{
    Directory.CreateDirectory(outputFolder);
}
```

*Почему это важно*: Если папка не существует, `Save` бросает `IOException`. Вызов `Directory.CreateDirectory` идемпотентен — он ничего не делает, если папка уже существует.

## Шаг 2: Создайте штрихкод Mailmark C‑type и **задать размеры**

Mailmark C‑type кодирует 20‑символьную буквенно-цифровую строку. После инициализации генератора вы можете **задать размеры** через объект `Parameters.Barcode`.

```csharp
// Step 2: Create a Mailmark C‑type barcode, configure its size, and save it as PNG
BarcodeGenerator mailmarkC = new BarcodeGenerator(EncodeTypes.Mailmark, "21B2254800659JW5O9QA6Y");

// Set the width of a single module (X‑dimension) to 4 pixels
mailmarkC.Parameters.Barcode.XDimension.Pixels = 4;

// Set the overall bar height to 50 pixels
mailmarkC.Parameters.Barcode.BarHeight.Pixels = 50;

// Save the image; the second argument specifies PNG format
mailmarkC.Save($"{outputFolder}PostalMailmarkCType.png", BarCodeImageFormat.Png);
```

### Почему выбраны эти значения?

* **X‑dimension** управляет шириной самой маленькой полосы («модуля»). Значение `4` пикселя дает штрихкод, который легко читается большинством лазерных принтеров, при этом размер файла остаётся умеренным.
* **BarHeight** определяет вертикальный размер полос. `50` пикселей — обычная высота для стандартных почтовых этикеток, но её можно увеличить для более крупных форматов.

> **Edge case:** Некоторые принтеры требуют минимальную высоту полосы 30 px. Установка высоты ниже возможностей принтера может привести к нечитаемым штрихкодам.

## Шаг 3: Создайте штрихкод Mailmark L‑type и **задать размеры**

L‑type использует более длинную строку данных (до 30 символов). Применяется тот же подход к задаванию размеров.

```csharp
// Step 3: Create a Mailmark L‑type barcode, configure its size, and save it as PNG
BarcodeGenerator mailmarkL = new BarcodeGenerator(EncodeTypes.Mailmark, "41038422416563762EF61AH8T");

// Reuse the same dimension settings for consistency
mailmarkL.Parameters.Barcode.XDimension.Pixels = 4;
mailmarkL.Parameters.Barcode.BarHeight.Pixels = 50;

// Save the L‑type barcode image
mailmarkL.Save($"{outputFolder}PostalMailmarkLType.png", BarCodeImageFormat.Png);
```

### Повторное использование конфигурации

Если вы генерируете много штрихкодов с одинаковыми размерами, рассмотрите возможность вынесения конфигурации в вспомогательный метод:

```csharp
void ApplyStandardDimensions(BarcodeGenerator generator)
{
    generator.Parameters.Barcode.XDimension.Pixels = 4;
    generator.Parameters.Barcode.BarHeight.Pixels = 50;
}
```

Вызов `ApplyStandardDimensions(mailmarkC)` и `ApplyStandardDimensions(mailmarkL)` уменьшает дублирование и делает будущие изменения (например, переход на модули по 5 пикселей) однострочным правкой.

## Шаг 4: Проверьте сгенерированные PNG‑файлы

После запуска программы откройте два PNG‑файла в любом просмотрщике изображений. Вы должны увидеть два разных штрихкода Mailmark, каждый с 4 px на модуль и высотой 50 px.

*Ожидаемый результат*

| Имя файла                     | Примерные размеры (px) |
|-------------------------------|--------------------------|
| `PostalMailmarkCType.png`     | 4 px × module × N modules |
| `PostalMailmarkLType.png`     | 4 px × module × N modules |

Точная ширина зависит от длины закодированных данных, но высота будет постоянно **50 px**, потому что мы задали `BarHeight.Pixels`.

## Распространённые подводные камни и как их избежать

| Issue                                 | Symptom                                      | Fix |
|---------------------------------------|----------------------------------------------|-----|
| Неверный путь к папке                 | `IOException: Could not find a part of the path` | Используйте `Path.Combine` с `Environment.SpecialFolder` или проверьте строку пути. |
| X‑dimension установлен в 0 или отрицательное значение | Штрихкод выглядит как сплошной блок            | Убедитесь, что `XDimension.Pixels` является положительным целым числом (минимум 1). |
| Неподдерживаемый `EncodeTypes.Mailmark` | `ArgumentException` при построении генератора | Убедитесь, что у вас установлена последняя версия библиотеки Aspose.BarCode, включающая поддержку Mailmark. |
| Сохранение в неправильном формате изображения | Повреждённый PNG‑файл                           | Используйте `BarCodeImageFormat.Png` (или `Jpeg`, если нужен другой формат). |

## Расширение примера

* **Разные размеры** – Измените `XDimension.Pixels` на 3 для более компактного штрихкода или увеличьте `BarHeight.Pixels` до 70 для больших этикеток.
* **Пакетная генерация** – Пройдитесь по коллекции строк данных, применяя те же настройки размеров на каждой итерации.
* **Другие форматы изображений** – Замените `BarCodeImageFormat.Png` на `BarCodeImageFormat.Jpeg` или `BarCodeImageFormat.Bmp`, если ваш рабочий процесс требует этого.

## Заключение

Теперь вы знаете **как задать размеры** штрихкодов Mailmark в C# и экспортировать их как PNG‑файлы. Настраивая `XDimension.Pixels` и `BarHeight.Pixels`, вы контролируете визуальный размер как C‑type, так и L‑type штрихкодов, гарантируя соответствие спецификациям принтера и ограничениям макета.  

Отсюда вы можете экспериментировать с различными значениями размеров, интегрировать код в более крупную систему почтовых этикеток или генерировать партии штрихкодов для массовой рассылки.

---

*Следующие шаги*: изучите **BarcodeGenerator dimensions** для QR‑кодов или прочитайте документацию Aspose.BarCode о **установке DPI** для печати высокого разрешения. Если нужно встроить штрихкод в PDF, комбинируйте этот подход с библиотекой **Aspose.PDF** для полного сквозного решения.

## Что стоит изучить дальше?

Следующие руководства охватывают тесно связанные темы, которые развивают техники, продемонстрированные в этом руководстве. Каждый ресурс включает полностью работающие примеры кода с пошаговыми объяснениями, чтобы помочь вам освоить дополнительные возможности API и исследовать альтернативные подходы к реализации в ваших проектах.

- [Как установить границу для настройки штрихкода ITF-14](/barcode/english/net/itf-14-barcode-customization/)
- [Как настроить штрихкоды Patch Code с помощью Aspose.BarCode для .NET](/barcode/english/net/patch-code-configuration/)
- [Как генерировать штрихкоды DataMatrix с использованием Aspose.BarCode для .NET – пошаговое руководство](/barcode/english/net/datamatrix-barcode-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}