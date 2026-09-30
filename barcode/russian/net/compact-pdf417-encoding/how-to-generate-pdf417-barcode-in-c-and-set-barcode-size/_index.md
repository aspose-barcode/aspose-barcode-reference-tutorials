---
category: general
date: 2026-08-22
description: Узнайте, как генерировать штрих‑код PDF417 в C# с помощью Aspose.BarCode,
  задавать размер штрих‑кода, регулировать количество столбцов и включать компактный
  режим.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate pdf417 barcode
- how to generate pdf417
- set barcode size
language: ru
lastmod: 2026-08-22
og_description: Создайте штрих‑код PDF417 на C# с помощью Aspose.BarCode. Это руководство
  показывает, как задать размер штрих‑кода, управлять колонками и включить компактный
  режим для получения меньшего изображения.
og_image_alt: Screenshot of a generated PDF417 barcode in C# showing compact mode
og_title: Создание штрих‑кода PDF417 в C# – установка размера, количества столбцов
  и компактного режима
schemas:
- author: Aspose
  dateModified: '2026-08-22'
  description: Learn how to generate PDF417 barcode in C# with Aspose.BarCode, set
    barcode size, adjust columns, and enable compact mode.
  headline: How to generate PDF417 barcode in C# and set barcode size
  type: TechArticle
tags:
- pdf417
- barcode
- csharp
title: Как сгенерировать штрих‑код PDF417 в C# и установить размер штрих‑кода
url: /ru/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-and-set-barcode-size/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Как генерировать PDF417 barcode в C# и задать размер штрих‑кода

Если вам нужно **генерировать PDF417 barcode** в приложении .NET, это руководство проведет вас через весь процесс. Вы увидите точно **как генерировать PDF417** с помощью Aspose.BarCode, настроите **set barcode size**, и создадите компактный PNG, который можно встроить в отчёты или мобильные приложения.

Создание штрих‑кода не требует отдельного графического редактора. К концу этого руководства у вас будет полностью рабочий метод C#, который генерирует изображение PDF417 с точными размерами, необходимыми вам, готовое для дальнейшей обработки.

## Что вы узнаете

* Установить и подключить библиотеку Aspose.BarCode.
* Создать PDF417 barcode generator и указать кодируемый текст.
* **Set barcode size** путем настройки X‑dimension и количества столбцов.
* Включить компактный (усечённый) режим для уменьшения символа.
* Сохранить результат в файл PNG.
* Устранить распространённые проблемы, такие как нечитаемые коды и слишком большие изображения.

### Требования

* .NET 6.0 или новее (API также работает с .NET Framework 4.6+).
* Базовое знакомство с C# и Visual Studio (или любой IDE для C#).
* Действительная лицензия Aspose.BarCode (бесплатная оценочная версия подходит для тестирования).

> **Pro tip:** Если вы планируете генерировать множество штрих‑кодов в цикле, переиспользуйте один экземпляр `BarcodeGenerator` и меняйте только свойство `CodeText`. Это уменьшает выделения памяти.

## Генерация PDF417 barcode с помощью Aspose.BarCode

Первый шаг — создать экземпляр `BarcodeGenerator` для символьного набора PDF417. Этот объект является точкой входа для всех операций со штрих‑кодами.

```csharp
using Aspose.BarCode.Generation;

// Step 1: Create a PDF417 barcode generator with the desired text
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.Pdf417,          // Symbology
    "Sample text for PDF417");   // Data to encode
```

*Почему это важно*: `EncodeTypes.Pdf417` указывает библиотеке использовать стандарт PDF417, который поддерживает большие объёмы данных и коррекцию ошибок. Конструктор также принимает данные, которые вы хотите закодировать, устраняя необходимость отдельного присваивания `CodeText` позже.

## Установка размера штрих‑кода и количества столбцов

Символы PDF417 состоят из строк и столбцов небольших прямоугольных модулей. Управление шириной модуля (X‑dimension) и количеством столбцов позволяет точно настроить общие размеры.

```csharp
// Step 2: Adjust the module size (X‑dimension) – 2 pixels per module
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;

// Step 3: Define the number of columns for the PDF417 code
barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 3;
```

*Объяснение*:  
* **X‑dimension** (`Pixels`) определяет ширину каждого модуля. Меньшие значения дают более плотный штрих‑код, а большие значения повышают читаемость на сканерах с низким разрешением.  
* **Columns** управляют горизонтальной компоновкой. Меньшее количество столбцов делает штрих‑код выше; больше столбцов — шире. Настраивая эти два параметра вместе, вы достигаете точного **set barcode size**, который вам нужен.

## Включение компактного режима для уменьшения штрих‑кода

PDF417 включает «compact» (или truncated) режим, который удаляет лишние отступы и уменьшает общий размер. Это особенно полезно, когда экранное пространство ограничено.

```csharp
// Step 4: Enable compact mode to truncate the barcode data
barcodeGenerator.Parameters.Barcode.Pdf417.Truncate = true;
```

