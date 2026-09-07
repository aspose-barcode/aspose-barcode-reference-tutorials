---
category: general
date: 2026-09-07
description: Узнайте, как генерировать микро‑PDF417 штрих‑код в C# с полным примером
  кода, настройкой X‑размера, конфигурацией колонок и экспортом в PNG.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate micro pdf417 barcode
- C# barcode generator
- MicroPdf417 encode type
- barcode X-dimension
- barcode column configuration
- save barcode as PNG
language: ru
lastmod: 2026-09-07
og_description: Создайте микробаркод PDF417 в C# с помощью этого краткого руководства.
  Включает настройки X‑размера, выбор колонок и экспорт в PNG для мгновенного использования.
og_image_alt: Screenshot showing a generated micro pdf417 barcode saved as a PNG file
og_title: Генерация микробарcode PDF417 в C# — полное руководство по программированию
schemas:
- author: Aspose
  dateModified: '2026-09-07'
  description: Learn how to generate micro pdf417 barcode in C# with a complete code
    example, X‑dimension tuning, column configuration, and PNG export.
  headline: How to generate micro pdf417 barcode in C# – step‑by‑step guide
  type: TechArticle
tags:
- barcode
- C#
- MicroPdf417
- image export
title: Как сгенерировать микро‑PDF417 штрих‑код в C# — пошаговое руководство
url: /ru/net/compact-pdf417-encoding/how-to-generate-micro-pdf417-barcode-in-c-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Как сгенерировать micro pdf417 barcode в C# – пошаговое руководство

Если вам нужно **сгенерировать micro pdf417 barcode** в .NET‑приложении, этот учебник покажет готовое решение, готовое к запуску. Вы увидите, как настроить X‑размер штрих‑кода, выбрать количество колонок и экспортировать результат в виде PNG‑изображения — всё с помощью библиотеки Aspose.BarCode C#.

Генерация micro pdf417 barcode часто требуется, когда необходимо закодировать компактные данные для мобильных билетов, меток инвентаря или защищённых документов. К концу этого руководства у вас будет переиспользуемый фрагмент кода, который можно вставить в любой проект на C#.

## Prerequisites

Прежде чем начать, убедитесь, что у вас есть:

