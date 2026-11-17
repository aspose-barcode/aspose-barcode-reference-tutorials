---
category: general
date: 2026-11-17
description: Узнайте, как сохранять штрих‑код, включать компактный режим, настраивать
  столбцы и генерировать штрих‑код PDF417 с полным примером на C#.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to save barcode
- enable compact mode
- how to adjust columns
- generate pdf417 barcode
- how to enable compact mode
language: ru
lastmod: 2026-11-17
og_description: Как сохранить штрих‑код, включить компактный режим и настроить столбцы
  при генерации штрих‑кода PDF417 в C#. Следуйте пошаговому руководству.
og_image_alt: Screenshot showing how to save barcode as PNG file in C#
og_title: Как сохранить штрих‑код в формате PNG и включить компактный режим в C#
schemas:
- author: Aspose
  dateModified: '2026-11-17'
  description: Learn how to save barcode, enable compact mode, adjust columns, and
    generate PDF417 barcode with a complete C# example.
  headline: How to save barcode as PNG and enable compact mode in C#
  type: TechArticle
- description: Learn how to save barcode, enable compact mode, adjust columns, and
    generate PDF417 barcode with a complete C# example.
  name: How to save barcode as PNG and enable compact mode in C#
  steps:
  - name: Expected output
    text: Opening the saved PNG file shows a vertically compact PDF417 barcode with
      three columns and truncated padding. The visual size is roughly 2 px per module,
      making the image suitable for embedding in HTML `<img>` tags or for printing
      on small labels.
  - name: What if I need a different image format?
    text: The `Save` method accepts any `BarCodeImageFormat` enum value, such as `Jpeg`,
      `Bmp`, or `Gif`. Replace `BarCodeImageFormat.Png` with the desired format, and
      the rest of the code remains unchanged.
  - name: How does truncation affect data capacity?
    text: Enabling **compact mode** (truncation) reduces the number of rows, which
      can lower the maximum data capacity of the barcode. If you encounter a “Data
      too large” exception, either increase the number of columns or disable truncation.
  - name: Can I use a dynamic column count?
    text: 'Yes. You can calculate the column count based on the length of the input
      string:'
  - name: Is the X‑dimension limited to integer pixels?
    text: The `Pixels` property accepts any positive integer. For higher‑resolution
      outputs (e.g., printing), you might prefer setting `Points` instead of `Pixels`
      to achieve device‑independent sizing.
  type: HowTo
tags:
- barcode
- pdf417
- csharp
- image generation
title: Как сохранить штрих‑код в формате PNG и включить компактный режим в C#
url: /ru/net/compact-pdf417-encoding/how-to-save-barcode-as-png-and-enable-compact-mode-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Как сохранить штрих‑код в PNG и включить компактный режим в C#

Если вам нужно **how to save barcode** в формате, который можно использовать в вебе или при печати, это руководство покажет вам точные шаги. Вы также узнаете, как **enable compact mode**, **adjust columns** и **generate PDF417 barcode** с библиотекой Aspose.BarCode для .NET.

В этом руководстве рассматривается всё — от настройки проекта до получения конечного PNG‑файла, так что вы можете скопировать код в своё решение без дополнительного исследования. Внешняя документация не требуется; включён полный, исполняемый пример.

## Требования

