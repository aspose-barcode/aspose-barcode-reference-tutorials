---
category: general
date: 2026-09-29
description: Как сохранить штрих‑код с помощью Aspose.BarCode в C# и узнать, как генерировать
  PDF417 с макро‑метаданными. Следуйте пошаговому руководству.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to save barcode
- how to generate pdf417
- how to set pdf417
- generate barcode with aspose
language: ru
lastmod: 2026-09-29
og_description: Сохранить штрих‑код с помощью Aspose.BarCode в C# просто. Этот учебник
  показывает, как сгенерировать PDF417 с макро‑метаданными и задать все необходимые
  параметры.
og_image_alt: Screenshot showing how to save barcode as PNG with PDF417 macro metadata
og_title: Как сохранить штрих‑код с Aspose – руководство по генерации PDF417
schemas:
- author: Aspose
  dateModified: '2026-09-29'
  description: How to save barcode using Aspose.BarCode in C# and learn how to generate
    PDF417 with macro metadata. Follow step‑by‑step guide.
  headline: How to save barcode and generate PDF417 with Aspose in C#
  type: TechArticle
- description: How to save barcode using Aspose.BarCode in C# and learn how to generate
    PDF417 with macro metadata. Follow step‑by‑step guide.
  name: How to save barcode and generate PDF417 with Aspose in C#
  steps:
  - name: '**Creating the generator** – The `BarcodeGenerator` constructor takes the
      barcode type (`EncodeTypes.MacroPdf417`) and the data to encode. Macro PDF417
      is a special variant that carries file‑transfer information, which is why we
      later fill macro fields.'
    text: '**Creating the generator** – The `BarcodeGenerator` constructor takes the
      barcode type (`EncodeTypes.MacroPdf417`) and the data to encode. Macro PDF417
      is a special variant that carries file‑transfer information, which is why we
      later fill macro fields.'
  - name: '**Appearance settings** – `XDimension.Pixels` controls the narrow bar width;
      adjusting it changes the overall image size without affecting data integrity.
      `Pdf417.Columns` defines the layout of the barcode matrix.'
    text: '**Appearance settings** – `XDimension.Pixels` controls the narrow bar width;
      adjusting it changes the overall image size without affecting data integrity.
      `Pdf417.Columns` defines the layout of the barcode matrix.'
  - name: '**Macro metadata** – These properties (`MacroPdf417FileID`, `MacroPdf417SegmentID`,
      etc.) are essential when you need to split a large file into multiple barcode
      segments. Setting them correctly ensures that a scanner can reconstruct the
      original file.'
    text: '**Macro metadata** – These properties (`MacroPdf417FileID`, `MacroPdf417SegmentID`,
      etc.) are essential when you need to split a large file into multiple barcode
      segments. Setting them correctly ensures that a scanner can reconstruct the
      original file.'
  - name: '**Saving the image** – The `Save` method writes the generated barcode to
      disk. You can choose any supported format (`Png`, `Jpeg`, `Bmp`, etc.). This
      line demonstrates the exact **how to save barcode** operation requested.'
    text: '**Saving the image** – The `Save` method writes the generated barcode to
      disk. You can choose any supported format (`Png`, `Jpeg`, `Bmp`, etc.). This
      line demonstrates the exact **how to save barcode** operation requested.'
  type: HowTo
tags:
- barcode
- PDF417
- Aspose
- C#
title: Как сохранить штрих‑код и сгенерировать PDF417 с помощью Aspose в C#
url: /ru/net/compact-pdf417-encoding/how-to-save-barcode-and-generate-pdf417-with-aspose-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Как сохранить штрих‑код и сгенерировать PDF417 с помощью Aspose в C#

Сохранение штрих‑кода с использованием Aspose.BarCode в C# — распространённая задача, когда необходимо внедрить данные в файл изображения. Это руководство проведёт вас через весь процесс создания штрих‑кода PDF417 с макро‑метаданными и сохранения результата в виде PNG‑изображения. К концу вы узнаете **как генерировать PDF417**, **как задавать параметры PDF417** и, что самое важное, **как программно сохранять файлы штрих‑кодов**.

Вы увидите полностью готовый, исполняемый пример, охватывающий каждый шаг — от добавления пакета NuGet Aspose.BarCode до настройки макро‑полей, таких как идентификатор файла, количество сегментов и контрольная сумма. Внешняя документация не требуется; код можно скопировать в новый консольный проект и сразу запустить. В руководстве предполагается, что у вас установлены Visual Studio 2022 (или новее) и .NET 6.0.

## Требования

- .NET 6.0 SDK (или любая версия .NET, поддерживаемая Aspose.BarCode 23.11+)
- Visual Studio 2022, VS Code или ваша любимая IDE для C#
- **Aspose.BarCode for .NET** пакет NuGet  
  ```bash
  dotnet add package Aspose.BarCode
  ```
- Базовые знания синтаксиса C# и консольных приложений

> **Полезный совет:** Используйте бесплатную оценочную лицензию разработчика от Aspose, если у вас ещё нет коммерческой лицензии. Оценка работает без изменений кода.

## Как сохранить штрих‑код — полный пример

