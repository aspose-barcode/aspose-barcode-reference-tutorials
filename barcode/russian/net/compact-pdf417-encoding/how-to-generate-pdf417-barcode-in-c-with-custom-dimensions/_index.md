---
category: general
date: 2026-09-07
description: Создайте штрих‑код PDF417 на C# и узнайте, как задать размеры штрих‑кода
  для точного контроля. Следуйте этому пошаговому руководству, чтобы создать PNG‑изображение.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate pdf417 barcode
- how to generate pdf417 barcode
- how to set barcode dimensions
language: ru
lastmod: 2026-09-07
og_description: Создайте штрих‑код PDF417 на C# и узнайте, как задать его размеры.
  Этот учебник демонстрирует полностью готовый, исполняемый пример.
og_image_alt: Generated PDF417 barcode image with custom dimensions
og_title: Генерация штрихкода PDF417 в C# – полное руководство с размерами
schemas:
- author: Aspose
  dateModified: '2026-09-07'
  description: Generate PDF417 barcode in C# and learn how to set barcode dimensions
    for precise control. Follow this step‑by‑step guide to create a PNG image.
  headline: How to generate PDF417 barcode in C# with custom dimensions
  type: TechArticle
- description: Generate PDF417 barcode in C# and learn how to set barcode dimensions
    for precise control. Follow this step‑by‑step guide to create a PNG image.
  name: How to generate PDF417 barcode in C# with custom dimensions
  steps:
  - name: Expected output
    text: '- **File:** `Pdf417Layout.png` (PNG, lossless) - **Dimensions:** Determined
      by `XDimension` (2 px) × (columns × rows) matrix - **Content:** A scannable
      PDF417 barcode encoding the Unicode string `Åspóse.Barcóde©`'
  - name: What if I need a larger image for printing?
    text: Increase `XDimension.Pixels` to 4 or 5. Larger values produce a higher‑resolution
      barcode but also increase file size.
  - name: Can I encode more data than the example string?
    text: Yes. PDF417 can hold up to 1,850 characters. Just replace the text argument
      in the `BarcodeGenerator` constructor. If the data exceeds the matrix capacity,
      the library automatically adds extra rows.
  - name: How does error correction work?
    text: 'PDF417 includes built‑in error correction. You can adjust its level via:'
  - name: What if the barcode appears blurry on screen?
    text: 'Make sure the output image’s DPI matches the display environment. You can
      set DPI when saving:'
  - name: Next steps
    text: '- Explore **how to generate PDF417 barcode** with different image formats
      (JPEG, BMP). - Learn **how to set barcode dimensions** dynamically based on
      user input or device DPI. - Integrate the barcode generation into an ASP.NET
      Core API to serve barcodes on demand.'
  type: HowTo
tags:
- barcode generation
- PDF417
- C#
title: Как сгенерировать штрих‑код PDF417 в C# с пользовательскими размерами
url: /ru/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-with-custom-dimensions/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Как генерировать штрих‑код PDF417 в C# с пользовательскими размерами

Если вам нужно **генерировать штрих‑код PDF417** в приложении .NET, это руководство покажет вам, как это сделать. Вы увидите полностью готовый, исполняемый пример, который создает PNG‑изображение и позволяет управлять размерами штрих‑кода.

Создание штрих‑кода PDF417 — распространённая задача для систем учёта, посадочных талонов и защищённых документов. В этом руководстве вы также узнаете **как задавать размеры штрих‑кода**, чтобы результат соответствовал требованиям вашего макета.

## Предварительные требования

- .NET 6.0 SDK или более поздняя версия  
- Visual Studio 2022 (или любая IDE, совместимая с C#)  
- Пакет NuGet **Aspose.BarCode for .NET** (или любая совместимая библиотека, поддерживающая PDF417)  

Вы можете добавить пакет следующей командой:

```bash
dotnet add package Aspose.BarCode
```

## Шаг 1: Создание генератора штрих‑кода PDF417

Первый шаг — создать экземпляр `BarcodeGenerator` с типом `EncodeTypes.Pdf417` и текстом, который вы хотите закодировать. Объект генератора хранит все настройки штрих‑кода.

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Step 1: Create a PDF417 barcode generator with the desired text
        BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
            EncodeTypes.Pdf417,
            "Åspóse.Barcóde©");
```

**Почему это важно:** Перечисление `EncodeTypes.Pdf417` указывает библиотеке использовать символьную схему PDF417, которая поддерживает большие объёмы данных и коррекцию ошибок. Строка текста может содержать символы Unicode, поэтому вы можете кодировать международные символы без дополнительной работы.

## Шаг 2: Как задать размеры штрих‑кода

Управление размером каждого модуля (самого маленького чёрно‑белого квадрата) определяет общую разрешающую способность изображения. Свойство `XDimension.Pixels` задаёт ширину одного модуля в пикселях.

```csharp
        // Step 2: Set the size of each barcode module (pixel resolution)
        barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

**Почему это важно:** Большое значение `XDimension` дает изображение с более высоким разрешением, что полезно для печати или сканирования с расстояния. Наоборот, меньшее значение уменьшает размер файла для веб‑использования.

## Шаг 3: Определение макета PDF417 (колонки и строки)

PDF417 позволяет влиять на форму матрицы, указывая количество колонок и строк. Это может влиять на читаемость и физический размер штрих‑кода.

```csharp
        // Step 3: Define the layout – number of columns and rows in the PDF417 matrix
        barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 4; // 4 columns
        barcodeGenerator.Parameters.Barcode.Pdf417.Rows    = 9; // 9 rows
```