*Почему включать усечение?*  
Когда `Truncate` равно `true`, генератор опускает стоп‑шаблон и некоторые коды коррекции ошибок, которые не требуются в большинстве сценариев сканирования. Получаемое изображение примерно на 15‑20 % меньше, не жертвуя целостностью данных в типичных случаях использования.

## Сохранение штрих‑кода как PNG‑изображения

После настройки размера и режима запишите штрих‑код на диск. PNG — без потерь, что гарантирует чёткие границы модулей.

```csharp
// Step 5: Save the generated barcode as a PNG image
barcodeGenerator.Save(
    "YOUR_DIRECTORY/CompactPdf417.png",
    BarCodeImageFormat.Png);
```

Файл `CompactPdf417.png` будет содержать чёткий символ PDF417, соответствующий размерам, заданным на предыдущих шагах.

### Ожидаемый результат

Открытие сохранённого PNG должно показать вертикально ориентированный PDF417 barcode, состоящий из трёх столбцов, каждый модуль шириной 2 px, и общий размер примерно **120 × 240 px** (ширина × высота). Сканирование изображения любым стандартным считывателем PDF417 возвращает исходный текст «Sample text for PDF417».

## Распространённые подводные камни и как их избежать

| Symptom | Likely cause | Fix |
|---------|--------------|-----|
| Штрих‑код нечитаем | X‑dimension слишком маленькая для сканера | Увеличьте `XDimension.Pixels` до 3 или 4 |
| Изображение слишком широкое для UI | Установлено слишком много столбцов | Уменьшите `Pdf417.Columns` или включите `Truncate` |
| Исключение `ArgumentOutOfRangeException` | Отрицательное или нулевое количество столбцов | Убедитесь, что `Columns` — положительное целое (минимум 1) |
| PNG‑файл пустой | Путь вывода не существует или нет прав на запись | Проверьте, что каталог существует и приложение имеет права на запись |

> **Pro tip:** Используйте `barcodeGenerator.ValidateParameters()` перед вызовом `Save()`, чтобы заранее обнаружить ошибки конфигурации.

## Полный, исполняемый пример

Ниже представлена автономная консольная программа, включающая все шаги выше. Скопируйте её в новый проект C#, восстановите пакет NuGet Aspose.BarCode и запустите, чтобы увидеть результат.

```csharp
using System;
using Aspose.BarCode.Generation;

namespace Pdf417Demo
{
    class Program
    {
        static void Main()
        {
            // Create the generator with the data to encode
            var generator = new BarcodeGenerator(
                EncodeTypes.Pdf417,
                "Sample text for PDF417");

            // Set module width (X‑dimension) – 2 px per module
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // Choose a small number of columns to keep the barcode compact
            generator.Parameters.Barcode.Pdf417.Columns = 3;

            // Enable truncation for a smaller image
            generator.Parameters.Barcode.Pdf417.Truncate = true;

            // Optional: validate parameters before saving
            generator.ValidateParameters();

            // Save as PNG
            const string outputPath = "CompactPdf417.png";
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"PDF417 barcode saved to {outputPath}");
        }
    }
}
```

**Running the program** создаёт `CompactPdf417.png` в рабочем каталоге исполняемого файла. Сканируйте изображение мобильным приложением (например, «Barcode Scanner»), чтобы убедиться, что закодированный текст соответствует исходной строке.

## Следующие шаги и связанные темы

* **Increase error correction level** – настройте `Pdf417.ErrorLevel` для условий с шумными сканированиями.  
* **Change orientation** – установите `Pdf417.Rotate` в `RotationAngle.Rotate90`, если нужен горизонтальный макет.  
* **Embed the barcode in a PDF** – комбинируйте Aspose.PDF с Aspose.BarCode, чтобы разместить изображение непосредственно в документе.  
* **Generate other 2‑D barcodes** – тот же класс `BarcodeGenerator` поддерживает DataMatrix, QR и Aztec коды; просто замените `EncodeTypes.Pdf417` на нужную символьную схему.

Освоив техники **generate PDF417 barcode**, вы сможете автоматизировать билеты, маркировку инвентаря и безопасную передачу данных в широком спектре приложений .NET.

## Заключение

Теперь вы знаете, как **generate PDF417 barcode** в C#, точно **set barcode size**, настроить столбцы, включить компактный режим и сохранить результат в PNG. Применяйте эти настройки, чтобы соответствовать любым ограничениям UI или требованиям сканирования, и при необходимости расширяйте подход на другие форматы штрих‑кодов. Счастливого кодинга!

## Что вам стоит изучить дальше?

Следующие руководства охватывают тесно связанные темы, которые развивают техники, продемонстрированные в этом руководстве. Каждый ресурс включает полные рабочие примеры кода с пошаговыми объяснениями, чтобы помочь вам освоить дополнительные возможности API и исследовать альтернативные подходы к реализации в ваших проектах.

- [Как генерировать PDF417 Barcode – Compact PDF417 Encoding](/barcode/english/net/compact-pdf417-encoding/)
- [Как создать Barcode – Compact PDF417 с Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [Как генерировать DataMatrix штрих‑коды с помощью Aspose.BarCode для .NET – пошаговое руководство](/barcode/english/net/datamatrix-barcode-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}