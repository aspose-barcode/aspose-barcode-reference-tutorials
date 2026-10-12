---
category: general
date: 2026-09-29
description: Узнайте, как создать штрих‑код Databar Expanded Stacked и сгенерировать
  его изображение в C#. Это пошаговое руководство показывает, как задать количество
  строк и столбцов с помощью BarcodeGenerator.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- databar expanded stacked
- how to create barcode
- how to set rows
- barcode generator c#
- generate barcode image
language: ru
lastmod: 2026-09-29
og_description: Генерация штрихкода Databar Expanded Stacked на C# объяснена. Следуйте
  руководству, чтобы создавать изображения штрихкодов, задавать ряды и сохранять PNG‑файлы
  с помощью BarcodeGenerator.
og_image_alt: Screenshot of a Databar Expanded Stacked barcode saved as a PNG file
og_title: Генерация штрихкода Databar Expanded Stacked на C# – полное руководство
schemas:
- author: Aspose
  dateModified: '2026-09-29'
  description: Learn how to create a Databar Expanded Stacked barcode and generate
    barcode image in C#. This step‑by‑step guide shows how to set rows and columns
    using BarcodeGenerator.
  headline: Databar Expanded Stacked barcode generation in C#
  type: TechArticle
tags:
- barcode
- C#
- Aspose
title: Генерация штрихкода Databar Expanded Stacked на C#
url: /ru/python-java/general/databar-expanded-stacked-barcode-generation-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Генерация штрих‑кода Databar Expanded Stacked на C#

Если вам нужно сгенерировать штрих‑код **Databar Expanded Stacked** на C#, это руководство покажет, как именно **создавать изображения штрих‑кодов** с пользовательскими строками и столбцами. Вы увидите, **как задавать строки**, как задавать столбцы и как **генерировать файлы изображений штрих‑кода** с помощью класса Aspose.BarCode `BarcodeGenerator`.

В этом учебнике вы:

* Установите необходимый пакет NuGet.
* Инициализируете `BarcodeGenerator` для символьной системы Databar Expanded Stacked.
* Настроите количество столбцов и строк.
* Сохраните полученные PNG‑файлы.
* Поймёте распространённые подводные камни, такие как отсутствие лицензии или неверные пути к изображениям.

Единственными предварительными требованиями являются современный .NET SDK (≥ .NET 6) и IDE, например Visual Studio 2022. Внешние сервисы не требуются.

## Установка и настройка библиотеки BarcodeGenerator для C#

Перед тем как писать код, добавьте пакет Aspose.BarCode в ваш проект:

```bash
dotnet add package Aspose.BarCode
```

Если вы используете Visual Studio, вы также можете установить его через **NuGet Package Manager** (поиск по *Aspose.BarCode*). После восстановления пакета можно приступать к программированию.

> **Pro tip:** Бесплатная оценочная версия добавляет небольшую водяную метку к сгенерированным штрих‑кодам. Для использования в продакшене получите файл лицензии и вызовите `License license = new License(); license.SetLicense("Aspose.BarCode.lic");` перед созданием любых объектов штрих‑кода.

## Генерация изображения штрих‑кода Databar Expanded Stacked

