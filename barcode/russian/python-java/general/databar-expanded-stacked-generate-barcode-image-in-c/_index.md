---
category: general
date: 2026-08-15
description: Databar расширил генерацию штабелируемых штрих‑кодов в C#. Узнайте, как
  создать изображение штрих‑кода, задать столбцы и строки для макетов DataBar.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- databar expanded stacked
- generate barcode image
- how to generate barcode
- how to set columns
- how to set rows
language: ru
lastmod: 2026-08-15
og_description: Databar расширил генерацию наложенных штрих‑кодов в C#. Следуйте этому
  пошаговому руководству, чтобы эффективно генерировать изображения штрих‑кодов, задавать
  столбцы и строки.
og_image_alt: Screenshot of a databar expanded stacked barcode generated with C#
og_title: Databar expanded stacked – создание изображения штрихкода в C#
schemas:
- author: Aspose
  dateModified: '2026-08-15'
  description: Databar expanded stacked barcode generation in C#. Learn how to generate
    barcode image, set columns and rows for DataBar layouts.
  headline: 'Databar expanded stacked: generate barcode image in C#'
  type: TechArticle
- description: Databar expanded stacked barcode generation in C#. Learn how to generate
    barcode image, set columns and rows for DataBar layouts.
  name: 'Databar expanded stacked: generate barcode image in C#'
  steps:
  - name: 1. Install the Aspose.BarCode library
    text: 'The code uses the **Aspose.BarCode for .NET** library, which provides the
      `BarcodeGenerator` class. Install the NuGet package with the following command:'
  - name: 2. Create a barcode generator for **databar expanded stacked**
    text: The generator is the entry point for all barcode operations. You must specify
      the symbology (`EncodeTypes.DatabarExpandedStacked`) and the text to encode.
  - name: 3. How to set columns for DataBar
    text: The `Columns` property controls how many vertical modules appear in the
      stacked barcode. Valid values are 2, 3, or 4. Setting columns influences the
      barcode’s width and the amount of data it can store.
  - name: 4. Save the 4‑column barcode image
    text: Saving the image produces a file that you can embed in reports, invoices,
      or mobile apps. The `Save` method accepts a file path and an image format.
  - name: 5. How to set rows for DataBar
    text: Rows add a second dimension to the stacked layout, allowing more data to
      be encoded without widening the barcode. The `Rows` property defaults to 1;
      you can increase it up to 3 for the expanded stacked variant.
  - name: 6. Save the 3‑row barcode image
    text: '```csharp // Step 5: Save the 3‑row barcode image barcode.Save("YOUR_DIRECTORY/DatabarRows3.png",
      BarCodeImageFormat.Png); ```'
  - name: 7. Complete C# example to generate barcode image
    text: 'Putting all steps together yields a self‑contained program you can copy
      into a console application:'
  type: HowTo
tags:
- barcode
- C#
- Aspose.BarCode
title: 'Databar expanded stacked: создать изображение штрихкода в C#'
url: /ru/python-java/general/databar-expanded-stacked-generate-barcode-image-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Databar expanded stacked: generate barcode image in C#

Если вам нужно сгенерировать изображение штрих‑кода **databar expanded stacked** в C#, это руководство покажет, **как генерировать штрих‑коды** с пользовательскими расположениями столбцов и строк. Вы увидите, как задать столбцы, как задать строки и как сохранить полученные изображения, не выходя из IDE.

В руководстве рассматривается:

* Создание генератора штрих‑кода для символьного набора **databar expanded stacked**.  
* Настройка макета из 4 столбцов и 3 строк.  
* Сохранение каждой конфигурации в файл PNG.  
* Советы по обработке граничных случаев, таких как неверное количество столбцов.

Внешняя документация не требуется; полный, готовый к запуску пример включён.

![Databar expanded stacked barcode example](YOUR_DIRECTORY/DatabarCols4.png){: .center alt="датабар расширенный штабелированный штрих‑код, сгенерированный с помощью C#" }

## Databar expanded stacked barcode generation steps

### 1. Install the Aspose.BarCode library

The code uses the **Aspose.BarCode for .NET** library, which provides the `BarcodeGenerator` class. Install the NuGet package with the following command:

```bash
dotnet add package Aspose.BarCode
```

After the package is installed, add the required namespace at the top of your file:

```csharp
using Aspose.BarCode.Generation;
```

### 2. Create a barcode generator for **databar expanded stacked**

The generator is the entry point for all barcode operations. You must specify the symbology (`EncodeTypes.DatabarExpandedStacked`) and the text to encode.

```csharp
// Step 1: Create a barcode generator for Databar Expanded Stacked
BarcodeGenerator barcode = new BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked,
    "Databar Expanded Stacked long");
