---
category: general
date: 2026-10-28
description: Создайте штрих‑код из текста на C# с помощью Aspose.BarCode. Узнайте,
  как генерировать изображение штрих‑кода PDF417, задавать количество столбцов, регулировать
  X‑размер и включать компактный режим.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode from text
- generate barcode c#
- generate pdf417 barcode
- pdf417 barcode image
language: ru
lastmod: 2026-10-28
og_description: Создайте штрих‑код из текста в C# с помощью Aspose.BarCode. Этот учебник
  показывает, как сгенерировать изображение штрих‑кода PDF417, настроить размер, количество
  столбцов и компактный режим.
og_image_alt: Screenshot showing a compact PDF417 barcode created from text using
  C#
og_title: Создайте штрих‑код из текста в C# — пошаговое руководство
schemas:
- author: Aspose
  dateModified: '2026-10-28'
  description: Create barcode from text in C# with Aspose.BarCode. Learn to generate
    PDF417 barcode image, set columns, adjust X‑dimension, and enable compact mode.
  headline: How to create barcode from text in C# using Aspose.BarCode
  type: TechArticle
tags:
- barcode
- C#
- PDF417
- image generation
title: Как создать штрих‑код из текста в C# с помощью Aspose.BarCode
url: /ru/net/compact-pdf417-encoding/how-to-create-barcode-from-text-in-c-using-aspose-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Как создать штрих‑код из текста в C# с помощью Aspose.BarCode

Если вам нужно **создать штрих‑код из текста** в .NET‑приложении, это руководство предоставляет готовое решение. Вы увидите, как **генерировать изображения штрих‑кода PDF417**, управлять шириной модуля, количеством колонок и включать компактный режим, не выходя из IDE.

В руководстве рассматривается всё, что требуется для **генерации штрих‑кода C#**: от установки библиотеки до сохранения окончательного PNG‑файла. По завершении вы сможете внедрять высокоплотный штрих‑код PDF417 в отчёты, билеты или этикетки инвентаря.

## Требования

Прежде чем начать, убедитесь, что у вас есть:

* .NET 6.0 SDK или более новая версия  
* Visual Studio 2022 (или любой редактор, поддерживающий .NET)  
* Доступ в Интернет для загрузки пакета Aspose.BarCode for .NET из NuGet  

Этого достаточно для компиляции и запуска примера в Windows, Linux или macOS.

## Шаг 1: Установите NuGet‑пакет Aspose.BarCode

Библиотека, обеспечивающая генерацию штрих‑кодов, — **Aspose.BarCode for .NET**. Установите её с помощью .NET CLI:

```bash
dotnet add package Aspose.BarCode
```

Пакет добавляет пространство имён `Aspose.BarCode`, в котором находится класс `BarcodeGenerator`, используемый в этом руководстве.

## Шаг 2: Создайте консольный проект и добавьте код

