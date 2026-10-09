---
category: general
date: 2026-09-26
description: Создайте штрих‑код PDF417 на C# с помощью Aspose.BarCode. Следуйте этому
  пошаговому руководству, чтобы настроить столбцы, включить компактный режим и сохранить
  в формате PNG.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate pdf417 barcode
- pdf417 barcode generator c#
- Aspose.BarCode C#
- barcode image format PNG
- compact PDF417 mode
language: ru
lastmod: 2026-09-26
og_description: Создайте штрих‑код PDF417 на C# с помощью Aspose.BarCode. Это руководство
  показывает, как задать количество столбцов, включить компактный режим и экспортировать
  результат в виде PNG‑изображения.
og_image_alt: Screenshot of a generated PDF417 barcode saved as PNG
og_title: Создание штрих‑кода PDF417 на C# – пошаговое руководство
schemas:
- author: Aspose
  dateModified: '2026-09-26'
  description: Generate PDF417 barcode in C# with Aspose.BarCode. Follow this step‑by‑step
    tutorial to configure columns, enable compact mode, and save as PNG.
  headline: How to generate PDF417 barcode in C# – complete guide
  type: TechArticle
tags:
- C#
- barcode
- Aspose
- PDF417
title: Как сгенерировать штрих‑код PDF417 в C# – полное руководство
url: /ru/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-complete-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Как сгенерировать штрих-код PDF417 на C# – полное руководство

Если вам нужно **создать штрих-код PDF417** в приложении .NET, этот учебник покажет готовое решение, готовое к запуску. Вы увидите, как настроить размер штрих‑кода, количество столбцов и компактный режим, а затем сохранить результат в виде PNG‑файла высокого качества.

Создание штрих‑кода — распространённая задача для систем учёта, платформ продажи билетов и кодирования документов. К концу этого руководства у вас будет автономная C#‑программа, генерирующая компактный PDF417 штрих‑код с использованием библиотеки **pdf417 barcode generator C#** от Aspose.

## Что понадобится

- .NET 6.0 SDK или новее (код также работает с .NET Framework 4.7+)
- Действительная лицензия Aspose.BarCode for .NET (бесплатная оценочная версия подходит для тестирования)
- IDE или редактор, например Visual Studio 2022, Rider или VS Code
- Базовые знания C# консольных проектов

> **Совет:** Если вы используете бесплатную оценочную версию, сгенерированное изображение будет содержать небольшую водяную метку Aspose. Приобретённая лицензия удаляет водяную метку и открывает полный набор функций.

## Шаг 1: Настройка библиотеки Aspose.BarCode

Создайте новый консольный проект и добавьте пакет Aspose.BarCode через NuGet.

```bash
dotnet new console -n Pdf417Demo
cd Pdf417Demo
dotnet add package Aspose.BarCode
```

Пакет предоставляет класс `BarcodeGenerator`, который является ядром рабочего процесса **pdf417 barcode generator C#**.

## Шаг 2: Написание полной программы генерации штрих‑кода

Откройте `Program.cs` и замените его содержимое следующим кодом. Программа демонстрирует каждый необходимый шаг, от инициализации генератора до сохранения изображения.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode.BarCodeImageFormat;