```

*Why this matters:* The `EncodeTypes` enum tells the library which barcode format to produce. Using **databar expanded stacked** ensures the resulting image follows the GS1 DataBar specification for stacked layouts.

### 3. How to set columns for DataBar

The `Columns` property controls how many vertical modules appear in the stacked barcode. Valid values are 2, 3, or 4. Setting columns influences the barcode’s width and the amount of data it can store.

```csharp
// Step 2: Configure a 4‑column layout
barcode.Parameters.Barcode.DataBar.Columns = 4;
```

**Tip:** If you attempt to assign a value outside the allowed range, the library throws an `ArgumentException`. Always validate input when exposing column selection to users.

### 4. Save the 4‑column barcode image

Saving the image produces a file that you can embed in reports, invoices, or mobile apps. The `Save` method accepts a file path and an image format.

```csharp
// Step 3: Save the 4‑column barcode image
barcode.Save("YOUR_DIRECTORY/DatabarCols4.png", BarCodeImageFormat.Png);
```

When the file is written, you can open it with any image viewer to confirm that the **databar expanded stacked** pattern appears correctly.

### 5. How to set rows for DataBar

Rows add a second dimension to the stacked layout, allowing more data to be encoded without widening the barcode. The `Rows` property defaults to 1; you can increase it up to 3 for the expanded stacked variant.

```csharp
// Step 4: Switch to a 3‑row layout (columns remain unchanged)
barcode.Parameters.Barcode.DataBar.Rows = 3;
```

**Why rows matter:** Increasing rows reduces the overall width while preserving data capacity, which is useful for narrow labels or mobile screen space.

### 6. Save the 3‑row barcode image

```csharp
// Step 5: Save the 3‑row barcode image
barcode.Save("YOUR_DIRECTORY/DatabarRows3.png", BarCodeImageFormat.Png);
```

You now have two PNG files—one with a 4‑column layout and another with a 3‑row layout—both using the **databar expanded stacked** symbology.

### 7. Complete C# example to generate barcode image

Putting all steps together yields a self‑contained program you can copy into a console application:

```csharp
using System;
using Aspose.BarCode.Generation;

namespace DatabarExpandedStackedDemo
{
    class Program
    {
        static void Main()
        {
            // Create the generator for Databar Expanded Stacked
            BarcodeGenerator barcode = new BarcodeGenerator(
                EncodeTypes.DatabarExpandedStacked,
                "Databar Expanded Stacked long");

            // Configure a 4‑column layout and save
            barcode.Parameters.Barcode.DataBar.Columns = 4;
            barcode.Save("YOUR_DIRECTORY/DatabarCols4.png", BarCodeImageFormat.Png);
            Console.WriteLine("4‑column barcode saved.");

            // Change to a 3‑row layout (columns stay at 4) and save
            barcode.Parameters.Barcode.DataBar.Rows = 3;
            barcode.Save("YOUR_DIRECTORY/DatabarRows3.png", BarCodeImageFormat.Png);
            Console.WriteLine("3‑row barcode saved.");
        }
    }
}
```

**Expected output**

Running the program prints:

```
4‑column barcode saved.
3‑row barcode saved.
```

and creates two PNG files in `YOUR_DIRECTORY`. Open the files to verify that each image displays a valid **databar expanded stacked** barcode.

## Common pitfalls and practical tips

* **Directory existence** – `Save` does not create missing folders. Ensure `YOUR_DIRECTORY` exists or use `Directory.CreateDirectory` before saving.
* **Column limits** – Values other than 2, 3, or 4 trigger an exception. Guard against user input errors with a simple range check:

  ```csharp
  int columns = 4;
  if (columns < 2 || columns > 4) throw new ArgumentOutOfRangeException(nameof(columns));
  barcode.Parameters.Barcode.DataBar.Columns = columns;
  ```

* **Row limits** – The expanded stacked variant supports up to 3 rows. Setting `Rows` to 0 or a value greater than 3 also raises an exception.
* **Image format** – `BarCodeImageFormat.Png` provides lossless quality, which is ideal for printing. Use `Jpeg` only when file size is a primary concern.

## Next steps

Now that you know **how to generate barcode** images with custom column and row configurations, you can:

* Integrate the generator into a web API to serve barcode images on demand.  
* Combine the barcode with PDF generation libraries to embed it in invoices.  
* Experiment with other DataBar variants (`DatabarExpanded`, `DatabarLimited`) using the same `Parameters.Barcode.DataBar` object.

For deeper customization—such as changing bar color, adding human‑readable text, or applying QR‑code overlays—refer to the Aspose.BarCode documentation on `BarcodeGenerator` properties.

---

By following this guide you have mastered the **databar expanded stacked** workflow, learned **how to set columns**, **how to set rows**, and produced two distinct barcode images ready for production use. Happy coding!


## What Should You Learn Next?


The following tutorials cover closely related topics that build on the techniques demonstrated in this guide. Each resource includes complete working code examples with step-by-step explanations to help you master additional API features and explore alternative implementation approaches in your own projects.

- [Generate barcode image – GS1 Coupon UPC-A Databar](/barcode/english/net/gs1-barcode-encoding/gs1-coupon-upc-a-databar-configuration/)
- [Create DotCode barcode image – rows & columns (Aspose.BarCode)](/barcode/english/net/dotcode-barcode-configuration/dotcode-rows-columns-configuration/)
- [How to Generate Barcode - One-Dimensional Barcode Types](/barcode/english/net/one-dimensional-barcode-types/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}