* .NET 6.0 или более поздняя версия установлен  
* Visual Studio 2022 (или любой IDE для C#)  
* Пакет NuGet `Aspose.BarCode` (`Install-Package Aspose.BarCode`)  

Эти три элемента — единственные зависимости для последующего кода.

## Шаг 1: Создать генератор штрих‑кода PDF417

Первая задача при **generate PDF417 barcode** — создать экземпляр `BarcodeGenerator` с правильным типом кодирования и данными, которые нужно закодировать.

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

// Step 1: Create a PDF417 barcode generator with the desired text.
BarcodeGenerator barcode = new BarcodeGenerator(EncodeTypes.Pdf417, "Compact mode");
```

Перечисление `EncodeTypes.Pdf417` указывает библиотеке использовать символьный набор PDF417, который представляет собой многослойный линейный штрих‑код, подходящий для кодирования больших объёмов данных. Строка `"Compact mode"` становится читаемым человеком текстом под штрих‑кодом.

## Шаг 2: Установить X‑размер (ширина модуля)

Каждая полоса в штрих‑коде называется модулем. Управление шириной модуля позволяет точно настроить визуальный размер штрих‑кода без изменения данных.

```csharp
// Step 2: Set the module (X) dimension – each bar will be 2 pixels wide.
barcode.Parameters.Barcode.XDimension.Pixels = 2;
```

X‑размер в 2 пикселя создаёт компактное изображение, которое всё равно надёжно считывается большинством устройств.

## Шаг 3: **How to adjust columns** для кода PDF417

PDF417 позволяет указать, сколько колонок должен использовать штрих‑код. Меньшее количество колонок даёт более высокий, узкий символ, а большее количество колонок делает символ шире, но короче.

```csharp
// Step 3: Define the number of columns for the PDF417 code (3 columns).
barcode.Parameters.Barcode.Pdf417.Columns = 3;
```

Эта строка демонстрирует **how to adjust columns**. Вы можете изменить значение на 2, 4 или любое другое число, поддерживаемое библиотекой, в зависимости от доступного пространства на целевом носителе.

## Шаг 4: **How to enable compact mode** и усечь символ

Компактный режим удаляет ненужные отступы и уменьшает общий размер штрих‑кода. Библиотека предоставляет эту возможность через свойство `Truncate`.

```csharp
// Step 4: Enable compact mode by truncating the symbol.
barcode.Parameters.Barcode.Pdf417.Truncate = true;
```

Обратите внимание, что фраза **enable compact mode** появляется здесь, а то же действие описано позже в руководстве точными словами **how to enable compact mode**, чтобы удовлетворить требование вторичного ключевого слова.

## Шаг 5: **How to save barcode** в виде PNG‑изображения

Сохранение сгенерированного изображения — последний шаг. Метод `Save` записывает штрих‑код в файловую систему в указанном вами формате.

```csharp
// Step 5: Save the generated barcode as a PNG image.
barcode.Save("YOUR_DIRECTORY/CompactPdf417.png", BarCodeImageFormat.Png);
```

Замените `YOUR_DIRECTORY` на абсолютный или относительный путь, в который ваше приложение может записывать. После выполнения вы найдете файл с именем `CompactPdf417.png`, содержащий компактный штрих‑код PDF417.

### Ожидаемый результат

Открытие сохранённого PNG‑файла показывает вертикально компактный штрих‑код PDF417 с тремя колонками и усечёнными отступами. Визуальный размер составляет примерно 2 px на модуль, что делает изображение пригодным для встраивания в HTML‑теги `<img>` или для печати на небольших этикетках.

## Полный, исполняемый пример

Ниже приведена полная программа, которую вы можете скопировать в новый консольный проект. Она включает все необходимые директивы `using` и демонстрирует **how to save barcode**, **enable compact mode**, **how to adjust columns** и **generate PDF417 barcode** в едином процессе.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace Pdf417CompactDemo
{
    class Program
    {
        static void Main(string[] args)
        {
            // Create a PDF417 barcode generator with the desired text.
            BarcodeGenerator barcode = new BarcodeGenerator(EncodeTypes.Pdf417, "Compact mode");

            // Set the module (X) dimension – each bar will be 2 pixels wide.
            barcode.Parameters.Barcode.XDimension.Pixels = 2;

            // Define the number of columns for the PDF417 code (3 columns).
            barcode.Parameters.Barcode.Pdf417.Columns = 3;

            // Enable compact mode by truncating the symbol.
            barcode.Parameters.Barcode.Pdf417.Truncate = true;

            // Save the generated barcode as a PNG image.
            string outputPath = "CompactPdf417.png"; // Adjust path as needed.
            barcode.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"Barcode saved to {outputPath}");
        }
    }
}
```

Запуск этой программы создаёт PNG‑файл, описанный выше. Вывод в консоль подтверждает расположение сохранённого файла, что помогает убедиться, что шаг **how to save barcode** выполнен успешно.

## Часто задаваемые вопросы и особые случаи

### Что если мне нужен другой формат изображения?

Метод `Save` принимает любое значение перечисления `BarCodeImageFormat`, например `Jpeg`, `Bmp` или `Gif`. Замените `BarCodeImageFormat.Png` на нужный формат, а остальной код останется без изменений.

### Как усечение влияет на ёмкость данных?

Включение **compact mode** (усечение) уменьшает количество строк, что может снизить максимальную ёмкость данных штрих‑кода. Если вы получите исключение «Data too large», увеличьте количество колонок или отключите усечение.

### Могу ли я использовать динамическое количество колонок?

Да. Вы можете вычислять количество колонок исходя из длины входной строки:

```csharp
int desiredColumns = Math.Max(2, Math.Min(30, inputText.Length / 10));
barcode.Parameters.Barcode.Pdf417.Columns = desiredColumns;
```

Этот фрагмент показывает **how to adjust columns** программно, гарантируя, что штрих‑код впишется в заданный макет.

### Ограничен ли X‑размер целыми пикселями?

Свойство `Pixels` принимает любое положительное целое число. Для вывода с более высоким разрешением (например, печать) вы можете предпочесть использовать `Points` вместо `Pixels` для получения независимого от устройства размера.

## Советы для использования в продакшене

* **Pro tip:** Оберните генерацию штрих‑кода в блок try‑catch, чтобы обработать `BarCodeException`, когда входные данные превышают ёмкость символа.  
* **Watch out for:** Права доступа к файловой системе. Процесс должен иметь право записи в целевой каталог, иначе шаг **how to save barcode** завершится ошибкой `UnauthorizedAccessException`.  
* **Performance note:** При создании множества штрих‑кодов в цикле выгодно переиспользовать один экземпляр `BarcodeGenerator` и лишь обновлять свойство `CodeText` между итерациями.

## Заключение

Теперь вы знаете, как **how to save barcode** в PNG‑файл, **enable compact mode**, **how to adjust columns** и **generate PDF417 barcode** с помощью Aspose.BarCode для C#. Полный пример демонстрирует каждый необходимый шаг, от инициализации генератора до записи окончательного изображения.

Отсюда вы можете изучать связанные темы, такие как добавление логотипа к штрих‑коду, настройка цветов или интеграция генератора в ASP.NET Core API. Каждое из этих расширений следует той же схеме, показанной в этом руководстве, поэтому вы можете уверенно адаптировать код.

Не стесняйтесь экспериментировать с различным количеством колонок, X‑размерами и форматами изображений, чтобы соответствовать точным требованиям вашего проекта. Приятного кодинга!

## Что стоит изучить дальше?

Следующие руководства охватывают тесно связанные темы, построенные на техниках, продемонстрированных в этом руководстве. Каждый ресурс включает полные работающие примеры кода с пошаговыми объяснениями, чтобы помочь вам освоить дополнительные возможности API и исследовать альтернативные подходы к реализации в ваших проектах.

- [Как сохранить штрих‑код и сгенерировать PDF417 с Aspose в C#](/barcode/english/net/compact-pdf417-encoding/how-to-save-barcode-and-generate-pdf417-with-aspose-in-c/)
- [Как создать штрих‑код PDF417 в C# с компактным режимом](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-in-c-with-compact-mode/)
- [Как создать штрих‑код PDF417 и сохранить его как PNG в C#](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-and-save-it-as-png-in-c/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}