namespace Pdf417Demo
{
    internal class Program
    {
        private static void Main()
        {
            // Step 2.1: Create a generator for PDF417 with Unicode text.
            // The text contains special characters to prove Unicode handling.
            var generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Åspóse.Barcóde©");

            // Step 2.2: Define the module (pixel) size of each barcode element.
            // XDimension controls the width of a single bar; 2 pixels gives a clear image.
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // Step 2.3: Set the number of columns.
            // PDF417 can automatically choose columns, but fixing it to 3 produces a compact layout.
            generator.Parameters.Barcode.Pdf417.Columns = 3;

            // Step 2.4: Enable compact mode.
            // Truncate reduces the amount of data stored, making the barcode smaller.
            generator.Parameters.Barcode.Pdf417.Truncate = true;

            // Step 2.5: Choose the output format and file path.
            // PNG preserves the exact pixel dimensions without compression artifacts.
            string outputPath = "CompactPdf417.png";
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"PDF417 barcode saved to {outputPath}");
        }
    }
}
```

### Почему каждая строка важна

| Line | Purpose |
|------|---------|
| `new BarcodeGenerator(EncodeTypes.Pdf417, "...")` | Создаёт генератор PDF417 и задаёт кодируемый текст. PDF417 поддерживает большие наборы данных и Unicode, что делает его подходящим для сложных идентификаторов. |
| `XDimension.Pixels = 2` | Контролирует визуальную плотность. Меньшие значения дают более тонкие полосы; большие значения повышают читаемость на экранах с низким разрешением. |
| `Pdf417.Columns = 3` | Переопределяет автоматический расчёт количества столбцов. Фиксированные столбцы полезны, когда необходимо разместить штрих‑код в заранее заданном пространстве. |
| `Pdf417.Truncate = true` | Активирует компактный режим, который удаляет лишние отступы и уменьшает общий размер. |
| `Save(..., BarCodeImageFormat.Png)` | Записывает штрих‑код в PNG‑файл, формат без потерь, идеальный для дальнейшей обработки или встраивания в PDF. |

## Шаг 3: Запуск программы и проверка результата

Build and run the project:

```bash
dotnet run
```

Вы должны увидеть сообщение в консоли, подтверждающее расположение файла, и файл с именем **CompactPdf417.png** появится в папке проекта.

![Generated PDF417 barcode example](images/compact-pdf417.png){.img-responsive alt="Пример сгенерированного штрих‑кода PDF417"}

*Изображение показывает компактный штрих‑код PDF417, который кодирует строку “Åspóse.Barcóde©”.*  

Если открыть PNG в просмотрщике изображений, вы заметите три столбца наложенных блоков данных, каждая полоса шириной 2 пикселя. Сканирование штрих‑кода стандартным считывателем PDF417 возвращает исходный текст, подтверждая, что генератор работает как ожидается.

## Распространённые подводные камни и как их избежать

| Issue | Reason | Fix |
|-------|--------|-----|
| Штрих‑код выглядит размытым | XDimension установлен слишком низко для целевого DPI | Увеличьте `XDimension.Pixels` до 3 или 4, либо рендерите с более высоким разрешением, используя `generator.Save(..., BarCodeImageFormat.Tiff)` |
| Unicode‑символы теряются | Входная строка не закодирована как UTF‑8 | Убедитесь, что исходный файл сохранён в кодировке UTF‑8; генератор автоматически обрабатывает Unicode, когда тип строки — `string`. |
| `Truncate` вызывает исключение | Размер данных превышает максимум для выбранного количества столбцов | Либо увеличьте `Pdf417.Columns`, либо установите `Pdf417.Truncate = false`, чтобы генератор выделил достаточно места. |
| Лицензия не применена | Оценочная версия добавляет водяную метку | Примените действительный файл лицензии через `Aspose.BarCode.License` перед созданием генератора. |

## Расширение решения

После того как у вас будет базовый поток **generate PDF417 barcode**, вы можете изучить дополнительные возможности:

- **Уровень коррекции ошибок** – Настройте `generator.Parameters.Barcode.Pdf417.ErrorCorrectionLevel` для повышения устойчивости к повреждениям.
- **Настройка цвета** – Используйте `generator.Parameters.Barcode.ForegroundColor` и `BackgroundColor` для соответствия фирменным рекомендациям.
- **Встраивание в PDF** – Сочетайте Aspose.PDF с Aspose.BarCode, чтобы разместить штрих‑код непосредственно в PDF‑документе.
- **Пакетная генерация** – Пройдитесь по коллекции идентификаторов, чтобы создать несколько PNG‑файлов за один запуск.

Все эти параметры задокументированы в справочнике API Aspose.BarCode и следуют той же схеме, продемонстрированной выше.

## Заключение

Теперь вы знаете, как **создать штрих‑код PDF417** в C# с помощью Aspose.BarCode, настроить столбцы, включить компактный режим и экспортировать результат в виде PNG‑изображения. Полный пример работает сразу после установки и может быть адаптирован для более крупных проектов, таких как системы продажи билетов, метки учёта или безопасное кодирование документов.  

Далее попробуйте расширенные настройки **pdf417 barcode generator C#**, такие как коррекция ошибок и настройка цвета, или интегрируйте штрих‑код в PDF‑отчёт с помощью Aspose.PDF. Экспериментируйте с различными значениями `XDimension` и количеством столбцов, чтобы найти оптимальный баланс между размером и надёжностью сканирования для вашего конкретного случая. Приятного кодирования!

## Что стоит изучить дальше?

Следующие учебники охватывают тесно связанные темы, опирающиеся на техники, продемонстрированные в этом руководстве. Каждый ресурс включает полностью работающие примеры кода с пошаговыми объяснениями, чтобы помочь вам освоить дополнительные возможности API и исследовать альтернативные подходы к реализации в ваших проектах.

- [Создать штрих‑код PDF417 на C# – полное руководство с компактным макетом](/barcode/english/net/compact-pdf417-encoding/generate-pdf417-barcode-in-c-complete-guide-with-compact-lay/)
- [Пример Aspose barcode: создание Macro PDF417 в C#](/barcode/english/net/compact-pdf417-encoding/aspose-barcode-example-generate-macro-pdf417-in-c/)
- [Как сохранить штрих‑код в C# – генерировать штрих‑коды PDF417](/barcode/english/net/compact-pdf417-encoding/how-to-save-barcode-in-c-generate-pdf417-barcodes/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}