Создайте новое консольное приложение (или интегрируйте код в любой проект C#) и добавьте следующие директивы `using`:

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;
```

Теперь напишите полную программу. Код следует точно тем же шагам, что и в оригинальном примере, и содержит поясняющие комментарии.

```csharp
// Program.cs
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        // --------------------------------------------------------------------
        // Step 1: Create a barcode generator for Databar Expanded Stacked
        // --------------------------------------------------------------------
        // The EncodeTypes enum tells the generator which symbology to use.
        var databarGenerator = new BarcodeGenerator(
            EncodeTypes.DatabarExpandedStacked,
            "Databar Expanded Stacked long");

        // --------------------------------------------------------------------
        // Step 2: Set the number of columns (the default is 1)
        // --------------------------------------------------------------------
        // Columns control the horizontal density of the barcode.
        databarGenerator.Parameters.Barcode.DataBar.Columns = 4;

        // --------------------------------------------------------------------
        // Step 3: Save the barcode image that uses 4 columns
        // --------------------------------------------------------------------
        // BarCodeImageFormat.Png creates a lossless PNG file.
        databarGenerator.Save("DatabarCols4.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved barcode with 4 columns to DatabarCols4.png");

        // --------------------------------------------------------------------
        // Step 4: Re‑initialize the generator for the same barcode type
        // --------------------------------------------------------------------
        // Re‑creating the object ensures that row settings start from defaults.
        databarGenerator = new BarcodeGenerator(
            EncodeTypes.DatabarExpandedStacked,
            "Databar Expanded Stacked long");

        // --------------------------------------------------------------------
        // Step 5: Set the number of rows (the default is 1)
        // --------------------------------------------------------------------
        // Rows affect the vertical stacking of the barcode modules.
        databarGenerator.Parameters.Barcode.DataBar.Rows = 3;

        // --------------------------------------------------------------------
        // Step 6: Save the barcode image that uses 3 rows
        // --------------------------------------------------------------------
        databarGenerator.Save("DatabarRows3.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved barcode with 3 rows to DatabarRows3.png");
    }
}
```

### Почему каждый шаг важен

* **Step 1** создаёт `BarcodeGenerator`, привязанный к символьной системе *Databar Expanded Stacked*, что необходимо для сканирования в розничных системах, совместимых с GS1.
* **Step 2** демонстрирует **как задавать строки** косвенно, сначала изменяя столбцы — это показывает, что настройки столбцов и строк независимы.
* **Step 3** сохраняет изображение, позволяя проверить визуальное влияние количества столбцов.
* **Step 4** переинициализирует генератор, чтобы конфигурация строк не наследовала ранее установленное значение столбцов, что часто является источником путаницы.
* **Step 5** явно показывает **как задавать строки**, что является основной темой данного руководства.
* **Step 6** сохраняет второе изображение, предоставляя сравнение плотности, основанной на столбцах и строках, бок‑о‑бок.

Запуск программы создает два PNG‑файла в каталоге вывода:

```
DatabarCols4.png   // 4 columns, default row count (1)
DatabarRows3.png   // 3 rows, default column count (1)
```

Откройте любой из файлов в просмотрщике изображений, чтобы убедиться, что штрих‑код отображается корректно.

## Распространённые варианты и граничные случаи

| Сценарий | Что изменить | Причина |
|----------|----------------|--------|
| **Different data payload** | Замените второй аргумент `BarcodeGenerator` на свою строку (например, `"123456789012"`). | Штрих‑код кодирует переданный текст; убедитесь, что он соответствует правилам GS1 для Databar. |
| **Other image formats** | Используйте `BarCodeImageFormat.Jpeg` или `BarCodeImageFormat.Bmp`. | Выберите формат, подходящий вашему последующему конвейеру обработки. |
| **Higher resolution** | Вызовите `databarGenerator.Save("file.png", BarCodeImageFormat.Png, 300);`, где последний аргумент — DPI. | Улучшает читаемость при печати больших этикеток. |
| **License handling** | Добавьте фрагмент кода `License` перед созданием любого генератора. | Убирает водяную метку оценки и открывает полный функционал. |

## Советы для надёжной генерации штрих‑кодов

* **Validate the input string** — Databar Expanded Stacked ожидает числовые данные длиной до 70 символов. Передача нечисловых символов может вызвать исключение.
* **Check file paths** — Используйте `Path.Combine(Environment.CurrentDirectory, "output.png")`, чтобы избежать жёстко заданных каталогов, которые могут отсутствовать на целевой машине.
* **Dispose objects** — `BarcodeGenerator` реализует `IDisposable`. Оберните его в блок `using`, если генерируете множество штрих‑кодов в цикле, чтобы своевременно освобождать нативные ресурсы.

```csharp
using (var generator = new BarcodeGenerator(...))
{
    // configure and save
}
```

## Заключение

Теперь вы знаете **как создать штрих‑код Databar Expanded Stacked** и **как задавать строки** (и столбцы) с помощью **API генератора штрих‑кодов C#**, а также можете **генерировать файлы изображений штрих‑кода** в формате PNG. Следуя полному примеру выше, вы сможете интегрировать штрих‑коды Databar в системы учёта, кассовые приложения или любое .NET‑решение, требующее высокоплотных штрих‑кодов GS1.

**Следующие шаги**

* Поэкспериментируйте с другими символьными системами, такими как `EncodeTypes.DatabarExpanded` или `EncodeTypes.QR`.  
* Изучите класс `BarcodeReader`, чтобы проверить, что созданные изображения сканируются.  
* Скомбинируйте генерацию штрих‑кода с созданием PDF (например, используя `Aspose.PDF`) для получения печатных этикеток.

Удачной разработки!

## Что вам стоит изучить дальше?

Следующие учебники охватывают тесно связанные темы, построенные на техниках, продемонстрированных в этом руководстве. Каждый ресурс содержит полностью работающие примеры кода с пошаговыми объяснениями, помогающими освоить дополнительные возможности API и исследовать альтернативные подходы в ваших проектах.

- [How to set columns for a Databar Expanded Stacked barcode – complete C# guide](/barcode/english/python-java/general/how-to-set-columns-for-a-databar-expanded-stacked-barcode-co/)
- [How to change barcode size in C# with DataBar Stacked](/barcode/english/python-java/general/how-to-change-barcode-size-in-c-with-databar-stacked/)
- [Databar expanded stacked: generate barcode image in C#](/barcode/english/python-java/general/databar-expanded-stacked-generate-barcode-image-in-c/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}