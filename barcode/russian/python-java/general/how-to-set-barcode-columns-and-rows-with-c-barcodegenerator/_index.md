---
category: general
date: 2026-09-16
description: Узнайте, как задать столбцы штрих‑кода в C# с помощью BarcodeGenerator
  и также установить строки штрих‑кода для штрих‑кодов DataBar Expanded Stacked.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- set barcode columns
- set barcode rows
- DataBar Expanded Stacked
- BarcodeGenerator C#
- barcode image format
- configure barcode dimensions
language: ru
lastmod: 2026-09-16
og_description: Быстро задайте столбцы штрихкода в C#. Это руководство покажет, как
  настроить столбцы, строки и формат изображения с помощью BarcodeGenerator.
og_image_alt: DataBar Expanded Stacked barcode showing custom columns and rows
og_title: Установите столбцы и строки штрих‑кода в C# — полное руководство по BarcodeGenerator
schemas:
- author: Aspose
  dateModified: '2026-09-16'
  description: Learn how to set barcode columns in C# using BarcodeGenerator and also
    set barcode rows for DataBar Expanded Stacked barcodes.
  headline: How to set barcode columns and rows with C# BarcodeGenerator
  type: TechArticle
tags:
- barcode
- C#
- Aspose.BarCode
title: Как задать столбцы и строки штрихкода с помощью C# BarcodeGenerator
url: /ru/python-java/general/how-to-set-barcode-columns-and-rows-with-c-barcodegenerator/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Как установить количество столбцов и строк штрих‑кода с помощью C# BarcodeGenerator

Если вам нужно задать количество столбцов штрих‑кода в приложении на C#, этот учебник покажет точные шаги, необходимые для этого. Вы увидите, как настроить как столбцы, так и строки для штрих‑кода **DataBar Expanded Stacked**, а затем сохранить результат в виде PNG‑изображения.

Программная генерация штрих‑кодов избавляет от ручного проектирования и гарантирует единообразие в отчетах, счетах и этикетках продукции. Пример ниже охватывает весь рабочий процесс: от установки библиотеки до создания двух изображений — одного с пользовательским количеством столбцов и другого с пользовательским количеством строк.

## Требования

Прежде чем начать, убедитесь, что у вас есть:

* .NET 6.0 или более поздняя версия.
* Ссылка на пакет **Aspose.BarCode for .NET** в NuGet. Установите его с помощью:

```bash
dotnet add package Aspose.BarCode
```

* Права записи в папку, куда будут сохраняться сгенерированные PNG‑файлы.

Эти требования гарантируют, что код будет компилироваться и работать без дополнительной настройки.

## Как задать количество столбцов штрих‑кода в C#

Первый основной шаг — создать экземпляр `BarcodeGenerator` для символьного набора **DataBar Expanded Stacked** и задать желаемое количество столбцов.

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // 1️⃣ Initialize a DataBar Expanded Stacked barcode generator with the target text.
        var barcodeGenerator = new BarcodeGenerator(
            EncodeTypes.DatabarExpandedStacked,
            "Databar Expanded Stacked long");

        // 2️⃣ Configure the number of columns. The DataBar object exposes a Columns property.
        barcodeGenerator.Parameters.Barcode.DataBar.Columns = 4;

        // 3️⃣ Save the image using the PNG format.
        barcodeGenerator.Save(@"C:\Barcodes\DatabarCols4.png", BarCodeImageFormat.Png);
    }
}
```

**Почему это работает:**  
`EncodeTypes.DatabarExpandedStacked` указывает библиотеке, какой символьный набор отрисовывать. Установка `Parameters.Barcode.DataBar.Columns` меняет внутреннюю раскладку модулей, что напрямую влияет на визуальную ширину штрих‑кода. Метод `Save` записывает изображение на диск в указанном `BarCodeImageFormat`.

### Ожидаемый результат
Откройте `C:\Barcodes\DatabarCols4.png` в любой программе просмотра изображений. Вы должны увидеть штрих‑код DataBar Expanded Stacked, который шире стандартного, поскольку использует четыре столбца.

## Как задать количество строк штрих‑кода в C#

После того как вы сохранили изображение с настройкой столбцов, вы можете захотеть штрих‑код, высота которого меняется за счёт строк. Процесс аналогичен настройке столбцов, но используется свойство `Rows`.

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // 4️⃣ Re‑initialize the generator for a fresh configuration.
        var barcodeGenerator = new BarcodeGenerator(
            EncodeTypes.DatabarExpandedStacked,
            "Databar Expanded Stacked long");

        // 5️⃣ Set the number of rows. This property controls the vertical module count.
        barcodeGenerator.Parameters.Barcode.DataBar.Rows = 3;

        // 6️⃣ Save the barcode image with the row configuration.
        barcodeGenerator.Save(@"C:\Barcodes\DatabarRows3.png", BarCodeImageFormat.Png);
    }
}
```