Следующий код создаёт **Macro PDF417** штрих‑код, заполняет все макро‑поля и сохраняет изображение как `ExtPDF417Meta.png`. Все необходимые директивы `using` включены, так что вы можете вставить фрагмент напрямую в `Program.cs`.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Step 1: Create a barcode generator for Macro PDF417 with sample data
        using (BarcodeGenerator generator = new BarcodeGenerator(
            EncodeTypes.MacroPdf417,          // EncodeTypes enum selects the barcode type
            "Åspóse.Barcóde©"))               // Sample data – Unicode characters are supported
        {
            // Step 2: Define basic barcode appearance
            generator.Parameters.Barcode.XDimension.Pixels = 2;   // narrow bar width (2 px)
            generator.Parameters.Barcode.Pdf417.Columns = 5;    // number of columns per row

            // Step 3: Configure Macro PDF417 metadata
            generator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
            generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;
            generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;
            generator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";
            generator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234; // CCITT‑16 example
            generator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000;
            generator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2019, 11, 1);
            generator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
            generator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
            generator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;

            // Step 4: Save the generated barcode as a PNG image
            // This is the core of **how to save barcode** with Aspose.
            generator.Save("ExtPDF417Meta.png", BarCodeImageFormat.Png);
        }

        Console.WriteLine("Barcode saved as ExtPDF417Meta.png");
    }
}
```

### Почему каждый шаг важен

1. **Создание генератора** — Конструктор `BarcodeGenerator` принимает тип штрих‑кода (`EncodeTypes.MacroPdf417`) и данные для кодирования. Macro PDF417 — специальный вариант, который переносит информацию о передаче файлов, поэтому позже мы заполняем макро‑поля.
2. **Настройки внешнего вида** — `XDimension.Pixels` управляет шириной узкой полоски; изменение этого параметра меняет общий размер изображения, не затрагивая целостность данных. `Pdf417.Columns` задаёт раскладку матрицы штрих‑кода.
3. **Метаданные макроса** — Эти свойства (`MacroPdf417FileID`, `MacroPdf417SegmentID` и др.) необходимы, когда нужно разбить большой файл на несколько сегментов штрих‑кода. Правильная их установка гарантирует, что сканер сможет восстановить исходный файл.
4. **Сохранение изображения** — Метод `Save` записывает сгенерированный штрих‑код на диск. Вы можете выбрать любой поддерживаемый формат (`Png`, `Jpeg`, `Bmp` и т.д.). Эта строка демонстрирует точную операцию **как сохранить штрих‑код**, о которой шла речь.

> **Частый вопрос:** *Что делать, если нужен другой формат изображения?*  
> Замените `BarCodeImageFormat.Png` на `BarCodeImageFormat.Jpeg` (или любое другое поддерживаемое значение перечисления) и соответственно измените расширение файла.

## Как сгенерировать PDF417 с макро‑метаданными

Если нужен обычный PDF417 (без макро‑данных), можно пропустить секцию макроса и оставить базовый генератор:

```csharp
using (BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.Pdf417, "Sample data"))
{
    gen.Parameters.Barcode.XDimension.Pixels = 3;
    gen.Save("SimplePdf417.png", BarCodeImageFormat.Png);
}
```

Приведённый код иллюстрирует **как быстро сгенерировать PDF417**. Обратите внимание, что перечисление `EncodeTypes.Pdf417` выбирает версию без макроса.

## Как задать PDF417 — расширенные параметры

Aspose.BarCode предоставляет множество параметров, специфичных для PDF417. Ниже перечислены некоторые, которые могут пригодиться:

| Property | Description | Typical values |
|----------|-------------|----------------|
| `Pdf417.Columns` | Количество колонок в строке | 1‑30 (по умолчанию 3) |
| `Pdf417.Rows` | Количество строк (авто‑расчёт, если 0) | 0‑90 |
| `Pdf417.ErrorLevel` | Уровень коррекции ошибок (0‑8) | 2‑4 для баланса размера/надёжности |
| `Pdf417.RowsPerStrip` | Строк на полосу для больших штрих‑кодов | 0 (авто) |
| `Pdf417.Pdf417MacroFileID` | Идентификатор файла при использовании макроса | Любое 32‑битное целое |

Установка этих значений выполняется по той же схеме, что показана в **Шаге 2** основного примера. Настройте их перед вызовом `Save`.

## Ожидаемый результат

Запуск полной программы создаёт `ExtPDF417Meta.png` в рабочем каталоге исполняемого файла. На изображении находится высоко‑разрешённый штрих‑код PDF417 со всеми встроенными макро‑полями. Сканирование изображения сканером, поддерживающим PDF417 (или мобильным приложением), вернёт исходную строку данных `"Åspóse.Barcóde©"` вместе с макро‑метаданными (ID файла, ID сегмента и т.д.).

![Barcode saved as PNG – how to save barcode example](ExtPDF417Meta.png "How to save barcode as PNG with macro PDF417 metadata")

*Текст alt‑изображения:* **как сохранить штрих‑код как PNG с метаданными PDF417 macro** (соответствует основному ключевому слову).

## Заключение

В этом руководстве вы узнали **как сохранять штрих‑коды** с помощью Aspose.BarCode, **как генерировать PDF417**, **как задавать параметры PDF417** и **как создавать штрих‑коды с Aspose** как для обычных, так и для макро‑включённых сценариев.

## Что изучать дальше?

Следующие руководства охватывают тесно связанные темы, расширяющие техники, продемонстрированные в этом материале. Каждый ресурс содержит полностью работающие примеры кода с пошаговыми объяснениями, чтобы помочь вам освоить дополнительные возможности API и исследовать альтернативные подходы в собственных проектах.

- [How to Generate PDF417 Barcode with Aspose – Complete Guide](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-with-aspose-complete-guide/)
- [How to Generate PDF417 Barcode Image in C# with Aspose](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-image-in-c-with-aspose/)
- [How to generate barcode in C# with Aspose.BarCode and add metadata](/barcode/english/net/compact-pdf417-encoding/how-to-generate-barcode-in-c-with-aspose-barcode-and-add-met/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}