**Почему это важно:** Настройка колонок и строк позволяет разместить штрих‑код в определённом пространстве или удовлетворить требования сканера к соотношению сторон. Библиотека автоматически добавляет отступы, если данные не заполняют матрицу полностью.

## Шаг 4: Сохранение штрих‑кода как PNG‑изображения

Наконец, запишите сгенерированный штрих‑код в файл. PNG сохраняет без потерь, что делает его идеальным для дальнейшей обработки.

```csharp
        // Step 4: Save the generated barcode as a PNG image
        barcodeGenerator.Save("Pdf417Layout.png", BarCodeImageFormat.Png);
    }
}
```

При запуске программы файл `Pdf417Layout.png` появляется в папке вывода проекта. Изображение выглядит так:

![Сгенерированное изображение штрих‑кода PDF417 с пользовательскими размерами](og_image_placeholder.png)

*Текст alt изображения: Сгенерированное изображение штрих‑кода PDF417 с пользовательскими размерами*  

**Почему это важно:** Сохранение в PNG гарантирует, что точные размеры модулей, которые вы задали, сохраняются, что критично для последующих приложений сканирования.

## Полный пример в одном блоке

Ниже приведена полная программа, которую вы можете скопировать, вставить и запустить без изменений (за исключением пути вывода, если это необходимо).

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Create a PDF417 barcode generator with the desired text
        BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
            EncodeTypes.Pdf417,
            "Åspóse.Barcóde©");

        // Set the size of each barcode module (pixel resolution)
        barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;

        // Define the layout – number of columns and rows in the PDF417 matrix
        barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 4; // 4 columns
        barcodeGenerator.Parameters.Barcode.Pdf417.Rows    = 9; // 9 rows

        // Save the generated barcode as a PNG image
        barcodeGenerator.Save("Pdf417Layout.png", BarCodeImageFormat.Png);
    }
}
```

### Ожидаемый результат

- **Файл:** `Pdf417Layout.png` (PNG, без потерь)  
- **Размеры:** Определяются `XDimension` (2 px) × (колонки × строки) матрица  
- **Содержимое:** Сканируемый штрих‑код PDF417, кодирующий Unicode‑строку `Åspóse.Barcóde©`

## Часто задаваемые вопросы и особые случаи

### Что делать, если нужен более крупный образ для печати?

Увеличьте `XDimension.Pixels` до 4 или 5. Большие значения дают штрих‑код с более высоким разрешением, но также увеличивают размер файла.

### Можно ли закодировать больше данных, чем в примере строки?

Да. PDF417 может хранить до 1 850 символов. Просто замените аргумент текста в конструкторе `BarcodeGenerator`. Если данные превышают ёмкость матрицы, библиотека автоматически добавит дополнительные строки.

### Как работает коррекция ошибок?

PDF417 включает встроенную коррекцию ошибок. Вы можете изменить её уровень с помощью:

```csharp
barcodeGenerator.Parameters.Barcode.Pdf417.ErrorLevel = 5; // 0‑8, higher = more correction
```

Более высокие уровни повышают надёжность, но увеличивают размер штрих‑кода.

### Что делать, если штрих‑код выглядит размытым на экране?

Убедитесь, что DPI выходного изображения соответствует среде отображения. Вы можете задать DPI при сохранении:

```csharp
barcodeGenerator.Save("Pdf417Layout.png", BarCodeImageFormat.Png, 300);
```

## Профессиональные советы

- **Профессиональный совет:** Всегда проверяйте сгенерированный штрих‑код на реальном сканере, который планируете использовать. Разные устройства имеют различную толерантность к размеру модуля и тихим зонам.  
- **Остерегайтесь:** Очень маленькие значения `XDimension` (< 1 px) могут отображаться как невидимые линии на экранах с высоким DPI.  
- **Совет для веб‑приложений:** Отдавайте PNG с заголовком `Cache-Control: public, max-age=86400`, чтобы уменьшить нагрузку от повторной генерации.

## Заключение

Теперь вы знаете, как **генерировать штрих‑код PDF417** в C# и точно **задавать размеры штрих‑кода**, чтобы соответствовать любым требованиям. Полный, исполняемый пример демонстрирует создание PNG‑изображения с пользовательским расположением колонок/строк и размером модуля, готового к печати или цифровому распространению.

### Следующие шаги

- Изучите **как генерировать штрих‑код PDF417** в разных форматах изображений (JPEG, BMP).  
- Узнайте **как задавать размеры штрих‑кода** динамически на основе ввода пользователя или DPI устройства.  
- Интегрируйте генерацию штрих‑кода в ASP.NET Core API для выдачи штрих‑кодов по запросу.

Не стесняйтесь экспериментировать с другими настройками PDF417, такими как коррекция ошибок, отступы и цвет. Приятного кодирования!

## Что изучать дальше?

Следующие руководства охватывают тесно связанные темы, которые опираются на техники, продемонстрированные в этом руководстве. Каждый ресурс включает полные рабочие примеры кода с пошаговыми объяснениями, чтобы помочь вам освоить дополнительные возможности API и исследовать альтернативные подходы к реализации в ваших проектах.

- [Как установить уровень ошибки в штрих‑коде PDF417 – Полное руководство](/barcode/english/net/compact-pdf417-encoding/how-to-set-error-level-in-pdf417-barcode-complete-guide/)
- [Как сохранить штрих‑код в C# – Генерация штрих‑кодов PDF417](/barcode/english/net/compact-pdf417-encoding/how-to-save-barcode-in-c-generate-pdf417-barcodes/)
- [Генерация штрих‑кода PDF417 в C# – Полное руководство](/barcode/english/net/compact-pdf417-encoding/generate-pdf417-barcode-in-c-complete-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}