**Почему это работает:**  
Повторная инициализация генератора гарантирует, что предыдущее значение столбцов не будет влиять на настройку строк. Изменение `Parameters.Barcode.DataBar.Rows` меняет высоту штрих‑кода, создавая более высокое изображение, когда количество строк превышает значение по умолчанию.

### Ожидаемый результат
Откройте `C:\Barcodes\DatabarRows3.png`. Штрих‑код будет выше, отражая конфигурацию из трёх строк.

## Полный пример от начала до конца

Ниже представлен один файл программы, который создаёт оба изображения за один запуск. Хранение кода в одном файле демонстрирует, как переключаться между настройками столбцов и строк без перезапуска приложения.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Common text for both barcodes.
        const string barcodeText = "Databar Expanded Stacked long";

        // ---------- Column configuration ----------
        var colGenerator = new BarcodeGenerator(EncodeTypes.DatabarExpandedStacked, barcodeText);
        colGenerator.Parameters.Barcode.DataBar.Columns = 4;
        colGenerator.Save(@"C:\Barcodes\DatabarCols4.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved barcode with 4 columns to DatabarCols4.png");

        // ---------- Row configuration ----------
        var rowGenerator = new BarcodeGenerator(EncodeTypes.DatabarExpandedStacked, barcodeText);
        rowGenerator.Parameters.Barcode.DataBar.Rows = 3;
        rowGenerator.Save(@"C:\Barcodes\DatabarRows3.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved barcode with 3 rows to DatabarRows3.png");
    }
}
```

Запуск программы создаёт два PNG‑файла:

* **DatabarCols4.png** – штрих‑код с четырьмя столбцами.  
* **DatabarRows3.png** – штрих‑код с тремя строками.

Оба файла используют **формат изображения штрих‑кода** PNG, который сохраняет чёткие границы и поддерживает без потерь сжатие — идеально подходит для печати и цифрового отображения.

## Часто задаваемые вопросы и советы

| Вопрос | Ответ |
|----------|--------|
| *Можно ли использовать JPEG вместо PNG?* | Да. Замените `BarCodeImageFormat.Png` на `BarCodeImageFormat.Jpeg`. JPEG имеет меньший размер, но вводит артефакты сжатия, что может повлиять на надёжность сканирования. |
| *Каково максимальное количество столбцов или строк?* | Библиотека проверяет значения в соответствии со спецификацией DataBar. Значения, выходящие за допустимый диапазон, вызывают `ArgumentException`. Смотрите документацию Aspose.BarCode для точных ограничений. |
| *Нужно ли освобождать `BarcodeGenerator`?* | Класс реализует `IDisposable`. Оборачивайте генератор в блок `using`, если создаёте много экземпляров в цикле, чтобы своевременно освобождать неуправляемые ресурсы. |
| *Как изменить размер штрих‑кода без изменения столбцов/строк?* | Используйте `barcodeGenerator.Parameters.Image.Width` и `Height` для масштабирования выходного изображения, оставляя раскладку модулей без изменений. |

**Совет:** При генерации штрих‑кодов для печати высокого разрешения увеличивайте размеры выходного изображения (`Width`/`Height`), а не количество столбцов или строк. Такой подход сохраняет стандартный размер модуля, определённый символьным набором, и даёт более чёткое изображение.

## Заключение

Теперь вы знаете, как задавать количество столбцов и строк штрих‑кода в C# с помощью класса **BarcodeGenerator**. Руководство охватывало инициализацию генератора, настройку количества столбцов и строк, сохранение штрих‑кода в формате PNG и работу с типичными вариациями, такими как изменение формата изображения и освобождение ресурсов.

Далее изучайте связанные темы, такие как **кастомизация цветов штрих‑кода**, **добавление читаемого человеком текста** и **встраивание штрих‑кодов в PDF‑документы**. Все эти расширения опираются на тот же шаблон конфигурации, продемонстрированный здесь, позволяя создавать полнофункциональные решения штрих‑кодов для любого .NET‑приложения.

## Что изучать дальше?

Следующие учебники охватывают тесно связанные темы, построенные на техниках, продемонстрированных в этом руководстве. Каждый ресурс включает полностью работающие примеры кода с пошаговыми объяснениями, чтобы помочь вам освоить дополнительные возможности API и исследовать альтернативные подходы в собственных проектах.

- [Barcode Generator Example in C# – Set Columns, Rows & Export Image](/barcode/english/python-java/general/barcode-generator-example-in-c-set-columns-rows-export-image/)
- [databar expanded stacked barcode guide – how to generate and size it in C#](/barcode/english/python-java/general/databar-expanded-stacked-barcode-guide-how-to-generate-and-s/)
- [Barcode generator example in C# – set width and height](/barcode/english/python-java/general/barcode-generator-example-in-c-set-width-and-height/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}