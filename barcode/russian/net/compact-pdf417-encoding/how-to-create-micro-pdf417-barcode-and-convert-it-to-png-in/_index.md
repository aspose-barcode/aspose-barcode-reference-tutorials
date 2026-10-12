---
category: general
date: 2026-10-12
description: Научитесь создавать микробаркод PDF417 и преобразовывать его в PNG с
  помощью C#. Пошаговое руководство с полным кодом и советами.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create micro PDF417 barcode
- convert barcode to PNG
- micro PDF417 C# example
- GS1 micro PDF417 generation
- barcode image settings
language: ru
lastmod: 2026-10-12
og_description: Создайте микро‑PDF417 штрих‑код и преобразуйте его в PNG с помощью
  C#. Следуйте этому полному руководству, чтобы сгенерировать как стандартные, так
  и версии GS1.
og_image_alt: Screenshot of a generated micro PDF417 barcode saved as a PNG file
og_title: Создание микро‑PDF417 штрих‑кода и преобразование его в PNG – учебник C#
schemas:
- author: Aspose
  dateModified: '2026-10-12'
  description: Learn to create micro PDF417 barcode and convert barcode to PNG using
    C#. Step‑by‑step guide with full code and tips.
  headline: How to create micro PDF417 barcode and convert it to PNG in C#
  type: TechArticle
tags:
- barcode
- C#
- PDF417
title: Как создать микро‑PDF417 штрих‑код и преобразовать его в PNG в C#
url: /ru/net/compact-pdf417-encoding/how-to-create-micro-pdf417-barcode-and-convert-it-to-png-in/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Как создать micro PDF417 barcode и конвертировать его в PNG на C#

Если вам нужно **create micro PDF417 barcode** в приложении .NET, этот учебник покажет вам точно как. Вы увидите полностью готовый, исполняемый пример, который генерирует как стандартный Micro PDF417 barcode, так и версию, соответствующую GS1, а затем **convert barcode to PNG** для дальнейшего использования, например, печати или отображения в вебе.

Создание штрих‑кода — это больше, чем вызов одной функции: выбор правильного размера модуля, количества столбцов и формата кодирования определяет надёжность сканирования. К концу этого руководства вы поймёте, почему каждое из этих настроек важно и как их адаптировать под свои проекты.

## Prerequisites

Before you start, make sure you have:

| Requirement | Reason |
|-------------|--------|
| .NET 6.0 SDK or later | Предоставляет среду выполнения для консольного приложения C# |
| Visual Studio 2022 (or any C# IDE) | Обеспечивает более удобное редактирование и отладку |
| **Aspose.BarCode for .NET** NuGet package | Содержит классы `BarcodeGenerator`, `EncodeTypes` и `BarCodeImageFormat` |
| Write permission to the output folder | Необходимо для вызовов `Save`, которые создают PNG‑файлы |

You can add the Aspose.BarCode package via the CLI:

```bash
dotnet add package Aspose.BarCode
```

## Step 1: Set up a minimal console project

Create a new console project and reference the barcode library. The following `Program.cs` contains all the code you need; no external files are required.

```csharp
using System;
using Aspose.BarCode.Generation;   // Core barcode generation classes
using Aspose.BarCode;               // For BarCodeImageFormat enum

namespace MicroPdf417Demo
{
    internal class Program
    {
        static void Main()
        {
            // Define the folder where PNG files will be saved
            string outputFolder = Environment.CurrentDirectory;

            // ------------------------------------------------------------
            // 1️⃣ Create a Micro PDF417 barcode generator with plain data
            // ------------------------------------------------------------
            BarcodeGenerator microGen = new BarcodeGenerator(
                EncodeTypes.MicroPdf417,          // Micro PDF417 symbology
                "Micro data");                    // Simple alphanumeric payload

            // ------------------------------------------------------------
            // 2️⃣ Adjust the X dimension (module size) and set column count
            // ------------------------------------------------------------
            // XDimension controls the physical size of each barcode module.
            // A value of 2 pixels gives a compact yet readable barcode.
            microGen.Parameters.Barcode.XDimension.Pixels = 2;

            // For Micro PDF417 you can limit the number of columns.
            // Four columns keep the barcode small enough for labels.
            microGen.Parameters.Barcode.Pdf417.Columns = 4;

            // ------------------------------------------------------------
            // 3️⃣ Convert barcode to PNG and save the image
            // ------------------------------------------------------------
            string microPath = System.IO.Path.Combine(outputFolder, "MicroPdf417.png");
            microGen.Save(microPath, BarCodeImageFormat.Png);
            Console.WriteLine($"Standard Micro PDF417 saved to: {microPath}");

            // ------------------------------------------------------------
            // 4️⃣ Create a GS1 Micro PDF417 barcode with AI‑encoded data
            // ------------------------------------------------------------
            // GS1 syntax requires Application Identifiers (AIs) wrapped in parentheses.
            // Example: (01) – GTIN, (21) – serial number.
            BarcodeGenerator gs1MicroGen = new BarcodeGenerator(
                EncodeTypes.Gs1MicroPdf417,
                "(01)12345678901231(21)ABC123");

            // ------------------------------------------------------------
            // 5️⃣ Set the X dimension for the GS1 barcode (same as step 2)
            // ------------------------------------------------------------
            gs1MicroGen.Parameters.Barcode.XDimension.Pixels = 2;

            // ------------------------------------------------------------
            // 6️⃣ Convert barcode to PNG and save the GS1 image
            // ------------------------------------------------------------
            string gs1Path = System.IO.Path.Combine(outputFolder, "GS1MicroPdf417.png");
            gs1MicroGen.Save(gs1Path, BarCodeImageFormat.Png);
            Console.WriteLine($"GS1 Micro PDF417 saved to: {gs1Path}");

            // End of demo
            Console.WriteLine("Barcode generation complete.");
        }
    }
}
```

### Why each line matters

* **`EncodeTypes.MicroPdf417` vs `EncodeTypes.Gs1MicroPdf417`** – Первый создаёт обычный Micro PDF417 barcode, а второй соответствует стандарту GS1, внедряя идентификаторы приложений (AIs). Выбирайте в зависимости от того, ожидает ли ваша downstream‑система данные GS1.
* **`XDimension.Pixels = 2`** – Управляет шириной модуля. Меньшие значения делают изображение плотнее, но могут стать нечитаемыми на сканерах с низким разрешением. Два пикселя — безопасный вариант для большинства принтеров этикеток.
* **`Pdf417.Columns = 4`** – Micro PDF417 позволяет ограничить количество столбцов, уменьшая общую ширину. Четыре столбца сохраняют компактность штрих‑кода без потери ёмкости данных для небольших полезных нагрузок.
* **`BarCodeImageFormat.Png`** – PNG сохраняет без потерь, что критично для чёткости штрих‑кода. Поэтому мы **convert barcode to PNG**, а не в JPEG.

## Step 2: Run the program and verify the output

1. Build the project: `dotnet build`.
2. Execute: `dotnet run`.

You should see console messages similar to:

```
Standard Micro PDF417 saved to: C:\Path\To\Project\MicroPdf417.png
GS1 Micro PDF417 saved to: C:\Path\To\Project\GS1MicroPdf417.png
Barcode generation complete.
```

Откройте сгенерированные PNG‑файлы в любом просмотрщике изображений. Оба изображения показывают чёткий, контрастный штрих‑код, готовый к сканированию.

### Expected visual result

| Barcode type | Appearance |
|--------------|------------|
| **Micro PDF417** | Маленький прямоугольный узор с 4 столбцами, читаемый большинством 2‑D сканеров. |
| **GS1 Micro PDF417** | Тот же размер, но кодирует GS1 AIs; сканер, поддерживающий GS1, вернёт GTIN и серийный номер. |

Если сканер не может прочитать изображение, попробуйте увеличить `XDimension.Pixels` до **3** или **4**, либо уменьшить количество столбцов для стандартного Micro PDF417.

## Common pitfalls and how to avoid them

| Issue | Cause | Fix |
|-------|-------|-----|
| Blurry barcode after printing | Low DPI printer settings | Export PNG at 300 dpi or higher, or let the printer driver handle scaling. |
| Scanner returns “invalid data” | Missing or malformed GS1 AI format | Ensure every AI is wrapped in parentheses and follows the GS1 specification (e.g., `(01)` for GTIN‑14). |
| Image file not created | Output folder lacks write permission | Run the program with elevated rights or choose a folder like `Environment.GetFolderPath(Environment.SpecialFolder.MyDocuments)`. |
| Barcode too large for label | Default column count too high | Reduce `Pdf417.Columns` (e.g., to **3**) or increase `XDimension` to shrink overall size. |

## Extending the example

* **Different image formats** – Replace `BarCodeImageFormat.Png` with `Jpeg` or `Bmp` if your workflow requires them. PNG remains the best choice for lossless quality.
* **Dynamic data** – Pass user input or database values to the `BarcodeGenerator` constructor to create barcodes on the fly.
* **Batch generation** – Wrap the creation logic in a loop that reads rows from a CSV file and saves each barcode with a unique filename.

## Conclusion

You now know how to **create micro PDF417 barcode** in C# and **convert barcode to PNG** for both standard and GS1‑compliant scenarios. The complete, runnable code demonstrates the essential settings—X dimension, column count, and encoding type—so you can adapt the solution to any .NET project that needs compact, high‑quality 2‑D barcodes.

*Next steps*: explore other symbologies supported by Aspose.BarCode (e.g., QR, DataMatrix), experiment with different `XDimension` values for high‑resolution printing, or integrate the generated PNGs into a web API that serves barcodes on demand.

## What Should You Learn Next?

The following tutorials cover closely related topics that build on the techniques demonstrated in this guide. Each resource includes complete working code examples with step-by-step explanations to help you master additional API features and explore alternative implementation approaches in your own projects.

- [Как создать micro pdf417 barcode в C# и сохранить его как PNG](/barcode/english/net/compact-pdf417-encoding/how-to-create-micro-pdf417-barcode-in-c-and-save-it-as-png/)
- [Создать barcode PNG в C# – полное руководство по GS1 Micro PDF417](/barcode/english/net/gs1-barcode-encoding/create-barcode-png-in-c-full-guide-to-gs1-micro-pdf417/)
- [Генерировать Micro PDF417 Barcode в C# – Полное руководство](/barcode/english/net/compact-pdf417-encoding/generate-micro-pdf417-barcode-in-c-complete-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}