* .NET 6.0 или новее (код также работает с .NET Framework 4.7+)
* Visual Studio 2022 (или любой IDE, поддерживающий C#)
* NuGet‑пакет **Aspose.BarCode for .NET** (версия 23.9 или новее)

Пакет можно установить из командной строки:

```bash
dotnet add package Aspose.BarCode
```

Дополнительные зависимости не требуются.

## Step 1: Create a barcode generator for MicroPdf417

Первой задачей является создание экземпляра `BarcodeGenerator` с перечислением `EncodeTypes.MicroPdf417` и текстом, который вы хотите закодировать. Текст может содержать Unicode‑символы, библиотека обрабатывает их автоматически.

```csharp
using Aspose.BarCode.Generation;

// Step 1: Create a barcode generator for MicroPdf417 with the desired text
BarcodeGenerator generator = new BarcodeGenerator(
    EncodeTypes.MicroPdf417,
    "Åspóse.Barcóde©"
);
```

**Почему это важно:**  
`EncodeTypes.MicroPdf417` указывает библиотеке использовать компактную символьную систему MicroPdf417, которая хранит больше данных в меньшем пространстве, чем полный PDF417. Передача текста при создании гарантирует, что генератор точно знает, что нужно закодировать.

## Step 2: Adjust the X‑dimension for finer resolution

X‑размер (ширина модуля) определяет, сколько пикселей занимает каждый столбец штрих‑кода. Значение **2 пикселя** даёт высокое разрешение, при котором штрих‑код остаётся читаемым большинством сканеров.

```csharp
// Step 2: Set the X‑dimension (module width) to 2 pixels for finer resolution
generator.Parameters.Barcode.XDimension.Pixels = 2;
```

**Pro tip:**  
Если вы нацелены на низкоразрешающие дисплеи или принтеры, увеличьте значение до 3‑4 пикселей, чтобы избежать размытия краёв. И наоборот, для этикеток высокой плотности можно уменьшить до 1 пикселя, но обязательно протестируйте результат со своим сканером.

## Step 3: Choose the number of columns

MicroPdf417 поддерживает **от 1 до 4 колонок**. Большее количество колонок делает штрих‑код короче, но уменьшает ёмкость коррекции ошибок. Для большинства сценариев билетов **4 колонки** обеспечивают компактную форму при сохранении надёжности.

```csharp
// Step 3: Choose the number of columns (1‑4 are allowed) to control barcode size
generator.Parameters.Barcode.Pdf417.Columns = 4;
```

**Почему вы можете изменить это:**  
Если закодированный текст превышает ёмкость по умолчанию, увеличьте количество колонок, чтобы избежать ошибок переполнения. Уменьшайте его, когда нужен узкий штрих‑код из‑за ограниченного пространства.

## Step 4: Define the output folder and file name

Выберите папку, в которой будет сохранено сгенерированное изображение. Использование `Path.Combine` гарантирует правильные разделители пути в Windows, Linux и macOS.

```csharp
using System.IO;

// Step 4: Define the output folder and file name
string outputFolder = Path.Combine(
    Environment.GetFolderPath(Environment.SpecialFolder.Desktop),
    "Barcodes"
);
Directory.CreateDirectory(outputFolder); // Ensure the folder exists
string outputPath = Path.Combine(outputFolder, "MicroPdf417.png");
```

**Обработка граничных случаев:**  
Если путь к папке недействителен или приложение не имеет прав на запись, `Directory.CreateDirectory` бросит исключение. Оберните логику сохранения в блок `try/catch` для продакшн‑кода.

## Step 5: Save the barcode as a PNG image

Наконец, экспортируйте штрих‑код в PNG‑файл. PNG сохраняет резкие края и поддерживает прозрачность, что делает его идеальным для отображения в UI или печати.

```csharp
using Aspose.BarCode;

// Step 5: Save the generated barcode as a PNG image
generator.Save(outputPath, BarCodeImageFormat.Png);
```

После выполнения вы найдёте **MicroPdf417.png** в папке `Barcodes` на рабочем столе. Открытие файла покажет чёткий, высоко‑разрешающий micro pdf417 barcode, готовый к сканированию.

### Expected output

Сохранённое изображение выглядит примерно как на иллюстрации ниже (реальный шаблон зависит от закодированного текста).

![Сгенерированный micro pdf417 barcode, сохранённый как PNG](https://example.com/placeholder-micro-pdf417.png "Скриншот сгенерированного micro pdf417 barcode, сохранённого в PNG‑файле")

*Alt text:* сгенерированный micro pdf417 barcode, сохранённый как PNG‑изображение

## Full, runnable example

Объединив все шаги, получаем единый, самодостаточный пример программы:

```csharp
using System;
using System.IO;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // 1️⃣ Create generator with MicroPdf417 and Unicode text
        BarcodeGenerator generator = new BarcodeGenerator(
            EncodeTypes.MicroPdf417,
            "Åspóse.Barcóde©"
        );

        // 2️⃣ Set X‑dimension for high‑resolution output
        generator.Parameters.Barcode.XDimension.Pixels = 2;

        // 3️⃣ Choose 4 columns to keep the barcode compact
        generator.Parameters.Barcode.Pdf417.Columns = 4;

        // 4️⃣ Prepare output folder on the desktop
        string outputFolder = Path.Combine(
            Environment.GetFolderPath(Environment.SpecialFolder.Desktop),
            "Barcodes"
        );
        Directory.CreateDirectory(outputFolder);
        string outputPath = Path.Combine(outputFolder, "MicroPdf417.png");

        // 5️⃣ Save as PNG
        generator.Save(outputPath, BarCodeImageFormat.Png);

        Console.WriteLine($"Barcode saved to: {outputPath}");
    }
}
```

Запустите программу (`dotnet run` из папки проекта) и убедитесь, что PNG‑файл появился как ожидалось.

## Common questions and troubleshooting

| Question | Answer |
|----------|--------|
| **Can I generate the barcode as JPEG instead of PNG?** | Да. Замените `BarCodeImageFormat.Png` на `BarCodeImageFormat.Jpeg`. JPEG сжимает изображение, но может добавить артефакты, влияющие на читаемость сканером. |
| **What if the text contains characters not supported by MicroPdf417?** | MicroPdf417 поддерживает полный диапазон Unicode. Если вы получаете `ArgumentException`, проверьте правильность кодировки строки (например, избегайте суррогатных пар, превышающих ёмкость символа). |
| **How do I change the foreground color?** | Используйте `generator.Parameters.Barcode.BarColor = Color.Blue;` перед вызовом `Save`. |
| **Is there a way to embed the barcode directly into a PDF?** | Да. Вызовите `generator.Save(stream, BarCodeImageFormat.Pdf);` или добавьте изображение в PDF‑документ с помощью библиотеки, такой как Aspose.PDF. |
| **My scanner cannot read the barcode—what should I check?** | Убедитесь, что X‑размер минимум 2 пикселя для большинства сканеров, проверьте, что количество колонок соответствует поддерживаемому диапазону сканера, и подтвердите, что напечатанный размер удовлетворяет минимальному размеру модуля сканера (обычно 0.5 мм). |

## Conclusion

Теперь вы знаете, как **сгенерировать micro pdf417 barcode** в C# от начала до конца. Руководство охватывало создание `BarcodeGenerator`, настройку X‑размера и количества колонок, подготовку пути вывода и сохранение результата в PNG. Регулируя дополнительные параметры — такие как цвет штрихов, формат изображения или уровень коррекции ошибок — вы сможете адаптировать штрих‑код под любые задачи, от мобильных билетов до меток инвентаря.

### Next steps

* Поэкспериментируйте с **значениями X‑размера** штрих‑кода, чтобы найти баланс между размером и читаемостью.  
* Исследуйте другие символьные системы (например, `EncodeTypes.Pdf417`, `EncodeTypes.QR`) с тем же шаблоном генератора.  
* Интегрируйте сгенерированный PNG в PDF‑отчёт с помощью **Aspose.PDF** или внедрите его напрямую в UI WinForms/WPF.  

Happy coding, and enjoy the flexibility that the Aspose.BarCode library brings to barcode generation in C#!

## What Should You Learn Next?

Следующие учебники охватывают тесно связанные темы, которые развивают техники, продемонстрированные в этом руководстве. Каждый ресурс включает полностью работающие примеры кода с пошаговыми объяснениями, чтобы помочь вам освоить дополнительные возможности API и исследовать альтернативные подходы в собственных проектах.

- [Barcode Generator Tutorial: How to Generate PDF417 Barcode in C#](/barcode/english/net/compact-pdf417-encoding/barcode-generator-tutorial-how-to-generate-pdf417-barcode-in/)
- [How to Save Barcode in C# – Generate PDF417 Barcodes](/barcode/english/net/compact-pdf417-encoding/how-to-save-barcode-in-c-generate-pdf417-barcodes/)
- [How to Generate PDF417 Barcode – Complete Programming Guide](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-complete-programming-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}