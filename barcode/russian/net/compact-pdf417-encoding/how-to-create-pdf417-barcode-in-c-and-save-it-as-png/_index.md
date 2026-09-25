---
category: general
date: 2026-08-22
description: Узнайте, как создать штрих‑код PDF417 в C# с помощью генератора штрих‑кодов,
  настроить макет и сохранить PNG. Включает полный код и советы для проектов генератора
  штрих‑кодов на C#.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create PDF417 barcode
- barcode generator C#
- how to save PNG
- how to generate PDF417
language: ru
lastmod: 2026-08-22
og_description: Создайте штрих‑код PDF417 на C# с помощью генератора штрих‑кодов,
  настройте макет и узнайте, как сохранить PNG. Следуйте этому пошаговому руководству.
og_image_alt: Screenshot of a generated PDF417 barcode saved as a PNG file
og_title: Создание штрихкода PDF417 в C# — полное руководство по генерации и сохранению
  PNG
schemas:
- author: Aspose
  dateModified: '2026-08-22'
  description: Learn how to create PDF417 barcode in C# with a barcode generator,
    set layout, and save PNG. Includes full code and tips for barcode generator C#
    projects.
  headline: How to create PDF417 barcode in C# and save it as PNG
  type: TechArticle
tags:
- barcode
- C#
- PDF417
title: Как создать штрих‑код PDF417 в C# и сохранить его в формате PNG
url: /ru/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-in-c-and-save-it-as-png/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Как создать PDF417 barcode в C# и сохранить его как PNG

Если вам нужно **create PDF417 barcode** в приложении C#, этот учебник покажет вам точные шаги. Вы увидите, как библиотека barcode generator C# может преобразовать любую строку в сканируемое изображение PDF417 и как сохранить PNG‑файлы без дополнительных инструментов.

Создание штрих‑кодов широко используется в логистике, билетных системах и управлении документами. К концу этого руководства у вас будет рабочая консольная программа, которая создаст PNG‑файл с именем `Pdf417Layout.png` в выбранной вами папке.

## Prerequisites

Прежде чем начать, убедитесь, что у вас есть:

- .NET 6.0 SDK или более поздняя версия (код также работает с .NET Framework 4.7+).
- Visual Studio 2022 или любой редактор, способный собирать проекты C#.
- Пакет NuGet **Aspose.BarCode for .NET** (или любая совместимая barcode generator C# library).  
  Установите его с помощью:

```bash
dotnet add package Aspose.BarCode
```

Дополнительные библиотеки для обработки изображений не требуются, поскольку генератор может записывать PNG напрямую.

## Step 1: Set up a new console project

Создайте новый консольный проект, чтобы пример оставался автономным.

```bash
dotnet new console -n Pdf417Demo
cd Pdf417Demo
dotnet add package Aspose.BarCode
```

Папка `Pdf417Demo` теперь содержит файл `Program.cs`, в который мы добавим код генерации штрих‑кода.

## Step 2: Import the barcode namespace

Откройте `Program.cs` и добавьте необходимую директиву `using` в начале файла:

```csharp
using Aspose.BarCode.Generation;
```

Это пространство имён предоставляет доступ к `BarcodeGenerator`, `EncodeTypes` и перечислению форматов изображений, необходимому для **how to save PNG**.

## Step 3: Create the PDF417 barcode generator

Ядром **how to generate PDF417** является класс `BarcodeGenerator`. Передайте тип кодирования `EncodeTypes.Pdf417` и текст, который нужно закодировать.

```csharp
// Step 3: Create a PDF417 barcode generator with the desired text
BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Sample");
```

`generator` теперь содержит все настройки штрих‑кода. По умолчанию макет работает, но мы настроим его в следующем шаге.

## Step 4: Define the barcode layout (columns and rows)

PDF417 позволяет управлять количеством столбцов (2‑30) и строк (1‑90). Настройка этих значений может улучшить читаемость для конкретных сканеров.

```csharp
// Step 4a: Set the number of columns (2‑30 allowed)
generator.Parameters.Barcode.Pdf417.Columns = 4;

// Step 4b: Set the number of rows (1‑90 allowed)
generator.Parameters.Barcode.Pdf417.Rows = 9;
```

> **Pro tip:** Если опустить эти настройки, библиотека автоматически выберет оптимальные значения. Однако фиксированные столбцы и строки дают предсказуемые размеры изображения, что удобно при встраивании PNG в PDF или пользовательский интерфейс.

## Step 5: Save the generated barcode as a PNG image

Теперь ответьте на **how to save PNG**, вызвав `Save`. Метод принимает целевой путь и перечисление формата изображения.

```csharp
// Step 5: Save the generated barcode as a PNG image
string outputPath = Path.Combine(Environment.CurrentDirectory, "Pdf417Layout.png");
generator.Save(outputPath, BarCodeImageFormat.Png);
Console.WriteLine($"PDF417 barcode saved to: {outputPath}");
```

Файл `Pdf417Layout.png` появится в папке проекта `bin/Debug/net6.0` после выполнения программы.

## Full runnable example

Ниже приведён полный файл `Program.cs`. Скопируйте его в проект, созданный в **Step 1**, и запустите `dotnet run`.

```csharp
using System;
using System.IO;
using Aspose.BarCode.Generation;

namespace Pdf417Demo
{
    class Program
    {
        static void Main(string[] args)
        {
            // 1️⃣ Create a PDF417 barcode generator with the desired text
            BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Sample");

            // 2️⃣ Define the barcode layout – set columns (2‑30) and rows (1‑90)
            generator.Parameters.Barcode.Pdf417.Columns = 4; // 4 columns
            generator.Parameters.Barcode.Pdf417.Rows = 9;    // 9 rows

            // 3️⃣ Choose the output path and save as PNG
            string outputPath = Path.Combine(
                Environment.CurrentDirectory,
                "Pdf417Layout.png");

            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"✅ PDF417 barcode created and saved as PNG at:");
            Console.WriteLine(outputPath);
        }
    }
}
```

### Expected output

При запуске программы консоль выведет абсолютный путь к PNG‑файлу, а файл будет содержать чёткий штрих‑код PDF417, похожий на изображение ниже.

![пример создания PDF417 barcode](image-placeholder.png "Штрих‑код PDF417, сохранённый как PNG")

Вы можете отсканировать PNG любым совместимым сканером PDF417 (мобильные приложения, аппаратные считыватели), чтобы убедиться, что закодированный текст — `"Sample"`.

## Handling edge cases and common pitfalls

| Ситуация | На что обратить внимание | Рекомендуемое решение |
|-----------|--------------------------|-----------------------|
| **Недопустимые значения столбцов/строк** | Значения вне диапазона 2‑30 (столбцы) или 1‑90 (строки) вызывают `ArgumentException`. | Проверяйте ввод пользователя перед присвоением или позволяйте библиотеке выбирать значения по умолчанию. |
| **Большие входные строки** | PDF417 может кодировать до 1 850 символов, но очень длинные строки резко увеличивают количество требуемых строк. | Разделите данные на несколько штрих‑кодов или используйте более высокий уровень коррекции ошибок при необходимости. |
| **Разрешения файловой системы** | Сохранение в папку только для чтения приводит к `UnauthorizedAccessException`. | Записывайте в `Environment.CurrentDirectory` или в путь, доступный пользователю, и обрабатывайте исключения с помощью try/catch. |
| **Отсутствует пакет NuGet** | Компиляция завершается ошибкой «type or namespace name could not be found». | Убедитесь, что установлен `Aspose.BarCode` (`dotnet add package Aspose.BarCode`). |

## Extending the example

Теперь, когда вы знаете **how to create PDF417 barcode** и **how to save PNG**, вы можете изучить связанные темы:

- **Barcode generator C#**: измените `EncodeTypes` на `Code128`, `QR` или другие символьные наборы.
- **Custom colors**: используйте `generator.Parameters.Barcode.ForegroundColor` и `BackgroundColor`, чтобы подобрать цвета под фирменный стиль.
- **Embedding in PDFs**: объедините PNG с библиотекой PDF (например, iText7), чтобы создавать печатные документы.
- **Dynamic data**: получайте текст из базы данных или ввода пользователя для генерации штрих‑кодов «на лету».

## Conclusion

Теперь у вас есть полное, готовое к использованию решение для **create PDF417 barcode** в C# и сохранения результата в PNG‑файл. Руководство охватило каждый шаг от настройки проекта до настройки макета и показало, как избежать типичных ошибок при работе с barcode generator C# library.

Экспериментируйте с различными настройками столбцов/строк, цветами или даже другими форматами штрих‑кодов. Если возникнут проблемы, вернитесь к разделу **how to generate PDF417** или изучите документацию библиотеки для продвинутых возможностей. Приятного кодинга!

## What Should You Learn Next?

Следующие учебники охватывают тесно связанные темы, которые развивают техники, продемонстрированные в этом руководстве. Каждый ресурс включает полностью работающие примеры кода с пошаговыми объяснениями, чтобы помочь вам освоить дополнительные возможности API и исследовать альтернативные подходы в собственных проектах.

- [Как создать штрих‑код – Compact PDF417 с Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [Как генерировать штрих‑код PDF417 – Compact PDF417 Encoding](/barcode/english/net/compact-pdf417-encoding/)
- [Как создать Quiet Zone для штрих‑кода ITF-14 с использованием Aspose.BarCode для .NET](/barcode/english/net/itf-14-barcode-customization/itf-14-barcode-quiet-zone-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}