Создайте новый консольный проект и замените сгенерированный `Program.cs` следующим кодом. Программа демонстрирует, как **создать штрих‑код из текста** и сохранить его как **изображение штрих‑кода PDF417**.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace Pdf417Demo
{
    class Program
    {
        static void Main()
        {
            // Step 2.1: Define the text to encode.
            // Unicode characters such as Å, ó, and © are supported out of the box.
            string data = "Åspóse.Barcóde©";

            // Step 2.2: Initialize the PDF417 generator with the desired text.
            // EncodeTypes.Pdf417 tells the generator which symbology to use.
            BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, data);

            // Step 2.3: Set the X‑dimension (module width) to 2 pixels for a denser barcode.
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // Step 2.4: Define the number of columns in the PDF417 symbol.
            // Fewer columns produce a taller barcode; three columns keep it compact.
            generator.Parameters.Barcode.Pdf417.Columns = 3;

            // Step 2.5: Enable compact mode by truncating the right‑hand column.
            // Truncate reduces the overall width while preserving data integrity.
            generator.Parameters.Barcode.Pdf417.Truncate = true;

            // Step 2.6: Choose the output folder and file name.
            string outputPath = "CompactPdf417.png";

            // Step 2.7: Save the barcode as a PNG image.
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"PDF417 barcode image saved to {outputPath}");
        }
    }
}
```

### Почему важна каждая строка

* **`EncodeTypes.Pdf417`** выбирает символьный набор PDF417, идеальный для кодирования больших объёмов данных в двумерном формате.  
* **`XDimension.Pixels = 2`** уменьшает ширину модуля, делая штрих‑код более плотным и подходящим для ограниченного пространства.  
* **`Pdf417.Columns = 3`** задаёт количество вертикальных колонок данных; меньшее значение даёт более высокий, но уже штрих‑код.  
* **`Pdf417.Truncate = true`** активирует компактный режим, обрезая неиспользуемые колонки справа. Это ключевая настройка, превращающая обычный PDF417 в **компактное изображение штрих‑кода PDF417**.  

## Шаг 3: Сборка и запуск проекта

Выполните следующие команды в каталоге проекта:

```bash
dotnet build
dotnet run
```

Когда программа завершит работу, в консоли появится сообщение с подтверждением пути к файлу. Откройте `CompactPdf417.png` в любом просмотрщике изображений, чтобы проверить результат.

**Ожидаемый вывод** – контрастный PNG, показывающий компактный штрих‑код PDF417, кодирующий строку `Åspóse.Barcóde©`. Сканирование изображения стандартным считывателем штрих‑кодов возвращает исходный текст, подтверждая успешную **генерацию pdf417 штрих‑кода**.

## Шаг 4: Настройка штрих‑кода под разные сценарии

Хотя в примере используется фиксированное количество колонок и X‑размер, вы можете адаптировать генератор под другие требования:

| Сценарий | Корректировка |
|----------|----------------|
| Большой объём данных | Увеличьте `Pdf417.Columns` или задайте `Pdf417.Rows` вручную |
| Повышенная надёжность сканирования | Увеличьте `XDimension.Pixels` до 3 или 4 |
| Другой формат изображения | Замените `BarCodeImageFormat.Png` на `Jpeg` или `Bmp` |
| Прозрачный фон | Установите `generator.Parameters.Barcode.BackgroundColor = System.Drawing.Color.Transparent` |

Эти параметры позволяют создавать **генерацию штрих‑кода C#**, подходящие для мобильных приложений, настольных отчётов или веб‑служб.

## Шаг 5: Обработка граничных случаев и лучшие практики

* **Поддержка Unicode** – Генератор автоматически кодирует Unicode‑символы, но убедитесь, что исходная строка в UTF‑8, если вы читаете её из файла.  
* **Большой объём текста** – PDF417 может кодировать до 1 850 буквенно‑цифровых символов. При превышении лимита библиотека бросит исключение; разбейте данные на несколько штрих‑кодов или перейдите к символьному набору большей ёмкости.  
* **Обработка ошибок** – Оберните код генерации в блок `try/catch`, чтобы перехватывать `BarCodeException` и выводить понятное сообщение об ошибке.  
* **Производительность** – При генерации множества штрих‑кодов в цикле выгодно переиспользовать один экземпляр `BarcodeGenerator` и менять только `CodeText` между итерациями.

```csharp
try
{
    generator.CodeText = nextText;
    generator.Save($"barcode_{i}.png", BarCodeImageFormat.Png);
}
catch (BarCodeException ex)
{
    Console.Error.WriteLine($"Failed to generate barcode: {ex.Message}");
}
```

## Полный список исходного кода

Ниже представлена полностью автономная программа, которую можно скопировать в `Program.cs`. Дополнительные файлы не требуются.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace Pdf417Demo
{
    class Program
    {
        static void Main()
        {
            string data = "Åspóse.Barcóde©";

            BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, data);
            generator.Parameters.Barcode.XDimension.Pixels = 2;
            generator.Parameters.Barcode.Pdf417.Columns = 3;
            generator.Parameters.Barcode.Pdf417.Truncate = true;

            string outputPath = "CompactPdf417.png";
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"PDF417 barcode image saved to {outputPath}");
        }
    }
}
```

Запуск этой программы создаёт **изображение штрих‑кода pdf417**, показанное на иллюстрации ниже.

![Compact PDF417 barcode created from text using C#](/images/compact-pdf417.png){.img-fluid alt="пример создания штрих‑кода из текста, показывающий компактный штрих‑код PDF417"}

*Описание изображения: PNG‑файл отображает компактный штрих‑код PDF417, кодирующий строку «Åspóse.Barcóde©».*  

## Заключение

Теперь вы знаете, как **создать штрих‑код из текста** в C# и получить **изображение штрих‑кода PDF417** с пользовательскими размерами и компактным режимом. Пример демонстрирует основные шаги для **генерации штрих‑кода C#**, работу с Unicode‑данными и настройку визуальных параметров под различные сценарии развертывания.

Далее изучайте связанные темы, такие как **генерация QR‑кода в C#**, **добавление штрих‑кода в PDF‑документы** или **встраивание штрих‑кодов в ASP.NET Core API**. Все они опираются на те же фундаментальные возможности `BarcodeGenerator`, рассмотренные здесь.

Удачной разработки и приятного внедрения штрих‑кодов в ваши .NET‑решения!

## Что изучать дальше?

Следующие руководства охватывают тесно связанные темы, построенные на техниках, продемонстрированных в этом руководстве. Каждый ресурс включает полностью работающие примеры кода с пошаговыми объяснениями, чтобы помочь вам освоить дополнительные возможности API и исследовать альтернативные подходы в собственных проектах.

- [Generate PDF417 Barcode in C# – Create PDF417 Barcode C#](/barcode/english/net/compact-pdf417-encoding/generate-pdf417-barcode-in-c-create-pdf417-barcode-c/)
- [How to generate PDF417 barcode with Aspose.BarCode in C#](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-with-aspose-barcode-in-c/)
- [How to create PDF417 barcode image in C# – complete guide](/barcode/english/net/compact-pdf417-encoding/generate-pdf417-barcode-in-c-complete-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}